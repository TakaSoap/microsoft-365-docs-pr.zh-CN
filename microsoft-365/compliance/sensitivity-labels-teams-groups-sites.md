---
title: 将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 您可以将标签应用于 Microsoft 团队、Office 365 组和 SharePoint 网站。
ms.openlocfilehash: ebe5e00c3458782e1874274cb508326968461ce3
ms.sourcegitcommit: 1bd81cf48c7fab1b8aaf7c3f550ce42ab02136dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39822488"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="58d71-103">将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用</span><span class="sxs-lookup"><span data-stu-id="58d71-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="58d71-104">在[microsoft 365 合规性中心](https://protection.office.com/)创建敏感度标签时，现在可以将其应用于 microsoft 团队、Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="58d71-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="58d71-105">您可以将策略与要控制的标签相关联：</span><span class="sxs-lookup"><span data-stu-id="58d71-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="58d71-106">公共/专用设置</span><span class="sxs-lookup"><span data-stu-id="58d71-106">Public/private settings</span></span>
- <span data-ttu-id="58d71-107">来宾访问</span><span class="sxs-lookup"><span data-stu-id="58d71-107">Guest access</span></span>
- <span data-ttu-id="58d71-108">来自非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="58d71-108">Access from unmanaged devices</span></span>

<span data-ttu-id="58d71-109">将标签应用于团队或组时，标签将自动应用于连接的 SharePoint 团队网站和其他方法。</span><span class="sxs-lookup"><span data-stu-id="58d71-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="58d71-110">现在，您还可以在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="58d71-111">[了解详细信息](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="58d71-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="58d71-112">关于 Microsoft 团队、Office 365 组和 SharePoint 网站的公共预览版</span><span class="sxs-lookup"><span data-stu-id="58d71-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="58d71-113">Microsoft 团队、Office 365 组和 SharePoint 网站的敏感度标签将逐步推出到租户，并且在最终发布之前可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="58d71-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="58d71-114">公共预览版不适用于 Office 365 内容传递网络（Cdn）。</span><span class="sxs-lookup"><span data-stu-id="58d71-114">The public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="58d71-115">概述</span><span class="sxs-lookup"><span data-stu-id="58d71-115">Overview</span></span>

<span data-ttu-id="58d71-116">发布敏感度标签时，跨 Office 365 的用户可以访问相同的标签列表。</span><span class="sxs-lookup"><span data-stu-id="58d71-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="58d71-117">这些图像显示：</span><span class="sxs-lookup"><span data-stu-id="58d71-117">These images show:</span></span>

- <span data-ttu-id="58d71-118">从 SharePoint 创建新的团队网站时列表的显示方式</span><span class="sxs-lookup"><span data-stu-id="58d71-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="58d71-119">在 Word 中查看列表时</span><span class="sxs-lookup"><span data-stu-id="58d71-119">When you view the list in Word</span></span>

![从 SharePoint 创建团队网站时的敏感度标签](media/sensitivity-label-new-team-site.png)

![在 Word 桌面应用程序中显示的敏感度标签](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="58d71-122">使用 Azure PowerShell 启用此预览</span><span class="sxs-lookup"><span data-stu-id="58d71-122">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="58d71-123">使用 Azure PowerShell 以全局管理员身份登录 Azure。</span><span class="sxs-lookup"><span data-stu-id="58d71-123">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="58d71-124">有关说明，请参阅[使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="58d71-124">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="58d71-125">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="58d71-125">Run the following command:</span></span>

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

<span data-ttu-id="58d71-126">如果启用此预览，Office 365 将不再使用新组和 SharePoint 网站的旧分类。</span><span class="sxs-lookup"><span data-stu-id="58d71-126">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="58d71-127">如果使用的是[AZURE AD 网站分类](/sharepoint/dev/solution-guidance/modern-experience-site-classification)（$setting ["ClassificationList"]），则现有组和网站仍将显示旧的分类。</span><span class="sxs-lookup"><span data-stu-id="58d71-127">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="58d71-128">若要显示新的分类，请对其进行转换。</span><span class="sxs-lookup"><span data-stu-id="58d71-128">To display the new classifications, convert them.</span></span> <span data-ttu-id="58d71-129">有关如何转换它们的信息，请参阅[如果您使用的是经典 AZURE AD 网站分类](#if-you-used-classic-azure-ad-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="58d71-129">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="58d71-130">创建或编辑敏感度标签时设置网站和组设置</span><span class="sxs-lookup"><span data-stu-id="58d71-130">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="58d71-131">启用预览后，请按照以下步骤创建或编辑敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-131">After you enable the preview, follow these steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="58d71-132">您必须完成这些步骤，才能使用网站和组，即使您已定义标签也是如此。</span><span class="sxs-lookup"><span data-stu-id="58d71-132">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="58d71-133">对这些设置所做的更改可能需要长达24小时的同步。</span><span class="sxs-lookup"><span data-stu-id="58d71-133">Changes to these settings may take up to 24 hours sync.</span></span>

1. <span data-ttu-id="58d71-134">在 Microsoft 365 合规性中心中，选择 "**分类** > **敏感度标签**"。</span><span class="sxs-lookup"><span data-stu-id="58d71-134">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="58d71-135">选择 "**创建标签**"。</span><span class="sxs-lookup"><span data-stu-id="58d71-135">Select **Create a label**.</span></span> <span data-ttu-id="58d71-136">如果您已经有一个标签，请跳至下一步。</span><span class="sxs-lookup"><span data-stu-id="58d71-136">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="58d71-137">选择所需的选项，然后在 "**网站和组设置**" 选项卡上选择：</span><span class="sxs-lookup"><span data-stu-id="58d71-137">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="58d71-138">隐私（公用/专用）：私有表示组织中的已批准成员只能查看组内的内容。</span><span class="sxs-lookup"><span data-stu-id="58d71-138">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="58d71-139">组织中的任何其他人都无法查看组中的内容。</span><span class="sxs-lookup"><span data-stu-id="58d71-139">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="58d71-140">了解更多</span><span class="sxs-lookup"><span data-stu-id="58d71-140">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="58d71-141">来宾访问：您可以控制来宾是否可以添加到组中。</span><span class="sxs-lookup"><span data-stu-id="58d71-141">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="58d71-142">了解如何在 Office 365 组中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="58d71-142">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="58d71-143">非托管设备：此设置允许您阻止或限制从 Intune 中未加入混合广告或合规性的设备访问 SharePoint 内容。</span><span class="sxs-lookup"><span data-stu-id="58d71-143">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="58d71-144">如果选择非托管设备，则需要转到 Azure AD 以完成策略设置。</span><span class="sxs-lookup"><span data-stu-id="58d71-144">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="58d71-145">有关信息，请参阅[控制来自非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="58d71-145">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

!["网站和组设置" 选项卡](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="58d71-147">将标签应用于团队、组或网站时，只有网站和组设置才会生效。</span><span class="sxs-lookup"><span data-stu-id="58d71-147">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="58d71-148">其他设置（如加密和内容标记）不适用于团队、组或网站中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="58d71-148">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="58d71-149">同样，如果您创建一个标签但不启用网站和组设置，则在用户创建团队、组和网站时，该标签仍可用，但在用户应用它时，将不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="58d71-149">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="58d71-150">了解如何发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="58d71-150">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="58d71-151">敏感度标签部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="58d71-151">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="58d71-152">如果在启用365了这些设置或对灵敏度标签的说明进行了更改之后遇到问题，请保存该标签，等待几小时，然后再次尝试创建团队或 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="58d71-152">If you experience issues when you create a Teams or Office 365 group after you enable these settings or make a change to a sensitivity label's description, save the label, wait a few hours, and then try to create the Team or Office 365 group again.</span></span>

<span data-ttu-id="58d71-153">如果您仍无法从 SharePoint Online 中看到新的敏感度标签，请立即与 Microsoft 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="58d71-153">If you are still not able to see the new sensitivity label from SharePoint Online, then contact Microsoft Support immediately.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="58d71-154">将敏感度标签应用于新团队</span><span class="sxs-lookup"><span data-stu-id="58d71-154">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="58d71-155">当用户在 Microsoft 团队中创建新团队时，用户可以选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-155">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="58d71-156">当用户选择敏感度级别时，将根据需要更改隐私设置。</span><span class="sxs-lookup"><span data-stu-id="58d71-156">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="58d71-157">根据为标签选择的来宾访问设置，用户可以或不能将组织外部的人员添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="58d71-157">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![创建新团队时的隐私设置](media/privacy-setting-new-team.png)

<span data-ttu-id="58d71-159">创建团队后，敏感度标签将显示在所有频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="58d71-159">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度标签显示在团队中](media/privacy-setting-teams.png)

<span data-ttu-id="58d71-161">该服务自动将相同的敏感度标签应用于 Office 365 组和连接的 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="58d71-161">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="58d71-162">将敏感度标签应用于新组</span><span class="sxs-lookup"><span data-stu-id="58d71-162">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="58d71-163">在 web 上的 Outlook 中，新的 "**敏感度**" 框中包含已发布标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-163">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="58d71-164">如果用户需要更多的信息，可以单击 "帮助" 图标阅读有关可用标签和相关策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="58d71-164">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![创建组并选择 "敏感度" 下的选项](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="58d71-166">将敏感度标签应用于新网站</span><span class="sxs-lookup"><span data-stu-id="58d71-166">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="58d71-167">管理员和最终用户可以在创建新式工作组网站和通信网站时选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-167">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="58d71-168">了解如何在新的 SharePoint 管理中心中创建网站</span><span class="sxs-lookup"><span data-stu-id="58d71-168">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="58d71-169">当用户创建新式团队和通信网站时，默认情况下已选择一个敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-169">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="58d71-170">用户可以选择 "帮助" 图标以了解有关标签的详细信息。</span><span class="sxs-lookup"><span data-stu-id="58d71-170">Users can select the help icon to learn more about the labels.</span></span>

![创建网站并在 "敏感度" 下选择一个选项](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="58d71-172">当用户浏览到网站时，他们可以看到标签的名称和应用的策略。</span><span class="sxs-lookup"><span data-stu-id="58d71-172">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![应用了灵敏度标签的网站](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="58d71-174">在 SharePoint 管理中心中管理敏感度标签</span><span class="sxs-lookup"><span data-stu-id="58d71-174">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="58d71-175">若要查看和编辑标签，请使用新 SharePoint 管理中心中的 "活动网站" 页。</span><span class="sxs-lookup"><span data-stu-id="58d71-175">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

!["活动网站" 页上的 "敏感度" 列](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="58d71-177">[了解有关在新 SharePoint 管理中心中管理网站的详细信息](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="58d71-177">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="58d71-178">更改标签的网站和组设置</span><span class="sxs-lookup"><span data-stu-id="58d71-178">Change site and group settings for a label</span></span>

<span data-ttu-id="58d71-179">最佳做法是，在将标签应用于多个团队、组或网站后，不要更改设置。</span><span class="sxs-lookup"><span data-stu-id="58d71-179">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="58d71-180">如果必须进行更改，则需要使用 Azure AD PowerShell 脚本手动应用更新。</span><span class="sxs-lookup"><span data-stu-id="58d71-180">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="58d71-181">此方法可确保所有现有团队、网站和组强制实施新设置。</span><span class="sxs-lookup"><span data-stu-id="58d71-181">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="58d71-182">支持新的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="58d71-182">Support for the new sensitivity labels</span></span>

<span data-ttu-id="58d71-183">以下应用和服务支持此预览中的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="58d71-183">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="58d71-184">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="58d71-184">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="58d71-185">SharePoint</span><span class="sxs-lookup"><span data-stu-id="58d71-185">SharePoint</span></span>
- <span data-ttu-id="58d71-186">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="58d71-186">Outlook on the web</span></span>
- <span data-ttu-id="58d71-187">Teams</span><span class="sxs-lookup"><span data-stu-id="58d71-187">Teams</span></span>
- <span data-ttu-id="58d71-188">SharePoint 管理中心</span><span class="sxs-lookup"><span data-stu-id="58d71-188">SharePoint admin center</span></span>
- <span data-ttu-id="58d71-189">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="58d71-189">Azure AD admin center</span></span>

<span data-ttu-id="58d71-190">您不能使用以下应用和服务创建具有新敏感度标签的 Office 365 组：</span><span class="sxs-lookup"><span data-stu-id="58d71-190">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="58d71-191">Outlook for Mac</span><span class="sxs-lookup"><span data-stu-id="58d71-191">Outlook for the Mac</span></span>
- <span data-ttu-id="58d71-192">Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="58d71-192">Outlook mobile</span></span>  
- <span data-ttu-id="58d71-193">适用于 Windows 的 Outlook 桌面</span><span class="sxs-lookup"><span data-stu-id="58d71-193">Outlook desktop for Windows</span></span>
- <span data-ttu-id="58d71-194">Forms</span><span class="sxs-lookup"><span data-stu-id="58d71-194">Forms</span></span>  
- <span data-ttu-id="58d71-195">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="58d71-195">Dynamics 365</span></span>  
- <span data-ttu-id="58d71-196">Yammer</span><span class="sxs-lookup"><span data-stu-id="58d71-196">Yammer</span></span>  
- <span data-ttu-id="58d71-197">Stream</span><span class="sxs-lookup"><span data-stu-id="58d71-197">Stream</span></span>  
- <span data-ttu-id="58d71-198">规划器</span><span class="sxs-lookup"><span data-stu-id="58d71-198">Planner</span></span>  
- <span data-ttu-id="58d71-199">项目</span><span class="sxs-lookup"><span data-stu-id="58d71-199">Project</span></span>  
- <span data-ttu-id="58d71-200">PowerBI</span><span class="sxs-lookup"><span data-stu-id="58d71-200">PowerBI</span></span>  
- <span data-ttu-id="58d71-201">团队管理员中心</span><span class="sxs-lookup"><span data-stu-id="58d71-201">Teams admin center</span></span>  
- <span data-ttu-id="58d71-202">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="58d71-202">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="58d71-203">Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="58d71-203">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="58d71-204">如果你使用的是经典 Azure AD 网站分类</span><span class="sxs-lookup"><span data-stu-id="58d71-204">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="58d71-205">如果启用此预览，Office 365 将不再支持新组和 SharePoint 网站的旧分类。</span><span class="sxs-lookup"><span data-stu-id="58d71-205">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="58d71-206">但是，除非您转换现有的组和网站，否则它们仍会显示旧的分类。</span><span class="sxs-lookup"><span data-stu-id="58d71-206">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="58d71-207">旧分类包括您设置的 "新式" 网站分类，可能通过 Azure AD PowerShell 或 PnP 核心库（定义了`ClassificationList`设置的值）。</span><span class="sxs-lookup"><span data-stu-id="58d71-207">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="58d71-208">例如，在 PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="58d71-208">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="58d71-209">有关旧分类方法的详细信息，请参阅[SharePoint "新式" 网站分类](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="58d71-209">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="58d71-210">根据您的当前部署，您可以通过两种方法将旧分类转换为新的分类。</span><span class="sxs-lookup"><span data-stu-id="58d71-210">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="58d71-211">如果您从未对文件和电子邮件使用敏感度标签（统一 Microsoft 信息保护标签）</span><span class="sxs-lookup"><span data-stu-id="58d71-211">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="58d71-212">我们建议您：</span><span class="sxs-lookup"><span data-stu-id="58d71-212">We recommend that you:</span></span>

1. <span data-ttu-id="58d71-213">在 Microsoft 365 合规性中心创建与现有分类名称相同的新敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-213">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="58d71-214">使用 PowerShell 将新标签应用于现有的 Office 365 组和 SharePoint 网站（使用名称映射）。</span><span class="sxs-lookup"><span data-stu-id="58d71-214">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="58d71-215">删除旧的分类。</span><span class="sxs-lookup"><span data-stu-id="58d71-215">Delete the old classifications.</span></span>

<span data-ttu-id="58d71-216">支持新敏感度标签的应用和服务将显示它们。</span><span class="sxs-lookup"><span data-stu-id="58d71-216">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="58d71-217">您可以使用新标签创建新的团队、组和网站。</span><span class="sxs-lookup"><span data-stu-id="58d71-217">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="58d71-218">用户仍可以从不支持新标签的应用和服务创建组。</span><span class="sxs-lookup"><span data-stu-id="58d71-218">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="58d71-219">但是，用户不能将标签应用于这些组。</span><span class="sxs-lookup"><span data-stu-id="58d71-219">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="58d71-220">使用 PowerShell 将新的敏感度标签应用于这些组。</span><span class="sxs-lookup"><span data-stu-id="58d71-220">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="58d71-221">您可以保留旧的分类;但是，强烈建议使用 PowerShell 将新的敏感度标签应用于这些组。</span><span class="sxs-lookup"><span data-stu-id="58d71-221">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="58d71-222">支持新的敏感度标签的应用和服务将使用新标签创建。</span><span class="sxs-lookup"><span data-stu-id="58d71-222">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="58d71-223">当用户从不支持新标签的应用和服务创建组时，他们可以选择一种分类。</span><span class="sxs-lookup"><span data-stu-id="58d71-223">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="58d71-224">如果对文件和电子邮件使用敏感度标签（统一 Microsoft 信息保护标签）</span><span class="sxs-lookup"><span data-stu-id="58d71-224">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="58d71-225">一旦启用此预览，请立即转到 Microsoft 365 合规中心中的每个标签，并对网站和组应用所需的策略。</span><span class="sxs-lookup"><span data-stu-id="58d71-225">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="58d71-226">用户将开始查看可用于网站和组的现有标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-226">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="58d71-227">在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="58d71-227">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="58d71-228">在应用新标签之前，请确保您运行的是最新的 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="58d71-228">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="58d71-229">如果已有最新版本，可以继续[使用新的灵敏度标签重新标记 Office 365 组](#relabel-office-365-groups-with-new-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="58d71-229">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="58d71-230">为预览准备 SharePoint Online 命令行管理程序：</span><span class="sxs-lookup"><span data-stu-id="58d71-230">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="58d71-231">如果已安装早期版本的 SharePoint Online 命令行管理程序，请转到 "**添加或删除程序**"，并卸载 "SharePoint Online 命令行管理程序"。</span><span class="sxs-lookup"><span data-stu-id="58d71-231">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="58d71-232">在 web 浏览器中，转到 "下载中心" 页面并[下载最新的 SharePoint Online 命令行管理](https://go.microsoft.com/fwlink/p/?LinkId=255251)程序。</span><span class="sxs-lookup"><span data-stu-id="58d71-232">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="58d71-233">选择您的语言，然后单击 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="58d71-233">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="58d71-234">在 x64 和 x86 .msi 文件之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="58d71-234">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="58d71-235">如果运行的是64位版本的 Windows 或 x86 文件（如果运行的是32位版本），请下载 x64 文件。</span><span class="sxs-lookup"><span data-stu-id="58d71-235">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="58d71-236">如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="58d71-236">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="58d71-237">下载文件后，运行文件并按照安装向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="58d71-237">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="58d71-238">使用新的灵敏度标签重新标记 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="58d71-238">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="58d71-239">确保您使用的是最新版本的 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="58d71-239">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="58d71-240">有关说明，请参阅[在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)程序。</span><span class="sxs-lookup"><span data-stu-id="58d71-240">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="58d71-241">在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户，连接到 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="58d71-241">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="58d71-242">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="58d71-242">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="58d71-243">运行以下命令以获取灵敏度标签及其 Guid 的列表。</span><span class="sxs-lookup"><span data-stu-id="58d71-243">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="58d71-244">记下要覆盖的标签的 GUID。</span><span class="sxs-lookup"><span data-stu-id="58d71-244">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="58d71-245">例如，"常规" 标签。</span><span class="sxs-lookup"><span data-stu-id="58d71-245">For example, the "General" label.</span></span>

5. <span data-ttu-id="58d71-246">使用以下命令可获取具有 "常规" 分类的组列表。</span><span class="sxs-lookup"><span data-stu-id="58d71-246">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="58d71-247">运行此命令时，您将连接到 Exchange Online PowerShell 并运行 Remove-unifiedgroup cmdlet。</span><span class="sxs-lookup"><span data-stu-id="58d71-247">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="58d71-248">对于每个组，添加新的敏感度标签 GUID。</span><span class="sxs-lookup"><span data-stu-id="58d71-248">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
