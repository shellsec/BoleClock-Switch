# BoleClock-Switch · 波乐时钟

让 Nintendo Switch 在闲暇时成为桌面时钟、床头时钟和专注计时器。

**作者：[shellsec](https://github.com/shellsec) · 波乐系列**  
免费使用 · 完全离线 · 中文 / English · 当前测试版 **0.3.1**

[下载编译版本](https://github.com/shellsec/BoleClock-Switch/releases) · [问题反馈](https://github.com/shellsec/BoleClock-Switch/issues)

本仓库用于发布使用说明、版本信息与编译后的 NRO，核心源代码暂不公开。需要已有 Nintendo Switch 自制软件运行环境。

**0.3.1 更新**：关于页补齐仓库和版权；修复配置备份及声明导出的 Switch 文件复制兼容性问题。
若仍提示保存失败，请记录新版提示中的步骤与错误码；先保留配置，不必直接删除。

## 功能

| 功能 | 内容 |
| --- | --- |
| 六种时钟样式 | 大数字、双位复古翻页、独立数字翻页、七段 LED、简约模拟、经典模拟 |
| 时间显示 | 12/24 小时、可选秒数、日期星期、三档大小、左中右对齐 |
| 翻页效果 | 数字随上下半片收合与展开，带中缝、圆角和遮光 |
| 配色 | 深色、浅色、粉色、复古暖色、薄荷绿，文字配色和阴影 |
| 壁纸 | 本地静态 JPG / PNG / WebP，裁剪铺满、完整显示、原始比例、遮罩 |
| 计时器 | 倒计时、秒表、番茄钟，开始/暂停/继续/重置，声音与画面提醒 |
| 中英文 | 即时切换，包含日期星期和动态提示 |
| OLED 辅助 | 定时微移、夜间低亮度、闲置调暗、闲置定时黑屏 |
| 主题预设 | 五个外观槽位，保存/套用/覆盖/删除 |
| 操作与保存 | 全触屏、Joy-Con / Pro Controller、自动保存和恢复设置 |
| 关于与 HOME 前端 | 作者、版本、仓库、版权、许可声明及可选专属 HOME 入口安装 |

背景轮播、跨应用自动通信和网络时间同步尚未提供。BoleClock 独立运行，不依赖或修改 BoleMusic、BoleWallpaper。

## 安装与更新

1. 从 [Releases](https://github.com/shellsec/BoleClock-Switch/releases) 下载最新 ZIP。
2. 解压，将 `switch/BoleClock/` 复制到 SD 卡的 `/switch/BoleClock/`。
3. 从 hbmenu 启动 `BoleClock.nro`。
4. 自定义背景放入 `backgrounds/`。更新时保留已有 `config/`、`backgrounds/` 和 `themes/`。

```text
/switch/BoleClock/
├── BoleClock.nro
├── config/
├── backgrounds/
└── themes/
```

优先在完整应用环境使用；相册 applet 内存受限，须单独实测。
图片仅支持静态 JPG/PNG/WebP，单文件最多 20 MiB、900 万像素、最长边 8192；加载失败回退默认背景。

首次运行可能提示安装专属 HOME 入口，可选择“安装 / 稍后 / 不再提示”。也可从 **设置 → 关于与 HOME 前端** 手动检查或安装，需要再次确认。
HOME 前端固定启动 `/switch/BoleClock/BoleClock.nro`，独立 TitleID 为 `012B0E80B0004000`。更新 NRO 通常无需重装前端。

## 使用

轻触屏幕显示工具栏，选择 **模式 / 背景 / 主题 / 设置 / 计时器 / 退出**。闲置 8 秒后工具栏隐藏。

| 手柄操作 | 作用 |
| --- | --- |
| 方向键 / 摇杆 | 移动焦点；左右调整选项 |
| A | 确认 |
| B | 返回 / 隐藏工具栏 |
| X | 设置 |
| Y | 主题 |
| + | 退出 |

所有已实现设置均可触屏完成，无需键盘鼠标。设置自动保存，失败时可在设置页选择“立即保存 / 重试”。

### 计时器怎么开始？

打开工具栏的 **计时器**，选择类型和时长后，触屏点“开始计时”或右上方开始按钮；手柄直接按 **A**。

- 倒计时：自定义小时、分钟、秒，另有 1/5/25/60 分钟快捷预设。
- 秒表：正向累计，可暂停、继续和重置。
- 番茄钟：默认 25 分钟专注 / 5 分钟休息、4 轮，可调整时长与轮次。
- 选择“全屏显示”进入大卡片计时：**A 开始/暂停/继续，Y 重置，X 计时设置，B 返回时钟**。
- 准备、暂停和完成状态始终显示触屏按钮；修改运行中的类型或时长须先重置。

离开前台或系统休眠后暂停，返回需手动继续；重新启动恢复为暂停快照。不提供后台唤醒或休眠中响铃。

### 中英文、OLED 和主题预设

- **设置 → 更多设置**：切换中文 / English，配置微移、夜间亮度、闲置调暗/黑屏和平滑秒针。
- 微移默认开启，每 60 秒变化，范围 ±4px；闲置调暗/黑屏默认关闭。
- 闲置调暗：1/5/15 分钟；调暗亮度：20/35/50/70%；闲置黑屏：5/15/30/60 分钟。
- 黑屏后的第一次触屏或手柄操作只唤醒，第二次执行操作。前台计时结束或阶段变化会恢复画面提醒。
- **主题 → 主题预设**：五个槽位保存当前外观，覆盖/删除须再次确认。预设不覆盖语言、OLED 设置或计时任务。

OLED 功能仅作辅助，不保证防止烧屏；调暗使用软件遮罩，不修改系统背光，也不阻止正常休眠。

## 关于、版权和第三方许可

Copyright © 2026 **shellsec**. All rights reserved.

BoleClock（波乐时钟）原创核心代码保留所有权利。软件免费发布编译版本，核心源代码暂不公开；免费使用不表示核心源码采用开源许可证。

第三方组件和独立 HOME loader 保留各自版权与许可证。应用内 **设置 → 关于与 HOME 前端** 可查看第三方声明，并导出完整声明和独立 loader 对应源码到 `BoleClock/licenses/`。该 loader 源码不包含 BoleClock 核心源码。

应用采用 devkitPro/libnx、SDL2、stb、libwebp、nlohmann/json 和 Noto CJK 字体等组件；具体版本、来源和许可声明随 NRO 内嵌提供。

本项目与 Nintendo 无隶属、赞助或认可关系。Nintendo Switch 为其相关权利人的商标。

## 测试状态与反馈

当前为真机待验收测试版：主机自动测试、软件渲染和 NRO 构建/结构校验已执行；这些不等于已通过实际 Switch 验证。
掌机/底座显示、真实手柄与触屏、音频、HOME 安装、休眠唤醒和长时间稳定性仍需设备测试。

反馈问题请附：应用版本、Switch 型号、系统与自制环境版本、启动方式、复现步骤、预期/实际结果，以及可选截图。
请勿上传个人密钥或其他敏感文件。

## English

**BoleClock** is a free, offline clock and timer homebrew app for Nintendo Switch by **shellsec**.

- Six styles: digital, paired flip, individual flip digits, seven-segment LED, minimal and classic analog.
- Countdown, stopwatch and Pomodoro; touch and controller controls; automatic settings restore.
- Chinese / English, local JPG/PNG/WebP backgrounds, five themes and five appearance preset slots.
- OLED aids: bounded pixel shift, night dimming, idle dimming and blackout. No burn-in guarantee or sleep inhibition.

Download a compiled ZIP from [Releases](https://github.com/shellsec/BoleClock-Switch/releases), copy `switch/BoleClock/` to the SD card, and launch the NRO with hbmenu. Preserve your data folders when updating.

Use **Settings → More settings** to change language and OLED options, and **Themes → Theme presets** to save a look.
In the full-screen timer: **A Start/Pause, Y Reset, X Timer settings, B Clock**. First input after software blackout only wakes the display.

The core source remains private. Third-party works retain their own licenses; notices and independent loader source can be exported from About. Hardware validation is pending; timers do not wake the console from system sleep.
