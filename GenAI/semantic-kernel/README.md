# Excitement to Execution!
Achieve more with **Microsoft Fabric, GenAI & Semantic Kernel!**

# Semantic Kernel
[Semantic Kernel](https://aka.ms/semantic-kernel) is a lightweight open-source SDK that allows you to orchestrate AI plugins. Semantic Kernel provides a set of connectors to infuse memories and models, simulating a "brain" for your app, and AI plugins for real-world interaction, serving as the "body."

![Unlock AI's Full Potential with Semantic Kernel: Where Brains and Bodies Converge.](https://learn.microsoft.com/en-us/semantic-kernel/media/mind-and-body-of-semantic-kernel.png)


# Prerequisites
1. Access to [Microsoft Fabric](https://fabric.microsoft.com/).
3. Azure OpenAI Endpoint, Key, and Deployments models (text-davinci-003, gpt-35-turbo)
4. Upload sample Skills to the Lakehouse
   1. Download **sk-samples-skills** folder from the current repo to your local device.
   2. Sign in to [Microsoft Fabric](https://fabric.microsoft.com/) -> Browse -> Filter -> Lakehouse -> Select your Lakehouse.
   3. Files Ellipsis, select Upload and then Upload folder
   

# Let's Get Started #

## Upload sample Skills to the Lakehouse
1. Download **[sk-samples-skills](./sk-samples-skills)** folder from the current repo to your local device.
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

## sk-msfabric-001-getting-started
1. MS Fabric -> Data Science experience -> Filter -> Notebook -> Select sk-msfabric-001-getting-started
2. Provide Azure OpenAI Endpoint, Key in the third cell
3. Run the cells from beginning to end.

## sk-msfabric-002-using-the-planner
1. MS Fabric -> Data Science experience -> Filter -> Notebook -> Select sk-msfabric-002-using-the-planner
2. Provide Azure OpenAI Endpoint, Key in the third cell
3. Run the cells from beginning to end.

# Reference
1. Github Semantic Kernel [repo](https://github.com/microsoft/semantic-kernel)

