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
ms.openlocfilehash: 3e98b1a52e698d52eba16d4296c062d7347759d0
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788351"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a><span data-ttu-id="b0942-103">配置具有高度敏感数据保护的团队</span><span class="sxs-lookup"><span data-stu-id="b0942-103">Configure teams with protection for highly sensitive data</span></span>

<span data-ttu-id="b0942-104">在本文中，我们将了解如何针对高度敏感级别的保护设置团队。</span><span class="sxs-lookup"><span data-stu-id="b0942-104">In this article, we look at setting up a team for a highly sensitive level of protection.</span></span> <span data-ttu-id="b0942-105">在执行本文中的步骤之前，请确保已完成[部署具有基线保护的团队](configure-teams-baseline-protection.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="b0942-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span>

<span data-ttu-id="b0942-106">对于这一层级的保护，我们创建了敏感度标签，可在组织中使用此敏感度标签来处理高度敏感的团队和文件。</span><span class="sxs-lookup"><span data-stu-id="b0942-106">For this tier of protection, we create a sensitivity label that can be used across your organization for highly sensitive teams and files.</span></span> <span data-ttu-id="b0942-107">只有组织成员和指定来宾才能解密使用此标签的文件。</span><span class="sxs-lookup"><span data-stu-id="b0942-107">Only members of your organization and guests that you have specified will be able to decrypt files that use this label.</span></span> <span data-ttu-id="b0942-108">如果需要进一步的隔离权限，使只有指定团队成员才能解密文件，参见[部署具有安全隔离的团队](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="b0942-108">If you need to further isolate permissions so that only members of a specific team can decrypt files, see  [Deploy a team with security isolation](secure-teams-security-isolation.md).</span></span>

<span data-ttu-id="b0942-109">高度敏感级别提供了以下超出基线层级的额外保护：</span><span class="sxs-lookup"><span data-stu-id="b0942-109">The highly sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="b0942-p103">团队的敏感度标签，可用于打开或关闭来宾共享，并阻止未托管设备访问 SharePoint 内容。此标签还可用于对文件进行分类和解密。</span><span class="sxs-lookup"><span data-stu-id="b0942-p103">A sensitivity label for the team that allows you to turn guest sharing on or off and blocks access to SharePoint content for unmanaged devices. This label can also be used to classify and encrypt files.</span></span>
- <span data-ttu-id="b0942-112">限制性更强的默认共享链接类型</span><span class="sxs-lookup"><span data-stu-id="b0942-112">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="b0942-113">只有团队所有者可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="b0942-113">Only team owners can create private channels.</span></span>
- <span data-ttu-id="b0942-114">关联 SharePoint 网站的访问请求被关闭。</span><span class="sxs-lookup"><span data-stu-id="b0942-114">Access requests for the associated SharePoint site are turned off.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b0942-115">视频演示</span><span class="sxs-lookup"><span data-stu-id="b0942-115">Video demonstration</span></span>

<span data-ttu-id="b0942-116">观看此视频，演练本文中介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="b0942-116">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NzI7]

## <a name="guest-sharing"></a><span data-ttu-id="b0942-117">来宾共享</span><span class="sxs-lookup"><span data-stu-id="b0942-117">Guest sharing</span></span>

<span data-ttu-id="b0942-118">根据业务性质，你可能希望也可能不希望为包含高度敏感数据的团队启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="b0942-118">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain highly sensitive data.</span></span> <span data-ttu-id="b0942-119">如果确实计划与团队中的组织外部人员进行协作，则建议启用来宾共享。</span><span class="sxs-lookup"><span data-stu-id="b0942-119">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="b0942-120">Microsoft 365 包括许多安全性和合规性功能，可帮助你安全地共享敏感内容。</span><span class="sxs-lookup"><span data-stu-id="b0942-120">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="b0942-121">这通常比直接通过电子邮件向组织外部的人员发送内容更安全。</span><span class="sxs-lookup"><span data-stu-id="b0942-121">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="b0942-122">有关与来宾安全共享的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="b0942-122">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="b0942-123">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="b0942-123">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="b0942-124">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="b0942-124">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="b0942-125">为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。</span><span class="sxs-lookup"><span data-stu-id="b0942-125">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="b0942-126">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="b0942-126">Sensitivity labels</span></span>

<span data-ttu-id="b0942-127">对于高度敏感级别的保护，我们将使用敏感度标签对团队进行分类。</span><span class="sxs-lookup"><span data-stu-id="b0942-127">For the highly sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="b0942-128">此标签还可用于分类和解密此团队或其他团队，或者其他文件位置（如 SharePoint 或 OneDrive）中的单个文件。</span><span class="sxs-lookup"><span data-stu-id="b0942-128">This label can also be used to classify and encrypt individual files in this or other teams or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="b0942-129">首先，必须为 Teams 启用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="b0942-129">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="b0942-130">有关详细信息，请参阅[使用敏感度标签保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="b0942-130">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="b0942-131">如果已在组织中部署了敏感度标签，请考虑此标签与总体标签策略的匹配情况。</span><span class="sxs-lookup"><span data-stu-id="b0942-131">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="b0942-132">可根据需要更改名称或设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="b0942-132">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="b0942-133">为 Teams 启用灵敏度标签后，下一步是创建标签。</span><span class="sxs-lookup"><span data-stu-id="b0942-133">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="b0942-134">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="b0942-134">To create a sensitivity label</span></span>
1. <span data-ttu-id="b0942-135">打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b0942-135">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="b0942-136">在“**解决方案**”下，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-136">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="b0942-137">单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-137">Click **Create a label**.</span></span>
4. <span data-ttu-id="b0942-138">为标签命名。</span><span class="sxs-lookup"><span data-stu-id="b0942-138">Give the label a name.</span></span> <span data-ttu-id="b0942-139">建议使用“**高度敏感**”，但如果该名称已在使用，则可以选择其他名称。</span><span class="sxs-lookup"><span data-stu-id="b0942-139">We suggest **Highly sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="b0942-140">添加显示名称和说明，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-140">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="b0942-141">在“**定义此标签页的搜索范围**”中，选择“**文件和电子邮件**”和“**组和站点**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-141">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="b0942-142">在“**选择文件和电子邮件的保护设置**”页面中，选择“**加密文件和电子邮件**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-142">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="b0942-143">在“**加密页面中**”页面中，选择“**配置加密设置**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-143">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="b0942-144">在“**向特定用户和组分配权限**”下，单击“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-144">Under **Assign permissions to specific users and groups**, click **Assign permissions**.</span></span>
10. <span data-ttu-id="b0942-145">点击“**添加组织中的所有用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-145">Click **Add all users and groups in your organization**.</span></span>
11. <span data-ttu-id="b0942-146">如果某些来宾应具有解密文件的权限，请单击“**添加用户或组**”并添加他们。</span><span class="sxs-lookup"><span data-stu-id="b0942-146">If there are guests who should have permissions to decrypt files, click **Add users or groups** and add them.</span></span>
12.  <span data-ttu-id="b0942-147">单击“**保存**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-147">Click **Save**, and then click **Next**.</span></span>
13. <span data-ttu-id="b0942-148">在“*文件和电子邮件自动标记*”页面中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-148">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
14. <span data-ttu-id="b0942-149">在“**定义组和站点的防护设置**”页面中，选择“**隐私和外部用户访问设置**”和“**设备权限和外部共享设置**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-149">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
15. <span data-ttu-id="b0942-150">在“**定义隐私和外部用户权限设置**”页面中，选择“**隐私**”下的“**私人**”选项。</span><span class="sxs-lookup"><span data-stu-id="b0942-150">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
16. <span data-ttu-id="b0942-151">如果你想允许来宾访问，选择“**外部用户权限**”下的“**让 Microsoft 365 组所有者添加组织外的人员为来宾**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-151">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
17. <span data-ttu-id="b0942-152">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-152">Click **Next**.</span></span>
18. <span data-ttu-id="b0942-153">在“**定义外部共享和设备权限设置**”页面中，选择“**从标记的 SharePoint 站点控制外部共享**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-153">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
19. <span data-ttu-id="b0942-154">如果当前允许来宾访问，在“**无法共享的内容**”下选择“**新的和当前来宾**”；如果不允许，则选择“**仅组织中的人员**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-154">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
20. <span data-ttu-id="b0942-155">在“**未托管的设备的访问**”下，选择“**阻止访问**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-155">Under **Access from unmanaged devices**, choose **Block access**.</span></span> <span data-ttu-id="b0942-156">（如果允许来宾且其没有托管设备，建议选择 **仅允许仅 Web 访问"**。）</span><span class="sxs-lookup"><span data-stu-id="b0942-156">(If you're allowing guests and they don't have managed devices, you may want to choose **Allow limited, web-only access**.)</span></span>
21. <span data-ttu-id="b0942-157">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-157">Click **Next**.</span></span>
22. <span data-ttu-id="b0942-158">在“**数据库列自动标记**”页面中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-158">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
23. <span data-ttu-id="b0942-159">单击“**创建标签**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-159">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="b0942-160">创建标签后，需要将其发布到使用它的用户。</span><span class="sxs-lookup"><span data-stu-id="b0942-160">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="b0942-161">对于敏感保护，我们将对所有用户提供该标签。</span><span class="sxs-lookup"><span data-stu-id="b0942-161">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="b0942-162">在 Microsoft 365 合规中心的“**信息保护**”页面的“**标签策略**”选项卡上发布标签。</span><span class="sxs-lookup"><span data-stu-id="b0942-162">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="b0942-163">如果你拥有适用于所有用户的现有策略，请将此标签添加到该策略。</span><span class="sxs-lookup"><span data-stu-id="b0942-163">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="b0942-164">如果需要创建新策略，请参阅[通过创建标签策略来发布灵敏度标签](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="b0942-164">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="b0942-165">创建团队</span><span class="sxs-lookup"><span data-stu-id="b0942-165">Create a team</span></span>

<span data-ttu-id="b0942-166">对高度敏感方案的进一步配置在与团队相关联的 SharePoint 网站中完成，因此下一步是创建团队。</span><span class="sxs-lookup"><span data-stu-id="b0942-166">Further configuration of the highly sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="b0942-167">创建高度敏感信息团队</span><span class="sxs-lookup"><span data-stu-id="b0942-167">To create a team for highly sensitive information</span></span>
1. <span data-ttu-id="b0942-168">在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-168">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="b0942-169">点击“**创建团队**”（第一张卡片，左上角）。</span><span class="sxs-lookup"><span data-stu-id="b0942-169">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="b0942-170">选择“**从头开始构建团队**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-170">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="b0942-171">在“**敏感度**”列表中，选择刚才创建的“**高敏感**”标签。</span><span class="sxs-lookup"><span data-stu-id="b0942-171">In the **Sensitivity** list, choose the **Highly sensitive** label that you just created.</span></span>
5. <span data-ttu-id="b0942-172">在“**隐私**”下，单击“**专用**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-172">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="b0942-173">为该团队键入一个名称，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-173">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="b0942-174">将用户添加到团队，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-174">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="b0942-175">专用频道设置</span><span class="sxs-lookup"><span data-stu-id="b0942-175">Private channel settings</span></span>

<span data-ttu-id="b0942-176">在此层级，仅限团队所有者创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="b0942-176">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="b0942-177">限制专用频道创建</span><span class="sxs-lookup"><span data-stu-id="b0942-177">To restrict private channel creation</span></span>
1. <span data-ttu-id="b0942-178">在团队中，单击“**更多选项**”，然后单击“**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-178">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="b0942-179">在“**设置**”选项卡上，展开“**成员权限**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-179">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="b0942-180">清除“**允许成员创建专用频道**”复选框。</span><span class="sxs-lookup"><span data-stu-id="b0942-180">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="b0942-181">还可以使用“[团队策略](/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="b0942-181">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="b0942-182">SharePoint 设置</span><span class="sxs-lookup"><span data-stu-id="b0942-182">SharePoint settings</span></span>

<span data-ttu-id="b0942-183">每次使用高度敏感标签创建新团队时，都需要在 SharePoint 中执行两步操作：</span><span class="sxs-lookup"><span data-stu-id="b0942-183">Each time you create a new team with the highly sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="b0942-184">在 SharePoint 管理中心内更新网站的来宾共享设置，以将默认共享链接更新为 *具有现有访问权限的人员*。</span><span class="sxs-lookup"><span data-stu-id="b0942-184">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="b0942-185">自主更新网站中的网站共享设置，防止成员共享文件、文件夹或网站，并关闭访问请求。</span><span class="sxs-lookup"><span data-stu-id="b0942-185">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="b0942-186">网站默认共享链接设置</span><span class="sxs-lookup"><span data-stu-id="b0942-186">Site default sharing link settings</span></span>

<span data-ttu-id="b0942-187">更新网站默认共享链接类型</span><span class="sxs-lookup"><span data-stu-id="b0942-187">To update the site default sharing link type</span></span>

1. <span data-ttu-id="b0942-188">打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="b0942-188">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="b0942-189">在“**网站**”下，单击“**活动的网站**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-189">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="b0942-190">单击与团队关联的网站。</span><span class="sxs-lookup"><span data-stu-id="b0942-190">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="b0942-191">在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-191">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="b0942-192">在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**具有现有访问权限的人员**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-192">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
6. <span data-ttu-id="b0942-193">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-193">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="b0942-194">专用频道</span><span class="sxs-lookup"><span data-stu-id="b0942-194">Private channels</span></span>

<span data-ttu-id="b0942-195">如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="b0942-195">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="b0942-196">这些网站在 SharePoint 管理中心中不可见，因此必须使用 Set-SPOSite PowerShell cmdlet 来更新来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="b0942-196">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="b0942-197">网站共享设置</span><span class="sxs-lookup"><span data-stu-id="b0942-197">Site sharing settings</span></span>

<span data-ttu-id="b0942-198">为了确保不与非团队成员共享 SharePoint 网站，我们将此类共享限制为所有者。</span><span class="sxs-lookup"><span data-stu-id="b0942-198">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="b0942-199">我们还将文件和文件夹的共享限制为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="b0942-199">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="b0942-200">这有助于确保无论何时与团队外部人员共享文件，所有者都会知道。</span><span class="sxs-lookup"><span data-stu-id="b0942-200">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="b0942-201">配置仅限所有者的网站共享</span><span class="sxs-lookup"><span data-stu-id="b0942-201">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="b0942-202">在 Teams 中，导航至要更新团队的“**常规**”标签。</span><span class="sxs-lookup"><span data-stu-id="b0942-202">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="b0942-203">在团队的工具栏中，单击“文件”。</span><span class="sxs-lookup"><span data-stu-id="b0942-203">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="b0942-204">单击省略号，然后单击“在 SharePoint 中打开”。</span><span class="sxs-lookup"><span data-stu-id="b0942-204">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="b0942-205">在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”。</span><span class="sxs-lookup"><span data-stu-id="b0942-205">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="b0942-206">在“**网站权限**”窗格的“**网站共享**”下方，单击“**更改成员共享方式**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-206">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="b0942-207">在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-207">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
7. <span data-ttu-id="b0942-208">将“**允许访问请求**”设置为“**关闭**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b0942-208">Set **Allow access requests** to **Off**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0942-209">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0942-209">See Also</span></span>

[<span data-ttu-id="b0942-210">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="b0942-210">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
