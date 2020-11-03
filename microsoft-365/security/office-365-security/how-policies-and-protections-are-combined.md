---
title: 电子邮件保护的顺序和优先级
keywords: security、恶意软件、Microsoft 365、M365、security center、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的应用程序保护顺序，以及保护策略中的优先级值如何确定应用的策略。
ms.openlocfilehash: 9bff44a0c9964c60f5b8b5c0afdfe6d29ee6da93
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843601"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="930bd-104">电子邮件保护的顺序和优先级</span><span class="sxs-lookup"><span data-stu-id="930bd-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="930bd-105">在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，入站电子邮件可能会被多种保护形式标记。</span><span class="sxs-lookup"><span data-stu-id="930bd-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="930bd-106">例如，EOP 中可供所有 Microsoft 365 客户使用的内置反网络钓鱼策略，以及 Microsoft Defender for Office 365 客户可以使用的更强健的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="930bd-106">For example, the built-in anti-phishing policies in EOP that are available to all Microsoft 365 customers, and the more robust anti-phishing policies that are available to Microsoft Defender for Office 365 customers.</span></span> <span data-ttu-id="930bd-107">邮件还会通过多个检测扫描，针对恶意软件、垃圾邮件、网络钓鱼等。在所有此活动中，可能会对应用的策略产生一些混淆。</span><span class="sxs-lookup"><span data-stu-id="930bd-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="930bd-108">通常情况下，应用于邮件的策略在 **CAT (Category)** 属性中的 **X-Forefront-反垃圾邮件报告** 标头中进行标识。</span><span class="sxs-lookup"><span data-stu-id="930bd-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="930bd-109">有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="930bd-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="930bd-110">有两个主要因素可用于确定将哪个策略应用于邮件：</span><span class="sxs-lookup"><span data-stu-id="930bd-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="930bd-111">**电子邮件保护类型的优先级** ：此顺序不可配置，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="930bd-111">**The priority of the email protection type** : This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="930bd-112">Priority</span><span class="sxs-lookup"><span data-stu-id="930bd-112">Priority</span></span>|<span data-ttu-id="930bd-113">电子邮件保护</span><span class="sxs-lookup"><span data-stu-id="930bd-113">Email protection</span></span>|<span data-ttu-id="930bd-114">类别</span><span class="sxs-lookup"><span data-stu-id="930bd-114">Category</span></span>|<span data-ttu-id="930bd-115">管理位置</span><span class="sxs-lookup"><span data-stu-id="930bd-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="930bd-116">1</span><span class="sxs-lookup"><span data-stu-id="930bd-116">1</span></span>|<span data-ttu-id="930bd-117">恶意软件</span><span class="sxs-lookup"><span data-stu-id="930bd-117">Malware</span></span>|<span data-ttu-id="930bd-118">CAT： MALW</span><span class="sxs-lookup"><span data-stu-id="930bd-118">CAT:MALW</span></span>|[<span data-ttu-id="930bd-119">在 EOP 中配置反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="930bd-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="930bd-120">双面</span><span class="sxs-lookup"><span data-stu-id="930bd-120">2</span></span>|<span data-ttu-id="930bd-121">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="930bd-121">Phishing</span></span>|<span data-ttu-id="930bd-122">CAT： PHSH</span><span class="sxs-lookup"><span data-stu-id="930bd-122">CAT:PHSH</span></span>|[<span data-ttu-id="930bd-123">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="930bd-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="930bd-124">第三章</span><span class="sxs-lookup"><span data-stu-id="930bd-124">3</span></span>|<span data-ttu-id="930bd-125">高可信度垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="930bd-125">High confidence spam</span></span>|<span data-ttu-id="930bd-126">CAT： HSPM</span><span class="sxs-lookup"><span data-stu-id="930bd-126">CAT:HSPM</span></span>|[<span data-ttu-id="930bd-127">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="930bd-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="930bd-128">4 </span><span class="sxs-lookup"><span data-stu-id="930bd-128">4</span></span>|<span data-ttu-id="930bd-129">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="930bd-129">Spoofing</span></span>|<span data-ttu-id="930bd-130">分类程序：欺骗</span><span class="sxs-lookup"><span data-stu-id="930bd-130">CAT:SPOOF</span></span>|[<span data-ttu-id="930bd-131">在 EOP 中配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="930bd-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="930bd-132">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="930bd-132">5<sup>\*</sup></span></span>|<span data-ttu-id="930bd-133">用户模拟 (受保护的域) </span><span class="sxs-lookup"><span data-stu-id="930bd-133">User impersonation (protected domains)</span></span>|<span data-ttu-id="930bd-134">UIMP</span><span class="sxs-lookup"><span data-stu-id="930bd-134">UIMP</span></span>|[<span data-ttu-id="930bd-135">在 Microsoft Defender for Office 365 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="930bd-135">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="930bd-136">型<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="930bd-136">6<sup>\*</sup></span></span>|<span data-ttu-id="930bd-137">域模拟 (受保护的用户) </span><span class="sxs-lookup"><span data-stu-id="930bd-137">Domain impersonation (protected users)</span></span>|<span data-ttu-id="930bd-138">DIMP</span><span class="sxs-lookup"><span data-stu-id="930bd-138">DIMP</span></span>|[<span data-ttu-id="930bd-139">在 Microsoft Defender for Office 365 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="930bd-139">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="930bd-140">7 </span><span class="sxs-lookup"><span data-stu-id="930bd-140">7</span></span>|<span data-ttu-id="930bd-141">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="930bd-141">Spam</span></span>|<span data-ttu-id="930bd-142">CAT： SPM</span><span class="sxs-lookup"><span data-stu-id="930bd-142">CAT:SPM</span></span>|[<span data-ttu-id="930bd-143">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="930bd-143">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="930bd-144">8 </span><span class="sxs-lookup"><span data-stu-id="930bd-144">8</span></span>|<span data-ttu-id="930bd-145">批量邮件</span><span class="sxs-lookup"><span data-stu-id="930bd-145">Bulk</span></span>|<span data-ttu-id="930bd-146">分类程序：批量</span><span class="sxs-lookup"><span data-stu-id="930bd-146">CAT:BULK</span></span>|[<span data-ttu-id="930bd-147">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="930bd-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="930bd-148"><sup>\*</sup> 这些功能仅在 Microsoft Defender for Office 365 中提供了反网络钓鱼策略中。</span><span class="sxs-lookup"><span data-stu-id="930bd-148"><sup>\*</sup> These features are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="930bd-149">**策略的优先级** ：对于每种保护类型 (反垃圾邮件、反恶意软件、反网络钓鱼等 ) ，有一个适用于每个人的默认策略，但您可以创建适用于特定用户的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="930bd-149">**The priority of the policy** : For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="930bd-150">每个自定义策略都有一个优先级值，用于确定策略在中的应用顺序。</span><span class="sxs-lookup"><span data-stu-id="930bd-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="930bd-151">默认策略总是最后应用。</span><span class="sxs-lookup"><span data-stu-id="930bd-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="930bd-152">如果用户是在同一类型的多个策略中定义的，则仅对其应用具有最高优先级的策略。</span><span class="sxs-lookup"><span data-stu-id="930bd-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="930bd-153">该类型的任何剩余策略不会评估给用户 (包括默认策略) 。</span><span class="sxs-lookup"><span data-stu-id="930bd-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="930bd-154">例如，将 Microsoft Defender 中 **适用于相同用户** 的 Microsoft 365 Defender 中的以下反网络钓鱼策略和同时标识为用户模拟和哄骗的邮件视为：</span><span class="sxs-lookup"><span data-stu-id="930bd-154">For example, consider the following anti-phishing policies in Microsoft Defender for Office 365 **that apply to the same users** , and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="930bd-155">策略名称</span><span class="sxs-lookup"><span data-stu-id="930bd-155">Policy name</span></span>|<span data-ttu-id="930bd-156">Priority</span><span class="sxs-lookup"><span data-stu-id="930bd-156">Priority</span></span>|<span data-ttu-id="930bd-157">用户模拟</span><span class="sxs-lookup"><span data-stu-id="930bd-157">User impersonation</span></span>|<span data-ttu-id="930bd-158">反欺骗</span><span class="sxs-lookup"><span data-stu-id="930bd-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="930bd-159">策略 A</span><span class="sxs-lookup"><span data-stu-id="930bd-159">Policy A</span></span>|<span data-ttu-id="930bd-160">1</span><span class="sxs-lookup"><span data-stu-id="930bd-160">1</span></span>|<span data-ttu-id="930bd-161">开</span><span class="sxs-lookup"><span data-stu-id="930bd-161">On</span></span>|<span data-ttu-id="930bd-162">关</span><span class="sxs-lookup"><span data-stu-id="930bd-162">Off</span></span>|
  |<span data-ttu-id="930bd-163">Policy B</span><span class="sxs-lookup"><span data-stu-id="930bd-163">Policy B</span></span>|<span data-ttu-id="930bd-164">双面</span><span class="sxs-lookup"><span data-stu-id="930bd-164">2</span></span>|<span data-ttu-id="930bd-165">关</span><span class="sxs-lookup"><span data-stu-id="930bd-165">Off</span></span>|<span data-ttu-id="930bd-166">开</span><span class="sxs-lookup"><span data-stu-id="930bd-166">On</span></span>|
  |

1. <span data-ttu-id="930bd-167">邮件被标记为欺骗，因为哄骗的优先级高于用户模拟 (8)  (4) 。</span><span class="sxs-lookup"><span data-stu-id="930bd-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="930bd-168">策略 A 应用于用户，因为它的优先级高于策略 B。</span><span class="sxs-lookup"><span data-stu-id="930bd-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="930bd-169">根据策略 A 中的设置，不会对邮件执行任何操作，因为在策略中禁用了反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="930bd-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="930bd-170">策略处理停止，因此策略 B 永远不会应用到用户。</span><span class="sxs-lookup"><span data-stu-id="930bd-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="930bd-171">由于相同的用户可能有意或无意地包含在同一类型的多个自定义策略中，因此，请对自定义策略使用以下设计准则：</span><span class="sxs-lookup"><span data-stu-id="930bd-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="930bd-172">为适用于少数用户的策略分配更高的优先级，并为应用于大量用户的策略分配较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="930bd-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="930bd-173">请记住，默认策略总是最后应用。</span><span class="sxs-lookup"><span data-stu-id="930bd-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="930bd-174">配置更高优先级的策略，使其具有比低优先级策略更严格或更多的专用设置。</span><span class="sxs-lookup"><span data-stu-id="930bd-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="930bd-175">请考虑使用较少的自定义策略 (仅对需要更严格或更多专用设置) 的用户使用自定义策略。</span><span class="sxs-lookup"><span data-stu-id="930bd-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
