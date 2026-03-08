# 🇨🇳 Clockwise 中文版

> **智能挂钟 DIY 项目 - 支持中文界面**

[![GitHub forks](https://img.shields.io/github/forks/Jane84894/clockwise?style=flat)](https://github.com/Jane84894/clockwise/network)
[![GitHub stars](https://img.shields.io/github/stars/Jane84894/clockwise?style=flat)](https://github.com/Jane84894/clockwise/stargazers)
[![GitHub license](https://img.shields.io/github/license/Jane84894/clockwise)](https://github.com/Jane84894/clockwise/blob/main/LICENSE)

---

## ✨ 中文版本特色

本仓库是 [jnthas/clockwise](https://github.com/jnthas/clockwise) 的**中文本地化版本**，在原版基础上添加了以下改进：

### 🎯 新增功能

- ✅ **中文语言支持** - Web 设置界面支持中英文切换
- ✅ **国际化 (i18n)** - 完整的语言切换功能
- ✅ **代码规范化** - 翻译代码注释为英文
- ✅ **UI 优化** - 改进用户界面体验

### 📦 与原版对比

| 特性 | 原版 | 中文版 |
|------|------|--------|
| **Web 界面语言** | 仅英文 | ✅ 英文 + 中文 |
| **语言切换** | ❌ 不支持 | ✅ 支持 |
| **代码注释** | 混合 | ✅ 统一英文 |
| **分支** | `main` | `cn-version` |

### 🚀 快速体验

访问 [https://clockwise.page](https://clockwise.page) 在线烧录固件，然后在设置界面切换语言！

---

## 📖 原版项目介绍

![News GIF](https://github.com/jnthas/clockwise/raw/gh-pages/static/images/news.gif) **[Latest version 1.4.2 released!](https://github.com/jnthas/clockwise/releases/tag/v1.4.2)** | [See full change log](https://github.com/jnthas/clockwise/blob/main/CHANGELOG.md#142---2024-04-21)

![Clockwise Logo](https://github.com/jnthas/clockwise/blob/gh-pages/static/images/clockwise_logo.png "Clockwise Logo")

---

**Clockwise** is an open-source smart wall clock that you can easily build yourself.  
It only needs:

- 64x64 RGB LED Matrix (HUB75 or HUB75E)
- ESP32 dev board
- 5V 3A power supply
- Jumpers

To simplify assembly, you can also use the [**WiseShield-32 DIY PCB kit**](https://www.elecrow.com/clockwise-diy-kit.html) — created in partnership with Elecrow especially for Clockwise.

---

## Features

- Real-time clock with customizable themes ("Clockfaces")
- Web-based interface for configuration
- Open-source hardware and firmware
- Compatible with various PCBs or just simple wiring
- Community-driven

---

## Quick Start

### 1. Required Hardware

If you want to build it from scratch, you will need at least these components below. Follow the instructions on [Wiki]() to assemble it. 
- 64x64 RGB LED matrix (HUB75 or HUB75E)
- ESP32 Dev Board
- 5V 3A power supply
- Jumpers

Alternatively, we created a custom PCB that simplifies this process a lot. The kit includes not only the PCB but all components including sensors to make your clock smarter. Check the [WiseShield-32 PCB kit](https://www.elecrow.com/clockwise-diy-kit.html) out now!

### 2. Flash Firmware

- Go to: [https://clockwise.page](https://clockwise.page)
- Follow the on-screen steps to flash Clockwise and configure WiFi

For detailed instructions:  
👉 [See Wiki: Getting Started](https://github.com/jnthas/clockwise/wiki/%F0%9F%9A%80-Getting-Started)

---

## Clockfaces Gallery

You can choose from many creative Clockfaces — or make your own:

Mario Bros | Words | World Map | Castlevania | Pacman | Pokedex | Canvas
:--:|:--:|:--:|:--:|:--:|:--:|:--:
[![](https://github.com/jnthas/cw-cf-0x01/blob/main/cf_0x01_thumb.jpg)](https://github.com/jnthas/cw-cf-0x01) | [![](https://github.com/jnthas/cw-cf-0x02/blob/main/cf_0x02_thumb.jpg)](https://github.com/jnthas/cw-cf-0x02) | [![](https://github.com/jnthas/cw-cf-0x03/blob/main/cf_0x03_thumb.jpg)](https://github.com/jnthas/cw-cf-0x03) | [![](https://github.com/jnthas/cw-cf-0x04/blob/main/cf_0x04_thumb.jpg)](https://github.com/jnthas/cw-cf-0x04) | [![](https://github.com/jnthas/cw-cf-0x05/blob/main/cf_0x05_thumb.jpg)](https://github.com/jnthas/cw-cf-0x05) | [![](https://github.com/jnthas/cw-cf-0x06/blob/main/cf_0x06_thumb.jpg)](https://github.com/jnthas/cw-cf-0x06) | [![](https://github.com/jnthas/cw-cf-0x07/raw/main/cf_0x07_thumb.jpg)](https://github.com/jnthas/cw-cf-0x07)

> Canvas is a special type of Clockface that is capable of rendering different themes described in a JSON file. More about **Canvas Clockface**: [Wiki page](https://github.com/jnthas/clockwise/wiki/Canvas-Clockface)

---

## 🇨🇳 中文使用说明

### 切换语言步骤

1. 打开设备 Web 设置界面
2. 点击导航栏的 **语言切换按钮** 🌐
3. 选择 **中文** 或 **English**
4. 语言偏好会自动保存

### 编译固件

```bash
# 克隆中文版仓库
git clone -b cn-version https://github.com/Jane84894/clockwise.git
cd clockwise/firmware

# 使用 PlatformIO 编译
pio run -t upload
```

### 中文支持详情

- **设置页面** - 完全中文化
- **状态提示** - 中文显示
- **错误信息** - 中文显示
- **语言持久化** - localStorage 保存偏好

---

## 🛠️ 开发说明

### 分支说明

- `main` - 原版代码（与上游同步）
- `cn-version` - **中文版本**（推荐使用）
- `gh-pages` - 项目官网

### 贡献代码

欢迎提交 Issue 和 Pull Request！

### 本地化 (i18n)

中文语言支持通过以下方式实现：

```javascript
// 语言包
const translations = {
  zh: { /* 中文翻译 */ },
  en: { /* English translations */ }
};

// 切换语言
function setLanguage(lang) {
  localStorage.setItem('preferredLanguage', lang);
  // 更新 UI
}
```

---

## 📄 许可证

本项目采用与原版相同的许可证。

- **原版项目**: [jnthas/clockwise](https://github.com/jnthas/clockwise)
- **原作者**: Jonathas Barbosa
- **许可证**: 查看 [LICENSE](LICENSE) 文件

---

## 🙏 致谢

- 感谢原作者 [Jonathas Barbosa](https://github.com/jnthas) 创建了这个优秀的开源项目
- 感谢所有 Clockwise 社区的贡献者

---

## 📬 联系方式

- **项目地址**: https://github.com/Jane84894/clockwise
- **原版项目**: https://github.com/jnthas/clockwise
- **在线烧录**: https://clockwise.page

---

**祝你使用愉快！** 🎉

如有问题，请提交 Issue 或联系维护者。
