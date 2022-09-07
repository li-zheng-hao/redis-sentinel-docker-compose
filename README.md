# redis-sentinel-docker-compose
redis哨兵 docker compose版本


# 启动(测试)


1. 进入redis文件夹，修改密码和ip地址后执行：


```
docker-compose -f docker-compose.yaml up -d
```

2. 进入sentinel文件夹，修改密码和ip地址后执行：

```
docker-compose -f docker-compose.yaml up -d
```

3.使用 Another Redis Desktop Manager工具连接集群,手动停止主节点,在管理界面可以看到主节点自动切换,然后手动启动主节点，可以看到主节点变成了从节点


# 生产环境使用

示例的文件中3个主从节点、3个哨兵都是部署在同一个物理机上,是达不到高可用的,因此在生产环境需要将上面的docker-compose文件拆分为3个,分别在3台主机上部署,哨兵也是同理,最少需要三台物理主机,每一台都放一个哨兵和存储数据的节点,这样一台宕机之后还剩下2个哨兵和2个工作节点，还能进行正常使用
