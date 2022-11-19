
macOS 和 Linux 版本在此发布：

支持

- macOS High Sierra 10.13 and higher
- Debian 9 (Stretch) and higher
- Ubuntu 16.04 and higher
- Fedora 30 and higher


## macOS
下载最新的.dmg包，双击安装即可。


## Linux
下载最新的压缩包，然后

- 解压压缩包：`tar -zxvf KA-1.1.7.2-linux-x64.tar.gz`
- 设置语言环境（或略此步骤可能导致软件启动报错）：`export LANG=en_US.UTF-8`
- 运行：`./KA-1.1.7.2-linux-x64/KafkaAssistant`

## 常见问题

- 关于Mac版本**安装时**报错：“已损坏，无法打开。 您应该将推出磁盘映像”，是因为当前版本未进行签名，被Mac GateKeeper机制拦截。通过以下步骤来暂时关闭Getakeeper（安装后再打开）：

    1. 在“系统偏好设置” -> “安全与隐私” 中选择 “任何来源”；如果您的系统没有此选项，在终端中执行以下命令后再次打开此设置页，然后勾选“任何来源”：`sudo spctl --master-disable`
    1. 双击安装 Kafka Assistant 即可。

    1. 安装完成之后，您应该还原之前的设置，这会保护您的Mac免受恶意软件的骚扰，通过以下命令打开 Getakeeper：`sudo spctl --master-enable`

---

- 关于Mac版本**运行时**报错：“已损坏，无法打开。 您应该将它移到废纸篓”，是因为当前版本未进行签名，被Mac GateKeeper机制拦截；打开终端输入以下命令来解除对 Kafka Assistant 的隔离：`sudo xattr -rd com.apple.quarantine /Applications/Kafka\ Assistant.app`

---

- 关于Mac/Linux版本**运行时**奔溃（黑苹果出现过此现象），请检查`$HOME/.local/share` 目录是否存在，如果不存在，请手动建立后再次打开Kafka Assistant。`$HOME/.local/share` 是存储用户特定数据文件的基本目录。关于此目录的更多介绍与规范，请查看：https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html

---

- 关于Linux版本打开时报错：“Unhandled exception. System.InvalidOperationException: Default font family name can't be null or empty.”，需要在运行前设置语言环境：`export LANG=en_US.UTF-8`
，然后再次运行：`./KA-1.1.7.2-linux-x64/KafkaAssistant`