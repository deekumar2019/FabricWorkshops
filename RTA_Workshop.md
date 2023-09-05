Hands-on-Lab

` `**Real-time Analytics** 

![](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.001.png)



Contents

1. Introduction  
1. Real-time Analytics  
1. Scenario
1. Prerequisites
1. Module 1: Create a Fabric workspace
1. ` `Module 2: Build your first Real-time Analytics solution in Fabric 
1) Create a KQL Database 
1) Create an Eventstream 
1) Stream data from Eventstream to KQL Database
1) Explore data and build Power BI report 
1. Module 3: Extending the real-time analytics solution
1) Get dimension data from Blob Storage 
1) Query data 
1) Explore data further in the KQL Queryset 
1) Build Power BI report 
1) Create OneLake shortcut
1. Module 4: Event hub to RTA



**Introduction:**

What is Microsoft Fabric?

Microsoft Fabric is an all-in-one analytics solution for enterprises that covers everything from data movement to data science, Real-Time Analytics, and business intelligence. It offers a comprehensive range of services, including data lake, data engineering, and data integration, all in one place. ![A screenshot of a blue screen

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.002.png)

Fabric brings together experiences such as Data Engineering, Data Factory, Data Science, Data Warehouse, Real-Time Analytics, and Power BI onto a shared SaaS foundation. This integration provides the following advantages:

- An extensive range of deeply integrated analytics in the industry.
- Shared experiences across experiences that are familiar and easy to learn.
- Developers can easily access and reuse all assets.
- A unified data lake that allows you to retain the data where it is while using your preferred analytics tools.
- Centralized administration and governance across all experiences.

With the Microsoft Fabric SaaS experience, all the data and the services are seamlessly integrated. IT teams can centrally configure core enterprise capabilities and permissions are automatically applied across all the underlying services. Additionally, data sensitivity labels are inherited automatically across the items in the suite.

**

**Real Time Analytics:**

Real-Time Analytics is a fully managed big data analytics platform optimized for streaming, and time-series data. It utilizes a query language and engine with exceptional performance for searching structured, semi-structured, and unstructured data. Real-Time Analytics is fully integrated with the entire suite of Fabric products, for both data loading, data transformation, and advanced visualization scenarios.


**What makes Real-Time Analytics unique?**

- **Capture, transform, and route** real-time events to various destinations, including custom apps.
- **Easily ingest or load** data from any source, in any data format.
- Run analytical queries **directly on raw data** without the need to build complex data models or create scripting to transform the data.
- Import data with **by-default streaming** that provides high performance, low latency, high freshness data analysis.
- Imported data undergoes **default partitioning** - both time and hash-based partitioning, and by-default **indexing**.
- Work with **versatile data structures** including query structured, semi-structured, or free text.
- **Query** raw data without transformation, with high performance, incredibly low response time, while using a wide variety of available [operators](https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/index?context=/fabric/context/context).
- **Scale to an unlimited** amount of data, from gigabytes to petabytes, with unlimited scale on concurrent queries and concurrent users.
- **Integrate** seamlessly with other experiences and items in Microsoft Fabric.

The main items available in Real-Time Analytics include:

1) [**Eventstream**](https://learn.microsoft.com/en-us/fabric/real-time-analytics/event-streams/overview) for capturing, transforming, and routing real-time events to various destinations with a no-code experience.
1) A [**KQL database**](https://learn.microsoft.com/en-us/fabric/real-time-analytics/create-database) for data storage and management. Data loaded into a KQL database can be accessed in OneLake and is exposed to other Fabric experiences.
1) A [**KQL queryset**](https://learn.microsoft.com/en-us/fabric/real-time-analytics/kusto-query-set) to run queries, view, and customize query results on data. The KQL queryset allows you to save queries for future use, export and share queries with others, and includes the option to generate a Power BI report.


**Real-time Analytics integration with other experiences:**

![](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.003.png)



**Scenario:**

You can use Real-time Analytics for a range of solutions, such as IoT analytics and log analytics, and in several scenarios including manufacturing operations, oil and gas, automotive, and more. 

In this tutorial, you will learn how to work with a Stockprice dataset. Here are the various steps you’ll perform as part of the tutorial: 

Module 1: Create a Power BI Workspace

Module 2: Create a history load of StockPrice data into KQL database using EventStream

Module 3: Ingest data from Event hub into Lakehouse and KQL table using Eventstream

**

**Prerequisites** 

- Power BI Premium License
- Fabric Capacity (Free F64 Fabric capacity available during the Fabric Preview period ending 9/30/2023)



**

**Module 1: Create a Fabric Workspace:**

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.004.png)

