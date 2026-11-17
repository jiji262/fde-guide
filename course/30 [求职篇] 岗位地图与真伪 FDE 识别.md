---
n: 30
chapter: "求职篇"
title: "岗位地图与真伪 FDE 识别"
chapter_order: 1
generated_at: "2026-07-15T00:00:00Z"
generated_by: "create-course-skill"
author: "anonymous"
---

上一讲我们把你手里的东西总装成了求职资产：三个递进作品集（带 eval 的端到端检索应用、Agentic RAG+MCP、多智能体研究助手），加上一份全用 "I" 改写的简历。武器备好了。这一讲要解决的是另一半问题：你该拿这套武器去打哪个靶子？

因为市面上挂着 "FDE" 牌子的岗位，大概有三成根本不是 FDE——是套了个时髦头衔的售前。你冲着"写进客户生产环境的代码"去，结果入职发现自己在背 quota、做可抛弃的 demo。这一讲的目标就一句话：教你在投简历之前，隔着 JD 就把真岗和假岗分出来。

![一个工程师面前摊开十几张招聘卡片，其中几张背面盖着红色"售前"印章，他正拿放大镜逐张看](assets/L30-hero.png)

[[CHAPTER:1 | 一张多轮面试的关卡地图，最后一关写着 "Why FDE?"]]

## 三判据：隔着 JD 就分真伪

先给结论：判断一个岗位是不是真 FDE，只看三件事——有没有 quota、写不写生产代码、售后嵌不嵌入并反哺产品。三条都对，是真的；缺一条，你就要警惕。

**第一刀，切薪酬结构。** 真 FDE 是工程岗，不是销售岗。数据很干脆：约 70% 的 FDE JD 里含股权，只有 8% 提到 OTE 或提成。所以你打开一份 JD，先搜 "quota"、"OTE"、"commission"、"bookings" 这几个词。搜到了，警报拉响——按销售业绩计酬的，本质是售前。真 FDE 的成功标准是别的东西，OpenAI 写得最清楚：

> "production adoption, measurable workflow impact, and eval-driven feedback that changes product and model roadmaps"

你看，衡量他的是"生产环境的采纳、可测的工作流影响、反哺路线图的 eval 反馈"，没有一个字提到签了多少单。这就像看一个厨师，你是看他今天卖了多少份，还是看他的菜有没有真的被端上桌吃掉——FDE 是后者。

[[FIG:three-tests-flow | 三判据决策流：quota→生产代码→售后反哺，任一为否即偏售前]]

**第二刀，切交付物。** 售前交付什么？可抛弃的 demo，谈完单就扔。FDE 交付什么？进客户真实环境、还得长期跑的耐用代码。Anthropic 的 JD 把交付物写到了逐字级别：

> "Deliver technical artifacts for customers like MCP servers, sub-agents, and agent skills that will be used in production workflows."

MCP server、子代理、agent skills，而且后面跟着 "used in production workflows"。这不是 PPT，是要上线被人用的东西。Cursor 说得更狠，直接甩一句 "These aren't prototypes."（这些不是原型）。所以你读 JD 时盯住动词：own、ship、harden、productionize 是真交付的味道；present、demo、showcase 偏售前。

**第三刀，切生命周期和闭环。** 这一刀最容易被忽略，但最关键。传统售前是"售前置"——签单之前上，签完就交给别人。FDE 是"售后嵌入"——签单之后才进场，而且驻场做完还得把一线洞察反哺回产品。腾讯云的中文 JD 把这层意思写得很直白：

> "将一线经验沉淀为可复用的交付资产与行业方案模板，反哺产品。"

"反哺"两个字是分界线。没有这个闭环的岗位，哪怕它让你写代码、让你驻场，也只是个高级实施，不是 FDE。别急，你现在记不住三条也没关系，本讲末尾我给你一张能直接对着 JD 打勾的 checklist。

## 按公司类型分层：真伪不是一刀切

这里要纠正一个新手最容易犯的错：以为"FDE"这个词本身有统一标准。没有。同一个头衔，在不同类型的公司里含金量差很远。所以正确的读法不是逐个 JD 死磕，而是先看这家公司属于哪一层，心里就有了底。

我把它分成四类，你对着投就行：

