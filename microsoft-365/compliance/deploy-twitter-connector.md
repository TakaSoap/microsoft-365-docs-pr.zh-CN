---
title: 部署连接器以存档 Twitter 数据
f1.keywords:
- NOCSH
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
description: 管理员可以设置本机连接器以将 Twitter 数据导入和存档到 Microsoft 365。 将此数据导入 Microsoft 365 后，您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的 Twitter 数据的管理。
ms.openlocfilehash: 9951040335a2dcacc90ac4dc7a6f3e5079bf5692
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595277"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="fe908-104">部署连接器以存档 Twitter 数据</span><span class="sxs-lookup"><span data-stu-id="fe908-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="fe908-105">本文包含的分步过程可部署使用 Office 365 导入服务将数据从组织的 Twitter 帐户导入 Microsoft 365 的连接器。</span><span class="sxs-lookup"><span data-stu-id="fe908-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="fe908-106">有关此过程的高级概述以及部署 Twitter 连接器所需的先决条件列表，请参阅[Set up a connector to Archive twitter data ](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="fe908-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="fe908-107">步骤1：在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="fe908-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="fe908-108">转到<https://portal.azure.com>并使用 Office 365 全局管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="fe908-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![登录到 Azure](media/TCimage01.png)

2. <span data-ttu-id="fe908-110">在左侧导航窗格中，单击 " **Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![转到 Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="fe908-112">在左侧导航窗格中，单击 "**应用程序注册（预览）** "，然后单击 "**新建注册**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![创建新的应用注册](media/TCimage03.png)

4. <span data-ttu-id="fe908-114">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe908-114">Register the application.</span></span> <span data-ttu-id="fe908-115">在 "**重定向 URI （可选）**" 下，选择 "应用程序类型" 下拉`https://portal.azure.com`列表中的 " **WEB** "，然后在 URI 框中键入 uri。</span><span class="sxs-lookup"><span data-stu-id="fe908-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="fe908-116">重https://portal.azure.com定向 URI 的类型</span><span class="sxs-lookup"><span data-stu-id="fe908-116">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="fe908-117">复制**应用程序（客户端） id**和**目录（租户） id** ，并将其保存到文本文件或其他安全位置。</span><span class="sxs-lookup"><span data-stu-id="fe908-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="fe908-118">可在后续步骤中使用这些 Id。</span><span class="sxs-lookup"><span data-stu-id="fe908-118">You use these IDs in later steps.</span></span>

    ![复制并保存应用程序 Id 和目录 Id](media/TCimage05.png)

6. <span data-ttu-id="fe908-120">转到**证书 & 新应用程序的证书**，并在 "**客户端密码**" 下，单击 "**新建客户端密码**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![创建新的客户端密码](media/TCimage06.png)

7. <span data-ttu-id="fe908-122">创建新的机密。</span><span class="sxs-lookup"><span data-stu-id="fe908-122">Create a new secret.</span></span> <span data-ttu-id="fe908-123">在 "说明" 框中，键入密码，然后选择一个过期时间段。</span><span class="sxs-lookup"><span data-stu-id="fe908-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![键入密码并选择 "过期期限"](media/TCimage08.png)

