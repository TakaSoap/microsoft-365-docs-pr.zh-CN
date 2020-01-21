---
title: 设置连接器以存档 Twitter 数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将 Twitter 数据导入 Office 365。 这使您可以在 Office 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据的管理。
ms.openlocfilehash: 083c293e869cb35b428592717b7cf3810e7fea8c
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247555"
---
# <a name="set-up-a-connector-to-archive-twitter-data"></a><span data-ttu-id="17193-104">设置连接器以存档 Twitter 数据</span><span class="sxs-lookup"><span data-stu-id="17193-104">Set up a connector to archive Twitter data</span></span>

<span data-ttu-id="17193-105">使用 Office 365 中安全 & 合规中心中的连接器从 Twitter 导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="17193-105">Use a connector in the Security & Compliance Center in Office 365 to import and archive data from Twitter.</span></span> <span data-ttu-id="17193-106">在设置和配置连接器后，它会连接到您的组织的 Twitter 帐户（根据计划），将项目的内容转换为电子邮件格式，然后将这些项目导入到 Office 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="17193-106">After you set up and configure a connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="17193-107">在导入 Twitter 数据之后，您可以将 Office 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Office 365 保留策略）应用到邮箱中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="17193-107">After Twitter data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Office 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="17193-108">例如，您可以使用内容搜索来搜索 Twitter 数据，或将与数据存储在一起的邮箱与高级电子数据展示事例中的保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="17193-108">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="17193-109">使用连接器在 Office 365 中导入和存档 Twitter 数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="17193-109">Using a connector to import and archive Twitter data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="17193-110">为 Twitter 设置连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="17193-110">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="17193-111">先完成以下先决条件，然后才能在安全 & 合规中心中设置和配置连接器，以便从组织的 Twitter 帐户导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="17193-111">Complete the following prerequisites before you can set up and configure a connector in the Security & Compliance Center to import and archive data from your organization's Twitter account.</span></span> 

- <span data-ttu-id="17193-112">您的组织需要 Twitter 帐户;设置连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="17193-112">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="17193-113">您的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="17193-113">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="17193-114">如果你没有现有的 Azure 订阅，你可以注册以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="17193-114">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="17193-115">注册免费的一年 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="17193-115">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="17193-116">注册 "转到即点即用 Azure 订阅"</span><span class="sxs-lookup"><span data-stu-id="17193-116">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="17193-117">Office 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全 & 合规中心中的连接器。</span><span class="sxs-lookup"><span data-stu-id="17193-117">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="17193-118">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="17193-118">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="17193-119">若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全局管理员的凭据登录，然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="17193-119">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="17193-120">在安全 & 合规性（步骤7）中设置自定义连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="17193-120">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="17193-121">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="17193-121">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="17193-122">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="17193-122">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="17193-123">或者，您可以创建新的角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="17193-123">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="17193-124">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="17193-124">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="17193-125">步骤1：从 GitHub 下载预建的连接器应用程序包</span><span class="sxs-lookup"><span data-stu-id="17193-125">Step 1: Download the pre-built connector app package from GitHub</span></span>

<span data-ttu-id="17193-126">第一步是下载将使用 Twitter API 连接到 Twitter 帐户并提取数据以便可以将其导入 Office 365 的 Twitter 连接器应用的源代码。</span><span class="sxs-lookup"><span data-stu-id="17193-126">The first step is to download the source code for the Twitter connector app that will use a Twitter API to connect to your Twitter account and extract data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="17193-127">转到[此 GitHub 网站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)。</span><span class="sxs-lookup"><span data-stu-id="17193-127">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="17193-128">在最新版本下，选择 " **SampleConnector** " 文件。</span><span class="sxs-lookup"><span data-stu-id="17193-128">Under the latest release, select the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="17193-129">将 ZIP 文件保存到本地计算机上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="17193-129">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="17193-130">您在步骤4中将此 zip 文件上传到 Azure。</span><span class="sxs-lookup"><span data-stu-id="17193-130">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="17193-131">步骤2：在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="17193-131">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="17193-132">下一步是在 Azure Active Directory （AAD）中注册新应用程序。</span><span class="sxs-lookup"><span data-stu-id="17193-132">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="17193-133">此应用程序与您在您在 Twitter 连接器的步骤4中实现的 web 应用程序资源相对应。</span><span class="sxs-lookup"><span data-stu-id="17193-133">This app corresponds to the web app resource that you implement in Step 4 for the Twitter connector.</span></span> 

