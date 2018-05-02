https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker

### 1.HyperV-Manager>HypervSettings>Virtual hdd   dockerdisk image yolu seçilir.
### 2.Docker for windows kurulur
### 3.Docker restart yapılır
---------------------------------------------------------

Aspnet core için docker,

https://stormpath.com/blog/tutorial-deploy-asp-net-core-on-linux-with-docker



http://www.enterprisecoding.com/post/yeni-baslayanlar-icin-docker
# Docker Komutları #
Çalışan Container’ları listelemek için

docker ps
Tüm container’ları listelemek için;
docker ps -a

Çalışan bir container’ı durdurmak için;
docker stop  [CONTAINER_ID]

Container’ı silmek için;
docker rm [CONTAINER_ID]

Docker imajını silmek için;
docker rmi [İMAJ_ADI]

Tüm Docker Container’larını silmek (Linux, Mac OS)
* docker rm $(docker ps -a -q)
* docker rm -f $(docker ps -a -q)

Tüm Docker imajlarını silmek (Linux, Mac OS)
docker rmi $(docker images -q)

# Docker dan makinaya
````
docker cp gok-mongo:/Mongox.json d:\mongo1.json
````

# Bash erişim
* PS C:\Users\Gokmen1977> docker exec -i -t  f9021a6b89e1  /bin/bash
* linux version : cat /etc/issue
* Dockerdan local makina current foldera kopyalama
 -- docker cp 506f:/var/opt/mssql/log/errorlog .



# Sql Server Linux 
powershell i yönetici olarak aç

image çekmek için sanal ram 4GB olmalı !!!!!!
parola : 8 hane strong olmalı  (Büyük harf vs yoksa çalışmaz)
localhost yazıp bağlan farklı port için (localhost,1402)

docker exec -it tomssl_sql /opt/mssql-tools/bin/sqlcmd -S localhost -U sa
ile test yap


https://tomssl.com/2018/01/15/running-microsoft-sql-server-on-a-linux-container-in-docker/

docker pull microsoft/mssql-server-linux

docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Ankara!06' -p 1401:1433 --name sql1 -d microsoft/mssql-server-linux

docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Ankara!06' -p 1500:1433 -v d:\pcdata:/var/opt --name sql1 -d microsoft/mssql-server-linux


docker ps -a

docker start af56 (id)

docker container prune  çalışmayan containerler silinir  

linux a erişim ;  
docker exec -i -t f9021a6b89e1 /bin/bash
varsayılan yol : root@f9021a6b89e1:/var/opt/mssql/data#

localden docker a dosya
docker cp 24092017_db1 7145:/var/pandapdb.bak     *7145 container id

çalışmazsa log kayıtlarından niye çalışmadığına bak

linqpad kullan erişmek için

# my sql
user=root olacak
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -p 3306:3306 -d mysql

# postgree sql
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres

# mongodb
kullanıcı istemez
docker run --name some-mongo -p 27017:27017 -d mongo

# Oracle
docker run -d -p 49160:22 -p 49161:1521 -e ORACLE_ALLOW_REMOTE=true wnameless/oracle-xe-11g

* hostname: localhost
* port: 49161
* sid: xe
* username: system
* password: oracle


# Windows Container

Nano Server oluşturarak işlemler yapılır
https://docs.microsoft.com/en-us/virtualization/windowscontainers/quick-start/quick-start-windows-10

