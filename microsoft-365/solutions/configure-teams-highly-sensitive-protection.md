---
title: 配置具有高度敏感数据保护的团队
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
recommendations: false
description: 了解如何部署具有高度敏感数据保护的团队。
ms.openlocfilehash: 7c5485a008434b351eebbec3ea1f20b10d82278a
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583684"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a><span data-ttu-id="569ef-103">配置具有高度敏感数据保护的团队</span><span class="sxs-lookup"><span data-stu-id="569ef-103">Configure teams with protection for highly sensitive data</span></span>

<span data-ttu-id="569ef-104">在本文中，我们将了解如何针对高度敏感级别的保护设置团队。</span><span class="sxs-lookup"><span data-stu-id="569ef-104">In this article, we look at setting up a team for a highly sensitive level of protection.</span></span> <span data-ttu-id="569ef-105">在执行本文中的步骤之前，请确保已完成[部署具有基线保护的团队](configure-teams-baseline-protection.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="569ef-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span>

<span data-ttu-id="569ef-106">对于这一层级的保护，我们创建了敏感度标签，可在组织中使用此敏感度标签来处理高度敏感的团队和文件。</span><span class="sxs-lookup"><span data-stu-id="569ef-106">For this tier of protection, we create a sensitivity label that can be used across your organization for highly sensitive teams and files.</span></span> <span data-ttu-id="569ef-107">只有组织成员和指定来宾才能解密使用此标签的文件。</span><span class="sxs-lookup"><span data-stu-id="569ef-107">Only members of your organization and guests that you have specified will be able to decrypt files that use this label.</span></span> <span data-ttu-id="569ef-108">如果需要进一步的隔离权限，使只有指定团队成员才能解密文件，参见[部署具有安全隔离的团队](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="569ef-108">If you need to further isolate permissions so that only members of a specific team can decrypt files, see  [Deploy a team with security isolation](secure-teams-security-isolation.md).</span></span>

<span data-ttu-id="569ef-109">高度敏感级别提供了以下超出基线层级的额外保护：</span><span class="sxs-lookup"><span data-stu-id="569ef-109">The highly sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="569ef-p103">团队的敏感度标签，可用于打开或关闭来宾共享，并阻止未托管设备访问 SharePoint 内容。此标签还可用于对文件进行分类和解密。</span><span class="sxs-lookup"><span data-stu-id="569ef-p103">A sensitivity label for the team that allows you to turn guest sharing on or off and blocks access to SharePoint content for unmanaged devices. This label can also be used to classify and encrypt files.</span></span>
- <span data-ttu-id="569ef-112">限制性更强的默认共享链接类型</span><span class="sxs-lookup"><span data-stu-id="569ef-112">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="569ef-113">只有团队所有者可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="569ef-113">Only team owners can create private channels.</span></span>
- <span data-ttu-id="569ef-114">关联 SharePoint 网站的访问请求被关闭。</span><span class="sxs-lookup"><span data-stu-id="569ef-114">Access requests for the associated SharePoint site are turned off.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="569ef-115">来宾共享</span><span class="sxs-lookup"><span data-stu-id="569ef-115">Guest sharing</span></span>

<span data-ttu-id="569ef-116">根据业务性质，你可能希望也可能不希望为包含高度敏感数据的团队启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="569ef-116">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain highly sensitive data.</span></span> <span data-ttu-id="569ef-117">如果确实计划与团队中的组织外部人员进行协作，则建议启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="569ef-117">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="569ef-118">Microsoft 365 包括许多安全性和合规性功能，可帮助你安全地共享敏感内容。</span><span class="sxs-lookup"><span data-stu-id="569ef-118">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="569ef-119">这通常比直接通过电子邮件向组织外部的人员发送内容更安全。</span><span class="sxs-lookup"><span data-stu-id="569ef-119">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="569ef-120">有关与来宾安全共享的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="569ef-120">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="569ef-121">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="569ef-121">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="569ef-122">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="569ef-122">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="569ef-123">为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。</span><span class="sxs-lookup"><span data-stu-id="569ef-123">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="569ef-124">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="569ef-124">Sensitivity labels</span></span>

<span data-ttu-id="569ef-125">对于高度敏感级别的保护，我们将使用敏感度标签对团队进行分类。</span><span class="sxs-lookup"><span data-stu-id="569ef-125">For the highly sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="569ef-126">此标签还可用于分类和解密此团队或其他团队，或者其他文件位置（如 SharePoint 或 OneDrive）中的单个文件。</span><span class="sxs-lookup"><span data-stu-id="569ef-126">This label can also be used to classify and encrypt individual files in this or other teams or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="569ef-127">首先，必须为 Teams 启用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="569ef-127">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="569ef-128">有关详细信息，请参阅[使用敏感度标签保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="569ef-128">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="569ef-129">如果已在组织中部署了敏感度标签，请考虑此标签与总体标签策略的匹配情况。</span><span class="sxs-lookup"><span data-stu-id="569ef-129">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="569ef-130">可根据需要更改名称或设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="569ef-130">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="569ef-131">为 Teams 启用灵敏度标签后，下一步是创建标签。</span><span class="sxs-lookup"><span data-stu-id="569ef-131">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="569ef-132">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="569ef-132">To create a sensitivity label</span></span>
1. <span data-ttu-id="569ef-133">打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="569ef-133">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="569ef-134">在“**解决方案**”下，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-134">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="569ef-135">单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-135">Click **Create a label**.</span></span>
4. <span data-ttu-id="569ef-136">为标签命名。</span><span class="sxs-lookup"><span data-stu-id="569ef-136">Give the label a name.</span></span> <span data-ttu-id="569ef-137">建议使用“**高度敏感**”，但如果该名称已在使用，则可以选择其他名称。</span><span class="sxs-lookup"><span data-stu-id="569ef-137">We suggest **Highly sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="569ef-138">添加显示名称和说明，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-138">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="569ef-139">在“**定义此标签页的搜索范围**”中，选择“**文件和电子邮件**”和“**组和站点**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-139">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="569ef-140">在“**选择文件和电子邮件的保护设置**”页面中，选择“**加密文件和电子邮件**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-140">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="569ef-141">在“**加密页面中**”页面中，选择“**配置加密设置**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-141">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="569ef-142">在“**向特定用户和组分配权限**”下，单击“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-142">Under **Assign permissions to specific users and groups**, click **Assign permissions**.</span></span>
10. <span data-ttu-id="569ef-143">点击“**添加组织中的所有用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-143">Click **Add all users and groups in your organization**.</span></span>
11. <span data-ttu-id="569ef-144">如果某些来宾应具有解密文件的权限，请单击“**添加用户或组**”并添加他们。</span><span class="sxs-lookup"><span data-stu-id="569ef-144">If there are guests who should have permissions to decrypt files, click **Add users or groups** and add them.</span></span>
12.  <span data-ttu-id="569ef-145">单击“**保存**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-145">Click **Save**, and then click **Next**.</span></span>
13. <span data-ttu-id="569ef-146">在“*文件和电子邮件自动标记*”页面中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-146">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
14. <span data-ttu-id="569ef-147">在“**定义组和站点的防护设置**”页面中，选择“**隐私和外部用户访问设置**”和“**设备权限和外部共享设置**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-147">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
15. <span data-ttu-id="569ef-148">在“**定义隐私和外部用户权限设置**”页面中，选择“**隐私**”下的“**私人**”选项。</span><span class="sxs-lookup"><span data-stu-id="569ef-148">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
16. <span data-ttu-id="569ef-149">如果你想允许来宾访问，选择“**外部用户权限**”下的“**让 Microsoft 365 组所有者添加组织外的人员为来宾**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-149">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
17. <span data-ttu-id="569ef-150">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-150">Click **Next**.</span></span>
18. <span data-ttu-id="569ef-151">在“**定义外部共享和设备权限设置**”页面中，选择“**从标记的 SharePoint 站点控制外部共享**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-151">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
19. <span data-ttu-id="569ef-152">如果当前允许来宾访问，在“**无法共享的内容**”下选择“**新的和当前来宾**”；如果不允许，则选择“**仅组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-152">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
20. <span data-ttu-id="569ef-153">在“**未托管的设备的访问**”下，选择“**阻止访问**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-153">Under **Access from unmanaged devices**, choose **Block access**.</span></span> <span data-ttu-id="569ef-154">（如果允许来宾且其没有托管设备，建议选择 **仅允许仅 Web 访问"**。）</span><span class="sxs-lookup"><span data-stu-id="569ef-154">(If you're allowing guests and they don't have managed devices, you may want to choose **Allow limited, web-only access**.)</span></span>
21. <span data-ttu-id="569ef-155">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-155">Click **Next**.</span></span>
22. <span data-ttu-id="569ef-156">在“**数据库列自动标记**”页面中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-156">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
23. <span data-ttu-id="569ef-157">单击“**创建标签**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-157">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="569ef-158">创建标签后，需要将其发布到使用它的用户。</span><span class="sxs-lookup"><span data-stu-id="569ef-158">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="569ef-159">对于敏感保护，我们将对所有用户提供该标签。</span><span class="sxs-lookup"><span data-stu-id="569ef-159">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="569ef-160">在 Microsoft 365 合规中心的“**信息保护**”页面的“**标签策略**”选项卡上发布标签。</span><span class="sxs-lookup"><span data-stu-id="569ef-160">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="569ef-161">如果你拥有适用于所有用户的现有策略，请将此标签添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="569ef-161">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="569ef-162">如果需要创建新策略，请参阅[通过创建标签策略来发布灵敏度标签](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="569ef-162">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="569ef-163">创建团队</span><span class="sxs-lookup"><span data-stu-id="569ef-163">Create a team</span></span>

<span data-ttu-id="569ef-164">对高度敏感方案的进一步配置在与团队相关联的 SharePoint 网站中完成，因此下一步是创建团队。</span><span class="sxs-lookup"><span data-stu-id="569ef-164">Further configuration of the highly sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="569ef-165">创建高度敏感信息团队</span><span class="sxs-lookup"><span data-stu-id="569ef-165">To create a team for highly sensitive information</span></span>
1. <span data-ttu-id="569ef-166">在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-166">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="569ef-167">点击“**创建团队**”（第一张卡片，左上角）。</span><span class="sxs-lookup"><span data-stu-id="569ef-167">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="569ef-168">选择“**从头开始构建团队**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-168">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="569ef-169">在“**敏感度**”列表中，选择刚才创建的“**高敏感**”标签。</span><span class="sxs-lookup"><span data-stu-id="569ef-169">In the **Sensitivity** list, choose the **Highly sensitive** label that you just created.</span></span>
5. <span data-ttu-id="569ef-170">在“**隐私**”下，单击“**专用**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-170">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="569ef-171">为该团队键入一个名称，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-171">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="569ef-172">将用户添加到团队，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-172">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="569ef-173">专用频道设置</span><span class="sxs-lookup"><span data-stu-id="569ef-173">Private channel settings</span></span>

<span data-ttu-id="569ef-174">在此层级，仅限团队所有者创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="569ef-174">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="569ef-175">限制专用频道创建</span><span class="sxs-lookup"><span data-stu-id="569ef-175">To restrict private channel creation</span></span>
1. <span data-ttu-id="569ef-176">在团队中，单击“**更多选项**”，然后单击“**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-176">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="569ef-177">在“**设置**”选项卡上，展开“**成员权限**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-177">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="569ef-178">清除“**允许成员创建专用频道**”复选框。</span><span class="sxs-lookup"><span data-stu-id="569ef-178">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="569ef-179">还可以使用“[团队策略](/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="569ef-179">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="569ef-180">SharePoint 设置</span><span class="sxs-lookup"><span data-stu-id="569ef-180">SharePoint settings</span></span>

<span data-ttu-id="569ef-181">每次使用高度敏感标签创建新团队时，都需要在 SharePoint 中执行两步操作：</span><span class="sxs-lookup"><span data-stu-id="569ef-181">Each time you create a new team with the highly sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="569ef-182">在 SharePoint 管理中心内更新网站的来宾共享设置，以将默认共享链接更新为 *具有现有访问权限的人员*。</span><span class="sxs-lookup"><span data-stu-id="569ef-182">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="569ef-183">自主更新网站中的网站共享设置，防止成员共享文件、文件夹或网站，并关闭访问请求。</span><span class="sxs-lookup"><span data-stu-id="569ef-183">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="569ef-184">网站默认共享链接设置</span><span class="sxs-lookup"><span data-stu-id="569ef-184">Site default sharing link settings</span></span>

<span data-ttu-id="569ef-185">更新网站默认共享链接类型</span><span class="sxs-lookup"><span data-stu-id="569ef-185">To update the site default sharing link type</span></span>

1. <span data-ttu-id="569ef-186">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="569ef-186">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="569ef-187">在“**网站**”下，单击“**活动的网站**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-187">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="569ef-188">单击与团队关联的网站。</span><span class="sxs-lookup"><span data-stu-id="569ef-188">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="569ef-189">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-189">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="569ef-190">在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**具有现有访问权限的人员**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-190">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
6. <span data-ttu-id="569ef-191">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-191">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="569ef-192">专用频道</span><span class="sxs-lookup"><span data-stu-id="569ef-192">Private channels</span></span>

<span data-ttu-id="569ef-193">如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="569ef-193">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="569ef-194">这些网站在 SharePoint 管理中心中不可见，因此必须使用 Set-SPOSite PowerShell cmdlet 来更新来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="569ef-194">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="569ef-195">网站共享设置</span><span class="sxs-lookup"><span data-stu-id="569ef-195">Site sharing settings</span></span>

<span data-ttu-id="569ef-196">为了确保不与非团队成员共享 SharePoint 网站，我们将此类共享限制为所有者。</span><span class="sxs-lookup"><span data-stu-id="569ef-196">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="569ef-197">我们还将文件和文件夹的共享限制为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="569ef-197">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="569ef-198">这有助于确保无论何时与团队外部人员共享文件，所有者都会知道。</span><span class="sxs-lookup"><span data-stu-id="569ef-198">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="569ef-199">配置仅限所有者的网站共享</span><span class="sxs-lookup"><span data-stu-id="569ef-199">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="569ef-200">在 Teams 中，导航至要更新团队的“**常规**”标签。</span><span class="sxs-lookup"><span data-stu-id="569ef-200">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="569ef-201">在团队的工具栏中，单击“文件”。</span><span class="sxs-lookup"><span data-stu-id="569ef-201">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="569ef-202">单击省略号，然后单击“在 SharePoint 中打开”。</span><span class="sxs-lookup"><span data-stu-id="569ef-202">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="569ef-203">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”。</span><span class="sxs-lookup"><span data-stu-id="569ef-203">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="569ef-204">在“**网站权限**”窗格的“**网站共享**”下方，单击“**更改成员共享方式**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-204">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="569ef-205">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-205">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
7. <span data-ttu-id="569ef-206">将“**允许访问请求**”设置为“**关闭**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="569ef-206">Set **Allow access requests** to **Off**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="569ef-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="569ef-207">See Also</span></span>

[<span data-ttu-id="569ef-208">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="569ef-208">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
