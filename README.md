# 从零到 FDE：AI 时代前线部署工程师转型实战课

> 给已有技术基础的人一条从现岗位到 FDE（Forward Deployed Engineer，前线部署工程师）的可执行路径：
> **用一手 JD 定标 → 零成本资源 + 可部署项目补技能 → 按背景产出作品集 → 识别真伪岗位并通过面试。**

`6 篇 · 38 讲` · `含开篇词与结束语共 40 篇正文` · `约 11.6 万汉字` · `187 张手绘插图`

---

## 这门课解决什么问题

MIT NANDA 的调研给出一个数字：95% 的企业 GenAI 试点没有可测的 P&L 影响。demo 能跑和生产能用之间的这道断层，就是 FDE 这个岗位存在的理由——也是 2026 年全年巨头合计承诺投入超 **\$9.85B（近百亿美元）** 把它做成「部署产业（DeployCos）」的原因。

中文世界关于这个岗位的内容大多停在「它是什么」。这门课回答后面三个问题：**怎么转、学什么、怎么学。** 全课基于 2025–2026 年（更新至 2026 年 11 月）一手 JD、薪酬报告与市场分析写成，覆盖 OpenAI（含 DeployCo）、Anthropic（含 Ode with Anthropic 与 Claude Frontier Academy）、Palantir、Google、xAI、微软、AWS、阿里云、腾讯云、火山引擎、字节等中外大厂的真实岗位要求。

## 适合谁

- 有至少一门语言（Python / TypeScript 优先）基础、了解 Web 与 API 的工程师、产品经理或售前
- 想在 AI 落地浪潮里转向「离客户最近、同时还写生产代码」的岗位
- 不满足于科普，要的是可执行的学习计划、作品集选题与面试打法

**不适合**：零编程基础想速成的人；期待「AI 岗位速通秘籍」的人——第 36 讲是认真的劝退章，代价那一面这门课直说。

## 学完你能做到

1. 讲清 FDE 与 SWE / 售前 / 顾问的本质区别，识别「真伪 FDE」岗位
2. 用一手大厂 JD 给自己定标，列出个人能力差距与补齐优先级
3. 掌握 2026 最新版 FDE 技术栈（context engineering / evals / agent + MCP v2 与 OAuth 2.1 / 检索光谱）并产出可部署项目
4. 按自身背景走完一条 90 天转型路径，产出 3 个作品集与一份改写后的简历
5. 通关 FDE 面试（AI 辅助编码轮、decomposition 案例、agentic eval 设计题、client simulation 与行为面），并清醒评估 offer

## 怎么读

| 你的情况 | 路径 | 大致投入 |
|---|---|---|
| 没听过 FDE，先判断值不值得转 | 01 → 04 → **36（先看代价）** → 再决定 | 半天 |
| 已确定要转，补能力 | 05 → 10 定标，11 → 21 逐个技能点做项目 | 8–12 周 |
| 能力够了，准备投简历 | 22 → 29 选路径出作品集，30 → 35 打面试 | 3–4 周 |
| 已经在岗，想走得更远 | 37 → 38 | 一晚上 |

每讲末尾都有产出物（速查卡、自查表、可部署项目），建议边读边做。第 21 讲的 Capstone 是作品集主件。

---

## 目录

- [**开篇词**](course/00%20开篇词.md) — 为什么写这门课、怎么用它

### 认知篇

> FDE 到底是什么、为什么 2026 年它成了「部署产业」，以及在中国语境里怎么定位。

- **01** [95% 的试点死在哪里：FDE 为什么存在](course/01%20%5B认知篇%5D%2095%25%20的试点死在哪里：FDE%20为什么存在.md)  
  <sub>一句话定义、4×4 边界判据、demo→生产断层</sub>
- **02** [2026 巨头军备竞赛：这不是风口是重组](course/02%20%5B认知篇%5D%202026%20巨头军备竞赛：这不是风口是重组.md)  
  <sub>全年时间线、$9.85B+ 投入、数据多口径、"FDE is dead" 与 Gartner 预警述评</sub>
