# codexmonitor-ipa

用于通过 GitHub Actions 按 `Dimillian/CodexMonitor` 项目官方命令构建 iOS IPA。

## 触发方式

1. 打开仓库的 `Actions` 页面。
2. 选择工作流 `按项目官方流程构建 IPA`。
3. 点击 `Run workflow`，保持默认参数：
   - `upstream_repo`: `Dimillian/CodexMonitor`
   - `upstream_ref`: `main`

## 下载产物

构建完成后，在该次运行页面下载 Artifact：`codexmonitor-ipa-official`。

包含文件：
- `Codex Monitor.ipa`
- `Codex Monitor.ipa.sha256`

## 说明

此工作流使用项目官方构建命令：

```bash
npm run tauri -- ios build --target aarch64 --export-method app-store-connect --build-number <timestamp> --ci
```

来源：`Dimillian/CodexMonitor` 仓库 `scripts/release_testflight_ios.sh`。
