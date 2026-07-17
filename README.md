# Recorder Studio for Obsidian

在 Obsidian 桌面版中录制屏幕、摄像头和讲解音频。交互参考 Excalicord：录制时显示可拖动的摄像头气泡和悬浮控制条，结束后把视频保存到 Vault。

## 从 GitHub 安装

1. 打开 [Releases](https://github.com/beyondaprilzjl-lab/obsidian-screen-recorder/releases/latest)，下载最新的 `obsidian-screen-recorder-版本号.zip`。
2. 解压到 Vault 的 `.obsidian/plugins/obsidian-screen-recorder/` 目录。
3. 确认目录中包含 `main.js`、`manifest.json`、`styles.css` 和 `native/`。
4. 重启 Obsidian，在“第三方插件”中启用 `Recorder Studio`。

不要只下载 `main.js`、`manifest.json` 和 `styles.css`。macOS 摄像头录制依赖发布包中的 `native/CameraBridge.app`。

## 功能

- 录制整个屏幕或指定应用窗口
- 圆形或圆角方形摄像头画中画
- 录制中拖动摄像头，输出视频同步更新位置
- 麦克风与系统音频混音
- 暂停、继续、取消和共享结束自动保存
- 0、3 或 5 秒开始倒计时
- 高、中、低三档输出分辨率和码率
- 默认优先保存为 MP4（H.264 / AAC），不支持时自动回退为 WebM
- 可选把视频嵌入录制开始时的 Markdown 笔记

## 使用

1. 在 Obsidian 第三方插件中启用 `Recorder Studio`。
2. 点击左侧栏的录制图标，或从命令面板运行“开始屏幕和摄像头录制”。
3. 在 Recorder Studio 的缩略图列表中选择屏幕或应用窗口，并按系统提示授权摄像头和麦克风。
4. 使用悬浮控制条暂停、继续、停止或取消。
5. 视频默认保存在 Vault 的 `recordings/` 目录。

设置页可以调整质量、帧率、摄像头形状和大小、音源、倒计时、保存目录及笔记嵌入行为。

## 仓库内容

- `main.js`：插件运行代码
- `manifest.json`：Obsidian 插件清单
- `styles.css`：界面样式
- `native/CameraBridge.app`：macOS 摄像头桥接程序
- `versions.json`：插件版本与最低 Obsidian 版本对应关系

## 限制

- 仅支持 Obsidian 桌面版。
- 随包提供的 macOS 摄像头桥接程序要求 macOS 12 或更高版本，并且当前仅提供 Apple Silicon (`arm64`) 构建。
- Windows 桌面捕获模式支持系统回环音频；macOS 当前仅录制麦克风。
- 录制当前 Obsidian 窗口时，悬浮控制条也可能被屏幕源捕获；摄像头画面始终由合成器写入最终视频。
- 长时间录制会在内存中累计视频分片，建议按章节录制。
