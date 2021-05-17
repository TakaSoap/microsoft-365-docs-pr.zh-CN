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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 了解如何让用户与外部用户共享其日历，以便进行会议和约会。
ms.openlocfilehash: 5fc80965ae277e66dfbf73de80618dec03d26759
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915046"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="c99ac-103">与外部用户共享日历</span><span class="sxs-lookup"><span data-stu-id="c99ac-103">Share calendars with external users</span></span>

<span data-ttu-id="c99ac-104">有时，用户必须安排与组织外部人员的会议。</span><span class="sxs-lookup"><span data-stu-id="c99ac-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="c99ac-105">为了简化查找常见会议时间的过程，Microsoft 365使日历可供这些人员使用。</span><span class="sxs-lookup"><span data-stu-id="c99ac-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="c99ac-106">这些用户需要查看组织中用户的忙/闲时间，但没有组织的Microsoft 365帐户。</span><span class="sxs-lookup"><span data-stu-id="c99ac-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="c99ac-107">可以在管理中心为组织中所有用户启用日历Microsoft 365共享。</span><span class="sxs-lookup"><span data-stu-id="c99ac-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c99ac-108">启用共享后，你的用户可以Outlook Web App组织内外的任何人共享其日历。</span><span class="sxs-lookup"><span data-stu-id="c99ac-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="c99ac-109">组织内部人员可以查看共享日历及其日历。</span><span class="sxs-lookup"><span data-stu-id="c99ac-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="c99ac-110">组织外部的人员将收到可用于查看日历的 URL。</span><span class="sxs-lookup"><span data-stu-id="c99ac-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="c99ac-111">贵组织的用户决定何时共享以及共享多少。</span><span class="sxs-lookup"><span data-stu-id="c99ac-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="c99ac-112">如果要与使用 Exchange Server 2013（内部部署解决方案）的组织共享日历，Exchange 管理员需要设置与云的身份验证关系。</span><span class="sxs-lookup"><span data-stu-id="c99ac-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="c99ac-113">这称为联合，必须满足最低软件要求。</span><span class="sxs-lookup"><span data-stu-id="c99ac-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="c99ac-114">有关详细信息，请参阅[共享](/exchange/sharing-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="c99ac-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="c99ac-115">使用管理中心启用Microsoft 365共享</span><span class="sxs-lookup"><span data-stu-id="c99ac-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c99ac-116">在管理中心，**转到"设置** \> **组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="c99ac-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="c99ac-117">在"服务 **"选项卡** 上，选择"**日历"。**</span><span class="sxs-lookup"><span data-stu-id="c99ac-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="c99ac-118">在 **"日历**"页上，选择是否允许用户与组织外部拥有日历或Microsoft 365 Exchange。</span><span class="sxs-lookup"><span data-stu-id="c99ac-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="c99ac-119">选择是否允许匿名用户 (凭据的用户) 通过电子邮件邀请访问日历。</span><span class="sxs-lookup"><span data-stu-id="c99ac-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="c99ac-120">选择要为用户提供的日历信息类型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="c99ac-121">你可以允许所有信息，或限制为仅时间或仅时间、主题和位置。</span><span class="sxs-lookup"><span data-stu-id="c99ac-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="c99ac-122">邀请其他人访问日历</span><span class="sxs-lookup"><span data-stu-id="c99ac-122">Invite people to access calendars</span></span>

<span data-ttu-id="c99ac-123">启用共享后，日历所有者可以将邀请扩展到特定用户。</span><span class="sxs-lookup"><span data-stu-id="c99ac-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="c99ac-124">有关说明，请参阅[在 Outlook Web App 中共享日历](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)。</span><span class="sxs-lookup"><span data-stu-id="c99ac-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>