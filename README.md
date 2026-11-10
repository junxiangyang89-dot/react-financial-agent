# ReAct Financial Agent

一个 A 股问答小项目。可以查年报、财务指标和历史股价，并在网页上查看工具调用过程。同一套工具有两种调用方式：手写 ReAct 和 Function Calling。

## 运行

需要 Python 3.12。Windows 下请把仓库克隆到不含中文的路径（如 `D:\code\react-financial-agent`），以便 FAISS 读取索引。在仓库根目录运行以下 PowerShell 命令。

```powershell
python -m pip install -r requirements.txt
$env:DASHSCOPE_API_KEY = '你的阿里云百炼 API Key'
# 使用 Function Calling 时再配置
# $env:DEEPSEEK_API_KEY = '你的 DeepSeek API Key'
python -m uvicorn serve:app --app-dir src --host 127.0.0.1 --port 8000
```

打开 [本地网页](http://127.0.0.1:8000)，试试「海康威视 2023 年年报披露了哪些主要风险？」

手写版默认用 `qwen-max`，Function Calling 默认走 DeepSeek。年报查询通过百炼 `text-embedding-v3` 编码，复用仓库里的 FAISS 索引。行情和财务数据由 AkShare 获取。

## 评估

[评估报告](report/evaluation_report.md)记录了两个模式同用 `deepseek-flash` 时的 5 道题结果，附逐题耗时、Token 用量和工具调用记录。

源码采用 [MIT 许可证](LICENSE)。年报片段来自上市公司公开披露文件，见[数据说明](vectorstore/README.md)。
