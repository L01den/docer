nano dockerfile (рис 1.)         // прописываю команду      
                                               
    FROM ubuntu:22.04

    RUN apt-get update

    RUN apt-get install -y mariadb-server


    ENV MARIADB_ROOT_PASSWORD="111"
    ENV MARIADB_USER="qqq"


    EXPOSE 3306


    LABEL version="1.0"

    LABEL description="MariaDB Server"


    HEALTHCHECK --start-period=5m \

    CMD mariadb -e 'SELECT @@datadir;' || exit 1


    CMD ["mysqld"]


sudo docker build -t mdb .

sudo docker container ls -a     //узнала имя контейнера

sudo docker start 6619d3e689e2  // запуск контейнера

sudo docker run --name test5 -d --link 6619d3e689e2:db -p 8082:80 phpmyadmin/phpmyadmin




