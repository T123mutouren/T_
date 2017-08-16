# redis

> Redis 是完全开源免费的，遵守BSD协议，是一个高性能的key-value数据库

## 特点

- Redis支持数据的持久化，可以将内存中的数据保存在磁盘中，重启的时候可以再次加载进行使用。
- Redis不仅仅支持简单的key-value类型的数据，同时还提供list，set，zset，hash等数据结构的存储。
- Redis支持数据的备份，即master-slave模式的数据备份。

## 优势
> 性能高（读写速度快）、丰富的数据类型、原子性、丰富的特性（支持 publish/subscribe, 通知, key 过期等等特性）  
> 运行在内存可以持久化到磁盘，要注意数据量不能大于硬件内存。  
> 在磁盘格式方面他们是紧凑的以追加的方式产生的，因为他们并不需要进行随机访问。

## Install
> 在官网下载安装包进行安装  
> 打开一个 cmd 窗口 使用cd命令切换目录到 C:\redis 运行 `redis-server.exe redis.windows.conf` 。  
> 这时候另启一个cmd窗口，原来的不要关闭，不然就无法访问服务端了。  
> 切换到redis目录下运行 `redis-cli.exe -h 127.0.0.1 -p 6379 `。  
> 设置键值对 `set myKey abc `  
> 取出键值对 `get myKey`

## Redis 配置 
*Redis 的配置文件位于 Redis 安装目录下，文件名为 redis.conf。*  
*可以通过 **CONFIG** 命令查看或设置配置项。*

> 获取配置项`redis 127.0.0.1:6379> CONFIG GET CONFIG_SETTING_NAME`  
> 获取所有配置项 `redis 127.0.0.1:6379> CONFIG GET *`

### 编辑配置
> 你可以通过修改 redis.conf 文件或使用 CONFIG set 命令来修改配置。  
> `redis 127.0.0.1:6379> CONFIG SET CONFIG_SETTING_NAME NEW_CONFIG_VALUE`

## Redis 数据类型 
_Redis支持五种数据类型：string（字符串），hash（哈希），list（列表），set（集合）及zset(sorted set：有序集合)。_

1. string _string是redis最基本的类型,可以包含任何数据。一个键最大能存储512MB。_
	> 设置命令 ：`SET key_name "value"`，`GET key_name`

1. Hash(哈希) _Redis hash 是一个键名对集合。一个string类型的field和value的映射表，hash特别适合用于存储对象。_
	> 设置命令 ：`HMSET user:1 username runoob password`，`HGETALL user:1`。

1. List(列表) _Redis 列表是简单的字符串列表，按照插入顺序排序。你可以添加一个元素到列表的头部（左边）或者尾部（右边）。_
	> 设置命令：`lpush runoob redis`，`lrange runoob 0 10`

1. Set(集合) _Redis的Set是string类型的无序集合。集合是通过哈希表实现的，所以添加，删除，查找的复杂度都是O(1)。_
    > 设置命令：`sadd key member`，`smembers runoob`  
    > 添加一个string元素到,key对应的set集合中，成功返回1,如果元素已经在集合中返回0,key对应的set不存在返回错误。

1. 
