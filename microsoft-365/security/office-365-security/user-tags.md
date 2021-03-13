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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 计划 2 中标识具有用户标记的特定用户组。 可在 Microsoft Defender for Office 365 中的警报、报告和调查之间使用标签筛选，以快速识别标记的用户。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80bd360888be3aeea42da6f9b58a119a9752d382
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758888"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="63543-104">Microsoft Defender for Office 365 中的用户标记</span><span class="sxs-lookup"><span data-stu-id="63543-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="63543-105">用户标记功能在预览版中，不可供所有人使用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="63543-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="63543-106">有关发布计划的信息，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="63543-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="63543-107">用户标记是 [Microsoft Defender for Office 365](office-365-atp.md)中特定用户组的标识符。</span><span class="sxs-lookup"><span data-stu-id="63543-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="63543-108">有两种类型的用户标记：</span><span class="sxs-lookup"><span data-stu-id="63543-108">There are two types of user tags:</span></span>

- <span data-ttu-id="63543-109">**系统标记**：目前 [，优先级帐户](../../admin/setup/priority-accounts.md) 是唯一类型的系统标记。</span><span class="sxs-lookup"><span data-stu-id="63543-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="63543-110">**自定义标记**：你可自己创建这些用户标记。</span><span class="sxs-lookup"><span data-stu-id="63543-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="63543-111">如果你的组织具有 Defender for Office 365 计划 2 (包含在订阅中或作为加载项) ，则除了使用优先级帐户标记外，还可以创建自定义用户标记。</span><span class="sxs-lookup"><span data-stu-id="63543-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="63543-112">向用户应用系统标记或自定义标记后，可以在警报、报告和调查中使用这些标记作为筛选器：</span><span class="sxs-lookup"><span data-stu-id="63543-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="63543-113">安全与合规中心&警报</span><span class="sxs-lookup"><span data-stu-id="63543-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="63543-114">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="63543-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="63543-115">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="63543-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="63543-116">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="63543-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="63543-117">对于优先级帐户，可以使用 Exchange[](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)管理中心中的"优先级帐户的电子邮件问题"报告 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="63543-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="63543-118">本文介绍如何在安全与合规中心内配置&标记。</span><span class="sxs-lookup"><span data-stu-id="63543-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="63543-119">安全与合规中心& cmdlet 用于管理用户标记。</span><span class="sxs-lookup"><span data-stu-id="63543-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="63543-120">若要了解用户标记如何作为策略的一部分来帮助保护高影响的用户帐户，请参阅 Microsoft [365](security-recommendations-for-priority-accounts.md)中优先级帐户的安全建议。</span><span class="sxs-lookup"><span data-stu-id="63543-120">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="63543-121">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="63543-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="63543-122">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="63543-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="63543-123">若要直接转到" **用户标记"** 页，请打开 <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="63543-123">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="63543-124">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="63543-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="63543-125">若要创建、修改和删除用户标记，您必须是组织管理或安全 **管理员\*\*\*\*角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="63543-125">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="63543-126">若要从现有用户标记中添加和删除成员，你需要是组织管理、**安全** 管理员或 **安全** 操作员角色组的成员</span><span class="sxs-lookup"><span data-stu-id="63543-126">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="63543-127">对于用户标记的只读访问，你需要是全局读取 **者** 或安全 **读者角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="63543-127">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="63543-128">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="63543-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="63543-129">**注意**：</span><span class="sxs-lookup"><span data-stu-id="63543-129">**Notes**:</span></span>

  - <span data-ttu-id="63543-130">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="63543-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="63543-131">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="63543-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="63543-132">用户标记管理由 Tag **Reader** 和 **Tag Manager 角色** 控制。</span><span class="sxs-lookup"><span data-stu-id="63543-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="63543-133">还可以在 Microsoft 365 管理中心管理和监视优先帐户。</span><span class="sxs-lookup"><span data-stu-id="63543-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="63543-134">有关说明，请参阅 [管理和监视优先级帐户](../../admin/setup/priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="63543-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="63543-135">使用安全&中心创建用户标记</span><span class="sxs-lookup"><span data-stu-id="63543-135">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="63543-136">在安全与&中心，转到"**威胁** 管理"" \> **用户标记"。**</span><span class="sxs-lookup"><span data-stu-id="63543-136">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63543-137">在打开 **的"用户标记**"页上，单击"**创建标记"。**</span><span class="sxs-lookup"><span data-stu-id="63543-137">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="63543-138">" **创建标记** "向导将在新的飞出控件中打开。在" **定义标记"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="63543-138">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="63543-139">**名称**：输入标记的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="63543-139">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="63543-140">这是你将看到并使用的值。</span><span class="sxs-lookup"><span data-stu-id="63543-140">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="63543-141">**说明**：输入标记的可选说明。</span><span class="sxs-lookup"><span data-stu-id="63543-141">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="63543-142">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="63543-142">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="63543-143">在 **"分配用户"** 页上，执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="63543-143">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="63543-144">单击 **"添加用户"。**</span><span class="sxs-lookup"><span data-stu-id="63543-144">Click **Add users**.</span></span> <span data-ttu-id="63543-145">在出现的"飞出"中，执行以下任一步骤以添加单个用户或组：</span><span class="sxs-lookup"><span data-stu-id="63543-145">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="63543-146">在框中单击并滚动浏览列表以选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="63543-146">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="63543-147">在框中单击并开始键入以筛选列表并选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="63543-147">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="63543-148">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="63543-148">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="63543-149">若要从框中删除单个条目，请单击框中用户或 ![ 组的" ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="63543-149">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="63543-150">若要从框下方的列表中删除现有条目，请单击" **删除** ![ "图标删除 ](../../media/scc-remove-icon.png) 条目。</span><span class="sxs-lookup"><span data-stu-id="63543-150">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="63543-151">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="63543-151">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="63543-152">单击 **"** 导入"选择一个包含用户或组的电子邮件地址的文本文件。</span><span class="sxs-lookup"><span data-stu-id="63543-152">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="63543-153">确保文本文件每行包含一个条目。</span><span class="sxs-lookup"><span data-stu-id="63543-153">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="63543-154">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="63543-154">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="63543-155">在" **审阅标记"** 页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="63543-155">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="63543-156">可以单击 **特定部分** 中的"编辑"进行更改。</span><span class="sxs-lookup"><span data-stu-id="63543-156">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="63543-157">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="63543-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="63543-158">使用安全&中心查看用户标记</span><span class="sxs-lookup"><span data-stu-id="63543-158">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="63543-159">在安全与&中心，转到"**威胁** 管理"" \> **用户标记"。**</span><span class="sxs-lookup"><span data-stu-id="63543-159">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63543-160">在打开 **的"** 用户标记"页上，选择要查看的用户标记 (不要单击复选框") "。</span><span class="sxs-lookup"><span data-stu-id="63543-160">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="63543-161">在出现的只读详细信息飞出中，查看设置。</span><span class="sxs-lookup"><span data-stu-id="63543-161">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="63543-162">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="63543-162">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="63543-163">使用安全&中心修改用户标记</span><span class="sxs-lookup"><span data-stu-id="63543-163">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="63543-164">在安全与&中心，转到"**威胁** 管理"" \> **用户标记"。**</span><span class="sxs-lookup"><span data-stu-id="63543-164">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63543-165">在打开 **的"用户标记**"页上，选择要查看的用户标记，然后单击"编辑 **标记"。**</span><span class="sxs-lookup"><span data-stu-id="63543-165">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="63543-166">策略向导将在"编辑"标记 **飞** 出中打开。单击 **"下** 一步"查看和修改设置。</span><span class="sxs-lookup"><span data-stu-id="63543-166">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="63543-167">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="63543-167">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="63543-168">使用安全&中心删除用户标记</span><span class="sxs-lookup"><span data-stu-id="63543-168">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="63543-169">**注意**：无法删除内置的 Priority **帐户** 标记。</span><span class="sxs-lookup"><span data-stu-id="63543-169">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="63543-170">在安全与&中心，转到"**威胁** 管理"" \> **用户标记"。**</span><span class="sxs-lookup"><span data-stu-id="63543-170">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="63543-171">在打开 **的"用户** 标记"页上，选择要删除的用户标记，单击"删除标记"，然后在出现的警告中选择"是，删除"。 </span><span class="sxs-lookup"><span data-stu-id="63543-171">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
