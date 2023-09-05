Hands-on-Lab

` `**Real-time Analytics** 

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/0236a594-e471-4086-92bf-3f74b1d1b4c0)




Contents

1. Introduction  
1. Real-time Analytics  
1. Scenario
1. Prerequisites
1. Module 1: Create a Fabric workspace.
1. Module 2: Build your first Real-time Analytics solution in Fabric.
7. Module 3: Ingest data from Event hub into Lakehouse and KQL table using Eventstream.



**Introduction:**

What is Microsoft Fabric?

Microsoft Fabric is an all-in-one analytics solution for enterprises that covers everything from data movement to data science, Real-Time Analytics, and business intelligence. It offers a comprehensive range of services, including data lake, data engineering, and data integration, all in one place. ![A screenshot of a blue screen

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/13b7ab9e-b706-437a-8c21-f2a08b97a82f)


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

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/1d8bd59f-aab5-4381-af3e-fcacfb42606e)




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

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/2982064f-17ce-463a-b984-7e17344291da)


**Fill out the Create Workspace as follows:**

- Workspace Name: RTA\_Workshop
- Description: This workspace is created to work on RTA capabilities in Fabric.
- Expand Advance settings
- License Mode: Trial (Provided Fabric Trial is enabled)
- Leave all the other settings to default.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/53df2751-8a61-459a-9cfd-f27284f08e1c)


- Select Apply.
- A new workspace will be created and opened.
**


**Module 2: Build your first Real-time Analytics solution in Fabric.**

- **Create a KQL Database** 
  - Click on New and you will see a drop down with multiple options. Select **KQL Database (Preview)**

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/3e71282a-2e50-42e1-8b09-71a0abc6e3da)


- On the New KQL Database dialog, enter a unique name: StockPrices
- Enable availability of data in Onelake by clicking on the pencil (Highlighted below)
-
![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/b0869e10-750b-4bf0-ac06-d63f9a3dd6f6)

- ` `**Create an Event stream:** The event streams feature in Microsoft Fabric gives you a centralized place in the Fabric platform to capture, transform, and route real-time events to various destinations with no-code experience. 
- Return to the Real-Time Analytics home page. The **Home** icon directs you to the home page of the experience you're currently using.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/731fafd6-6c8e-40c6-9168-b6041cec7152)


- **Select** *Event Stream Preview*

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/ef92d877-1ef0-4b0d-9338-d8012b64dbbc)


- Enter EventStreamStockPrices as the eventstream name and select **Create** 
- When provisioning is complete, the Eventstream landing page is shown.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/88457117-66c9-42a6-b51c-d09e0cb71cce)


- **Stream data from Eventstream to your KQL database**
- In the Eventstream authoring area, select **New source** > **Sample data**.
- Enter **StockPricedata** as the Source Name, and then select **Stock Market** from the dropdown of **Sample data**.
- Select **Add**.
- In the Eventstream authoring area, select **New destination** > **KQL Database**.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/eff76d70-e915-4a29-846b-1edda1e0c66c)


- In the **KQL Database** pane, fill out the fields as follows:

|**Field**|**Suggested value**|
| :- | :- |
|**Destination name**|*StockPricesdatabase*|
|**Workspace**|The workspace in which you [created a database](https://learn.microsoft.com/en-us/fabric/real-time-analytics/tutorial-1-resources#create-a-kql-database).|
|**KQL Database**|<p>*StockPrices*</p><p></p>|

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/35b4c2af-7d00-4922-a695-e5df225f8f6e)


- Select **Add and configure.**

A data ingestion pane opens with the **Destination** tab selected.

- **Configure data loading to the KQL database**
- Select **New table**, and enter *StockPrices* as the table name.
- Select **Next: Source** to open the **Source tab**.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/a82b1703-5cde-4b63-b045-8d9a059d3478)


- Review the default values. The data connection name is made from the database name and the eventstream name.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/f47ec969-874d-46b0-86b0-f1c4d5bbc466)


- Select **Next: Schema** to open the **Schema** tab.

**Schema mapping**

- The incoming data source is uncompressed, so keep the **Compression type** as *uncompressed*.
- From the **Data format** dropdown, select **JSON**.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/8d1e51ca-5624-4706-9223-7a442464eeb1)


- Select **Next:Summary** :In the **Continuous ingestion from Eventstream established** window, all steps are marked with green check marks when the data connection is successfully created. **The data from Eventstream begins streaming automatically into your table.**

**Load File from One Lake in KQL database:**

**If you have an existing Lakehouse, use that lakehouse and if not use the steps listed in 1) to create one.**

- **Create a Lakehouse:**
  - In the [Power BI service](https://powerbi.com/), select **Workspaces** from the left-hand menu.
  - To open your workspace, enter its **RTA\_Workshop** in the search textbox located at the top and select it from the search results.
  - From the experience switcher located at the bottom left, select **Data Engineering**

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/e8148617-cce4-48c5-97bc-ae01c8b15088)


- In the **Data Engineering** tab, select **Lakehouse** to create a lakehouse.
- In the **New lakehouse** dialog box, enter **RTA\_Lakehouse** in the **Name** field.
- Select **Create** to create and open the new lakehouse.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/d1ab7acb-9509-4c5f-b644-05151b145b3e)


- **Upload a file to Lakehouse:**
  - Download the File Stocktickers.txt to your local machine.
  - Once you have opened the Lakehouse, right click on Files and you’ll see several options, pick the **Upload Files** option: ![A screenshot of a computer

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/66e455be-c677-4d75-90c8-0e7cc35b4091)


