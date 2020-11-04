---
title: 自动转发的邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的自动转发的邮件报告。
ms.openlocfilehash: 01a094b8531672708fc024e8ed0c5833786dbb0c
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877785"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="1b015-103">自动转发的邮件在安全 & 合规中心中的洞察力</span><span class="sxs-lookup"><span data-stu-id="1b015-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1b015-104">在安全 & 合规性中心的 [邮件流仪表板](mail-flow-insights-v2.md)中， **自动转发的邮件** 可在 [安全合规性中心](https://protection.office.com)显示有关自动从您的组织转发给外部域中的收件人的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="1b015-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Security & 合规中心中的自动转发的邮件小部件](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="1b015-106">自动转发的邮件详细信息</span><span class="sxs-lookup"><span data-stu-id="1b015-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="1b015-107">当您单击小组件中的邮件数量时，将显示一个弹出窗口，其中显示有关自动转发邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="1b015-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="1b015-108">**通过转发方法自动转发的邮件** ：</span><span class="sxs-lookup"><span data-stu-id="1b015-108">**Auto-forwarded messages by forwarding methods** :</span></span>

  - <span data-ttu-id="1b015-109">**按邮件流规则**</span><span class="sxs-lookup"><span data-stu-id="1b015-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="1b015-110">**按收件箱规则**</span><span class="sxs-lookup"><span data-stu-id="1b015-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="1b015-111">**通过 SMTP 转发** ：这是管理员可以在邮箱上配置的自动转发，如 [配置邮箱的电子邮件转发](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)中所述。</span><span class="sxs-lookup"><span data-stu-id="1b015-111">**By SMTP forwarding** : This is automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="1b015-112">有关更多详细信息，请 [转到转发报告](view-mail-flow-reports.md#forwarding-report) 的链接。</span><span class="sxs-lookup"><span data-stu-id="1b015-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="1b015-113">**按域和用户自动转发的邮件** ：</span><span class="sxs-lookup"><span data-stu-id="1b015-113">**Auto-forwarded messages by domains and users** :</span></span>

  - <span data-ttu-id="1b015-114">**转发到的前5个域**</span><span class="sxs-lookup"><span data-stu-id="1b015-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="1b015-115">**上周 (新域)**</span><span class="sxs-lookup"><span data-stu-id="1b015-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="1b015-116">**前5个转发用户**</span><span class="sxs-lookup"><span data-stu-id="1b015-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="1b015-117">**上周 (新用户)**</span><span class="sxs-lookup"><span data-stu-id="1b015-117">**New users (last week)**</span></span>
  - <span data-ttu-id="1b015-118">有关更多详细信息，请 [转到转发修改报告](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 的链接。</span><span class="sxs-lookup"><span data-stu-id="1b015-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![安全 & 合规中心中的自动转发的邮件的详细信息弹出报告](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="1b015-120">见解</span><span class="sxs-lookup"><span data-stu-id="1b015-120">Insights</span></span>

<span data-ttu-id="1b015-121">根据报告数据生成两个见解：</span><span class="sxs-lookup"><span data-stu-id="1b015-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="1b015-122">新用户转发电子邮件</span><span class="sxs-lookup"><span data-stu-id="1b015-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="1b015-123">转发的新域电子邮件</span><span class="sxs-lookup"><span data-stu-id="1b015-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="1b015-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b015-124">See also</span></span>

<span data-ttu-id="1b015-125">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="1b015-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
