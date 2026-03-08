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

## 🔧 刷写固件（手动方式）

### 方法一：使用 PlatformIO（推荐）⭐

**步骤 1：安装 PlatformIO**

```bash
# 安装 VS Code
# 访问 https://code.visualstudio.com/ 下载并安装

# 在 VS Code 中安装 PlatformIO 扩展
# 点击左侧扩展图标 → 搜索 "PlatformIO IDE" → 安装
```

**步骤 2：克隆仓库**

```bash
# 克隆中文版仓库
git clone -b cn-version https://github.com/Jane84894/clockwise.git
cd clockwise/firmware
```

**步骤 3：编译并烧录**

```bash
# 使用 PlatformIO 编译并烧录
pio run -t upload

# 或者先编译，再烧录
pio run
pio run -t upload
```

**步骤 4：监控串口输出（可选）**

```bash
# 查看串口输出（波特率：115200）
pio device monitor --baud 115200
```

---

### 方法二：使用 ESP-IDF

**步骤 1：安装 ESP-IDF**

```bash
# 访问 ESP-IDF 安装指南
# https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/

# 安装 ESP-IDF v4.4 或更高版本
```

**步骤 2：配置项目**

```bash
# 进入固件目录
cd firmware

# 使用 menuconfig 配置项目
idf.py menuconfig
```

**步骤 3：编译并烧录**

```bash
# 编译项目
idf.py build

# 烧录到 ESP32
idf.py -p /dev/ttyUSB0 flash

# macOS 用户
idf.py -p /dev/cu.usbserial-XXXX flash

# Windows 用户
idf.py -p COM3 flash
```

**步骤 4：监控串口输出**

```bash
# 监控串口（波特率：115200）
idf.py -p /dev/ttyUSB0 monitor
```

---

### 方法三：使用 esptool.py（仅烧录已编译的固件）

**步骤 1：安装 esptool**

```bash
# 使用 pip 安装
pip install esptool
```

**步骤 2：烧录固件**

```bash
# 进入固件目录
cd firmware

# 烧录固件（替换为你的串口和设备地址）
esptool.py --port /dev/ttyUSB0 --baud 460800 \
  --before default_reset --after hard_reset write_flash \
  --flash_mode dio --flash_freq 40m --flash_size detect \
  0x1000 build/bootloader/bootloader.bin \
  0x8000 build/partition_table/partition-table.bin \
  0x10000 build/clockwise.bin
```

---

## 🌐 配置 WiFi 和时钟

**固件烧录完成后：**

1. **连接 WiFi 热点**
   - 设备上电后，会创建 WiFi 热点：`Clockwise-XXXX`
   - 使用手机或电脑连接此热点

2. **打开 Web 设置页面**
   - 浏览器访问：`192.168.4.1`
   - 进入时钟配置界面

3. **配置网络和时间**
   - 选择你的 WiFi 网络
   - 输入 WiFi 密码
   - 设置时区
   - 保存配置

4. **切换语言（中文版特色）**
   - 在设置页面顶部，点击 🌐 语言切换按钮
   - 选择 **中文** 或 **English**
   - 语言偏好会自动保存

---

## 🇨🇳 中文使用说明

### 语言切换

中文版固件在 Web 设置界面添加了语言切换功能：

- **位置**：设置页面顶部导航栏
- **图标**：🌐 地球图标
- **支持语言**：中文 / English
- **保存方式**：自动保存到 localStorage

### 编译中文版固件

```bash
# 确保使用 cn-version 分支
git clone -b cn-version https://github.com/Jane84894/clockwise.git
cd clockwise/firmware

# 编译并烧录
pio run -t upload
```

### 中文支持详情

- ✅ **设置页面** - 完全中文化
- ✅ **状态提示** - 中文显示
- ✅ **错误信息** - 中文显示
- ✅ **语言持久化** - localStorage 保存偏好

---

## 🛠️ 开发说明

### 分支说明

| 分支 | 用途 | 说明 |
|------|------|------|
| `main` | 📖 文档 + 与上游同步 | 默认分支，包含中文 README |
| `cn-version` | 💻 中文版本代码 | 中文语言支持实现 |
| `gh-pages` | 🌐 项目官网 | 原作者维护 |

### 推荐开发流程

```bash
# 1. 克隆中文版仓库
git clone -b cn-version https://github.com/Jane84894/clockwise.git
cd clockwise

# 2. 开发你的修改
# 在 firmware 目录下进行修改

# 3. 编译测试
cd firmware
pio run

# 4. 提交你的贡献
git add .
git commit -m "feat: 你的修改说明"
git push origin cn-version
```

### 贡献代码

欢迎提交 Issue 和 Pull Request！

**贡献指南：**
1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

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
- **Issues**: https://github.com/Jane84894/clockwise/issues

---

**祝你使用愉快！** 🎉

如有问题，请提交 Issue 或联系维护者。
