---
title: 正在转发的新域的电子邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解如何使用安全 & 合规中心中的 "邮件流" 仪表板中的新域转发电子邮件，以调查其用户何时将邮件转发到从未转发到的外部域。
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356939"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="dec36-103">在安全 & 合规中心中转发的新域的电子邮件洞察力</span><span class="sxs-lookup"><span data-stu-id="dec36-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dec36-104">将电子邮件转发给特定域中的外部收件人的商业原因有很多。</span><span class="sxs-lookup"><span data-stu-id="dec36-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="dec36-105">但是，当组织中的用户突然开始将邮件转发到域时，您的组织中没有任何人将邮件转发给 (新域) 的域是可疑的。</span><span class="sxs-lookup"><span data-stu-id="dec36-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="dec36-106">这种情况可能表示用户帐户受到威胁。</span><span class="sxs-lookup"><span data-stu-id="dec36-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="dec36-107">如果您怀疑帐户已损坏，请参阅 [响应已泄露的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="dec36-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="dec36-108">当您组织中的用户将邮件转发到新域时，将在 [安全 & 合规中心](https://protection.office.com)中 **转发的新域** 将向您发出通知。</span><span class="sxs-lookup"><span data-stu-id="dec36-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="dec36-109">此洞察力仅在检测到问题时显示，并显示在 " [转发报告](view-mail-flow-reports.md#forwarding-report) " 页上。</span><span class="sxs-lookup"><span data-stu-id="dec36-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![正在转发的新域的电子邮件见解](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="dec36-111">当您单击该小组件时，将显示一个弹出对话框，您可在其中找到有关转发邮件的更多详细信息，包括返回到 [转发报告](view-mail-flow-reports.md#forwarding-report)的链接。</span><span class="sxs-lookup"><span data-stu-id="dec36-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![单击正在转发的新域的电子邮件洞察力之后显示的详细信息浮出控件](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="dec36-113">当您在 (**报告** 仪表板 "或") 上的 "**热门见解 & 建议**" 区域中单击 "**查看全部**" 后，您还可以转到此详细信息页面 \> **Dashboard** <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="dec36-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="dec36-114">若要阻止自动将邮件转发到外部域，请为部分或全部外部域配置远程域。</span><span class="sxs-lookup"><span data-stu-id="dec36-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="dec36-115">有关详细信息，请参阅 [在 Exchange Online 中管理远程域](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="dec36-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dec36-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="dec36-116">Related topics</span></span>

<span data-ttu-id="dec36-117">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="dec36-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
