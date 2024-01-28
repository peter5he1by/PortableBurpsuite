# PortableBurpsuite

这是本人长期维护自用的便携式 BurpSuite 武器库，目前可能并不适合所有人，遇到问题请多多提 issue。

如果这个程序对您有帮助，请点个star让我知道，这将是我继续维护的动力。

## 已知BUG

- [x] 加载部分插件后，在上下文菜单项目较多时：
  - [x] 弹出顶级上下文菜单时会有一定延迟。*HackVector插件注册了过多的菜单项，现在默认关闭该插件*
  - [x] 在Repeater或相似的上下文菜单中光标指向'Convert Selection'时，会花费较多时间弹出其子菜单。*可以在菜单项上进行一点“拖拽”动作快速引出子菜单*


## 下载链接

密码：peterzh4ng

如果你下载 no_jre 版本（体积更小，但也没小多少），那么你需要在工具根目录放一个名为'jre'的JDK或JRE，或是它们的快捷方式。

请自行[下载burpsuite程序的jar包](https://portswigger.net/burp/releases?requestededition=professional&requestedplatform=Jar)，放置于jar目录下。

|源|链接|
| --- | --- |
|mega.nz|[https://mega.nz/folder/Je8UXAhC#ft-xK84MQOfsQ1O3CFVbug/file/UHtEwL4A](https://mega.nz/folder/Je8UXAhC#ft-xK84MQOfsQ1O3CFVbug/file/UHtEwL4A)|
|百度网盘|[https://pan.baidu.com/s/1JJ5YYbhTa66x6u-6lPKb2w?pwd=4cdq](https://pan.baidu.com/s/1JJ5YYbhTa66x6u-6lPKb2w?pwd=4cdq)|

## 注意事项

**请使用 `Start.exe` 启动**

- **插件并未经过安全审计，请在不包含敏感信息的虚拟机使用。**
- 仅支持 Windows；
- 仅支持较新版本的BurpSuite；

如果有任何需求可在此处提issue；

## 文件结构

```powershell
.bchecks           # BChecks
.configlib         # ConfigLibrary
.dont_touch        # 其它相关的配置、脚本等
.payloads          # Intruder字典路径
.plugin-libs       # 插件使用的库路径
.plugins           # 插件
jar                # BurpSuite程序包
jre                # jre
burp.project.json  # BurpSuite project settings，改动此文件不影响程序的便携性
jvm.args           # 启动burpsuite时jvm的参数（注意，这不是burpsuite程序的参数）
Start.exe          # *启动脚本（自动部署）

init.lock          # 初始化标记（空文件夹）
```
## 部署工具帮您做了什么？

生成证书保存于桌面，并导入计算机证书存储，对于使用系统证书存储的程序（如Chrome浏览器，但不包括Firefox），您不再需要手动导入证书。

![图片](https://github.com/peter5he1by/PortableBurpsuite/assets/86906331/83d7ce0b-d620-46ea-b607-325345f5b516)

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

- ~~什么都可以~~
- 如果您在使用自己的BurpSuite过程中发现了新的BUG（不在上文所述的“已知BUG”范围内），可以提供一些信息以帮助我解决那些BUG，不胜感激。

## ChangeLog

#### 2023-12-23

优化：

- 现在启动程序将生成证书并导入系统和burp，证书将被保存到桌面以供其它用途
- 默认最大化启动burp
- ~~精简JDK~~
- 移除部分插件
- 关闭了一个对Burp有很大负担的插件
- 使用JRE而不是JDK

修复：

- 此前Start.exe并不会申请UAC，但UAC是必要的

#### 2023-11-27

- 修复了一个bug，这个bug曾导致bchecks无法复制到用户的BurpSuite配置文件目录。

#### 2023-11-21

- 添加/更新了一些插件
- 支持向启动burpsuite的java.exe添加命令行参数

#### 2023-11-20

- 支持加载自定义的javaagent

#### 2023-11-15

- 将PortSwigger的BChecks仓库中的所有bchecks内置到包
- 改动了目录结构，减少干扰
