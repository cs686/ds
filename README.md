# 项目简介

该策略以实验与证伪为导向，关注基于 DeepSeek（ds）与指标的组合方案。项目非商业化产品，请理性使用并自行评估风险。

- 思路来源与演进可关注推特：https://x.com/huojichuanqi
- 当前重点：ds + 指标方案。基础版本以本地计算指标为主，正在尝试用 ds 直接分析指标，效果仍在评估中。

## 重要设置

- 为简化逻辑，请确保交易所持仓模式为「单向持仓」。

## 环境要求

- Ubuntu 20.04+（推荐阿里云：香港或新加坡轻量服务器）
- Python 3.10
- Conda（Anaconda/Miniconda 均可）

## 安装步骤

```bash
# 安装 Anaconda（按需替换版本号）
wget https://repo.anaconda.com/archive/Anaconda3-2024.10-1-Linux-x86_64.sh
bash Anaconda3-2024.10-1-Linux-x86_64.sh

# 载入 conda 环境脚本（建议写入 bashrc）
source /root/anaconda3/etc/profile.d/conda.sh
echo ". /root/anaconda3/etc/profile.d/conda.sh" >> ~/.bashrc

# 创建并激活 Python 环境
conda create -n ds python=3.10 -y
conda activate ds

# 系统与进程管理（可选）
apt-get update && apt-get upgrade -y
apt install npm -y
npm install -g pm2

# 安装 Python 依赖
pip install -r requirements.txt
```

> 说明：此前文档中曾出现 `python=4.10` 的笔误，请使用 `python=3.10`。

## 配置文件

在策略根目录创建 `.env`，并填写以下内容：

```dotenv
DEEPSEEK_API_KEY=你的DeepSeek API密钥

BINANCE_API_KEY=
BINANCE_SECRET=

OKX_API_KEY=
OKX_SECRET=
OKX_PASSWORD=
```

安全提示：
- 请将 `.env` 添加到忽略文件，避免提交到仓库。
- 密钥仅用于本地/授权环境，切勿分享。

## 运行与部署

- 运行方式取决于项目入口脚本，请根据实际文件组织执行（例如 `python your_entry.py` 或使用 pm2 管理进程）。
- 如需可视化或进阶用法，请参考下方视频教程。

## 视频教程

- 基础教程：https://www.youtube.com/watch?v=Yv-AMVaWUVg
- 分档移动止盈止损：https://youtu.be/-vfeyqUkuzY

## 常见问题（FAQ）

- Conda 环境创建失败：请确认使用 `python=3.10`；若安装脚本路径不同，请调整 `source` 与 `echo` 命令中的路径。
- 依赖安装失败：检查 `requirements.txt` 是否完整，必要时为科学网络环境配置代理。

## 免责声明

- 本项目用于研究与验证，不构成任何投资建议。
- 加密资产与量化交易存在高风险，请谨慎操作并自行承担后果。

## 联系与支持

- 推特（了解思路与进展）：https://x.com/huojichuanqi
- 打赏地址（TRC20）：TUunBuqQ1ZDYt9WrA3ZarndFPQgefXqZAM

---

如需补充内容（使用示例、指标说明、截图/架构图、项目徽章、英文版 README 等），请告知偏好，我会继续完善。