**Fill out the Create Workspace as follows:**

- Workspace Name: RTA\_Workshop
- Description: This workspace is created to work on RTA capabilities in Fabric.
- Expand Advance settings
- License Mode: Trial (Provided Fabric Trial is enabled)
- Leave all the other settings to default.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.005.png)

- Select Apply.
- A new workspace will be created and opened.
**


**Module 2: Build your first Real-time Analytics solution in Fabric.**

- **Create a KQL Database** 
  - Click on New and you will see a drop down with multiple options. Select **KQL Database (Preview)**

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.006.png)

- On the New KQL Database dialog, enter a unique name: StockPrices
- Enable availability of data in Onelake by clicking on the pencil (Highlighted below) ![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.007.png)
- ` `**Create an Event stream:** The event streams feature in Microsoft Fabric gives you a centralized place in the Fabric platform to capture, transform, and route real-time events to various destinations with no-code experience. 
- Return to the Real-Time Analytics home page. The **Home** icon directs you to the home page of the experience you're currently using.

![](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.008.png)

- **Select** *Event Stream Preview*

![A screenshot of a web page

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.009.png)

- Enter EventStreamStockPrices as the eventstream name and select **Create** 
- When provisioning is complete, the Eventstream landing page is shown.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.010.png)

- **Stream data from Eventstream to your KQL database**
- In the Eventstream authoring area, select **New source** > **Sample data**.
- Enter **StockPricedata** as the Source Name, and then select **Stock Market** from the dropdown of **Sample data**.
- Select **Add**.
- In the Eventstream authoring area, select **New destination** > **KQL Database**.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.011.png)

- In the **KQL Database** pane, fill out the fields as follows:

|**Field**|**Suggested value**|
| :- | :- |
|**Destination name**|*StockPricesdatabase*|
|**Workspace**|The workspace in which you [created a database](https://learn.microsoft.com/en-us/fabric/real-time-analytics/tutorial-1-resources#create-a-kql-database).|
|**KQL Database**|<p>*StockPrices*</p><p></p>|
![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.012.png)

- Select **Add and configure.**

A data ingestion pane opens with the **Destination** tab selected.

- **Configure data loading to the KQL database**
- Select **New table**, and enter *StockPrices* as the table name.
- Select **Next: Source** to open the **Source tab**.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.013.png)

- Review the default values. The data connection name is made from the database name and the eventstream name.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.014.png)

- Select **Next: Schema** to open the **Schema** tab.

**Schema mapping**

- The incoming data source is uncompressed, so keep the **Compression type** as *uncompressed*.
- From the **Data format** dropdown, select **JSON**.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.015.png)

- Select **Next:Summary** :In the **Continuous ingestion from Eventstream established** window, all steps are marked with green check marks when the data connection is successfully created. **The data from Eventstream begins streaming automatically into your table.**

**Load File from One Lake in KQL database:**

**If you have an existing Lakehouse, use that lakehouse and if not use the steps listed in 1) to create one.**

- **Create a Lakehouse:**
  - In the [Power BI service](https://powerbi.com/), select **Workspaces** from the left-hand menu.
  - To open your workspace, enter its **RTA\_Workshop** in the search textbox located at the top and select it from the search results.
  - From the experience switcher located at the bottom left, select **Data Engineering**

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.016.png)

- In the **Data Engineering** tab, select **Lakehouse** to create a lakehouse.
- In the **New lakehouse** dialog box, enter **RTA\_Lakehouse** in the **Name** field.
- Select **Create** to create and open the new lakehouse.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.017.png)

- **Upload a file to Lakehouse:**
  - Download the File Stocktickers.txt to your local machine.
  - Once you have opened the Lakehouse, right click on Files and you’ll see several options, pick the **Upload Files** option: ![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.018.png)

