port  7001	7002	7003	7004	7005	7006
bind 127.0.0.1       		 #绑定当前机器 IP，如果安装在docker下，这里是0.0.0.0
daemonize    yes	         #后台运行Redis
cluster-enabled yes 		 #取消注释，启动集群模式
cluster-config-file	nodes-7001.conf 	
pidfile /usr/local/bob/skynet-demo/redis/7001/redis.pid   #以各自的端口号命名
cluster-node-timeout 15000                    # 取消注释，集群节点超时时限
appendonly yes 			        # 将 no 修改为 yes，开启aof持久化
dir "/usr/local/bob/skynet-demo/redis/7001/"

创建集群
./redis-cli --cluster create --cluster-replicas 1 127.0.0.1:7001 127.0.0.1:7002 127.0.0.1:7003 127.0.0.1:7004 127.0.0.1:7005 127.0.0.1:7006
