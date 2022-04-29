# Windows-Install-Yunzai-Bot
# b站原教程地址
https://www.bilibili.com/read/cv15119056?spm_id_from=333.999.0.0
# b站视频教程
https://www.bilibili.com/video/BV1aY4y1a7Fz?spm_id_from=333.999.0.0

# 需要软件
vs code

# 1 安装nodejs
下载地址
    http://nodejs.cn/download/
下载完成后进行安装
    //如果出现Change, repair, or remove installation界面，点击Change选项
安装完成后，按下"Win"+"R"键打开运行窗口，输入CMD打开命令行窗口
分别输入指令检查node是否安装成功
    node -v
    npm -v
如果均出现版本号，则安装成功

# 2 下载Redis并解压 安装相应服务
下载地址
    https://github.com/tporadowski/redis/releases
点击名为"Redis-x64-xxx.zip"的文件进行下载，其中xxx为版本号

下载完成后，解压文件到你想存放的目录即可
将Redis安装成服务
    进入redis的目录 在地址栏输入cmd
    执行指令
        redis-server --service-install redis.windows.conf --loglevel verbose
        （安装redis服务）
    windows中搜索"服务"并打开
    在服务中找到【Redis】并启动该服务

# 3 下载git
下载地址
    https://git-scm.com/downloads
    选择"Windows"版本进入，点击"Click here to download"进行下载
下载完成后进行安装

# 4 下载SmartSystemMenu（或任意可后台运行的console）
    https://github.com/AlexanderPro/SmartSystemMenu/releases
解压并启动SmartSystemMenu.exe
在任务栏中找到程序图标，右击勾选"自动启动程序"

# 5 克隆Yunzai-Bot项目
在你想存放机器人的文件夹中右击选择【Git Bash Here】
    git clone https://gitee.com/Le-niao/Yunzai-Bot.git

# 6 打开Yunzai-Bot文件夹 安装相应模块
    npm install -g cnpm --registry=https://registry.npmmirror.com
    cnpm install
    （cnpm这条命令只能手动输入，不能粘贴 粘贴会报错）

# 7 打开plugin文件夹 安装喵喵插件Miao-Plugin
    git clone https://gitee.com/yoimiya-kokomi/miao-plugin.git

# 8 获取米游社Cookie
登录网页版米游社
【F12】打开控制台
执行指令
    document.cookie
复制返回的内容并保存到新建文档中

# 9 启动Redis服务
在服务中打开Redis服务 //前面已经启动过

# 10 初次启动程序
有两种启动方法 如果第一种方法出现无法输入q号等情况的话尝试第二种
方法1 
    在Yunzai-Bot文件夹中右击选择【Git Bash Here】
    执行以下指令启动程序
        node app
    填写相应数据 完成启动
方法2
    打开Yunzai-Bot目录下的config文件夹
    复制一份【config_default.js】，并重命名为【config.js】
    使用vs code打开【config.js】
        填写【account】栏目下的【qq】和【pwd】
        将刚才保存的Cookie粘贴到【mysCookies】栏目后面的[  ]内 
            示例：
            mysCookies:[ (把cookie粘贴到这里) ,]
        在【masterQQ:】后面的[]内填写大号作为管理员qq
        其他属性请自行更改
    填写完成后保存 回到Yunzai-Bot目录下
    右击选择【Git Bash Here】
    执行以下指令启动程序
        node app

启动程序后，右击窗口栏，选择 系统托盘>最小化到托盘 即可后台运行

# 11 再次启动/关闭程序
# 启动
1 启动Redis
    搜索并打开服务列表，启动Redis
2 在Yunzai-Bot目录下右击选择【Git Bash Here】
    执行命令
        node app
3 将窗口最小化到托盘
# 关闭
1 打开最小化的git窗口 将其关闭
2 关闭Redis
    搜索并打开服务列表，关闭Redis
