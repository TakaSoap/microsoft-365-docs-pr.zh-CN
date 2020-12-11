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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置本机连接器，将 Twitter 数据导入和存档到 Microsoft 365。 在将数据导入到 Microsoft 365 后，可以使用合规性功能（如法定保留、内容搜索和保留策略）来管理组织的 Twitter 数据的管理。
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619908"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="8476b-104">部署连接器以存档 Twitter 数据</span><span class="sxs-lookup"><span data-stu-id="8476b-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="8476b-105">本文包含部署连接器的分步过程，该连接器使用 Office 365 导入服务将数据从组织的 Twitter 帐户导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8476b-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="8476b-106">有关此过程的简要概述和部署 Twitter 连接器所需的先决条件列表，请参阅"设置连接器以存档[Twitter 数据"。 ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="8476b-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="8476b-107">步骤 1：在 Azure Active Directory 中创建应用</span><span class="sxs-lookup"><span data-stu-id="8476b-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="8476b-108">转到 <https://portal.azure.com> 全局管理员帐户的凭据并登录。</span><span class="sxs-lookup"><span data-stu-id="8476b-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![登录到 Azure](../media/TCimage01.png)

2. <span data-ttu-id="8476b-110">在左侧导航窗格中，单击 **Azure Active Directory。**</span><span class="sxs-lookup"><span data-stu-id="8476b-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![转到 Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="8476b-112">在左侧导航窗格中，单击"预览 (应用) ，然后单击 **"新建\*\*\*\*注册"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![创建新的应用注册](../media/TCimage03.png)

4. <span data-ttu-id="8476b-114">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="8476b-114">Register the application.</span></span> <span data-ttu-id="8476b-115">在 **重定向 URI (可选**) ，在应用程序类型下拉列表中选择 **Web，** 然后在框中键入 `https://portal.azure.com` URI。</span><span class="sxs-lookup"><span data-stu-id="8476b-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="8476b-116">重定向 https://portal.azure.com URI 的类型</span><span class="sxs-lookup"><span data-stu-id="8476b-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="8476b-117">将 **应用程序 (客户端**) ID 和目录 (租户) **ID，** 并将其保存到文本文件或其他安全位置。</span><span class="sxs-lookup"><span data-stu-id="8476b-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="8476b-118">在稍后的步骤中使用这些 ID。</span><span class="sxs-lookup"><span data-stu-id="8476b-118">You use these IDs in later steps.</span></span>

    ![复制并保存应用程序 ID 和目录 ID](../media/TCimage05.png)

6. <span data-ttu-id="8476b-120">转到"**证书&** 新应用密码"，在"客户端密码"**下单击\*\*\*\*"新建客户端密码"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![创建新的客户端密码](../media/TCimage06.png)

7. <span data-ttu-id="8476b-122">创建新密码。</span><span class="sxs-lookup"><span data-stu-id="8476b-122">Create a new secret.</span></span> <span data-ttu-id="8476b-123">在描述框中，键入密码，然后选择过期期限。</span><span class="sxs-lookup"><span data-stu-id="8476b-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![键入密码并选择过期期限](../media/TCimage08.png)

