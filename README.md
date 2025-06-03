# Real-Time Weather Monitoring Pipeline using Microsoft Fabric

A real-time data solution for weather monitoring and alerting using Microsoft Fabric's unified platform—integrating Eventstream, KQL Database, Notebooks, Power BI, and Data Activator.

## Business Case :

Timely and accurate weather data is essential for industries like agriculture, logistics, disaster response, and aviation. These sectors rely heavily on real-time information to make decisions that minimize risk and maximize efficiency. Traditional weather systems often involve delays or lack seamless automation. This project addresses that gap by delivering a fully automated real-time pipeline that not only ingests weather data but also visualizes insights and triggers alerts instantly using Microsoft Fabric's modern capabilities.

![Screenshot 2025-05-29 150734](https://github.com/user-attachments/assets/1e9392f8-b1c7-42f8-aaec-6fbd8691e26a)

## Solution Overview :

This solution creates a robust, modular, and scalable pipeline that ingests weather data from a public API, processes it using Eventstream, stores it in a KQL Database, and then surfaces the information in Power BI dashboards. Additionally, it enables Data Activator to automatically trigger alerts to Microsoft Teams based on weather conditions. The key components of this pipeline include:

* **Eventstream & Custom Endpoints** for real-time ingestion

* **KQL Database** for structured querying and analytics.

* **Fabric Notebooks** for automation and API integration.

* **Power BI** for interactive dashboards with DirectLake.

* **Data Activator** for real-time alerts to stakeholders via Teams.


## Architecture in Action :


### API Integration :

* Connects to a weather data provider using an API key and base URL.
* Returns live weather metrics such as temperature, humidity, wind speed, etc.

### Eventstream :

* A custom point source is set up in Eventstream to receive and stream the incoming API data.
* Events are routed to a KQL Database.

### KQL Database :

* A structured table is created to store the weather metrics for querying.
* Supports high-performance, real-time querying and integration with Power BI.

### Notebook Automation :

* A Fabric notebook fetches weather data using Python.
* The data is pushed into the Eventstream custom endpoint on a scheduled basis.

### Power BI Dashboard :

* Power BI connects to the KQL Database using KQL base.
* Enables dynamic dashboards for real-time monitoring of weather patterns.

### Data Activator Integration :

* Triggers alerts when conditions such as "temperature > 40°C" or "wind speed > 100 km/h" are met.
* Sends instant notifications to Microsoft Teams to notify relevant users.

## Final Thoughts – Step-by-Step Process :

1) **Create Weather API Setup:** Register with a weather API provider, obtain the base URL and API key for accessing live weather data.

2) **Configure Custom Eventstream:** In Microsoft Fabric, set up a new Eventstream with a custom endpoint that will accept incoming weather data in JSON format.

3) **Create KQL Database and Table:** Define a KQL Database and create a table schema that matches the structure of the weather data.

4) **Automate Data Push with Notebooks:** Use a Fabric notebook written in Python to fetch weather data periodically and post it to the Eventstream endpoint.

5) **Stream Data to KQL Table:** Once the Eventstream receives the events, the data is immediately streamed into the KQL table in real time.

6) **Build Power BI Dashboard:** Connect Power BI to the KQL Database using DirectLake and build real-time visuals that reflect current weather conditions.

7) **Set Up Data Activator Rules:** Define conditions (e.g., severe weather alerts) in Data Activator and configure notifications to be sent to Microsoft Teams channels.

8) **Monitor and Act:** Stakeholders receive real-time alerts and can take proactive action based on the incoming weather insights.

This workflow demonstrates how Microsoft Fabric can manage everything from ingestion to insight—all without leaving the platform.

## Summary :

This project is a complete, real-time weather monitoring solution built entirely within the Microsoft Fabric ecosystem. It starts by fetching live weather data via an API and pushing it into an Eventstream, which is connected to a structured KQL Database for real-time storage and querying. Power BI visualizes this data instantly using DirectLake connectivity. Most importantly, when predefined weather conditions are met—such as extreme temperatures or wind speeds—Data Activator automatically triggers Microsoft Teams alerts to ensure immediate action. This solution is modular, scalable, and easily adaptable for any use case that requires real-time monitoring and alerts, including traffic, IoT devices, environmental data, or stock price surveillance.
