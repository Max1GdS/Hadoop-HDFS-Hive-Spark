<h1>Comandos Spark</h1> <p>Spark admite múltiples lenguajes como Scala, PySpark, SparkR, Java y SQL para procesamiento en memoria y en distribuciones como HDFS y Hive.</p> 
<h3>Características</h3> <ul> <li><strong>Procesar:</strong> <ul> <li>Distribución HDFS, Hive</li> <li>En memoria</li> </ul> </li> 
  <li><strong>RDD o DataFrame:</strong> Estructuras inmutables, es decir, no se modifican en el tiempo. <ul> 
    <li>Pueden almacenar datos tabulares o no estructurados.</li> </ul> </li> </ul> <h3>Comandos Spark Scala</h3> <ul> 
      <li>Sirve para ingresar como usuario root <br>Sudo su</li> <li>Sirve para levantar los servicios de Docker <br>docker compose up -d</li>
      <li>Acceder a los servicios Spark en el contenedor <br>docker exec -it spark-master bash</li> <li>
        Cambiar el directorio a la carpeta de Spark <br>cd /spark/bin</li> <li>Iniciar Spark Shell en SCALA o PYTHON <br>./spark-shell (Scala) 
          <br>./pyspark (Python)</li> </ul> <h3>Transferencia de archivos CSV</h3> <ul> <li> Cargar archivo MOCK_DATA.csv desde la máquina local<br>
            C:\Users\sistemas\Downloads\MOCK_DATA.csv</li> <li> Subir archivo CSV al servidor remoto mediante SCP
              <br> scp MOCK_DATA.csv usuario@dirección's password:/home/ubuntu/Hadoop</li> <li> Copiar archivo desde la máquina local al contenedor Docker de Hadoop<br> 
                docker cp /home/ubuntu/Hadoop/datos.csv namenode:/tmp/</li>
          </ul> <h3>Ejercicios en Spark</h3> <h4>Ejercicio 1</h4> <p>Filtrar números pares de una lista:</p> <pre>val data = sc.parallelize(List(1, 2, 3, 4, 5, 6)) val evenNumbers = data.filter(x => x % 2 == 0) evenNumbers.collect() 
          </pre><h4>Ejercicio 2</h4> <p>Suma de una lista de números:</p> <pre>val data = sc.parallelize(List(1, 2, 3, 4, 5)) val sum = data.reduce((a, b) => a + b) println(sum) </pre> <h4>Ejercicio 3</h4> 
          <p>Reducir datos por clave (key) y sumar valores:</p> <pre>val data = sc.parallelize(List(("a", 1), ("b", 1), ("a", 2), ("b", 2))) val result = data.reduceByKey((x, y) => x + y) result.collect() 
          </pre><h4>Ejercicio 4</h4> <p>Convertir una lista a un DataFrame:</p> <pre>val data = sc.parallelize(List(("Alice", 20), ("Bob", 25))) val df = data.toDF("name", "age") df.show() </pre> <h4>Ejercicio 5</h4> 
          <p>Cargar un archivo CSV desde HDFS:</p> 
          <pre>val df = spark.read.option("header", "true").csv("hdfs://path/to/datos.csv") val df = spark.read.option("header", "true").csv("hdfs://datos.csv")
docker cp /ruta/local/del/archivo.csv namenode:/ruta/contenedor/ hdfs dfs -put datos.csv /
val df = spark.read.option("header", "true").csv("hdfs://namenode:8020/datos.csv") df.show() </pre>
