### Развертывание HADOOP в Yandex Cloud (hdp-sandbox)
Необходимая конфигурация VM: 
- 16Гб RAM
- 50Гб HDD
- Ubuntu 20.04

#### Порядок развертывания:
```
ssh zvezdochetast@your.vm.ip.address
echo "your.vm.ip.address sandbox-hdp.hortonworks.com" | sudo tee -a /etc/hosts
git clone https://github.com/zvezdochetast/hdp-sandbox.git
git checkout dev
docker compose up -d (или docker-compose up -d)
docker exec -it sandbox-hdp bash
```

- Выполнить команду `ambari-server status` для проверки того, что Ambari запущен. В выводе команды должно присутствовать `Ambari Server running`.
- Выполнить команду `ambari-admin-password-reset`, придумать и ввести пароль пользователя `admin`.
- Открыть в браузере своего компьютера страницу `http://sandbox-hdp.hortonworks.com:8081`.
Имя пользователя: "admin", пароль - пароль, придуманный на шаге 8.
- Запустить службы HDFS, YARN, Hive, Spark2, Zeppelin Notebook и Data Analytics Studio.

