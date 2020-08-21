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
description: 管理员可以了解 Exchange Online Protection (和 EOP) 中的应用程序防护顺序，以及保护策略中的优先级值如何确定应用哪种策略。
ms.openlocfilehash: 9556d2262eb59224357e20027a1f0e63404081f2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827405"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="d1cfd-104">电子邮件保护的顺序和优先级</span><span class="sxs-lookup"><span data-stu-id="d1cfd-104">Order and precedence of email protection</span></span>

<span data-ttu-id="d1cfd-105">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，入站电子邮件可能会被多种形式的保护标记。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="d1cfd-106">例如，适用于所有 Microsoft 365 客户的内置 EOP 防钓鱼策略，以及也为 Office 365 高级威胁防护 (Office 365 ATP 客户提供的更强大的 ATP) 防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection (Office 365 ATP) customers.</span></span> <span data-ttu-id="d1cfd-107">邮件还会通过对恶意软件、垃圾邮件、网络钓鱼等进行多次检测扫描。鉴于所有此活动，可能会混淆策略所应用于的对象。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="d1cfd-108">通常情况下，应用于邮件的策略在"CAT 和类别和属性的**X-Forefront-Antispam-Report"\*\*\*\*标头)  (标识**。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="d1cfd-109">有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="d1cfd-110">确定对邮件应用哪个策略有两个主要因素：</span><span class="sxs-lookup"><span data-stu-id="d1cfd-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="d1cfd-111">**电子邮件保护类型的优先级：** 此顺序不可配置，下表中进行了详细介绍：</span><span class="sxs-lookup"><span data-stu-id="d1cfd-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="d1cfd-112">Priority</span><span class="sxs-lookup"><span data-stu-id="d1cfd-112">Priority</span></span>|<span data-ttu-id="d1cfd-113">电子邮件保护</span><span class="sxs-lookup"><span data-stu-id="d1cfd-113">Email protection</span></span>|<span data-ttu-id="d1cfd-114">类别</span><span class="sxs-lookup"><span data-stu-id="d1cfd-114">Category</span></span>|<span data-ttu-id="d1cfd-115">管理位置</span><span class="sxs-lookup"><span data-stu-id="d1cfd-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="d1cfd-116">1</span><span class="sxs-lookup"><span data-stu-id="d1cfd-116">1</span></span>|<span data-ttu-id="d1cfd-117">恶意软件</span><span class="sxs-lookup"><span data-stu-id="d1cfd-117">Malware</span></span>|<span data-ttu-id="d1cfd-118">CAT：MALW</span><span class="sxs-lookup"><span data-stu-id="d1cfd-118">CAT:MALW</span></span>|[<span data-ttu-id="d1cfd-119">在 EOP 中配置反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="d1cfd-120">2</span><span class="sxs-lookup"><span data-stu-id="d1cfd-120">2</span></span>|<span data-ttu-id="d1cfd-121">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="d1cfd-121">Phishing</span></span>|<span data-ttu-id="d1cfd-122">CAT：PHSH</span><span class="sxs-lookup"><span data-stu-id="d1cfd-122">CAT:PHSH</span></span>|[<span data-ttu-id="d1cfd-123">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="d1cfd-124">3</span><span class="sxs-lookup"><span data-stu-id="d1cfd-124">3</span></span>|<span data-ttu-id="d1cfd-125">高可信度垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d1cfd-125">High confidence spam</span></span>|<span data-ttu-id="d1cfd-126">CAT：HSPM</span><span class="sxs-lookup"><span data-stu-id="d1cfd-126">CAT:HSPM</span></span>|[<span data-ttu-id="d1cfd-127">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="d1cfd-128">4 </span><span class="sxs-lookup"><span data-stu-id="d1cfd-128">4</span></span>|<span data-ttu-id="d1cfd-129">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="d1cfd-129">Spoofing</span></span>|<span data-ttu-id="d1cfd-130">CAT：SPOOF</span><span class="sxs-lookup"><span data-stu-id="d1cfd-130">CAT:SPOOF</span></span>|[<span data-ttu-id="d1cfd-131">在 EOP 中配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="d1cfd-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="d1cfd-132">5 </span><span class="sxs-lookup"><span data-stu-id="d1cfd-132">5</span></span>|<span data-ttu-id="d1cfd-133">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d1cfd-133">Spam</span></span>|<span data-ttu-id="d1cfd-134">CAT：SPM</span><span class="sxs-lookup"><span data-stu-id="d1cfd-134">CAT:SPM</span></span>|[<span data-ttu-id="d1cfd-135">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-135">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="d1cfd-136">6 </span><span class="sxs-lookup"><span data-stu-id="d1cfd-136">6</span></span>|<span data-ttu-id="d1cfd-137">批量邮件</span><span class="sxs-lookup"><span data-stu-id="d1cfd-137">Bulk</span></span>|<span data-ttu-id="d1cfd-138">CAT：BULK</span><span class="sxs-lookup"><span data-stu-id="d1cfd-138">CAT:BULK</span></span>|[<span data-ttu-id="d1cfd-139">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-139">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="d1cfd-140">7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1cfd-140">7<sup>\*</sup></span></span>|<span data-ttu-id="d1cfd-141">域模拟 (受保护用户) </span><span class="sxs-lookup"><span data-stu-id="d1cfd-141">Domain impersonation (protected users)</span></span>|<span data-ttu-id="d1cfd-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="d1cfd-142">DIMP</span></span>|[<span data-ttu-id="d1cfd-143">配置 ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-143">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="d1cfd-144">8<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1cfd-144">8<sup>\*</sup></span></span>|<span data-ttu-id="d1cfd-145">用户模拟 (受保护的域) </span><span class="sxs-lookup"><span data-stu-id="d1cfd-145">User impersonation (protected domains)</span></span>|<span data-ttu-id="d1cfd-146">UIMP</span><span class="sxs-lookup"><span data-stu-id="d1cfd-146">UIMP</span></span>|[<span data-ttu-id="d1cfd-147">配置 ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-147">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="d1cfd-148"><sup>\*</sup> 这些功能仅在 ATP 防钓鱼策略中提供。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="d1cfd-149">**策略的优先级：** 对于每种保护类型 (反垃圾邮件、反恶意软件、反网络钓鱼 ) 等，有一个适用于所有人的默认策略，但您可以创建应用于特定用户的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="d1cfd-150">每个自定义策略都具有一个优先级值，用于确定应用策略时的顺序。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="d1cfd-151">默认策略始终最后应用。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="d1cfd-152">如果用户在同一类型的多个策略中定义，则只会向其应用优先级最高的策略。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="d1cfd-153">不会为用户查询该类型的任何其他策略 (包括默认策略) 。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="d1cfd-154">例如，请考虑以下适用于相同用户的 ATP 防钓鱼 **策略以及**标识为用户模拟和欺骗邮件的邮件：</span><span class="sxs-lookup"><span data-stu-id="d1cfd-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="d1cfd-155">ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="d1cfd-155">ATP anti-phishing policy</span></span>|<span data-ttu-id="d1cfd-156">Priority</span><span class="sxs-lookup"><span data-stu-id="d1cfd-156">Priority</span></span>|<span data-ttu-id="d1cfd-157">用户模拟</span><span class="sxs-lookup"><span data-stu-id="d1cfd-157">User impersonation</span></span>|<span data-ttu-id="d1cfd-158">反欺骗</span><span class="sxs-lookup"><span data-stu-id="d1cfd-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="d1cfd-159">策略 A</span><span class="sxs-lookup"><span data-stu-id="d1cfd-159">Policy A</span></span>|<span data-ttu-id="d1cfd-160">1</span><span class="sxs-lookup"><span data-stu-id="d1cfd-160">1</span></span>|<span data-ttu-id="d1cfd-161">开</span><span class="sxs-lookup"><span data-stu-id="d1cfd-161">On</span></span>|<span data-ttu-id="d1cfd-162">关</span><span class="sxs-lookup"><span data-stu-id="d1cfd-162">Off</span></span>|
  |<span data-ttu-id="d1cfd-163">策略 B</span><span class="sxs-lookup"><span data-stu-id="d1cfd-163">Policy B</span></span>|<span data-ttu-id="d1cfd-164">2</span><span class="sxs-lookup"><span data-stu-id="d1cfd-164">2</span></span>|<span data-ttu-id="d1cfd-165">关</span><span class="sxs-lookup"><span data-stu-id="d1cfd-165">Off</span></span>|<span data-ttu-id="d1cfd-166">开</span><span class="sxs-lookup"><span data-stu-id="d1cfd-166">On</span></span>|
  |

1. <span data-ttu-id="d1cfd-167">该邮件将标记并视为欺骗邮件，因为欺骗的优先级高于用户模拟 (4) 4% (8) 。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="d1cfd-168">策略 A 应用于用户，因为它的优先级高于策略 B。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="d1cfd-169">根据策略 A 中的设置，不会对邮件执行任何操作，因为在策略中已禁用反欺骗。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="d1cfd-170">策略处理停止，因此策略 B 永远不会应用于用户。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="d1cfd-171">由于有意或无意包括在同一类型的多个自定义策略中包含相同用户，请使用以下针对自定义策略的设计指南：</span><span class="sxs-lookup"><span data-stu-id="d1cfd-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="d1cfd-172">为适用于少量用户的策略分配较高优先级，并为适用于大量用户的策略分配较低优先级。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="d1cfd-173">请记住，默认策略始终最后应用。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="d1cfd-174">配置高优先级策略，使具有比低优先级策略更严格或更高级的设置。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="d1cfd-175">请考虑使用更少 (的自定义策略，只对需要更严格或更专用设置的用户使用自定义) 。</span><span class="sxs-lookup"><span data-stu-id="d1cfd-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
