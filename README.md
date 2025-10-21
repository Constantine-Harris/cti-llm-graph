# CTI-LLM-Graph （威胁情报 × 大模型 × 攻击图谱）

## 项目简介
多源网络威胁情报（报告/IOC/日志/代码） → 大模型抽取（IoC/TTP/事件三元组） → 融合为攻击知识图谱 → RAG增强 → 联邦学习（隐私保护）与少样本实时检测 → 推理下一步攻击与防御建议。

## 目录结构
- `docs/` 写作与图表
  - `paper/` 论文内容（outline、草稿、图表引用）
  - `figures/` 图片
  - `tables/` 表格（相关工作对比等）
- `papers/` 文献PDF与导出引用文件
- `data/` 外部知识库（ATT&CK等）
- `datasets/` 数据集与标注（含 mini-benchmark）
- `src/` 代码
  - `extract/` 抽取：实体/事件/TTP
  - `rag/` 检索增强
  - `fusion/` 实体对齐与融合
  - `graph/` 图谱构建/导出
- `experiments/` 实验脚本与结果
- `requirements.txt` 依赖
- `LICENSE` 开源协议

## 快速开始
1. `conda create -n cti python=3.11 -y && conda activate cti`
2. `pip install -r requirements.txt`
3. 打开 `docs/paper/outline.md` 按大纲写作，数据与代码按模块推进。

## 目标与评测（简述）
- 抽取：NER/TTP/事件三元组（P/R/F1）
- 融合：实体对齐正确率、事件链一致性
- 图谱：覆盖率与错连率
- 日志检测：ROC-AUC、PR-AUC
- 联邦：联邦vs各自本地的相对提升Δ
- 端到端：从IOC到图谱的闭环耗时、可读性评分