<span data-ttu-id="17193-134">有关分步说明，请参阅["步骤2：在 Azure Active Directory 中创建应用程序](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)"。</span><span class="sxs-lookup"><span data-stu-id="17193-134">For step-by-step instructions, see [Step 2: Create an app in Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="17193-135">在完成此步骤（按照分步说明操作）后，您将把以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="17193-135">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="17193-136">这些值将在部署过程的后续步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="17193-136">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="17193-137">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="17193-137">AAD application ID</span></span>
- <span data-ttu-id="17193-138">AAD 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="17193-138">AAD application secret</span></span>
- <span data-ttu-id="17193-139">AAD 应用程序 Uri</span><span class="sxs-lookup"><span data-stu-id="17193-139">AAD application Uri</span></span>
- <span data-ttu-id="17193-140">租户 Id</span><span class="sxs-lookup"><span data-stu-id="17193-140">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="17193-141">步骤3：创建 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="17193-141">Step 3: Create an Azure Storage account</span></span>

<span data-ttu-id="17193-142">您为组织部署的 Twitter 连接器将这些项目从 Twitter 上载到您在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="17193-142">The Twitter connector that you deploy for your organization uploads the items from Twitter to the Azure Storage location that you create in this step.</span></span> <span data-ttu-id="17193-143">在安全 & 合规中心（步骤7）中创建自定义连接器后，Office 365 导入服务会将 Twitter 数据从 Azure 存储位置复制到 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="17193-143">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="17193-144">如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-twitter)" 部分中所述，您必须具有有效的 azure 订阅才能创建 azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="17193-144">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="17193-145">有关分步说明，请参阅[第3步：创建 Azure 存储帐户](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="17193-145">For step-by-step instructions, see [Step 3: Create an Azure Storage account](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="17193-146">在完成此步骤（按照分步说明操作）后，将保存生成的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="17193-146">During the completion of this step (by following the step-by-step instructions), you save the connection string Uri that is generated.</span></span> <span data-ttu-id="17193-147">在第4步中在 Azure 中创建 web 应用资源时，可以使用此字符串。</span><span class="sxs-lookup"><span data-stu-id="17193-147">You use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="17193-148">步骤4：在 Azure 中创建 web 应用资源</span><span class="sxs-lookup"><span data-stu-id="17193-148">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="17193-149">下一步是在 Azure 中为 Twitter 连接器创建 web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="17193-149">The next step is to create a web app resource in Azure for the Twitter connector.</span></span> 

<span data-ttu-id="17193-150">有关分步说明，请参阅[第4步：在 Azure 中创建新的 web 应用资源](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)。</span><span class="sxs-lookup"><span data-stu-id="17193-150">For step-by-step instructions, see [Step 4: Create a new web app resource in Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="17193-151">在完成此步骤（按照分步说明操作）后，您将在创建 web 应用资源时提供以下信息（在完成前面的步骤之后，您已将其复制到文本文件中）。</span><span class="sxs-lookup"><span data-stu-id="17193-151">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="17193-152">APISecretKey –您在完成此步骤的过程中创建此密码;它在步骤7中使用。</span><span class="sxs-lookup"><span data-stu-id="17193-152">APISecretKey – You create this secret during the completion of this step; it's used in Step 7.</span></span>
- <span data-ttu-id="17193-153">StorageAccountConnectionString –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="17193-153">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure Storage account in Step 3.</span></span>
- <span data-ttu-id="17193-154">tenantId –在步骤2中创建 Azure Active Directory 中的 Twitter 连接器应用之后复制的 Office 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="17193-154">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="17193-155">此外，您还可以在此步骤中上载在第1步中下载的 SampleConnector 文件，以部署 Twitter 连接器应用的源代码。</span><span class="sxs-lookup"><span data-stu-id="17193-155">Also, you upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Twitter connector app.</span></span>

<span data-ttu-id="17193-156">完成此步骤后，请务必复制 Azure 应用服务 URL （例如， `https://twitterconnector.azurewebsites.net`）。</span><span class="sxs-lookup"><span data-stu-id="17193-156">After completing this step, be sure to copy the Azure app service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="17193-157">您需要使用此 URL 来完成步骤5、步骤6和步骤7。</span><span class="sxs-lookup"><span data-stu-id="17193-157">You need to use this URL to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-create-developer-app-on-twitter"></a><span data-ttu-id="17193-158">步骤5：在 Twitter 上创建开发人员应用</span><span class="sxs-lookup"><span data-stu-id="17193-158">Step 5: Create developer app on Twitter</span></span>

<span data-ttu-id="17193-159">下一步是在 Twitter 上创建和配置开发人员应用程序。</span><span class="sxs-lookup"><span data-stu-id="17193-159">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="17193-160">您在步骤7中创建的自定义连接器使用 Twitter 应用与 Twitter API 进行交互，以从组织的 Twitter 帐户中获取数据。</span><span class="sxs-lookup"><span data-stu-id="17193-160">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="17193-161">有关分步说明，请参阅[第5步：创建 Twitter 应用](deploy-twitter-connector.md#step-5-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="17193-161">For step-by-step instructions, see [Step 5: Create the Twitter app](deploy-twitter-connector.md#step-5-create-the-twitter-app).</span></span>

<span data-ttu-id="17193-162">在完成此步骤（按照分步说明操作）后，将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="17193-162">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="17193-163">这些值将用于在步骤6中配置 Twitter 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="17193-163">These values will be used to configure the Twitter connector app in Step 6.</span></span>

- <span data-ttu-id="17193-164">Twitter API 密钥</span><span class="sxs-lookup"><span data-stu-id="17193-164">Twitter API Key</span></span>
- <span data-ttu-id="17193-165">Twitter API 密钥</span><span class="sxs-lookup"><span data-stu-id="17193-165">Twitter API Secret Key</span></span>
- <span data-ttu-id="17193-166">Twitter 访问令牌</span><span class="sxs-lookup"><span data-stu-id="17193-166">Twitter Access Token</span></span>
- <span data-ttu-id="17193-167">Twitter 访问令牌机密</span><span class="sxs-lookup"><span data-stu-id="17193-167">Twitter Access Token Secret</span></span>

## <a name="step-6-configure-the-twitter-connector-app"></a><span data-ttu-id="17193-168">步骤6：配置 Twitter 连接器应用</span><span class="sxs-lookup"><span data-stu-id="17193-168">Step 6: Configure the Twitter connector app</span></span>

<span data-ttu-id="17193-169">下一步是将配置设置添加到在步骤4中创建 Azure web 应用资源时上载的 Twitter 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="17193-169">The next step is to add configurations settings to the Twitter connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="17193-170">为此，请转到连接器应用的主页并配置该页面。</span><span class="sxs-lookup"><span data-stu-id="17193-170">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="17193-171">有关分步说明，请参阅 "[步骤6：配置连接器 web 应用程序"](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="17193-171">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="17193-172">在完成此步骤（按照分步说明操作）后，您将提供以下信息（在完成上述步骤后，您已将其复制到文本文件中）：</span><span class="sxs-lookup"><span data-stu-id="17193-172">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="17193-173">Twitter API 密钥（在步骤5中获取）</span><span class="sxs-lookup"><span data-stu-id="17193-173">Twitter API Key (obtained in Step 5)</span></span>
- <span data-ttu-id="17193-174">Twitter API 密钥（在步骤5中获取）</span><span class="sxs-lookup"><span data-stu-id="17193-174">Twitter API Secret Key (obtained in Step 5)</span></span>
- <span data-ttu-id="17193-175">Twitter 访问令牌（在步骤5中获取）</span><span class="sxs-lookup"><span data-stu-id="17193-175">Twitter Access Token (obtained in Step 5)</span></span>
- <span data-ttu-id="17193-176">Twitter 访问令牌机密（在步骤5中获取）</span><span class="sxs-lookup"><span data-stu-id="17193-176">Twitter Access Token Secret (obtained in Step 5)</span></span>
- <span data-ttu-id="17193-177">Azure Active Directory 应用程序 ID （在步骤2中获取的 AAD 应用程序 ID）</span><span class="sxs-lookup"><span data-stu-id="17193-177">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="17193-178">Azure Active Directory 应用程序密码（在步骤2中获取的 AAD 应用程序密码）</span><span class="sxs-lookup"><span data-stu-id="17193-178">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="17193-179">Azure Active Directory 应用程序 Uri （在步骤2中获取的 AAD 应用程序 Uri; 例如，`https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)`</span><span class="sxs-lookup"><span data-stu-id="17193-179">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)`</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="17193-180">步骤7：在安全 & 合规性中心中设置自定义连接器</span><span class="sxs-lookup"><span data-stu-id="17193-180">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="17193-181">最后一步是在安全 & 合规性中心中设置自定义连接器，以将组织的 Twitter 帐户中的数据导入 Office 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="17193-181">The final step is to set up the custom connector in the Security & Compliance Center that imports data from your organization's Twitter account to a specified mailbox in Office 365.</span></span> <span data-ttu-id="17193-182">成功完成此步骤后，Office 365 导入服务将开始从 Twitter 向 Office 365 导入数据。</span><span class="sxs-lookup"><span data-stu-id="17193-182">After you successfully complete this step, the Office 365 Import service will start importing data from Twitter to Office 365.</span></span> 

<span data-ttu-id="17193-183">有关分步说明，请参阅[第7步：在安全与合规中心中设置自定义连接器](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="17193-183">For step-by-step instructions, see [Step 7: Set up a custom connector in the security and compliance center](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center).</span></span> 

<span data-ttu-id="17193-184">在完成此步骤（按照分步说明操作）后，您将提供以下信息（在完成这些步骤后，您已将其复制到文本文件中）。</span><span class="sxs-lookup"><span data-stu-id="17193-184">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="17193-185">Azure 应用服务 URL （在步骤4中获取; 例如， `https://twitterconnector.azurewebsites.net`）</span><span class="sxs-lookup"><span data-stu-id="17193-185">Azure app service URL (obtained in Step 4; for example, `https://twitterconnector.azurewebsites.net`)</span></span>
- <span data-ttu-id="17193-186">APISecretKey （您在步骤4中创建）</span><span class="sxs-lookup"><span data-stu-id="17193-186">APISecretKey (that you created in Step 4)</span></span>
