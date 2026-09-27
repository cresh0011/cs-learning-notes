# hs-title-cls

> 中文商品标题文本分类 Demo —— 模拟电商场景下的 HS 编码归类

- **仓库**：https://github.com/cresh0011/hs-title-cls （公开）
- **本地路径**：`D:\android\hs_title_cls`
- **状态**：四模块全链路跑通

## 项目定位

输入一条中文商品标题，输出商品类目及置信度。按「数据 → 训练 → 推理 → 接口」四层单向拆分，每层只依赖上一层：

```
data_process.py  →  train.py  →  predict.py  →  api.py
   数据层            训练层        推理层         接口层
```

技术栈：`bert-base-chinese` 微调 + PyTorch + Transformers，接口层用 FastAPI。

## ⚠️ 关键提醒：指标不可信

数据集是 `data_process.py` 用固定种子（`SEED = 42`）**随机生成的 2000 条仿真标题**，类目词与标题的对应关系是人为设计的，类间区分度极高。

**因此验证集准确率会高到接近满分，这个数字不代表任何真实效果，不可对外引用。** 项目真正的价值是工程流程跑通，不是模型效果。这一声明已写进该仓库的 README 开头，是仓库公开的前提，不要删改。

## 踩过的坑

| 问题 | 处置 |
| --- | --- |
| 目录含 784MB 模型权重，GitHub 拒收单文件 > 100MB | `.gitignore` 排除 `model/`、`pretrained/`，推送体积从 790MB 降到 261KB |
| 中文 Windows 默认 cp936，标题里的 emoji 直接让程序崩 | 统一加 `-X utf8` 运行，VS Code 调试配置里设 `PYTHONUTF8=1` |
| `.vscode/settings.json` 钉死了本机 Python 解释器绝对路径 | 一并加入 `.gitignore`，该文件对他人无意义 |
| 无显卡或显存不足 | 代码自动回退 CPU，但训练慢很多 |

## 后续可做

- [ ] 换真实数据验证一次，看指标会掉到什么程度（这是最有价值的一步）
- [ ] 补 `requirements.txt` 锁定依赖版本
- [ ] 文本清洗目前是针对仿真噪声的正则，迁移真实数据需要重写

## 相关笔记

- 暂无
