---
title: 电子邮件保护的顺序和优先级
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， ATP， Microsoft Defender ATP， Office 365 ATP， Azure ATP
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
description: 管理员可以了解 Exchange Online Protection (EOP) 中的保护的应用程序顺序，以及保护策略中的优先级值如何确定应用的策略。
ms.openlocfilehash: a18234344e1100f3b6a03c10e970c8195e53e7df
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760562"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="a22a3-104">电子邮件保护的顺序和优先级</span><span class="sxs-lookup"><span data-stu-id="a22a3-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a22a3-105">在 Exchange Online 中具有邮箱的 Microsoft 365 组织或独立 Exchange Online Protection (EOP) 组织中，入站电子邮件可能由多种形式的保护标记。</span><span class="sxs-lookup"><span data-stu-id="a22a3-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="a22a3-106">例如，EOP 中可用于所有 Microsoft 365 客户的内置防钓鱼策略，以及适用于 Office 365 客户的 Microsoft Defender 的更可靠的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="a22a3-106">For example, the built-in anti-phishing policies in EOP that are available to all Microsoft 365 customers, and the more robust anti-phishing policies that are available to Microsoft Defender for Office 365 customers.</span></span> <span data-ttu-id="a22a3-107">邮件还通过恶意软件、垃圾邮件、网络钓鱼等的多个检测扫描。鉴于所有这些活动，可能混淆了应用了哪个策略。</span><span class="sxs-lookup"><span data-stu-id="a22a3-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="a22a3-108">通常，应用于邮件的策略在 CAT (Category) 属性中的 **X-Forefront-Antispam-Report** **标头** 中标识。</span><span class="sxs-lookup"><span data-stu-id="a22a3-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="a22a3-109">有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="a22a3-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="a22a3-110">有两个主要因素可确定对邮件应用哪个策略：</span><span class="sxs-lookup"><span data-stu-id="a22a3-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="a22a3-111">**电子邮件保护类型的** 优先级：此顺序不可配置，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="a22a3-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="a22a3-112">Priority</span><span class="sxs-lookup"><span data-stu-id="a22a3-112">Priority</span></span>|<span data-ttu-id="a22a3-113">电子邮件保护</span><span class="sxs-lookup"><span data-stu-id="a22a3-113">Email protection</span></span>|<span data-ttu-id="a22a3-114">类别</span><span class="sxs-lookup"><span data-stu-id="a22a3-114">Category</span></span>|<span data-ttu-id="a22a3-115">管理位置</span><span class="sxs-lookup"><span data-stu-id="a22a3-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="a22a3-116">1 </span><span class="sxs-lookup"><span data-stu-id="a22a3-116">1</span></span>|<span data-ttu-id="a22a3-117">恶意软件</span><span class="sxs-lookup"><span data-stu-id="a22a3-117">Malware</span></span>|<span data-ttu-id="a22a3-118">CAT：MALW</span><span class="sxs-lookup"><span data-stu-id="a22a3-118">CAT:MALW</span></span>|[<span data-ttu-id="a22a3-119">在 EOP 中配置反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="a22a3-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="a22a3-120">2 </span><span class="sxs-lookup"><span data-stu-id="a22a3-120">2</span></span>|<span data-ttu-id="a22a3-121">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="a22a3-121">Phishing</span></span>|<span data-ttu-id="a22a3-122">CAT：PHSH</span><span class="sxs-lookup"><span data-stu-id="a22a3-122">CAT:PHSH</span></span>|[<span data-ttu-id="a22a3-123">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="a22a3-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="a22a3-124">3 </span><span class="sxs-lookup"><span data-stu-id="a22a3-124">3</span></span>|<span data-ttu-id="a22a3-125">高可信度垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a22a3-125">High confidence spam</span></span>|<span data-ttu-id="a22a3-126">CAT：HSPM</span><span class="sxs-lookup"><span data-stu-id="a22a3-126">CAT:HSPM</span></span>|[<span data-ttu-id="a22a3-127">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="a22a3-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="a22a3-128">4 </span><span class="sxs-lookup"><span data-stu-id="a22a3-128">4</span></span>|<span data-ttu-id="a22a3-129">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="a22a3-129">Spoofing</span></span>|<span data-ttu-id="a22a3-130">CAT：SPOOF</span><span class="sxs-lookup"><span data-stu-id="a22a3-130">CAT:SPOOF</span></span>|[<span data-ttu-id="a22a3-131">在 EOP 中配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="a22a3-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="a22a3-132">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a22a3-132">5<sup>\*</sup></span></span>|<span data-ttu-id="a22a3-133">用户模拟 (受保护的用户) </span><span class="sxs-lookup"><span data-stu-id="a22a3-133">User impersonation (protected users)</span></span>|<span data-ttu-id="a22a3-134">UIMP</span><span class="sxs-lookup"><span data-stu-id="a22a3-134">UIMP</span></span>|[<span data-ttu-id="a22a3-135">在 Microsoft Defender for Office 365 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="a22a3-135">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="a22a3-136">6<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a22a3-136">6<sup>\*</sup></span></span>|<span data-ttu-id="a22a3-137">域模拟 (受保护的域) </span><span class="sxs-lookup"><span data-stu-id="a22a3-137">Domain impersonation (protected domains)</span></span>|<span data-ttu-id="a22a3-138">DIMP</span><span class="sxs-lookup"><span data-stu-id="a22a3-138">DIMP</span></span>|[<span data-ttu-id="a22a3-139">在 Microsoft Defender for Office 365 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="a22a3-139">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="a22a3-140">7 </span><span class="sxs-lookup"><span data-stu-id="a22a3-140">7</span></span>|<span data-ttu-id="a22a3-141">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a22a3-141">Spam</span></span>|<span data-ttu-id="a22a3-142">CAT：SPM</span><span class="sxs-lookup"><span data-stu-id="a22a3-142">CAT:SPM</span></span>|[<span data-ttu-id="a22a3-143">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="a22a3-143">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="a22a3-144">8 </span><span class="sxs-lookup"><span data-stu-id="a22a3-144">8</span></span>|<span data-ttu-id="a22a3-145">批量邮件</span><span class="sxs-lookup"><span data-stu-id="a22a3-145">Bulk</span></span>|<span data-ttu-id="a22a3-146">CAT：BULK</span><span class="sxs-lookup"><span data-stu-id="a22a3-146">CAT:BULK</span></span>|[<span data-ttu-id="a22a3-147">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="a22a3-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="a22a3-148"><sup>\*</sup> 这些功能仅在 Microsoft Defender for Office 365 中的防钓鱼策略中可用。</span><span class="sxs-lookup"><span data-stu-id="a22a3-148"><sup>\*</sup> These features are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="a22a3-149">策略的优先级：对于每种保护类型 (反垃圾邮件、反恶意软件、防钓鱼等 ) ，都有一个适用于所有用户的默认策略，但您可以创建适用于特定用户的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a22a3-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="a22a3-150">每个自定义策略都有一个优先级值，用于确定应用策略的顺序。</span><span class="sxs-lookup"><span data-stu-id="a22a3-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="a22a3-151">默认策略始终应用最后一个。</span><span class="sxs-lookup"><span data-stu-id="a22a3-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="a22a3-152">如果用户在相同类型的多个策略中定义，则仅应用优先级最高的策略。</span><span class="sxs-lookup"><span data-stu-id="a22a3-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="a22a3-153">不会为用户评估该类型的任何剩余策略 (包括默认策略) 。</span><span class="sxs-lookup"><span data-stu-id="a22a3-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="a22a3-154">例如，请考虑适用于相同用户的 Microsoft Defender for Office 365中的以下防钓鱼策略，以及标识为用户模拟和欺骗的邮件：</span><span class="sxs-lookup"><span data-stu-id="a22a3-154">For example, consider the following anti-phishing policies in Microsoft Defender for Office 365 **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="a22a3-155">策略名称</span><span class="sxs-lookup"><span data-stu-id="a22a3-155">Policy name</span></span>|<span data-ttu-id="a22a3-156">Priority</span><span class="sxs-lookup"><span data-stu-id="a22a3-156">Priority</span></span>|<span data-ttu-id="a22a3-157">用户模拟</span><span class="sxs-lookup"><span data-stu-id="a22a3-157">User impersonation</span></span>|<span data-ttu-id="a22a3-158">反欺骗</span><span class="sxs-lookup"><span data-stu-id="a22a3-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="a22a3-159">策略 A</span><span class="sxs-lookup"><span data-stu-id="a22a3-159">Policy A</span></span>|<span data-ttu-id="a22a3-160">1 </span><span class="sxs-lookup"><span data-stu-id="a22a3-160">1</span></span>|<span data-ttu-id="a22a3-161">开</span><span class="sxs-lookup"><span data-stu-id="a22a3-161">On</span></span>|<span data-ttu-id="a22a3-162">关</span><span class="sxs-lookup"><span data-stu-id="a22a3-162">Off</span></span>|
  |<span data-ttu-id="a22a3-163">策略 B</span><span class="sxs-lookup"><span data-stu-id="a22a3-163">Policy B</span></span>|<span data-ttu-id="a22a3-164">2 </span><span class="sxs-lookup"><span data-stu-id="a22a3-164">2</span></span>|<span data-ttu-id="a22a3-165">关</span><span class="sxs-lookup"><span data-stu-id="a22a3-165">Off</span></span>|<span data-ttu-id="a22a3-166">开</span><span class="sxs-lookup"><span data-stu-id="a22a3-166">On</span></span>|
  |

1. <span data-ttu-id="a22a3-167">邮件被标记为欺骗邮件并被视为欺骗邮件，因为欺骗的优先级比用户模拟高 (4) 5 (高) 。</span><span class="sxs-lookup"><span data-stu-id="a22a3-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (5).</span></span>
2. <span data-ttu-id="a22a3-168">策略 A 应用于用户，因为它的优先级高于策略 B。</span><span class="sxs-lookup"><span data-stu-id="a22a3-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="a22a3-169">根据策略 A 中的设置，不会对邮件执行任何操作，因为策略中已关闭反欺骗。</span><span class="sxs-lookup"><span data-stu-id="a22a3-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="a22a3-170">策略处理将停止，因此策略 B 从不应用于用户。</span><span class="sxs-lookup"><span data-stu-id="a22a3-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="a22a3-171">由于同一用户可能会有意或无意地包含在同一类型的多个自定义策略中，因此请对自定义策略使用以下设计准则：</span><span class="sxs-lookup"><span data-stu-id="a22a3-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="a22a3-172">为应用于少数用户的策略分配更高的优先级，为适用于大量用户的策略分配较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="a22a3-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="a22a3-173">请记住，默认策略始终应用最后。</span><span class="sxs-lookup"><span data-stu-id="a22a3-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="a22a3-174">将优先级较高的策略配置为具有比低优先级策略更严格或更专业的设置。</span><span class="sxs-lookup"><span data-stu-id="a22a3-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="a22a3-175">请考虑使用更少的自定义策略 (仅对需要更严格或更专门的设置的用户使用) 。</span><span class="sxs-lookup"><span data-stu-id="a22a3-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
