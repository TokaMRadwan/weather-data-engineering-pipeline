# Real-Time Weather Data Engineering Pipeline

**NTI Big Data Training Project**

**Technologies:** Python, WeatherAPI, Apache Kafka, Apache Flume, HDFS, PySpark Structured Streaming, InfluxDB, Grafana

## Project Overview

Developed a real-time weather data engineering pipeline during my NTI Big Data training. The project collects weather observations for seven Egyptian cities from a weather API, processes streaming data using Apache Spark, stores raw events in HDFS, and visualizes weather insights through Grafana dashboards.

## Data Pipeline Architecture

**WeatherAPI → Python Producer → Apache Flume → Kafka**

From Kafka, data flows through two parallel paths:

- **Storage:** Kafka → Apache Flume → HDFS
- **Analytics:** Kafka → PySpark Structured Streaming → InfluxDB → Grafana

## Project Components

- **Python Producer (`producer.py`):** Fetches weather observations and writes JSON records to a local file.
- **Apache Flume (`weather.conf`):** Reads the generated records and publishes them to Kafka.
- **Apache Kafka:** Manages the weather event stream through `weather_topic`.
- **HDFS (`kafka-to-hdfs.conf`):** Stores raw weather records for distributed storage.
- **PySpark (`spark_weather.py`):** Processes streaming weather data and calculates temperature, humidity, and wind-speed statistics for each city.
- **InfluxDB:** Stores aggregated weather metrics for time-series analysis.
- **Grafana:** Displays temperature comparisons and trends across Egyptian cities.

## Dashboard Results

The project includes two Grafana visualizations:

- **Current Temperature by City:** Comparison of temperature measurements across seven cities.
- **Temperature Trend by City:** Visualization of temperature changes over time.

## Project Environment

The project was developed in a Linux-based Big Data training environment using locally configured services. Running it elsewhere requires the relevant Kafka, Flume, Hadoop, Spark, InfluxDB, and Grafana infrastructure.

**Security note:** The original producer contained a hard-coded API key, which should be revoked and replaced with secure configuration before the project is shared or reused.

## Project Background

Developed as part of the National Telecommunication Institute (NTI) Big Data training program to gain hands-on experience with streaming ingestion, distributed storage, real-time data processing, and visualization.
