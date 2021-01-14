---
title: 在 Microsoft 365 Defender 中获取事件通知
description: 了解如何创建规则，以在 Microsoft 365 Defender 中获取事件的电子邮件通知
keywords: 事件， 电子邮件， 电子邮件通知， 配置， 用户， 邮箱， 电子邮件， 事件
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848887"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="11b3f-104">通过电子邮件获取事件通知</span><span class="sxs-lookup"><span data-stu-id="11b3f-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="11b3f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="11b3f-105">**Applies to:**</span></span>
- <span data-ttu-id="11b3f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11b3f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="11b3f-107">你可以设置 Microsoft 365 Defender，以在有新事件或现有事件的新更新时通过电子邮件通知你。</span><span class="sxs-lookup"><span data-stu-id="11b3f-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="11b3f-108">你可以选择根据事件严重性或设备组获取通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="11b3f-109">还可以选择仅在每个事件的第一次更新时收到通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="11b3f-110">可以在电子邮件通知中添加或删除收件人。</span><span class="sxs-lookup"><span data-stu-id="11b3f-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="11b3f-111">新添加的收件人在添加事件后收到事件通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="11b3f-112">电子邮件通知包含有关事件的重要详细信息，如事件名称、严重性和类别等。</span><span class="sxs-lookup"><span data-stu-id="11b3f-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="11b3f-113">还可以直接转到事件，以便立即开始调查。</span><span class="sxs-lookup"><span data-stu-id="11b3f-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="11b3f-114">有关调查事件 More on investigatings， see [Investigate incidents in Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)</span><span class="sxs-lookup"><span data-stu-id="11b3f-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="11b3f-115">您需要"管理安全设置"权限才能配置电子邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="11b3f-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="11b3f-116">如果选择使用基本权限管理，具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="11b3f-117">同样，如果组织使用基于角色的访问控制 (RBAC) ，则只能基于允许管理的设备组创建、编辑、删除和接收通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="11b3f-118">创建事件通知规则</span><span class="sxs-lookup"><span data-stu-id="11b3f-118">Create rules for incident notifications</span></span>

<span data-ttu-id="11b3f-119">若要为事件设置第一个电子邮件通知，请创建一个新规则并自定义电子邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="11b3f-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="11b3f-120">在导航窗格中，选择 **"设置**  >  **事件电子邮件通知"。**</span><span class="sxs-lookup"><span data-stu-id="11b3f-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="11b3f-121">选择 **"添加项目"。**</span><span class="sxs-lookup"><span data-stu-id="11b3f-121">Select **Add item**.</span></span>
3. <span data-ttu-id="11b3f-122">在"名称"**中为规则** 命名，并提供 **"说明"。**</span><span class="sxs-lookup"><span data-stu-id="11b3f-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![为事件电子邮件创建规则窗口](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="11b3f-124">选择 **"下** 一步"转到 **"通知设置"。**</span><span class="sxs-lookup"><span data-stu-id="11b3f-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="11b3f-125">你可以在此处指定：</span><span class="sxs-lookup"><span data-stu-id="11b3f-125">Here you can specify:</span></span>
    - <span data-ttu-id="11b3f-126">**警报严重性** - 选择将触发事件通知的警报严重性。</span><span class="sxs-lookup"><span data-stu-id="11b3f-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="11b3f-127">例如，如果您只想获得有关高严重性事件的通知，请选择"高"。</span><span class="sxs-lookup"><span data-stu-id="11b3f-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="11b3f-128">**设备组** 作用域 - 此下拉列表显示用户可以访问的所有设备组。</span><span class="sxs-lookup"><span data-stu-id="11b3f-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="11b3f-129">选择要为哪些设备组创建事件通知规则。</span><span class="sxs-lookup"><span data-stu-id="11b3f-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="11b3f-130">**仅在每个事件首次出现时** 通知 - 选择此选项将仅在第一个匹配其他选择的警报上发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="11b3f-131">以后与事件相关的更新或警报不会触发通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="11b3f-132">**包含组织名称** - 指示是否在电子邮件通知上显示客户名称。</span><span class="sxs-lookup"><span data-stu-id="11b3f-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="11b3f-133">**包含特定于租户的门户链接** - 添加包含租户 ID 的链接，以允许访问特定租户。</span><span class="sxs-lookup"><span data-stu-id="11b3f-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![事件电子邮件的 Notif 设置窗口](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="11b3f-135">选择 **"** 下一步"转到 **"收件人"** 部分。</span><span class="sxs-lookup"><span data-stu-id="11b3f-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="11b3f-136">你可以在此处指定将接收事件电子邮件通知的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="11b3f-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="11b3f-137">键入 **每个电子邮件地址后** ，选择"添加收件人"。</span><span class="sxs-lookup"><span data-stu-id="11b3f-137">Select **Add a recipient** after typing every email address.</span></span>

    ![事件电子邮件的"添加收件人"窗口](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="11b3f-139">最后， **选择"下一** 步 **"转到"** 查看规则"，以便你可以看到与新规则关联的所有设置。</span><span class="sxs-lookup"><span data-stu-id="11b3f-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="11b3f-140">收件人将开始根据设置通过电子邮件接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="11b3f-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="11b3f-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11b3f-141">See also</span></span>
- [<span data-ttu-id="11b3f-142">Microsoft 365 Defender 中的事件概述</span><span class="sxs-lookup"><span data-stu-id="11b3f-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="11b3f-143">确定 Microsoft 365 Defender 中事件的优先级</span><span class="sxs-lookup"><span data-stu-id="11b3f-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="11b3f-144">调查 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="11b3f-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

