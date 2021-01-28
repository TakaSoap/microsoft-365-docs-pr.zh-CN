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
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029938"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="fd881-103">安全与合规中心中的自动转发&见解</span><span class="sxs-lookup"><span data-stu-id="fd881-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fd881-104">安全 &**与** 合规中心的邮件流仪表板 [](mail-flow-insights-v2.md)中的"自动转发邮件"见解显示有关从组织自动转发给外部域中 [收件人](https://protection.office.com)的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="fd881-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![安全与合规中心中的"自动转发&小组件](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="fd881-106">自动转发的邮件详细信息</span><span class="sxs-lookup"><span data-stu-id="fd881-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="fd881-107">单击小组件中的消息数时，将显示一个显示有关自动转发邮件的详细信息的飞出窗格：</span><span class="sxs-lookup"><span data-stu-id="fd881-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="fd881-108">**通过转发方法自动转发邮件**：</span><span class="sxs-lookup"><span data-stu-id="fd881-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="fd881-109">**按邮件流规则**</span><span class="sxs-lookup"><span data-stu-id="fd881-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="fd881-110">**按收件箱规则**</span><span class="sxs-lookup"><span data-stu-id="fd881-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="fd881-111">**通过 SMTP 转发**：此方法指示管理员可在邮箱上配置的自动转发，如"为邮箱配置电子邮件 [转发"中所述](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。</span><span class="sxs-lookup"><span data-stu-id="fd881-111">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="fd881-112">指向转发 [报告的链接，](view-mail-flow-reports.md#forwarding-report) 了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="fd881-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="fd881-113">**按域和用户自动转发的邮件**：</span><span class="sxs-lookup"><span data-stu-id="fd881-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="fd881-114">**转发到的前 5 个域**</span><span class="sxs-lookup"><span data-stu-id="fd881-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="fd881-115">**上个星期 (新域)**</span><span class="sxs-lookup"><span data-stu-id="fd881-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="fd881-116">**前 5 个转发用户**</span><span class="sxs-lookup"><span data-stu-id="fd881-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="fd881-117">**上周 (新用户)**</span><span class="sxs-lookup"><span data-stu-id="fd881-117">**New users (last week)**</span></span>
  - <span data-ttu-id="fd881-118">有关更多详细信息， [请参阅转发修改](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 报告的链接。</span><span class="sxs-lookup"><span data-stu-id="fd881-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![安全与合规中心内自动转发的邮件报告&飞出](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="fd881-120">见解</span><span class="sxs-lookup"><span data-stu-id="fd881-120">Insights</span></span>

<span data-ttu-id="fd881-121">基于报告数据生成两个见解：</span><span class="sxs-lookup"><span data-stu-id="fd881-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="fd881-122">新用户转发电子邮件</span><span class="sxs-lookup"><span data-stu-id="fd881-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="fd881-123">正在转发电子邮件的新域</span><span class="sxs-lookup"><span data-stu-id="fd881-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="fd881-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd881-124">See also</span></span>

<span data-ttu-id="fd881-125">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="fd881-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
