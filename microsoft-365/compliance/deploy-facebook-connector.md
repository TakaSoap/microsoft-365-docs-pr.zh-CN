---
title: 部署连接器以存档 Facebook 商业页面数据
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
description: 管理员可以设置本机连接器以将 Facebook 商业页面导入和存档到 Microsoft 365。 将此数据导入 Microsoft 365 后，您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的 Facebook 数据的管理。
ms.openlocfilehash: 240ce3a90cf46a05ab5d6030b9318d42d23904d8
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434223"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="9b005-104">部署连接器以存档 Facebook 商业页面数据</span><span class="sxs-lookup"><span data-stu-id="9b005-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="9b005-105">本文包含了部署使用 Office 365 导入服务将数据从 Facebook 商业页面导入到 Microsoft 365 的连接器的分步过程。</span><span class="sxs-lookup"><span data-stu-id="9b005-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="9b005-106">有关此过程的简要概述以及部署 Facebook 连接器所需的先决条件列表，请参阅[Set up a connector to Archive facebook data](archive-facebook-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="9b005-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="9b005-107">步骤1：在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="9b005-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="9b005-108">转到 <https://portal.azure.com> 并使用全局管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="9b005-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![在 AAD 中创建应用程序](../media/FBCimage1.png)

2. <span data-ttu-id="9b005-110">在左侧导航窗格中，单击 " **Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![单击 "Azure Active Directory"](../media/FBCimage2.png)

3. <span data-ttu-id="9b005-112">在左侧导航窗格中，单击 "**应用程序注册（预览）** "，然后单击 "**新建注册**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![单击 "\* \* 应用注册（预览） \* \*"，然后单击 "新建注册 \* \*"](../media/FBCimage3.png)

4. <span data-ttu-id="9b005-114">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="9b005-114">Register the application.</span></span> <span data-ttu-id="9b005-115">在 "重定向 URI" 下，选择 "应用程序类型" 下拉列表中的 "Web"，然后 <https://portal.azure.com> 为 URI 键入相应的框。</span><span class="sxs-lookup"><span data-stu-id="9b005-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![注册应用程序](../media/FBCimage4.png)

5. <span data-ttu-id="9b005-117">复制**应用程序（客户端） id**和**目录（租户） id** ，并将其保存到文本文件或其他安全位置。</span><span class="sxs-lookup"><span data-stu-id="9b005-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="9b005-118">可在后续步骤中使用这些 Id。</span><span class="sxs-lookup"><span data-stu-id="9b005-118">You use these IDs in later steps.</span></span>

   ![复制应用程序 ID 和目录 ID 并将其保存](../media/FBCimage5.png)

6. <span data-ttu-id="9b005-120">转到**证书 & 新应用程序的密码。**</span><span class="sxs-lookup"><span data-stu-id="9b005-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![转到证书 & 新应用程序的密码](../media/FBCimage6.png)

7. <span data-ttu-id="9b005-122">单击 "**新建客户端密码**"</span><span class="sxs-lookup"><span data-stu-id="9b005-122">Click **New client secret**</span></span>

   ![单击 "新建客户端密码"](../media/FBCimage7.png)

8. <span data-ttu-id="9b005-124">创建新的机密。</span><span class="sxs-lookup"><span data-stu-id="9b005-124">Create a new secret.</span></span> <span data-ttu-id="9b005-125">在 "说明" 框中，键入密码，然后选择一个过期时间段。</span><span class="sxs-lookup"><span data-stu-id="9b005-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![键入密码，然后选择一个过期期限](../media/FBCimage8.png)

