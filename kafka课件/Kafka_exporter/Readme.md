##### 一： 查看版本

```
/opt/prometheus/client/kafka_exporter/kafka_exporter --version
```

##### 二： 守护进程启动配置文件

kafka-exporter-prd.conf

```
[program:kafka-exporter-prd]
command=/opt/prometheus/client/kafka_exporter/kafka_exporter --kafka.server=01.qq.cn:9092 --kafka.server=02.qq.cn:9092 --kafka.server=03.qq.cn:9092 --kafka.version=1.0.2 --log.level=info
numprocs=1
directory=/opt/prometheus/client/kafka_exporter/
user=wwwuser
autorestart=true
redirect_stderr=true
stdout_logfile=/home/data/logs/kafka_exporter/prd/kafka_exporter-prd.log
loglevel=info
environment=MALLOC_ARENA_MAX="1"

```

