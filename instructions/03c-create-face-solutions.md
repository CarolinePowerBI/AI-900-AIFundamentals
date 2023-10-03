---
lab:
    title: 'Explore face recognition​'
---

# Explore face detection

> **Note**
> To complete this lab, you will need an [Azure subscription](https://azure.microsoft.com/free?azure-portal=true) in which you have administrative access.

Computer vision solutions often require an artificial intelligence (AI) solution to be able to detect human faces. For example, suppose the retail company Northwind Traders wants to locate where customers are standing in a store to best assist them. One way to accomplish this is to determine if there are any faces in the images, and if so, to identify the bounding box coordinates around the faces.

To test the capabilities of the Face service, you'll use Azure Vision Studio. This is a UI-based platform that lets you explore Azure AI Vision features, without needing to write any code. 

## Get started with Azure Vision Studio 

1. Open the [Azure Vision Studio](https://portal.vision.cognitive.azure.com). If you are not already logged in, select **Sign In** on the top menu, and use the email and password associated with your Azure subscription. 
1. Before you can use the studio, you need to associate it with an Azure AI services resource. On the rop right of the screen, click the **Settings** icon.

    ![Azure Vision Studio](media/content-safety/settings-toggle.png)

1. Under *Select a resource to work with* click **Create a new resource**. 
1. Create the new resource with the following settings:
    - **Name**: *Enter a unique name*.
    - **Subscription**: *Your Azure subscription*.
    - **Resource group**: *Select or create a resource group with a unique name*.
    - **Resource type**: Do not change
    - **Location**: *Choose any available region*.
    - **Price tier**: F0

1. Select **Review + create** then **Create** and wait for deployment to complete.
1. 

*Congratulations! You have successfully assoc
2. 
1. Wait for PowerShell to start. You should see the following screen in the Azure portal:  

    ![Wait for PowerShell to start.](media/create-face-solutions/powershell-prompt.png)

## Configure and run a client application

Now that you have a custom model, you can run a simple client application that uses the Face service.

1. In the command shell, enter the following command to download the sample application and save it to a folder called ai-900.

    ```PowerShell
    git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
    ```

    > **Tip**
    > If you already used this command in another lab to clone the *ai-900* repository, you can skip this step.

1. The files are downloaded to a folder named **ai-900**. Now we want to see all of the files in your Cloud Shell storage and work with them. Type the following command into the shell:

     ```PowerShell
    code .
    ```

    Notice how this opens up an editor like the one in the image below: 

    ![The code editor.](media/create-face-solutions/powershell-portal-guide-4.png) 

1. In the **Files** pane on the left, expand **ai-900** and select **find-faces.ps1**. This file contains some code that uses the Face service to detect and analyze faces in an image, as shown here:

    ![The editor containing code to detect faces in an image](media/create-face-solutions/find-faces-code.png)

1. Don't worry too much about the details of the code, the important thing is that it needs the endpoint URL and either of the keys for your Face resource. Copy these from the **Keys and Endpoints** page for your resource from the Azure portal and paste them into the code editor, replacing the **YOUR_KEY** and **YOUR_ENDPOINT** placeholder values respectively.

    > **Tip**
    > You may need to use the separator bar to adjust the screen area as you work with the **Keys and Endpoint** and **Editor** panes.

    After pasting the key and endpoint values, the first two lines of code should look similar to this:

    ```PowerShell
    $key="1a2b3c4d5e6f7g8h9i0j...."    
    $endpoint="https..."
    ```

1. At the top right of the editor pane, use the **...** button to open the menu and select **Save** to save your changes. Then open the menu again and select **Close Editor**.

    The sample client application will use your Face service to analyze the following image, taken by a camera in the Northwind Traders store:

    ![An image of a parent using a cellphone camera to take a picture of a child in in a store](media/create-face-solutions/store-camera-1.jpg)

1. In the PowerShell pane, enter the following commands to run the code:

    ```PowerShell
    cd ai-900
    ./find-faces.ps1 store-camera-1.jpg
    ```

1. Review the returned information, which includes the location of the face in the image. The location of a face is indicated by the top-left coordinates, and the width and height of a *bounding box*, as shown here:

    ![An image of a person with their face outlined](media/create-face-solutions/store-camera-1-face.jpg)

    >**Note**
    >Face service capabilities that return personally identifiable features are restricted. See https://azure.microsoft.com/blog/responsible-ai-investments-and-safeguards-for-facial-recognition/ for details.

1. Now let's try another image:

    ![An image of person with a shopping basket](media/create-face-solutions/store-camera-2.jpg)

    To analyze the second image, enter the following command:

    ```PowerShell
    ./find-faces.ps1 store-camera-2.jpg
    ```

1. Review the results of the face analysis for the second image.

1. Let's try one more:

    ![An image of person with a shopping cart](media/create-face-solutions/store-camera-3.jpg)

    To analyze the third image, enter the following command:

    ```PowerShell
    ./find-faces.ps1 store-camera-3.jpg
    ```

1. Review the results of the face analysis for the third image.

## Learn more

This simple app shows only some of the capabilities of the Face service. To learn more about what you can do with this service, see the [Face API page](https://azure.microsoft.com/en-us/products/cognitive-services/vision-services).
