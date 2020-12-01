redis-server
6379	6380	6381
注意修改redis.conf的
port
logfile
pid
dbfilename
pidfile

slaveof  127.0.0.1 6379 
slaveof  127.0.0.1 6379

redis-sentinel
26379	26380	26381
sentinel.conf
port
pidfile
logfile
sentinel monitor mymaster