---
title: 使用连接器存档 Facebook 数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解如何设置& Microsoft 365 合规中心中的连接器将 & 存档数据从 Facebook 商业版页面导入到 Microsoft 365。
ms.openlocfilehash: df86897defa92788399f704c53c00ebb9e4f4269
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790146"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a><span data-ttu-id="a4cec-103">设置连接器以存档 Facebook 数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="a4cec-103">Set up a connector to archive Facebook data (preview)</span></span>

<span data-ttu-id="a4cec-104">使用 Microsoft 365 合规中心中的连接器将 Facebook 商业版页面中的数据导入和存档到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a4cec-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="a4cec-105">设置和配置连接器后，它将按计划连接到 Facebook Business 页面 () ，将 Facebook 项目的内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a4cec-105">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="a4cec-106">导入 Facebook 数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Facebook 数据。</span><span class="sxs-lookup"><span data-stu-id="a4cec-106">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="a4cec-107">例如，将邮箱置于诉讼保留或分配给保留策略时，将保留 Facebook 数据。</span><span class="sxs-lookup"><span data-stu-id="a4cec-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="a4cec-108">您可以使用内容搜索搜索第三方数据，或将存储 Facebook 数据的邮箱与高级电子数据展示案例中的保管人关联。</span><span class="sxs-lookup"><span data-stu-id="a4cec-108">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="a4cec-109">使用连接器在 Microsoft 365 中导入和存档 Facebook 数据可帮助组织遵守政府政策和法规策略。</span><span class="sxs-lookup"><span data-stu-id="a4cec-109">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="a4cec-110">设置 Facebook 商业版页面连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="a4cec-110">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="a4cec-111">完成以下先决条件，然后才能在 Microsoft 365 合规中心中设置和配置连接器，以从组织的 Facebook 商业页面导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="a4cec-111">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="a4cec-112">您需要一个 Facebook 帐户作为组织业务页面 (设置连接器帐户时需要登录到此) 。</span><span class="sxs-lookup"><span data-stu-id="a4cec-112">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="a4cec-113">目前，只能存档来自 Facebook 业务页面的数据;无法存档单个 Facebook 配置文件的数据。</span><span class="sxs-lookup"><span data-stu-id="a4cec-113">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="a4cec-114">你的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="a4cec-114">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="a4cec-115">如果你没有现有的 Azure 订阅，你可以注册以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="a4cec-115">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="a4cec-116">注册一年免费的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="a4cec-116">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free)

    - [<span data-ttu-id="a4cec-117">注册 Azure 付费订阅</span><span class="sxs-lookup"><span data-stu-id="a4cec-117">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="a4cec-118">Microsoft 365 订阅中包含的免费 [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) 订阅不支持安全与合规&连接器。</span><span class="sxs-lookup"><span data-stu-id="a4cec-118">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="a4cec-119">Facebook 商业版页面连接器在一天中总共可以导入 200，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="a4cec-119">The connector for Facebook Business pages can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="a4cec-120">如果一天中 Facebook 商业版项目超过 200，000 个，则这些项目不会导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a4cec-120">If there are more than 200,000 Facebook Business items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="a4cec-121">在步骤 5 (Microsoft 365 合规中心中设置自定义连接器) 必须在 Exchange Online 中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="a4cec-121">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a4cec-122">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="a4cec-122">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="a4cec-123">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="a4cec-123">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a4cec-124">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="a4cec-124">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a4cec-125">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="a4cec-125">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="a4cec-126">步骤 1：在 Azure Active Directory 中创建应用</span><span class="sxs-lookup"><span data-stu-id="a4cec-126">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="a4cec-127">第一步是在 Azure Active Directory (AAD) 。</span><span class="sxs-lookup"><span data-stu-id="a4cec-127">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="a4cec-128">此应用程序对应于你在 Facebook 连接器的步骤 4 和步骤 5 中实现的 Web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="a4cec-128">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="a4cec-129">有关分步说明，请参阅在 [Azure Active Directory 中创建应用](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="a4cec-129">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="a4cec-130">在完成此步骤 (使用前面的分步说明) ，您将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="a4cec-130">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="a4cec-131">这些值在部署过程的稍后步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="a4cec-131">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="a4cec-132">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="a4cec-132">AAD application ID</span></span>

- <span data-ttu-id="a4cec-133">AAD 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="a4cec-133">AAD application secret</span></span>

- <span data-ttu-id="a4cec-134">租户 ID</span><span class="sxs-lookup"><span data-stu-id="a4cec-134">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="a4cec-135">步骤 2：将连接器 Web 服务从 GitHub 部署到 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="a4cec-135">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="a4cec-136">下一步是部署 Facebook 业务页面连接器应用的源代码，该应用将使用 Facebook API 连接到 Facebook 帐户并提取数据，以便将其导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a4cec-136">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="a4cec-137">为组织部署的 Facebook 连接器将项目从 Facebook 业务页面上载到在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="a4cec-137">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="a4cec-138">在步骤 5) 中的 Microsoft 365 合规中心 (创建 Facebook 业务页面连接器后，导入服务将 Facebook 业务页面数据从 Azure 存储位置复制到 Microsoft 365 组织的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a4cec-138">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="a4cec-139">如前面" [先决条件"部分](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) 所述，你必须具有有效的 Azure 订阅，以创建 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="a4cec-139">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="a4cec-140">有关分步说明，请参阅将连接器 [Web 服务从 GitHub 部署到 Azure 帐户](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="a4cec-140">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="a4cec-141">在完成此步骤的分步说明中，您将提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="a4cec-141">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="a4cec-142">APISecretKey：在此步骤完成期间创建此密码。</span><span class="sxs-lookup"><span data-stu-id="a4cec-142">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="a4cec-143">它在步骤 5 中使用。</span><span class="sxs-lookup"><span data-stu-id="a4cec-143">It's used in Step 5.</span></span>

- <span data-ttu-id="a4cec-144">TenantId：在步骤 1 中的 Azure Active Directory 中创建 Facebook 连接器应用后复制的 Microsoft 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="a4cec-144">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="a4cec-145">完成此步骤后，请务必复制 Azure 应用服务 URL (例如 https://fbconnector.azurewebsites.net) 。</span><span class="sxs-lookup"><span data-stu-id="a4cec-145">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="a4cec-146">您需要使用此 URL 完成步骤 3、步骤 4 和步骤 5) 。</span><span class="sxs-lookup"><span data-stu-id="a4cec-146">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="a4cec-147">步骤 3：在 Facebook 上注册 Web 应用</span><span class="sxs-lookup"><span data-stu-id="a4cec-147">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="a4cec-148">下一步是在 Facebook 上创建和配置新应用。</span><span class="sxs-lookup"><span data-stu-id="a4cec-148">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="a4cec-149">在步骤 5 中创建的 Facebook 业务页面连接器使用 Facebook Web 应用与 Facebook API 进行交互，以从组织的 Facebook 业务页面获取数据。</span><span class="sxs-lookup"><span data-stu-id="a4cec-149">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="a4cec-150">有关分步说明，请参阅"注册[Facebook 应用"。](deploy-facebook-connector.md#step-3-register-the-facebook-app)</span><span class="sxs-lookup"><span data-stu-id="a4cec-150">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="a4cec-151">完成此步骤 (按照下面的分步说明) ，将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="a4cec-151">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="a4cec-152">这些值用于在步骤 4 中配置 Facebook 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="a4cec-152">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="a4cec-153">Facebook 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="a4cec-153">Facebook application ID</span></span>

- <span data-ttu-id="a4cec-154">Facebook 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="a4cec-154">Facebook application secret</span></span>

- <span data-ttu-id="a4cec-155">Facebook webhook 验证令牌</span><span class="sxs-lookup"><span data-stu-id="a4cec-155">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="a4cec-156">步骤 4：配置 Facebook 连接器应用</span><span class="sxs-lookup"><span data-stu-id="a4cec-156">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="a4cec-157">下一步是将配置设置添加到你在步骤 1 中创建 Azure Web 应用资源时上载的 Facebook 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="a4cec-157">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="a4cec-158">为此，请进入连接器应用的主页并配置它。</span><span class="sxs-lookup"><span data-stu-id="a4cec-158">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="a4cec-159">有关分步说明，请参阅"配置 [Facebook 连接器"应用](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。</span><span class="sxs-lookup"><span data-stu-id="a4cec-159">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="a4cec-160">在完成此步骤 (按照) 的分步说明进行操作， (在完成上述步骤之后复制到文本文件的以下信息) ：</span><span class="sxs-lookup"><span data-stu-id="a4cec-160">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="a4cec-161">在步骤 3 (获取的 Facebook 应用程序 ID) </span><span class="sxs-lookup"><span data-stu-id="a4cec-161">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="a4cec-162">在步骤 3 (获取的 Facebook 应用程序) </span><span class="sxs-lookup"><span data-stu-id="a4cec-162">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="a4cec-163">Facebook webhook 验证 (步骤 3 中获取的令牌) </span><span class="sxs-lookup"><span data-stu-id="a4cec-163">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="a4cec-164">步骤 1 (获取的 AAD 应用程序 ID 中的 Azure Active Directory 应用程序 ID) </span><span class="sxs-lookup"><span data-stu-id="a4cec-164">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="a4cec-165">在步骤 1 (获取的 AAD 应用程序密码的 Azure Active Directory 应用程序) </span><span class="sxs-lookup"><span data-stu-id="a4cec-165">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="a4cec-166">步骤 5：在 Microsoft 365 合规中心中设置 Facebook 商业版页面连接器</span><span class="sxs-lookup"><span data-stu-id="a4cec-166">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="a4cec-167">最后一步是在 Microsoft 365 合规中心设置连接器，以将数据从 Facebook 商业版页面导入到 Microsoft 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="a4cec-167">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="a4cec-168">完成此步骤后，Microsoft 365 导入服务将开始将数据从 Facebook 商业版页面导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a4cec-168">After you complete this step, the Microsoft 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="a4cec-169">有关分步说明，请参阅步骤 [5：在 Microsoft 365 合规](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)中心设置 Facebook 连接器。</span><span class="sxs-lookup"><span data-stu-id="a4cec-169">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="a4cec-170">完成此步骤 (按照) 中的分步说明进行操作， (在完成这些步骤后复制到文本文件中的以下信息) 。</span><span class="sxs-lookup"><span data-stu-id="a4cec-170">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="a4cec-171">在步骤 1 (获取的 AAD 应用程序 ID) </span><span class="sxs-lookup"><span data-stu-id="a4cec-171">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="a4cec-172">在步骤 1 (获取的 Azure 应用服务 URL;例如， https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="a4cec-172">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="a4cec-173">在步骤 2 (中创建的 APISecretKey) </span><span class="sxs-lookup"><span data-stu-id="a4cec-173">APISecretKey (that you created in Step 2)</span></span>
