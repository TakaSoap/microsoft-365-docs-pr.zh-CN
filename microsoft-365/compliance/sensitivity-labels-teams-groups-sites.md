---
title: 将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用
f1.keywords:
- NOCSH
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 可将标签应用于 Microsoft Teams、Office 365 组和 SharePoint 网站。
ms.openlocfilehash: 7fd19d9d8f84bd6463d61aec68dbd86c4fc627c0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601559"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="25d2b-103">将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用</span><span class="sxs-lookup"><span data-stu-id="25d2b-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="25d2b-104">在 [Microsoft 365 合规中心](https://protection.office.com/)中创建敏感度标签后，可将其应用于 Microsoft Teams、Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="25d2b-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="25d2b-105">可将策略与标签相关联以控制：</span><span class="sxs-lookup"><span data-stu-id="25d2b-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="25d2b-106">公用/专用设置</span><span class="sxs-lookup"><span data-stu-id="25d2b-106">Public/private settings</span></span>
- <span data-ttu-id="25d2b-107">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="25d2b-107">Guest access</span></span>
- <span data-ttu-id="25d2b-108">非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="25d2b-108">Access from unmanaged devices</span></span>

<span data-ttu-id="25d2b-109">将标签应用于团队或组时，该标签会自动应用于连接的 SharePoint 团队网站，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="25d2b-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="25d2b-110">现在，你还可以为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-110">You can now also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="25d2b-111">有关详细信息，请参阅[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-111">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="25d2b-112">关于 Microsoft Teams、Office 365 组和 SharePoint 网站的公共预览版</span><span class="sxs-lookup"><span data-stu-id="25d2b-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="25d2b-113">Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签将逐步向租户推出，并且在最终发布之前可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="25d2b-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="25d2b-114">此公共预览版不适用于 Office 365 内容交付网络 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="25d2b-115">概述</span><span class="sxs-lookup"><span data-stu-id="25d2b-115">Overview</span></span>

<span data-ttu-id="25d2b-116">发布敏感度标签时，Office 365 中的用户可以访问相同的标签列表。</span><span class="sxs-lookup"><span data-stu-id="25d2b-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="25d2b-117">这些图像显示：</span><span class="sxs-lookup"><span data-stu-id="25d2b-117">These images show:</span></span>

- <span data-ttu-id="25d2b-118">从 SharePoint 中创建新团队网站时列表的显示方式</span><span class="sxs-lookup"><span data-stu-id="25d2b-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="25d2b-119">在 Word 中查看列表时</span><span class="sxs-lookup"><span data-stu-id="25d2b-119">When you view the list in Word</span></span>

<span data-ttu-id="25d2b-120">例如：</span><span class="sxs-lookup"><span data-stu-id="25d2b-120">For example:</span></span>

![从 SharePoint 中创建团队网站时使用的敏感度标签](media/sensitivity-label-new-team-site.png)

![Word 桌面应用程序中显示的敏感度标签](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a><span data-ttu-id="25d2b-123">启用此预览</span><span class="sxs-lookup"><span data-stu-id="25d2b-123">Enable this preview</span></span>

<span data-ttu-id="25d2b-124">必须使用 [Azure Active Directory PowerShell Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)（模块名称 **AzureADPreview**）的预览版才能启用 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签预览：</span><span class="sxs-lookup"><span data-stu-id="25d2b-124">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (module name **AzureADPreview**) to enable this preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

- <span data-ttu-id="25d2b-125">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="25d2b-125">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="25d2b-126">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="25d2b-126">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="25d2b-127">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="25d2b-127">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="25d2b-128">现在，你已启用 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签预览：</span><span class="sxs-lookup"><span data-stu-id="25d2b-128">You're now ready to enable the preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:</span></span>

1. <span data-ttu-id="25d2b-129">在 PowerShell 会话中，使用具有全局管理员权限的工作或学校帐户连接到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="25d2b-129">In a PowerShell session, using a work or school account that has global admin privileges, connect to Azure Active Directory.</span></span> <span data-ttu-id="25d2b-130">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="25d2b-130">For example, run:</span></span>
    
    ```powershell
    Connect-AzureAD
    ````
    
    <span data-ttu-id="25d2b-131">有关完整说明，请参阅[连接到 Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-131">For full instructions, see [Connect to Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).</span></span>

2. <span data-ttu-id="25d2b-132">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="25d2b-132">Run the following commands:</span></span>
    
    ```powershell
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
    
    > [!NOTE]
    > <span data-ttu-id="25d2b-133">启用此预览时，Office 365 不再使用新组和 SharePoint 网站的旧分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-133">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="25d2b-134">如果使用 [Azure AD 网站分类](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"])，则现有组和网站仍将显示旧分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-134">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="25d2b-135">若要显示新分类，请进行转换。</span><span class="sxs-lookup"><span data-stu-id="25d2b-135">To display the new classifications, convert them.</span></span> <span data-ttu-id="25d2b-136">有关如何转换它们的信息，请参阅[如果使用经典 Azure AD 网站分类](#if-you-used-classic-azure-ad-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-136">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

3. <span data-ttu-id="25d2b-137">在同一 PowerShell 会话中，通过使用拥有全局管理员权限的工作或学校帐户，立即连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="25d2b-137">In the same PowerShell session, now connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="25d2b-138">有关说明，请参阅[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-138">For instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

4. <span data-ttu-id="25d2b-139">运行以下命令以将标签同步到 Azure AD，以便它们可与 Office 365 组一起使用：</span><span class="sxs-lookup"><span data-stu-id="25d2b-139">Run the following commands to synchronize your labels to Azure AD, so that they can used with Office 365 groups:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="25d2b-140">创建或编辑敏感度标签时设置网站和组设置</span><span class="sxs-lookup"><span data-stu-id="25d2b-140">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="25d2b-141">启用预览后，请使用以下步骤创建或编辑敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-141">After you enable the preview, use the following steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="25d2b-142">即使已经定义标签，也必须完成这些步骤，这样才能将新的敏感度标签与网站和组配合使用。</span><span class="sxs-lookup"><span data-stu-id="25d2b-142">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="25d2b-143">对这些设置所做的更改最长可能需要 24 小时才能同步。</span><span class="sxs-lookup"><span data-stu-id="25d2b-143">Changes to these settings might take up to 24 hours to synchronize.</span></span>

1. <span data-ttu-id="25d2b-144">在 Microsoft 365 合规中心，选择“**分类**” > “**敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="25d2b-144">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="25d2b-145">选择“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="25d2b-145">Select **Create a label**.</span></span> <span data-ttu-id="25d2b-146">如果你已拥有标签，请跳至下一步。</span><span class="sxs-lookup"><span data-stu-id="25d2b-146">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="25d2b-147">选择所需选项，然后在“**网站和组设置**”选项卡上选择：</span><span class="sxs-lookup"><span data-stu-id="25d2b-147">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>
    
    - <span data-ttu-id="25d2b-148">专用（公用/专用）：专用意味着只有组织中获批的成员可以查看组中的内容。</span><span class="sxs-lookup"><span data-stu-id="25d2b-148">Privacy (Public/Private): Private means that only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="25d2b-149">组织中的任何其他人均无法查看组中的内容。</span><span class="sxs-lookup"><span data-stu-id="25d2b-149">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="25d2b-150">了解更多</span><span class="sxs-lookup"><span data-stu-id="25d2b-150">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="25d2b-151">来宾访问：控制是否可以将来宾添加到组中。</span><span class="sxs-lookup"><span data-stu-id="25d2b-151">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="25d2b-152">了解如何管理 Office 365 组中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="25d2b-152">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="25d2b-153">非托管设备：通过此设置，可阻止或限制未加入混合 AD 或在 Intune 中不兼容的设备访问 SharePoint 内容。</span><span class="sxs-lookup"><span data-stu-id="25d2b-153">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="25d2b-154">如果选择“非托管设备”，则必须转到 Azure AD 以完成策略设置。</span><span class="sxs-lookup"><span data-stu-id="25d2b-154">If you select Unmanaged devices, you must go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="25d2b-155">有关信息，请参阅[控制非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-155">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>
    
    ![网站和组设置选项卡](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="25d2b-157">将标签应用于团队、组或网站时，只有网站和组设置会生效。</span><span class="sxs-lookup"><span data-stu-id="25d2b-157">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="25d2b-158">其他设置（例如加密和内容标记）不适用于团队、组或网站中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="25d2b-158">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="25d2b-159">同样，如果您已创建标签并且未打开网站和组设置，则当用户创建团队、组和网站时，该标签仍可用，但是它将在不应用任何设置的情况下进行分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-159">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it will classify without applying any settings.</span></span>

[<span data-ttu-id="25d2b-160">了解有关发布敏感度标签的详细信息</span><span class="sxs-lookup"><span data-stu-id="25d2b-160">Learn more about publishing sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a><span data-ttu-id="25d2b-161">敏感度标签管理</span><span class="sxs-lookup"><span data-stu-id="25d2b-161">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="25d2b-162">创建、修改和删除用于 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签时，需要与向用户发布标签策略的操作进行仔细协调。</span><span class="sxs-lookup"><span data-stu-id="25d2b-162">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="25d2b-163">使用以下指南，避免可能影响所有用户的网站和组的创建错误。</span><span class="sxs-lookup"><span data-stu-id="25d2b-163">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="25d2b-164">**创建和发布标签：**</span><span class="sxs-lookup"><span data-stu-id="25d2b-164">**Creating and publishing labels:**</span></span>

<span data-ttu-id="25d2b-165">创建并发布敏感度标签后，团队、组和网站中的用户最长可能需要 24 小时才能看到该标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-165">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="25d2b-166">使用以下步骤为租户中的所有用户发布标签：</span><span class="sxs-lookup"><span data-stu-id="25d2b-166">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="25d2b-167">创建敏感度标签，并将其仅发布到租户中的几个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="25d2b-167">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="25d2b-168">等待 24 小时。</span><span class="sxs-lookup"><span data-stu-id="25d2b-168">Wait for 24 hours.</span></span>

3. <span data-ttu-id="25d2b-169">等待 24 小时后，使用在步骤 1 中指定的用户帐户之一，创建具有在步骤 1 中创建的标签的团队、Office 365 组或 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="25d2b-169">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="25d2b-170">如果在步骤 3 的创建操作过程中没有错误，请为租户中的所有用户发布标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-170">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="25d2b-171">如果出现错误，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。</span><span class="sxs-lookup"><span data-stu-id="25d2b-171">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="25d2b-172">**修改和删除已发布的标签：**</span><span class="sxs-lookup"><span data-stu-id="25d2b-172">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="25d2b-173">如果修改或删除一个或多个标签策略中包含的敏感度标签，则这些操作可能会导致所有团队、组和网站的创建失败。</span><span class="sxs-lookup"><span data-stu-id="25d2b-173">If you modify or delete a sensitivity label that is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="25d2b-174">若要避免这种情况，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="25d2b-174">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="25d2b-175">从包含敏感度标签的所有标签策略中删除该标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-175">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="25d2b-176">等待 48 小时。</span><span class="sxs-lookup"><span data-stu-id="25d2b-176">Wait for 48 hours.</span></span>

3. <span data-ttu-id="25d2b-177">等待 48 小时后，尝试创建团队、组或网站，并确认标签不再可见。</span><span class="sxs-lookup"><span data-stu-id="25d2b-177">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="25d2b-178">如果敏感度标签不可见，则现在可以安全地修改或删除该标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-178">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="25d2b-179">如果标签仍可见，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。</span><span class="sxs-lookup"><span data-stu-id="25d2b-179">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="25d2b-180">敏感度标签部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="25d2b-180">Troubleshoot sensitivity label deployment</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="25d2b-181">发布后标签不可见</span><span class="sxs-lookup"><span data-stu-id="25d2b-181">Labels not visible after publishing</span></span>
<span data-ttu-id="25d2b-182">如果在启用这些设置或修改敏感度标签的说明后创建团队或 Office 365 组时遇到问题，请保存标签，等待几小时，然后再次尝试创建团队或组。</span><span class="sxs-lookup"><span data-stu-id="25d2b-182">If you experience issues when you create a team or Office 365 group after you enable these settings or modify a sensitivity label's description, save the label, wait a few hours, and then try to create the team or group again.</span></span> <span data-ttu-id="25d2b-183">有关信息，请参阅[计划在创建或更改敏感度标签后推出](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-183">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="25d2b-184">如果仍无法在 SharePoint Online 中看到新的敏感度标签，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。</span><span class="sxs-lookup"><span data-stu-id="25d2b-184">If you are still not able to see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="25d2b-185">团队、组或 SharePoint 网站创建错误</span><span class="sxs-lookup"><span data-stu-id="25d2b-185">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="25d2b-186">如果在公共预览期间遇到创建错误，则你有两个选择：</span><span class="sxs-lookup"><span data-stu-id="25d2b-186">If you experience creation errors during the public preview, you have two options:</span></span>

- <span data-ttu-id="25d2b-187">确保敏感度标签对任何用户都不是强制性的。</span><span class="sxs-lookup"><span data-stu-id="25d2b-187">Ensure that sensitivity labels are not mandatory for any user.</span></span>

- <span data-ttu-id="25d2b-188">你可以按照此页面“[启用此预览](#enable-this-preview)”部分中的相同说明，为 Microsoft Teams、Office 365 组和 SharePoint 网站关闭敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-188">You can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from the [Enable this preview](#enable-this-preview) section on this page.</span></span> <span data-ttu-id="25d2b-189">但是，若要禁用预览，请搜索行 `$setting["EnableMIPLabels"] = "True"`，并将 **True** 值更改为 **False**。</span><span class="sxs-lookup"><span data-stu-id="25d2b-189">However, to disable the preview, search for the line `$setting["EnableMIPLabels"] = "True"`, and change the **True** value to **False**.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="25d2b-190">为新团队应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="25d2b-190">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="25d2b-191">在 Microsoft Teams 中创建新团队时，用户可以选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-191">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="25d2b-192">当他们选择敏感度级别时，隐私设置会根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="25d2b-192">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="25d2b-193">根据为标签选择的来宾访问设置，用户可以或不能将组织外部人员添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="25d2b-193">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="25d2b-194">了解有关 Teams 的敏感度标签的详细信息</span><span class="sxs-lookup"><span data-stu-id="25d2b-194">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![创建新团队时使用的隐私设置](media/privacy-setting-new-team.png)

<span data-ttu-id="25d2b-196">创建团队后，敏感度标签将显示在所有频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="25d2b-196">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度标签将显示在团队上](media/privacy-setting-teams.png)

<span data-ttu-id="25d2b-198">该服务会自动将相同的敏感度标签应用于 Office 365 组和连接的 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="25d2b-198">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="25d2b-199">为新组应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="25d2b-199">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="25d2b-200">在 Outlook 网页版中，新的“**敏感度**”框包含已发布的标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-200">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="25d2b-201">如果用户需要更多信息，则可以单击帮助图标以阅读有关可用标签和关联策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="25d2b-201">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![创建组并选择“敏感度”下的选项](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="25d2b-203">为新网站应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="25d2b-203">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="25d2b-204">管理员和最终用户可在创建新式团队网站和通信网站时选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-204">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="25d2b-205">了解如何在新的 SharePoint 管理中心中创建网站</span><span class="sxs-lookup"><span data-stu-id="25d2b-205">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="25d2b-206">当用户创建新式团队和通信网站时，默认情况下已选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-206">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="25d2b-207">用户可以选择帮助图标，以了解有关标签的详细信息。</span><span class="sxs-lookup"><span data-stu-id="25d2b-207">Users can select the help icon to learn more about the labels.</span></span>

![创建网站并选择“敏感度”下的选项](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="25d2b-209">当用户浏览网站时，可以查看标签的名称和应用的策略。</span><span class="sxs-lookup"><span data-stu-id="25d2b-209">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![已应用敏感度标签的网站](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="25d2b-211">在 SharePoint 管理中心中管理敏感度标签</span><span class="sxs-lookup"><span data-stu-id="25d2b-211">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="25d2b-212">若要查看和编辑标签，请使用新 SharePoint 管理中心中的“活动网站”页面。</span><span class="sxs-lookup"><span data-stu-id="25d2b-212">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![“活动网站”页面上的“敏感度”列](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="25d2b-214">[了解有关在新 SharePoint 管理中心中管理网站的详细信息](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-214">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="25d2b-215">更改标签的网站和组设置</span><span class="sxs-lookup"><span data-stu-id="25d2b-215">Change site and group settings for a label</span></span>

<span data-ttu-id="25d2b-216">每当您对标签的网站和组设置进行更改时，您必须运行以下 PowerShell 命令，以便团队、网站和组可以使用新设置。</span><span class="sxs-lookup"><span data-stu-id="25d2b-216">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="25d2b-217">最佳做法是，在为多个团队、组或网站应用标签后，不要更改标签的网站和组设置。</span><span class="sxs-lookup"><span data-stu-id="25d2b-217">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="25d2b-218">运行以下命令，连接到 Office 365 安全与合规中心 PowerShell，获取灵敏度标签及其 GUID 的列表。</span><span class="sxs-lookup"><span data-stu-id="25d2b-218">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="25d2b-219">记下该标签或已更改标签的 GUID。</span><span class="sxs-lookup"><span data-stu-id="25d2b-219">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="25d2b-220">立即连接到 Exchange Online PowerShell 并运行 Get-UnifiedGroup cmdlet，指定标签 GUID，替代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的示例 GUID：</span><span class="sxs-lookup"><span data-stu-id="25d2b-220">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="25d2b-221">对于每个组，请重新应用灵敏度标签，指定标签 GUID 来替代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的 GUID 示例：</span><span class="sxs-lookup"><span data-stu-id="25d2b-221">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="25d2b-222">支持新的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="25d2b-222">Support for the new sensitivity labels</span></span>

<span data-ttu-id="25d2b-223">以下应用和服务支持此预览版中的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="25d2b-223">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="25d2b-224">Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="25d2b-224">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="25d2b-225">SharePoint</span><span class="sxs-lookup"><span data-stu-id="25d2b-225">SharePoint</span></span>
- <span data-ttu-id="25d2b-226">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="25d2b-226">Outlook on the web</span></span>
- <span data-ttu-id="25d2b-227">Teams</span><span class="sxs-lookup"><span data-stu-id="25d2b-227">Teams</span></span>
- <span data-ttu-id="25d2b-228">SharePoint 管理中心</span><span class="sxs-lookup"><span data-stu-id="25d2b-228">SharePoint admin center</span></span>
- <span data-ttu-id="25d2b-229">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="25d2b-229">Azure AD admin center</span></span>

<span data-ttu-id="25d2b-230">无法使用以下应用和服务创建具有新敏感度标签的 Office 365 组：</span><span class="sxs-lookup"><span data-stu-id="25d2b-230">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="25d2b-231">Outlook for Mac</span><span class="sxs-lookup"><span data-stu-id="25d2b-231">Outlook for the Mac</span></span>
- <span data-ttu-id="25d2b-232">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="25d2b-232">Outlook mobile</span></span>  
- <span data-ttu-id="25d2b-233">适用于 Windows 的 Outlook 桌面版</span><span class="sxs-lookup"><span data-stu-id="25d2b-233">Outlook desktop for Windows</span></span>
- <span data-ttu-id="25d2b-234">Forms</span><span class="sxs-lookup"><span data-stu-id="25d2b-234">Forms</span></span>  
- <span data-ttu-id="25d2b-235">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="25d2b-235">Dynamics 365</span></span>  
- <span data-ttu-id="25d2b-236">Yammer</span><span class="sxs-lookup"><span data-stu-id="25d2b-236">Yammer</span></span>  
- <span data-ttu-id="25d2b-237">Stream</span><span class="sxs-lookup"><span data-stu-id="25d2b-237">Stream</span></span>  
- <span data-ttu-id="25d2b-238">Planner</span><span class="sxs-lookup"><span data-stu-id="25d2b-238">Planner</span></span>  
- <span data-ttu-id="25d2b-239">Project</span><span class="sxs-lookup"><span data-stu-id="25d2b-239">Project</span></span>  
- <span data-ttu-id="25d2b-240">PowerBI</span><span class="sxs-lookup"><span data-stu-id="25d2b-240">PowerBI</span></span>  
- <span data-ttu-id="25d2b-241">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="25d2b-241">Teams admin center</span></span>  
- <span data-ttu-id="25d2b-242">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="25d2b-242">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="25d2b-243">Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="25d2b-243">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="25d2b-244">如果使用经典 Azure AD 网站分类</span><span class="sxs-lookup"><span data-stu-id="25d2b-244">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="25d2b-245">启用此预览时，Office 365 不再支持新组和 SharePoint 网站的旧分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-245">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="25d2b-246">但是，除非进行转换，否则现有组和网站仍会显示旧分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-246">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="25d2b-247">旧分类包括可能通过 Azure AD PowerShell 或 PnP 核心库设置的“新式”网站分类，这些分类定义了 `ClassificationList` 设置的值。</span><span class="sxs-lookup"><span data-stu-id="25d2b-247">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="25d2b-248">例如，在 PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="25d2b-248">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="25d2b-249">有关旧分类方法的详细信息，请参阅 [SharePoint“新式”网站分类](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-249">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="25d2b-250">根据当前部署，可通过两种方法将旧分类转换为新分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-250">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="25d2b-251">如果从未对文件和电子邮件使用敏感度标签（统一的 Microsoft 信息保护标签）</span><span class="sxs-lookup"><span data-stu-id="25d2b-251">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="25d2b-252">我们建议你：</span><span class="sxs-lookup"><span data-stu-id="25d2b-252">We recommend that you:</span></span>

1. <span data-ttu-id="25d2b-253">在 Microsoft 365 合规中心中创建与现有分类名称相同的新敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-253">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="25d2b-254">使用 PowerShell 通过名称映射将新标签应用于现有的 Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="25d2b-254">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="25d2b-255">删除旧分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-255">Delete the old classifications.</span></span>

<span data-ttu-id="25d2b-256">支持新敏感度标签的应用和服务将显示它们。</span><span class="sxs-lookup"><span data-stu-id="25d2b-256">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="25d2b-257">可以创建具有新标签的新网站、组和网站。</span><span class="sxs-lookup"><span data-stu-id="25d2b-257">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="25d2b-258">用户仍可以通过不支持新标签的应用和服务创建组。</span><span class="sxs-lookup"><span data-stu-id="25d2b-258">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="25d2b-259">但是，用户不能为这些组应用标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-259">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="25d2b-260">使用 PowerShell 为这些组应用新的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-260">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="25d2b-261">你可以保留旧分类；但是，我们强烈建议使用 PowerShell 将新的敏感度标签应用于这些组。</span><span class="sxs-lookup"><span data-stu-id="25d2b-261">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="25d2b-262">支持新敏感度标签的应用和服务将使用新标签进行创建。</span><span class="sxs-lookup"><span data-stu-id="25d2b-262">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="25d2b-263">当用户通过不支持新标签的应用和服务创建组时，他们可以选择分类。</span><span class="sxs-lookup"><span data-stu-id="25d2b-263">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="25d2b-264">如果对文件和电子邮件使用敏感度标签（统一的 Microsoft 信息保护标签）</span><span class="sxs-lookup"><span data-stu-id="25d2b-264">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="25d2b-265">一旦启用此预览，请在 Microsoft 365 合规中心中转到每个标签，并为网站和组应用所需的策略。</span><span class="sxs-lookup"><span data-stu-id="25d2b-265">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="25d2b-266">用户将开始看到对网站和组可用的现有标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-266">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="25d2b-267">在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="25d2b-267">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="25d2b-268">应用新标签之前，请确保你正在运行最新的 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="25d2b-268">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="25d2b-269">如果你已拥有最新版本，则可继续操作并[使用新的敏感度标签重新标记 Office 365 组](#relabel-office-365-groups-with-new-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-269">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="25d2b-270">要准备适用于预览版的 SharePoint Online 命令行管理程序：</span><span class="sxs-lookup"><span data-stu-id="25d2b-270">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="25d2b-271">如果安装的是早期版本的 SharePoint Online 命令行管理程序，请转到“**添加或删除程序**”并卸载“SharePoint Online 命令行管理程序”。</span><span class="sxs-lookup"><span data-stu-id="25d2b-271">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="25d2b-272">在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-272">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="25d2b-273">选择语言，然后单击“**下载**”。</span><span class="sxs-lookup"><span data-stu-id="25d2b-273">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="25d2b-274">在 x64 和 x86.msi 文件之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="25d2b-274">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="25d2b-275">如果运行 64 位版本的 Windows，请下载 x64 文件；如果运行 32 位版本，请下载 x86 文件。</span><span class="sxs-lookup"><span data-stu-id="25d2b-275">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="25d2b-276">如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-276">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="25d2b-277">下载文件后，运行该文件并按照安装向导中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="25d2b-277">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="25d2b-278">使用新的敏感度标签重新标记 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="25d2b-278">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="25d2b-279">确保你使用的是最新版本的 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="25d2b-279">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="25d2b-280">有关说明，请参阅[在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理程序](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-280">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="25d2b-281">使用在 Office 365 中拥有全局管理员或 SharePoint 管理员权限的工作或学校帐户，连接到 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="25d2b-281">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="25d2b-282">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="25d2b-282">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="25d2b-283">运行以下命令以获取敏感度标签及其 GUID 的列表。</span><span class="sxs-lookup"><span data-stu-id="25d2b-283">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="25d2b-284">记下要覆盖的标签的 GUID。</span><span class="sxs-lookup"><span data-stu-id="25d2b-284">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="25d2b-285">例如，“常规”标签。</span><span class="sxs-lookup"><span data-stu-id="25d2b-285">For example, the "General" label.</span></span>

5. <span data-ttu-id="25d2b-286">使用以下命令获取具有“常规”分类的组列表。</span><span class="sxs-lookup"><span data-stu-id="25d2b-286">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="25d2b-287">运行此命令时，将连接到 Exchange Online PowerShell 并运行 Get-UnifiedGroup cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25d2b-287">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="25d2b-288">对于每个组，添加新的敏感度标签 GUID。</span><span class="sxs-lookup"><span data-stu-id="25d2b-288">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