| 公司类型 | 代表 | FDE 真伪 | 你要注意什么 |
|---|---|---|---|
| Frontier lab | OpenAI / Anthropic | 纯交付岗 | evals 面试权重极高，MCP 是硬门槛 |
| AI-native 应用 | Cursor / Harvey / Sierra | 纯交付岗 | 反 prototype，per-client eval harness |
| 平台绑定型 | Vercel / Snowflake | 含售前成分 | 技能锁定单一栈，评估可迁移性 |
| 咨询旁路 | Deloitte / Accenture / 火山×安永 | 交付+实施混合 | 门槛较低（1 年 GenAI 起），脏活比例高，防外包化 |

[[FIG:company-layers | 四类公司分层图：越靠 frontier lab 越纯交付，越靠平台/咨询售前成分越高]]

**Frontier lab 和 AI-native，基本闭着眼是真交付。** OpenAI、Anthropic、Cursor、Harvey、Sierra 这一档，JD 白纸黑字写着 post-sales、写着 evals 作为成功标准、写着"不是原型"。而且 Plank 在 2026 年 Q3 的招聘追踪揭示了一个关键结构：**全球约 90% 的在招 FDE 岗位集中在初创与高增长 AI-native 公司**（Lenny's Newsletter 2026 年 11 月统计在招总量约 1,500 个，同比暴涨 361%）。Harvey 甚至把整条工作流压进一句：

> "Design → prototype → productionize custom workflows … then harden them for reliability, observability, and scale."

从设计到硬化上线，一条龙全是你的活。这种岗位你不用怀疑真伪，要怀疑的是自己够不够格。

**但平台绑定型，你得多留个心眼。** 最典型的是 Vercel——它的 FDE JD 里明确含 pre-sales 成分，而且把 TypeScript 写成 "this is your primary language"，深度绑死 Next.js 和它自家的 AI SDK。这不是说 Vercel 的岗位不好，而是它跟 Anthropic 的 FDE 是两种物种。这就像你去应聘"全科医生"，结果一家是真的什么都看，另一家其实主要是替医院拉病人、顺带看点小病。你冲哪个去，得心里清楚。所以碰到平台型 FDE，先搜 pre-sales，再问自己：这套栈两年后我还带得走吗？

**咨询旁路是转型者的低门槛入口，但要防"FDE Washing（伪 FDE 洗白）"。** Deloitte 的栈绑定 FDE（Palantir/Anthropic/AWS/Databricks 等通道）只要 1 年 GenAI 经验，埃森哲×Google Cloud、安永×火山引擎也在成千人地扩招，是门槛最友好的口子。代价是部分团队容易滑向按人天卖苦力的传统实施。国内也是同理——真正的 FDE 主力集中在云厂商（阿里云、腾讯云、火山引擎）和头部应用商；大模型独角兽里月之暗面 Kimi、MiniMax、阶跃星辰在 2026 秋招已开放少量战略大客户 FDE，唯独死磕基础研究的 **DeepSeek** 坚持零 FDE 编制。你要是盯着 DeepSeek 投 FDE，方向就错了。

## 七个头衔一起搜，别漏掉独立 JV 暗道

结论先行：如果你只在招聘网站搜 "Forward Deployed Engineer" 这一个词，你会漏掉一大半真岗。因为到 2026 下半年，这个角色的职位名已经裂解成至少七个常见变体，各家爱叫啥叫啥。

你要一次把这七个词都撒下去：

```text
Forward Deployed Engineer
Forward Deployed Software Engineer (FDSWE / FDSE)
Frontier Deployed Engineer
Deployment Strategist
Agent Engineer
AI Solutions Engineer / Customer Solutions Engineer
Field Engineer
```

同一个岗位，OpenAI 有平行的 FDSWE（7+ 年、$185–325K，专做交付抽象层），Anthropic 在 2026 年 10 月推出了"Frontier Deployed Engineer"体系，Palantir 的 Echo 线叫 Deployment Strategist，Sierra 干脆叫 Agent Engineer（$280–410K）。名字不同，内核一样：嵌入客户、把 agent 系统带上生产。你把这串词做成一个搜索清单，每周固定跑一遍，覆盖面立刻翻倍。

[[FIG:six-titles-map | 六个等价头衔汇聚到同一个 FDE 内核的辐射图]]

