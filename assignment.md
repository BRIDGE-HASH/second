本次作业围绕“2025年度新兴人工智能技术全景扫描”和“全球主要国家新冠疫苗接种策略对比”两大主题，采用 SerpAPI（或自定义搜索）、OpenAI GPT-4-turbo API，利用 Python 脚本与 Jupyter Notebook 实现数据抓取、清洗、信息抽取和报告生成。


## 二、`assignment2.md` 主要内容

### 2.1 主题一：2025年度新兴人工智能技术全景扫描

#### a) 选题理由、子任务与执行流程

* **选题理由**：随着大规模预训练模型的商业化落地，行业对模型性能、算力和生态工具的需求迅速增长，需要详尽的技术全景扫描来把握趋势。
* **子任务划分**：

  1. **基础模型及预训练**：统计 OpenAI、Google DeepMind、Meta、Anthropic 等主要玩家及其最新公开论文、模型参数规模。
  2. **硬件与算力**：收集 NVIDIA H100 Tensor Core GPU 性能指标（最高达30×推理加速）及 Hopper 架构详细说明，并查询 AWS GPU 云实例（如 G4/T4、A100/H100）的价格与可用区域。
  3. **行业应用与落地**：梳理金融风控、智能制造、医疗影像等典型案例，记录准确率、召回率等量化指标。
  4. **开源社区与工具**：分析 Hugging Face、PEFT、LoRA 等项目的 GitHub stars、issues 数量，衡量社区活跃度。
* **执行流程**：

  1. 用 SerpAPI 拉取各领域前 10 条搜索结果；
  2. 用 HTTP + `requests` 解析 JSON；
  3. 通过 GPT-4-turbo 提示链（Chain-of-Thought）抽取结构化信息；
  4. 汇入 Pandas DataFrame，输出 CSV/JSON 表格；
  5. 在 Jupyter 中生成可视化图表并提炼报告段落。

 b) 个人分工与工时

> **我负责全部步骤**

* 数据采集与脚本编写
* GPT-4 提示设计与抽取
* 数据清洗与表格生成
* 可视化与报告撰写
* 文档编写与校对

 c) API Key 配置方法

* SerpAPI：在环境变量中设置 `SERPAPI_KEY`；HTTP 请求示例见 `fetch_search.py`。
* OpenAI：在环境变量中设置 `OPENAI_API_KEY`；调用示例见 `gpt_extract.py`。

 d) 输出格式及使用说明

* 表1**：主要玩家 vs 发布模型 & 参数规模 & 发布时间（theme1\_table1.csv）
* **表2**：近期论文标题 vs 引用次数 vs 关键创新点（theme1\_table2.csv）
* **表3**：硬件型号 vs 理论 FLOPS vs 单价 vs 上架云平台（theme1\_table3.csv）
* **表4**：行业案例 vs 应用场景 vs KPI 对比（Baseline vs AI 驱动）（theme1\_table4.csv）
* 所有表格均提供 JSON 与 CSV 格式，便于脚本二次处理。

---

 2.2 主题二：全球主要国家新冠疫苗接种策略对比

 a) 选题理由、子任务与执行流程

* **选题理由**：新冠疫苗在不同国家的研发平台、接种优先级、冷链物流和公众接受度存在显著差异，系统化对比有助于公共卫生决策。
* **子任务划分**：

  1. **疫苗类型与研发进度**：mRNA、腺病毒载体、灭活、蛋白亚单位；对比临床三期有效率。
  2. **接种政策与优先人群**：美国、英国、中国、印度、巴西等国家的优先接种人群与接种间隔政策。
  3. **分发与冷链物流**：主要供应商冷链标准、运输成本和丢弃率估算。
  4. **接种效果与公众态度**：接种率、重症/住院率变化（Our World in Data 数据）；社交媒体舆情分析（微博、Twitter）。
* 执行流程：同主题一，先抓取政策文档与新闻，再用 GPT-4 提取结构化指标，最后汇总成表并撰写报告。

 b) 个人分工

> 我负责全部步骤

* 政策与文献检索
* GPT-4 信息抽取
* 数据清洗与表格制作
* 舆情分析与图表
* 文档撰写与翻译

c) API Key 配置方法

* 与主题一相同，环境变量 `SERPAPI_KEY`、`OPENAI_API_KEY` 即可复用。

#### d) 输出格式及使用说明

* **表1**：国家 vs 疫苗平台 vs 三期有效率（theme2\_table1.csv）
* **表2**：国家 vs 接种优先级别 vs 政策发布日期（theme2\_table2.csv）
* **表3**：供应商 vs 冷链标准 vs 成本 & 丢弃率（theme2\_table3.csv）
* **表4**：国家 vs 接种率 vs 重症/住院率变化（theme2\_table4.csv）

---

## 三、参考文献

1. **AI Index Report 2025**: 最全面的年度 AI 发展监测报告
2. **NVIDIA H100 Tensor Core GPU**: 高性能推理与训练指标介绍
3. **NVIDIA Hopper 架构深度解析**: H100 Tensor Core 创新设计说明
4. **AWS EC2 On-Demand Pricing**: 云 GPU 按需定价与计费模型
5. **AI in Finance Use Cases**: 金融风控与欺诈检测案例概览
6. **PEFT & LoRA 开源项目**: 参数高效微调工具生态活跃度
7. **Foundation Model Players**: OpenAI、DeepMind、Anthropic 等市场格局
8. **mRNA-1273 疫苗三期试验结果**: 疫苗有效率与安全性报告
9. **COVID-19 Vaccine Policy Dataset**: 185国接种政策面板数据集
10. **Our World in Data COVID-19 Vaccinations**: 全球接种率实时统计
11. **WHO Vaccine Delivery Cost Guidelines**: 冷链与物流成本估算方法
12. **Public Perception of COVID-19 Vaccines**: 社交媒体情感分析研究
