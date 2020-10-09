---
title: Office 365 ATP 中的用户标记
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
description: 管理员可以了解如何使用 Office 365 ATP 计划2中的用户标记标识特定用户组。 标记筛选在 Office 365 ATP 中的通知、报告和调查中可用，以快速识别已标记的用户。
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399381"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="8ee4e-104">Office 365 ATP 中的用户标记</span><span class="sxs-lookup"><span data-stu-id="8ee4e-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="8ee4e-105">用户标记是 [Office 365 高级威胁防护 (ATP) ](office-365-atp.md)中的特定用户组的标识符。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="8ee4e-106">有两种类型的用户标记：</span><span class="sxs-lookup"><span data-stu-id="8ee4e-106">There are two types of user tags:</span></span>

- <span data-ttu-id="8ee4e-107">**系统标记**：当前， [优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是唯一的系统标记类型。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-107">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="8ee4e-108">**自定义标记**：您自己创建这些用户标记。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-108">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="8ee4e-109">如果您的组织具有 Office 365 ATP 计划 2 (包含在订阅中或作为加载项) ，除了使用优先级帐户标记之外，还可以创建自定义用户标记。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-109">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="8ee4e-110">向用户应用系统标签或自定义标记后，可以将这些标记用作警报、报告和调查中的筛选器：</span><span class="sxs-lookup"><span data-stu-id="8ee4e-110">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="8ee4e-111">安全 & 合规中心中的警报</span><span class="sxs-lookup"><span data-stu-id="8ee4e-111">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="8ee4e-112">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="8ee4e-112">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="8ee4e-113">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="8ee4e-113">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="8ee4e-114">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="8ee4e-114">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="8ee4e-115">本文介绍如何在安全 & 合规中心中配置用户标记。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-115">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="8ee4e-116">Security & 合规性中心中没有可用于管理用户标记的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-116">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8ee4e-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8ee4e-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8ee4e-118">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8ee4e-119">若要直接转到 " **用户标记** " 页，请打开 <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-119">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="8ee4e-120">若要创建、修改或删除 **自定义用户标记**，您需要是安全 & 合规性中心中的 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-120">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="8ee4e-121">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-121">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="8ee4e-122">若要 (系统标记) 配置优先级帐户，您必须是 [全局管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 或 [Exchange 管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-122">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="8ee4e-123">您还可以在 Microsoft 365 管理中心中管理和监视优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-123">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8ee4e-124">有关说明，请参阅 [管理和监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-124">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="8ee4e-125">使用安全中心创建用户标记</span><span class="sxs-lookup"><span data-stu-id="8ee4e-125">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="8ee4e-126">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-126">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8ee4e-127">在打开的 " **用户标记** " 页上，单击 " **创建标记**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-127">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="8ee4e-128">" **创建标记** " 向导将在新的飞出中打开。在 " **定义标记** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8ee4e-128">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="8ee4e-129">**名称**：为标记输入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-129">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="8ee4e-130">这是你将看到和使用的值。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-130">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="8ee4e-131">**说明**：输入标记的可选说明。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-131">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="8ee4e-132">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-132">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8ee4e-133">在 " **分配邮箱** " 页上，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8ee4e-133">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="8ee4e-134">单击 " **添加邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-134">Click **Add mailboxes**.</span></span> <span data-ttu-id="8ee4e-135">在出现的 "飞出" 中，执行以下任一步骤添加单个用户或组：</span><span class="sxs-lookup"><span data-stu-id="8ee4e-135">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="8ee4e-136">在框中单击，并在列表中滚动以选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-136">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="8ee4e-137">在框中单击，然后开始键入以筛选列表并选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-137">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="8ee4e-138">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-138">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="8ee4e-139">若要从框中删除单个条目， **Remove**请 ![ ](../../media/scc-remove-icon.png) 在框中的用户或组上单击 "删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-139">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="8ee4e-140">若要从框下方的列表中删除现有条目，请单击 " **删除** ![ 删除图标 ](../../media/scc-remove-icon.png) " 条目。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-140">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="8ee4e-141">完成后，请单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-141">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="8ee4e-142">单击 " **导入** " 以选择包含用户或组的电子邮件地址的文本文件。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-142">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="8ee4e-143">确保文本文件中每行包含一个条目。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-143">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="8ee4e-144">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-144">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8ee4e-145">在 " **查看标记** " 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-145">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="8ee4e-146">您可以单击 "特定" 部分中的 " **编辑** " 来进行更改。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-146">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="8ee4e-147">完成后，请单击 " **提交**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-147">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="8ee4e-148">使用安全中心查看用户标记</span><span class="sxs-lookup"><span data-stu-id="8ee4e-148">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="8ee4e-149">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-149">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8ee4e-150">在打开的 " **用户标记** " 页上，选择要查看的用户标记 (不要单击复选框) 。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-150">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="8ee4e-151">在出现的只读详细信息飞出中，查看设置。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-151">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="8ee4e-152">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-152">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="8ee4e-153">使用安全中心修改用户标记</span><span class="sxs-lookup"><span data-stu-id="8ee4e-153">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="8ee4e-154">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-154">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8ee4e-155">在打开的 " **用户标记** " 页上，选择要查看的用户标记，然后单击 " **编辑标记**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-155">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="8ee4e-156">"策略向导" 将在 " **编辑" 标记** 飞出时打开。单击 " **下一步** " 查看并修改设置。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-156">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="8ee4e-157">完成后，请单击 " **提交**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="8ee4e-158">使用安全中心删除用户标记</span><span class="sxs-lookup"><span data-stu-id="8ee4e-158">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="8ee4e-159">**注意**：不能删除内置的 " **优先级" 帐户** 标记。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-159">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="8ee4e-160">在 "安全中心" 中，转到 " **威胁管理** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-160">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="8ee4e-161">在打开的 " **用户标记** " 页上，选择要删除的用户标记，单击 " **删除标记**"，然后选择 **"是，** 在出现的警告中删除"。</span><span class="sxs-lookup"><span data-stu-id="8ee4e-161">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
