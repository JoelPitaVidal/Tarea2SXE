# Tarea2SXE
Contenedores con Docker.

##Pásos seguidos durante el proceso:

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
