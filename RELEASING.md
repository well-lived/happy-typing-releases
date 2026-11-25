# 发布一个版本

1. 在分发 Mac 上完成签名、公证和打包。创建 GitHub Release **草稿**，标签使用产品版本加 `v`，例如 `v0.1.0-beta.3`。测试版本勾选 **Set as a pre-release**。
2. 填写版本说明并上传同一次打包生成的三个文件：通用 DMG、文件名以 `.dmg.sha256` 结尾的校验文件、Sparkle 的 `appcast.xml`。在安装包目录用 `shasum -a 256 -c <校验文件名>` 核对安装包。
3. 审核通过并准备向用户分发时，点击 **Publish release**。官网每五分钟读取已公开的 Release（包括 Beta），核对附件和清单，按构建号选择最新版。每个公开版本都使用新标签和递增的构建号。
4. 打开[官网下载入口](https://happytyping.welllived.cn/download/mac)，核对跳转到该版本的 GitHub DMG；再用上一版应用通过「关于 → 检查更新」完成一次升级。[官网更新清单](https://happytyping.welllived.cn/updates/appcast.xml)

每次发布只需上传到本仓库。GitHub 自动生成的 Source code 压缩包包含产品文档，安装应用请选择 DMG。
