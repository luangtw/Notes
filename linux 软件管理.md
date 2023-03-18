# linux 软件管理

ps aux | grep 进程名          # 查看此程序所有进程
service mysql start           # 启动mysql
service mysql stop            # 关闭mysql
netstat -lnp|grep 80          # 查看80端口占用程序


进程查看信息
User PID CPU占用 内存占用 VSZ虚拟内存大小 RSS物理内存大小 TTY终端 State进程状态 Start启动时间 \ Command启动命令
