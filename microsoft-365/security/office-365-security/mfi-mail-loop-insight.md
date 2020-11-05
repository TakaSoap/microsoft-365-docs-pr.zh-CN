---
title: 修复可能的邮件循环见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的 "邮件流" 仪表板中的 "修复可能的邮件循环真知灼见" 来识别和修复其组织中的邮件循环。
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920557"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="f9975-103">修复安全 & 合规中心中可能的邮件循环见解</span><span class="sxs-lookup"><span data-stu-id="f9975-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f9975-104">邮件循环已损坏，因为：</span><span class="sxs-lookup"><span data-stu-id="f9975-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="f9975-105">它们会浪费系统资源。</span><span class="sxs-lookup"><span data-stu-id="f9975-105">They waste system resources.</span></span>
- <span data-ttu-id="f9975-106">它们使用您的组织的邮件卷配额。</span><span class="sxs-lookup"><span data-stu-id="f9975-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="f9975-107">它们发送混淆的未送达报告 (也称为 Ndr 或退回邮件) 发送给原始邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="f9975-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="f9975-108">修复了 [安全 & 合规中心](https://protection.office.com)中的 [邮件流仪表板](mail-flow-insights-v2.md)的 **建议** 的邮件 **循环** 见解，当组织中检测到邮件循环时，会向您发出通知。</span><span class="sxs-lookup"><span data-stu-id="f9975-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="f9975-109">此洞察力仅在检测到条件后出现 (如果您没有任何邮件循环，则不会看到) 的洞察力。</span><span class="sxs-lookup"><span data-stu-id="f9975-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![修复邮件流仪表板的 "为您推荐的情况" 区域中的邮件流规则的速度下降](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="f9975-111">当您单击小组件上的 " **查看详细信息** " 时，将显示一个弹出项，其中包含详细信息：</span><span class="sxs-lookup"><span data-stu-id="f9975-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="f9975-112">**域**</span><span class="sxs-lookup"><span data-stu-id="f9975-112">**Domain**</span></span>
- <span data-ttu-id="f9975-113">**邮件数** ：您可以单击 " **查看示例邮件** "，查看受循环影响的邮件示例的 [邮件跟踪](message-trace-scc.md) 结果。</span><span class="sxs-lookup"><span data-stu-id="f9975-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="f9975-114">**域类型** （例如，权威或非权威）。</span><span class="sxs-lookup"><span data-stu-id="f9975-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="f9975-115">**MX 记录** ：主机 (域的 MX 记录的 **邮件服务器** ) 和 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="f9975-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="f9975-116">**循环原因** 和 **解决方法** ：我们将确定最常见的邮件循环方案，并提供建议的操作来修复循环。</span><span class="sxs-lookup"><span data-stu-id="f9975-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![在 "修复可能的邮件循环" 见解上单击 "查看详细信息" 后出现的详细信息浮出](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="f9975-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9975-118">See also</span></span>

<span data-ttu-id="f9975-119">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="f9975-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
