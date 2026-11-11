# EvoVerse Linux 环境产品 · 客户交付发布仓库（正式）

EvoVerse Linux 环境产品（`rk3588-ai`）的**正式客户交付发布仓库**：
面向 Ubuntu Server 24.04 LTS x86_64 主机，RK3588 AArch64 目标。

- 当前版本：**2026.11.2**（tag = 精确版本；身份一律 sha256 digest，禁 `latest`）
- Release：<https://github.com/butonlyif/evoverse-env-delivery/releases/tag/2026.11.2>
- Gitee 镜像（国内下载）：<https://gitee.com/but-only-if/evoverse-env-delivery/releases/tag/2026.11.2>（备用：<https://gitee.com/but-only-if/evoverse-env-releases/releases/tag/2026.11.2>）
- 源真值仓库：<https://github.com/butonlyif/evoverse-linux-dev>
- 验证与安装指引：
  [docs/installation.md](https://github.com/butonlyif/evoverse-linux-dev/blob/master/docs/installation.md)

## 交付资产与身份纪律

Release 附着 13 个交付资产（扁平命名：子目录内容 `<子目录>-<文件>`，
如 `receipts-receipt-quick.json`）。每个资产 sha256 见 release 内 **SHA256SUMS**。

签名密钥公告（2026-11-11 轮换，追加式）：

- `2026.11.1` 起签名密钥为 **`gitee-release-2026c`**（公钥 sha256 指纹
  `80ce306774e251dd3fe4f9a6c6bb6c8424b82241e42405f26de1097a8138e750`）。
- `gitee-release-2026b`（指纹 `2a2fd2a0a34866dddf6d2699602cd82529b989b2186feddfc87fa1b47d00a994`）
  **保留且未撤销**：`2026.11.0` 验签不受影响。
- 两个公钥均在 [keys/](keys/)，与各 release 内 KEYS-MANIFEST.json 指纹一致。
- 发布不可变：任何修订都是新版本新 release。

## 客户验证（先验证，后安装）

```bash
git clone https://github.com/butonlyif/evoverse-linux-dev.git && cd evoverse-linux-dev
# GitHub 版资产可匿名下载；离线在地验证（跨平台）：
python3 scripts/release.py verify-bundle --bundle <bundle目录> --trust-dir trust
```

## 诚实状态

`2026.11.2` **随附资格回执** `receipts-receipt-quick.json`（rk3588-ai@2026.11.2 软件资格链
PASS：生产 install.Install 离线 tag+imageId 身份装成，verify PASS；8 个 action 经生产 manager CLI 全链通过，
2 个负向探针按预期拒收）。
执行环境为**开发侧授权 linux/amd64 特权容器**——非客户 clean host、非 bare-metal：
E5 硬件资格 NOT_RUN（无板卡），真实 clean-host 全阶段验收 NOT_RUN，在地六阶段
部署 NOT_RUN。逐项披露见 release 内 **RELEASE-NOTES.md**。环境可用性不构成
任何超出回执范围的声明。
