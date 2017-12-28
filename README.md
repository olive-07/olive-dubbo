# olive-dubbo
项目来源：http://m.blog.csdn.net/wangbo54979/article/details/77773110

1:首先介绍windows下安装redis: redis这部分采取 http://blog.csdn.net/jquerys/article/details/48624949博主的博文 我看他上面写的挺好就不自觉写了直接截图重要部分来说 1、Redis简介 redis是一个key-value存储系统。和Memcached类似，它支持存储的value类型相对更多，包括string(字符串)、list(链表)、set(集合)、zset(sorted set --有序集合)和hashs（哈希类型）。这些数据类型都支持push/pop、add/remove及取交集并集和差集及更丰富的操作，而且这些操作都是原子性的。在此基础上，redis支持各种不同方式的排序。与memcached一样，为了保证效率，数据都是缓存在内存中。区别的是redis会周期性的把更新的数据写入磁盘或者把修改操作写入追加的记录文件，并且在此基础上实现了master-slave(主从)同步。

Redis 是一个高性能的key-value数据库。 redis的出现，很大程度补偿了memcached这类key/value存储的不足，在部分场合可以对关系数据库起到很好的补充作用。它提供了Python，Ruby，Erlang，PHP客户端，使用很方便。

2、windows下安装redis 下载地址https://github.com/dmajkic/redis/downloads。下载到的Redis支持32bit和64bit。根据自己实际情况选择，我选择32bit。把32bit文件内容拷贝到需要安装的目录下,比如：D:\dev\redis-2.4.5。

打开一个cmd窗口，使用cd命令切换到指定目录（D:\dev\redis-2.4.5）运行 redis-server.exe redis.conf 。运行以后出现如下界面。

这就说明Redis服务端已经安装成功。

重新打开一个cmd窗口，使用cd命令切换到指定目录（D:\dev\redis-2.4.5）运行 redis-cli.exe -h 127.0.0.1 -p 6379，其中 127.0.0.1是本地ip，6379是redis服务端的默认端口。运行成功如下图所示。 这样，Redis windows环境下搭建已经完成，是不是很简单。

这样，Redis windows环境下搭建已经完成，是不是很简单。

环境已经搭建好，总得测试下吧。比如：存储一个key为test，value为hello word的字符串，然后获取key值。

正确输出 hell word，测试成功！

2:dubbo windows下的安装简介:

1：下载zookeeper ，稳定版3.4.8，最新版3.5.1，解压后，进入到conf目录，复制一份zoo_sample.conf，改名为zoo.conf，用无格式编辑器（比如sublime text，notepad等）打开，修改dataDir=/tmp/zookeeper为你的动物园管理员数据存放路径，比如笔者的为D：/软件/ zookeeperData /动物园管理员，修改为dataDir=D:/software/zookeeperData/zookeeper，保存即可，如果要配置ZK集群，还需要其他配置，暂时不说集群这一块，后面涉及到了再说。 zookeeper国内下载镜像地址：http ://mirrors.hust.edu.cn/apache/zookeeper/ bin /找到启动服务点击运行成功之后

2：下载JDK，maven安装配置这基础的东西就不说了找文档看看就会

3：dubbo-admin.war 这个战争包是阿里达博团队开发的一个可视化操作达博的后台管理服务，可是查看机器，提供者，消费者，以及手动配置负载权重等。将次包下载后，放在tomcat的的的webapps目录下，如果你的tomcat的和动物园管理员不是同一台服务器，需要修改战争包下的配置文件，将地址指向的动物园管理员的服务地址，端口是动物园管理员的端口，默认2181。

如果对于只是想搭建完了 测试看下效果 上面zookeeper 安装步骤下载安装运行就行 dubbo-admin.war 那就不是重点了