8. <span data-ttu-id="fe908-125">复制密码的值，并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="fe908-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="fe908-126">这是您在后续步骤中使用的 AAD 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="fe908-126">This is the AAD application secret that you use in later steps.</span></span>

   ![复制并保存密码](media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="fe908-128">步骤2：将来自 GitHub 的连接器 web 服务部署到你的 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="fe908-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="fe908-129">转到[此 GitHub 网站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)，然后单击 "**部署到 Azure**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![转到 Azure 主页](media/FBCimage11.png)

2. <span data-ttu-id="fe908-131">单击 "**部署到 Azure**" 后，您将被重定向到具有自定义模板页面的 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="fe908-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="fe908-132">填写 "**基础知识**" 和 "**设置**详细信息"，然后单击 "**购买**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![单击 "创建资源并键入存储帐户"](media/FBCimage12.png)

    - <span data-ttu-id="fe908-134">**订阅：** 选择要将 Twitter 连接器 web 服务部署到的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="fe908-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="fe908-135">**资源组：** 选择或创建新的资源组。</span><span class="sxs-lookup"><span data-stu-id="fe908-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="fe908-136">资源组是保留 Azure 解决方案的相关资源的容器。</span><span class="sxs-lookup"><span data-stu-id="fe908-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="fe908-137">**位置：** 选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="fe908-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="fe908-138">**Web 应用名称：** 为连接器 web 应用提供一个唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="fe908-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="fe908-139">Th 名称的长度必须介于3到18个字符之间。</span><span class="sxs-lookup"><span data-stu-id="fe908-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="fe908-140">此名称用于创建 Azure 应用服务 URL;例如，如果提供 Web 应用程序名称**twitterconnector** ，则 Azure 应用服务 URL 将为**twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="fe908-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="fe908-141">**tenantId：** 在步骤1中创建 Azure Active Directory 中的 Facebook 连接器应用之后复制的 Microsoft 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="fe908-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="fe908-142">**APISecretKey：** 您可以键入任何值作为密码。</span><span class="sxs-lookup"><span data-stu-id="fe908-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="fe908-143">这用于在步骤5中访问连接器 web 应用。</span><span class="sxs-lookup"><span data-stu-id="fe908-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="fe908-144">部署成功后，页面外观将类似于以下屏幕截图：</span><span class="sxs-lookup"><span data-stu-id="fe908-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![单击 "存储"，然后单击 "存储帐户"](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="fe908-146">步骤3：创建 Twitter 应用</span><span class="sxs-lookup"><span data-stu-id="fe908-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="fe908-147">转到https://developer.twitter.com，使用组织的开发人员帐户的凭据登录，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![转到https://developer.twitter.com并登录](media/TCimage25-5.png)
2. <span data-ttu-id="fe908-149">单击 "**创建应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-149">Click **Create an app**.</span></span>
   
   ![转到 "应用程序" 页以创建应用程序](media/TCimage26.png)

3. <span data-ttu-id="fe908-151">在 "**应用程序详细信息**" 下，添加有关应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="fe908-151">Under **App details**, add information about the application.</span></span>

   ![输入有关应用程序的信息](media/TCimage27.png)

4. <span data-ttu-id="fe908-153">在 Twitter 开发人员仪表板上，选择刚创建的应用程序，并复制显示的应用 ID 并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="fe908-153">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="fe908-154">然后单击 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-154">Then click **Details**.</span></span>
   
   ![复制并保存应用程序 Id](media/TCimage28.png)

5. <span data-ttu-id="fe908-156">在 "**密钥和标记**" 选项卡上的 "**使用者 api 密钥**" 下，复制 api 密钥并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="fe908-156">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="fe908-157">然后，单击 "**创建**" 以生成访问令牌和访问令牌机密，并将它们复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="fe908-157">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![复制并保存到 API 密钥](media/TCimage29.png)

   <span data-ttu-id="fe908-159">然后，单击 "**创建**" 以生成访问令牌和访问令牌机密，并将它们复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="fe908-159">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="fe908-160">单击 "**权限**" 选项卡并配置权限，如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="fe908-160">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![配置权限](media/TCimage30.png)

7. <span data-ttu-id="fe908-162">保存权限设置后，单击 "**应用程序详细信息**" 选项卡，然后单击 "编辑" > "编辑**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-162">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![编辑应用程序详细信息](media/TCimage31.png)

8. <span data-ttu-id="fe908-164">执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fe908-164">Do the following tasks:</span></span>

   - <span data-ttu-id="fe908-165">选中此复选框可允许连接器应用登录 Twitter。</span><span class="sxs-lookup"><span data-stu-id="fe908-165">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="fe908-166">使用以下格式添加 OAuth 重定向 Uri： \*\* \<connectorserviceuri>/views/twitteroauth\**，其中*connectorserviceuri\*的值为您的组织的 Azure 应用服务 URL;例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="fe908-166">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![允许连接器应用登录到 Twitter 并添加 OAuth 重定向 Uri](media/TCimage32.png)

<span data-ttu-id="fe908-168">现在可以使用 Twitter 开发人员应用。</span><span class="sxs-lookup"><span data-stu-id="fe908-168">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="fe908-169">步骤4：配置连接器 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="fe908-169">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="fe908-170">转到 https://\<AzureAppResourceName> azurewebsites.net （其中**AzureAppResourceName**是您在步骤4中命名的 Azure 应用程序资源的名称）。</span><span class="sxs-lookup"><span data-stu-id="fe908-170">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="fe908-171">例如，如果名称为**twitterconnector**，请转到https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="fe908-171">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="fe908-172">该应用程序的主页如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="fe908-172">The home page of the app looks like the following screenshot:</span></span>

   ![转到 Azure 应用资源页](media/FBCimage41.png)

2. <span data-ttu-id="fe908-174">单击 "**配置**" 以显示登录页。</span><span class="sxs-lookup"><span data-stu-id="fe908-174">Click **Configure** to display a sign in page.</span></span>

   ![单击 "配置" 以显示登录页](media/FBCimage42.png)

3. <span data-ttu-id="fe908-176">在 "租户 Id" 框中，键入或粘贴您在步骤2中获取的租户 Id。</span><span class="sxs-lookup"><span data-stu-id="fe908-176">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="fe908-177">在 "密码" 框中，键入或粘贴 APISecretKey （您在步骤2中获取），然后单击 "**设置配置设置**" 以显示 "配置详细信息" 页。</span><span class="sxs-lookup"><span data-stu-id="fe908-177">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![使用租户 Id 和 API 密钥登录](media/TCimage35.png)

4. <span data-ttu-id="fe908-179">输入以下配置设置</span><span class="sxs-lookup"><span data-stu-id="fe908-179">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="fe908-180">**Twitter Api 密钥：** 您在步骤3中创建的 Twitter 应用程序的应用 ID。</span><span class="sxs-lookup"><span data-stu-id="fe908-180">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="fe908-181">**Twitter Api 密钥：** 您在步骤3中创建的 Twitter 应用程序的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="fe908-181">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="fe908-182">**Twitter 访问令牌：** 您在步骤3中创建的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="fe908-182">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="fe908-183">**Twitter 访问令牌机密：** 您在步骤3中创建的访问令牌密码。</span><span class="sxs-lookup"><span data-stu-id="fe908-183">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="fe908-184">**AAD 应用程序 ID：** 您在步骤1中创建的 Azure Active Directory 应用程序的应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="fe908-184">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="fe908-185">**AAD 应用程序密码：** 您在步骤1中创建的 APISecretKey 密码的值。</span><span class="sxs-lookup"><span data-stu-id="fe908-185">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="fe908-186">单击 "**保存**" 以保存连接器设置。</span><span class="sxs-lookup"><span data-stu-id="fe908-186">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="fe908-187">步骤5：在 Microsoft 365 合规性中心中设置 Twitter 连接器</span><span class="sxs-lookup"><span data-stu-id="fe908-187">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="fe908-188">转到[https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后单击左侧导航中的 "**数据连接器**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-188">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fe908-189">在 " **Twitter**" 下的 "**数据连接器（预览）** " 页上，单击 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-189">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="fe908-190">在**Twitter**页面上，单击 "**添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-190">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="fe908-191">在 "**服务条款**" 页上，单击 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-191">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="fe908-192">在 "**为连接器应用添加凭据**" 页上，输入以下信息，然后单击 "**验证连接**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-192">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![输入连接器应用凭据](media/TCimage38.png)

    - <span data-ttu-id="fe908-194">在 "**名称**" 框中，键入连接器的名称，如**Twitter 帮助句柄**。</span><span class="sxs-lookup"><span data-stu-id="fe908-194">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="fe908-195">在 "**连接器 URL** " 框中，键入或粘贴 Azure 应用服务 URL;例如`https://twitterconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="fe908-195">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="fe908-196">在 "**密码**" 框中，键入或粘贴您在步骤2中创建的 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="fe908-196">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="fe908-197">在 " **Azure 应用 ID** " 框中，键入或粘贴您在步骤1中获取的 Azure 应用程序应用程序 id （也称为 "*客户端 id*"）的值。</span><span class="sxs-lookup"><span data-stu-id="fe908-197">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="fe908-198">成功验证连接后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-198">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="fe908-199">在 "**授权 Microsoft 365 导入数据**" 页上，再次键入或粘贴 APISecretKey，然后单击 "**登录 web 应用**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-199">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="fe908-200">单击 "**使用 Twitter 登录**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-200">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="fe908-201">在 Twitter 登录页面上，使用您的组织的 Twitter 帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="fe908-201">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![登录到 Twitter 帐户](media/TCimage42.png)

   <span data-ttu-id="fe908-203">登录后，Twitter 页面将显示以下消息： "已成功设置 Twitter 连接器作业"。</span><span class="sxs-lookup"><span data-stu-id="fe908-203">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="fe908-204">单击 "**继续**" 以完成 Twitter 连接器的设置。</span><span class="sxs-lookup"><span data-stu-id="fe908-204">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="fe908-205">在 "**设置筛选器**" 页上，您可以将筛选器应用于最初导入特定年龄的项目。</span><span class="sxs-lookup"><span data-stu-id="fe908-205">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="fe908-206">选择年龄，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-206">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="fe908-207">在 "**选择存储位置**" 页上，键入要将 Twitter 项目导入到其中的 Microsoft 365 邮箱的电子邮件地址，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe908-207">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="fe908-208">在 "**提供管理员同意**" 中，单击 "**提供许可**"，然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="fe908-208">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="fe908-209">您必须是全局管理员，才能同意 Office 365 导入服务以访问组织中的数据。</span><span class="sxs-lookup"><span data-stu-id="fe908-209">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="fe908-210">单击 "**下一步**" 查看连接器设置，然后单击 "**完成**" 以完成连接器设置。</span><span class="sxs-lookup"><span data-stu-id="fe908-210">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="fe908-211">在 "合规性中心" 中，转到 "**数据连接器**" 页，然后单击 "**连接器**" 选项卡以查看导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="fe908-211">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
