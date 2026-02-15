# codexmonitor-ipa

用于通过 GitHub Actions 构建 `Dimillian/CodexMonitor` 的未签名 iOS 安装包（`unsigned.ipa`）。

## 触发方式

1. 打开仓库的 `Actions` 页面。
2. 选择工作流 `构建未签名 IPA`。
3. 点击 `Run workflow`，保持默认参数：
   - `upstream_repo`: `Dimillian/CodexMonitor`
   - `upstream_ref`: `main`

## 下载产物

构建完成后，在该次运行页面下载 Artifact：`codexmonitor-unsigned-ipa`。

包含文件：
- `unsigned.ipa`
- `unsigned.ipa.sha256`

## 安装说明（Windows 非越狱）

1. 用 Sideloadly 打开 `unsigned.ipa`。
2. 输入你的 Apple ID 在本机重签。
3. USB 安装到 iPhone。
4. 手机上信任开发者证书后启动应用。

说明：免费 Apple ID 签名通常 7 天过期，到期后需重新签名安装。
