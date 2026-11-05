# EvoVerse Linux 环境产品 · 客户交付发布仓库（正式）

EvoVerse Linux 环境产品（`rk3588-ai`）的**正式客户交付发布仓库**：
面向 Ubuntu Server 24.04 LTS x86_64 主机，RK3588 AArch64 目标。

- 当前版本：**2026.11.0**（tag = 精确版本；身份一律 sha256 digest，禁 `latest`）
- Release：<https://github.com/butonlyif/evoverse-env-delivery/releases/tag/2026.11.0>
- Gitee 镜像（国内下载）：<https://gitee.com/but-only-if/evoverse-env-releases/releases/tag/2026.11.0>
- 源真值仓库：<https://github.com/butonlyif/evoverse-linux-dev>
- 验证与安装指引：
  [docs/installation.md](https://github.com/butonlyif/evoverse-linux-dev/blob/master/docs/installation.md)

## 交付资产与身份纪律

Release 附着 12 个交付资产（GitHub 自动生成的源码归档 `2026.11.0.zip/.tar.gz`
非交付闭图成员，豁免）。每个资产 sha256 见 release 内 **SHA256SUMS**；
签名密钥 `gitee-release-2026b`（公钥 sha256 指纹
`2a2fd2a0a34866dddf6d2699602cd82529b989b2186feddfc87fa1b47d00a994`），
公钥文件见 [keys/](keys/)，与 release 内 KEYS-MANIFEST.json 指纹一致。
发布不可变：任何修订都是新版本新 release。

## 客户验证（先验证，后安装）

```bash
git clone https://github.com/butonlyif/evoverse-linux-dev.git && cd evoverse-linux-dev
# GitHub 版资产可匿名下载；离线在地验证（跨平台）：
python3 scripts/release.py verify-bundle --bundle <bundle目录> --trust-dir trust
```

## 诚实状态

本交付**不携带资格回执**（2026-11-05 首发决策）：资格验证未运行——
E4 软件资格仅开发侧完成，E5 硬件资格 BLOCKED（无板卡），干净主机验收
NOT_RUN。详见 release 内 **RELEASE-NOTES.md**。环境可用性不构成任何声明。
