# Prometheus + Alertmanager告警Tomcat异常情况

* 对应文章: 无
* jmx-exporter config: [jmx-exporter-config.yml](jmx-exporter-config.yml)
* Prometheus rules: [prom-alert-rules.yml](prom-alert-rules.yml)
* Alertmanager config: [alertmanager-config.yml](alertmanager-config.default.yml)
* Grafana dashboard: [Tomcat dashboard](https://grafana.com/dashboards/8704)

用法：

复制`alertmanager-config.default.yml`文件到文件名`alertmanager-config.yml`。设置smtp相关配置，以及下面`user-a`的邮箱。

**邮箱发送失败问题**

中国的企业/个人邮箱几乎都不支持TLS（见这个[issue][issue]），因此请用gmail邮箱。

```bash
# docker run所有容器
./demo.sh run

# docker stop所有容器
./demo.sh stop

# docker start所有容器
./demo.sh start

# docker restart所有容器
./demo.sh restart

# 清理prom-data和grafana-data
./demo.sh clear-data

# docker rm所有容器
./demo.sh clear-container
```

[issue]: https://github.com/prometheus/alertmanager/issues/980#issuecomment-328088587
