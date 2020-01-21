---
title: 部署连接器以存档 Twitter 数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置本机连接器以将 Twitter 数据导入和存档到 Office 365。 将此数据导入 Office 365 后，您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的 Twitter 数据的管理。
ms.openlocfilehash: ee15086c6389fa2d2e7d07412ab533301cd8a842
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247465"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="8e497-104">部署连接器以存档 Twitter 数据</span><span class="sxs-lookup"><span data-stu-id="8e497-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="8e497-105">本文包含的分步过程可部署使用 Office 365 导入服务将数据从组织的 Twitter 帐户导入 Office 365 的连接器。</span><span class="sxs-lookup"><span data-stu-id="8e497-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="8e497-106">有关此过程的简要概述以及部署 Twitter 连接器所需的先决条件列表，请参阅[使用连接器在 Office 365 中存档 Twitter 数据（预览）](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="8e497-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="8e497-107">步骤1：下载程序包</span><span class="sxs-lookup"><span data-stu-id="8e497-107">Step 1: Download the package</span></span>

<span data-ttu-id="8e497-108">从位于 GitHub 存储库中的 "发布" 部分下载预[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)建程序包（网址为）。</span><span class="sxs-lookup"><span data-stu-id="8e497-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="8e497-109">在最新版本下，下载名为**SampleConnector**的 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="8e497-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="8e497-110">您在步骤4中将此 zip 文件上传到 Azure。</span><span class="sxs-lookup"><span data-stu-id="8e497-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="8e497-111">步骤2：在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="8e497-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="8e497-112">转到<https://portal.azure.com>并使用 Office 365 全局管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="8e497-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![登录到 Azure](media/TCimage01.png)

2. <span data-ttu-id="8e497-114">在左侧导航窗格中，单击 " **Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![转到 Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="8e497-116">在左侧导航窗格中，单击 "**应用程序注册（预览）** "，然后单击 "**新建注册**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![创建新的应用注册](media/TCimage03.png)

4. <span data-ttu-id="8e497-118">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="8e497-118">Register the application.</span></span> <span data-ttu-id="8e497-119">在 "**重定向 URI （可选）**" 下，选择 "应用程序类型" 下拉`https://portal.azure.com`列表中的 " **WEB** "，然后在 URI 框中键入 uri。</span><span class="sxs-lookup"><span data-stu-id="8e497-119">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="8e497-120">重https://portal.azure.com定向 URI 的类型</span><span class="sxs-lookup"><span data-stu-id="8e497-120">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="8e497-121">复制**应用程序（客户端） id**和**目录（租户） id** ，并将其保存到文本文件或其他安全位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="8e497-122">可在后续步骤中使用这些 Id。</span><span class="sxs-lookup"><span data-stu-id="8e497-122">You use these IDs in later steps.</span></span>

    ![复制并保存应用程序 Id 和目录 Id](media/TCimage05.png)

6. <span data-ttu-id="8e497-124">转到**证书 & 新应用程序的证书**，并在 "**客户端密码**" 下，单击 "**新建客户端密码**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-124">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![创建新的客户端密码](media/TCimage06.png)

7. <span data-ttu-id="8e497-126">创建新的机密。</span><span class="sxs-lookup"><span data-stu-id="8e497-126">Create a new secret.</span></span> <span data-ttu-id="8e497-127">在 "说明" 框中，键入密码，然后选择一个过期时间段。</span><span class="sxs-lookup"><span data-stu-id="8e497-127">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![键入密码并选择 "过期期限"](media/TCimage08.png)

8. <span data-ttu-id="8e497-129">复制密码的值，并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-129">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="8e497-130">这是您在后续步骤中使用的 AAD 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="8e497-130">This is the AAD application secret that you use in later steps.</span></span>

   ![复制并保存密码](media/TCimage09.png)

