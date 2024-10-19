# Hadoop-HDFS-Hive-Spark
<h2 align="center">Historia de Hadoop (2006)</h2>
<p>Hadoop fue creado en 2006 por Doug Cutting, inspirado en un elefante de peluche que su hija tenía. Hadoop es una plataforma de software que soporta la computación distribuida a gran escala, diseñada para manejar grandes volúmenes de datos de manera eficiente. Apache Software Foundation es la organización que lo respalda, junto con muchos otros proyectos como SugarCRM y OSCommerce.</p>
<h3>Componentes de Hadoop:</h3>

<ul>•	HDFS (Hadoop Distributed File System): Sistema de archivos distribuido que permite el almacenamiento escalable y confiable de grandes volúmenes de datos.</ul>
<ul>•	YARN (Yet Another Resource Negotiator): Sistema que gestiona los recursos en clústeres y asigna tareas a través de diferentes nodos.</ul>
<ul>•	MapReduce: Modelo de programación y procesamiento para manejar grandes cantidades de datos de manera distribuida, basado en un algoritmo de clave-valor.</ul>

<h3>Herramientas para manejo de datos:</h3>

<ul>•	Flume: Ingresa datos no estructurados o semiestructurados a Hadoop.</ul>
<ul>•	Sqoop: Transfiere datos estructurados entre bases de datos y Hadoop.</ul>
<ul>•	Kafka & Storm: Herramientas para procesamiento en tiempo real y streaming de datos.</ul>
<ul>•	HBase: Base de datos NoSQL para el almacenamiento de grandes volúmenes de datos no estructurados.</ul>

<h3>Procesamiento de datos</h3>

<ul>•	Spark: Motor de procesamiento de datos en memoria que admite múltiples lenguajes como Scala, R, Python y Java. Ideal para grandes volúmenes de datos y análisis en tiempo real.</ul>
<ul>•	Solr & Lucene: Tecnologías para búsqueda e indexación de grandes cantidades de datos.</ul>
<ul>•	Hive y Drill: Hive es un sistema de gestión de datos para trabajar con datos estructurados en Hadoop utilizando HQL (Hive Query Language). Drill permite realizar consultas distribuidas y rápidas sobre grandes volúmenes de datos.</ul>
<ul>•	Pig: Lenguaje de alto nivel para la creación de flujos de datos y procesamiento de grandes conjuntos de datos en Hadoop.</ul>
<ul>•	Oozie: Sistema de planificación de flujos de trabajo que permite programar y ejecutar tareas en Hadoop de manera similar a los crons en Linux.</ul>
<ul>•	Zookeeper & Ambari: Herramientas para la gestión y coordinación de clústeres de Hadoop.</ul>

<h3>Técnicas avanzadas</h3>

<ul>•	Minería de datos: Proceso de analizar grandes volúmenes de datos para descubrir patrones y relaciones ocultas.</ul>
<ul>•	Machine Learning: Técnica de aprendizaje automático que permite construir modelos predictivos basados en grandes conjuntos de datos.</ul>
<ul>•	Big Data: Referencia al conjunto de tecnologías y métodos que permiten almacenar, procesar y analizar grandes volúmenes de datos. El Big Data combina minería de datos y machine learning para obtener información útil y accionable.</ul>
<h3>Cloud y Big Data</h3>
<ul>•	Cloud Storage: Servicio de almacenamiento en la nube que permite gestionar y almacenar grandes cantidades de datos de manera eficiente.</ul>
<ul>•	Cloud Pub/Sub: Servicio de mensajería asíncrona en tiempo real para la comunicación entre aplicaciones.</ul>
<ul>•	GSP Big Data: Google Skill Boost ofrece formación en herramientas y conceptos de Big Data a través de la plataforma de Google Cloud (ver video en Google Cloud sobre este tema).</ul>
<ul>•	Dataproc: Servicio para ejecutar clústeres de Hadoop y Spark, facilitando el procesamiento de big data.</ul>
<ul>•	Dataprep: Herramienta visual para limpiar y preparar datos sin escribir código, lista para análisis.</ul>
<ul>•	Dataflow: Procesamiento de datos en tiempo real para ETL y análisis, basado en Apache Beam.</ul>
<ul>•	Bigquery: Data warehouse escalable para análisis de grandes volúmenes de datos mediante SQL.</ul>

<p>HDFS( (Hadoop Distributed File System), es un sistema de archivos distribuido diseñado para almacenar y gestionar grandes volúmenes de datos en entornos de clústeres de computadoras, es software de código abierto, desarrollado por Apache</p>

ip de uso 172.31
<h3>Comandos HDFS</h3>

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
