---
n: 16
chapter: "实战篇"
title: "检索光谱：从 RAG 到 context architecture"
chapter_order: 6
generated_at: "2026-07-15T00:00:00Z"
generated_by: "create-course-skill"
author: "anonymous"
---

上一讲我们把 evals 立成了分水岭：没有它，流畅的输出会掩盖错误，迭代会原地打转。这一讲换个角度——你搭出来的那套系统，靠什么把正确答案喂给模型？答案十有八九会指向一个词：RAG。但这两年网上到处是「RAG is dead」的标题，你可能已经被搞懵了：到底还学不学？

我的结论先给你：RAG 没死，它只是从主角降成了 agent 的记忆层。真正该学的不是某一条管线，而是「检索光谱」——从传统 RAG 到 agentic search 再到 context architecture 的一整条谱系。这一讲我带你把这条谱走一遍，最后落到你能上手的项目 3。

![一个工程师盯着「RAG is dead」的热搜标题，手边却是一份客户要你三天上线的检索需求](assets/L16-hero.png)

## 别把 RAG 当主线，先看清整条光谱

先记结论：RAG 不是一门独立主课，它是检索光谱上的第一段。看懵了也没关系，我先给你一张地图，再逐段展开。

这条光谱从左到右是四段：传统 RAG → agentic RAG → agentic search → context architecture。左边最「死板」——一次检索、一次生成；越往右，模型越像个会自己找资料的人，能多轮、能反思、能决定要不要检索。你要学的不是背下每一段，而是知道什么场景落在哪一段。

![检索光谱四段：从一次性 RAG 到会自己找资料的 context architecture](assets/L16-retrieval-spectrum.png)

传统 RAG 这一段还是得先吃透，它是你理解后面所有花样的地基。它就三步：切块（chunking）、向量化（embedding）、召回后重排（rerank）。说个你能对上的场景：这就像你把一本厚厚的客户手册撕成一张张便利贴，给每张贴一个「气味标签」，用户来问的时候，你按气味最接近的先抓几张出来，再快速挑出最相关的塞给模型。

```python
# 传统 RAG 三步的骨架（伪代码，说明流程用）
chunks = split_document(doc, size=512, overlap=64)   # 1. chunking
vectors = embed(chunks)                              # 2. embedding
store.upsert(vectors)

def answer(query):
    hits = store.search(embed(query), top_k=20)      # 召回
    ranked = rerank(query, hits)[:5]                  # 3. rerank
    return llm(build_prompt(query, ranked))          # 一次生成
```

这里每一步都有坑，而坑就是 FDE 的活。切块切太大，噪声进来；切太小，语义断掉。重排这一步最容易被新手省掉，但它往往是召回质量从 60 分到 85 分的关键。

![切块大小的取舍：太大混入噪声，太小切断语义](assets/L16-chunk-size-tradeoff.png)

向量库怎么选，也别一上来就纠结。我的建议很直接：**先用 pgvector 起步**。你手上大概率已经有 Postgres，装个扩展就能跑，数据和业务表在同一个库里，省掉一套运维。等你的数据量、并发、过滤需求真的把 pgvector 压不住了，再去懂 Pinecone、Weaviate 这类专用向量库的取舍——托管省心但要按量付费、要多维护一套系统。传统做法是团队一开工就上专用向量库，结果三个人维护一套用不满的基础设施；FDE 做法是 pgvector 先跑通业务，用真实压力数据去证明「该换了」再换。

![先 pgvector 跑通，再用真实压力证明该换专用向量库](assets/L16-pgvector-first.png)

## 从 agentic RAG 到 agentic search

结论先行：光谱越往右，「检索」这个动作越不再是固定的一次，而是模型自己决定的一连串动作。这一节的核心变化，是把检索的控制权交给 agent。

传统 RAG 是「先检索、再回答」，一锤子买卖。agentic RAG 把这个动作变成可以反复做的工具：模型看一眼问题，觉得不够，就再检索一次；换个关键词，再检索一次；甚至先检索一批，读完发现方向错了，回头改查询。就像你查资料，很少一次搜索就搞定，通常是搜一下、看两眼、再换词搜——agentic RAG 让模型也这么干。

```python
# agentic RAG：把检索包成一个工具，交给模型自己决定何时调、调几次
def search_tool(query: str) -> list[str]:
    hits = store.search(embed(query), top_k=10)
    return [h.text for h in rerank(query, hits)[:5]]

# agent 循环里，模型可以多轮调用 search_tool，直到自认为证据够了
agent = Agent(tools=[search_tool], stop_when="evidence_sufficient")
```

![agentic RAG：模型多轮调用检索工具，直到证据够了才回答](assets/L16-agentic-rag-loop.png)

再往右一段更颠覆，叫 agentic search。这里有个能让你重新审视整条光谱的数据：Amazon Science 测出来，用 agentic 关键词搜索的方式，**达到了 RAG 忠实度的 94.5%，而且零向量库**。你没看错——不切块、不做 embedding、不维护向量库，让 agent 像人一样用关键词去搜、去翻、去交叉验证，效果逼近了那套重管线。

别急，这不等于向量库要扔。它的意思是：当你的数据本身就带好的搜索接口（比如企业内网搜索、日志系统、数据库全文检索），你可能根本不需要先建一套向量管线。FDE 的判断力就体现在这儿——不是所有场景都值得上向量库，有时候一个好用的 search API 加一个会用它的 agent，就够了。

