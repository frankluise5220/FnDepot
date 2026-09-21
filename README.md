# FnDepot 外部源：MMH 家庭财务工作台

本仓库是 **MMH** 面向飞牛 fnOS 的 FnDepot 外部应用源，遵循 [FnDepot 外部应用源 V2 规范](https://github.com/EWEDLCM/FnDepot)。

仓库根目录的 `fnpack.json` 即源索引文件，安装包（FPK）本体不在本仓库，由 `download_url` 指向 GitHub Releases / 自建 CDN。

## 如何添加这个源

在 FnDepot 客户端的「添加源」入口填入下面任一地址：

```text
https://github.com/frankluise5220/FnDepot
```

或直接使用索引文件直链：

```text
https://raw.githubusercontent.com/frankluise5220/FnDepot/main/fnpack.json
```

添加后即可在源内看到 **MMH 家庭财务工作台**（`appname=mmh`）。

## 应用信息

| 项目 | 说明 |
|---|---|
| 应用名 | MMH 家庭财务工作台（`mmh`） |
| 简介 | 本地部署的家庭记账与资产管理工具：账户流水、信用卡账单、基金持仓、统计报表、数据导入，数据保存在自己的飞牛 NAS 上 |
| 架构 | x86（x86_64）、arm（arm64） |
| 类型 | 原生应用（非 Docker），`run_as=root` |
| 默认端口 | 7777 |
| 最低系统版本 | fnOS 0.9.0 |
| 项目主页 | <https://github.com/frankluise5220/MMH> |
| 问题反馈 | <https://github.com/frankluise5220/MMH/issues> |
| 安装说明 | <https://github.com/frankluise5220/MMH/blob/main/deploy/nas-install-manual.md> |

## 版本策略

- 仅保留最近 5 个版本，`releases` 按版本号升序排列。
- 已发布的「版本号 + 架构」文件视为不可变，不静默替换同版本 FPK。
- 每个安装包都提供 `sha256` 与 `size`，客户端会强制校验哈希。
- 升级请直接覆盖安装，**不要先卸载再安装**（卸载只用于用户主动删除应用或异常恢复）。

## 维护

源文件由 MMH 发布流程维护：发布新版本时在 `releases` 中新增版本节点，并用 MMH 仓库内的 `scripts/sync-fndepot-source.cjs` 从 GitHub Releases API 补齐 `sha256` / `size` / `updated_at`。

## 免责声明

本仓库为第三方外部源，由应用作者自行维护。FnDepot 不对本源的应用代码、安装包安全性或运行稳定性做审核、担保或背书。请自行评估后安装。
