---
title: 修复可能的邮件循环见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理员可了解如何在安全 & 合规中心的邮件流仪表板中使用"固定可能的邮件循环见解"，以识别并修复其组织中的邮件循环。
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826949"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="6895e-103">修复安全与合规中心内可能&的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="6895e-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="6895e-104">邮件循环很不合适，因为它会耗费系统资源、占用组织的邮件卷配额，并将混解的未送达报告 (也称为 NDR，或将退回邮件) 给原始发件人。</span><span class="sxs-lookup"><span data-stu-id="6895e-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="6895e-105">安全 & **合规** 中心区中 **"为** 您区中的邮件流 ["区域，"](mail-flow-insights-v2.md) 准备好"可能的邮件循环见解会在组织中检测到邮件循环时通知您。</span><span class="sxs-lookup"><span data-stu-id="6895e-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="6895e-106">只有在检测到条件时如果没有任何邮件循环，则此 (看到的情况就不会) 。</span><span class="sxs-lookup"><span data-stu-id="6895e-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![修复邮件流规则缓慢见解，在"为你区中的邮件流仪表板建议"区域显示](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="6895e-108">在单击 **小部件上的** 查看详细信息时，将出现一个浮出控件，并显示更多信息：</span><span class="sxs-lookup"><span data-stu-id="6895e-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="6895e-109">**域**</span><span class="sxs-lookup"><span data-stu-id="6895e-109">**Domain**</span></span>
- <span data-ttu-id="6895e-110">**邮件数**：您可以单击 **"查看示例邮件**"来查看受[message trace](message-trace-scc.md)循环影响的邮件示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="6895e-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="6895e-111">**域类型**"例如，权威或非权威。</span><span class="sxs-lookup"><span data-stu-id="6895e-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="6895e-112">**MX 记录**： (\*\*邮箱服务器) \*\* 的 **MX** 记录的优先级值。</span><span class="sxs-lookup"><span data-stu-id="6895e-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="6895e-113">**循环原因\*\*\*\*和如何修复**：我们将尝试识别最常见的邮件循环方案，并提供建议操作 (如果可用），) 来修复循环。</span><span class="sxs-lookup"><span data-stu-id="6895e-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![单击"可能的可能邮件"循环见解显示后显示的详细信息浮出控件](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="6895e-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="6895e-115">Related topics</span></span>

<span data-ttu-id="6895e-116">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="6895e-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
