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
description: '了解如何让你的用户与外部用户共享会议和约会的日历。 '
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780057"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="2035d-103">与外部用户共享日历</span><span class="sxs-lookup"><span data-stu-id="2035d-103">Share calendars with external users</span></span>

<span data-ttu-id="2035d-104">通常有必要安排与组织外的人员的会议。</span><span class="sxs-lookup"><span data-stu-id="2035d-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="2035d-105">为了简化查找相互 agreeable 会议时间的过程，Microsoft 365 使您能够将日历提供给 "外部用户"，即那些需要查看忙/闲时间但对 Microsoft 365 环境没有用户帐户的人。</span><span class="sxs-lookup"><span data-stu-id="2035d-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="2035d-106">日历共享是全局设置，表示您（管理员）可以为租户中的所有用户启用它。</span><span class="sxs-lookup"><span data-stu-id="2035d-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="2035d-107">一旦已启用共享，用户就可以使用 Outlook Web App 与组织内外的任何人共享其日历。</span><span class="sxs-lookup"><span data-stu-id="2035d-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="2035d-108">组织内部的人员可以并排查看共享日历和其自己的日历。</span><span class="sxs-lookup"><span data-stu-id="2035d-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="2035d-109">组织外部的人员将收到可用于查看日历的 URL。</span><span class="sxs-lookup"><span data-stu-id="2035d-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="2035d-110">用户可以决定何时共享、共享量以及何时保持日历私密。</span><span class="sxs-lookup"><span data-stu-id="2035d-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2035d-p103">如果要与使用 Exchange Server 2013（内部部署解决方案）的组织共享日历，Exchange 管理员需要设置与云的身份验证关系。这称为"联盟"，必须满足最低的软件要求。有关详细信息，请参阅[共享](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2035d-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="2035d-114">使用 Microsoft 365 管理中心启用日历共享</span><span class="sxs-lookup"><span data-stu-id="2035d-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="2035d-115">在管理中心中，转到 "**设置** \> **组织设置**"。</span><span class="sxs-lookup"><span data-stu-id="2035d-115">In the admin center, go to **Settings** \> **Org Settings**.</span></span> 
    
2. <span data-ttu-id="2035d-116">在 "**服务**" 选项卡上，选择 "**日历**"。</span><span class="sxs-lookup"><span data-stu-id="2035d-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="2035d-117">在打开的 "**日历**" 页上，选择是否希望让用户与组织外部的人员共享他们的日历，他们拥有 Microsoft 365 或 Exchange。</span><span class="sxs-lookup"><span data-stu-id="2035d-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="2035d-118">选择是否要允许匿名用户（没有登录凭据的用户）通过电子邮件邀请访问日历。</span><span class="sxs-lookup"><span data-stu-id="2035d-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="2035d-119">选择对用户可用的日历信息的类型。</span><span class="sxs-lookup"><span data-stu-id="2035d-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="2035d-120">您可以允许所有信息，也可以将其限制为仅时间或时间、主题和位置。</span><span class="sxs-lookup"><span data-stu-id="2035d-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="2035d-121">邀请其他人访问日历</span><span class="sxs-lookup"><span data-stu-id="2035d-121">Invite people to access calendars</span></span>

<span data-ttu-id="2035d-p105">一旦为租户启用共享，日历所有者就可以将邀请扩展到特定用户。 有关说明，请参阅[在 Outlook Web App 中共享日历](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)。</span><span class="sxs-lookup"><span data-stu-id="2035d-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span> 
  
