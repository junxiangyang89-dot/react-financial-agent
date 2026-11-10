# 年报检索数据

`faiss_index.bin` 和 `faiss_meta.json` 配套使用。索引有 10,353 条 1024 维向量，由 `text-embedding-v3` 生成。

文本来自贵州茅台（600519）、五粮液（000858）、宁德时代（300750）、中国平安（601318）和海康威视（002415）公开披露的 2021–2023 年年度报告。每条记录保留公司代码、年份和页码，可在[上海证券交易所](https://www.sse.com.cn/disclosure/listedinfo/regular/)或[巨潮资讯网](https://www.cninfo.com.cn/)查询原文。仓库的 MIT 许可证适用于项目源码，年报材料的权利归原权利人。
