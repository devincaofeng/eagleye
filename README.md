## 简易网盘

支持多用户登录，客户端自动上传指定目录下的所有文件，服务端基于 reactor 模式，采用 epoll+多线程，增大并发量。
数据库使用 mysql，libzlog 作为日志库，最终将用户文件存到 fastDFS 分布式文件系统中，改善了数据的持久性

### 主要文件说明
- cli.c      客户端文件，负责上传指定目录下的所有文件
- ctrl.c     外部管控文件，按需改变程序执行状况
- list.c     封装一个链表，及链表常用操作
- log.c      日志模块
- monitor.c  程序主逻辑，用于监听，建立客户端连接
- mysql_db.c 存储用户信息。
- recv.c     服务器用来接收客户端文件
- scan_dir.c 递归扫描目录下的所有文件
- send.c     向存储服务器发送文件
- user.c     用户信息结构体
- wrap.c     包裹系统函数