- **03** [四类入口：组织形态图谱与你该投哪](course/03%20%5B认知篇%5D%20四类入口：组织形态图谱与你该投哪.md)  
  <sub>内部事业部 / 资本化 DeployCos / SaaS+SI / 咨询旁路、职位变体</sub>
- **04** [中国语境：洋名换皮还是真机会](course/04%20%5B认知篇%5D%20中国语境：洋名换皮还是真机会.md)  
  <sub>云厂商与独角兽分化、上海首批 274 名 FDE 职称、工信部政策、真伪三判据</sub>

### 能力篇

> 把中外大厂 JD 逐字拆开，定出你要长成的样子，再反推个人差距。

- **05** [T 型能力地图：40% 写码 + 60% 面客](course/05%20%5B能力篇%5D%20T%20型能力地图：40%25%20写码%20+%2060%25%20面客.md)  
  <sub>三层能力结构、RAG 中心→agentic+evals 中心换代</sub>
- **06** [硬门槛技术栈：招聘方真正卡的五项](course/06%20%5B能力篇%5D%20硬门槛技术栈：招聘方真正卡的五项.md)  
  <sub>Python+SQL、五大区分度筛查项、按 JD 频率排序</sub>
- **07** [国际大厂 JD 逐字拆解](course/07%20%5B能力篇%5D%20国际大厂%20JD%20逐字拆解.md)  
  <sub>OpenAI / Anthropic / Palantir / Google / xAI / Harvey / Cursor；动词库 + 金句库</sub>
- **08** [级别与薪酬矩阵：别被年薪百万骗了](course/08%20%5B能力篇%5D%20级别与薪酬矩阵：别被年薪百万骗了.md)  
  <sub>Google 2/5/8/10 年阶梯、equity 55–70%、frontier vs Palantir</sub>
- **09** [国内 JD 与雇主地图](course/09%20%5B能力篇%5D%20国内%20JD%20与雇主地图.md)  
  <sub>腾讯云 / 阿里云 / 火山×安永 / 智谱 / 字节、对标岗映射、驻场补贴、去哪投简历</sub>
- **10** [用 JD 反推个人差距](course/10%20%5B能力篇%5D%20用%20JD%20反推个人差距.md)  
  <sub>以 Anthropic 画像自查、低门槛入口清单、90 天补齐优先级</sub>

### 实战篇

> 以 context engineering 为总纲，每个技能点配零成本资源 + 一个可部署带 eval 的项目，章末即作品集。

- **11** [怎么学：Anthropic Academy 免费证书串 + 中文平行线](course/11%20%5B实战篇%5D%20怎么学：Anthropic%20Academy%20免费证书串%20+%20中文平行线.md)  
  <sub>Claude Academy（原 Anthropic Academy）13 门免费证书链、Pearson VUE 认证 + 中文平行线</sub>
- **12** [客户发现：挖真需求而非客户嘴上要的](course/12%20%5B实战篇%5D%20客户发现：挖真需求而非客户嘴上要的.md)  
  <sub>Mom Test 三原则、需求剥层、先 clarify 再动手</sub>
- **13** [问题分解与 walking-skeleton MVP](course/13%20%5B实战篇%5D%20问题分解与%20walking-skeleton%20MVP.md)  
  <sub>5 步分解法、全程出声推理、Sierra ADLC</sub>
- **14** [Context Engineering：prompt 只是其中一层](course/14%20%5B实战篇%5D%20Context%20Engineering：prompt%20只是其中一层.md)  
  <sub>系统提示 / 检索 / 记忆 / 工具返回整体设计、防注入</sub>
- **15** [评测工程 evals：把 demo 变成能上线的分水岭](course/15%20%5B实战篇%5D%20评测工程%20evals：把%20demo%20变成能上线的分水岭.md)  
  <sub>error analysis 优先、二元 pass/fail、judge 对齐、O'Reilly 新书与工具四象限</sub>
