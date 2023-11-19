# PortableBurpsuite

这是本人长期维护自用的便携式 BurpSuite 武器库，目前可能并不适合所有人，遇到问题请多多提 issue。

如果这个程序对你有帮助，请点个star让我知道，这将是我继续维护的动力。

## 下载链接

密码：peterzhang

|--源--|--链接--|

|mega.nz|[https://mega.nz/folder/Je8UXAhC#ft-xK84MQOfsQ1O3CFVbug/file/UHtEwL4A](https://mega.nz/folder/Je8UXAhC#ft-xK84MQOfsQ1O3CFVbug/file/UHtEwL4A)|

|百度网盘|[https://pan.baidu.com/s/1r8ai6fjr6jfiPrOQyGx7rw?pwd=z5i1](https://pan.baidu.com/s/1r8ai6fjr6jfiPrOQyGx7rw?pwd=z5i1)|


## 注意事项

**请使用 `start.vbs` 启动，不要直接运行其它任何脚本。**

- 仅支持 Windows，并且目前仅在 Windows 10 Build 19045 上测试过；
- 在这个包的基础上进一步自定义也许是很困难的，因为我暂时不打算向使用者提供进一步的自定义功能，这比较麻烦；
- 如果有任何需求可在此处提issue，由我来实现。
- **插件并未经过安全审计，请在不包含敏感信息的虚拟机使用**

## 文件结构

```powershell
.dont_touch        # init.exe 使用的配置模板
.payloads          # Intruder字典路径
.plugin-libs       # 插件使用的库路径
.plugins           # 插件
jar                # BurpSuite程序包
jdk-18.0.2.1       # jdk
burp.project.json  # BurpSuite project settings，改动此文件不影响程序的便携性
burpsuite.ico      # 图标（嗯没什么用）
start.vbs          # *启动脚本（自动部署）
```
## 我做了什么优化？（程序帮你做了什么？）

默认使用了 Scope，后面如果有需要的话会做这部分配置的更新机制。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/c0a41338-6e7b-4b89-84eb-9f4ed9ce180e)

配置好插件依赖。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/e540b0b1-9f39-409d-8d61-bb88bc78bbc7)

使用 Intruder 的 PayloadPosition 预置一些字典，这个也可以提供更新机制。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/215388a8-b7ef-45ad-ac19-6f896f615851)

Repeater 可以使用 Ctrl+S 发包。

预先载入了几个常用的比较“老实的”插件。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/12a1d3ec-fbcb-429c-839d-4181b1598fc9)

收集了一些其它的插件，按需勾选使用。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/fa2c2b80-4e5b-417e-ad7d-4db032d4427c)

给 [HaE](https://github.com/gh0stkey/HaE) 提了 issue，他们已经让 HaE 支持便携的配置文件了，不用担心内网环境需要下载 HaE 的在线规则了。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/e8ed5bcb-b4a6-4ab4-94dc-4c5ddb65c6a6)

OneScan 对便携配置文件的支持还有些问题，不过目前也已经能内置一些字典了，字典来自@三娃子，在f0ng的[log4j2burpscanner](https://github.com/f0ng/log4j2burpscanner)交流群可以抓到他。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/5d560569-6284-4420-bbf4-3fd142e02ffb)

加入我能找到的所有开源的BChecks

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/fe9c24d4-5cb4-402b-a23c-76108bc1bd6c)


## 为这个项目做点什么？

- 什么都可以

## 鸣谢

- [ ] TODO

## ChangeLog

##### 2023-11-15

- 将PortSwigger的BChecks仓库中的所有bchecks内置到包
- 改动了目录结构，减少干扰
