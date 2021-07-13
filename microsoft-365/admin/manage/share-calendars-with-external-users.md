---
title: 与外部用户共享日历
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 在组织中启用日历Microsoft 365 管理中心以便用户可以与组织内外的任何人共享其日历。
ms.openlocfilehash: 21dbf12ec495f3a22a45d8a23af807ffd34fef72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392451"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="442e5-103">与外部用户共享日历</span><span class="sxs-lookup"><span data-stu-id="442e5-103">Share calendars with external users</span></span>

<span data-ttu-id="442e5-104">有时，用户必须安排与组织外部人员的会议。</span><span class="sxs-lookup"><span data-stu-id="442e5-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="442e5-105">为了简化查找常见会议时间的过程，Microsoft 365使日历可供这些人员使用。</span><span class="sxs-lookup"><span data-stu-id="442e5-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="442e5-106">这些用户需要查看组织中用户的忙/闲时间，但没有组织的Microsoft 365帐户。</span><span class="sxs-lookup"><span data-stu-id="442e5-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="442e5-107">您可以为组织中所有用户启用日历共享，Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="442e5-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="442e5-108">启用共享后，你的用户可以Outlook Web App组织内外的任何人共享其日历。</span><span class="sxs-lookup"><span data-stu-id="442e5-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="442e5-109">组织内部人员可以查看共享日历及其日历。</span><span class="sxs-lookup"><span data-stu-id="442e5-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="442e5-110">组织外部的人员将收到可用于查看日历的 URL。</span><span class="sxs-lookup"><span data-stu-id="442e5-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="442e5-111">贵组织的用户决定何时共享以及共享多少。</span><span class="sxs-lookup"><span data-stu-id="442e5-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="442e5-112">如果要与使用 Exchange Server 2013（内部部署解决方案）的组织共享日历，Exchange 管理员需要设置与云的身份验证关系。</span><span class="sxs-lookup"><span data-stu-id="442e5-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="442e5-113">这称为联合，必须满足最低软件要求。</span><span class="sxs-lookup"><span data-stu-id="442e5-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="442e5-114">有关详细信息，请参阅[共享](/exchange/sharing-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="442e5-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="442e5-115">启用日历共享Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="442e5-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="442e5-116">在管理中心，**转到"设置** \> **组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="442e5-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="442e5-117">在"服务 **"选项卡** 上，选择"**日历"。**</span><span class="sxs-lookup"><span data-stu-id="442e5-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="442e5-118">在 **"日历**"页上，选择是否允许用户与组织外部拥有日历或Microsoft 365 Exchange。</span><span class="sxs-lookup"><span data-stu-id="442e5-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="442e5-119">选择是否允许匿名用户 (凭据的用户) 通过电子邮件邀请访问日历。</span><span class="sxs-lookup"><span data-stu-id="442e5-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="442e5-120">选择要为用户提供的日历信息类型。</span><span class="sxs-lookup"><span data-stu-id="442e5-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="442e5-121">你可以允许所有信息，或限制为仅时间或仅时间、主题和位置。</span><span class="sxs-lookup"><span data-stu-id="442e5-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="442e5-122">邀请其他人访问日历</span><span class="sxs-lookup"><span data-stu-id="442e5-122">Invite people to access calendars</span></span>

<span data-ttu-id="442e5-123">启用共享后，日历所有者可以将邀请扩展到特定用户。</span><span class="sxs-lookup"><span data-stu-id="442e5-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="442e5-124">有关说明，请参阅在 Outlook Web App 中[共享日历](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)。</span><span class="sxs-lookup"><span data-stu-id="442e5-124">For instructions, see [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span></span>

## <a name="related-content"></a><span data-ttu-id="442e5-125">相关内容</span><span class="sxs-lookup"><span data-stu-id="442e5-125">Related content</span></span>

<span data-ttu-id="442e5-126">[打开或关闭网站](/sharepoint/change-external-sharing-site) 外部共享 (文章) </span><span class="sxs-lookup"><span data-stu-id="442e5-126">[Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site) (article)</span></span>\
<span data-ttu-id="442e5-127">[视频Microsoft 365 管理中心 (](../../business-video/admin-center-overview.md)概述) </span><span class="sxs-lookup"><span data-stu-id="442e5-127">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>\
<span data-ttu-id="442e5-128">[管理电子邮件和日历](../email/index.yml) (链接页) </span><span class="sxs-lookup"><span data-stu-id="442e5-128">[Manage email and calendars](../email/index.yml) (link page)</span></span>