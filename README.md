# PortableBurpsuite

## 注意事项

- 仅支持 Windows，并且目前仅在 Windows 10 Build 19045 上测试过；
- 在这个包的基础上进一步自定义也许是很困难的，因为我并未打算向使用者提供进一步的自定义功能；
- 如果有任何需求可在此处提issue，由我来实现。

## 文件结构

```powershell
.dont_touch        # init.exe 使用的配置模板
.payloads          # Intruder字典路径
.plugin-libs       # 插件使用的库路径
.plugins           # 插件
jar                # BurpSuite程序包
jdk-18.0.2.1       # jdk
burp.project.json  # BurpSuite project settings，改动此文件不影响程序的便携性
burpsuite.ico      # 图标
init.exe           # 配置部署工具，没加壳
keygen.cmd         # 用于单独启动密钥生成工具
start.ps1          # 部署脚本，由vbs调用来隐藏console
start.vbs          # 启动脚本（自动部署）
```

## 下载链接

[https://mega.nz/folder/Je8UXAhC#ft-xK84MQOfsQ1O3CFVbug/file/UHtEwL4A](https://mega.nz/folder/Je8UXAhC#ft-xK84MQOfsQ1O3CFVbug/file/UHtEwL4A)
