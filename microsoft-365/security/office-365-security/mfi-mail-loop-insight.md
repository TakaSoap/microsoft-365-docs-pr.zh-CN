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
description: 管理员可以 &了解如何使用安全与合规中心内"邮件流"仪表板中的"修复可能的邮件循环见解"来标识和修复其组织的邮件循环。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203799"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="04d7f-103">修复安全与合规中心内可能&见解</span><span class="sxs-lookup"><span data-stu-id="04d7f-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04d7f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="04d7f-104">**Applies to**</span></span>
- [<span data-ttu-id="04d7f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="04d7f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="04d7f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="04d7f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="04d7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04d7f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="04d7f-108">邮件循环错误，因为：</span><span class="sxs-lookup"><span data-stu-id="04d7f-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="04d7f-109">它们会浪费系统资源。</span><span class="sxs-lookup"><span data-stu-id="04d7f-109">They waste system resources.</span></span>
- <span data-ttu-id="04d7f-110">它们使用您组织的邮件卷配额。</span><span class="sxs-lookup"><span data-stu-id="04d7f-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="04d7f-111">它们向原始邮件发件人 (混淆的未送达报告或退回) 邮件。</span><span class="sxs-lookup"><span data-stu-id="04d7f-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="04d7f-112">安全 **与** 合规中心内"邮件流"仪表板的"推荐使用 [](mail-flow-insights-v2.md)"区域中的"修复可能的邮件循环见解 ["&在](https://protection.office.com)组织中检测到邮件循环时通知您。</span><span class="sxs-lookup"><span data-stu-id="04d7f-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="04d7f-113">此见解仅在检测到条件 (（如果没有任何邮件循环）后显示，你将看不到) 。</span><span class="sxs-lookup"><span data-stu-id="04d7f-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![修复邮件流仪表板的"推荐使用"区域中的慢邮件流规则见解](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="04d7f-115">单击小 **组件上的** "查看详细信息"时，将显示一个包含详细信息的飞出控件：</span><span class="sxs-lookup"><span data-stu-id="04d7f-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="04d7f-116">**域**</span><span class="sxs-lookup"><span data-stu-id="04d7f-116">**Domain**</span></span>
- <span data-ttu-id="04d7f-117">**邮件数**：**可以单击"** 查看示例邮件"以查看受 [](message-trace-scc.md)循环影响的邮件示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="04d7f-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="04d7f-118">**域类型**" 例如，权威或非权威。</span><span class="sxs-lookup"><span data-stu-id="04d7f-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="04d7f-119">**MX 记录**： (**邮箱)\*\*\*\*域的** MX 记录的优先级值。</span><span class="sxs-lookup"><span data-stu-id="04d7f-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="04d7f-120">**循环原因\*\*\*\*和如何修复**：我们将确定最常见的邮件循环方案并提供建议的操作来修复循环。</span><span class="sxs-lookup"><span data-stu-id="04d7f-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![单击"修复可能的邮件循环见解"上的"查看详细信息"后显示的详细信息 flyout](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="04d7f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04d7f-122">See also</span></span>

<span data-ttu-id="04d7f-123">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="04d7f-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
