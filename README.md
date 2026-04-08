# Rime 输入法配置说明

本仓库为 Windows 小狼毫 (Weasel) 输入法的个人配置文件，针对**嵌入式工程师**使用场景优化。

---

## 📁 文件清单

| 文件名 | 作用说明 |
|--------|----------|
| `default.custom.yaml` | **全局配置** - 控制输入法整体行为，包括中英文切换键（Shift）、程序感知（在代码编辑器中自动切英文）等 |
| `luna_pinyin_simp.custom.yaml` | **拼音方案配置** - 控制朙月拼音·简化字方案的具体设置，包括简体字开关、全角/半角标点 |
| `weasel.custom.yaml` | **界面主题** - 小狼毫输入法的外观配置，当前使用 ink（水墨）配色 |
| `custom_phrase.txt` | **自定义短语** - 快速输入代码片段，如 `u8`→`uint8_t`、`HAL_Init`→`HAL_Init` |
| `engineer_dict.yaml` | **嵌入式词库** - 专业术语词库，包含芯片厂商、通信协议、HAL函数、数据结构等 |
| `english_dict.dict.yaml` | **英文词典占位** - 预留的英文单词词典（暂未使用） |
| `installation.yaml` | **安装信息** - 记录输入法安装路径等信息 |
| `user.yaml` | **用户状态** - 记录用户最后部署时间等状态信息 |

---

## ⚙️ 核心功能

### 1. 简体中文输出
- 默认启用简体字模式，不会出现繁体字

### 2. 程序感知（自动切换）
在以下程序中自动切换为英文模式：
- VS Code、Visual Studio、JetBrains 全家桶（IDEA、PyCharm、CLion 等）
- 终端类：Windows Terminal、CMD、PowerShell、Git Bash
- 编辑器：Vim、Neovim、Sublime Text、Notepad++

### 3. 自定义短语（代码片段）
| 输入 | 输出 |
|------|------|
| `u8` | `uint8_t` |
| `i32` | `int32_t` |
| `HAL_Init` | `HAL_Init` |
| `gadd` | `git add` |

完整列表见 `custom_phrase.txt`

### 4. 嵌入式专业词库
包含术语：
- **芯片厂商**：意法半导体、德州仪器、兆易创新、乐鑫等
- **通信协议**：UART、SPI、I2C、CAN、USB、以太网等
- **ARM相关**：Cortex-M、NVIC、DMA等
- **数据结构**：链表、栈、队列、二叉树等

完整列表见 `engineer_dict.yaml`

---

## 🚀 使用方法

### 首次部署
1. 安装 [小狼毫输入法](https://github.com/rime/weasel/releases)
2. 克隆本仓库到 `%APPDATA%\Rime` 目录
3. 右键任务栏小狼毫图标 → **重新部署**

### 日常同步
```bash
cd %APPDATA%\Rime
git pull  # 拉取最新配置
git push  # 推送本地更改
```

---

## ⌨️ 快捷键

| 快捷键 | 功能 |
|--------|------|
| `Shift` | 中英文切换 |
| `F4` / ``Ctrl+` `` | 切换输入法方案/开关 |
| `` ` `` + 拼音 | 符号反查（笔画输入）|

---

## 📝 个性化修改

### 添加自定义短语
编辑 `custom_phrase.txt`，格式：
```
短语<tab>编码<tab>权重
```

### 修改程序感知
编辑 `default.custom.yaml` 中的 `app_options` 部分。

### 切换主题
编辑 `weasel.custom.yaml` 中的 `style/color_scheme`。

---

## 🔗 相关链接

- [Rime 官网](https://rime.im/)
- [小狼毫 GitHub](https://github.com/rime/weasel)
- [Rime 配置指南](https://github.com/rime/home/wiki/CustomizationGuide)