- Upload the File from your local machine.
- Copy the Url of the loaded file: 
- Click on the 3 dots … next to Stockprices.txt

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.019.png)

- Copy the One Lake URL

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.020.png)

- Go to KQL database: StockPrices
  1. Right Click on Database Name: StockPrices
  1. You should see this will show option to Get Data – Click on **OneLake**

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.021.png)

- A new Window pops up, click on new table and call it **StockTicker**

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.022.png)

- Click on **Next Source**
- Copy the **Onelake URI in the box highlighted:**

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.023.png)

- Click Next Schema. Choose the Data Format=**PSV**

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.024.png)

- Click **Next: Summary** and the data will get loaded into the Stockticker table



# **Explore your data with KQL and SQL**
- Go to your KQL database: **Stockprices**
- To Query a table, right click on the table, you’ll see a lot of options to query your table:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.025.png)

- Click on the first option: **Show any 100 records.**
- A new window will pop-up with the Query and the results displayed under the Query:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.026.png)

- Similarly, you can try other sample queries from the options showing up to Query table in step b) above
- Once you are satisfied with the queries, you can save your queries by clicking on: **Save as KQL queryset:** ![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.027.png)

**Build a Power BI report** 

- Copy and paste the following query into your KQL queryset. The output of this query is used as the dataset for building the Power BI report.

StockPrices

| summarize Count=count(sector) by symbol

| sort by Count

- Click on Build Power BI report: You will land into a Power BI application with the Query showing up on the right side:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.028.png)

- Click on the Data Tab and move the symbol to x-axis and the Count variable to y-axis as below:

![](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.029.png)

- Click on File and save the** report giving it a name**: PowerBI-RTA** and the workspace name: **RTA\_Workshop**:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.030.png)



**Module 3: Ingest data from Event hub into Lakehouse and KQL table using Eventstream**

Prerequisites:

- Event hub pre-created in Azure portal with event hub data available to stream the data to Fabric.
- Pre-create an access policy to access the data in Fabric

Please follow the link below to deploy an application which will deploy both the application and the Event hub using the Azure portal: 

- Follow the steps Set a shared access policy on your event hub : Before you can create a connection to your Event Hubs data, you need to set a shared access policy (SAS) on the event hub and collect some information to be used later in setting up the connection. 

`              `In the Azure portal, browse to the event hubs instance you plan to connect.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.031.png)

- Create a new event stream in Fabric real time Analytics experience: New\_Toll\_Es

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.032.png)

- Create New Event hub source connection:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.033.png)

- If you do not have existing connection to Evenhub create a new one, capturing the following details from Event hub portal:
- Eventhub Name Space: (Event hub Name Space)
- Event hub name : (Event hub name)
- Shared Access Key Name: (Name of your policy)
- Shared Access Key: (Primary Key of your Event hub)

![](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.034.png)

- After you have created the new connection, enter the values for your cloud connection:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.035.png)

- Enter your consumer group from Eventhub where you will be reading the data from.
- Select a Data format for your event hub data: This can be Json, Avro or CSV data formats
- Enter Add to add all the details to the source of the Event stream.

Enter the destination details:

Destination: Lakehouse:

- Click on + on the right side of Eventream box to enter your destination:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.036.png)

- If you chose the lakehouse, please enter all the Lakehouse details in the popped up window:

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.037.png)

- Once you save the settings, the data should be flowing into your Lakehouse

Destination: KQL Table:

- If you would like the data to be steaming into KQL database, you can pick KQL database as the destination by entering all the details in the pop-up window.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.038.png)

- Once both the destination options have configured, you have now set up your Fabric to get real time data from Event hub.




- Log into Fabric “Real-Time Analytics” experience and log into your KQL database: StockPrice

![A close-up of a white background

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.039.png) 

- Click on Get Data and then Pick Event hubs from the drop-down menu.

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.040.png)

- A new window pops up: ![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.041.png)
- Select Next: Source and enter all the details we captured in step 2)

![A screenshot of a computer

Description automatically generated](Aspose.Words.7da1746c-ecaf-4916-9e4f-5cfefac41f0b.042.png)

- Select Save. A new cloud  data connection between Fabric and Event Hubs is created.