9. <span data-ttu-id="9b005-127">复制密码的值，并将其保存到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="9b005-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="9b005-128">这是您在后续步骤中使用的 AAD 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="9b005-128">This is the AAD application secret that you use in later steps.</span></span>

   ![复制密码的值并将其保存](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="9b005-130">步骤2：将来自 GitHub 的连接器 web 服务部署到你的 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="9b005-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="9b005-131">转到[此 GitHub 网站](https://github.com/microsoft/m365-sample-connector-csharp-aspnet)，然后单击 "**部署到 Azure**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![单击 "部署到 Azure"](../media/FBCGithubApp.png)

2. <span data-ttu-id="9b005-133">单击 "**部署到 Azure**" 后，您将被重定向到具有自定义模板页面的 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="9b005-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="9b005-134">填写 "**基础知识**" 和 "**设置**详细信息"，然后单击 "**购买**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="9b005-135">**订阅：** 选择要将 Facebook 商业页面连接器 web 服务部署到的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="9b005-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="9b005-136">**资源组：** 选择或创建新的资源组。</span><span class="sxs-lookup"><span data-stu-id="9b005-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="9b005-137">资源组是保留 Azure 解决方案的相关资源的容器。</span><span class="sxs-lookup"><span data-stu-id="9b005-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="9b005-138">**位置：** 选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="9b005-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="9b005-139">**Web 应用名称：** 为连接器 web 应用提供一个唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="9b005-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="9b005-140">Th 名称的长度必须介于3到18个字符之间。</span><span class="sxs-lookup"><span data-stu-id="9b005-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="9b005-141">此名称用于创建 Azure 应用服务 URL;例如，如果提供 Web 应用程序名称**fbconnector** ，则 Azure 应用服务 URL 将为**fbconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="9b005-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="9b005-142">**tenantId：** 在步骤1中创建 Azure Active Directory 中的 Facebook 连接器应用之后复制的 Microsoft 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="9b005-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="9b005-143">**APISecretKey：** 您可以键入任何值作为密码。</span><span class="sxs-lookup"><span data-stu-id="9b005-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="9b005-144">这用于在步骤5中访问连接器 web 应用。</span><span class="sxs-lookup"><span data-stu-id="9b005-144">This is used to access the connector web app in Step 5.</span></span>

     ![单击 "创建资源并键入存储帐户"](../media/FBCimage12.png)

3. <span data-ttu-id="9b005-146">部署成功后，页面外观将类似于以下屏幕截图：</span><span class="sxs-lookup"><span data-stu-id="9b005-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![单击 "存储"，然后单击 "存储帐户"](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="9b005-148">步骤3：注册 Facebook 应用程序</span><span class="sxs-lookup"><span data-stu-id="9b005-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="9b005-149">转到 <https://developers.facebook.com> ，使用组织的 Facebook 商业版页面的帐户登录，然后单击 "**添加新应用**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![为 Facebook 商业页面添加新的应用程序](../media/FBCimage25.png)

2. <span data-ttu-id="9b005-151">创建新的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="9b005-151">Create a new app ID.</span></span>

   ![创建新的应用程序 ID](../media/FBCimage26.png)

3. <span data-ttu-id="9b005-153">在左侧导航窗格中，单击 "**添加产品**"，然后单击 " **Facebook 登录**磁贴" 中的 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![单击 "添加产品"](../media/FBCimage27.png)

4. <span data-ttu-id="9b005-155">在 "集成 Facebook 登录" 页上，单击 " **Web**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![在 "集成 Facebook 登录" 页上单击 "Web"](../media/FBCimage28.png)

5. <span data-ttu-id="9b005-157">添加 Azure 应用服务 URL;例如 `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="9b005-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![添加 Azure 应用服务 URL](../media/FBCimage29.png)

6. <span data-ttu-id="9b005-159">完成 Facebook 登录设置的快速入门部分。</span><span class="sxs-lookup"><span data-stu-id="9b005-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![完成快速入门部分](../media/FBCimage30.png)

7. <span data-ttu-id="9b005-161">在 " **Facebook Login**" 下的左侧导航窗格中，单击 "**设置**"，然后在 "**有效 OAuth 重定向 Uri** " 框中添加 OAuth 重定向 uri。</span><span class="sxs-lookup"><span data-stu-id="9b005-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="9b005-162">使用格式\*\* \<connectorserviceuri> /Views/FacebookOAuth\*\*，其中 connectorserviceuri 的值是您的组织的 AZURE 应用服务 URL; 例如， `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="9b005-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![将 OAuth 重定向 URI 添加到 "有效 OAuth 重定向 Uri" 框](../media/FBCimage31.png)

8. <span data-ttu-id="9b005-164">在左侧导航窗格中，单击 "**添加产品**"，然后单击 " **webhook"。**</span><span class="sxs-lookup"><span data-stu-id="9b005-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="9b005-165">在 "**页面**" 下拉菜单中，单击 "**页面**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![单击 "添加产品"，然后单击 "\* \* Webhook](../media/FBCimage32.png)

9. <span data-ttu-id="9b005-167">添加 Webhook 回调 URL 并添加验证令牌。</span><span class="sxs-lookup"><span data-stu-id="9b005-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="9b005-168">回调 URL 的格式，使用格式\*\* <connectorserviceuri> /api/FbPageWebhook\*\*，其中 connectorserviceuri 的值是您的组织的 AZURE 应用服务 URL; 例如 `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="9b005-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="9b005-169">验证令牌应类似于强密码。</span><span class="sxs-lookup"><span data-stu-id="9b005-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="9b005-170">将验证令牌复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="9b005-170">Copy the verify token to a text file or other storage location.</span></span>

   ![添加验证令牌](../media/FBCimage33.png)

10. <span data-ttu-id="9b005-172">测试并订阅源终结点。</span><span class="sxs-lookup"><span data-stu-id="9b005-172">Test and subscribe to the endpoint for feed.</span></span>

    ![测试并订阅终结点](../media/FBCimage34.png)

11. <span data-ttu-id="9b005-174">添加隐私 URL、应用程序图标和业务使用。</span><span class="sxs-lookup"><span data-stu-id="9b005-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="9b005-175">此外，将应用程序 ID 和应用程序密码复制到文本文件或其他存储位置。</span><span class="sxs-lookup"><span data-stu-id="9b005-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![添加隐私 URL、应用程序图标和业务使用](../media/FBCimage35.png)

12. <span data-ttu-id="9b005-177">将应用程序公开。</span><span class="sxs-lookup"><span data-stu-id="9b005-177">Make the app public.</span></span>

    ![将应用程序设为公共](../media/FBCimage36.png)

13. <span data-ttu-id="9b005-179">将用户添加到 "管理员" 或 "测试人员" 角色。</span><span class="sxs-lookup"><span data-stu-id="9b005-179">Add user to the admin or tester role.</span></span>

    ![将用户添加到 "管理员" 或 "测试人员" 角色](../media/FBCimage37.png)

14. <span data-ttu-id="9b005-181">添加**页面公共内容访问**权限。</span><span class="sxs-lookup"><span data-stu-id="9b005-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd 页面公共内容访问权限](../media/FBCimage38.png)

15. <span data-ttu-id="9b005-183">添加 "管理页面" 权限。</span><span class="sxs-lookup"><span data-stu-id="9b005-183">Add Manage Pages permission.</span></span>

    ![添加管理页面权限](../media/FBCimage39.png)

16. <span data-ttu-id="9b005-185">获取由 Facebook 审阅的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9b005-185">Get the application reviewed by Facebook.</span></span>

    ![获取由 Facebook 审查的应用程序](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="9b005-187">步骤4：配置连接器 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="9b005-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="9b005-188">转到 `https://<AzureAppResourceName>.azurewebsites.net` （其中，AzureAppResourceName 是您在步骤4中命名的 Azure 应用程序资源的名称）。</span><span class="sxs-lookup"><span data-stu-id="9b005-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="9b005-189">例如，如果名称为**fbconnector**，请转到 `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="9b005-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="9b005-190">该应用程序的主页看起来将类似于以下屏幕截图：</span><span class="sxs-lookup"><span data-stu-id="9b005-190">The home page of the app will look like the following screenshot:</span></span>

   ![转到你的连接器 web 应用](../media/FBCimage41.png)

2. <span data-ttu-id="9b005-192">单击 "**配置**" 以显示登录页。</span><span class="sxs-lookup"><span data-stu-id="9b005-192">Click **Configure** to display a sign in page.</span></span>

   ![单击 "配置" 以显示登录页](../media/FBCimage42.png)

3. <span data-ttu-id="9b005-194">在 "租户 Id" 框中，键入或粘贴您在步骤2中获取的租户 Id。</span><span class="sxs-lookup"><span data-stu-id="9b005-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="9b005-195">在 "密码" 框中，键入或粘贴 APISecretKey （您在步骤2中获取），然后单击 "**设置配置设置**" 以显示 "配置详细信息" 页。</span><span class="sxs-lookup"><span data-stu-id="9b005-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![使用租户 Id 和密码登录并转到 "配置详细信息" 页](../media/FBCimage43.png)

4. <span data-ttu-id="9b005-197">输入以下配置设置</span><span class="sxs-lookup"><span data-stu-id="9b005-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="9b005-198">**Facebook 应用程序 ID：** 您在步骤3中获取的 Facebook 应用程序的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="9b005-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="9b005-199">**Facebook 应用程序密码：** 您在步骤3中获取的 Facebook 应用程序的应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="9b005-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="9b005-200">**Facebook webhook 验证令牌：** 您在步骤3中创建的验证令牌。</span><span class="sxs-lookup"><span data-stu-id="9b005-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="9b005-201">**AAD 应用程序 ID：** 您在步骤1中创建的 Azure Active Directory 应用程序的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="9b005-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="9b005-202">**AAD 应用程序密码：** 您在步骤1中创建的 APISecretKey 密码的值。</span><span class="sxs-lookup"><span data-stu-id="9b005-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="9b005-203">单击 "**保存**" 以保存连接器设置。</span><span class="sxs-lookup"><span data-stu-id="9b005-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="9b005-204">步骤5：在 Microsoft 365 合规性中心中设置 Facebook 连接器</span><span class="sxs-lookup"><span data-stu-id="9b005-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="9b005-205">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后单击左侧导航中的 "**数据连接器**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9b005-206">在 " **Facebook 商业页面**" 下的 "**数据连接器（预览）** " 页上，单击 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-206">On the **Data connectors (preview)** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="9b005-207">在 " **Facebook 商业页面**" 页面上，单击 "**添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="9b005-208">在 "**服务条款**" 页上，单击 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="9b005-209">在 "**为连接器应用添加凭据**" 页上，输入以下信息，然后单击 "**验证连接**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![输入连接器应用凭据](../media/TCimage38.png)

   - <span data-ttu-id="9b005-211">在 "**名称**" 框中，键入连接器的名称，例如 " **Facebook 新闻" 页面**。</span><span class="sxs-lookup"><span data-stu-id="9b005-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="9b005-212">在 "**连接 URL** " 框中，键入或粘贴 Azure 应用服务 URL;例如 `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="9b005-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="9b005-213">在 "**密码**" 框中，键入或粘贴您在步骤2中添加的 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="9b005-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="9b005-214">在 " **Azure 应用 ID** " 框中，键入或粘贴应用程序（客户端） id 的值也称为您在步骤1中创建的 AAD 应用程序 id。</span><span class="sxs-lookup"><span data-stu-id="9b005-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="9b005-215">成功验证连接后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="9b005-216">在 "**授权 Microsoft 365 导入数据**" 页上，再次键入或粘贴 APISecretKey，然后单击 "**登录 web 应用**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="9b005-217">在 "**配置 Facebook 连接器应用程序**" 页上，单击 "**使用 facebook 登录**"，然后使用组织的 Facebook 商业版页面帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="9b005-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="9b005-218">确保您登录到的 Facebook 帐户已分配给您组织的 Facebook 商业页面的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="9b005-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![使用 Facebook 登录](../media/FBCimage50.png)

9. <span data-ttu-id="9b005-220">将显示您登录到的 Facebook 帐户所管理的商业页面的列表。</span><span class="sxs-lookup"><span data-stu-id="9b005-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="9b005-221">选择要存档的页面，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-221">Select the page to archive and then click **Next**.</span></span>

   ![选择要存档的组织业务页面](../media/FBCimage52.png)

10. <span data-ttu-id="9b005-223">单击 "**继续**" 退出连接器服务应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="9b005-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="9b005-224">在 "**设置筛选器**" 页上，您可以将筛选器应用于最初导入特定年龄的项目。</span><span class="sxs-lookup"><span data-stu-id="9b005-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="9b005-225">选择年龄，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="9b005-226">在 "**选择存储位置**" 页上，键入将向其导入 Facebook 项的 Microsoft 365 邮箱的电子邮件地址，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9b005-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="9b005-227">在 "**提供管理员同意**" 中，单击 "**提供许可**"，然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="9b005-227">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="9b005-228">您必须是全局管理员，才能同意 Office 365 导入服务以访问组织中的数据。</span><span class="sxs-lookup"><span data-stu-id="9b005-228">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="9b005-229">单击 "**下一步**" 查看连接器设置，然后单击 "**完成**" 以完成连接器设置。</span><span class="sxs-lookup"><span data-stu-id="9b005-229">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="9b005-230">在 "合规性中心" 中，转到 "**数据连接器**" 页，然后单击 "**连接器**" 选项卡以查看导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="9b005-230">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
