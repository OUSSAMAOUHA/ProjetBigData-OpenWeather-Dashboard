

# Creation of a Dashboard for real-time visualization of weather data using Kafka, Spark, Hive, Tableau, and Apache Airflow.

# *Table of Contents*
1. [Project Objective](#Project-Objective)
2. [Prerequisites for the Project - Installation and Configuration](#prerequisites-for-the-project---installation-and-configuration)
    - [Development Environment](#1-development-environment)
    - [Setting Up the Dockerized Environment](#2-setting-up-the-dockerized-environment)
    - [Tableau Installation and Configuration](#3-tableau-installation-and-configuration)
3. [Dashboard Creation for Visualization](#dashboard-creation-for-visualization)
    - [Obtaining OpenWeatherMap API Key](#1-obtaining-openweathermap-api-key)
    - [Collecting Weather Data from API to Kafka Topic](#2-collecting-weather-data-from-api-to-kafka-topic)
    - [Processing and Storing Data with Spark and Hive](#3-processing-and-storing-data-with-spark-and-hive)
    - [Visualizing Results with Tableau](#4-visualizing-results-with-tableau)
    - [Orchestration with Apache Airflow](#5-orchestration-with-apache-airflow)

# I. Project Objective

This project aims to establish an integrated system for real-time processing and visualization of weather data using various technologies. It begins with data collection from the OpenWeatherMap API. These data then transit through Kafka for real-time processing via Spark Streaming. The obtained results are stored in Hive, a dedicated data warehouse. Finally, this data is visually explored using Tableau. The entire process is deployed in a Dockerized environment, simplifying the management and deployment of the infrastructure essential to this weather data processing chain.

# II. Prerequisites for the Project - Installation and Configuration

This project requires the prior installation and configuration of several tools and environments. Follow these steps carefully to ensure a smooth project flow.

## 1. Development Environment
Operating System: Ensure you have a compatible operating system with the necessary tools (Example: Here, we use Windows).
RAM: Make sure you have a RAM memory greater than 13 GB.
Docker:
Download and install Docker following specific instructions for your operating system: Docker link
Verify the installation with the command: docker –version
Docker Compose:
Download and install Docker Compose following specific instructions for your operating system: Docker Compose link
Verify the installation with the command: docker-compose --version
## 2. Setting Up the Dockerized Environment
Creating Containers
Develop a docker-compose.yml file describing the necessary services for this application. Refer to the docker-compose.yml file in the project folder.
Running Containers
To start the containers defined in your docker-compose.yml file and run them in the background, use the following command: docker-compose up -d

Once the containers are running, you can list the running container IDs and their associated ports using the command: docker ps
To access services in a web browser, use the following URLs:

Zeppelin: http://localhost:8082
Confluent: http://localhost:9021
Spark: http://localhost:8080
Airflow: http://localhost:3000
Namenode: http://localhost:9870
Ensure that the services are correctly started and that the ports specified in your docker-compose.yml file are not used by other applications on your system.

## 3. Tableau Installation and Configuration
In this project, Tableau serves as the primary visualization tool. Ensure it is correctly installed and configured for optimal performance.
Tableau Desktop Download:
Visit the Tableau website and download the Tableau Desktop installer compatible with your operating system.
Follow the installation wizard's instructions for a successful installation.
Tableau Activation:
Upon launching Tableau Desktop, you'll be prompted to activate your license. Follow the activation process by entering the product key provided or opting for a trial version.

Connecting to Hive from Tableau:
Tableau can directly connect to Hive to visualize the data stored in Hive tables.

Selecting Hive Table or View:
Open Tableau Desktop and select "Connect" -> "Hadoop HDFS" -> "Hive Server 2".
Input the necessary connection information (Hostname, Port, Authentication) to connect to the Hive instance.
Data Connection Configuration:
Once connected to Hive, select the database containing the tables with the weather data.
Follow the steps within Tableau to configure the data connection and start visualizing the data.
# III. Dashboard Creation for Visualization
## 1. Obtaining OpenWeatherMap API Key
To collect weather data, you'll need an API key from OpenWeatherMap. Visit their website to sign up and obtain an API key.

## 2. Collecting Weather Data from API to Kafka Topic
Using Kafka, fetch data from the OpenWeatherMap API and publish it to a Kafka topic using a Kafka producer.

## 3. Processing and Storing Data with Spark and Hive
Implement Spark streaming to process the weather data fetched from the Kafka topic. Store the processed data into Hive tables.

## 4. Visualizing Results with Tableau
Connect Tableau to the Hive tables containing the processed weather data. Create visualizations (charts, graphs, etc.) based on the data attributes for effective data analysis and interpretation.

## 5. Orchestration with Apache Airflow
Use Apache Airflow for orchestrating the entire pipeline. Create Directed Acyclic Graphs (DAGs) to automate the data collection, processing, and visualization tasks.


This project integration enables the seamless flow of weather data collection, processing, storage, and visualization using Kafka, Spark, Hive, Tableau, and Apache Airflow. Adjustments and further enhancements can be made based on specific requirements or additional functionalities desired for the weather data pipeline.

This guide provides an outline and steps to execute the project; detailed configuration and implementation specifics may vary based on environment and project intricacies.

Si vous avez planifié le processus de collecte, de traitement et de stockage des données à intervalles réguliers avec Apache Airflow, vous pouvez configurer Tableau pour actualiser automatiquement les données à partir de Hive.
