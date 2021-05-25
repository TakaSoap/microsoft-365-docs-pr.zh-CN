---
title: 在 defender 中通过电子邮件Microsoft 365通知
description: 了解如何创建规则，以在 Defender 中获取Microsoft 365电子邮件通知
keywords: 事件， 电子邮件， 电子邮件通知， 配置， 用户， 邮箱， 电子邮件， 事件， 分析， 响应
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2e47b35646a1cd6e1075d80f9ed0550e8e1e819f
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651388"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="c2d30-104">通过电子邮件获取事件通知</span><span class="sxs-lookup"><span data-stu-id="c2d30-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c2d30-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c2d30-105">**Applies to:**</span></span>
- <span data-ttu-id="c2d30-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2d30-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c2d30-107">你可以设置 Microsoft 365 Defender，以通过电子邮件通知员工有关新事件或现有事件更新。</span><span class="sxs-lookup"><span data-stu-id="c2d30-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="c2d30-108">可以选择基于以下选项获取通知：</span><span class="sxs-lookup"><span data-stu-id="c2d30-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="c2d30-109">事件严重性。</span><span class="sxs-lookup"><span data-stu-id="c2d30-109">Incident severity.</span></span>
- <span data-ttu-id="c2d30-110">设备组。</span><span class="sxs-lookup"><span data-stu-id="c2d30-110">Device group.</span></span>
- <span data-ttu-id="c2d30-111">仅在每个事件的第一次更新时。</span><span class="sxs-lookup"><span data-stu-id="c2d30-111">Only on the first update per incident.</span></span>

<span data-ttu-id="c2d30-112">电子邮件通知包含有关事件的重要详细信息，如事件名称、严重性和类别等。</span><span class="sxs-lookup"><span data-stu-id="c2d30-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="c2d30-113">您还可以直接转到事件并立即开始分析。</span><span class="sxs-lookup"><span data-stu-id="c2d30-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="c2d30-114">有关详细信息，请参阅调查 [事件](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d30-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="c2d30-115">可以在电子邮件通知中添加或删除收件人。</span><span class="sxs-lookup"><span data-stu-id="c2d30-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="c2d30-116">新收件人在添加事件后会收到事件通知。</span><span class="sxs-lookup"><span data-stu-id="c2d30-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="c2d30-117">您需要"管理安全设置"权限才能配置电子邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="c2d30-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="c2d30-118">如果选择使用基本权限管理，则具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="c2d30-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="c2d30-119">同样，如果组织使用的是基于角色的访问控制 (RBAC) ，则只能根据允许管理的设备组创建、编辑、删除和接收通知。</span><span class="sxs-lookup"><span data-stu-id="c2d30-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="c2d30-120">为电子邮件通知创建规则</span><span class="sxs-lookup"><span data-stu-id="c2d30-120">Create a rule for email notifications</span></span>

<span data-ttu-id="c2d30-121">按照以下步骤创建新规则并自定义电子邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="c2d30-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="c2d30-122">在导航窗格中，选择"设置 > Microsoft 365 **Defender >事件电子邮件通知"。**</span><span class="sxs-lookup"><span data-stu-id="c2d30-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="c2d30-123">选择 **"添加项目"。**</span><span class="sxs-lookup"><span data-stu-id="c2d30-123">Select **Add item**.</span></span>
3. <span data-ttu-id="c2d30-124">在"**基本信息"** 页上，键入规则名称和说明，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="c2d30-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="c2d30-125">在" **通知设置"** 页上，配置：</span><span class="sxs-lookup"><span data-stu-id="c2d30-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="c2d30-126">**警报严重性** - 选择将触发事件通知的警报严重性。</span><span class="sxs-lookup"><span data-stu-id="c2d30-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="c2d30-127">例如，如果你只想获得有关高严重性事件的通知，请选择"高 **"。**</span><span class="sxs-lookup"><span data-stu-id="c2d30-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="c2d30-128">**设备组** 作用域 - 你可以指定所有设备组，也可以从租户中的设备组列表中选择。</span><span class="sxs-lookup"><span data-stu-id="c2d30-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="c2d30-129">**仅在发生每个事件时通知** - 选择是否仅希望通知与其他选择匹配的第一个警报。</span><span class="sxs-lookup"><span data-stu-id="c2d30-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="c2d30-130">以后与事件相关的更新或警报不会发送其他通知。</span><span class="sxs-lookup"><span data-stu-id="c2d30-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="c2d30-131">**在电子邮件中包括组织名称** - 选择是否要在电子邮件通知中显示您的组织名称。</span><span class="sxs-lookup"><span data-stu-id="c2d30-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="c2d30-132">**包含特定于租户的门户链接**- 选择是否要在电子邮件通知中添加包含租户 ID 的链接，以访问特定租户Microsoft 365租户。</span><span class="sxs-lookup"><span data-stu-id="c2d30-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="事件电子邮件通知的通知设置":::

5. <span data-ttu-id="c2d30-134">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c2d30-134">Select **Next**.</span></span> <span data-ttu-id="c2d30-135">在 **"收件人"** 页上，添加将接收事件通知的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c2d30-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="c2d30-136">键入 **每个** 新电子邮件地址后，选择"添加"。</span><span class="sxs-lookup"><span data-stu-id="c2d30-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="c2d30-137">若要测试通知并确保收件人在收件箱中收到通知，请选择"**发送测试电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="c2d30-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="c2d30-138">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c2d30-138">Select **Next**.</span></span> <span data-ttu-id="c2d30-139">在"**复查规则**"页上，查看规则的设置，然后选择"创建 **规则"。**</span><span class="sxs-lookup"><span data-stu-id="c2d30-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="c2d30-140">收件人将开始根据设置通过电子邮件接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="c2d30-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="c2d30-141">若要编辑现有规则，请从规则列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="c2d30-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="c2d30-142">在具有规则名称的窗格中，选择"编辑规则"，在"基本"、通知 **设置** 和"**收件人"页上进行更改**。 </span><span class="sxs-lookup"><span data-stu-id="c2d30-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="c2d30-143">若要删除规则，请从规则列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="c2d30-143">To delete a rule, select it from the list of rules.</span></span> <span data-ttu-id="c2d30-144">在具有规则名称的窗格中，选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="c2d30-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2d30-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2d30-145">See also</span></span>
- [<span data-ttu-id="c2d30-146">事件概述</span><span class="sxs-lookup"><span data-stu-id="c2d30-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c2d30-147">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="c2d30-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="c2d30-148">调查事件</span><span class="sxs-lookup"><span data-stu-id="c2d30-148">Investigate incidents</span></span>](investigate-incidents.md)
