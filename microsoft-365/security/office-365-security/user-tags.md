---
title: 用户标记
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
description: 管理员可以了解如何在 Oiffce 365 ATP 计划2中识别具有用户标记的特定用户组。 标记筛选在 Office 365 ATP 中的通知、报告和调查中可用，以快速识别已标记的用户。
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210020"
---
# <a name="user-tags-in-the-microsoft-security-center"></a><span data-ttu-id="b5675-104">Microsoft 安全中心中的用户标记</span><span class="sxs-lookup"><span data-stu-id="b5675-104">User tags in the Microsoft Security Center</span></span>

<span data-ttu-id="b5675-105">用户标记是 [Office 365 高级威胁防护 (ATP) ](office-365-atp.md)中的特定用户组的标识符。</span><span class="sxs-lookup"><span data-stu-id="b5675-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="b5675-106">[优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是一类用户标记。</span><span class="sxs-lookup"><span data-stu-id="b5675-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="b5675-107">如果您的组织具有 Office 365 ATP 计划 2 (包含在订阅中或作为加载项) ，除了使用优先级帐户标记之外，还可以创建自定义用户标记。</span><span class="sxs-lookup"><span data-stu-id="b5675-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="b5675-108">对特定用户应用标记后，可以将这些标记用作警报、报告和调查中的筛选器：</span><span class="sxs-lookup"><span data-stu-id="b5675-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="b5675-109">安全 & 合规中心中的警报</span><span class="sxs-lookup"><span data-stu-id="b5675-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="b5675-110">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="b5675-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="b5675-111">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="b5675-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="b5675-112">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="b5675-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="b5675-113">本文介绍如何在安全中心中配置用户标记。</span><span class="sxs-lookup"><span data-stu-id="b5675-113">This article explains how to configure user tags in the Security Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5675-114">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b5675-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b5675-115">你可以在上打开 "安全中心" <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="b5675-115">You open the Security Center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="b5675-116">若要直接转到 " **用户标记** " 页，请打开 <https://security.microsoft.com/securitysettings/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="b5675-116">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="b5675-117">若要创建、修改或删除用户标记，您需要是安全 & 合规性中心中的 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b5675-117">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="b5675-118">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b5675-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b5675-119">您还可以在 Microsoft 365 管理中心中管理和监视优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="b5675-119">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b5675-120">有关说明，请参阅 [管理和监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="b5675-120">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="b5675-121">使用安全中心创建用户标记</span><span class="sxs-lookup"><span data-stu-id="b5675-121">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="b5675-122">在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-122">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="b5675-123">在打开的 " **用户标记** " 页上，单击 " **创建标记**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-123">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="b5675-124">" **创建标记** " 向导将在新的飞出中打开。在 " **定义标记** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b5675-124">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="b5675-125">**名称**：为标记输入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="b5675-125">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="b5675-126">这是你将看到和使用的值。</span><span class="sxs-lookup"><span data-stu-id="b5675-126">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="b5675-127">**说明**：输入标记的可选说明。</span><span class="sxs-lookup"><span data-stu-id="b5675-127">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="b5675-128">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b5675-128">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b5675-129">在 " **分配邮箱** " 页上，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="b5675-129">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="b5675-130">单击 " **添加邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-130">Click **Add mailboxes**.</span></span> <span data-ttu-id="b5675-131">在出现的 "飞出" 中，执行以下任一步骤添加单个用户或组：</span><span class="sxs-lookup"><span data-stu-id="b5675-131">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="b5675-132">在框中单击，并在列表中滚动以选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="b5675-132">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="b5675-133">在框中单击，然后开始键入以筛选列表并选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="b5675-133">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="b5675-134">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="b5675-134">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="b5675-135">若要从框中删除单个条目， **Remove**请 ![ ](../../media/scc-remove-icon.png) 在框中的用户或组上单击 "删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="b5675-135">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="b5675-136">若要从框下方的列表中删除现有条目，请单击 " **删除** ![ 删除图标 ](../../media/scc-remove-icon.png) " 条目。</span><span class="sxs-lookup"><span data-stu-id="b5675-136">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="b5675-137">完成后，请单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-137">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="b5675-138">单击 " **导入** " 以选择包含用户或组的电子邮件地址的文本文件。</span><span class="sxs-lookup"><span data-stu-id="b5675-138">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="b5675-139">确保文本文件中每行包含一个条目。</span><span class="sxs-lookup"><span data-stu-id="b5675-139">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="b5675-140">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b5675-140">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b5675-141">在 " **查看标记** " 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="b5675-141">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="b5675-142">您可以单击 "特定" 部分中的 " **编辑** " 来进行更改。</span><span class="sxs-lookup"><span data-stu-id="b5675-142">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="b5675-143">完成后，请单击 " **提交**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-143">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="b5675-144">使用安全中心查看用户标记</span><span class="sxs-lookup"><span data-stu-id="b5675-144">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="b5675-145">在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-145">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="b5675-146">在打开的 " **用户标记** " 页上，选择要查看的用户标记 (不要单击复选框) 。</span><span class="sxs-lookup"><span data-stu-id="b5675-146">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="b5675-147">在出现的只读详细信息飞出中，查看设置。</span><span class="sxs-lookup"><span data-stu-id="b5675-147">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="b5675-148">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b5675-148">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="b5675-149">使用安全中心修改用户标记</span><span class="sxs-lookup"><span data-stu-id="b5675-149">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="b5675-150">在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-150">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="b5675-151">在打开的 " **用户标记** " 页上，选择要查看的用户标记，然后单击 " **编辑标记**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-151">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="b5675-152">"策略向导" 将在 " **编辑" 标记** 飞出时打开。单击 " **下一步** " 查看并修改设置。</span><span class="sxs-lookup"><span data-stu-id="b5675-152">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="b5675-153">完成后，请单击 " **提交**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-153">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="b5675-154">使用安全中心删除用户标记</span><span class="sxs-lookup"><span data-stu-id="b5675-154">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="b5675-155">**注意**：不能删除内置的 " **优先级" 帐户** 标记。</span><span class="sxs-lookup"><span data-stu-id="b5675-155">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="b5675-156">在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。</span><span class="sxs-lookup"><span data-stu-id="b5675-156">In the Security Center, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="b5675-157">在打开的 " **用户标记** " 页上，选择要删除的用户标记，单击 " **删除标记**"，然后选择 **"是，** 在出现的警告中删除"。</span><span class="sxs-lookup"><span data-stu-id="b5675-157">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
