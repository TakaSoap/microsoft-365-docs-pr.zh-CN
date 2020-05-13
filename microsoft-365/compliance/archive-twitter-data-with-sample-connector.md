---
title: 设置连接器以存档 Twitter 数据
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
ms.custom:
- seo-marvel-apr2020
description: 设置连接器以将 Twitter 数据导入 Microsoft 365，以便您可以使用合规性功能，如合法保留、内容搜索和保留策略。
ms.openlocfilehash: efc02dcf7b9c40fafedf230e4786f6f6494c27d6
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210578"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a><span data-ttu-id="e0892-103">设置连接器以存档 Twitter 数据（预览）</span><span class="sxs-lookup"><span data-stu-id="e0892-103">Set up a connector to archive Twitter data (preview)</span></span>

<span data-ttu-id="e0892-104">使用 Microsoft 365 合规性中心中的连接器将来自 Twitter 的数据导入和存档到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e0892-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Twitter to Microsoft 365.</span></span> <span data-ttu-id="e0892-105">设置和配置连接器后，它会连接到您的组织的 Twitter 帐户（定期），将项目的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e0892-105">After you set up and configure the connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="e0892-106">导入 Twitter 数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核和 Microsoft 365 保留策略）应用到 Twitter 数据。</span><span class="sxs-lookup"><span data-stu-id="e0892-106">After the Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to the Twitter data.</span></span> <span data-ttu-id="e0892-107">例如，如果将邮箱置于诉讼保留状态或分配到保留策略，则会保留 Twitter 数据。</span><span class="sxs-lookup"><span data-stu-id="e0892-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Twitter data is preserved.</span></span> <span data-ttu-id="e0892-108">您可以使用内容搜索来搜索第三方数据，或关联在高级电子数据展示事例中与保管人存储 Twitter 数据的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e0892-108">You can search third-party data using Content Search or associate the mailbox where the Twitter data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="e0892-109">使用连接器在 Microsoft 365 中导入和存档 Twitter 数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="e0892-109">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="e0892-110">在导入 Twitter 数据之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Microsoft 365 保留策略）应用到存储在邮箱中的数据。</span><span class="sxs-lookup"><span data-stu-id="e0892-110">After Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="e0892-111">例如，您可以使用内容搜索来搜索 Twitter 数据，或将与数据存储在一起的邮箱与高级电子数据展示事例中的保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="e0892-111">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="e0892-112">使用连接器在 Microsoft 365 中导入和存档 Twitter 数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="e0892-112">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="e0892-113">为 Twitter 设置连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="e0892-113">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="e0892-114">先完成以下先决条件，然后才能在 Microsoft 365 合规性中心中设置和配置连接器，以便从组织的 Twitter 帐户导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="e0892-114">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Twitter account.</span></span>

- <span data-ttu-id="e0892-115">您的组织需要 Twitter 帐户;设置连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="e0892-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="e0892-116">您的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="e0892-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="e0892-117">如果你没有现有的 Azure 订阅，你可以注册以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e0892-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="e0892-118">注册免费的一年 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="e0892-118">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="e0892-119">注册 "转到即点即用 Azure 订阅"</span><span class="sxs-lookup"><span data-stu-id="e0892-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="e0892-120">Microsoft 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全 & 合规中心中的连接器。</span><span class="sxs-lookup"><span data-stu-id="e0892-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="e0892-121">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="e0892-121">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="e0892-122">若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用全局管理员的凭据登录，然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="e0892-122">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of a global admin, and then accept the request.</span></span>

- <span data-ttu-id="e0892-123">在 Microsoft 365 合规性中心（步骤5）中设置 Twitter 连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="e0892-123">The user who sets up the Twitter connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e0892-124">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="e0892-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="e0892-125">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="e0892-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e0892-126">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="e0892-126">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e0892-127">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="e0892-127">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="e0892-128">步骤1：在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="e0892-128">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="e0892-129">第一步是在 Azure Active Directory （AAD）中注册新应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0892-129">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="e0892-130">此应用程序对应于您在您在 Twitter 连接器的步骤2中实现的 web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="e0892-130">This app corresponds to the web app resource that you implement in Step 2 for the Twitter connector.</span></span>

