---
title: 将 Microsoft Defender for Endpoint 与其他 Microsoft 解决方案集成
description: 了解 Microsoft Defender for Endpoint 如何与其他 Microsoft 解决方案集成，包括 Microsoft Defender for Identity 和 Azure Defender。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender， 条件访问， office， Microsoft Defender for Endpoint， microsoft defender for identity， microsoft defender for office， Azure Defender， Microsoft 云应用安全， azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aeb6d93017f138ce898d25f7d76e05cdcf3e90c5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878564"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="469c8-104">Microsoft Defender for Endpoint 和其他 Microsoft 解决方案</span><span class="sxs-lookup"><span data-stu-id="469c8-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="469c8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="469c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="469c8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="469c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="469c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="469c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="469c8-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="469c8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="469c8-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="469c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="469c8-110">与其他 Microsoft 解决方案集成</span><span class="sxs-lookup"><span data-stu-id="469c8-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="469c8-111">Microsoft Defender for Endpoint 直接与各种 Microsoft 解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="469c8-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="469c8-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="469c8-112">Azure Defender</span></span>
<span data-ttu-id="469c8-113">Microsoft Defender for Endpoint 提供了全面的服务器保护解决方案，包括终结点检测和响应 (EDR) 服务器上Windows功能。</span><span class="sxs-lookup"><span data-stu-id="469c8-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="469c8-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="469c8-114">Azure Sentinel</span></span>
<span data-ttu-id="469c8-115">Microsoft Defender for Endpoint 连接器允许你将来自 Microsoft Defender for Endpoint 的警报流式传输至 Azure Sentinel。</span><span class="sxs-lookup"><span data-stu-id="469c8-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="469c8-116">这将使您能够更全面分析整个组织的安全事件，并生成有效且即时响应的手册。</span><span class="sxs-lookup"><span data-stu-id="469c8-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="469c8-117">Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="469c8-117">Azure Information Protection</span></span>
<span data-ttu-id="469c8-118">我们最近弃用 Azure 信息保护集成，因为我们的 Endpoint DLP 功能包含针对存储在终结点设备上敏感数据的改进的发现和保护解决方案，以便提高解决方案的可见性和集成。</span><span class="sxs-lookup"><span data-stu-id="469c8-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="469c8-119">这是在下面的博客中 [宣布的](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)。</span><span class="sxs-lookup"><span data-stu-id="469c8-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="469c8-120">我们建议客户开始使用 Endpoint DLP。</span><span class="sxs-lookup"><span data-stu-id="469c8-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="469c8-121">条件访问</span><span class="sxs-lookup"><span data-stu-id="469c8-121">Conditional Access</span></span>
<span data-ttu-id="469c8-122">Microsoft Defender for Endpoint 的动态设备风险评分已集成到条件访问评估中，确保只有安全设备有权访问资源。</span><span class="sxs-lookup"><span data-stu-id="469c8-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="469c8-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="469c8-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="469c8-124">Microsoft Cloud App Security Microsoft Defender for Endpoint 终结点信号，以允许直接查看云应用程序使用情况，包括从所有 Microsoft Defender for Endpoint 受监视设备使用不受支持的云服务 (卷影 IT) 。</span><span class="sxs-lookup"><span data-stu-id="469c8-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="469c8-125">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="469c8-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="469c8-126">可疑活动是用户上下文中运行的进程。</span><span class="sxs-lookup"><span data-stu-id="469c8-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="469c8-127">Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 之间的集成提供了跨活动和标识进行网络安全调查的灵活性。</span><span class="sxs-lookup"><span data-stu-id="469c8-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="469c8-128">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="469c8-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="469c8-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp)通过 保险箱 链接、保险箱 附件、高级防钓鱼和欺骗智能功能帮助保护组织免受电子邮件或文件中恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="469c8-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="469c8-130">Microsoft Defender for Office 365 和 Microsoft Defender for Endpoint 之间的集成使安全分析师能够前往上游调查攻击的入口点。</span><span class="sxs-lookup"><span data-stu-id="469c8-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="469c8-131">通过威胁情报共享，可以包含和阻止攻击。</span><span class="sxs-lookup"><span data-stu-id="469c8-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="469c8-132">Defender for Office 365显示最近 30 天内的事件数据。</span><span class="sxs-lookup"><span data-stu-id="469c8-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="469c8-133">对于警报，Defender for Office 365基于第一次活动时间显示数据。</span><span class="sxs-lookup"><span data-stu-id="469c8-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="469c8-134">此后，数据将不再在 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="469c8-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="469c8-135">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="469c8-135">Skype for Business</span></span>
<span data-ttu-id="469c8-136">通过Skype for Business集成，分析人员可以通过门户中的简单按钮与可能受到威胁的用户或设备所有者进行通信。</span><span class="sxs-lookup"><span data-stu-id="469c8-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="469c8-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="469c8-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="469c8-138">借助 Microsoft 365 Defender、Microsoft Defender for Endpoint 和各种 Microsoft 安全解决方案，形成统一的攻破前和入侵后企业防御套件，可跨终结点、标识、电子邮件和应用程序进行本机集成，以检测、阻止、调查和自动响应复杂的攻击。</span><span class="sxs-lookup"><span data-stu-id="469c8-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint, and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="469c8-139">详细了解 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="469c8-139">Learn more about Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-365-defender)


## <a name="related-topics"></a><span data-ttu-id="469c8-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="469c8-140">Related topics</span></span>
- [<span data-ttu-id="469c8-141">配置集成和其他高级功能</span><span class="sxs-lookup"><span data-stu-id="469c8-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="469c8-142">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="469c8-142">Microsoft 365 Defender overview</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="469c8-143">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="469c8-143">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="469c8-144">使用条件访问保护用户、数据和设备</span><span class="sxs-lookup"><span data-stu-id="469c8-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