- **16** [检索光谱：从 RAG 到 context architecture](course/16%20%5B实战篇%5D%20检索光谱：从%20RAG%20到%20context%20architecture.md)  
  <sub>chunking / embedding / rerank、agentic search、GraphRAG 成本边界</sub>
- **17** [Agent 编排 + MCP：亲手写一个 MCP server](course/17%20%5B实战篇%5D%20Agent%20编排%20+%20MCP：亲手写一个%20MCP%20server.md)  
  <sub>何时不用 agent、LangGraph 1.x / Claude Agent SDK、MCP v2 规范与 OAuth 2.1</sub>
- **18** [与 coding agent 协作：门槛换轴不降低](course/18%20%5B实战篇%5D%20与%20coding%20agent%20协作：门槛换轴不降低.md)  
  <sub>spec writing、AGENTS.md（AAIF 标准）/ SKILL.md、orchestration 失败模式</sub>
- **19** [企业系统集成、数据工程与私有化部署](course/19%20%5B实战篇%5D%20企业系统集成、数据工程与私有化部署.md)  
  <sub>CRM / ERP / SSO、OAuth 2.1 OBO 防越权、脏数据合规、OTel GenAI 可观测性</sub>
- **20** [赛道选修：computer use 与 voice](course/20%20%5B实战篇%5D%20赛道选修：computer%20use%20与%20voice.md)  
  <sub>OSWorld 2.0 可靠性边界、APA 架构、GPT-Live 1 / Realtime SIP 语音栈</sub>
- **21** [反哺产品与 Capstone：端到端 FDE 模拟交付](course/21%20%5B实战篇%5D%20反哺产品与%20Capstone：端到端%20FDE%20模拟交付.md)  
  <sub>沉淀可复用资产、体面离场（handback packet）、作品集主件、live URL + README</sub>

### 转型篇

> 通用框架 + 四条路径 + 真实案例库，把你现在的背景翻译成 FDE 的入口。

- **22** [通用转型框架与选岗坐标系](course/22%20%5B转型篇%5D%20通用转型框架与选岗坐标系.md)  
  <sub>五步法、Two Archetypes、平台绑定 vs 模型通用</sub>
- **23** [真实案例库：成功、代价与出口](course/23%20%5B转型篇%5D%20真实案例库：成功、代价与出口.md)  
  <sub>Kanav / Het / Milos、Saraf / Barry / Nabeel、Niles 四出口与 Palantir 校友 $265B 版图</sub>
- **24** [产品经理 → FDE](course/24%20%5B转型篇%5D%20产品经理%20→%20FDE.md)  
  <sub>补生产编码 + AI 工程、Deployment Strategist 备选入口、简历改写与话术</sub>
- **25** [前端工程师 → FDE](course/25%20%5B转型篇%5D%20前端工程师%20→%20FDE.md)  
  <sub>前端 -51% vs FDE +361%、补数据工程 + LLM 系统、Vercel 天然入口与绑定风险</sub>
- **26** [后端／数据／ML → FDE](course/26%20%5B转型篇%5D%20后端／数据／ML%20→%20FDE.md)  
  <sub>Palantir 数据流贴身区、别卷 PyTorch、补面客、简历改写与话术</sub>
- **27** [售前／解决方案／顾问 → FDE](course/27%20%5B转型篇%5D%20售前／解决方案／顾问%20→%20FDE.md)  
  <sub>编码强度 moderate→high、咨询系千人军备竞赛与低门槛旁路</sub>
- **28** [非典型背景与国内特有路径](course/28%20%5B转型篇%5D%20非典型背景与国内特有路径.md)  
  <sub>上海 274 名 FDE 职称落地、53AI Echo+Delta、川宁生物与中石油驻场实录</sub>
- **29** [作品集与简历总装](course/29%20%5B转型篇%5D%20作品集与简历总装.md)  
  <sub>3 递进模板、公开写作 = 第四件作品、JD 动词库改简历</sub>