**还有一条大多数人不知道的暗道：资本化 DeployCos / JV 的独立招聘通道。** 2026 年这场累计承诺资本突破 **98.5 亿美元**的交付实体竞赛，催生了一批独立法人公司，它们不走母公司的招聘主页，自己单独招人：
- **OpenAI 的 Deployment Company（官网 `deploy.co`）**：TPG、Advent、Brookfield 等出资超 40 亿美元，先收购伦敦 Tomoro 拿下约 150 名 FDE，2026 年 7 月又全资收购了 Palantir 年度最佳合作伙伴 **Northslope**，在美欧亚大举独立扩招。
- **Ode with Anthropic（招聘页 `jobs.ashbyhq.com/ode-with-anthropic`）**：由前 BCG 管理层联合 Anthropic 与 Blackstone/高盛资本支持组建的 15 亿美元交付合资企业，甚至首创了 **BYOT（Bring Your Own Team）** 通道——允许两三个配合默契的工程师/策略师组队一起投递！

[[FIG:jv-hidden-channel | 母公司招聘页之外，DeployCo 等 JV 实体的独立招聘入口]]

这些 JV 是什么意思？意思是招聘入口在母公司官网之外。你只刷 `openai.com/careers` 或 `anthropic.com/careers`，是刷不到 `deploy.co` 和 `Ode with Anthropic` 的岗位的。所以你的投递清单里要专门留一栏给这些独立交付实体（也可以参考追踪站 `deploycos.com`）。传统做法是盯着大厂招聘主页刷；FDE 求职的正确做法是——母公司主页、等价头衔、JV 独立通道，三条线并行。

顺便说一句门槛：别被"要 5 年经验"吓住。Google FDE I、Scale、Harvey Founding、微软 IC3 都是 2 年档，Deloitte 只要 1 年 GenAI，BCG 甚至开了校招 FDE 通道。有个真实例子，Kanav Bhatnagar 24 岁、毕业约 3 年，就进了 Rippling 当创始 FDE。年限从来不是你不敢投的理由。

## 真伪识别 checklist：投前逐条打勾

说了这么多，我把它压成一张你能直接用的清单。打开任何一份挂着 FDE 名头的 JD，对着下面十条过一遍：

**红旗（出现就警惕，越多越可能是售前）**
- [ ] JD 里出现 quota / OTE / commission / bookings
- [ ] 成功标准是"签单"而非"生产采纳"
- [ ] 交付物是 demo / POC / showcase，且用完即弃
- [ ] 岗位在售前置阶段介入（pre-sales / pipeline）
- [ ] 只做配置，不碰产品能力边界之外的开发

**绿旗（出现越多越可能是真交付）**
- [ ] 明确 post-sales / 交付后嵌入客户团队
- [ ] 交付物点名 MCP server / sub-agents / production code
- [ ] 成功标准含 evals、workflow impact、production adoption
- [ ] 有"反哺产品/路线图"的闭环表述
- [ ] 动词是 own / ship / harden / productionize

[[FIG:checklist-card | 一张红绿双栏的真伪识别打勾卡]]

用法很简单：红旗过半，基本可以判定是套壳售前，你想清楚再投；绿旗过半，才是你这套作品集该瞄准的靶子。有一个边界情况要提醒你——Vercel 型平台岗会同时亮起绿旗和红旗（既写生产代码，又含 pre-sales），这时候别纠结真伪标签，回到上一节的分层判断，问自己"技能可迁移性"这一条能不能接受。

所以你现在该做什么？把你上一讲整理好的投递清单拿出来，逐个公司标上它属于哪一层、亮了几个绿旗，再补上六头衔搜索和 JV 通道两栏。这张表做完，你的求职就从"海投"变成了"精准打击"。

## 小结

真伪 FDE 就看三条：有没有 quota、写不写生产代码、售后嵌入并反哺产品。别指望单一标准，要按公司分层——frontier lab 和 AI-native 是纯交付真岗，Vercel 型平台厂商含售前成分，咨询旁路门槛低但脏活多。搜岗时六个等价头衔一起撒，别漏掉 DeployCo 这类 JV 的独立通道。投前用红绿 checklist 逐条打勾，把海投变成精准打击。下一讲，我们进面试流程地图，看这些真岗到底怎么一关关考你。

## 思考题

拿你现在最想投的那家公司的 FDE JD，对着本讲的红绿 checklist 逐条打勾，数一数它绿旗几个、红旗几个——它到底是真交付岗，还是套了壳的售前？如果是平台绑定型，它那套技术栈两年后你还带得走吗？欢迎在评论区聊聊你的想法。
