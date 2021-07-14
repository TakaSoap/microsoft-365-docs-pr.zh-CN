---
title: 管理应用策略
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 管理应用治理策略。
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420093"
---
# <a name="manage-app-policies"></a><span data-ttu-id="472b7-103">管理应用策略</span><span class="sxs-lookup"><span data-stu-id="472b7-103">Manage app policies</span></span>

><span data-ttu-id="472b7-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="472b7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="472b7-105">若要及时了解组织正在使用的最新应用、响应基于应用的新攻击，以及针对应用合规性需求进行持续更改，可能需要通过以下方式管理应用策略：</span><span class="sxs-lookup"><span data-stu-id="472b7-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="472b7-106">创建针对新应用的新策略</span><span class="sxs-lookup"><span data-stu-id="472b7-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="472b7-107">更改现有策略的状态（活动、非活动、审核模式）</span><span class="sxs-lookup"><span data-stu-id="472b7-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="472b7-108">更改现有策略的条件</span><span class="sxs-lookup"><span data-stu-id="472b7-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="472b7-109">更改用于自动修正警报的现有策略的操作</span><span class="sxs-lookup"><span data-stu-id="472b7-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="472b7-110">以下是管理现有策略的流程示例：</span><span class="sxs-lookup"><span data-stu-id="472b7-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="472b7-111">编辑策略：</span><span class="sxs-lookup"><span data-stu-id="472b7-111">Edit the policy:</span></span>

  - <span data-ttu-id="472b7-112">更改策略的设置。</span><span class="sxs-lookup"><span data-stu-id="472b7-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="472b7-113">如果需要，请将状态更改为“**审核模式**”以进行测试。</span><span class="sxs-lookup"><span data-stu-id="472b7-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="472b7-114">检查预期行为，例如生成的警报。</span><span class="sxs-lookup"><span data-stu-id="472b7-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="472b7-115">如果该行为不是预期行为，请返回到步骤 1。</span><span class="sxs-lookup"><span data-stu-id="472b7-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="472b7-116">如果该行为是预期行为，请编辑策略并将其状态更改为“活动”（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="472b7-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![管理应用策略工作流](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="472b7-118">编辑应用策略配置</span><span class="sxs-lookup"><span data-stu-id="472b7-118">Editing an app policy configuration</span></span>

<span data-ttu-id="472b7-119">若要更改现有应用策略的配置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="472b7-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="472b7-120">在策略列表中选择策略，然后在应用策略窗格中选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="472b7-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="472b7-121">为列表中的策略选择垂直省略号，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="472b7-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="472b7-122">对于“**编辑策略**”页面，请逐步浏览页面并进行相应的更改：</span><span class="sxs-lookup"><span data-stu-id="472b7-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="472b7-123">**说明**：更改说明，让用户可以更轻松地理解策略的用途。</span><span class="sxs-lookup"><span data-stu-id="472b7-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="472b7-124">**严重性**</span><span class="sxs-lookup"><span data-stu-id="472b7-124">**Severity**</span></span>
- <span data-ttu-id="472b7-125">**策略设置**：更改应用策略的应用集，</span><span class="sxs-lookup"><span data-stu-id="472b7-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="472b7-126">也可以选择使用现有条件或修改条件。</span><span class="sxs-lookup"><span data-stu-id="472b7-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="472b7-127">**操作**：更改策略生成的警报的自动修正操作。</span><span class="sxs-lookup"><span data-stu-id="472b7-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="472b7-128">**状态**：更改策略状态。</span><span class="sxs-lookup"><span data-stu-id="472b7-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="472b7-129">删除应用策略</span><span class="sxs-lookup"><span data-stu-id="472b7-129">Deleting an app policy</span></span>

<span data-ttu-id="472b7-130">若要删除应用策略，你可以：</span><span class="sxs-lookup"><span data-stu-id="472b7-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="472b7-131">在策略列表中选择策略，然后在应用策略窗格中选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="472b7-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="472b7-132">选择列表中策略的垂直省略号，然后选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="472b7-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="472b7-133">或者，也可以将应用策略的状态更改为“非活动”。</span><span class="sxs-lookup"><span data-stu-id="472b7-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="472b7-134">处于非活动状态的策略将不会生成警报。</span><span class="sxs-lookup"><span data-stu-id="472b7-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="472b7-135">例如，重命名应用策略以指示其有用，并将其状态设置为“非活动”，而不是删除具有一组特定条件的应用策略，这些条件对将来的策略非常有用。</span><span class="sxs-lookup"><span data-stu-id="472b7-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="472b7-136">你可以稍后返回该策略，并针对类似应用对其进行修改，然后将其状态设置为“审核模式”或“非活动”。</span><span class="sxs-lookup"><span data-stu-id="472b7-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
