# Tarea2SXE
Contenedores con Docker.

## Pásos seguidos durante el proceso:

>1:Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo

Para poder instalar alpine es necesário que docker este instalado, una vez lo tengamos 
ejecutarémos el comando:-`sudo docker pull alpine` para instalarlo.

>2:Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre

Para crear un contenedor sin nómbre introducímos el siguiente comando:
-`sudo docker container create -i -t alpine`

Comprobamos que no está ejecutándose con el comando:
-`docker ps`
Y obtenemos el nombre con el comando:
-`docker ps -a`
vemos que tiene un nombre generado aleatóriamente

>3:Crea un contenedor con el nombre 'dam_alp1'. ¿Como puedes acceder a él?

La sintáxis para crear el contenedor dam_alp1 es prácticamente igual,la diferencia es
que especificámos el parámetro **--name**

-`sudo docker container create -i -t --name dam_alp1 alpine`

Para poder iniciarlo y acceder directamente a el utilizarémos el siguiente comando:
-`start --attach -i dam_alp1`
con **--attack** accedemos directamente


>4:Comprueba que ip tiene y si puedes hacer un ping a google.com

Comprobamos la ip con el comando:-`ip a`,comprobando que en este caso es la 
**172.17.0.2** 

Realizamos un ping a Google con el comando:-`ping www.google.com`
y comprobamos que envía y recibe los paquetes de datos, demostrando que 
si puede hacer ping

>5:Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?

Creamos el contenedor con el comando anteriormente mencionado:
-`sudo docker container create -i -t --name dam_alp2 alpine`

y con el comando:-`start --attach -i dam_alp2` lo iniciámos.

Finálmente con:-`ping 172.17.0.2` hacemos ping a dam_alp1, confirmando que si es posible

>6:Sal del terminal, ¿que ocurrió con el contenedor?

Al salir de la terminal con -`shift d` se apaga el contenedor

>7:¿Cuanta memoria en el disco duro ocupaste?

Para comprobar la cantidad de memória usada por ambos contenedores utilizamos el comando -`sudo docker system df -v`
viendo que dam_alp1 ocupa 21B y dam_alp2 ocupa 40B

>7:¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?

Para saberlo debémos abrir otra terminál y arrancar uno de los contenedóres, para posteriorménte 
utilizar el comando:-`sudo docker stats` y ver las estdísticas de este
