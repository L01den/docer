sudo docker run -h myPostgres --name myPostgres -e POSTGRES_PASSWORD=111 -d postgres    //создаём контейнер с postgres
sudo docker start myPosgres     //запускаем контейнер
sudo docker exec -it  myPostgres bash   //входим в контейнер
psql -U postgres -d postgres    //заходим в postgres
create database test;    // создаём базу данных 
\l  //смотрим все базы данных
sudo docker run --name myphp -d --link myPostgres:db -p 8082:80 phpmyadmin/phpmyadmin   // создаём phpmyadmin с postgres внутри
    // зайти не удалось, но веб открылся по этому хосту




