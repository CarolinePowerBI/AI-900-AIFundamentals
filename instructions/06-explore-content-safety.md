---
lab:
    title: 'Explore Content Safety Studio'
---

The Content Safety Studio enables you to explore how text and image content can be moderated. You can run tests on sample text or images and get a severity score ranging from safe to high for each category. You can quickly find out how the Content Safety AI service works, and what it is capable of. 

In this exercise you will create a multi-service Azure AI services resource in the Azure portal and inspect its endpoint and keys. You will then use the Content Safety Studio to explore the functionality of the Content Safety AI service. 

## Create an AI Services resource

1.  In another browser tab, open the Azure portal at [https://portal.azure.com](https://portal.azure.com?azure-portal=true), signing in with your Microsoft account.
1.	Click the **&#65291;Create a resource** button and search for *Azure AI services*. Select **create** an **Azure AI services** plan. You will be taken to a page to create an Azure AI services resource. Configure it with the following settings:
- **Subscription**: Your Azure subscription.
- **Resource group**: Select or create a suitable resource group.
- **Region**: Choose any available region.
- **Name**: Enter a unique name.
- **Pricing tier**: F0 
2.	Review and create the resource and wait for deployment to complete. 

## Associate the resource to the Content Safety Studio 
In a separate browser tab, open the Content Safety Studio and sign in. The Getting started screen is displayed.

1.	Click **Settings** on the top menu.
2.	Select the Azure AI service resource you just created, and then click **Use resource**.
3.	View the endpoint and key for your resource, scrolling if necessary. If you check in the Azure Portal, you will see that this is the endpoint and key for your resource showing that you have successfully associated your resource with the Content Safety studio.
4.	Click **Content Safety Studio** to return to the home page. Under *Moderate text content*, click **Try it out**.
5.	Under *Run a simple test*, click **Safe Content**. Notice that text is displayed in the box below. 
6.	Click **Run test**. 
7.	In the Results panel, inspect the results. There are four severity levels from safe to high, and four types of harmful content. Does the Content Safety AI service consider this sample to be acceptable or not? 
8.	Now try another sample. Select the text under Violent content with misspelling. Check that the content is displayed in the box below.
9.	Click **Run test** and inspect the results in the Results panel below. Is this sample acceptable? If not, why not?

You can run tests on all the samples, then inspect the results.

You have now seen for yourself how quick and easy it is to use an AI service. Let's recap how it works:
- Create the resource
- Associate it with the AI studio
- Try it out

Before finishing, why not try some of your own text? Simply copy and paste the text under *Sample text or type your own words or phrases* and click **Run test**. This gives you an idea of the possibilities of Content Safety, and how it might be used within an application to identify harmful content. And you can try other AI services just as easily, using the appropriate AI studio.

After you have finished, delete the Azure AI services resource in the Azure Portal. 
