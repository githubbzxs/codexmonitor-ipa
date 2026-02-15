# codexmonitor-ipa

用于通过 GitHub Actions 构建 `Dimillian/CodexMonitor` 的 iOS IPA。

支持两条工作流：
- `按项目官方流程构建 IPA`（需要签名环境）
- `构建未签名IPA`（生成 `unsigned.ipa`，用于本地重签）

## 触发方式

1. 打开仓库的 `Actions` 页面。
2. 选择工作流：
   - `按项目官方流程构建 IPA`，或
   - `构建未签名IPA`（你当前场景建议用这个）。
3. 点击 `Run workflow`，保持默认参数：
   - `upstream_repo`: `Dimillian/CodexMonitor`
   - `upstream_ref`: `main`

## 下载产物

构建完成后，在该次运行页面下载对应 Artifact：
- 官方流程：`codexmonitor-ipa-official`
- 未签名流程：`codexmonitor-unsigned-ipa`

包含文件：
- 官方流程：
  - `Codex Monitor.ipa`
  - `Codex Monitor.ipa.sha256`
- 未签名流程：
  - `unsigned.ipa`
  - `unsigned.ipa.sha256`

## 说明

此工作流使用项目官方构建命令：

```bash
npm run tauri -- ios build --target aarch64 --export-method app-store-connect --build-number <timestamp> --ci
```

来源：`Dimillian/CodexMonitor` 仓库 `scripts/release_testflight_ios.sh`。

未签名工作流说明：
- 通过 `xcodebuild` 禁用签名直接构建 `.app`。
- 再手动封装为 `Payload/*.app -> unsigned.ipa`。
