---
title: 电子邮件保护的顺序和优先级
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， ATP， Microsoft Defender for Endpoint， Office 365 ATP， Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的保护的应用程序顺序，以及保护策略中的优先级值如何确定应用哪个策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3419cba5781e7ab1042f7312c721069d88fb8767
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687645"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="2c54c-104">电子邮件保护的顺序和优先级</span><span class="sxs-lookup"><span data-stu-id="2c54c-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2c54c-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2c54c-105">**Applies to**</span></span>
- [<span data-ttu-id="2c54c-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2c54c-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2c54c-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2c54c-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2c54c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c54c-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2c54c-109">在具有 Exchange Online 邮箱或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，入站电子邮件可能由多种形式的保护标记。</span><span class="sxs-lookup"><span data-stu-id="2c54c-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="2c54c-110">例如，EOP 中可用于所有 Microsoft 365 客户的内置防钓鱼策略，以及适用于 Office 365 客户的 Microsoft Defender 的更可靠的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="2c54c-110">For example, the built-in anti-phishing policies in EOP that are available to all Microsoft 365 customers, and the more robust anti-phishing policies that are available to Microsoft Defender for Office 365 customers.</span></span> <span data-ttu-id="2c54c-111">邮件还会通过恶意软件、垃圾邮件、网络钓鱼等的多个检测扫描。鉴于所有这些活动，可能混淆了要应用哪个策略。</span><span class="sxs-lookup"><span data-stu-id="2c54c-111">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="2c54c-112">通常，应用于邮件的策略在 CAT (Category 属性的 **X-Forefront-Antispam-Report** **标头)** 标识。</span><span class="sxs-lookup"><span data-stu-id="2c54c-112">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="2c54c-113">有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="2c54c-113">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="2c54c-114">有两个主要因素可确定将哪个策略应用于邮件：</span><span class="sxs-lookup"><span data-stu-id="2c54c-114">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="2c54c-115">**电子邮件保护类型的优先级**：此顺序不可配置，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="2c54c-115">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="2c54c-116">Priority</span><span class="sxs-lookup"><span data-stu-id="2c54c-116">Priority</span></span>|<span data-ttu-id="2c54c-117">电子邮件保护</span><span class="sxs-lookup"><span data-stu-id="2c54c-117">Email protection</span></span>|<span data-ttu-id="2c54c-118">类别</span><span class="sxs-lookup"><span data-stu-id="2c54c-118">Category</span></span>|<span data-ttu-id="2c54c-119">管理位置</span><span class="sxs-lookup"><span data-stu-id="2c54c-119">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="2c54c-120">1</span><span class="sxs-lookup"><span data-stu-id="2c54c-120">1</span></span>|<span data-ttu-id="2c54c-121">恶意软件</span><span class="sxs-lookup"><span data-stu-id="2c54c-121">Malware</span></span>|<span data-ttu-id="2c54c-122">CAT：MALW</span><span class="sxs-lookup"><span data-stu-id="2c54c-122">CAT:MALW</span></span>|[<span data-ttu-id="2c54c-123">在 EOP 中配置反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="2c54c-123">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="2c54c-124">2</span><span class="sxs-lookup"><span data-stu-id="2c54c-124">2</span></span>|<span data-ttu-id="2c54c-125">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="2c54c-125">Phishing</span></span>|<span data-ttu-id="2c54c-126">CAT：PHSH</span><span class="sxs-lookup"><span data-stu-id="2c54c-126">CAT:PHSH</span></span>|[<span data-ttu-id="2c54c-127">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="2c54c-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="2c54c-128">3</span><span class="sxs-lookup"><span data-stu-id="2c54c-128">3</span></span>|<span data-ttu-id="2c54c-129">高可信度垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2c54c-129">High confidence spam</span></span>|<span data-ttu-id="2c54c-130">CAT：HSPM</span><span class="sxs-lookup"><span data-stu-id="2c54c-130">CAT:HSPM</span></span>|[<span data-ttu-id="2c54c-131">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="2c54c-131">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="2c54c-132">4 </span><span class="sxs-lookup"><span data-stu-id="2c54c-132">4</span></span>|<span data-ttu-id="2c54c-133">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="2c54c-133">Spoofing</span></span>|<span data-ttu-id="2c54c-134">CAT：SPOOF</span><span class="sxs-lookup"><span data-stu-id="2c54c-134">CAT:SPOOF</span></span>|[<span data-ttu-id="2c54c-135">在 EOP 中配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="2c54c-135">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="2c54c-136">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2c54c-136">5<sup>\*</sup></span></span>|<span data-ttu-id="2c54c-137">用户模拟 (受保护的用户) </span><span class="sxs-lookup"><span data-stu-id="2c54c-137">User impersonation (protected users)</span></span>|<span data-ttu-id="2c54c-138">UIMP</span><span class="sxs-lookup"><span data-stu-id="2c54c-138">UIMP</span></span>|[<span data-ttu-id="2c54c-139">在 Microsoft Defender for Office 365 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2c54c-139">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="2c54c-140">6<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2c54c-140">6<sup>\*</sup></span></span>|<span data-ttu-id="2c54c-141">域模拟 (受保护的域) </span><span class="sxs-lookup"><span data-stu-id="2c54c-141">Domain impersonation (protected domains)</span></span>|<span data-ttu-id="2c54c-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="2c54c-142">DIMP</span></span>|[<span data-ttu-id="2c54c-143">在 Microsoft Defender for Office 365 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="2c54c-143">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="2c54c-144">7 </span><span class="sxs-lookup"><span data-stu-id="2c54c-144">7</span></span>|<span data-ttu-id="2c54c-145">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2c54c-145">Spam</span></span>|<span data-ttu-id="2c54c-146">CAT：SPM</span><span class="sxs-lookup"><span data-stu-id="2c54c-146">CAT:SPM</span></span>|[<span data-ttu-id="2c54c-147">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="2c54c-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="2c54c-148">8 </span><span class="sxs-lookup"><span data-stu-id="2c54c-148">8</span></span>|<span data-ttu-id="2c54c-149">批量邮件</span><span class="sxs-lookup"><span data-stu-id="2c54c-149">Bulk</span></span>|<span data-ttu-id="2c54c-150">CAT：BULK</span><span class="sxs-lookup"><span data-stu-id="2c54c-150">CAT:BULK</span></span>|[<span data-ttu-id="2c54c-151">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="2c54c-151">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="2c54c-152"><sup>\*</sup> 这些功能仅在 Microsoft Defender for Office 365 中的防钓鱼策略中可用。</span><span class="sxs-lookup"><span data-stu-id="2c54c-152"><sup>\*</sup> These features are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="2c54c-153">策略优先级：对于每种保护类型 (反垃圾邮件、反恶意软件、防钓鱼等 ) ，都有一个适用于所有用户的默认策略，但你可以创建适用于特定用户的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2c54c-153">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="2c54c-154">每个自定义策略都有一个优先级值，用于确定策略的应用顺序。</span><span class="sxs-lookup"><span data-stu-id="2c54c-154">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="2c54c-155">默认策略始终应用最后。</span><span class="sxs-lookup"><span data-stu-id="2c54c-155">The default policy is always applied last.</span></span>

  <span data-ttu-id="2c54c-156">如果用户在相同类型的多个策略中定义，则仅应用优先级最高的策略。</span><span class="sxs-lookup"><span data-stu-id="2c54c-156">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="2c54c-157">不会为用户评估此类型的任何剩余策略 (包括默认策略) 。</span><span class="sxs-lookup"><span data-stu-id="2c54c-157">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="2c54c-158">例如，请考虑适用于相同用户的 Microsoft Defender for Office 365中的以下防钓鱼策略，以及标识为用户模拟和欺骗的邮件：</span><span class="sxs-lookup"><span data-stu-id="2c54c-158">For example, consider the following anti-phishing policies in Microsoft Defender for Office 365 **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="2c54c-159">策略名称</span><span class="sxs-lookup"><span data-stu-id="2c54c-159">Policy name</span></span>|<span data-ttu-id="2c54c-160">Priority</span><span class="sxs-lookup"><span data-stu-id="2c54c-160">Priority</span></span>|<span data-ttu-id="2c54c-161">用户模拟</span><span class="sxs-lookup"><span data-stu-id="2c54c-161">User impersonation</span></span>|<span data-ttu-id="2c54c-162">反欺骗</span><span class="sxs-lookup"><span data-stu-id="2c54c-162">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="2c54c-163">策略 A</span><span class="sxs-lookup"><span data-stu-id="2c54c-163">Policy A</span></span>|<span data-ttu-id="2c54c-164">1</span><span class="sxs-lookup"><span data-stu-id="2c54c-164">1</span></span>|<span data-ttu-id="2c54c-165">开</span><span class="sxs-lookup"><span data-stu-id="2c54c-165">On</span></span>|<span data-ttu-id="2c54c-166">关</span><span class="sxs-lookup"><span data-stu-id="2c54c-166">Off</span></span>|
  |<span data-ttu-id="2c54c-167">策略 B</span><span class="sxs-lookup"><span data-stu-id="2c54c-167">Policy B</span></span>|<span data-ttu-id="2c54c-168">2</span><span class="sxs-lookup"><span data-stu-id="2c54c-168">2</span></span>|<span data-ttu-id="2c54c-169">关</span><span class="sxs-lookup"><span data-stu-id="2c54c-169">Off</span></span>|<span data-ttu-id="2c54c-170">开</span><span class="sxs-lookup"><span data-stu-id="2c54c-170">On</span></span>|
  |

1. <span data-ttu-id="2c54c-171">邮件被标记为欺骗邮件并被视为欺骗邮件，因为欺骗的优先级 (4) 比 5 (高) 。</span><span class="sxs-lookup"><span data-stu-id="2c54c-171">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (5).</span></span>
2. <span data-ttu-id="2c54c-172">策略 A 应用于用户，因为它的优先级高于策略 B。</span><span class="sxs-lookup"><span data-stu-id="2c54c-172">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="2c54c-173">根据策略 A 中的设置，不会对邮件执行任何操作，因为策略中已关闭反欺骗。</span><span class="sxs-lookup"><span data-stu-id="2c54c-173">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="2c54c-174">策略处理将停止，因此策略 B 从不应用于用户。</span><span class="sxs-lookup"><span data-stu-id="2c54c-174">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="2c54c-175">由于同一用户可能会有意或无意地包含在同一类型的多个自定义策略中，因此请对自定义策略使用以下设计准则：</span><span class="sxs-lookup"><span data-stu-id="2c54c-175">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="2c54c-176">为适用于少数用户的策略分配更高的优先级，为适用于大量用户的策略分配较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="2c54c-176">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="2c54c-177">请记住，默认策略始终应用最后。</span><span class="sxs-lookup"><span data-stu-id="2c54c-177">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="2c54c-178">将高优先级策略配置为具有比较低优先级策略更严格或更专门的设置。</span><span class="sxs-lookup"><span data-stu-id="2c54c-178">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="2c54c-179">请考虑使用更少的自定义策略 (仅对需要更严格或更专业设置的用户使用) 。</span><span class="sxs-lookup"><span data-stu-id="2c54c-179">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
