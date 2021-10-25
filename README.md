# How to run
- `./start.sh`
- `/usr/bin/zookeeper-server-start config/zookeeper.properties`
- `/usr/bin/kafka-server-start config/server.properties`
- `python kafka_server.py`

## Start Kafka Consumer
- `kafka-console-consumer --topic "com.udacity.calls.v1" --from-beginning --bootstrap-server localhost:9092`

## Run Spark
- `spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.4 --master local[*] data_stream.py`

## Question1: How did changing values on the SparkSession property parameters affect the throughput and latency of the data?
- spark.executor.memory : setting executor memory 
- spark.executor.cores : setting executor cores 
- spark.driver.memory : setting driver memory 
- numInputRecords : The number of records processed in a trigger 
- inputRowsPerSecond : The rate of data arriving processedRowsPerSecond : The rate at which Spark is processing data

## Question2: What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?

Set spark.driver.memory and spark.executor.memory to "2g" or 2 gigabytes improved processing speed.