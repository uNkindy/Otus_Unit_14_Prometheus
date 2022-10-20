### Домашняя работа №14 (Prometheus)
#### 1. Установлен rpm пакет Prometheus v.2.37.1 (Last Stable Version);
- Проверена доступность веб-сайта Prometheus:
```console
[root@devops prometheus-2.37.1.linux-amd64]# curl localhost:9090
<a href="/graph">Found</a>.

[root@devops prometheus-2.37.1.linux-amd64]#
```
#### 2. Настроен конфигурационный файл [prometheus.yml](https://github.com/uNkindy/Otus_Unit_14_Prometheus/blob/main/prometheus.yml). Настроено получение метрик с хоста, на котором установлен Centos 7;
#### 3. На хост с Centos 7 установлен и запущен node-exporter;
#### 4. Скачан, настроен и запущен докер-контейнер с Grafana:
```console
[root@devops prometheus-2.37.1.linux-amd64]# docker ps
CONTAINER ID   IMAGE                        COMMAND     CREATED       STATUS       PORTS                                       NAMES
ea998fc39f6a   grafana/grafana-enterprise   "/run.sh"   9 hours ago   Up 9 hours   0.0.0.0:3000->3000/tcp, :::3000->3000/tcp   grafana
```
#### 5. Настроен firewalld для доступа к хосту (добавлен доверенный ip адрес):
```console
[root@devops prometheus-2.37.1.linux-amd64]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: p1p4
  sources:
  services: dhcpv6-client ssh vnc-server
  ports:
  protocols:
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
        rule family="ipv4" source address="192.168.2.94" accept
```
#### 6. В веб-интерфейсе Grafana создан новый dashboard Stanislav Krivoshhev;
#### 7. В dashboard добавлены следующие метрики:
- Загрузка ядер ЦП (герцы);
- Использованная оперативная память в процентах;
- Занятость раздела root жесткого диска в процентах;
- Количество переданных байт;
- Количество принятых байт;

#### 7. Скриншот dashboard [Stanislav Krivosheev]() прилагаю.