<span data-ttu-id="e0892-131">有关分步说明，请参阅[在 Azure Active Directory 中创建应用](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="e0892-131">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="e0892-132">在完成此步骤（按照分步说明操作）后，您将把以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="e0892-132">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="e0892-133">这些值将在部署过程的后续步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="e0892-133">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="e0892-134">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="e0892-134">AAD application ID</span></span>

- <span data-ttu-id="e0892-135">AAD 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="e0892-135">AAD application secret</span></span>

- <span data-ttu-id="e0892-136">租户 Id</span><span class="sxs-lookup"><span data-stu-id="e0892-136">Tenant Id</span></span>

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a><span data-ttu-id="e0892-137">步骤2：将 GitHub 存储库中的连接器 web 服务部署到 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="e0892-137">Step 2: Deploy connector web service from GitHub repository to your Azure account</span></span>

<span data-ttu-id="e0892-138">下一步是部署将使用 Twitter API 连接到 Twitter 帐户并提取数据的 Twitter 连接器应用的源代码，以便您可以将数据导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e0892-138">The next step is to deploy the source code for the Twitter connector app that will use Twitter API to connect to your Twitter account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="e0892-139">为组织部署的 Twitter 连接器会将组织的 Twitter 帐户中的项目上载到在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="e0892-139">The Twitter connector that you deploy for your organization will upload the items from your organization's Twitter account to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="e0892-140">在 Microsoft 365 合规性中心（步骤5）中创建 Twitter 连接器后，Office 365 导入服务会将 Twitter 数据从 Azure 存储位置复制到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e0892-140">After you create a Twitter connector in the Microsoft 365 compliance center (in Step 5), the Office 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="e0892-141">如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-twitter)" 部分中所述，您必须具有有效的 azure 订阅才能创建 azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="e0892-141">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="e0892-142">若要部署 Twitter 连接器应用的源代码，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0892-142">To deploy the source code for the Twitter connector app:</span></span>

1. <span data-ttu-id="e0892-143">转到[此 GitHub 网站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。</span><span class="sxs-lookup"><span data-stu-id="e0892-143">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).</span></span>

2. <span data-ttu-id="e0892-144">单击 "**部署到 Azure**"。</span><span class="sxs-lookup"><span data-stu-id="e0892-144">Click **Deploy to Azure**.</span></span>