9. <span data-ttu-id="8e497-132">转到**清单**并复制 identifierUris （也称为 AAD 应用程序 Uri），如以下屏幕截图中所示。</span><span class="sxs-lookup"><span data-stu-id="8e497-132">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="8e497-133">将 AAD 应用程序 Uri 复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-133">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="8e497-134">您可以在步骤6中使用它。</span><span class="sxs-lookup"><span data-stu-id="8e497-134">You use it in Step 6.</span></span>

    ![复制并保存 AAD 应用程序 Uri](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="8e497-136">步骤3：创建 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="8e497-136">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="8e497-137">转到您的组织的 Azure 主页。</span><span class="sxs-lookup"><span data-stu-id="8e497-137">Go to the Azure home page for your organization.</span></span>

    ![Gi 到 Azure 主页](media/TCimage11.png)

2. <span data-ttu-id="8e497-139">单击 "**创建资源**"，然后在搜索框中键入**存储帐户**。</span><span class="sxs-lookup"><span data-stu-id="8e497-139">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![创建存储帐户资源](media/TCimage12.png)

3. <span data-ttu-id="8e497-141">单击 "**存储**"，然后单击 "**存储帐户**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-141">Click **Storage**, and then click **Storage account**.</span></span>

   ![单击 "存储"，然后单击 "存储帐户"](media/TCimage13.png)

4. <span data-ttu-id="8e497-143">在 "**创建存储帐户**" 页上的 "订阅" 框中，根据您拥有的 Azure 订阅的类型选择 "按即点**即**用" 或 "**免费试用**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-143">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![选择存储帐户类型](media/TCimage14.png)

5. <span data-ttu-id="8e497-145">选择或创建一个资源组。</span><span class="sxs-lookup"><span data-stu-id="8e497-145">Select or create a resource group.</span></span>

   ![选择或创建资源组](media/TCimage15.png)

6. <span data-ttu-id="8e497-147">键入存储帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="8e497-147">Type a name for the storage account.</span></span>

   ![为存储帐户命名](media/TCimage16.png)

7. <span data-ttu-id="8e497-149">查看，然后单击 "**创建**" 以创建存储帐户。</span><span class="sxs-lookup"><span data-stu-id="8e497-149">Review and then click **Create** to create the storage account.</span></span>

   ![查看设置，然后创建存储帐户](media/TCimage17.png)

8. <span data-ttu-id="8e497-151">几分钟后，单击 "**刷新**"，然后单击 "**转到资源**" 以导航到存储帐户。</span><span class="sxs-lookup"><span data-stu-id="8e497-151">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![转到刚创建的存储帐户](media/TCimage18.png)

9. <span data-ttu-id="8e497-153">单击左侧导航窗格中的 "**访问密钥**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-153">Click **Access keys** in the left navigation pane.</span></span>

   ![单击 "访问密钥"](media/TCimage19.png)

10. <span data-ttu-id="8e497-155">复制**连接字符串**并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-155">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="8e497-156">在步骤4中创建 web 应用资源时，可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="8e497-156">You use this when creating a web app resource in Step 4.</span></span>

    ![复制连接字符串](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="8e497-158">步骤4：在 Azure 中创建新的 web 应用资源</span><span class="sxs-lookup"><span data-stu-id="8e497-158">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="8e497-159">在 Azure 门户的**主页**上，单击 "**创建资源\>所有\> Web 应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-159">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="8e497-160">在 " **Web 应用程序**" 页上，单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-160">On the **Web app** page, click **Create**.</span></span>

   ![在 Azure 中创建 web 应用资源](media/TCimage21.png)

2. <span data-ttu-id="8e497-162">填写详细信息（如下所示），然后创建 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8e497-162">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="8e497-163">您在 "**应用名称**" 框中输入的名称用于创建 Azure 应用服务 URL;例如，twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="8e497-163">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![<span data-ttu-id="8e497-164">Web 应用资源的类型名称;例如 twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="8e497-164">Type name for the web app resource; for example twitterconnector.azurewebsites.net</span></span> ](media/TCimage22.png)

3. <span data-ttu-id="8e497-165">转到新创建的 web 应用资源，并单击左侧导航窗格中的 "**应用程序设置**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-165">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="8e497-166">在 "**应用程序设置**" 下，单击 "**添加新设置**"，然后添加以下三个设置。</span><span class="sxs-lookup"><span data-stu-id="8e497-166">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="8e497-167">使用从前面的步骤中复制到文本文件中的值：</span><span class="sxs-lookup"><span data-stu-id="8e497-167">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="8e497-168">**APISecretKey** –您可以键入任何值作为密码。</span><span class="sxs-lookup"><span data-stu-id="8e497-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="8e497-169">这用于在步骤7中访问连接器 web 应用。</span><span class="sxs-lookup"><span data-stu-id="8e497-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="8e497-170">**StorageAccountConnectionString** –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="8e497-170">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="8e497-171">**tenantId** –在步骤2中创建 Azure Active Directory 中的 Twitter 连接器应用之后复制的 Office 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="8e497-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![添加应用程序设置](media/TCimage23.png)

4. <span data-ttu-id="8e497-173">在 "**常规设置**" 下，单击 "**始终打开**" 旁边的 **""** 。</span><span class="sxs-lookup"><span data-stu-id="8e497-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="8e497-174">单击页面顶部的 "**保存**" 以保存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="8e497-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![打开 web 应用资源，然后将其保存](media/TCimage24.png)

5. <span data-ttu-id="8e497-176">最后一步是将连接器应用源代码上载到您在步骤1中下载的 Azure。</span><span class="sxs-lookup"><span data-stu-id="8e497-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="8e497-177">在 web 浏览器中，转到<AzureAppResourceName>https://. scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="8e497-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="8e497-178">例如，如果您的 Azure 应用资源的名称（在此部分中的步骤2中命名）为**twitterconnector**，则您将转到https://twitterconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="8e497-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="8e497-179">将 SampleConnector （您在步骤1中下载的）拖放到此页面。</span><span class="sxs-lookup"><span data-stu-id="8e497-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="8e497-180">上载文件并成功部署后，页面外观将类似于以下屏幕截图：</span><span class="sxs-lookup"><span data-stu-id="8e497-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![将 SampleConnector 文件拖放到此页面](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="8e497-182">步骤5：创建 Twitter 应用</span><span class="sxs-lookup"><span data-stu-id="8e497-182">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="8e497-183">转到https://developer.twitter.com，使用组织的开发人员帐户的凭据登录，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-183">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![转到https://developer.twitter.com并登录](media/TCimage25-5.png)
2. <span data-ttu-id="8e497-185">单击 "**创建应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-185">Click **Create an app**.</span></span>
   
   ![转到 "应用程序" 页以创建应用程序](media/TCimage26.png)

3. <span data-ttu-id="8e497-187">在 "**应用程序详细信息**" 下，添加有关应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="8e497-187">Under **App details**, add information about the application.</span></span>

   ![输入有关应用程序的信息](media/TCimage27.png)

4. <span data-ttu-id="8e497-189">在 Twitter 开发人员仪表板上，选择刚创建的应用程序，并复制显示的应用 ID 并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-189">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="8e497-190">然后单击 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-190">Then click **Details**.</span></span>
   
   ![复制并保存应用程序 Id](media/TCimage28.png)

5. <span data-ttu-id="8e497-192">在 "**密钥和标记**" 选项卡上的 "**使用者 api 密钥**" 下，复制 api 密钥并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-192">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="8e497-193">然后，单击 "**创建**" 以生成访问令牌和访问令牌机密，并将它们复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-193">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![复制并保存到 API 密钥](media/TCimage29.png)

   <span data-ttu-id="8e497-195">然后，单击 "**创建**" 以生成访问令牌和访问令牌机密，并将它们复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8e497-195">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="8e497-196">单击 "**权限**" 选项卡并配置权限，如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="8e497-196">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![配置权限](media/TCimage30.png)

7. <span data-ttu-id="8e497-198">保存权限设置后，单击 "**应用程序详细信息**" 选项卡，然后单击 "编辑" > "编辑**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-198">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![编辑应用程序详细信息](media/TCimage31.png)

8. <span data-ttu-id="8e497-200">执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8e497-200">Do the following tasks:</span></span>

   - <span data-ttu-id="8e497-201">选中此复选框可允许连接器应用登录 Twitter。</span><span class="sxs-lookup"><span data-stu-id="8e497-201">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="8e497-202">使用以下格式添加 OAuth 重定向 Uri： \*\* \<connectorserviceuri>/views/twitteroauth\**，其中*connectorserviceuri\*的值为您的组织的 Azure 应用服务 URL;例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="8e497-202">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![允许连接器应用登录到 Twitter 并添加 OAuth 重定向 Uri](media/TCimage32.png)

<span data-ttu-id="8e497-204">现在可以使用 Twitter 开发人员应用。</span><span class="sxs-lookup"><span data-stu-id="8e497-204">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="8e497-205">步骤6：配置连接器 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="8e497-205">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="8e497-206">转到 https://\<AzureAppResourceName> azurewebsites.net （其中**AzureAppResourceName**是您在步骤4中命名的 Azure 应用程序资源的名称）。</span><span class="sxs-lookup"><span data-stu-id="8e497-206">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="8e497-207">例如，如果名称为**twitterconnector**，请转到https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="8e497-207">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="8e497-208">该应用程序的主页如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="8e497-208">The home page of the app looks like the following screenshot:</span></span>

   ![转到 Azure 应用资源页](media/FBCimage41.png)

2. <span data-ttu-id="8e497-210">单击 "**配置**" 以显示登录页。</span><span class="sxs-lookup"><span data-stu-id="8e497-210">Click **Configure** to display a sign in page.</span></span>

   ![单击 "配置" 以显示登录页](media/FBCimage42.png)

3. <span data-ttu-id="8e497-212">在 "租户 Id" 框中，键入或粘贴您在步骤2中获取的租户 Id。</span><span class="sxs-lookup"><span data-stu-id="8e497-212">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="8e497-213">在 "密码" 框中，键入或粘贴 APISecretKey （您在步骤2中获取），然后单击 "**设置配置设置**" 以显示 "**配置详细信息**" 页。</span><span class="sxs-lookup"><span data-stu-id="8e497-213">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![使用租户 Id 和 API 密钥登录](media/TCimage35.png)

4. <span data-ttu-id="8e497-215">在 "**配置详细信息**" 下，输入以下配置设置</span><span class="sxs-lookup"><span data-stu-id="8e497-215">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="8e497-216">**Twitter Api 密钥**–您在步骤5中创建的 twitter 应用程序的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="8e497-216">**Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="8e497-217">**Twitter api**密钥–您在步骤5中创建的 twitter 应用程序的 Api 密钥。</span><span class="sxs-lookup"><span data-stu-id="8e497-217">**Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="8e497-218">**Twitter 访问令牌**–您在步骤5中创建的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="8e497-218">**Twitter Access Token** – The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="8e497-219">**Twitter 访问令牌密码**–您在步骤5中创建的访问令牌密码。</span><span class="sxs-lookup"><span data-stu-id="8e497-219">**Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="8e497-220">**AAD 应用程序 id** –您在步骤2中创建的 Azure Active Directory 应用程序的应用程序 id</span><span class="sxs-lookup"><span data-stu-id="8e497-220">**AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="8e497-221">**AAD 应用程序机密**–您在步骤4中创建的 APISecretKey 密码的值。</span><span class="sxs-lookup"><span data-stu-id="8e497-221">**AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="8e497-222">**Aad 应用程序 uri** –在步骤2中获取的 aad 应用程序 uri;例如， `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`。</span><span class="sxs-lookup"><span data-stu-id="8e497-222">**AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="8e497-223">**App Insights 检测键**–将此框保留为空。</span><span class="sxs-lookup"><span data-stu-id="8e497-223">**App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="8e497-224">单击 "**保存**" 以保存连接器设置。</span><span class="sxs-lookup"><span data-stu-id="8e497-224">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="8e497-225">步骤7：在安全与合规中心中设置自定义连接器</span><span class="sxs-lookup"><span data-stu-id="8e497-225">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="8e497-226">转到<https://protection.office.com> ，然后单击 "**信息\>调控\>导入存档第三方数据**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-226">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

    ![转到安全与合规中心中的 "存档第三方数据" 页](media/TCimage36.png)

2. <span data-ttu-id="8e497-228">单击 "**添加连接器**"，然后单击 " **Twitter**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-228">Click **Add a connector** and then click **Twitter**.</span></span>

   ![单击 "添加连接器" 以添加 Twitter 连接器](media/TCimage37.png)

3. <span data-ttu-id="8e497-230">在 "**添加连接器应用程序**" 页上，输入以下信息，然后单击 "**验证连接器**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-230">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="8e497-231">在第一个框中，键入连接器的名称，如**Twitter**。</span><span class="sxs-lookup"><span data-stu-id="8e497-231">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="8e497-232">在第二个框中，键入或粘贴您在步骤4中添加的 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="8e497-232">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="8e497-233">在第三个框中，键入或粘贴 Azure 应用服务 URL;例如， **https://twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="8e497-233">In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="8e497-234">成功验证连接器后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-234">After the connector is successfully validated, click **Next**.</span></span>

   ![输入连接器应用设置](media/TCimage38.png)

4. <span data-ttu-id="8e497-236">单击 "**使用连接器应用登录**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-236">Click **Login with Connector App**.</span></span>

   ![登录到连接器应用](media/TCimage39.png)

5. <span data-ttu-id="8e497-238">再次键入或粘贴 APISecretKey，然后单击 "**登录到连接器服务**"。</span><span class="sxs-lookup"><span data-stu-id="8e497-238">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![键入 API 密钥以登录到连接器服务](media/TCimage40.png)

6. <span data-ttu-id="8e497-240">单击 "**继续使用 Twitter**。</span><span class="sxs-lookup"><span data-stu-id="8e497-240">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="8e497-241">在 Twitter 登录页面上，使用组织的 Twitter 帐户的帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="8e497-241">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![登录到 Twitter 帐户](media/TCimage42.png)

   <span data-ttu-id="8e497-243">登录后，Twitter 页面将显示以下消息： "已成功设置 Twitter 连接器作业"。</span><span class="sxs-lookup"><span data-stu-id="8e497-243">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="8e497-244">单击 "**完成**" 以完成 Twitter 连接器的设置。</span><span class="sxs-lookup"><span data-stu-id="8e497-244">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="8e497-245">在 "**设置筛选器**" 页上，可以应用筛选器以导入（和存档）特定时间的项目。</span><span class="sxs-lookup"><span data-stu-id="8e497-245">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="8e497-246">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8e497-246">Click **Next**.</span></span>

   ![配置筛选器以导入特定年龄的项目](media/TCimage44.png)

10. <span data-ttu-id="8e497-248">在 "**设置存储帐户**" 页上，键入将向 Twitter 项目导入的 Office 365 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8e497-248">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![指定要将 Twitter 项目导入到的 Office 365 邮箱](media/TCimage45.png)

11. <span data-ttu-id="8e497-250">查看您的设置，然后单击 "**完成**" 以完成安全性 & 合规性中心中的连接器设置。</span><span class="sxs-lookup"><span data-stu-id="8e497-250">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![查看设置，然后单击 "完成"](media/TCimage46.png)

    ![显示连接器设置已完成的屏幕](media/TCimage47.png)

12. <span data-ttu-id="8e497-253">转到 "**存档第三方数据**" 页，查看导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="8e497-253">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![在安全与合规中心中显示的新连接器](media/TCimage48.png)
