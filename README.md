# srv
##游戏简介
* 该游戏是休闲益智游戏, 主要玩法移动方格进行拼图
* 服务器实现的主要功能是处理玩家的登录, 保存玩家上传的图形关卡, 关卡的点赞, 根据点赞进行排行等功能

##服务器实现
* 数据库建库, 落地全部使用gorm进行操作
* 服务器与客户端的通信使用websocket, 之前一个版本使用的是tcp, 因为客户端不好支持所以改了, 不过修改起来很方便
* 协议通信使用的json格式
* 并发模型使用的多线程, 每个客户端连接会创建一个连接线程, 消息收发通过channel送到不同的接受和发送线程

##各文件夹介绍
* admin 配置脚本
* bin 可执行文件
* conf 服务器配置文件, 暂时只有mainserver和mysql是起作用的
* log 游戏运行日志
* pkg 编译生成的中间文件
* script 启动脚本等
* src 源代码, 各文件作用, 见注释

##编译
./admin make生成main_server和mysql两个可执行文件
* mysql 初始化数据库
* main_server 游戏主服务

