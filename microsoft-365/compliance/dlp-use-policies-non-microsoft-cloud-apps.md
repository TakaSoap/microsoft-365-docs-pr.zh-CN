---
title: '使用非 Microsoft 云应用的数据丢失防护策略 (预览) '
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用非 Microsoft 云应用的 dlp 策略。
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649653"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="d2a6d-103">使用非 Microsoft 云应用的数据丢失防护策略 (预览) </span><span class="sxs-lookup"><span data-stu-id="d2a6d-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="d2a6d-104">对非 Microsoft 云应用 (DLP) 策略的数据丢失防护是 Microsoft 365 DLP 功能套件的一部分;使用这些功能，您可以跨 Microsoft 365 服务发现和保护敏感项目。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="d2a6d-105">有关所有 Microsoft DLP 产品的详细信息，请参阅 [数据丢失防护概述](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="d2a6d-106">您可以使用 DLP 策略来监视和检测何时使用敏感项目，并通过非 Microsoft 云应用共享这些应用。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="d2a6d-107">使用这些策略，您将能够确保正确使用和保护它们所需的可见性和控制，并有助于防止可能危害它们的风险行为。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d2a6d-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="d2a6d-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="d2a6d-109">SKU/订阅许可</span><span class="sxs-lookup"><span data-stu-id="d2a6d-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="d2a6d-110">在开始对非 Microsoft 云应用使用 DLP 策略之前，请确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 和任何加载项。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="d2a6d-111">若要访问和使用此功能，您必须具有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="d2a6d-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="d2a6d-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d2a6d-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="d2a6d-113">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="d2a6d-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="d2a6d-114">Microsoft 365 E5 安全版</span><span class="sxs-lookup"><span data-stu-id="d2a6d-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="d2a6d-115">准备云应用安全环境</span><span class="sxs-lookup"><span data-stu-id="d2a6d-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="d2a6d-116">对非 Microsoft 云应用的 DLP 策略使用云应用安全 DLP 功能。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="d2a6d-117">若要使用它，应准备云应用安全环境。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="d2a6d-118">有关说明，请参阅 [为您的应用程序设置即时可见性、保护和调控操作](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="d2a6d-119">连接非 Microsoft 云应用</span><span class="sxs-lookup"><span data-stu-id="d2a6d-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="d2a6d-120">若要将 DLP 策略用于特定的非 Microsoft 云应用，应用必须连接到云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="d2a6d-121">有关信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d2a6d-121">For information, see:</span></span>

- [<span data-ttu-id="d2a6d-122">连接框</span><span class="sxs-lookup"><span data-stu-id="d2a6d-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d2a6d-123">连接收存箱</span><span class="sxs-lookup"><span data-stu-id="d2a6d-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d2a6d-124">连接 G 套件</span><span class="sxs-lookup"><span data-stu-id="d2a6d-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d2a6d-125">连接 Salesforce</span><span class="sxs-lookup"><span data-stu-id="d2a6d-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d2a6d-126">连接 Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="d2a6d-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="d2a6d-127">将云应用程序连接到云应用安全性之后，可以为其创建 Microsoft 365 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="d2a6d-128">此外，还可以使用 Microsoft 云应用安全为 Microsoft 云应用创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="d2a6d-129">但是，建议使用 Microsoft 365 创建和管理针对 Microsoft 云应用的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="d2a6d-130">创建到非 Microsoft 云应用的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="d2a6d-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="d2a6d-131">当您选择 DLP 策略的位置时，请打开 **Microsoft 云应用安全** 位置。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="d2a6d-132">若要选择特定的应用或实例，请选择 " **选择实例**"。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="d2a6d-133">如果不选择实例，策略将使用 Microsoft Cloud App Security 租户中的所有已连接应用。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![应用策略的位置](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="d2a6d-136">您可以为每个受支持的非 Microsoft 云应用程序选择各种操作。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="d2a6d-137">每个应用程序都有不同的可能操作 (取决于云应用程序 API) 。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![创建规则](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="d2a6d-139">在 DLP 策略中创建规则时，可以为非 Microsoft 云应用程序选择操作。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="d2a6d-140">若要限制第三方应用，请选择 " **限制第三方应用**"。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![限制第三方应用程序](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="d2a6d-142">有关创建和配置 DLP 策略的信息，请参阅 [Create test and 调谐 a dlp policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="d2a6d-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2a6d-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2a6d-143">See Also</span></span>

- [<span data-ttu-id="d2a6d-144">创建测试并优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="d2a6d-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="d2a6d-145">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="d2a6d-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="d2a6d-146">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="d2a6d-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
