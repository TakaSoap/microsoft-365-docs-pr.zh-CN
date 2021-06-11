---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 计划 2 中标识具有用户标记的特定用户组。 可在 Microsoft Defender for Office 365警报、报告和调查之间使用标签筛选，以快速识别标记用户。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 105e927e50f7b1d1217587587b8d7ee3b7d6bd4c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904100"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="86d48-104">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="86d48-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="86d48-105">用户标记功能在预览版中，不可供所有人使用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="86d48-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="86d48-106">有关发布计划的信息，请查看Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="86d48-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="86d48-107">用户标记是 Microsoft Defender for Office 365[中的特定用户组的标识符](defender-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="86d48-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="86d48-108">有两种类型的用户标记：</span><span class="sxs-lookup"><span data-stu-id="86d48-108">There are two types of user tags:</span></span>

- <span data-ttu-id="86d48-109">**系统标记**：目前 [，优先级帐户](../../admin/setup/priority-accounts.md) 是唯一类型的系统标记。</span><span class="sxs-lookup"><span data-stu-id="86d48-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="86d48-110">**自定义标记**：你可自己创建这些用户标记。</span><span class="sxs-lookup"><span data-stu-id="86d48-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="86d48-111">如果你的组织拥有 Defender for Office 365 计划 2 (包含在订阅中或作为加载项) ，则除了使用优先级帐户标记外，还可以创建自定义用户标记。</span><span class="sxs-lookup"><span data-stu-id="86d48-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="86d48-112">目前，只能将用户标记应用于邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="86d48-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="86d48-113">向用户应用系统标记或自定义标记后，可以在警报、报告和调查中使用这些标记作为筛选器：</span><span class="sxs-lookup"><span data-stu-id="86d48-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="86d48-114">警告</span><span class="sxs-lookup"><span data-stu-id="86d48-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="86d48-115">自定义警报策略</span><span class="sxs-lookup"><span data-stu-id="86d48-115">Custom alert policies</span></span>](../../compliance/alert-policies.md#viewing-alerts)
- [<span data-ttu-id="86d48-116">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="86d48-116">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="86d48-117">电子邮件实体页面</span><span class="sxs-lookup"><span data-stu-id="86d48-117">Email entity page</span></span>](mdo-email-entity-page.md#other-innovations)
- [<span data-ttu-id="86d48-118">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="86d48-118">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="86d48-119">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="86d48-119">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="86d48-120">对于优先级帐户，可以在 EAC [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) Exchange管理中心 (优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="86d48-120">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="86d48-121">本文介绍了如何在 defender 门户中配置Microsoft 365标记。</span><span class="sxs-lookup"><span data-stu-id="86d48-121">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="86d48-122">Defender 门户中没有任何 cmdlet Microsoft 365管理用户标记。</span><span class="sxs-lookup"><span data-stu-id="86d48-122">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="86d48-123">若要了解用户标记如何作为策略的一部分来帮助保护高影响的用户帐户，请参阅安全建议[中](security-recommendations-for-priority-accounts.md)优先级帐户Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="86d48-123">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="86d48-124">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="86d48-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="86d48-125">在 打开Microsoft 365 Defender 门户 <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="86d48-125">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="86d48-126">若要直接转到" **用户标记"** 页，请打开 <https://security.microsoft.com/securitysettings/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="86d48-126">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="86d48-127">你需要在 defender 门户中Microsoft 365权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="86d48-127">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="86d48-128">若要创建、修改和删除用户标记，您必须是组织管理或安全 **管理员\*\*\*\*角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="86d48-128">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="86d48-129">若要从现有用户标记中添加和删除成员，你需要是组织管理、**安全** 管理员或 **安全** 操作员角色组的成员</span><span class="sxs-lookup"><span data-stu-id="86d48-129">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="86d48-130">对于用户标记的只读访问，你需要是全局读取 **者** 或安全 **读者角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="86d48-130">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="86d48-131">有关详细信息，请参阅 Defender 门户[中Microsoft 365权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="86d48-131">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="86d48-132">将用户添加到 Microsoft 365 管理中心中的相应 Azure Active Directory 角色会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="86d48-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="86d48-133">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="86d48-133">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="86d48-134">用户标记管理由 Tag **Reader** 和 **Tag Manager 角色** 控制。</span><span class="sxs-lookup"><span data-stu-id="86d48-134">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="86d48-135">还可以在管理中心内管理和监视Microsoft 365帐户。</span><span class="sxs-lookup"><span data-stu-id="86d48-135">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="86d48-136">有关说明，请参阅 [管理和监视优先级帐户](../../admin/setup/priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="86d48-136">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="86d48-137">有关保护管理员帐户 (特权 _帐户_) ，请参阅 [本主题](/azure/architecture/framework/security/critical-impact-accounts)。</span><span class="sxs-lookup"><span data-stu-id="86d48-137">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="86d48-138">使用 Microsoft 365 Defender 门户创建用户标记</span><span class="sxs-lookup"><span data-stu-id="86d48-138">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="86d48-139">在 Microsoft 365 Defender 门户中，转到设置 \> **电子邮件&协作** \> **用户标记。**</span><span class="sxs-lookup"><span data-stu-id="86d48-139">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="86d48-140">在"**用户标记"** 页上，单击" ![ 创建标记图标 ](../../media/m365-cc-sc-create-icon.png) **""创建标记"。**</span><span class="sxs-lookup"><span data-stu-id="86d48-140">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="86d48-141">" **创建标记** "向导将在新的飞出控件中打开。</span><span class="sxs-lookup"><span data-stu-id="86d48-141">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="86d48-142">在" **定义标记"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="86d48-142">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="86d48-143">**名称**：输入标记的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="86d48-143">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="86d48-144">这是你将看到并使用的值。</span><span class="sxs-lookup"><span data-stu-id="86d48-144">This is the value that you'll see and use.</span></span> <span data-ttu-id="86d48-145">请注意，创建标记后无法重命名它。</span><span class="sxs-lookup"><span data-stu-id="86d48-145">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="86d48-146">**说明**：输入标记的可选说明。</span><span class="sxs-lookup"><span data-stu-id="86d48-146">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="86d48-147">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="86d48-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="86d48-148">在 **"分配成员** "页上，执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="86d48-148">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="86d48-149">单击 ![ "添加成员"图标 ](../../media/m365-cc-sc-create-icon.png) **"添加成员"。**</span><span class="sxs-lookup"><span data-stu-id="86d48-149">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="86d48-150">在出现的"飞出"中，执行以下任一步骤以添加单个用户或组：</span><span class="sxs-lookup"><span data-stu-id="86d48-150">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="86d48-151">在框中单击并滚动浏览列表以选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="86d48-151">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="86d48-152">在框中单击并开始键入以筛选列表并选择用户或组。</span><span class="sxs-lookup"><span data-stu-id="86d48-152">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="86d48-153">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="86d48-153">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="86d48-154">若要删除单个条目，请单击</span><span class="sxs-lookup"><span data-stu-id="86d48-154">To remove individual entries, click</span></span> ![删除条目图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="86d48-156">框中的条目旁边。</span><span class="sxs-lookup"><span data-stu-id="86d48-156">next to the entry in the box.</span></span>
     - <span data-ttu-id="86d48-157">若要删除所有条目，请单击框下方的"所选 nn 用户和 nn 组"项上的" ![ ](../../media/m365-cc-sc-remove-selection-icon.png) 删除条目图标"。 </span><span class="sxs-lookup"><span data-stu-id="86d48-157">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="86d48-158">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="86d48-158">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="86d48-159">返回到" **分配成员** "页，您还可以通过单击条目旁边的"删除 ![ "图标 ](../../media/m365-cc-sc-delete-icon.png) 来删除条目。</span><span class="sxs-lookup"><span data-stu-id="86d48-159">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="86d48-160">单击 **"** 导入"选择一个包含用户或组的电子邮件地址的文本文件。</span><span class="sxs-lookup"><span data-stu-id="86d48-160">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="86d48-161">确保文本文件每行包含一个条目。</span><span class="sxs-lookup"><span data-stu-id="86d48-161">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="86d48-162">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="86d48-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="86d48-163">在出现的 **"审阅标记** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="86d48-163">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="86d48-164">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="86d48-164">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="86d48-165">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="86d48-165">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="86d48-166">完成后，单击"提交 **"，** 然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="86d48-166">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="86d48-167">使用 Microsoft 365 Defender 门户查看用户标记</span><span class="sxs-lookup"><span data-stu-id="86d48-167">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="86d48-168">在 Microsoft 365 Defender 门户中，转到设置 \> **电子邮件&协作** \> **用户标记。**</span><span class="sxs-lookup"><span data-stu-id="86d48-168">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="86d48-169">在 **"用户标记** "页上，用户标记列表中将显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="86d48-169">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="86d48-170">**Tag**：用户标记的名称。</span><span class="sxs-lookup"><span data-stu-id="86d48-170">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="86d48-171">请注意，这包括内置的 **优先级帐户** 系统标记。</span><span class="sxs-lookup"><span data-stu-id="86d48-171">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="86d48-172">**应用于**：成员数</span><span class="sxs-lookup"><span data-stu-id="86d48-172">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="86d48-173">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="86d48-173">**Last modified**</span></span>
   - <span data-ttu-id="86d48-174">**创建于**</span><span class="sxs-lookup"><span data-stu-id="86d48-174">**Created on**</span></span>

3. <span data-ttu-id="86d48-175">当您通过单击该名称选择用户标记时，详细信息将显示在一个 flyout 中。</span><span class="sxs-lookup"><span data-stu-id="86d48-175">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="86d48-176">使用 Microsoft 365 Defender 门户修改用户标记</span><span class="sxs-lookup"><span data-stu-id="86d48-176">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="86d48-177">在 Microsoft 365 Defender 门户中，转到设置 \> **电子邮件&协作** \> **用户标记。**</span><span class="sxs-lookup"><span data-stu-id="86d48-177">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="86d48-178">在"**用户标记**"页上，从列表中选择用户标记，然后单击"编辑 ![ 标记图标"" ](../../media/m365-cc-sc-edit-icon.png) **编辑标记"。**</span><span class="sxs-lookup"><span data-stu-id="86d48-178">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="86d48-179">在出现的详细信息飞出控件中，提供相同的向导和设置，如本文前面使用[Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags)门户创建用户标记部分所述。</span><span class="sxs-lookup"><span data-stu-id="86d48-179">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="86d48-180">**注意**：</span><span class="sxs-lookup"><span data-stu-id="86d48-180">**Notes**:</span></span>

   - <span data-ttu-id="86d48-181">" **定义标记** "页对内置 **Priority** 帐户系统标记不可用，因此无法重命名此标记或更改说明。</span><span class="sxs-lookup"><span data-stu-id="86d48-181">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="86d48-182">不能重命名自定义标记，但可以更改说明。</span><span class="sxs-lookup"><span data-stu-id="86d48-182">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="86d48-183">使用 Microsoft 365 Defender 门户删除用户标记</span><span class="sxs-lookup"><span data-stu-id="86d48-183">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="86d48-184">无法删除内置的 **优先级帐户系统** 标记。</span><span class="sxs-lookup"><span data-stu-id="86d48-184">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="86d48-185">在 Microsoft 365 Defender 门户中，转到设置 \> **电子邮件&协作** \> **用户标记。**</span><span class="sxs-lookup"><span data-stu-id="86d48-185">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="86d48-186">在"**用户标记**"页上，从列表中选择用户标记，然后单击"删除 ![ 标记图标"" ](../../media/m365-cc-sc-delete-icon.png) **删除标记"。**</span><span class="sxs-lookup"><span data-stu-id="86d48-186">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="86d48-187">阅读出现的确认对话框中的警告，然后单击"是 **，删除"。**</span><span class="sxs-lookup"><span data-stu-id="86d48-187">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
