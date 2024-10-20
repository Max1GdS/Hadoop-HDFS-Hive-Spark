<h1>Comandos Hive</h1> 
<p>Hive permite la creación, manipulación y consulta de bases de datos y tablas utilizando un lenguaje SQL simplificado, adaptado para entornos distribuidos como Hadoop.</p>

<h3>Comandos básicos</h3>
<ul> 
  <li><strong>Acceder al contenedor de Hive:</strong> 
    <ul> 
      <li>Ingresar al servidor de Hive mediante Docker <br> 
        <code>sudo docker exec -it hive-server bash</code></li> 
      <li>Acceder a la carpeta de Hive <br> 
        <code>cd /opt/hive/bin</code></li> 
      <li>Iniciar el shell de Hive <br> 
        <code>./hive</code></li> 
    </ul> 
  </li> 
</ul>

<h3>Comandos Hive SQL</h3> 
<ul> 
  <li>Crear una base de datos: <br> 
    <code>CREATE DATABASE mi_base_datos;</code> 
  </li> 
  <li>Usar una base de datos existente: <br> 
    <code>USE mi_base_datos;</code> 
  </li> 
  <li>Activar configuraciones de concurrencia y particionamiento: <br> 
    <code>SET hive.support.concurrency=true;</code><br> 
    <code>SET hive.txn.manager=org.apache.hadoop.hive.ql.lockmgr.DbTxnManager;</code><br> 
    <code>SET hive.enforce.bucketing=true;</code><br> 
    <code>SET hive.exec.dynamic.partition.mode=nonstrict;</code>
  </li> 
</ul>

<h3>Operaciones con tablas</h3> 
<ul> 
  <li>Crear una tabla simple: <br> 
    <code>CREATE TABLE mi_tabla ( id INT, nombre STRING, edad INT ) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',';</code> 
  </li> 
  <li>Insertar datos en la tabla: <br> 
    <code>INSERT INTO mi_tabla VALUES (1,'Juan',30);</code> 
  </li> 
  <li>Seleccionar todos los datos de la tabla: <br> 
    <code>SELECT * FROM mi_tabla;</code> 
  </li> 
</ul>

<h3>Tabla de estudiantes</h3> 
<ul> 
  <li>Crear una tabla para almacenar datos de estudiantes: <br> 
    <code>CREATE TABLE estudiantes ( id INT, nombre STRING, edad INT ) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',';</code> 
  </li> 
  <li>Insertar registros en la tabla de estudiantes: <br> 
    <code>INSERT INTO estudiantes VALUES (1, 'Carlos', 25);</code> 
  </li> 
  <li>Consultar estudiantes con una edad mayor a 20: <br> 
    <code>SELECT * FROM estudiantes WHERE edad > 20;</code> 
  </li> 
  <li>Actualizar la edad de un estudiante: <br> 
    <code>UPDATE estudiantes SET edad = 26 WHERE nombre = 'Carlos';</code> 
  </li> 
  <li>Crear una tabla de estudiantes con particionamiento en buckets: <br> 
    <code>CREATE TABLE estudiantes ( id INT, nombre STRING, edad INT ) CLUSTERED BY (id) INTO 3 BUCKETS STORED AS ORC TBLPROPERTIES ('transactional'='true');</code> 
  </li> 
  <li>Eliminar un registro de la tabla de estudiantes: <br> 
    <code>DELETE FROM estudiantes WHERE id = 1;</code> 
  </li> 
</ul>
