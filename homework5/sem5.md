##### 1. Cоздать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД

nano docker-compose.yml (рис 1.)

sudo docker-compose up (рис 2, 3)
    // Abminer с ДБ рис 4, 5 

##### 2. Cоздать 3 сервиса в каждом окружении (dev, prod, lab)

sudo docker swarm init (рис 6.)

sudo docker swarm join --token SWMTKN-1-5rdzpysg5cnhnagcfzyyfwdbt4vdevj8wxnjbkekd1qye5yaq8-4hvslo8g1wulrkp0cq5qmm7nb 192.168.1.48:2377 (проделать команду 2 раза на других виртуальных машиных )

sudo docker node promote haews66rdvbmt2gjhksx2yih

sudo docker node promote thghjh0vbvuyiuk78koikhg6u

sudo docker node update --lable-add evn=dev qwh65t59v12n8c8qvh91lvcp7

sudo docker node update --lable-add evn=prod haews66rdvbmt2gjhksx2yih

sudo docker node update --lable-add evn=lab thghjh0vbvuyiuk78koikhg6u

sudo docker start deploy --compose-file docker-compose.yml