Hands-on-Lab

**Data Activator**

![A screenshot of a computer program

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.001.png)



Contents

1) Introduction- Fabric 
1) Introduction - Data Activator
1) Prerequisites
1) Module 1: Create a Fabric workspace
1) ` `Module 2: Build your Data Activator alerts from Power Bi reports



**Introduction:**

What is Microsoft Fabric?

Microsoft Fabric is an all-in-one analytics solution for enterprises that covers everything from data movement to data science, Real-Time Analytics, and business intelligence. It offers a comprehensive range of services, including data lake, data engineering, and data integration, all in one place. ![A screenshot of a blue screen

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.002.png)

Fabric brings together experiences such as Data Engineering, Data Factory, Data Science, Data Warehouse, Real-Time Analytics, and Power BI onto a shared SaaS foundation. This integration provides the following advantages:

- An extensive range of deeply integrated analytics in the industry.
- Shared experiences across experiences that are familiar and easy to learn.
- Developers can easily access and reuse all assets.
- A unified data lake that allows you to retain the data where it is while using your preferred analytics tools.
- Centralized administration and governance across all experiences.

With the Microsoft Fabric SaaS experience, all the data and the services are seamlessly integrated. IT teams can centrally configure core enterprise capabilities and permissions are automatically applied across all the underlying services. Additionally, data sensitivity labels are inherited automatically across the items in the suite.

**

**Data Activator:**

Data Activator is a no-code tool for automatically taking actions when patterns or conditions are detected in changing data. It monitors data in Power BI reports and Event Hub data streams, for when the data hits certain thresholds or matches other patterns. It then automatically takes appropriate action such as alerting users or kicking off Power Automate workflows.


**What makes Activator unique?**

Data Activator allows customers to build a digital nervous system that acts across all their data, at scale and in a timely manner. Business users can describe business conditions in a no-code experience to launch actions such as Email, Teams notifications, Power Automate flows and call into 3rd party action system. Business users can self-serve their needs and reduce their reliance on internal IT and/or developer teams, either of which is often costly or hinders agility. Customer organizations don’t need a developer team to manage and maintain custom in-house monitoring or alerting solutions.

**Activator Common use cases:**

- Run ads when same-store sales decline.
- Alert store managers to move food from failing grocery store freezers before it spoils.
- Retain customers who had a bad experience by tracking their journey through apps, websites etc.
- Help logistics companies find lost shipments proactively by starting an investigation workflow when package status isn’t updated for a certain length of time.
- Alert account teams when customers fall into arrears, with customized time or value limits per customer.
- Track data pipeline quality, either re-running jobs or alerting when pipelines fail or anomalies are detected.




**How Activator works:**

Data Activator drives actions through a 3-step process: 

1) **Connect to your data:** Data Activator can connect to a wide range of data sources in Microsoft Fabric, from Power BI datasets, Eventstreams, and more. Once Data Activator is connected to your data, it continually monitors it for actionable patterns. 
1) **Detect actionable conditions:** Data Activator gives you a single place to define actionable patterns in your data. These can range from simple thresholds (such as value being exceeded) to more complex patterns over time (such a value trending down).  
1) **Trigger actions:** When Data Activator detects an actionable pattern, it triggers an action. That action can be an email or a Teams alert to the relevant person in your organization or triggering an automatic process, via a Power Automate flow or an action in one of your organization’s line-of-business apps. 

![Driving actions from your data with Data Activator | Microsoft Fabric ...](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.003.png)



**Prerequisites** 

- Power BI Premium License
- Fabric Capacity (Free F64 Fabric capacity available during the Fabric Preview period ending 9/30/2023)



**

**Module 1: Create a PowerBI Workspace:**

![A screenshot of a computer

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.004.png)

**Fill out the Create Workspace as follows:**

- Workspace Name: RTA\_Workshop
- Description: This workspace is created to work on RTA capabilities in Fabric.
- Expand Advance settings
- License Mode: Trial (Provided Fabric Trial is enabled)
- Leave all the other settings to default.

![A screenshot of a computer

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.005.png)

1) Select Apply.
1) A new workspace will be created and opened.
**


**Module 2: Build your Data Activator alerts from Power Bi reports.**

1. On the context switcher, select the Data Activator Experience, you would be provided with an option to create **Reflex** item and a **Reflex Sample** item. Choose the Reflex Sample.

![A screenshot of a computer

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.006.png)

1. By default, you would be able to see the package delivery sample steaming data loaded and getting updated frequently and you can view it on the data tab.

![A screenshot of a computer

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.007.png)

1. Select the design mode and create a new property. Choose the "Package in Transit" property and select the packages of your choice on the top right corner of the visual chart and value as Humidity, as you choose these values, you can examine the refresh happening on the data visual and the value on the chat starts showing the values for City.
1. Select the next step, choose "Detect" and use the filter: Operation as "is equal" and Value as 50

![A screenshot of a computer

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.008.png)

1. As a next step, choose "Act" and choose "Send teams message".
1. Add the necessary "to address", headline and optional message to the teams' message and click on Start.
1. This enabled your Reflex property.
1. As you watch the data hitting the value > 50, for the selected packages, you would see the teams' message on the Data Activator teams bot.

![A screenshot of a web page

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.009.png)

**Module 3: Create Reflex item from Power BI Report Trigger Action**

1. Choose any pre-created Power BI report which has visuals with date/time column in them. Select an area chart with datetime key(DeliveryDateKey) field as your X-axis and Sum of Profits as your Y-axis

![A screenshot of a computer

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.010.png)

1. On the Visual properties (...) ellipses, you will find an option "Trigger Action".
1. On clicking "Trigger Action" option, you would see a pop-up pane on the right-hand side, you can configure the basic settings for the Reflex item that is getting generated.

![A screenshot of a computer

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.011.png)

1. Choose the Reflex properties based on the measures available in the table and set the threshold points for the trigger as SumOfProfits   < $53million and create the new Reflex item by providing a name “**NewReflexProfit**s” under a chosen workspace.
1. Once the Reflex item is created, you would be able to go to the Reflex item with the pop-up link or on the chosen workspace and continue to configure actions(set up a email message) on the reflex trigger that is set.
1. Monitor the email message notification in your inbox for details:

Example email message as below:

![A screenshot of a computer error

Description automatically generated](Aspose.Words.4812d379-4c46-4ec3-a347-2873b82fd539.012.png) 