8. <span data-ttu-id="8476b-125">复制密码的值并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8476b-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="8476b-126">这是在稍后步骤中使用的 AAD 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="8476b-126">This is the AAD application secret that you use in later steps.</span></span>

   ![复制并保存密码](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="8476b-128">步骤 2：将连接器 Web 服务从 GitHub 部署到 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="8476b-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="8476b-129">转到此 [GitHub 网站，然后单击](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)**"部署到 Azure"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![转到 Azure 主页](../media/FBCimage11.png)

2. <span data-ttu-id="8476b-131">单击" **部署到 Azure"** 后，将重定向到具有自定义模板页的 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="8476b-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="8476b-132">填写"**基础知识"和**"**设置"** 详细信息，然后单击"购买 **"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![单击"创建资源和类型存储帐户"](../media/FBCimage12.png)

    - <span data-ttu-id="8476b-134">**订阅：** 选择要将 Twitter 连接器 Web 服务部署到的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8476b-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="8476b-135">**资源组：** 选择或创建新的资源组。</span><span class="sxs-lookup"><span data-stu-id="8476b-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="8476b-136">资源组是一个容器，用于保存 Azure 解决方案的相关资源。</span><span class="sxs-lookup"><span data-stu-id="8476b-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="8476b-137">**位置：** 选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="8476b-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="8476b-138">**Web 应用名称：** 为连接器 Web 应用提供唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="8476b-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="8476b-139">第 th 个名称的长度必须介于 3 到 18 个字符之间。</span><span class="sxs-lookup"><span data-stu-id="8476b-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="8476b-140">此名称用于创建 Azure 应用服务 URL;例如，如果你提供 **twitterconnector** 的 Web 应用名称，则 Azure 应用服务 URL **将** twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="8476b-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="8476b-141">**tenantId：** 在步骤 1 中的 Azure Active Directory 中创建 Facebook 连接器应用后复制的 Microsoft 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="8476b-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="8476b-142">**APISecretKey：** 你可以键入任何值作为密码。</span><span class="sxs-lookup"><span data-stu-id="8476b-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="8476b-143">这用于访问步骤 5 中的连接器 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="8476b-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="8476b-144">部署成功后，页面将类似于以下屏幕截图：</span><span class="sxs-lookup"><span data-stu-id="8476b-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![单击"存储"，然后单击"存储"帐户](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="8476b-146">步骤 3：创建 Twitter 应用</span><span class="sxs-lookup"><span data-stu-id="8476b-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="8476b-147">转到，使用您组织的开发人员帐户的凭据登录， https://developer.twitter.com 然后单击"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![转到 https://developer.twitter.com 并登录](../media/TCimage25-5.png)
2. <span data-ttu-id="8476b-149">单击 **"创建应用"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-149">Click **Create an app**.</span></span>
   
   ![转到"应用"页以创建应用](../media/TCimage26.png)

3. <span data-ttu-id="8476b-151">在 **"应用详细信息**"下，添加有关应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="8476b-151">Under **App details**, add information about the application.</span></span>

   ![输入有关应用的信息](../media/TCimage27.png)

4. <span data-ttu-id="8476b-153">在 Twitter 开发人员仪表板上，选择你刚刚创建的应用，然后单击"详细信息 **"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![复制并保存应用 ID](../media/TCimage28.png)

5. <span data-ttu-id="8476b-155">在 **"密钥和令牌** "选项卡上的" **使用者 API** 密钥"下，复制 API 密钥和 API 密钥，并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8476b-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="8476b-156">然后单击 **"创建** "以生成访问令牌和访问令牌密码，然后将这些密码复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8476b-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![复制并保存到 API 密钥](../media/TCimage29.png)

   <span data-ttu-id="8476b-158">然后单击 **"创建** "以生成访问令牌和访问令牌密码，然后将这些密码复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="8476b-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="8476b-159">单击 **"权限"** 选项卡并配置权限，如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="8476b-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![配置权限](../media/TCimage30.png)

7. <span data-ttu-id="8476b-161">保存权限设置后，单击 **"应用** 详细信息"选项卡，然后单击"编辑> **编辑详细信息**。</span><span class="sxs-lookup"><span data-stu-id="8476b-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![编辑应用详细信息](../media/TCimage31.png)

8. <span data-ttu-id="8476b-163">执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8476b-163">Do the following tasks:</span></span>

   - <span data-ttu-id="8476b-164">选中复选框以允许连接器应用登录到 Twitter。</span><span class="sxs-lookup"><span data-stu-id="8476b-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="8476b-165">使用以下格式添加 OAuth 重定向 **Uri：/Views/TwitterOAuth， \<connectorserviceuri>** 其中 *connectorserviceuri* 的值为组织的 Azure 应用服务 URL;例如 https://twitterconnector.azurewebsites.net/Views/TwitterOAuth 。</span><span class="sxs-lookup"><span data-stu-id="8476b-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![允许连接器应用登录到 Twitter 并添加 OAuth 重定向 Uri](../media/TCimage32.png)

<span data-ttu-id="8476b-167">Twitter 开发人员应用现在可供使用。</span><span class="sxs-lookup"><span data-stu-id="8476b-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="8476b-168">步骤 4：配置连接器 Web 应用</span><span class="sxs-lookup"><span data-stu-id="8476b-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="8476b-169">转到 https:// \<AzureAppResourceName> .azurewebsites.net (，其中 **AzureAppResourceName** 是你在步骤 4 中指定的 Azure 应用资源) 。</span><span class="sxs-lookup"><span data-stu-id="8476b-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="8476b-170">例如，如果名称为 **twitterconnector，** 请转到 https://twitterconnector.azurewebsites.net 。</span><span class="sxs-lookup"><span data-stu-id="8476b-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="8476b-171">应用程序的主页类似于以下屏幕截图：</span><span class="sxs-lookup"><span data-stu-id="8476b-171">The home page of the app looks like the following screenshot:</span></span>

   ![转到 Azure 应用资源页面](../media/FBCimage41.png)

2. <span data-ttu-id="8476b-173">单击 **"** 配置"以显示登录页。</span><span class="sxs-lookup"><span data-stu-id="8476b-173">Click **Configure** to display a sign in page.</span></span>

   ![单击"配置"以显示登录页](../media/FBCimage42.png)

3. <span data-ttu-id="8476b-175">在"租户 ID"框中，键入或 (步骤 2 中获取的租户 ID) 。</span><span class="sxs-lookup"><span data-stu-id="8476b-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="8476b-176">在密码框中，键入或粘贴在步骤 2 (获取的 APISecretKey) ，然后单击"设置 **配置** 设置"以显示配置详细信息页。</span><span class="sxs-lookup"><span data-stu-id="8476b-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![使用租户 ID 和 API 密钥登录](../media/TCimage35.png)

4. <span data-ttu-id="8476b-178">输入以下配置设置</span><span class="sxs-lookup"><span data-stu-id="8476b-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="8476b-179">**Twitter Api 密钥：** 你在步骤 3 中创建的 Twitter 应用程序的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="8476b-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="8476b-180">**Twitter Api 密钥：** 你在步骤 3 中创建的 Twitter 应用程序的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="8476b-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="8476b-181">**Twitter 访问令牌：** 在步骤 3 中创建的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="8476b-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="8476b-182">**Twitter 访问令牌密码：** 在步骤 3 中创建的访问令牌密码。</span><span class="sxs-lookup"><span data-stu-id="8476b-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="8476b-183">**AAD 应用程序 ID：** 在步骤 1 中创建的 Azure Active Directory 应用的应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="8476b-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="8476b-184">**AAD 应用程序密码：** 在步骤 1 中创建的 APISecretKey 密码的值。</span><span class="sxs-lookup"><span data-stu-id="8476b-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="8476b-185">单击 **"** 保存"保存连接器设置。</span><span class="sxs-lookup"><span data-stu-id="8476b-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="8476b-186">步骤 5：在 Microsoft 365 合规中心中设置 Twitter 连接器</span><span class="sxs-lookup"><span data-stu-id="8476b-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="8476b-187">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航中 **，然后单击** "数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="8476b-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8476b-188">在"**数据连接器"** 页面上的 **Twitter** 下，单击"**查看"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="8476b-189">在 **Twitter 页面上**，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="8476b-190">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="8476b-191">在 **"为连接器应用程序添加** 凭据"页上，输入以下信息，然后单击"**验证连接"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![输入连接器应用凭据](../media/TCimage38.png)

    - <span data-ttu-id="8476b-193">在 **"名称** "框中，键入连接器的名称，例如 Twitter **帮助句柄**。</span><span class="sxs-lookup"><span data-stu-id="8476b-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="8476b-194">在" **连接器 URL"** 框中，键入或粘贴 Azure 应用服务 URL;例如 `https://twitterconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="8476b-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="8476b-195">在 **"密码** "框中，键入或粘贴在步骤 2 中创建的 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="8476b-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="8476b-196">在"Azure 应用 **ID"** 框中，键入或粘贴 Azure 应用程序应用程序 ID (也称为在步骤 1) 获取的客户端 *ID。*</span><span class="sxs-lookup"><span data-stu-id="8476b-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="8476b-197">成功验证连接后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="8476b-198">在"**授权 Microsoft 365 导入** 数据"页上，再次键入或粘贴 APISecretKey，然后单击"登录 **Web 应用"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="8476b-199">单击 **Twitter 登录**。</span><span class="sxs-lookup"><span data-stu-id="8476b-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="8476b-200">在 Twitter 登录页面上，使用组织的 Twitter 帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="8476b-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![登录 Twitter 帐户](../media/TCimage42.png)

   <span data-ttu-id="8476b-202">登录后，Twitter 页面将显示以下消息"Twitter 连接器作业设置成功"。</span><span class="sxs-lookup"><span data-stu-id="8476b-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="8476b-203">单击 **"** 继续"完成设置 Twitter 连接器。</span><span class="sxs-lookup"><span data-stu-id="8476b-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="8476b-204">在 **"设置筛选器** "页上，可以应用筛选器以初始导入具有特定年龄的项目。</span><span class="sxs-lookup"><span data-stu-id="8476b-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="8476b-205">选择一个年龄，然后单击"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="8476b-206">在 **"选择存储位置**"页上，键入 Twitter 项目将导入到的 Microsoft 365 邮箱的电子邮件地址，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="8476b-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="8476b-207">单击 **"** 下一步"查看连接器设置， **然后单击"** 完成"以完成连接器设置。</span><span class="sxs-lookup"><span data-stu-id="8476b-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="8476b-208">在合规中心，转到"数据连接器 **"页，** 然后单击"连接器 **"选项卡以查看** 导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="8476b-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
