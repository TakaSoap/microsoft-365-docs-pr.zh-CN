---
title: 修复慢邮件流规则见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的"修复慢速邮件流规则"见解来识别和修复低效率或已损坏的邮件流规则 (也称为组织中) 传输规则。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef9f26994f563a5f9dad411f2276fd42c28496f9
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029122"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="80618-103">修复安全与合规中心内缓慢&规则见解</span><span class="sxs-lookup"><span data-stu-id="80618-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="80618-104">无效的邮件流规则 (也称为传输规则) 可能会导致组织的邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="80618-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="80618-105">此见解报告对组织的邮件流有影响的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="80618-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="80618-106">这些类型的规则的示例包括：</span><span class="sxs-lookup"><span data-stu-id="80618-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="80618-107">使用" **是大型组** 的成员"的条件。</span><span class="sxs-lookup"><span data-stu-id="80618-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="80618-108">使用复杂正则表达式的条件 (正则表达式) 模式匹配。</span><span class="sxs-lookup"><span data-stu-id="80618-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="80618-109">在附件中使用内容检查的条件。</span><span class="sxs-lookup"><span data-stu-id="80618-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="80618-110">安全 **与** 合规中心内邮件流仪表板的"建议你"区域中的 [](mail-flow-insights-v2.md)"修复慢邮件流 [](https://protection.office.com)规则"见解&在邮件流规则完成时间过长时通知您。 </span><span class="sxs-lookup"><span data-stu-id="80618-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="80618-111">此见解仅在检测到条件 (（如果没有任何邮件循环）后，您才能看到) 。</span><span class="sxs-lookup"><span data-stu-id="80618-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="80618-112">可以使用此通知来帮助确定和微调邮件流规则，以帮助减少邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="80618-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![修复邮件流仪表板的"建议"区域中的慢邮件流规则见解](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="80618-114">单击小 **组件上的** "查看详细信息"时，将显示一个包含详细信息的飞出控件：</span><span class="sxs-lookup"><span data-stu-id="80618-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="80618-115">**规则**：您可以将鼠标悬停在摘要上方，以查看规则的所有条件、例外和操作。</span><span class="sxs-lookup"><span data-stu-id="80618-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="80618-116">You can click on the summary to edit the rule in the Exchange admin center (EAC) .</span><span class="sxs-lookup"><span data-stu-id="80618-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="80618-117">**评估的邮件数**：可以单击"查看示例邮件"以查看受规则影响 [](message-trace-scc.md)的邮件示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="80618-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="80618-118">**每封邮件所花费的平均时间**</span><span class="sxs-lookup"><span data-stu-id="80618-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="80618-119">**在邮件上花费的中值时间**：将上半部分与时间数据的下半部分分开的中间值。</span><span class="sxs-lookup"><span data-stu-id="80618-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![单击"修复慢速邮件流规则"见解上的"查看详细信息"后显示的详细信息飞出](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="80618-121">有关邮件流规则中的条件和例外，请参阅邮件流规则条件和例外， ([Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)中的) 例外。</span><span class="sxs-lookup"><span data-stu-id="80618-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="80618-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80618-122">See also</span></span>

<span data-ttu-id="80618-123">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="80618-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
