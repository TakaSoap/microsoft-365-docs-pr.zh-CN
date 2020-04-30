---
title: 使用连接器存档 Facebook 数据
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
description: 管理员可以将连接器设置为从数据源（如 Facebook 商业页面、Twitter、LinkedIn 公司页面和即时 Bloomberg）导入第三方数据。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据的管理。
ms.openlocfilehash: 21023e380e4065f40edd4c3dea3f4c461d743f04
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943231"
---
# <a name="set-up-a-connector-to-archive-facebook-data"></a><span data-ttu-id="095e4-104">使用连接器存档 Facebook 数据</span><span class="sxs-lookup"><span data-stu-id="095e4-104">Set up a connector to archive Facebook data</span></span>

<span data-ttu-id="095e4-105">使用 Microsoft 365 合规性中心中的连接器将来自 Facebook 商业页面的数据导入并存档到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="095e4-105">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="095e4-106">在设置并配置连接器后，它会连接到 Facebook 商业页面（按计划），将 Facebook 项目的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="095e4-106">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="095e4-107">在导入 Facebook 数据之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Facebook 数据。</span><span class="sxs-lookup"><span data-stu-id="095e4-107">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="095e4-108">例如，如果将邮箱置于诉讼保留或分配到保留策略，则会保留 Facebook 数据。</span><span class="sxs-lookup"><span data-stu-id="095e4-108">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="095e4-109">您可以使用内容搜索来搜索第三方数据，或关联在高级电子数据展示事例中与保管人存储 Facebook 数据的邮箱。</span><span class="sxs-lookup"><span data-stu-id="095e4-109">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="095e4-110">使用连接器在 Microsoft 365 中导入和存档 Facebook 数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="095e4-110">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="095e4-111">设置用于 Facebook 商业页面的连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="095e4-111">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="095e4-112">先完成以下先决条件，然后才能在 Microsoft 365 合规性中心中设置和配置连接器，以便从组织的 Facebook 商业页面导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="095e4-112">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="095e4-113">您的组织的业务页面需要一个 Facebook 帐户（在设置连接器时，需要登录到此帐户）。</span><span class="sxs-lookup"><span data-stu-id="095e4-113">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="095e4-114">目前，您只能存档 Facebook 商业页面中的数据;您不能存档单个 Facebook 配置文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="095e4-114">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="095e4-115">您的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="095e4-115">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="095e4-116">如果你没有现有的 Azure 订阅，你可以注册以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="095e4-116">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="095e4-117">注册免费的一年 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="095e4-117">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="095e4-118">注册 "转到即点即用 Azure 订阅"</span><span class="sxs-lookup"><span data-stu-id="095e4-118">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="095e4-119">Microsoft 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全 & 合规中心中的连接器。</span><span class="sxs-lookup"><span data-stu-id="095e4-119">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="095e4-120">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="095e4-120">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="095e4-121">若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用全局管理员的凭据登录，然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="095e4-121">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of a global admin, and then accept the request.</span></span>

- <span data-ttu-id="095e4-122">在 Microsoft 365 合规性中心（步骤5）中设置自定义连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="095e4-122">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="095e4-123">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="095e4-123">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="095e4-124">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="095e4-124">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="095e4-125">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="095e4-125">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="095e4-126">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。</span><span class="sxs-lookup"><span data-stu-id="095e4-126">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="095e4-127">步骤1：在 Azure Active Directory 中创建应用程序</span><span class="sxs-lookup"><span data-stu-id="095e4-127">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="095e4-128">第一步是在 Azure Active Directory （AAD）中注册新应用程序。</span><span class="sxs-lookup"><span data-stu-id="095e4-128">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="095e4-129">此应用程序对应于您在第4步和第5步中为 Facebook 连接器实现的 web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="095e4-129">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="095e4-130">有关分步说明，请参阅[在 Azure Active Directory 中创建应用](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="095e4-130">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="095e4-131">在完成此步骤（通过使用前面的分步说明）时，您将把以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="095e4-131">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="095e4-132">这些值将在部署过程的后续步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="095e4-132">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="095e4-133">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="095e4-133">AAD application ID</span></span>

- <span data-ttu-id="095e4-134">AAD 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="095e4-134">AAD application secret</span></span>

- <span data-ttu-id="095e4-135">租户 Id</span><span class="sxs-lookup"><span data-stu-id="095e4-135">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="095e4-136">步骤2：将来自 GitHub 的连接器 web 服务部署到你的 Azure 帐户</span><span class="sxs-lookup"><span data-stu-id="095e4-136">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="095e4-137">下一步是部署 Facebook 商业页面连接器应用程序的源代码，该应用程序将使用 Facebook API 连接到 Facebook 帐户并提取数据，以便您可以将数据导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="095e4-137">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="095e4-138">您为组织部署的 Facebook 连接器会将您的 Facebook 商业页面中的项目上载到在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="095e4-138">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="095e4-139">在 Microsoft 365 合规性中心（第5步）中创建 Facebook 商业页面连接器后，导入服务会将 Facebook business pages 数据从 Azure 存储位置复制到 Microsoft 365 组织中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="095e4-139">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="095e4-140">如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)" 部分中所述，您必须具有有效的 azure 订阅才能创建 azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="095e4-140">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="095e4-141">有关分步说明，请参阅[将连接器 web 服务从 GitHub 部署到你的 Azure 帐户](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="095e4-141">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="095e4-142">在完成此步骤的分步说明中，您将提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="095e4-142">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="095e4-143">APISecretKey：在完成此步骤的过程中，您将创建此密码。</span><span class="sxs-lookup"><span data-stu-id="095e4-143">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="095e4-144">它在步骤5中使用。</span><span class="sxs-lookup"><span data-stu-id="095e4-144">It's used in Step 5.</span></span>