<span data-ttu-id="e0892-145">有关分步说明，请参阅[将连接器 web 服务从 GitHub 部署到你的 Azure 帐户](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="e0892-145">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="e0892-146">按照分步说明完成此步骤，您将提供以下信息</span><span class="sxs-lookup"><span data-stu-id="e0892-146">While you follow the step-by-step instructions to complete this step, you provide the following information</span></span>

- <span data-ttu-id="e0892-147">APISecretKey：在完成此步骤的过程中，您将创建此密码。</span><span class="sxs-lookup"><span data-stu-id="e0892-147">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="e0892-148">它在步骤5中使用。</span><span class="sxs-lookup"><span data-stu-id="e0892-148">It's used in Step 5.</span></span>

- <span data-ttu-id="e0892-149">tenantId：在第1步中创建 Azure Active Directory 中的 Twitter 应用之后复制的 Microsoft 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="e0892-149">tenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Twitter app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="e0892-150">完成此步骤后，请务必复制 app Service URL （例如 `https://twitterconnector.azurewebsites.net` ）。</span><span class="sxs-lookup"><span data-stu-id="e0892-150">After completing this step, be sure to copy the app Service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="e0892-151">您需要使用此 URL 来完成步骤3、步骤4和步骤5。</span><span class="sxs-lookup"><span data-stu-id="e0892-151">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-create-developer-app-on-twitter"></a><span data-ttu-id="e0892-152">步骤3：在 Twitter 上创建开发人员应用</span><span class="sxs-lookup"><span data-stu-id="e0892-152">Step 3: Create developer app on Twitter</span></span>

<span data-ttu-id="e0892-153">下一步是在 Twitter 上创建和配置开发人员应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0892-153">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="e0892-154">您在步骤7中创建的自定义连接器使用 Twitter 应用与 Twitter API 进行交互，以从组织的 Twitter 帐户中获取数据。</span><span class="sxs-lookup"><span data-stu-id="e0892-154">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="e0892-155">有关分步说明，请参阅[创建 Twitter 应用](deploy-twitter-connector.md#step-3-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="e0892-155">For step-by-step instructions, see [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).</span></span>

<span data-ttu-id="e0892-156">在完成此步骤（按照分步说明操作）后，将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="e0892-156">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="e0892-157">这些值将用于在步骤4中配置 Twitter 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="e0892-157">These values will be used to configure the Twitter connector app in Step 4.</span></span>

- <span data-ttu-id="e0892-158">Twitter API 密钥</span><span class="sxs-lookup"><span data-stu-id="e0892-158">Twitter API Key</span></span>

- <span data-ttu-id="e0892-159">Twitter API 密钥</span><span class="sxs-lookup"><span data-stu-id="e0892-159">Twitter API Secret Key</span></span>

- <span data-ttu-id="e0892-160">Twitter 访问令牌</span><span class="sxs-lookup"><span data-stu-id="e0892-160">Twitter Access Token</span></span>

- <span data-ttu-id="e0892-161">Twitter 访问令牌机密</span><span class="sxs-lookup"><span data-stu-id="e0892-161">Twitter Access Token Secret</span></span>

## <a name="step-4-configure-the-twitter-connector-app"></a><span data-ttu-id="e0892-162">步骤4：配置 Twitter 连接器应用</span><span class="sxs-lookup"><span data-stu-id="e0892-162">Step 4: Configure the Twitter connector app</span></span>

<span data-ttu-id="e0892-163">下一步是将配置设置添加到您在步骤2中部署的 Twitter 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="e0892-163">The next step is to add configurations settings to the Twitter connector app that you deployed in Step 2.</span></span> <span data-ttu-id="e0892-164">为此，请转到连接器应用的主页并配置该页面。</span><span class="sxs-lookup"><span data-stu-id="e0892-164">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="e0892-165">有关分步说明，请参阅[Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="e0892-165">For step-by-step instructions, see [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).</span></span>

<span data-ttu-id="e0892-166">在完成此步骤（按照分步说明操作）后，您将提供以下信息（在完成上述步骤后，您已将其复制到文本文件中）：</span><span class="sxs-lookup"><span data-stu-id="e0892-166">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="e0892-167">Twitter API 密钥（在步骤3中获取）</span><span class="sxs-lookup"><span data-stu-id="e0892-167">Twitter API Key (obtained in Step 3)</span></span>

- <span data-ttu-id="e0892-168">Twitter API 密钥（在步骤3中获取）</span><span class="sxs-lookup"><span data-stu-id="e0892-168">Twitter API Secret Key (obtained in Step 3)</span></span>

- <span data-ttu-id="e0892-169">Twitter 访问令牌（在步骤3中获取）</span><span class="sxs-lookup"><span data-stu-id="e0892-169">Twitter Access Token (obtained in Step 3)</span></span>

- <span data-ttu-id="e0892-170">Twitter 访问令牌机密（在步骤3中获取）</span><span class="sxs-lookup"><span data-stu-id="e0892-170">Twitter Access Token Secret (obtained in Step 3)</span></span>

- <span data-ttu-id="e0892-171">Azure Active Directory 应用程序 ID （在步骤1中获取的 AAD 应用程序 ID）</span><span class="sxs-lookup"><span data-stu-id="e0892-171">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="e0892-172">Azure Active Directory 应用程序密码（在步骤1中获取的 AAD 应用程序密码）</span><span class="sxs-lookup"><span data-stu-id="e0892-172">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="e0892-173">步骤5：在 Microsoft 365 合规性中心中设置 Twitter 连接器</span><span class="sxs-lookup"><span data-stu-id="e0892-173">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="e0892-174">最后一步是在 Microsoft 365 合规性中心中设置 Twitter 连接器，以将组织的 Twitter 帐户中的数据导入到 Microsoft 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="e0892-174">The final step is to set up the Twitter connector in the Microsoft 365 compliance center that will import data from your organization's Twitter account to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="e0892-175">完成此步骤后，Office 365 导入服务将开始从您的组织的 Twitter 帐户向 Microsoft 365 导入数据。</span><span class="sxs-lookup"><span data-stu-id="e0892-175">After you complete this step, the Office 365 Import service will start importing data from your organization's Twitter account to Microsoft 365.</span></span>

<span data-ttu-id="e0892-176">有关分步说明，请参阅[在 Microsoft 365 合规性中心中设置 Twitter 连接器](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="e0892-176">For step-by-step instructions, see [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="e0892-177">在完成此步骤（按照分步说明操作）后，您将提供以下信息（在完成这些步骤后，您已将其复制到文本文件中）。</span><span class="sxs-lookup"><span data-stu-id="e0892-177">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="e0892-178">Azure 应用服务 URL （在步骤2中获取; 例如， `https://twitterconnector.azurewebsites.net` ）</span><span class="sxs-lookup"><span data-stu-id="e0892-178">Azure app service URL (obtained in Step 2; for example, `https://twitterconnector.azurewebsites.net`)</span></span>

- <span data-ttu-id="e0892-179">APISecretKey （您在步骤2中创建）</span><span class="sxs-lookup"><span data-stu-id="e0892-179">APISecretKey (that you created in Step 2)</span></span>
