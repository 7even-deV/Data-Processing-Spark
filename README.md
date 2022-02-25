# Data Processing

Este es el repositorio del proyecto del BootCamp Big Data Processing de KeepCoding.

El proyecto consiste en crear una arquitectura lambda para el procesamiento de datos recogidos de una antena de telefonía móvil.

El procesamiento se realizará con 2 fuentes de datos:

● Datos en Streaming, de los dispositivos móviles enviados desde un Docker previamente levantado en una máquina virtual (VM) de Google Cloud, que llegan a un sistema de mensajes de Apache Kafka también previamente levantado en la misma VM, con el Topic de Kafka ​(devices)​.

● Base de datos, de los registros de usuarios de la telefonía móvil, con la tabla (user_metadata), alojada en un PostgreSQL previamente creado en Google Cloud.

El código está estructurado en 3 partes (carpetas/archivos) diferenciadas:

1. provisioner/JdbcProvisioner: Realizar la carga de las tablas y de los metadatos necesarios en el PostgreSQL de Google Cloud.

2. streaming/StreamingJob: ​Recolectar las métricas de las antenas de telefonía móvil y agregarlas cada 5 minutos (total de bytes recibidos por antena, transmitidos por ID/APP) y guardar los resultados en en el PostgreSQL de Google Cloud.

3. batch/BatchJob: ​Calcular analíticas sobre los datos recolectados del StreamingJob y almacenarlas en el PostgreSQL de Google Cloud.
