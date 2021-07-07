---
title: 对非 Microsoft 云应用使用数据丢失防护策略
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
ms.openlocfilehash: 4bda45a6da6b9626391da37eb9a806b3308c5e7f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322313"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a><span data-ttu-id="36c69-103">对非 Microsoft 云应用使用数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="36c69-103">Use data loss prevention policies for non-Microsoft cloud apps</span></span>

<span data-ttu-id="36c69-104">从 DLP (到) 应用的数据丢失防护是 DLP 功能Microsoft 365的一部分;使用这些功能，可以跨服务发现和保护Microsoft 365项。</span><span class="sxs-lookup"><span data-stu-id="36c69-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="36c69-105">有关所有 Microsoft DLP 产品/服务的信息，请参阅了解 [数据丢失防护](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="36c69-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="36c69-106">您可以使用 DLP 策略对非 Microsoft 云应用进行监视和检测，以监视和检测何时通过非 Microsoft 云应用使用和共享敏感项目。</span><span class="sxs-lookup"><span data-stu-id="36c69-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="36c69-107">使用这些策略可为你提供所需的可见性和控制，以确保正确使用和保护它们，并且有助于防止可能损害它们的风险行为。</span><span class="sxs-lookup"><span data-stu-id="36c69-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="36c69-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="36c69-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="36c69-109">SKU/订阅许可</span><span class="sxs-lookup"><span data-stu-id="36c69-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="36c69-110">开始将 DLP 策略用于非 Microsoft 云应用之前，Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何加载项。</span><span class="sxs-lookup"><span data-stu-id="36c69-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="36c69-111">若要访问和使用此功能，你必须拥有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="36c69-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="36c69-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="36c69-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="36c69-113">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="36c69-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="36c69-114">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="36c69-114">Microsoft 365 E5 Security</span></span>

### <a name="permissions"></a><span data-ttu-id="36c69-115">权限</span><span class="sxs-lookup"><span data-stu-id="36c69-115">Permissions</span></span>
<span data-ttu-id="36c69-116">创建 DLP 策略的用户应是：</span><span class="sxs-lookup"><span data-stu-id="36c69-116">The user who creates the DLP policy should be a:</span></span>
- <span data-ttu-id="36c69-117">全局管理员</span><span class="sxs-lookup"><span data-stu-id="36c69-117">Global administrator</span></span>
- <span data-ttu-id="36c69-118">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="36c69-118">Compliance administrator</span></span>
- <span data-ttu-id="36c69-119">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="36c69-119">Compliance data administrator</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="36c69-120">准备云应用安全环境</span><span class="sxs-lookup"><span data-stu-id="36c69-120">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="36c69-121">非 Microsoft 云应用的 DLP 策略使用云应用安全 DLP 功能。</span><span class="sxs-lookup"><span data-stu-id="36c69-121">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="36c69-122">若要使用它，应准备云应用安全环境。</span><span class="sxs-lookup"><span data-stu-id="36c69-122">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="36c69-123">有关说明，请参阅为应用设置即时可见性、保护 [和管理操作](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。</span><span class="sxs-lookup"><span data-stu-id="36c69-123">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="36c69-124">连接非 Microsoft 云应用</span><span class="sxs-lookup"><span data-stu-id="36c69-124">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="36c69-125">若要将 DLP 策略用于特定的非 Microsoft 云应用，该应用必须连接到 云应用安全。</span><span class="sxs-lookup"><span data-stu-id="36c69-125">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="36c69-126">有关信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="36c69-126">For information, see:</span></span>

- [<span data-ttu-id="36c69-127">连接Box</span><span class="sxs-lookup"><span data-stu-id="36c69-127">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="36c69-128">连接 Dropbox</span><span class="sxs-lookup"><span data-stu-id="36c69-128">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="36c69-129">连接G-Suite</span><span class="sxs-lookup"><span data-stu-id="36c69-129">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="36c69-130">连接Salesforce</span><span class="sxs-lookup"><span data-stu-id="36c69-130">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="36c69-131">连接Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="36c69-131">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="36c69-132">将云应用连接到 云应用安全 后，Microsoft 365创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="36c69-132">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

> [!NOTE]
> <span data-ttu-id="36c69-133">此外，还可使用 Microsoft Cloud App Security Microsoft 云应用创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="36c69-133">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="36c69-134">但是，建议使用 Microsoft 365 Microsoft 云应用创建和管理 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="36c69-134">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="36c69-135">创建对非 Microsoft 云应用的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="36c69-135">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="36c69-136">为 DLP 策略选择一个位置时，请打开Microsoft Cloud App Security **位置。**</span><span class="sxs-lookup"><span data-stu-id="36c69-136">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="36c69-137">若要选择特定应用或实例，请选择"**选择实例"。**</span><span class="sxs-lookup"><span data-stu-id="36c69-137">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="36c69-138">如果未选择实例，该策略将使用你的租户中所有Microsoft Cloud App Security应用。</span><span class="sxs-lookup"><span data-stu-id="36c69-138">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![要应用策略的位置](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="36c69-141">你可以为每种受支持的非 Microsoft 云应用选择各种操作。</span><span class="sxs-lookup"><span data-stu-id="36c69-141">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="36c69-142">对于每一个应用，可能的操作 (取决于云应用 API) 。</span><span class="sxs-lookup"><span data-stu-id="36c69-142">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![创建规则](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="36c69-144">在 DLP 策略中创建规则时，可以选择针对非 Microsoft 云应用的操作。</span><span class="sxs-lookup"><span data-stu-id="36c69-144">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="36c69-145">若要限制第三方应用，请选择"**限制第三方应用"。**</span><span class="sxs-lookup"><span data-stu-id="36c69-145">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![限制第三方应用](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> <span data-ttu-id="36c69-147">应用于非 Microsoft 应用的 DLP 策略使用Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="36c69-147">DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="36c69-148">当为非 Microsoft 应用创建 DLP 策略时，将自动在应用中创建Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="36c69-148">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="36c69-149">有关创建和配置 DLP 策略的信息，请参阅创建 [测试和调整 DLP 策略](./create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="36c69-149">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36c69-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36c69-150">See Also</span></span>

- [<span data-ttu-id="36c69-151">创建测试和调整 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="36c69-151">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md)
- [<span data-ttu-id="36c69-152">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="36c69-152">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="36c69-153">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="36c69-153">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md)
