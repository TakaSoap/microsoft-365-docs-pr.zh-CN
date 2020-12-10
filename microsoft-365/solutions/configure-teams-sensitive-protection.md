---
title: 配置具有敏感数据保护的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: 了解如何部署具有敏感数据保护的团队。
ms.openlocfilehash: ad1cf437bdbe3bd7b25347bb49698314097462ab
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612948"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="591e0-103">配置具有敏感数据保护的团队</span><span class="sxs-lookup"><span data-stu-id="591e0-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="591e0-104">在本文中，我们将了解如何针对敏感级别的保护设置团队。</span><span class="sxs-lookup"><span data-stu-id="591e0-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="591e0-105">在执行本文中的步骤之前，请确保已完成[部署具有基线保护的团队](configure-teams-baseline-protection.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="591e0-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="591e0-106">敏感级别提供了以下超出基线层级的额外保护：</span><span class="sxs-lookup"><span data-stu-id="591e0-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="591e0-107">团队的敏感度标签，可用于打开或关闭来宾共享，并仅允许未托管设备通过 Web 访问 SharePoint 内容。</span><span class="sxs-lookup"><span data-stu-id="591e0-107">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices.</span></span> <span data-ttu-id="591e0-108">此标签还可用于对文件进行分类。</span><span class="sxs-lookup"><span data-stu-id="591e0-108">This label can also be used to classify files.</span></span>
- <span data-ttu-id="591e0-109">限制性更强的默认共享链接类型</span><span class="sxs-lookup"><span data-stu-id="591e0-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="591e0-110">只有团队所有者可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="591e0-110">Only team owners can create private channels.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="591e0-111">来宾共享</span><span class="sxs-lookup"><span data-stu-id="591e0-111">Guest sharing</span></span>

<span data-ttu-id="591e0-112">根据业务性质，你可能希望也可能不希望为包含敏感数据的团队启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="591e0-112">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="591e0-113">如果确实计划与团队中的组织外部人员进行协作，则建议启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="591e0-113">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="591e0-114">Microsoft 365 包括许多安全性和合规性功能，可帮助你安全地共享敏感内容。</span><span class="sxs-lookup"><span data-stu-id="591e0-114">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="591e0-115">这通常比直接通过电子邮件向组织外部的人员发送内容更安全。</span><span class="sxs-lookup"><span data-stu-id="591e0-115">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="591e0-116">有关与来宾安全共享的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="591e0-116">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="591e0-117">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="591e0-117">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="591e0-118">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="591e0-118">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="591e0-119">为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。</span><span class="sxs-lookup"><span data-stu-id="591e0-119">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="591e0-120">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="591e0-120">Sensitivity labels</span></span>

<span data-ttu-id="591e0-121">对于敏感级别的保护，我们将使用敏感度标签对团队进行分类。</span><span class="sxs-lookup"><span data-stu-id="591e0-121">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="591e0-122">此标签还可用于分类此团队或其他团队，或者其他文件位置（如 SharePoint 或 OneDrive）中的单个文件。</span><span class="sxs-lookup"><span data-stu-id="591e0-122">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="591e0-123">首先，必须为 Teams 启用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="591e0-123">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="591e0-124">有关详细信息，请参阅[使用敏感度标签保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="591e0-124">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) for details.</span></span>

