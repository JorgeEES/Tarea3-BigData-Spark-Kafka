# Tarea 3: Procesamiento de datos con Apache Spark y Kafka

## 1. Descripción del proyecto

Este proyecto se desarrolla como parte de la actividad académica del curso de Big Data de la Universidad Nacional Abierta y a Distancia (UNAD). Su objetivo es aplicar herramientas de procesamiento distribuido mediante Apache Spark, utilizando un conjunto de datos históricos de la Tasa Representativa del Mercado (TRM) para el procesamiento batch y datos simulados de sensores para el procesamiento en tiempo real con Apache Kafka y Spark Structured Streaming.

## 2. Tecnologías utilizadas

- **Python:** lenguaje utilizado para desarrollar los scripts.
- **Apache Spark y PySpark:** procesamiento distribuido y análisis de datos.
- **Hadoop HDFS:** almacenamiento del archivo CSV utilizado en el procesamiento batch.
- **Apache Kafka:** publicación y distribución de eventos de sensores.
- **Spark Structured Streaming:** consumo y análisis de datos en tiempo real.
- **Ubuntu Server:** entorno de ejecución de las herramientas.

## 3. Archivos del repositorio

| Archivo | Descripción |
|---|---|
| `tarea3.py` | Lee los datos de la TRM desde HDFS, muestra el esquema y las primeras filas, calcula estadísticas descriptivas, filtra valores superiores a 5.000 COP y ordena los registros de mayor a menor. |
| `kafka_producer.py` | Genera datos simulados de sensores con identificador, temperatura, humedad y marca de tiempo, y los publica en el topic `sensor_data`. |
| `spark_streaming_consumer.py` | Consume eventos del topic `sensor_data` y calcula promedios de temperatura y humedad por sensor en ventanas de un minuto. |

## 4. Resultados obtenidos

En el procesamiento batch se obtuvieron estadísticas descriptivas del conjunto de datos de la TRM y se identificaron registros con valores superiores a 5.000 COP. También se ordenaron los valores de forma descendente para facilitar su consulta.

En el procesamiento en tiempo real se verificó la creación del topic `sensor_data`, el envío continuo de registros por medio del productor y el procesamiento de los eventos con Spark Structured Streaming. Los resultados mostraron promedios de temperatura y humedad agrupados por sensor y por ventana de tiempo.

## 5. Ejecución

Los scripts se ejecutaron en un entorno Ubuntu con las herramientas y dependencias correspondientes previamente instaladas y configuradas.

Para el procesamiento batch, el archivo `rows.csv` debe estar disponible en la ruta HDFS configurada en `tarea3.py`.

Para el procesamiento en tiempo real, ZooKeeper y el broker de Kafka deben estar activos, el topic `sensor_data` debe existir y Spark debe disponer del conector Kafka compatible con la versión instalada.

## 6. Evidencias

Las evidencias de ejecución, los resultados del procesamiento batch y las salidas de Spark Structured Streaming se documentan en el informe académico de la actividad.
