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
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解 Office 365 保护的应用程序顺序，以及保护策略中的优先级值如何确定要应用的策略。
ms.openlocfilehash: 856b3bc39cd971e605cd9f1c0f31554a853c1b67
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036712"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="b41bb-104">电子邮件保护的顺序和优先级</span><span class="sxs-lookup"><span data-stu-id="b41bb-104">Order and precedence of email protection</span></span>

<span data-ttu-id="b41bb-105">作为 Microsoft 365 用户，您的入站电子邮件可能会被多种保护形式标记。</span><span class="sxs-lookup"><span data-stu-id="b41bb-105">As a Microsoft 365 user, your inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="b41bb-106">例如，可供所有 Microsoft 365 客户使用的内置 EOP 反网络钓鱼策略，以及 Office 365 高级威胁防护客户也可以使用的更强健的 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="b41bb-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection customers.</span></span> <span data-ttu-id="b41bb-107">邮件还会通过多个检测扫描，针对恶意软件、垃圾邮件、网络钓鱼等。在所有此活动中，可能会对应用的策略产生一些混淆。</span><span class="sxs-lookup"><span data-stu-id="b41bb-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="b41bb-108">通常情况下，应用于邮件的策略在**CAT （Category）** 属性的**X-Forefront-反垃圾邮件报告**标头中标识。</span><span class="sxs-lookup"><span data-stu-id="b41bb-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="b41bb-109">有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="b41bb-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="b41bb-110">有两个主要因素可用于确定将哪个策略应用于邮件：</span><span class="sxs-lookup"><span data-stu-id="b41bb-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="b41bb-111">**电子邮件保护类型的优先级**：此顺序不可配置，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="b41bb-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="b41bb-112">**优先级**</span><span class="sxs-lookup"><span data-stu-id="b41bb-112">**Priority**</span></span>|<span data-ttu-id="b41bb-113">**电子邮件保护**</span><span class="sxs-lookup"><span data-stu-id="b41bb-113">**Email protection**</span></span>|<span data-ttu-id="b41bb-114">**类别**</span><span class="sxs-lookup"><span data-stu-id="b41bb-114">**Category**</span></span>|<span data-ttu-id="b41bb-115">**管理位置**</span><span class="sxs-lookup"><span data-stu-id="b41bb-115">**Where to manage**</span></span>|
  |<span data-ttu-id="b41bb-116">1</span><span class="sxs-lookup"><span data-stu-id="b41bb-116">1</span></span>|<span data-ttu-id="b41bb-117">恶意软件</span><span class="sxs-lookup"><span data-stu-id="b41bb-117">Malware</span></span>|<span data-ttu-id="b41bb-118">CAT： MALW</span><span class="sxs-lookup"><span data-stu-id="b41bb-118">CAT:MALW</span></span>|[<span data-ttu-id="b41bb-119">在 Office 365 中配置反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="b41bb-119">Configure anti-malware policies in Office 365</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="b41bb-120">双面</span><span class="sxs-lookup"><span data-stu-id="b41bb-120">2</span></span>|<span data-ttu-id="b41bb-121">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="b41bb-121">Phishing</span></span>|<span data-ttu-id="b41bb-122">CAT： PHSH</span><span class="sxs-lookup"><span data-stu-id="b41bb-122">CAT:PHSH</span></span>|[<span data-ttu-id="b41bb-123">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="b41bb-123">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b41bb-124">第三章</span><span class="sxs-lookup"><span data-stu-id="b41bb-124">3</span></span>|<span data-ttu-id="b41bb-125">高可信度垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b41bb-125">High confidence spam</span></span>|<span data-ttu-id="b41bb-126">CAT： HSPM</span><span class="sxs-lookup"><span data-stu-id="b41bb-126">CAT:HSPM</span></span>|[<span data-ttu-id="b41bb-127">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="b41bb-127">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b41bb-128">4 </span><span class="sxs-lookup"><span data-stu-id="b41bb-128">4</span></span>|<span data-ttu-id="b41bb-129">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="b41bb-129">Spoofing</span></span>|<span data-ttu-id="b41bb-130">分类程序：欺骗</span><span class="sxs-lookup"><span data-stu-id="b41bb-130">CAT:SPOOF</span></span>|[<span data-ttu-id="b41bb-131">在 Office 365 中配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="b41bb-131">Configure spoof intelligence in Office 365</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="b41bb-132">5 </span><span class="sxs-lookup"><span data-stu-id="b41bb-132">5</span></span>|<span data-ttu-id="b41bb-133">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b41bb-133">Spam</span></span>|<span data-ttu-id="b41bb-134">CAT： SPM</span><span class="sxs-lookup"><span data-stu-id="b41bb-134">CAT:SPM</span></span>|[<span data-ttu-id="b41bb-135">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="b41bb-135">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b41bb-136">6 </span><span class="sxs-lookup"><span data-stu-id="b41bb-136">6</span></span>|<span data-ttu-id="b41bb-137">批量邮件</span><span class="sxs-lookup"><span data-stu-id="b41bb-137">Bulk</span></span>|<span data-ttu-id="b41bb-138">分类程序：批量</span><span class="sxs-lookup"><span data-stu-id="b41bb-138">CAT:BULK</span></span>|[<span data-ttu-id="b41bb-139">在 Office 365 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="b41bb-139">Configure anti-spam policies in Office 365</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="b41bb-140">步<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b41bb-140">7<sup>\*</sup></span></span>|<span data-ttu-id="b41bb-141">域模拟（受保护的用户）</span><span class="sxs-lookup"><span data-stu-id="b41bb-141">Domain impersonation (protected users)</span></span>|<span data-ttu-id="b41bb-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="b41bb-142">DIMP</span></span>|[<span data-ttu-id="b41bb-143">在 Office 365 中配置 ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="b41bb-143">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="b41bb-144">utf-8<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b41bb-144">8<sup>\*</sup></span></span>|<span data-ttu-id="b41bb-145">用户模拟（受保护的域）</span><span class="sxs-lookup"><span data-stu-id="b41bb-145">User impersonation (protected domains)</span></span>|<span data-ttu-id="b41bb-146">UIMP</span><span class="sxs-lookup"><span data-stu-id="b41bb-146">UIMP</span></span>|[<span data-ttu-id="b41bb-147">在 Office 365 中配置 ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="b41bb-147">Configure ATP anti-phishing policies in Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="b41bb-148"><sup>\*</sup>这些功能仅在 ATP 反网络钓鱼策略中可用。</span><span class="sxs-lookup"><span data-stu-id="b41bb-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="b41bb-149">**策略的优先级**：对于每种保护类型（反垃圾邮件、反恶意软件、反网络钓鱼等），都有一个适用于每个人的默认策略，但您通常可以创建适用于特定用户的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b41bb-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can often create custom policies that apply to specific users.</span></span> <span data-ttu-id="b41bb-150">每个自定义策略都有一个优先级值，用于确定策略在中的应用顺序。</span><span class="sxs-lookup"><span data-stu-id="b41bb-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="b41bb-151">默认策略总是最后应用。</span><span class="sxs-lookup"><span data-stu-id="b41bb-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="b41bb-152">如果用户是在同一类型的多个策略中定义的，则仅对其应用具有最高优先级的策略。</span><span class="sxs-lookup"><span data-stu-id="b41bb-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="b41bb-153">不会为用户计算任何其他类型的策略（包括默认策略）。</span><span class="sxs-lookup"><span data-stu-id="b41bb-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="b41bb-154">例如，考虑以下 ATP 反网络钓鱼策略，这些策略**适用于相同的用户**以及同时标识为用户模拟和哄骗的邮件：</span><span class="sxs-lookup"><span data-stu-id="b41bb-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  |||||
  |---|---|---|---|
  |<span data-ttu-id="b41bb-155">**ATP 反网络钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="b41bb-155">**ATP anti-phishing policy**</span></span>|<span data-ttu-id="b41bb-156">**优先级**</span><span class="sxs-lookup"><span data-stu-id="b41bb-156">**Priority**</span></span>|<span data-ttu-id="b41bb-157">**用户模拟**</span><span class="sxs-lookup"><span data-stu-id="b41bb-157">**User impersonation**</span></span>|<span data-ttu-id="b41bb-158">**反欺骗**</span><span class="sxs-lookup"><span data-stu-id="b41bb-158">**Anti-spoofing**</span></span>|
  |<span data-ttu-id="b41bb-159">策略 A</span><span class="sxs-lookup"><span data-stu-id="b41bb-159">Policy A</span></span>|<span data-ttu-id="b41bb-160">1</span><span class="sxs-lookup"><span data-stu-id="b41bb-160">1</span></span>|<span data-ttu-id="b41bb-161">开</span><span class="sxs-lookup"><span data-stu-id="b41bb-161">On</span></span>|<span data-ttu-id="b41bb-162">关闭</span><span class="sxs-lookup"><span data-stu-id="b41bb-162">Off</span></span>|
  |<span data-ttu-id="b41bb-163">Policy B</span><span class="sxs-lookup"><span data-stu-id="b41bb-163">Policy B</span></span>|<span data-ttu-id="b41bb-164">双面</span><span class="sxs-lookup"><span data-stu-id="b41bb-164">2</span></span>|<span data-ttu-id="b41bb-165">关</span><span class="sxs-lookup"><span data-stu-id="b41bb-165">Off</span></span>|<span data-ttu-id="b41bb-166">开</span><span class="sxs-lookup"><span data-stu-id="b41bb-166">On</span></span>|
  |

1. <span data-ttu-id="b41bb-167">邮件被标记为欺骗，因为哄骗具有更高的优先级（4），而不是用户模拟（8）。</span><span class="sxs-lookup"><span data-stu-id="b41bb-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="b41bb-168">策略 A 应用于用户，因为它的优先级高于策略 B。</span><span class="sxs-lookup"><span data-stu-id="b41bb-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="b41bb-169">根据策略 A 中的设置，不会对邮件执行任何操作，因为在策略中禁用了反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="b41bb-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="b41bb-170">策略处理停止，因此策略 B 永远不会应用到用户。</span><span class="sxs-lookup"><span data-stu-id="b41bb-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="b41bb-171">由于相同的用户可能有意或无意地包含在同一类型的多个自定义策略中，因此，请对自定义策略使用以下设计准则：</span><span class="sxs-lookup"><span data-stu-id="b41bb-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="b41bb-172">为适用于少数用户的策略分配更高的优先级，并为应用于大量用户的策略分配较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="b41bb-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="b41bb-173">请记住，默认策略总是最后应用。</span><span class="sxs-lookup"><span data-stu-id="b41bb-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="b41bb-174">配置更高优先级的策略，使其具有比低优先级策略更严格或更多的专用设置。</span><span class="sxs-lookup"><span data-stu-id="b41bb-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="b41bb-175">请考虑使用较少的自定义策略（仅对需要更严格或更多专用设置的用户使用自定义策略）。</span><span class="sxs-lookup"><span data-stu-id="b41bb-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
