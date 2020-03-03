---
title: 内幕风险管理用户
description: 了解 Microsoft 365 中的内部人员风险管理用户
keywords: Microsoft 365，内幕风险管理，风险管理，合规性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: f499cacd0ec63f9a192e2773b3604473d2153545
ms.sourcegitcommit: 9d6f9fd271e83c00e92a5e0247fcc51fc2070c3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42370491"
---
# <a name="insider-risk-management-users"></a><span data-ttu-id="65478-104">内幕风险管理用户</span><span class="sxs-lookup"><span data-stu-id="65478-104">Insider risk management users</span></span>

<span data-ttu-id="65478-105">内幕风险管理用户是组织中包含在一个或多个内幕风险管理策略中的员工。</span><span class="sxs-lookup"><span data-stu-id="65478-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="65478-106">使用**用户仪表板**快速查看有关员工的风险信息，并将员工添加到现有的内幕风险管理策略中。</span><span class="sxs-lookup"><span data-stu-id="65478-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="65478-107">内幕风险管理策略中包含的每个用户在**用户仪表板**上显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="65478-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="65478-108">**Users**：用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="65478-108">**Users**: The username for a user.</span></span>
- <span data-ttu-id="65478-109">**风险级别**：用户的当前计算的风险级别。</span><span class="sxs-lookup"><span data-stu-id="65478-109">**Risk level**: The current calculated risk level of the user.</span></span> <span data-ttu-id="65478-110">此分数每24小时计算一次，并使用与该用户关联的所有活动警报中的警报风险分数。</span><span class="sxs-lookup"><span data-stu-id="65478-110">This score is calculated every 24 hours and uses the alert risk scores from all active alerts associated to the user.</span></span>
- <span data-ttu-id="65478-111">**主动警报**：针对所有策略的活动警报数。</span><span class="sxs-lookup"><span data-stu-id="65478-111">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="65478-112">已**确认冲突**：针对用户确认的已*确认策略冲突*的案例数。</span><span class="sxs-lookup"><span data-stu-id="65478-112">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="65478-113">**案例**：用户的当前活动事例。</span><span class="sxs-lookup"><span data-stu-id="65478-113">**Case**: The current active case for the user.</span></span>

![内幕风险管理用户仪表板](../media/insider-risk-users-dashboard.png)

>[!NOTE]
><span data-ttu-id="65478-115">在某些情况下，在用户仪表板上显示的用户数量可能会受到限制，具体取决于活动警报和匹配策略的数量。</span><span class="sxs-lookup"><span data-stu-id="65478-115">The number of users displayed on the User dashboard may be limited in some instances, depending on the volume of active alerts and matching policies.</span></span> <span data-ttu-id="65478-116">在生成警报时显示具有活动警报的用户，在达到显示的最大用户数的情况下，可能会发生极少的情况。</span><span class="sxs-lookup"><span data-stu-id="65478-116">Users with active alerts are displayed as the alerts are generated, and there may be rare cases when the maximum number of displayed users is reached.</span></span> <span data-ttu-id="65478-117">如果发生这种情况，则在对现有用户通知进行会审时，将不显示活动警报的用户添加到用户仪表板。</span><span class="sxs-lookup"><span data-stu-id="65478-117">If this happens, users with active alerts who aren’t displayed will be added to the User dashboard as existing user alerts are triaged.</span></span>

## <a name="view-user-details"></a><span data-ttu-id="65478-118">查看用户详细信息</span><span class="sxs-lookup"><span data-stu-id="65478-118">View user details</span></span>

<span data-ttu-id="65478-119">若要查看有关某个用户的风险活动的更多详细信息，请双击用户**仪表板**中的用户以打开用户详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="65478-119">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="65478-120">在 "详细信息" 窗格中，您可以查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="65478-120">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="65478-121">**用户配置文件**选项卡</span><span class="sxs-lookup"><span data-stu-id="65478-121">**User profile** tab</span></span>
    - <span data-ttu-id="65478-122">**名称和标题**：用户的姓名和职位职务。</span><span class="sxs-lookup"><span data-stu-id="65478-122">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="65478-123">**用户电子邮件**：用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="65478-123">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="65478-124">**别名**：用户的网络别名。</span><span class="sxs-lookup"><span data-stu-id="65478-124">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="65478-125">**组织或部门**：用户的组织或部门。</span><span class="sxs-lookup"><span data-stu-id="65478-125">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="65478-126">**用户活动**选项卡</span><span class="sxs-lookup"><span data-stu-id="65478-126">**User activity** tab</span></span>
    - <span data-ttu-id="65478-127">**最近用户活动的历史记录**：列出触发事件的策略和用户活动的风险指示器。</span><span class="sxs-lookup"><span data-stu-id="65478-127">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="65478-128">触发事件可能是接受辞职日期或员工上次计划的工作日期。</span><span class="sxs-lookup"><span data-stu-id="65478-128">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="65478-129">风险指标是确定为具有风险的元素且与包含用户的策略相匹配的活动。</span><span class="sxs-lookup"><span data-stu-id="65478-129">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="65478-130">列出了 "事件" 和 "风险" 活动，其中最新项最先列出。</span><span class="sxs-lookup"><span data-stu-id="65478-130">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="65478-131">将用户添加到策略</span><span class="sxs-lookup"><span data-stu-id="65478-131">Add a user to a policy</span></span>

<span data-ttu-id="65478-132">若要将用户添加到内部风险管理策略，您将使用 "新建策略" 向导或 "Microsoft 365 合规性中心" 中的 "**内幕风险管理**" 解决方案中的 "**用户**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="65478-132">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="65478-133">完成以下步骤以将用户添加到现有内幕风险策略：</span><span class="sxs-lookup"><span data-stu-id="65478-133">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="65478-134">在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**用户**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="65478-134">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="65478-135">选择 "在工具栏上**向策略添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="65478-135">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="65478-136">在 "**添加新用户**" 对话框中，开始在 "**用户**" 字段中键入用户名。</span><span class="sxs-lookup"><span data-stu-id="65478-136">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="65478-137">选择要添加到策略中的用户。</span><span class="sxs-lookup"><span data-stu-id="65478-137">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="65478-138">选择 "**策略**" 字段的下拉箭头以显示配置的 "内幕风险管理策略"。</span><span class="sxs-lookup"><span data-stu-id="65478-138">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="65478-139">选择要将用户添加到的策略。</span><span class="sxs-lookup"><span data-stu-id="65478-139">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="65478-140">使用**激活窗口**滑块控件可定义策略对此用户处于活动状态的时间长度，并在用户执行与策略匹配的第一个活动时触发。</span><span class="sxs-lookup"><span data-stu-id="65478-140">Use the **Activation window** slider control to define how long the policy is active for this user and is triggered when the user performs the first activity matching the policy.</span></span> <span data-ttu-id="65478-141">"监视" 窗口的范围是5到30天。</span><span class="sxs-lookup"><span data-stu-id="65478-141">The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="65478-142">选择 "**添加**"，然后**确认**将该用户添加到策略中。</span><span class="sxs-lookup"><span data-stu-id="65478-142">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
