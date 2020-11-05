---
title: 修复慢邮件流规则见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规性中心中的 "修复缓慢的邮件流规则" 来识别和修复低效或损坏的邮件流规则 (也称为传输规则在其组织中) 。
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920544"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="349ae-103">修复了安全 & 合规中心中的邮件流规则的更慢理解</span><span class="sxs-lookup"><span data-stu-id="349ae-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="349ae-104">邮件流规则效率低下 (也称为传输规则) 可能会导致贵组织的邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="349ae-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="349ae-105">此洞察力可报告影响组织的邮件流的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="349ae-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="349ae-106">这些规则类型的示例包括：</span><span class="sxs-lookup"><span data-stu-id="349ae-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="349ae-107">使用的条件 **是** 大型组的成员。</span><span class="sxs-lookup"><span data-stu-id="349ae-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="349ae-108">使用复杂正则表达式 (regex) 模式匹配的条件。</span><span class="sxs-lookup"><span data-stu-id="349ae-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="349ae-109">使用附件中的内容检查的条件。</span><span class="sxs-lookup"><span data-stu-id="349ae-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="349ae-110">在 [安全 & 合规中心](https://protection.office.com)中的 [邮件流仪表板](mail-flow-insights-v2.md)的 " **建议** " 中，" **修复速度较慢的邮件流规则** " 了解如何在邮件流规则的完成时间过长时通知您。</span><span class="sxs-lookup"><span data-stu-id="349ae-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="349ae-111">此洞察力仅在检测到条件后出现 (如果您没有任何邮件循环，则不会看到) 的洞察力。</span><span class="sxs-lookup"><span data-stu-id="349ae-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="349ae-112">您可以使用此通知来帮助您识别和微调邮件流规则，以帮助减少邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="349ae-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![修复邮件流仪表板的 "为您推荐的情况" 区域中的邮件流规则的速度下降](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="349ae-114">当您单击小组件上的 " **查看详细信息** " 时，将显示一个弹出项，其中包含详细信息：</span><span class="sxs-lookup"><span data-stu-id="349ae-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="349ae-115">**规则** ：您可以将鼠标悬停在摘要上以查看该规则的所有条件、例外和操作。</span><span class="sxs-lookup"><span data-stu-id="349ae-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="349ae-116">您可以单击摘要以编辑 Exchange 管理中心 (EAC) 中的规则。</span><span class="sxs-lookup"><span data-stu-id="349ae-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="349ae-117">已 **评估的邮件数** ：您可以单击 " **查看示例邮件** "，查看受规则影响的邮件示例的 [邮件跟踪](message-trace-scc.md)结果。</span><span class="sxs-lookup"><span data-stu-id="349ae-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="349ae-118">**每封邮件所用的平均时间**</span><span class="sxs-lookup"><span data-stu-id="349ae-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="349ae-119">**在邮件上花费** 的中间时间：将上半部分与时间数据的下半部分隔开的中间值。</span><span class="sxs-lookup"><span data-stu-id="349ae-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![单击 "修复慢速邮件流规则" 中的 "查看详细信息" 后出现的详细信息浮出控件](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="349ae-121">有关邮件流规则中的条件和例外的详细信息，请参阅 [mail flow rule 条件和例外 (谓词) 在 Exchange Online 中](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="349ae-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="349ae-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="349ae-122">See also</span></span>

<span data-ttu-id="349ae-123">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="349ae-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
