# Achieve more with **Microsoft Fabric, GenAI & Semantic Kernel!**
<img src="https://dataplatformblogcdn.azureedge.net/wp-content/uploads/2023/08/Screenshot-2023-08-13-at-20.53.03.png" width=50% height=50%>



# Semantic Kernel
[Semantic Kernel](https://aka.ms/semantic-kernel) is a lightweight open-source SDK that allows you to orchestrate AI plugins. Semantic Kernel provides a set of connectors to infuse memories and models, simulating a "brain" for your app, and AI plugins for real-world interaction, serving as the "body."

<img src="./images/mind-and-body-of-semantic-kernel.png" width=25% height=25%>


# Prerequisites
1. Access to [Microsoft Fabric](https://fabric.microsoft.com/).
3. Azure OpenAI Endpoint, Key, and Deployments models (text-davinci-003, gpt-35-turbo)
4. Upload sample Skills to the Lakehouse
   1. Download **sk-samples-skills** folder from the current repo to your local device.
   2. Sign in to [Microsoft Fabric](https://fabric.microsoft.com/) -> Browse -> Filter -> Lakehouse -> Select your Lakehouse.
   3. Files Ellipsis, select Upload and then Upload folder
   

# Let's Get Started #

## Upload sample Plugins to the Lakehouse
A Plugin (aka Skill) is a group of functions that are exposed to AI apps and services. The functions within plugins can then be orchestrated by an AI application to accomplish user requests. 
1. Download **[sk-sample-plugins](./sk-sample-plugins)** folder from the current repo to your local device.
2. Sign in to [Microsoft Fabric](https://fabric.microsoft.com/), Browse, Filter on Lakehouse, Click to Select your Lakehouse.
3. In the Explorer, Click on the Ellipsis across Files, select Upload and then Upload folder

## (Optional) Add semantic kernel to Spark Library management
This may take 5-8 minutes.
If you skip this step, then you need to install semantic kernel for every notebook, by uncommenting relevant line in the notebook.
If you perform this step, there will be additional 2-3 minutes when your spark session starts.
1. Select your workspace, click on Workspace setttings, click on Data Engineering/Science
2. Select Library management, Select "+ Add from PyPI"
3. Input semantic-kernel, choose 0.3.8.dev0 or latest available.
4. Optionally Add pip version 23.2.1

## Import notebooks
1. Download notebooks from the current repo to your local device.
2. In MS Fabric, Switch to the Data Science experience. 
3. Import notebook, upload

## Use Plugins inline, and from Lakehouse file 
1. MS Fabric -> Data Science experience -> Filter -> Notebook -> Select sk-msfabric-001-getting-started
2. Provide Azure OpenAI Endpoint, Key in the third cell
3. Run the cells from beginning to end.

## Use the Planner
Planner is a function that takes a user's ask and returns back a plan on how to accomplish the request. It does so by using AI to mix-and-match the plugins registered in the kernel so that it can recombine them into a series of steps that complete a goal.
1. MS Fabric -> Data Science experience -> Filter -> Notebook -> Select sk-msfabric-002-using-the-planner
2. Provide Azure OpenAI Endpoint, Key in the third cell
3. Run the cells from beginning to end.

## Use Natural Language to query Lakehouse
1. MS Fabric -> Data Science experience -> Filter -> Notebook -> Select sk-msfabric-003-NLP_to_SQL
2. Provide Azure OpenAI Endpoint, Key in the third cell
3. Run the cells from beginning to end.

# Reference
1. Github Semantic Kernel [repo](https://github.com/microsoft/semantic-kernel)

