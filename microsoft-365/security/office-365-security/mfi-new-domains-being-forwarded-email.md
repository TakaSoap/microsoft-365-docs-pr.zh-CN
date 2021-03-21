---
title: 正在转发的新域的电子邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"正在转发的新域"电子邮件见解来调查用户何时将邮件转发到从未转发到的外部域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929344"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="bfd3b-103">安全与合规中心内转发电子邮件见解&域</span><span class="sxs-lookup"><span data-stu-id="bfd3b-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bfd3b-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="bfd3b-104">**Applies to**</span></span>
- [<span data-ttu-id="bfd3b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bfd3b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bfd3b-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="bfd3b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bfd3b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfd3b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="bfd3b-108">将电子邮件转发给特定域中的外部收件人有有效的业务原因。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="bfd3b-109">但是，当贵组织的用户突然开始将邮件转发到组织中没有人将邮件转发到新域的域中时， (可疑) 。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="bfd3b-110">此条件可能指示用户帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="bfd3b-111">如果您怀疑帐户已被泄露，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="bfd3b-112">安全 **与合规** 中心 [内&](https://protection.office.com) 转发的电子邮件见解的新域在组织用户将邮件转发到新域时通知你。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="bfd3b-113">此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![正在转发的新域的电子邮件见解](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="bfd3b-115">单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括返回 [转发报告的链接](view-mail-flow-reports.md#forwarding-report)。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![单击"正在转发的新域"电子邮件见解后显示的详细信息飞出](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="bfd3b-117">单击报表仪表板或仪表板上"热门见解"&建议"区域中的"查看全部"后，选择见解后， (**进入** 此 \>  <https://protection.office.com/insightdashboard> 详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="bfd3b-118">若要阻止自动将邮件转发到外部域，请为部分或所有外部域配置远程域。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="bfd3b-119">有关详细信息，请参阅在 [Exchange Online 中管理远程域](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bfd3b-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="bfd3b-120">Related topics</span></span>

<span data-ttu-id="bfd3b-121">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd3b-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>