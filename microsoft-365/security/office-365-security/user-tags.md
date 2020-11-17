---
title: Microsoft Defender for Office 365 中的用户标记
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 计划2中标识具有用户标记的特定用户组。 标记筛选在 Microsoft Defender for Office 365 中通过警报、报告和调查提供，可快速识别已标记的用户。
ms.openlocfilehash: 14ebcebeb8081a2de341fd06facabd9f7d55b119
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123615"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="667dd-104">Microsoft Defender for Office 365 中的用户标记</span><span class="sxs-lookup"><span data-stu-id="667dd-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="667dd-105">"用户标记" 功能在预览中不可用，每个人都不可用，并且可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="667dd-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="667dd-106">有关发布计划的信息，请参阅 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="667dd-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="667dd-107">用户标记是 [Microsoft Defender For Office 365](office-365-atp.md)中特定用户组的标识符。</span><span class="sxs-lookup"><span data-stu-id="667dd-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="667dd-108">有两种类型的用户标记：</span><span class="sxs-lookup"><span data-stu-id="667dd-108">There are two types of user tags:</span></span>

- <span data-ttu-id="667dd-109">**系统标记**：当前， [优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是唯一的系统标记类型。</span><span class="sxs-lookup"><span data-stu-id="667dd-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="667dd-110">**自定义标记**：您自己创建这些用户标记。</span><span class="sxs-lookup"><span data-stu-id="667dd-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="667dd-111">如果您的组织具有适用于 Office 365 的 Defender for Office 计划 2 (包含在订阅中或作为加载项) ，除了使用优先级帐户标记之外，您还可以创建自定义用户标记。</span><span class="sxs-lookup"><span data-stu-id="667dd-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="667dd-112">向用户应用系统标签或自定义标记后，可以将这些标记用作警报、报告和调查中的筛选器：</span><span class="sxs-lookup"><span data-stu-id="667dd-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="667dd-113">安全 & 合规中心中的警报</span><span class="sxs-lookup"><span data-stu-id="667dd-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="667dd-114">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="667dd-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="667dd-115">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="667dd-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="667dd-116">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="667dd-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="667dd-117">对于优先级帐户，您可以在 Exchange 管理中心 (EAC) 中使用 [优先级帐户报告的电子邮件问题](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) 。</span><span class="sxs-lookup"><span data-stu-id="667dd-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="667dd-118">本文介绍如何在安全 & 合规中心中配置用户标记。</span><span class="sxs-lookup"><span data-stu-id="667dd-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="667dd-119">Security & 合规性中心中没有可用于管理用户标记的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="667dd-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="667dd-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="667dd-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="667dd-121">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="667dd-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="667dd-122">若要直接转到 " **用户标记** " 页，请打开 <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="667dd-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="667dd-123">若要创建、修改或删除 **自定义用户标记**，您需要是安全 & 合规性中心中的 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="667dd-123">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="667dd-124">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="667dd-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="667dd-125">若要 (系统标记) 配置优先级帐户，您必须是 [全局管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 或 [Exchange 管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)。</span><span class="sxs-lookup"><span data-stu-id="667dd-125">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="667dd-126">您还可以在 Microsoft 365 管理中心中管理和监视优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="667dd-126">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="667dd-127">有关说明，请参阅 [管理和监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="667dd-127">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="667dd-128">使用安全中心创建用户标记</span><span class="sxs-lookup"><span data-stu-id="667dd-128">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="667dd-129">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-129">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="667dd-130">在打开的 " **用户标记** " 页上，单击 " **创建标记**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-130">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="667dd-131">" **创建标记** " 向导将在新的飞出中打开。在 " **定义标记** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="667dd-131">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="667dd-132">**名称**：为标记输入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="667dd-132">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="667dd-133">这是你将看到和使用的值。</span><span class="sxs-lookup"><span data-stu-id="667dd-133">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="667dd-134">**说明**：输入标记的可选说明。</span><span class="sxs-lookup"><span data-stu-id="667dd-134">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="667dd-135">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="667dd-135">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="667dd-136">在 " **分配邮箱** " 页上，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="667dd-136">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="667dd-137">单击 " **添加邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-137">Click **Add mailboxes**.</span></span> <span data-ttu-id="667dd-138">在出现的 "飞出" 中，执行以下任一步骤添加单个用户或组：</span><span class="sxs-lookup"><span data-stu-id="667dd-138">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="667dd-139">在框中单击，并在列表中滚动以选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="667dd-139">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="667dd-140">在框中单击，然后开始键入以筛选列表并选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="667dd-140">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="667dd-141">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="667dd-141">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="667dd-142">若要从框中删除单个条目， **Remove** 请 ![ ](../../media/scc-remove-icon.png) 在框中的用户或组上单击 "删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="667dd-142">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="667dd-143">若要从框下方的列表中删除现有条目，请单击 " **删除** ![ 删除图标 ](../../media/scc-remove-icon.png) " 条目。</span><span class="sxs-lookup"><span data-stu-id="667dd-143">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="667dd-144">完成后，请单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-144">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="667dd-145">单击 " **导入** " 以选择包含用户或组的电子邮件地址的文本文件。</span><span class="sxs-lookup"><span data-stu-id="667dd-145">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="667dd-146">确保文本文件中每行包含一个条目。</span><span class="sxs-lookup"><span data-stu-id="667dd-146">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="667dd-147">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="667dd-147">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="667dd-148">在 " **查看标记** " 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="667dd-148">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="667dd-149">您可以单击 "特定" 部分中的 " **编辑** " 来进行更改。</span><span class="sxs-lookup"><span data-stu-id="667dd-149">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="667dd-150">完成后，请单击 " **提交**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-150">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="667dd-151">使用安全中心查看用户标记</span><span class="sxs-lookup"><span data-stu-id="667dd-151">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="667dd-152">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-152">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="667dd-153">在打开的 " **用户标记** " 页上，选择要查看的用户标记 (不要单击复选框) 。</span><span class="sxs-lookup"><span data-stu-id="667dd-153">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="667dd-154">在出现的只读详细信息飞出中，查看设置。</span><span class="sxs-lookup"><span data-stu-id="667dd-154">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="667dd-155">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="667dd-155">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="667dd-156">使用安全中心修改用户标记</span><span class="sxs-lookup"><span data-stu-id="667dd-156">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="667dd-157">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="667dd-158">在打开的 " **用户标记** " 页上，选择要查看的用户标记，然后单击 " **编辑标记**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-158">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="667dd-159">"策略向导" 将在 " **编辑" 标记** 飞出时打开。单击 " **下一步** " 查看并修改设置。</span><span class="sxs-lookup"><span data-stu-id="667dd-159">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="667dd-160">完成后，请单击 " **提交**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-160">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="667dd-161">使用安全中心删除用户标记</span><span class="sxs-lookup"><span data-stu-id="667dd-161">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="667dd-162">**注意**：不能删除内置的 " **优先级" 帐户** 标记。</span><span class="sxs-lookup"><span data-stu-id="667dd-162">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="667dd-163">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="667dd-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="667dd-164">在打开的 " **用户标记** " 页上，选择要删除的用户标记，单击 " **删除标记**"，然后选择 **"是，** 在出现的警告中删除"。</span><span class="sxs-lookup"><span data-stu-id="667dd-164">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
