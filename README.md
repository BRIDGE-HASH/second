2025 年度新兴人工智能技术全景扫描
📘 项目背景
随着人工智能技术的迅猛发展，2025 年涌现出众多创新成果，涵盖基础模型、硬件生态、行业应用以及开源工具等多个领域。本项目旨在通过系统化的信息收集与分析，全面梳理当年度的 AI 技术进展，辅助研究人员、开发者和决策者把握技术趋势。

🎯 项目目的
利用自动化工具收集并整理 AI 领域的最新资讯和数据。

对收集到的信息进行结构化处理，提取关键指标和情感倾向。

生成高质量的表格数据和中英双语报告，便于后续分析和决策支持。

🛠️ 使用方法
1. 环境配置
安装所需的 Python 库：

bash
复制
编辑
pip install -r requirements.txt
设置环境变量：

bash
复制
编辑
export SERPAPI_KEY='你的_SerpAPI_Key'
export OPENAI_API_KEY='你的_OpenAI_API_Key'
请将上述命令中的 '你的_SerpAPI_Key' 和 '你的_OpenAI_API_Key' 替换为您实际的 API 密钥。

2. 数据收集与处理
运行 code/fetch_search.py 脚本，使用 SerpAPI 获取相关领域的新闻数据。

运行 code/gpt_extract.py 脚本，调用 OpenAI 的 GPT-4 模型对新闻内容进行情感分析和关键词提取。

在 code/notebook.ipynb 中，对处理后的数据进行整理和可视化分析。

3. 输出结果
在 data/ 目录下，生成以下 4 张高精度表格（CSV 格式）：

table1.csv：主要玩家 vs 发布模型 & 参数规模 & 发布时间

table2.csv：近期论文标题 vs 引用次数 vs 关键创新点

table3.csv：硬件型号 vs 理论 FLOPS vs 单价 vs 上架云平台

table4.csv：行业案例 vs 应用场景 vs KPI 对比（Baseline vs AI 驱动）

在 results/ 目录下，生成中英双语综合报告 report.md，约 800-1000 字。

📂 项目结构
bash
复制
编辑
assignment2/
├── README.md                 # 项目说明文档
├── assignment2.md            # 作业说明、个人分工、技术栈等
├── code/                     # 代码文件夹
│   ├── fetch_search.py       # SerpAPI 调用示例
│   ├── gpt_extract.py        # OpenAI API 抽取示例
│   └── notebook.ipynb        # 分析与数据处理的 Jupyter Notebook
├── data/                     # 数据文件夹
│   ├── table1.csv
│   ├── table2.csv
│   ├── table3.csv
│   └── table4.csv
└── results/                  # 结果文件夹
    └── report.md             # 中英双语报告