![agentic search：零向量库，靠关键词搜索逼近 94.5% 的 RAG 忠实度](assets/L16-agentic-search-zero-vector.png)

我把三段的取舍给你摆一张表，你选型时对着看：

| 段位 | 检索次数 | 要不要向量库 | 适合场景 |
|---|---|---|---|
| 传统 RAG | 固定一次 | 通常要 | 静态文档库、问答明确 |
| agentic RAG | 模型决定多次 | 要 | 需要多轮找证据、问题发散 |
| agentic search | 模型决定多次 | 可不要 | 已有好搜索接口的系统 |

![三段检索方式的取舍对照表](assets/L16-spectrum-tradeoff-table.png)

## context architecture：检索只是记忆层的一种

先给判断：光谱的最右端不是「更强的 RAG」，而是压根换了个问法——不再问「怎么检索」，而问「模型这一步该看到什么」。这就是 context architecture，上一讲评测、这一讲检索，其实都在为它服务。

把视角拉高你会发现，检索回来的文档，只是模型上下文里的一层。完整的上下文是好几层叠起来的：系统提示、检索注入、记忆（历史对话、用户偏好）、工具返回、agent 的状态。RAG 负责的，就是「检索注入」这一层。所以「RAG 未死」的准确说法是：**它是 agent 的记忆层**，是 context architecture 里负责「从外部知识调取相关片段」的那块。

![context architecture 分层：RAG 只是「检索注入」这一层](assets/L16-context-layers.png)

这也是为什么「RAG is dead」是标题党。死掉的不是检索，是「以为搭好一条 chunk-embed-rerank 管线就完事」的心态。传统做法是把 RAG 当终点，管线跑通就交付；FDE 做法是把 RAG 当 context architecture 的一个组件，去问「这一层该注入什么、注入多少、和别的层怎么配合、token 预算够不够」。这也呼应了整门课的换轴——从 prompt engineering 到 context engineering，「prompt engineer」这个职位名基本已经消失了。

对你的实际动作是什么？两条。第一，别再把「我会 RAG」写进简历当卖点，招聘方现在默认你会，他们要看的是你能不能设计整层上下文。第二，你每做一个检索项目，都顺手画一张「上下文架构图」——这一步喂给模型的东西，分别来自哪几层。这张图，就是你区别于「只会调 API」的人的证据。

## 项目 3：同一份数据，两个版本，一张对比表

结论先给：这一讲最值钱的产出，是一个能挂 live URL 的对比项目。它一次性证明你会检索、会 evals、还会写作——一石三鸟。

具体怎么做，我给你拆成四步。选一份真实、够脏的数据集（客服工单、产品文档、政务问答都行），然后在**同一份数据**上做两版实现：

1. **传统 RAG 版**：pgvector + chunk/embed/rerank，就是本讲第一节那套。
2. **agentic search 版**：给 agent 一个 search 工具，让它多轮自己找，尽量少依赖甚至不依赖向量库。
3. **用你上一讲搭的 eval harness 去测两版**：同一套测试集、同一个二元 judge，量忠实度和成本。别只报「感觉 agentic 更好」——报数字。
4. **写成一篇对比博客 + 部署出一个 live URL**：把前后指标摆成一张表，讲清楚哪个场景该选哪版。

```text
# 对比报告该长这样（示意）
数据集：某公司 1200 条客服工单
              忠实度    平均延迟   单次成本   维护复杂度
传统 RAG        86.0%     0.8s      $0.004     要维护向量库
agentic search  81.5%     2.3s      $0.011     零向量库
结论：静态高频问答用传统 RAG；长尾、需交叉验证的用 agentic search
```

![项目 3：同一数据集，传统 RAG 与 agentic search 两版并排对比](assets/L16-project3-two-versions.png)

为什么非要两版对比、而不是只做一个「更潮」的 agentic 版？因为 FDE 的价值不是「我用了最新技术」，而是「我能替客户判断该用哪种」。一张带真实数字的对比表，比十句「我熟悉 agentic RAG」都有说服力。记住这门课反复讲的那条：作品集的 live URL 加 eval 指标，胜过任何证书，一个部署项目 60 秒就能被验证。

![一个能打开、带指标的 live URL，胜过一摞证书](assets/L16-live-url-portfolio.png)

## 小结

RAG 没死，它降级成了检索光谱的第一段、agent 的记忆层。这条光谱从传统 RAG（chunk/embed/rerank，pgvector 先起步）走到 agentic RAG、再到零向量库也能逼近 94.5% 忠实度的 agentic search，终点是把检索当作一层的 context architecture。别被「RAG is dead」的标题党带偏——死的是把管线当终点的心态。你的动作很明确：做项目 3，同一份数据两版实现、一张对比表、一个 live URL。

## 思考题

回到你自己手头或想做的那个检索场景：如果只允许你做一版，你会选传统 RAG 还是 agentic search，判断依据是什么——是数据在不在向量库里、是延迟成本能不能接受，还是客户有没有现成的搜索接口？把你的选型逻辑写下来，它就是下一讲《Agent 编排 + MCP：亲手写一个 MCP server》里，你给检索工具接上「插头」的起点。欢迎在评论区聊聊你的想法。
