# GECOOS AC

这是 GECOOS AC 上游安装包的自动同步发布仓库，用于将上游发布的版本整理为 GitHub Release，方便下载、校验和集成。

本仓库不会修改上游程序逻辑，只负责同步更新日志、提取不同系统和架构的可执行文件，并生成 release 附件。

## 下载

请前往 [Releases](https://github.com/AkimioJR/gecoos-ac/releases) 下载最新版本。

每个 Release 通常包含：

- `manifest.json`：本次 release 的文件清单
- `gecoosac_<os>_<arch>`：默认登录页面版本
- `gecoosac_single_page_<os>_<arch>`：单页面版本
- `gecoosac_no_page_<os>_<arch>`：不含页面版本
- Windows 可执行文件会保留 `.exe` 后缀

其中 `<os>` 和 `<arch>` 表示上游包内对应的操作系统和 CPU 架构。

## 版本与更新日志

Release tag 使用上游产品版本号，例如 `v2.2`。

更新日志会同步到仓库根目录的 [updatelog](./updatelog)，每次自动发布时也会从最新日期的小节生成 Release body。

## 自动更新

仓库通过 GitHub Actions 自动检查上游版本：

- 每天北京时间 20:00 运行一次
- 支持手动触发 workflow
- 当上游版本 tag 与当前最新 GitHub Release tag 不一致时，自动下载、提取、同步更新日志并发布新 Release

## 说明

本仓库是便于分发和自动化集成的镜像仓库，不是 GECOOS AC 官方仓库。程序版权、商标和功能说明归原作者或上游发布方所有。