### 求职篇

> 识别真伪岗位、拆解 2026 面试流程与新题型，再学会评估 offer。

- **30** [岗位地图与真伪 FDE 识别](course/30%20%5B求职篇%5D%20岗位地图与真伪%20FDE%20识别.md)  
  <sub>三判据防 FDE Washing、七变体等价头衔、DeployCo / Ode 独立通道</sub>
- **31** [面试流程地图](course/31%20%5B求职篇%5D%20面试流程地图.md)  
  <sub>通用三段式、AI 辅助编码三大阵营（Sierra / Claude Code Round / Work Trial）</sub>
- **32** [Decomposition 案例实战](course/32%20%5B求职篇%5D%20Decomposition%20案例实战.md)  
  <sub>5 步框架、前 10 分钟禁画框图、能跑的糙方案 > 漂亮但跑不通</sub>
- **33** [新题型：agentic eval 设计题](course/33%20%5B求职篇%5D%20新题型：agentic%20eval%20设计题.md)  
  <sub>复用 evals 方法论、两道全解 + $pass^k$ / 轨迹评测 / MCP 防越权高阶追问</sub>
- **34** [Client simulation 与行为面 STAR](course/34%20%5B求职篇%5D%20Client%20simulation%20与行为面%20STAR.md)  
  <sub>暴怒 CTO / 合规 pushback、国内大厂真题、8 个故事、"Why FDE" 最重要</sub>
- **35** [Offer 尽调与谈判](course/35%20%5B求职篇%5D%20Offer%20尽调与谈判.md)  
  <sub>FDE Pulse 四问、OpenAI 无 cliff vs Anthropic S-1 期权拆解、国内反问四刀</sub>

### 成长篇

> 入职后的 90 天、清醒的代价一面，以及长期怎么走。

- **36** [劝退章：入坑前想清楚](course/36%20%5B成长篇%5D%20劝退章：入坑前想清楚.md)  
  <sub>不适合人群、Blind 三大职业隐患、Gartner 70% 裁撤预警、国内薪资真相</sub>
- **37** [上手 90 天路线图](course/37%20%5B成长篇%5D%20上手%2090%20天路线图.md)  
  <sub>Salesforce 6 周 onboarding + pod 制、handback packet 体面离场与五坑自救</sub>
- **38** [长期出路与持续学习](course/38%20%5B成长篇%5D%20长期出路与持续学习.md)  
  <sub>Niles 四出口、四个高薪新邻居岗、2026 年底凭证策略与订阅书单</sub>

- [**结束语**](course/结束语.md) — 写在最后

---

## 仓库结构

```
.
├── README.md                       本文件（总入口）
└── course/
    ├── 00 开篇词.md … 38 ….md      正文 40 篇
    ├── 结束语.md
    └── assets/                     187 张插图
```

大纲、调研原始材料、生成脚本与状态文件保留在本地，未入库。

## 插图怎么来的

全书插图统一「细线条手绘 + 米黄纸质背景 + 墨绿（#0E6E62）点缀」风格，由本地脚本批量生成：扫描正文里的 `[[HERO:]] / [[FIG:]] / [[CHAPTER:]]` 占位符 → 调用图像模型 → 就地替换为 `![](assets/xxx.png)`。

## 数据口径与免责

- 薪酬、市场规模、投入金额均标注来源与时间口径，已全量更新至 **2026 年 11 月**公开数据；引用前请回查原始来源。
- 逐字拆解的 JD 是撰写与修订时的版本，用作方法示范，不等于当前实时在招要求。
- 本课不承诺求职结果。第 35 讲「Offer 尽调」与第 36 讲「劝退章」是这门课诚实度的一部分，别跳过。

## 友情链接

- [LINUX DO](https://linux.do) — 新的理想型社区

## 版权

个人创作内容，保留所有权利。转载或商用请先联系。
