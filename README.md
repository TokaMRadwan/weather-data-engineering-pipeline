# Real-Time Weather Data Engineering Pipeline

**NTI Big Data Training Project**

## Project Overview
Developed a real-time weather data pipeline to collect, ingest, store, process, and visualize weather information for seven Egyptian cities.

The project demonstrates practical experience with streaming data ingestion, distributed storage, real-time analytics, and data visualization.

## Technologies Used
- **Programming:** Python
- **Data Source:** WeatherAPI
- **Data Ingestion:** Apache Flume
- **Message Streaming:** Apache Kafka
- **Distributed Storage:** Hadoop HDFS
- **Stream Processing:** PySpark Structured Streaming
- **Time-Series Database:** InfluxDB
- **Visualization:** Grafana

## Data Pipeline Architecture

**WeatherAPI → Python Producer → Local JSON File → Apache Flume → Apache Kafka**

The data is then processed through two parallel pipelines:

1. **Storage Pipeline:** Kafka → Apache Flume → HDFS
2. **Analytics Pipeline:** Kafka → PySpark Structured Streaming → InfluxDB → Grafana

## Key Features

- Collects weather data from seven Egyptian cities through WeatherAPI.
- Ingests JSON weather records into Apache Kafka using Apache Flume.
- Stores raw streaming data in HDFS.
- Processes streaming data using PySpark.
- Calculates average, maximum, and minimum temperatures, average humidity, and average wind speed by city.
- Stores aggregated weather metrics in InfluxDB.
- Visualizes weather information using Grafana dashboards.

## Project Files

| File | Description |
|---|---|
| `producer.py` | Collects weather data from WeatherAPI |
| `weather.conf` | Flume configuration for sending records to Kafka |
| `kafka-to-hdfs.conf` | Flume configuration for storing Kafka data in HDFS |
| `spark_weather.py` | Spark streaming processing and InfluxDB integration |

## Dashboard Visualizations

The project includes Grafana screenshots showing:

- Current Temperature by City
- Temperature Trend by City

## Development Environment

Developed during the National Telecommunication Institute (NTI) Big Data training program in a Linux-based environment using locally configured Big Data services.

Running the project requires configuring Kafka, Flume, HDFS, Spark, InfluxDB, and Grafana.

The Python producer also requires a `WEATHER_API_KEY` environment variable containing a valid WeatherAPI key.

## Project Purpose

To gain hands-on experience building an end-to-end data engineering pipeline that integrates data ingestion, distributed storage, stream processing, time-series analytics, and visualization.
