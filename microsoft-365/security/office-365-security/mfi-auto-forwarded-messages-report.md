---
title: 自动转发的邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理员可以在安全与合规中心的邮件流仪表板中了解自动转发&报告。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203811"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="35dae-103">安全与合规中心中的自动转发&见解</span><span class="sxs-lookup"><span data-stu-id="35dae-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="35dae-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="35dae-104">**Applies to**</span></span>
- [<span data-ttu-id="35dae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="35dae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="35dae-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="35dae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="35dae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35dae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="35dae-108">安全 &**与** 合规中心内"邮件 [](mail-flow-insights-v2.md)流"仪表板中的"自动转发邮件"见解显示有关从组织自动转发给外部域中 [收件人](https://protection.office.com)的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="35dae-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![安全与合规中心中的"自动转发&小组件](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="35dae-110">自动转发的邮件详细信息</span><span class="sxs-lookup"><span data-stu-id="35dae-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="35dae-111">单击小组件中的邮件数时，将显示一个显示有关自动转发邮件的详细信息的飞出窗格：</span><span class="sxs-lookup"><span data-stu-id="35dae-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="35dae-112">**通过转发方法自动转发邮件**：</span><span class="sxs-lookup"><span data-stu-id="35dae-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="35dae-113">**按邮件流规则**</span><span class="sxs-lookup"><span data-stu-id="35dae-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="35dae-114">**按收件箱规则**</span><span class="sxs-lookup"><span data-stu-id="35dae-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="35dae-115">**通过 SMTP 转发**：此方法指示管理员可以在邮箱上配置的自动转发，如为邮箱配置 [电子邮件转发中所述](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。</span><span class="sxs-lookup"><span data-stu-id="35dae-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="35dae-116">指向转发 [报告的链接，](view-mail-flow-reports.md#forwarding-report) 了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="35dae-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="35dae-117">**由域和用户自动转发的邮件**：</span><span class="sxs-lookup"><span data-stu-id="35dae-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="35dae-118">**转发到的前 5 个域**</span><span class="sxs-lookup"><span data-stu-id="35dae-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="35dae-119">**上周 (新域)**</span><span class="sxs-lookup"><span data-stu-id="35dae-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="35dae-120">**前 5 大转发用户**</span><span class="sxs-lookup"><span data-stu-id="35dae-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="35dae-121">**上周 (新用户)**</span><span class="sxs-lookup"><span data-stu-id="35dae-121">**New users (last week)**</span></span>
  - <span data-ttu-id="35dae-122">有关更多详细信息 [，请参阅转发修改](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 报告的链接。</span><span class="sxs-lookup"><span data-stu-id="35dae-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![安全与合规中心内自动转发的邮件报告的详细信息&显示](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="35dae-124">见解</span><span class="sxs-lookup"><span data-stu-id="35dae-124">Insights</span></span>

<span data-ttu-id="35dae-125">根据报告数据生成两个见解：</span><span class="sxs-lookup"><span data-stu-id="35dae-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="35dae-126">新用户转发电子邮件</span><span class="sxs-lookup"><span data-stu-id="35dae-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="35dae-127">正在转发电子邮件的新域</span><span class="sxs-lookup"><span data-stu-id="35dae-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="35dae-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35dae-128">See also</span></span>

<span data-ttu-id="35dae-129">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="35dae-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>