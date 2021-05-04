---
title: '对非 Microsoft 云应用使用数据丢失防护策略 (预览) '
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
description: 了解如何将 dlp 策略用于非 Microsoft 云应用。
ms.openlocfilehash: d4c5170cab01b1ca22701b13c7afbf4f2e0ba7da
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114130"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="ead68-103">使用非 Microsoft 云应用数据丢失防护策略 (预览) </span><span class="sxs-lookup"><span data-stu-id="ead68-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="ead68-104">从 DLP (到) 应用的数据丢失防护是 DLP 功能Microsoft 365的一部分;使用这些功能，可以跨服务发现和保护Microsoft 365项。</span><span class="sxs-lookup"><span data-stu-id="ead68-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="ead68-105">有关所有 Microsoft DLP 产品/服务的信息，请参阅了解 [数据丢失防护](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="ead68-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="ead68-106">您可以使用 DLP 策略对非 Microsoft 云应用进行监视和检测，以监视和检测何时通过非 Microsoft 云应用使用和共享敏感项目。</span><span class="sxs-lookup"><span data-stu-id="ead68-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="ead68-107">使用这些策略可为你提供所需的可见性和控制，以确保正确使用和保护它们，并且有助于防止可能损害它们的风险行为。</span><span class="sxs-lookup"><span data-stu-id="ead68-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ead68-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="ead68-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="ead68-109">SKU/订阅许可</span><span class="sxs-lookup"><span data-stu-id="ead68-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="ead68-110">开始将 DLP 策略用于非 Microsoft 云应用之前，Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何加载项。</span><span class="sxs-lookup"><span data-stu-id="ead68-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="ead68-111">若要访问和使用此功能，你必须拥有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="ead68-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="ead68-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ead68-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="ead68-113">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="ead68-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="ead68-114">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="ead68-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="ead68-115">准备云应用安全环境</span><span class="sxs-lookup"><span data-stu-id="ead68-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="ead68-116">非 Microsoft 云应用的 DLP 策略使用云应用安全 DLP 功能。</span><span class="sxs-lookup"><span data-stu-id="ead68-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="ead68-117">若要使用它，应准备云应用安全环境。</span><span class="sxs-lookup"><span data-stu-id="ead68-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="ead68-118">有关说明，请参阅为应用设置即时可见性、保护 [和管理操作](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。</span><span class="sxs-lookup"><span data-stu-id="ead68-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="ead68-119">连接非 Microsoft 云应用</span><span class="sxs-lookup"><span data-stu-id="ead68-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="ead68-120">若要将 DLP 策略用于特定的非 Microsoft 云应用，该应用必须连接到 云应用安全。</span><span class="sxs-lookup"><span data-stu-id="ead68-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="ead68-121">有关信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="ead68-121">For information, see:</span></span>

- [<span data-ttu-id="ead68-122">连接Box</span><span class="sxs-lookup"><span data-stu-id="ead68-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="ead68-123">连接 Dropbox</span><span class="sxs-lookup"><span data-stu-id="ead68-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="ead68-124">连接G-Suite</span><span class="sxs-lookup"><span data-stu-id="ead68-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="ead68-125">连接Salesforce</span><span class="sxs-lookup"><span data-stu-id="ead68-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="ead68-126">连接Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="ead68-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="ead68-127">将云应用连接到 云应用安全 后，Microsoft 365创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="ead68-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="ead68-128">此外，还可使用 Microsoft Cloud App Security Microsoft 云应用创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="ead68-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="ead68-129">但是，建议使用 Microsoft 365 Microsoft 云应用创建和管理 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="ead68-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="ead68-130">创建对非 Microsoft 云应用的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="ead68-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="ead68-131">为 DLP 策略选择一个位置时，请打开Microsoft Cloud App Security **位置。**</span><span class="sxs-lookup"><span data-stu-id="ead68-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="ead68-132">若要选择特定应用或实例，请选择"**选择实例"。**</span><span class="sxs-lookup"><span data-stu-id="ead68-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="ead68-133">如果未选择实例，该策略将使用你的租户中所有Microsoft Cloud App Security应用。</span><span class="sxs-lookup"><span data-stu-id="ead68-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![要应用策略的位置](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="ead68-136">你可以为每种受支持的非 Microsoft 云应用选择各种操作。</span><span class="sxs-lookup"><span data-stu-id="ead68-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="ead68-137">对于每一个应用，可能的操作 (取决于云应用 API) 。</span><span class="sxs-lookup"><span data-stu-id="ead68-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![创建规则](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="ead68-139">在 DLP 策略中创建规则时，可以选择针对非 Microsoft 云应用的操作。</span><span class="sxs-lookup"><span data-stu-id="ead68-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="ead68-140">若要限制第三方应用，请选择"**限制第三方应用"。**</span><span class="sxs-lookup"><span data-stu-id="ead68-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![限制第三方应用](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="ead68-142">有关创建和配置 DLP 策略的信息，请参阅创建 [测试和调整 DLP 策略](./create-test-tune-dlp-policy.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="ead68-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="ead68-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ead68-143">See Also</span></span>

- [<span data-ttu-id="ead68-144">创建测试和调整 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="ead68-144">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="ead68-145">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="ead68-145">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="ead68-146">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="ead68-146">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)