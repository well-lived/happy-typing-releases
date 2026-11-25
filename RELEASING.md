# 发布一个版本

在分发 Mac 上完成应用签名、公证和 Sparkle 更新签名，使用打包流程生成的同一批文件发布到官网和 GitHub。

1. 创建 GitHub Release 草稿，标签与产品版本一致，例如版本号前加 `v`。在本公开仓库的 `main` 上创建标签。测试版勾选 **Set as a pre-release**。
2. 填写用户可见的改动、系统要求和已知问题。上传 `Happy-Typing-<版本>-universal.dmg`、对应的 `.dmg.sha256` 和该版本生成的 `appcast.xml`。在安装包目录运行 `shasum -a 256 -c <校验文件名>` 核对产物。
3. 将同一份 DMG 和校验文件部署到官网的 `/downloads/`。确认安装包可通过 HTTPS 下载、校验一致后，再发布 `/updates/appcast.xml`。保留旧版本安装包，供已读取旧清单的客户端使用。
4. 在官网构建时设置对应的发布版本和下载开关，检查下载按钮。用上一版客户端执行「关于 → 检查更新」，确认版本号正确并完成安装，再发布 GitHub 草稿。

现有客户端读取[官网更新清单](https://happytyping.welllived.cn/updates/appcast.xml)。上传 GitHub Release 单独不会触发官网部署。GitHub 自动生成的 Source code 压缩包包含本仓库的产品文档，Mac 用户请下载 DMG。