<span data-ttu-id="591e0-125">如果已在组织中部署了敏感度标签，请考虑此标签与总体标签策略的匹配情况。</span><span class="sxs-lookup"><span data-stu-id="591e0-125">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="591e0-126">可根据需要更改名称或设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="591e0-126">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="591e0-127">为 Teams 启用灵敏度标签后，下一步是创建标签。</span><span class="sxs-lookup"><span data-stu-id="591e0-127">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="591e0-128">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="591e0-128">To create a sensitivity label</span></span>
1. <span data-ttu-id="591e0-129">打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="591e0-129">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="591e0-130">在“**解决方案**”下，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-130">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="591e0-131">单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-131">Click **Create a label**.</span></span>
4. <span data-ttu-id="591e0-132">为标签命名。</span><span class="sxs-lookup"><span data-stu-id="591e0-132">Give the label a name.</span></span> <span data-ttu-id="591e0-133">建议使用“**敏感**”，但如果该名称已在使用，则可以选择其他名称。</span><span class="sxs-lookup"><span data-stu-id="591e0-133">We suggest **sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="591e0-134">添加工具提示，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-134">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="591e0-135">在“**加密**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-135">On the **Encryption** page, click **Next**.</span></span>
7. <span data-ttu-id="591e0-136">如果希望自动向使用此标签分类的文件添加页眉、页脚或水印，请在“**内容标记**”页面上启用内容标记。</span><span class="sxs-lookup"><span data-stu-id="591e0-136">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
8. <span data-ttu-id="591e0-137">在“**网站和组设置**”页面上，将“**网站和组设置**”设置为“**开启**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-137">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
9. <span data-ttu-id="591e0-138">在“**Office 365 与组连接的团队网站的隐私**”下拉菜单中，选择“**专用 - 只有成员才能访问网站**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-138">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
10. <span data-ttu-id="591e0-139">如果想要允许来宾访问，请选择“**允许 Office 365 组所有者向组中添加组织外部人员**”复选框。</span><span class="sxs-lookup"><span data-stu-id="591e0-139">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
11. <span data-ttu-id="591e0-140">在“**非托管的设备**”下，选择“**允许仅限于 Web 的访问**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-140">Under **Unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
12. <span data-ttu-id="591e0-141">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-141">Click **Next**.</span></span>
13. <span data-ttu-id="591e0-142">在“**Office 应用程序自动标记**”页面上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-142">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
14. <span data-ttu-id="591e0-143">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-143">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="591e0-144">创建标签后，需要将其发布到使用它的用户。</span><span class="sxs-lookup"><span data-stu-id="591e0-144">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="591e0-145">对于敏感保护，我们将对所有用户提供该标签。</span><span class="sxs-lookup"><span data-stu-id="591e0-145">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="591e0-146">在 Microsoft 365 合规中心的“**信息保护**”页面的“**标签策略**”选项卡上发布标签。</span><span class="sxs-lookup"><span data-stu-id="591e0-146">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="591e0-147">如果你拥有适用于所有用户的现有策略，请将此标签添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="591e0-147">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="591e0-148">如果需要创建新策略，请参阅[通过创建标签策略来发布灵敏度标签](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="591e0-148">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="591e0-149">创建团队</span><span class="sxs-lookup"><span data-stu-id="591e0-149">Create a team</span></span>

<span data-ttu-id="591e0-150">对敏感方案的进一步配置在与团队相关联的 SharePoint 网站中完成，因此下一步是创建团队。</span><span class="sxs-lookup"><span data-stu-id="591e0-150">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="591e0-151">针对敏感信息创建团队</span><span class="sxs-lookup"><span data-stu-id="591e0-151">To create a team for sensitive information</span></span>
1. <span data-ttu-id="591e0-152">在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-152">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="591e0-153">点击“**创建团队**”（第一张卡片，左上角）。</span><span class="sxs-lookup"><span data-stu-id="591e0-153">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="591e0-154">选择“**从头开始构建团队**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-154">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="591e0-155">在“**灵敏度**”列表中，选择刚才创建的“**敏感**”标签。</span><span class="sxs-lookup"><span data-stu-id="591e0-155">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="591e0-156">在“**隐私**”下，单击“**专用**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-156">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="591e0-157">为该团队键入一个名称，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-157">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="591e0-158">将用户添加到团队，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-158">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="591e0-159">专用频道设置</span><span class="sxs-lookup"><span data-stu-id="591e0-159">Private channel settings</span></span>