- <span data-ttu-id="095e4-145">TenantId：在第1步中创建 Azure Active Directory 中的 Facebook 连接器应用之后复制的 Microsoft 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="095e4-145">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="095e4-146">完成此步骤后，请务必复制 Azure 应用服务 URL （例如， https://fbconnector.azurewebsites.net)。</span><span class="sxs-lookup"><span data-stu-id="095e4-146">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="095e4-147">您需要使用此 URL 来完成步骤3、步骤4和步骤5。</span><span class="sxs-lookup"><span data-stu-id="095e4-147">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="095e4-148">步骤3：在 Facebook 上注册 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="095e4-148">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="095e4-149">下一步是在 Facebook 上创建和配置新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="095e4-149">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="095e4-150">您在步骤5中创建的 Facebook 商业页面连接器使用 Facebook web 应用与 Facebook API 进行交互，以从组织的 Facebook 商业版页面中获取数据。</span><span class="sxs-lookup"><span data-stu-id="095e4-150">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="095e4-151">有关分步说明，请参阅[注册 Facebook 应用](deploy-facebook-connector.md#step-3-register-the-facebook-app)。</span><span class="sxs-lookup"><span data-stu-id="095e4-151">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="095e4-152">在完成此步骤（按照分步说明操作）后，将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="095e4-152">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="095e4-153">这些值用于在步骤4中配置 Facebook 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="095e4-153">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="095e4-154">Facebook 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="095e4-154">Facebook application ID</span></span>

- <span data-ttu-id="095e4-155">Facebook 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="095e4-155">Facebook application secret</span></span>

- <span data-ttu-id="095e4-156">Facebook webhook verify token</span><span class="sxs-lookup"><span data-stu-id="095e4-156">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="095e4-157">步骤4：配置 Facebook 连接器应用程序</span><span class="sxs-lookup"><span data-stu-id="095e4-157">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="095e4-158">下一步是将配置设置添加到在步骤1中创建 Azure web 应用资源时上载的 Facebook 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="095e4-158">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="095e4-159">为此，请转到连接器应用的主页并配置该页面。</span><span class="sxs-lookup"><span data-stu-id="095e4-159">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="095e4-160">有关分步说明，请参阅[Configure The Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。</span><span class="sxs-lookup"><span data-stu-id="095e4-160">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="095e4-161">在完成此步骤（按照分步说明执行）后，您将提供以下信息（在完成上述步骤后，您已将其复制到文本文件中）：</span><span class="sxs-lookup"><span data-stu-id="095e4-161">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="095e4-162">Facebook 应用程序 ID （在步骤3中获取）</span><span class="sxs-lookup"><span data-stu-id="095e4-162">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="095e4-163">Facebook 应用程序密码（在步骤3中获取）</span><span class="sxs-lookup"><span data-stu-id="095e4-163">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="095e4-164">Facebook webhook verify token （在步骤3中获取）</span><span class="sxs-lookup"><span data-stu-id="095e4-164">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="095e4-165">Azure Active Directory 应用程序 ID （在步骤1中获取的 AAD 应用程序 ID）</span><span class="sxs-lookup"><span data-stu-id="095e4-165">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="095e4-166">Azure Active Directory 应用程序密码（在步骤1中获取的 AAD 应用程序密码）</span><span class="sxs-lookup"><span data-stu-id="095e4-166">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="095e4-167">第5步：设置 Microsoft 365 合规性中心中的 Facebook 商业页面连接器</span><span class="sxs-lookup"><span data-stu-id="095e4-167">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="095e4-168">最后一步是在 Microsoft 365 合规性中心中设置连接器，以将来自 Facebook 商业页面的数据导入到 Microsoft 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="095e4-168">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="095e4-169">完成此步骤后，Office 365 导入服务将开始将你的 Facebook 商业页面中的数据导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="095e4-169">After you complete this step, the Office 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="095e4-170">有关分步说明，请参阅[第5步：在 Microsoft 365 合规性中心中设置 Facebook 连接器](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="095e4-170">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="095e4-171">在完成此步骤（按照分步说明执行）后，您将提供以下信息（在完成这些步骤后，您已将其复制到文本文件中）。</span><span class="sxs-lookup"><span data-stu-id="095e4-171">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="095e4-172">AAD 应用程序 ID （在步骤1中获取）</span><span class="sxs-lookup"><span data-stu-id="095e4-172">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="095e4-173">Azure 应用服务 URL （在步骤1中获取; 例如，https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="095e4-173">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="095e4-174">APISecretKey （您在步骤2中创建）</span><span class="sxs-lookup"><span data-stu-id="095e4-174">APISecretKey (that you created in Step 2)</span></span>
