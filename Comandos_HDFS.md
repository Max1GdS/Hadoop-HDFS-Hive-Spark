<h1>Comandos HDFS</h1>

1.	Sirve para ingresar como usuario root<br>
Sudo su
3.	Sirve para levantar los servicios de Docker<br>
docker compose up -d
4.	Acceder al contenedor NameNode(diferente al sistema de archivo local)<br>
docker exec -it namenode bash
5.	Sirve para crear archivos<br>
Touch text1.txt
6.	Listar contenido del almacenamiento HDFS(archivos y carpetas)<br>
hdfs dfs -ls /
7.	Crear Directorio en HDFS<br>
hdfs dfs -mkdir /user/hdfs
8.	Copia un archivo desde el sistema local a HDFS<br>
hdfs dfs -put 1.txt  /user/
9.	Copia un archivo desde HDFS al sistema local<br>
hdfs dfs -get  /user/1.txt
10.	Eliminar archive/carpeta de HDFS<br>
hdfs dfs -rm /user/hdfs/file
hdfs dfs -rm -r /user/hdfs/nombreCarpeta
11.	Ver contenido de un archivo HDFS<br>
hdfs dfs -cat /user/hdfs/file
12.	Mover archivos entre carpetas HDFS<br>
hdfs dfs -mv /user/hdfs/oldfile /user/hdfs/newfile
13.	Cambiar permisos de un archivo o directorio en HDFS<br>
hdfs dfs -chmod 755 /user/hdfs/file
14.	Ver el uso del disco en HDFS de forma legible<br>
hdfs dfs -du -h /user/hdfs/
15.	Ver el estado de capacidad de HDFS<br>
hdfs dfsadmin -report 