- Upload the File from your local machine.
- Copy the Url of the loaded file: 
- Click on the 3 dots … next to Stockprices.txt

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/a3ff11a4-ced7-49c2-a761-d5a0a69c8c32)


- Copy the One Lake URL

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/4f73f8c7-62cf-4d4b-bb6c-2cc7f439fa58)


- Go to KQL database: StockPrices
  1. Right Click on Database Name: StockPrices
  1. You should see this will show option to Get Data – Click on **OneLake**

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/59cb354d-5f9b-4dc8-90a4-81e17fc6bf05)


- A new Window pops up, click on new table and call it **StockTicker**

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/d4226b78-91b5-4799-bebd-5e656c5560bb)


- Click on **Next Source**
- Copy the **Onelake URI in the box highlighted:**

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/b59f9a8c-1190-4222-9bb2-7f4c42f329d3)


- Click Next Schema. Choose the Data Format=**PSV**

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/dad44e8a-8078-4c2d-a676-aa8122db2d1b)


- Click **Next: Summary** and the data will get loaded into the Stockticker table



# **Explore your data with KQL and SQL**
- Go to your KQL database: **Stockprices**
- To Query a table, right click on the table, you’ll see a lot of options to query your table:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/acc4df90-4efb-4ad9-bd1a-f4def297ad64)


- Click on the first option: **Show any 100 records.**
- A new window will pop-up with the Query and the results displayed under the Query:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/5c2330b4-37a9-49aa-ab73-57b23cf45761)


- Similarly, you can try other sample queries from the options showing up to Query table in step b) above
- Once you are satisfied with the queries, you can save your queries by clicking on: **Save as KQL queryset:**
-
![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/1479fac2-72a5-40f4-8ae6-a339f54bbc6f)


**Build a Power BI report** 

- Copy and paste the following query into your KQL queryset. The output of this query is used as the dataset for building the Power BI report.

StockPrices

| summarize Count=count(sector) by symbol

| sort by Count

- Click on Build Power BI report: You will land into a Power BI application with the Query showing up on the right side:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/0d7b0ce0-da83-4eb6-bfed-163653c6ee16)

- Click on the Data Tab and move the symbol to x-axis and the Count variable to y-axis as below:


![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/981371bd-8c76-4c72-b65e-27bd9830d7e8)



- Click on File and save the** report giving it a name**: PowerBI-RTA** and the workspace name: **RTA\_Workshop**:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/1176ea94-df16-4be1-bff1-88af628b474e)




**Module 3: Ingest data from Event hub into Lakehouse and KQL table using Eventstream**

Prerequisites:

- Event hub pre-created in Azure portal with event hub data available to stream the data to Fabric.
- Pre-create an access policy to access the data in Fabric

Please follow the link below to deploy an application which will deploy both the application and the Event hub using the Azure portal: 

- Follow the steps Set a shared access policy on your event hub : Before you can create a connection to your Event Hubs data, you need to set a shared access policy (SAS) on the event hub and collect some information to be used later in setting up the connection. 

`              `In the Azure portal, browse to the event hubs instance you plan to connect.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/1a55c96f-0c5d-4d35-982d-c2c50d3a4fb3)


- Create a new event stream in Fabric real time Analytics experience: New\_Toll\_Es

![A screenshot of a computer

Description automatically generated](Aspose.Words.434d5218-f08f-4a9c-8c1b-1e06dff426f8.032.png)

- Create New Event hub source connection:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/bd2f3544-eeb2-4ab9-b438-47f521348701)


- If you do not have existing connection to Evenhub create a new one, capturing the following details from Event hub portal:
- Eventhub Name Space: (Event hub Name Space)
- Event hub name : (Event hub name)
- Shared Access Key Name: (Name of your policy)
- Shared Access Key: (Primary Key of your Event hub)

![](Aspose.Words.434d5218-f08f-4a9c-8c1b-1e06dff426f8.034.png)

- After you have created the new connection, enter the values for your cloud connection:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/3a93bdea-efb7-4713-9324-209a59e2f75e)


- Enter your consumer group from Eventhub where you will be reading the data from.
- Select a Data format for your event hub data: This can be Json, Avro or CSV data formats
- Enter Add to add all the details to the source of the Event stream.

Enter the destination details:

Destination: Lakehouse:

- Click on + on the right side of Eventream box to enter your destination:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/7a4fdcf0-b3ce-478b-9842-4cb5fc0769c2)


- If you chose the lakehouse, please enter all the Lakehouse details in the popped up window:


![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/d6c3eb25-f366-4a20-873a-3dc3950eef8c)


- Once you save the settings, the data should be flowing into your Lakehouse

Destination: KQL Table:

- If you would like the data to be steaming into KQL database, you can pick KQL database as the destination by entering all the details in the pop-up window.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/3276bd5e-453c-4faf-89ab-9dfc242a817b)








- Log into Fabric “Real-Time Analytics” experience and log into your KQL database: StockPrice

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/c0c7dc85-dbc7-4c79-9928-c13eb27eb4b1)


- Click on Get Data and then Pick Event hubs from the drop-down menu.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/d92d0d3a-3f3a-410f-a7c3-65c52386e413)


- A new window pops up:

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/6e96465b-c588-4d94-8dab-c2e8e56c89f0)

- Select Next: Source and enter all the details we captured in step 2)

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/f01052c6-b1e4-435d-a037-25f4df6bfccb)


- Select Save. A new cloud  data connection between Fabric and Event Hubs is created.

- - Once both the destination options have configured, you have now set up your Fabric to get real time data from Event hub into Onelake and KQL table.

![image](https://github.com/deekumar2019/FabricWorkshops/assets/48809317/e28f9c04-acec-49d1-b682-99f9766c8c37)



