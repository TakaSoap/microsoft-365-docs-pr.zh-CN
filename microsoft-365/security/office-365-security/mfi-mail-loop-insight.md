---
title: 修复可能的邮件循环见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在安全与合规中心的邮件流仪表板中使用"修复可能的邮件循环"见解&标识和修复其组织的邮件循环。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029890"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="58c5a-103">修复安全与合规中心内可能的邮件&见解</span><span class="sxs-lookup"><span data-stu-id="58c5a-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="58c5a-104">邮件循环错误，因为：</span><span class="sxs-lookup"><span data-stu-id="58c5a-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="58c5a-105">它们浪费系统资源。</span><span class="sxs-lookup"><span data-stu-id="58c5a-105">They waste system resources.</span></span>
- <span data-ttu-id="58c5a-106">它们使用组织的邮件卷配额。</span><span class="sxs-lookup"><span data-stu-id="58c5a-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="58c5a-107">它们向原始邮件 (发送混淆的未送达报告) 或退回邮件。</span><span class="sxs-lookup"><span data-stu-id="58c5a-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="58c5a-108">安全 **与** 合规中心内邮件流仪表板的"建议你"区域中 [](mail-flow-insights-v2.md)的"修复可能的邮件 [](https://protection.office.com)循环见解"&在组织中检测到邮件循环时通知您。 </span><span class="sxs-lookup"><span data-stu-id="58c5a-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="58c5a-109">此见解仅在检测到条件 (（如果没有任何邮件循环）后，您才能看到) 。</span><span class="sxs-lookup"><span data-stu-id="58c5a-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![修复邮件流仪表板的"建议"区域中的慢邮件流规则见解](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="58c5a-111">单击小 **组件上的** "查看详细信息"时，将显示一个包含详细信息的飞出控件：</span><span class="sxs-lookup"><span data-stu-id="58c5a-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="58c5a-112">**域**</span><span class="sxs-lookup"><span data-stu-id="58c5a-112">**Domain**</span></span>
- <span data-ttu-id="58c5a-113">**消息数**：可以单击"**查看示例** 邮件"以查看受循环 [](message-trace-scc.md)影响的邮件示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="58c5a-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="58c5a-114">**域类型**" 例如，权威或非权威。</span><span class="sxs-lookup"><span data-stu-id="58c5a-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="58c5a-115">**MX 记录**： (**邮箱)** MX 记录的优先级值和优先级值。</span><span class="sxs-lookup"><span data-stu-id="58c5a-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="58c5a-116">**循环原因\*\*\*\*和修复** 方法：我们将确定最常见的邮件循环方案并提供建议的操作来修复循环。</span><span class="sxs-lookup"><span data-stu-id="58c5a-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![单击"修复可能的邮件循环见解"上的"查看详细信息"后显示的详细信息飞出](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="58c5a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58c5a-118">See also</span></span>

<span data-ttu-id="58c5a-119">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="58c5a-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