<span data-ttu-id="591e0-160">在此层级，仅限团队所有者创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="591e0-160">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="591e0-161">限制专用频道创建</span><span class="sxs-lookup"><span data-stu-id="591e0-161">To restrict private channel creation</span></span>
1. <span data-ttu-id="591e0-162">在团队中，单击“**更多选项**”，然后单击“**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-162">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="591e0-163">在“**设置**”选项卡上，展开“**成员权限**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-163">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="591e0-164">清除“**允许成员创建专用频道**”复选框。</span><span class="sxs-lookup"><span data-stu-id="591e0-164">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="591e0-165">还可以使用“[团队策略](https://docs.microsoft.com/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="591e0-165">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="591e0-166">SharePoint 设置</span><span class="sxs-lookup"><span data-stu-id="591e0-166">SharePoint settings</span></span>

<span data-ttu-id="591e0-167">每次使用敏感标签创建新团队时，都需要在 SharePoint 中执行两步操作：</span><span class="sxs-lookup"><span data-stu-id="591e0-167">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="591e0-168">更新 SharePoint 管理中心中网站的来宾共享设置，使其与创建标签时选择的内容一致，并将默认共享链接更新为“*特定用户*”。</span><span class="sxs-lookup"><span data-stu-id="591e0-168">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="591e0-169">更新网站本身的网站共享设置，防止成员共享网站。</span><span class="sxs-lookup"><span data-stu-id="591e0-169">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-guest-sharing-settings"></a><span data-ttu-id="591e0-170">网站来宾共享设置</span><span class="sxs-lookup"><span data-stu-id="591e0-170">Site guest sharing settings</span></span>

<span data-ttu-id="591e0-171">创建标签时选择的来宾共享设置（仅影响团队成员身份）应与关联的SharePoint 网站的来宾共享设置匹配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="591e0-171">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="591e0-172">标签设置</span><span class="sxs-lookup"><span data-stu-id="591e0-172">Label setting</span></span>|<span data-ttu-id="591e0-173">SharePoint 网站设置</span><span class="sxs-lookup"><span data-stu-id="591e0-173">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="591e0-174">**允许 Office 365 组所有者将组织外部的人员添加到组** 已选中</span><span class="sxs-lookup"><span data-stu-id="591e0-174">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="591e0-175">**新来宾和现有来宾**（新团队默认值）</span><span class="sxs-lookup"><span data-stu-id="591e0-175">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="591e0-176">**允许 Office 365 组所有者将组织外部的人员添加到组** 未选中</span><span class="sxs-lookup"><span data-stu-id="591e0-176">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="591e0-177">**仅组织内部人员**</span><span class="sxs-lookup"><span data-stu-id="591e0-177">**Only people in your organization**</span></span>|

<span data-ttu-id="591e0-178">更新网站设置</span><span class="sxs-lookup"><span data-stu-id="591e0-178">To update site settings</span></span>
1. <span data-ttu-id="591e0-179">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="591e0-179">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="591e0-180">在“**网站**”下，单击“**活动的网站**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-180">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="591e0-181">单击与团队关联的网站。</span><span class="sxs-lookup"><span data-stu-id="591e0-181">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="591e0-182">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-182">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="591e0-183">如果在创建敏感标签时允许来宾共享，请确保选定“**新来宾和现有来宾**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-183">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="591e0-184">如果创建标签时不允许共享，请选择“**仅限组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-184">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="591e0-185">在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**特定人员(仅用户指定的人员)**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-185">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
7. <span data-ttu-id="591e0-186">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-186">Click **Save**.</span></span>

<span data-ttu-id="591e0-187">如果要将在团队创建过程中编制脚本，可使用含有以下参数的 [Set-sposite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite)：</span><span class="sxs-lookup"><span data-stu-id="591e0-187">If you want to script this as part of your team creation process, you can use [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) with the following parameters:</span></span>

- <span data-ttu-id="591e0-188">`-SharingCapability Disabled` 用于禁用来宾共享（默认启用）</span><span class="sxs-lookup"><span data-stu-id="591e0-188">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="591e0-189">`-DefaultSharingLinkType Internal` 用于更改“*指定人员*”的默认共享链接</span><span class="sxs-lookup"><span data-stu-id="591e0-189">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

#### <a name="private-channels"></a><span data-ttu-id="591e0-190">专用频道</span><span class="sxs-lookup"><span data-stu-id="591e0-190">Private channels</span></span>

<span data-ttu-id="591e0-191">如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="591e0-191">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="591e0-192">这些网站在 SharePoint 管理中心中不可见，因此必须使用 Set-SPOSite PowerShell cmdlet 来更新来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="591e0-192">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="591e0-193">网站共享设置</span><span class="sxs-lookup"><span data-stu-id="591e0-193">Site sharing settings</span></span>

<span data-ttu-id="591e0-194">为了帮助确保不与非团队成员共享 SharePoint 网站，我们限制为仅允许所有者进行此类共享。</span><span class="sxs-lookup"><span data-stu-id="591e0-194">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="591e0-195">配置仅限所有者的网站共享</span><span class="sxs-lookup"><span data-stu-id="591e0-195">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="591e0-196">在 Teams 中，导航至要更新团队的“**常规**”标签。</span><span class="sxs-lookup"><span data-stu-id="591e0-196">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="591e0-197">在团队的工具栏中，单击“文件”。</span><span class="sxs-lookup"><span data-stu-id="591e0-197">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="591e0-198">单击省略号，然后单击“在 SharePoint 中打开”。</span><span class="sxs-lookup"><span data-stu-id="591e0-198">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="591e0-199">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”。</span><span class="sxs-lookup"><span data-stu-id="591e0-199">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="591e0-200">在“网站权限”窗格的“**共享设置**”下方，单击“**更改共享设置**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-200">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="591e0-201">在“**共享权限**”下，选择选择“**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="591e0-201">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="591e0-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="591e0-202">See Also</span></span>

[<span data-ttu-id="591e0-203">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="591e0-203">Create and configure sensitivity labels and their policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)


