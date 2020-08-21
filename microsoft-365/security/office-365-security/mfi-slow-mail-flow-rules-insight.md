---
title: 修复慢邮件流规则见解
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
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理员可了解如何使用安全 & 合规中心内的修复慢邮件流规则见解，以识别并修复其组织中也称为传输规则 () 的低效或断开的邮件流规则。
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826877"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="4ac60-103">修复了安全管理与合规中心中的邮件流&见解</span><span class="sxs-lookup"><span data-stu-id="4ac60-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

<span data-ttu-id="4ac60-104">低效邮件流规则 (亦称为"传输规则") 会为组织带来邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="4ac60-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="4ac60-105">此见解报告会对你组织的邮件流产生影响的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="4ac60-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="4ac60-106">这些类型的规则的示例包括：</span><span class="sxs-lookup"><span data-stu-id="4ac60-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="4ac60-107">大型组 **使用是其** 成员的条件。</span><span class="sxs-lookup"><span data-stu-id="4ac60-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="4ac60-108">使用复杂正则表达式条件 (正则表达式) 模式匹配。</span><span class="sxs-lookup"><span data-stu-id="4ac60-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="4ac60-109">使用附件中内容检查的条件。</span><span class="sxs-lookup"><span data-stu-id="4ac60-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="4ac60-110">**"为安全**& 合规中心"中的"**为你**区中的邮件流"区域[，"](mail-flow-insights-v2.md)建议的邮件流规则见解"见解会在邮件流规则过长而无法完成时通知你。</span><span class="sxs-lookup"><span data-stu-id="4ac60-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="4ac60-111">只有在检测到条件时如果没有任何邮件循环，则此 (看到的情况就不会) 。</span><span class="sxs-lookup"><span data-stu-id="4ac60-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="4ac60-112">可以使用此通知帮助你确定并调整邮件流规则，以帮助减少邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="4ac60-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![修复邮件流规则缓慢见解，在"为你区中的邮件流仪表板建议"区域](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="4ac60-114">在单击 **小部件上的** 查看详细信息时，将出现一个浮出控件，并显示更多信息：</span><span class="sxs-lookup"><span data-stu-id="4ac60-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="4ac60-115">**规则**：可以将鼠标悬停在摘要上，以查看规则的所有条件、例外情况和操作。</span><span class="sxs-lookup"><span data-stu-id="4ac60-115">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="4ac60-116">可以单击摘要，以编辑 Exchange 管理中心邮箱 (设置) 。</span><span class="sxs-lookup"><span data-stu-id="4ac60-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="4ac60-117">**评估的邮件数**：您可以单击 **"查看示例邮件**"来查看受规则[message trace](message-trace-scc.md)影响的邮件示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="4ac60-117">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="4ac60-118">**每封邮件的平均时间**</span><span class="sxs-lookup"><span data-stu-id="4ac60-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="4ac60-119">**邮件上居中时间：** 将上半部分和时间数据分隔开的中间值。</span><span class="sxs-lookup"><span data-stu-id="4ac60-119">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![单击"修复缓慢邮件流规则见解"后显示的详细信息浮出控件](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="4ac60-121">有关 Exchange Online 中邮件流规则的条件和例外的详细信息，请参阅[邮件流规则条件和例外 (预测) Exchange Online 中的部分。](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="4ac60-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4ac60-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="4ac60-122">Related topics</span></span>

<span data-ttu-id="4ac60-123">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="4ac60-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
