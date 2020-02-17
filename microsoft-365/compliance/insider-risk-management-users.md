---
title: 内幕风险管理用户（预览）
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
ms.openlocfilehash: a9ff7e38a99a5fe5bd8da5301bec5e19bc015cf3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072781"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="77288-104">内幕风险管理用户（预览）</span><span class="sxs-lookup"><span data-stu-id="77288-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="77288-105">内幕风险管理用户是组织中包含在一个或多个内幕风险管理策略中的员工。</span><span class="sxs-lookup"><span data-stu-id="77288-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="77288-106">使用**用户仪表板**快速查看有关员工的风险信息，并将员工添加到现有的内幕风险管理策略中。</span><span class="sxs-lookup"><span data-stu-id="77288-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="77288-107">内幕风险管理策略中包含的每个用户在**用户仪表板**上显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="77288-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="77288-108">**Users**：用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="77288-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="77288-109">**风险级别**：</span><span class="sxs-lookup"><span data-stu-id="77288-109">**Risk level**:</span></span> 
- <span data-ttu-id="77288-110">**主动警报**：针对所有策略的活动警报数。</span><span class="sxs-lookup"><span data-stu-id="77288-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="77288-111">已**确认冲突**：针对用户确认的已*确认策略冲突*的案例数。</span><span class="sxs-lookup"><span data-stu-id="77288-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="77288-112">**案例**：用户的当前活动事例。</span><span class="sxs-lookup"><span data-stu-id="77288-112">**Case**: The current active case for the user.</span></span>

![内幕风险管理用户仪表板](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="77288-114">查看用户详细信息</span><span class="sxs-lookup"><span data-stu-id="77288-114">View user details</span></span>

<span data-ttu-id="77288-115">若要查看有关某个用户的风险活动的更多详细信息，请双击用户**仪表板**中的用户以打开用户详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="77288-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="77288-116">在 "详细信息" 窗格中，您可以查看以下信息：</span><span class="sxs-lookup"><span data-stu-id="77288-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="77288-117">**用户配置文件**选项卡</span><span class="sxs-lookup"><span data-stu-id="77288-117">**User profile** tab</span></span>
    - <span data-ttu-id="77288-118">**名称和标题**：用户的姓名和职位职务。</span><span class="sxs-lookup"><span data-stu-id="77288-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="77288-119">**用户电子邮件**：用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77288-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="77288-120">**别名**：用户的网络别名。</span><span class="sxs-lookup"><span data-stu-id="77288-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="77288-121">**组织或部门**：用户的组织或部门。</span><span class="sxs-lookup"><span data-stu-id="77288-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="77288-122">**用户活动**选项卡</span><span class="sxs-lookup"><span data-stu-id="77288-122">**User activity** tab</span></span>
    - <span data-ttu-id="77288-123">**最近用户活动的历史记录**：列出触发事件的策略和用户活动的风险指示器。</span><span class="sxs-lookup"><span data-stu-id="77288-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="77288-124">触发事件可能是接受辞职日期或员工上次计划的工作日期。</span><span class="sxs-lookup"><span data-stu-id="77288-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="77288-125">风险指标是确定为具有风险的元素且与包含用户的策略相匹配的活动。</span><span class="sxs-lookup"><span data-stu-id="77288-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="77288-126">列出了 "事件" 和 "风险" 活动，其中最新项最先列出。</span><span class="sxs-lookup"><span data-stu-id="77288-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="77288-127">将用户添加到策略</span><span class="sxs-lookup"><span data-stu-id="77288-127">Add a user to a policy</span></span>

<span data-ttu-id="77288-128">若要将用户添加到内部风险管理策略，您将使用 "新建策略" 向导或 "Microsoft 365 合规性中心" 中的 "**内幕风险管理**" 解决方案中的 "**用户**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77288-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="77288-129">完成以下步骤以将用户添加到现有内幕风险策略：</span><span class="sxs-lookup"><span data-stu-id="77288-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="77288-130">在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**用户**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77288-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="77288-131">选择 "在工具栏上**向策略添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="77288-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="77288-132">在 "**添加新用户**" 对话框中，开始在 "**用户**" 字段中键入用户名。</span><span class="sxs-lookup"><span data-stu-id="77288-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="77288-133">选择要添加到策略中的用户。</span><span class="sxs-lookup"><span data-stu-id="77288-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="77288-134">选择 "**策略**" 字段的下拉箭头以显示配置的 "内幕风险管理策略"。</span><span class="sxs-lookup"><span data-stu-id="77288-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="77288-135">选择要将用户添加到的策略。</span><span class="sxs-lookup"><span data-stu-id="77288-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="77288-136">使用 "**监视窗口**" 滑块控件定义 .。。"监视" 窗口的范围是5到30天。</span><span class="sxs-lookup"><span data-stu-id="77288-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="77288-137">选择 "**添加**"，然后**确认**将该用户添加到策略中。</span><span class="sxs-lookup"><span data-stu-id="77288-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
