# Easy-Dwgo

一个专为 Unraid 系统设计的 Go 环境管理插件，让您在 Unraid 上轻松安装、管理和使用 Go 开发环境。

> ⚠️ **注意**：这是自用测试版本，仅供学习和测试使用。在生产环境中使用前请谨慎评估。

## ✨ 主要特性

- 🚀 **一键安装**：支持一键下载和安装 Go 环境
- 🔄 **多版本支持**：支持 Go 1.20.x、1.21.x、1.22.x 多个版本
- 💾 **持久化存储**：Go SDK 自动备份到 U 盘，重启后自动恢复
- 🎯 **自动恢复**：系统重启后自动恢复 Go 环境，无需手动操作
- 🌐 **Web 管理界面**：提供直观的 Web 界面进行环境管理
- ⚡ **内存优化**：GOPATH 使用内存路径，提升性能
- 🔧 **环境变量自动配置**：自动设置 GOROOT、GOPATH 等环境变量

## 📋 系统要求

- Unraid 6.12.0 或更高版本
- 至少 100MB 可用磁盘空间
- 网络连接（用于下载 Go SDK）

## 🚀 安装方法

### 方法一：通过 Unraid 插件管理器安装

1. 在 Unraid Web 界面中，进入 **Apps** 页面
2. 搜索 "easy-dwgo" 或直接访问插件 URL
3. 点击 **Install** 按钮进行安装

### 方法二：手动安装

1. 下载 `easy-dwgo.plg` 文件
2. 将文件放置到 `/boot/config/plugins/` 目录
3. 在 Unraid Web 界面中进入 **Plugins** 页面
4. 找到 easy-dwgo 插件并点击 **Install**

## 📖 使用指南

### 首次使用

1. 安装插件后，进入 **Utilities** → **Easy-Dwgo**
2. 在 Web 界面中选择要安装的 Go 版本
3. 点击 **下载/安装** 按钮
4. 等待下载和安装完成

### 版本管理

- **Go 1.20.14**：稳定版本，适合生产环境
- **Go 1.21.5**：推荐版本，平衡稳定性和新特性
- **Go 1.22.0**：最新版本，包含最新特性

### 环境信息

- **GOROOT**：`/usr/local/go`
- **GOPATH**：`/tmp/go`（内存路径）
- **自动恢复**：重启后 Go SDK 自动恢复

## 🛠️ 功能说明

### Go 环境管理

- **自动安装**：一键下载和安装指定版本的 Go SDK
- **版本切换**：支持安装不同版本的 Go 环境
- **环境恢复**：系统重启后自动恢复 Go 环境
- **状态监控**：实时显示 Go 环境安装状态

### 持久化机制

- Go SDK 自动备份到 U 盘（`/boot/config/plugins/easy-dwgo/go-sdk.tar.gz`）
- 系统重启后自动检测并恢复 Go 环境
- 环境变量自动配置到系统级别

### Web 管理界面

- 直观的状态显示
- 版本选择和安装
- 实时进度监控
- 环境信息查看

## 🔧 高级配置

### 手动环境恢复

如果自动恢复失败，可以手动执行：

```bash
/usr/local/emhttp/plugins/easy-dwgo/scripts/go_manager.sh restore
```

### 检查 Go 状态

```bash
/usr/local/emhttp/plugins/easy-dwgo/scripts/go_manager.sh check
```

### 获取 Go 版本

```bash
/usr/local/emhttp/plugins/easy-dwgo/scripts/go_manager.sh version
```

## 📁 目录结构

```
/usr/local/emhttp/plugins/easy-dwgo/
├── scripts/
│   ├── go_manager.sh          # Go 环境管理脚本
│   └── download_go.sh        # Go 下载脚本
├── index.php                  # Web 管理界面
├── api.php                    # API 接口
└── EasyDwgo.Main.page        # 主页面配置

/boot/config/plugins/easy-dwgo/
├── go-sdk.tar.gz             # Go SDK 备份文件
└── version.conf              # 版本配置文件
```

## 🐛 故障排除

### 常见问题

**Q: 安装后 Go 命令不可用？**
A: 请检查环境变量是否正确设置，可以尝试重新安装或手动恢复环境。

**Q: 重启后 Go 环境丢失？**
A: 检查 `/boot/config/plugins/easy-dwgo/go-sdk.tar.gz` 文件是否存在，如果存在但未自动恢复，请手动执行恢复脚本。

**Q: 下载失败？**
A: 请检查网络连接，确保可以访问 golang.org。

### 日志文件

- 插件日志：`/var/log/easy-dwgo.log`
- 下载日志：`/var/tmp/easy-dwgo-progress/go.log`

## 🗑️ 卸载

1. 在 Unraid Web 界面中进入 **Plugins** 页面
2. 找到 easy-dwgo 插件
3. 点击 **Remove** 按钮
4. 确认卸载

卸载将自动清理：
- Go SDK 文件
- 环境变量配置
- 开机自动恢复配置
- 所有相关目录和文件

## ⚠️ 重要声明

**这是自用测试版本**，具有以下特点：

- 🧪 **测试性质**：仅供个人学习和测试使用
- 🔧 **功能可能不稳定**：某些功能可能存在问题或未完全实现
- 📝 **文档可能不完整**：使用说明可能不够详细
- 🚫 **不建议生产使用**：不建议在生产环境中使用此版本
- 🔄 **持续改进**：会根据使用反馈持续改进和完善

## 🤝 贡献

欢迎提交 Issue 和 Pull Request 来帮助改进这个项目！

## 📄 许可证

本项目采用 MIT 许可证。

## 👨‍💻 作者

**隔壁小王**

## 📞 支持

如果您在使用过程中遇到问题，可以通过以下方式获取支持：

- 提交 GitHub Issue
- 加入 Telegram 群组：https://t.me/+7jcTMePlNVwwZjg1

---

**免责声明**：本插件为测试版本，使用前请备份重要数据。作者不对使用本插件造成的任何损失承担责任。
