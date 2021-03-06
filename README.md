# 本地Windows系统下安装Yunzai-Bot
> <center>本教程撰于 2022-05-05 11:18 ，请注意时效性</center>

如果使用云服务器部署 可省去以下步骤：

【云服务器部署】2 无需将Redis添加为服务 直接点击redis-server.exe启动程序并不要关掉窗口

【云服务器部署】4 无需安装SmartSystemMenu插件 因为不需要后台运行git bash窗口

【云服务器部署】 扫码登录：需要搭建pptp / 密码+验证码登录： 无需搭建pptp

# 更新记录

**2022-05-08** [miao-plugin更新依赖项，需要npm安装moment库！！（详情见步骤 6 ）](#2022-05-08-更新)


# b站原教程地址

<ul>
<a href="https://www.bilibili.com/read/cv15119056?spm_id_from=333.999.0.0">https://www.bilibili.com/read/cv15119056?spm_id_from=333.999.0.0
</a>
</ul>

# b站视频教程
<ul>
<a href = "https://www.bilibili.com/video/BV1aY4y1a7Fz?spm_id_from=333.999.0.0">https://www.bilibili.com/video/BV1aY4y1a7Fz?spm_id_from=333.999.0.0
</a>
</ul>


# 需要软件
**[vs code](https://code.visualstudio.com/)**

# 1 安装nodejs
下载地址
<ul>
<a href="http://nodejs.cn/download/">http://nodejs.cn/download/</a>
</ul>

下载完成后进行安装

- 如果出现Change, repair, or remove installation界面，点击Change选项

安装完成后，按下 **Win** + **R** 键打开运行窗口，输入 `CMD` 打开命令行窗口

分别输入以下指令检查node是否安装成功

```powershell
node -v
npm -v
```

如果均出现版本号，则安装成功

- 如果未出现版本号，请确定node js是否安装成功，可以尝试以下方法解决：
	- 百度搜索 *将nodejs添加到环境变量*
	- 百度搜索 *将npm添加到环境变量*
	- 检查 *nodejs* 的安装路径，确认是否安装成功

# 2 下载Redis 完成安装和运行
下载地址
<ul>
<a href="https://github.com/tporadowski/redis/releases">https://github.com/tporadowski/redis/releases</a>
</ul>

点击名为"Redis-x64-xxx.zip"的文件进行下载，其中xxx为版本号

下载完成后，解压文件到你想存放的目录即可

~~将Redis安装成服务~~ 根据自己的部署环境分别执行以下步骤：

云服务器

- 云服务器部署请直接双击运行redis-server.exe并最小化窗口即可（不能关闭）

本地部署

- 本地部署推荐将Redis安装成服务，方法如下
```powershell
# 进入redis的目录 在地址栏输入cmd
# 执行以下指令
	redis-server --service-install redis.windows.conf --loglevel verbose
# (安装redis服务）
```
- windows中搜索"服务"并打开
- 在服务中找到【Redis】并启动该服务

# 3 下载Git并安装
下载地址

- https://git-scm.com/downloads

选择"Windows"版本进入，点击"Click here to download"进行下载

下载完成后进行安装

# 4 下载SmartSystemMenu
~~推荐使用该插件可以最小化cmd窗口~~
推荐使用本地部署方式的下载此插件 **可以最小化cmd窗口** 并且可以随时查看运行状态 

云服务器直接跳过此步 因为直接挂着也不影响

- 注：安装能最小化到任务栏运行的console、直接将bot后台运行都可以，有能力可自行实现

SmartSystemMenu插件下载地址：

- https://github.com/AlexanderPro/SmartSystemMenu/releases

解压并启动SmartSystemMenu.exe

在任务栏中找到程序图标，右击勾选"自动启动程序"

# 5 克隆Yunzai-Bot项目
在你想存放机器人的文件夹中右击选择【Git Bash Here】

在Git Bash窗口中执行以下指令

```bash
	git clone https://gitee.com/Le-niao/Yunzai-Bot.git
```

# 6 打开Yunzai-Bot文件夹 安装相应模块
在Yunzai-Bot目录下 右击选择【Git Bash Here】

在Git Bash窗口中执行以下命令

```bash
npm install -g cnpm --registry=https://registry.npmmirror.com
cnpm install
#（cnpm这条命令只能手动输入，不能粘贴 粘贴可能会报错）
```


# 2022-05-08 更新

喵喵插件需要新的依赖项 `moment` ，请在Yunzai-Bot目录下【Git Bash Here】并输入以下指令。(接上方 `cnpm install` 指令执行完成后)
```bash
npm install moment
```

# 7 安装喵喵插件Miao-Plugin
打开 *Yunzai-Bot目录* 下的 **plugins** 文件夹 右击选择【Git Bash Here】

在Git Bash窗口中执行以下命令

```bash
    git clone https://gitee.com/yoimiya-kokomi/miao-plugin.git
```

# 8 获取米游社Cookie
登录网页版米游社

【F12】打开控制台

执行指令

```javascript
    document.cookie
```

复制返回的内容并保存到新建文档中

# 9 启动Redis服务
在服务中打开Redis服务 

//前面已经启动过

# 10 初次启动程序
有两种启动方法 如果第一种方法出现无法输入q号等情况的话尝试第二种

方法1 

* 在Yunzai-Bot文件夹中右击选择【Git Bash Here】
* 执行以下指令启动程序
```bash
    	node app
```
* 填写相应数据 完成启动

方法2

* 打开Yunzai-Bot目录下的config文件夹
* 复制一份【config_default.js】，并重命名为【config.js】
* 使用vs code打开【config.js】
```json
// 填写【account】栏目下的【qq】和【pwd】
// 将刚才保存的Cookie粘贴到【mysCookies】栏目后面的[  ]内 
// 示例：
		mysCookies:[ (把cookie粘贴到这里) ,]
// 在【masterQQ:】后面的[]内填写大号作为管理员qq
// 其他属性请自行更改
```
* 填写完成后保存 回到Yunzai-Bot目录下
* 右击选择【Git Bash Here】
* 执行以下指令启动程序
```bash
    	node app
```

启动程序后，右击窗口栏，选择 系统托盘>最小化到托盘 即可后台运行

# 11 再次启动/关闭程序
# 启动
1 启动Redis

搜索并打开服务列表，启动Redis

2 在Yunzai-Bot目录下右击选择【Git Bash Here】

执行命令

```bash
     node app
```

3 将窗口最小化到托盘

# 关闭
1 打开最小化的git窗口 将其关闭

2 关闭Redis

搜索并打开服务列表，关闭Redis

# 结尾

- 免责声明：本教程参考自该项目作者Le-niao撰写的原版教程。
- 文章转载许可：允许转载，声明出处即可。
	- 引用格式示例：
	- [1] [举杯对月未成双](https://gdufs2920.cloud/).[【本地/云服务器】Windows系统下安装Yunzai-Bot[DB/OL]](https://gdufs2920.cloud/bob200057/35/).(2022-05).https://gdufs2920.cloud/bob200057/35/
- 本文使用 <a href="https://segmentfault.com/markdown" target="_blank" rel="noopener"><i class="iconfont icon-markdown" style="color:#000"></i> **Markdown**</a> 格式进行编写与预览，如有排版问题欢迎留言。(评论已支持 <a href="https://segmentfault.com/markdown" target="_blank" rel="noopener"><i class="iconfont icon-markdown" style="color:#000"></i> **Markdown**</a> 格式，暂不支持**HTML**标签)

有什么问题欢迎提issue，邮箱、b站私信、qq均可，在能力范围内可以帮忙。
