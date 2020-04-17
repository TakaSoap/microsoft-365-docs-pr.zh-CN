---
title: Office 365 中的电子邮件保护的顺序和优先级
keywords: security、恶意软件、Microsoft 365、M365、security center、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 介绍 Office 365 保护的应用程序顺序，以及保护策略中的优先级值如何确定应用的策略。
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537409"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a><span data-ttu-id="149a8-104">Office 365 中的电子邮件保护的顺序和优先级</span><span class="sxs-lookup"><span data-stu-id="149a8-104">Order and precedence of email protection in Office 365</span></span>

<span data-ttu-id="149a8-105">在 Office 365 中，会对入站电子邮件进行评估，因此可以通过多种保护形式（恶意软件、垃圾邮件、网络钓鱼等）对其进行标记。</span><span class="sxs-lookup"><span data-stu-id="149a8-105">In Office 365, inbound email is evaluated by, and therefore might be flagged by, multiple forms of protection (malware, spam, phishing, etc).</span></span> <span data-ttu-id="149a8-106">在所有此活动中，很难确定应用的策略和顺序。</span><span class="sxs-lookup"><span data-stu-id="149a8-106">Given all of this activity, it can be hard to determine which policy was applied and in what order.</span></span>

<span data-ttu-id="149a8-107">通常情况下，应用于邮件的策略在**CAT （Category）** 属性的**X-Forefront-反垃圾邮件报告**标头中标识。</span><span class="sxs-lookup"><span data-stu-id="149a8-107">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="149a8-108">有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="149a8-108">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="149a8-109">有两个主要因素可用于确定将哪个策略应用于邮件：</span><span class="sxs-lookup"><span data-stu-id="149a8-109">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="149a8-110">**电子邮件保护类型的优先级**：此顺序不可配置，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="149a8-110">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="149a8-111">**优先级**</span><span class="sxs-lookup"><span data-stu-id="149a8-111">**Priority**</span></span>|<span data-ttu-id="149a8-112">**电子邮件保护**</span><span class="sxs-lookup"><span data-stu-id="149a8-112">**Email protection**</span></span>|<span data-ttu-id="149a8-113">**类别**</span><span class="sxs-lookup"><span data-stu-id="149a8-113">**Category**</span></span>|<span data-ttu-id="149a8-114">**管理位置**</span><span class="sxs-lookup"><span data-stu-id="149a8-114">**Where to manage**</span></span>|
  |<span data-ttu-id="149a8-115">1</span><span class="sxs-lookup"><span data-stu-id="149a8-115">1</span></span>|<span data-ttu-id="149a8-116">恶意软件</span><span class="sxs-lookup"><span data-stu-id="149a8-116">Malware</span></span>|<span data-ttu-id="149a8-117">CAT： MALW</span><span class="sxs-lookup"><span data-stu-id="149a8-117">CAT:MALW</span></span>|[<span data-ttu-id="149a8-118">在 Office 365 中配置反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="149a8-118">Configure anti-malware policies in Office 365</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="149a8-119">双面</span><span class="sxs-lookup"><span data-stu-id="149a8-119">2</span></span>|<span data-ttu-id="149a8-120">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="149a8-120">Phishing</span></span>|<span data-ttu-id="149a8-121">CAT： PHSH</span><span class="sxs-lookup"><span data-stu-id="149a8-121">CAT:PHSH</span></span>|[<span data-ttu-id="149a8-122">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="149a8-122">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="149a8-123">第三章</span><span class="sxs-lookup"><span data-stu-id="149a8-123">3</span></span>|<span data-ttu-id="149a8-124">高可信度垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="149a8-124">High confidence spam</span></span>|<span data-ttu-id="149a8-125">CAT： HSPM</span><span class="sxs-lookup"><span data-stu-id="149a8-125">CAT:HSPM</span></span>|[<span data-ttu-id="149a8-126">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="149a8-126">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="149a8-127">4 </span><span class="sxs-lookup"><span data-stu-id="149a8-127">4</span></span>|<span data-ttu-id="149a8-128">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="149a8-128">Spoofing</span></span>|<span data-ttu-id="149a8-129">分类程序：欺骗</span><span class="sxs-lookup"><span data-stu-id="149a8-129">CAT:SPOOF</span></span>|[<span data-ttu-id="149a8-130">在 Office 365 中配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="149a8-130">Configure spoof intelligence in Office 365</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="149a8-131">5 </span><span class="sxs-lookup"><span data-stu-id="149a8-131">5</span></span>|<span data-ttu-id="149a8-132">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="149a8-132">Spam</span></span>|<span data-ttu-id="149a8-133">CAT： SPM</span><span class="sxs-lookup"><span data-stu-id="149a8-133">CAT:SPM</span></span>|[<span data-ttu-id="149a8-134">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="149a8-134">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="149a8-135">6 </span><span class="sxs-lookup"><span data-stu-id="149a8-135">6</span></span>|<span data-ttu-id="149a8-136">批量邮件</span><span class="sxs-lookup"><span data-stu-id="149a8-136">Bulk</span></span>|<span data-ttu-id="149a8-137">分类程序：批量</span><span class="sxs-lookup"><span data-stu-id="149a8-137">CAT:BULK</span></span>|[<span data-ttu-id="149a8-138">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="149a8-138">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="149a8-139">步<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="149a8-139">7<sup>\*</sup></span></span>|<span data-ttu-id="149a8-140">域模拟（受保护的用户）</span><span class="sxs-lookup"><span data-stu-id="149a8-140">Domain impersonation (protected users)</span></span>|<span data-ttu-id="149a8-141">DIMP</span><span class="sxs-lookup"><span data-stu-id="149a8-141">DIMP</span></span>|[<span data-ttu-id="149a8-142">在 Office 365 中配置 ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="149a8-142">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="149a8-143">utf-8<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="149a8-143">8<sup>\*</sup></span></span>|<span data-ttu-id="149a8-144">用户模拟（受保护的域）</span><span class="sxs-lookup"><span data-stu-id="149a8-144">User impersonation (protected domains)</span></span>|<span data-ttu-id="149a8-145">UIMP</span><span class="sxs-lookup"><span data-stu-id="149a8-145">UIMP</span></span>|[<span data-ttu-id="149a8-146">在 Office 365 中配置 ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="149a8-146">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="149a8-147"><sup>\*</sup>这些功能仅在 ATP 反网络钓鱼策略中可用。</span><span class="sxs-lookup"><span data-stu-id="149a8-147"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="149a8-148">**策略的优先级**：对于每种保护类型（反垃圾邮件、反恶意软件、反网络钓鱼等），都有一个适用于每个人的默认策略，但您通常可以创建适用于特定用户的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="149a8-148">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can often create custom policies that apply to specific users.</span></span> <span data-ttu-id="149a8-149">每个自定义策略都有一个优先级值，用于确定策略在中的应用顺序。</span><span class="sxs-lookup"><span data-stu-id="149a8-149">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="149a8-150">默认策略总是最后应用。</span><span class="sxs-lookup"><span data-stu-id="149a8-150">The default policy is always applied last.</span></span>

  <span data-ttu-id="149a8-151">如果用户是在同一类型的多个策略中定义的，则仅对其应用具有最高优先级的策略。</span><span class="sxs-lookup"><span data-stu-id="149a8-151">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="149a8-152">不会为用户计算任何其他类型的策略（包括默认策略）。</span><span class="sxs-lookup"><span data-stu-id="149a8-152">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="149a8-153">例如，考虑以下 ATP 反网络钓鱼策略，这些策略**适用于相同的用户**以及同时标识为用户模拟和哄骗的邮件：</span><span class="sxs-lookup"><span data-stu-id="149a8-153">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="149a8-154">**ATP 反网络钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="149a8-154">**ATP anti-phishing policy**</span></span>|<span data-ttu-id="149a8-155">**优先级**</span><span class="sxs-lookup"><span data-stu-id="149a8-155">**Priority**</span></span>|<span data-ttu-id="149a8-156">**用户模拟**</span><span class="sxs-lookup"><span data-stu-id="149a8-156">**User impersonation**</span></span>|<span data-ttu-id="149a8-157">**反欺骗**</span><span class="sxs-lookup"><span data-stu-id="149a8-157">**Anti-spoofing**</span></span>|
  |<span data-ttu-id="149a8-158">策略 A</span><span class="sxs-lookup"><span data-stu-id="149a8-158">Policy A</span></span>|<span data-ttu-id="149a8-159">1</span><span class="sxs-lookup"><span data-stu-id="149a8-159">1</span></span>|<span data-ttu-id="149a8-160">开</span><span class="sxs-lookup"><span data-stu-id="149a8-160">On</span></span>|<span data-ttu-id="149a8-161">关闭</span><span class="sxs-lookup"><span data-stu-id="149a8-161">Off</span></span>|
  |<span data-ttu-id="149a8-162">Policy B</span><span class="sxs-lookup"><span data-stu-id="149a8-162">Policy B</span></span>|<span data-ttu-id="149a8-163">双面</span><span class="sxs-lookup"><span data-stu-id="149a8-163">2</span></span>|<span data-ttu-id="149a8-164">关</span><span class="sxs-lookup"><span data-stu-id="149a8-164">Off</span></span>|<span data-ttu-id="149a8-165">开</span><span class="sxs-lookup"><span data-stu-id="149a8-165">On</span></span>|
  |

1. <span data-ttu-id="149a8-166">邮件被标记为欺骗，因为哄骗具有更高的优先级（4），而不是用户模拟（8）。</span><span class="sxs-lookup"><span data-stu-id="149a8-166">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="149a8-167">策略 A 应用于用户，因为它的优先级高于策略 B。</span><span class="sxs-lookup"><span data-stu-id="149a8-167">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="149a8-168">根据策略 A 中的设置，不会对邮件执行任何操作，因为在策略中禁用了反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="149a8-168">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="149a8-169">策略处理停止，因此策略 B 永远不会应用到用户。</span><span class="sxs-lookup"><span data-stu-id="149a8-169">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="149a8-170">由于相同的用户可能有意或无意地包含在同一类型的多个自定义策略中，因此，请对自定义策略使用以下设计准则：</span><span class="sxs-lookup"><span data-stu-id="149a8-170">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="149a8-171">为适用于少数用户的策略分配更高的优先级，并为应用于大量用户的策略分配较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="149a8-171">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="149a8-172">请记住，默认策略总是最后应用。</span><span class="sxs-lookup"><span data-stu-id="149a8-172">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="149a8-173">配置更高优先级的策略，使其具有比低优先级策略更严格或更多的专用设置。</span><span class="sxs-lookup"><span data-stu-id="149a8-173">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="149a8-174">请考虑使用较少的自定义策略（仅对需要更严格或更多专用设置的用户使用自定义策略）。</span><span class="sxs-lookup"><span data-stu-id="149a8-174">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
