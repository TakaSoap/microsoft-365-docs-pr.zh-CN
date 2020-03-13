---
title: 将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用
f1.keywords:
- NOCSH
ms.author: cabailey
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
description: 使用敏感度标签保护 SharePoint 和 Microsoft Teams 网站以及 Office 365 组中的内容。
ms.openlocfilehash: b1bac1cbe094a1e56c05dd7fd1aa5377f0a85ce5
ms.sourcegitcommit: 62eac95c27295ba285e28cec5acf815314fbfd00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2020
ms.locfileid: "42601349"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="70ab3-103">使用敏感度标签保护 Microsoft Teams 网站、Office 365 组和 SharePoint 网站中的内容（公共预览版）</span><span class="sxs-lookup"><span data-stu-id="70ab3-103">Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="70ab3-104">现在，在 [Microsoft 365 合规中心](https://protection.office.com/)内创建敏感度标签时，可以将它们应用于以下容器：Microsoft Teams 网站、Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="70ab3-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to the following containers: Microsoft Teams sites, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="70ab3-105">使用以下标签设置来帮助保护这些容器中的内容：</span><span class="sxs-lookup"><span data-stu-id="70ab3-105">Use the following label settings to help protect the content in those containers:</span></span>

- <span data-ttu-id="70ab3-106">与 Office 365 组连接的团队网站的隐私（公共或专用）</span><span class="sxs-lookup"><span data-stu-id="70ab3-106">Privacy (public or private) of Office 365 group-connected teams sites</span></span>
- <span data-ttu-id="70ab3-107">外部用户访问</span><span class="sxs-lookup"><span data-stu-id="70ab3-107">External users access</span></span>
- <span data-ttu-id="70ab3-108">非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="70ab3-108">Access from unmanaged devices</span></span> 

<span data-ttu-id="70ab3-109">如果你将此标签应用于受支持的容器，此标签会自动向连接的网站或组应用所配置的选项。</span><span class="sxs-lookup"><span data-stu-id="70ab3-109">When you apply this label to a supported container, the label automatically applies the configured options to the connected site or group.</span></span> 

<span data-ttu-id="70ab3-110">但是，这些容器中的内容不会为设置继承标签，例如标签名称、视觉标记或加密。</span><span class="sxs-lookup"><span data-stu-id="70ab3-110">Content in those containers however, do not inherit the labels for settings such as the label name, visual markings, or encryption.</span></span> <span data-ttu-id="70ab3-111">这样，用户可以标记 SharePoint 网站或团队网站中的文档（请参阅[为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)）。</span><span class="sxs-lookup"><span data-stu-id="70ab3-111">So that users can label their documents in SharePoint sites or team sites, [enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="70ab3-112">关于 Microsoft Teams、Office 365 组和 SharePoint 网站的公共预览版</span><span class="sxs-lookup"><span data-stu-id="70ab3-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="70ab3-113">适用于 Microsoft Teams 网站、Office 365 组和 SharePoint 网站的敏感度标签正在逐步向租户推出，在最终发布之前可能会有所改变。</span><span class="sxs-lookup"><span data-stu-id="70ab3-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites are in gradual rollout to tenants and might change before final release.</span></span> <span data-ttu-id="70ab3-114">此公共预览版不适用于 Office 365 内容交付网络 (CDN)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-114">This public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

<span data-ttu-id="70ab3-115">在你为新设置启用此预览版和配置敏感度标签之前，用户可在其应用中查看和应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-115">Before you enable this preview and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="70ab3-116">例如，在 Word 中：</span><span class="sxs-lookup"><span data-stu-id="70ab3-116">For example, from Word:</span></span>

![Word 桌面应用中显示的敏感度标签](../media/sensitivity-label-word.png)

<span data-ttu-id="70ab3-118">启用并配置此预览版后，用户还可查看敏感度标签并将其应用于 Microsoft Teams、Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="70ab3-118">After you enable and configure this preview, users can additionally see and apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="70ab3-119">例如，在从 SharePoint 创建新的团队网站时：</span><span class="sxs-lookup"><span data-stu-id="70ab3-119">For example, when you create a new team site from SharePoint:</span></span>

![从 SharePoint 中创建团队网站时使用的敏感度标签](../media/sensitivity-labels-new-team-site.png)

## <a name="enable-this-preview-and-synchronize-labels"></a><span data-ttu-id="70ab3-121">启用此预览版并同步标签</span><span class="sxs-lookup"><span data-stu-id="70ab3-121">Enable this preview and synchronize labels</span></span>

1. <span data-ttu-id="70ab3-122">由于此功能使用 Azure AD 功能，因此请按照以下 Azure AD 文档中的说明来启用预览版：[在 Azure Active Directory 中向 Office 365 组分配敏感度标签（预览）](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-122">Because this feature uses Azure AD functionality, follow the instructions in the Azure AD documentation to enable the preview: [Assign sensitivity labels to Office 365 groups in Azure Active Directory (preview)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="70ab3-123">在 PowerShell 会话中，通过使用拥有全局管理员权限的工作或学校帐户，立即连接到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="70ab3-123">In a PowerShell session, connect to the Security & Compliance Center by using a work or school account that has global admin privileges.</span></span> <span data-ttu-id="70ab3-124">例如：</span><span class="sxs-lookup"><span data-stu-id="70ab3-124">For example:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```
    
    <span data-ttu-id="70ab3-125">有关完整说明，请参阅[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-125">For full instructions, see [Connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="70ab3-126">运行以下命令将敏感度标签同步到 Azure AD，使其可与 Office 365 组一起使用：</span><span class="sxs-lookup"><span data-stu-id="70ab3-126">Run the following command to synchronize your sensitivity labels to Azure AD, so that they can be used with Office 365 groups:</span></span>
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="70ab3-127">如何创建或编辑敏感度标签时设置网站和组设置</span><span class="sxs-lookup"><span data-stu-id="70ab3-127">How to configure site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="70ab3-128">你现已可创建或编辑要提供给网站和组使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="70ab3-129">启用预览版后，敏感度标签向导中会显示一个新页面，即“**网站和组设置**”</span><span class="sxs-lookup"><span data-stu-id="70ab3-129">Enabling the preview makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="70ab3-130">如果在创建或编辑敏感度标签方面需要帮助，请查看[创建和配置敏感度标签](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)中的说明。</span><span class="sxs-lookup"><span data-stu-id="70ab3-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="70ab3-131">在这个新的“**网站和组设置**”页面中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="70ab3-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="70ab3-132">**与 Office 365 组连接的团队网站的隐私**：默认设置“无 - 让用户选择谁可以访问网站”\*\*\*\* 目前正在逐步向租户推出。</span><span class="sxs-lookup"><span data-stu-id="70ab3-132">**Privacy of Office 365 group-connected teams sites**: The default setting of **None - let user chose who can access the site** is currently rolling out to tenants.</span></span> <span data-ttu-id="70ab3-133">如果需要使用敏感度标签保护容器中的内容，但仍允许用户自行配置隐私设置，请保留此默认设置。</span><span class="sxs-lookup"><span data-stu-id="70ab3-133">Keep this default setting when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
    
    <span data-ttu-id="70ab3-134">选择“公共”\*\*\*\* 或“私有”\*\*\*\* 可以设置和锁定将此标签应用于容器时的隐私设置。</span><span class="sxs-lookup"><span data-stu-id="70ab3-134">Select **Public** or**Private** to set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="70ab3-135">如果希望组织中的任何人都可以访问应用了此标签的团队网站或组，请选择“公共”\*\*\*\*；如果希望仅限组织中已批准的成员访问，请选择“私有”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="70ab3-135">Choose **Public** if you want anyone in your organization to access the team site or group where this label is applied, or **Private** if you want access to be restricted to only approved members in your organization.</span></span> 
    
    <span data-ttu-id="70ab3-136">“公共”\*\*\*\* 或“私有”\*\*\*\* 设置替换之前可能已为团队或组配置的任何隐私设置，并锁定隐私值，因此只有先从容器中删除敏感度标签才能更改它。</span><span class="sxs-lookup"><span data-stu-id="70ab3-136">The **Public** or **Private** setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="70ab3-137">在你删除敏感度标签后，标签中的隐私设置仍保留，用户现在可以再次更改它。</span><span class="sxs-lookup"><span data-stu-id="70ab3-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="70ab3-138">**外部用户访问**：控制组所有者是否可[向组添加来宾](/office365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="70ab3-139">**未托管的设备**：对于[未托管的设备](/sharepoint/control-access-from-unmanaged-devices)，允许完全访问、仅限 Web 的访问或完全阻止访问。</span><span class="sxs-lookup"><span data-stu-id="70ab3-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> 

![网站和组设置选项卡](../media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="70ab3-141">将标签应用于团队、组或网站时，只有这些网站和组设置会生效。</span><span class="sxs-lookup"><span data-stu-id="70ab3-141">Only these site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="70ab3-142">其他标签设置（例如加密和内容标记）不适用于团队、组或网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="70ab3-142">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
> 
> <span data-ttu-id="70ab3-143">正在逐步向租户推出：当用户创建团队、组和网站时，只有带有网站和组设置的标签才可供选择。</span><span class="sxs-lookup"><span data-stu-id="70ab3-143">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="70ab3-144">如果当前可以向容器应用未启用网站和组设置的标签，只有标签名称会应用于容器。</span><span class="sxs-lookup"><span data-stu-id="70ab3-144">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="70ab3-145">如果尚未发布敏感度标签，现可通过[将其添加到敏感度标签策略](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)进行发布。</span><span class="sxs-lookup"><span data-stu-id="70ab3-145">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="70ab3-146">分配有含有此标签的敏感度标签策略的用户，将能够为网站和组选择。</span><span class="sxs-lookup"><span data-stu-id="70ab3-146">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="70ab3-147">根据标签策略，在向容器应用此标签时，只有策略设置“默认将此标签应用于文档和电子邮件”\*\*\*\* 适用。</span><span class="sxs-lookup"><span data-stu-id="70ab3-147">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="70ab3-148">其他策略设置都不会应用，包括强制标记、需要用户理由和自定义帮助页面链接。</span><span class="sxs-lookup"><span data-stu-id="70ab3-148">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="70ab3-149">敏感度标签管理</span><span class="sxs-lookup"><span data-stu-id="70ab3-149">Sensitivity label management</span></span>

> [!WARNING]
> <span data-ttu-id="70ab3-150">创建、修改和删除用于 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签时，需要与向用户发布标签策略的操作进行仔细协调。</span><span class="sxs-lookup"><span data-stu-id="70ab3-150">Creating, modifying, and deleting sensitivity labels that you use for Microsoft Teams, Office 365 groups, and SharePoint sites requires careful coordination with publishing label policies to users.</span></span> 

<span data-ttu-id="70ab3-151">使用以下指南，避免可能影响所有用户的网站和组的创建错误。</span><span class="sxs-lookup"><span data-stu-id="70ab3-151">Avoid creation errors for sites and groups that can affect all users by using the following guidance.</span></span>

<span data-ttu-id="70ab3-152">**创建和发布标签：**</span><span class="sxs-lookup"><span data-stu-id="70ab3-152">**Creating and publishing labels:**</span></span>

<span data-ttu-id="70ab3-153">创建并发布敏感度标签后，团队、组和网站中的用户最长可能需要 24 小时才能看到该标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-153">After a sensitivity label is created and published, it can take up to 24 hours for the label to become visible for users in teams, groups, and sites.</span></span> <span data-ttu-id="70ab3-154">使用以下步骤为租户中的所有用户发布标签：</span><span class="sxs-lookup"><span data-stu-id="70ab3-154">Use the following steps to publish a label for all users in the tenant:</span></span>

1. <span data-ttu-id="70ab3-155">创建敏感度标签，并将其仅发布到租户中的几个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="70ab3-155">Create the sensitivity label and publish it for just a few user accounts in the tenant.</span></span>

2. <span data-ttu-id="70ab3-156">等待 24 小时。</span><span class="sxs-lookup"><span data-stu-id="70ab3-156">Wait for 24 hours.</span></span>

3. <span data-ttu-id="70ab3-157">等待 24 小时后，使用在步骤 1 中指定的用户帐户之一，创建具有在步骤 1 中创建的标签的团队、Office 365 组或 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="70ab3-157">After this 24 hours wait, use one of the user accounts you specified in step 1 to create a team, Office 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="70ab3-158">如果在步骤 3 的创建操作过程中没有错误，请为租户中的所有用户发布标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-158">If there are no errors during the creation operation for step 3, publish the label for all users in your tenant.</span></span> <span data-ttu-id="70ab3-159">如果出现错误，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。</span><span class="sxs-lookup"><span data-stu-id="70ab3-159">If there are errors, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

<span data-ttu-id="70ab3-160">**修改和删除已发布的标签：**</span><span class="sxs-lookup"><span data-stu-id="70ab3-160">**Modifying and deleting published labels:**</span></span>

<span data-ttu-id="70ab3-161">如果修改或删除的敏感度标签已启用网站和组设置，且包含在一个或多个标签策略中，这些操作可能会导致所有团队、组和网站的创建失败。</span><span class="sxs-lookup"><span data-stu-id="70ab3-161">If you modify or delete a sensitivity label with the site and group settings enabled, and that label is included in one or more label policies, these actions can result in creation failures for all teams, groups, and sites.</span></span> <span data-ttu-id="70ab3-162">若要避免这种情况，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="70ab3-162">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="70ab3-163">从包含敏感度标签的所有标签策略中删除该标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-163">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="70ab3-164">等待 48 小时。</span><span class="sxs-lookup"><span data-stu-id="70ab3-164">Wait for 48 hours.</span></span>

3. <span data-ttu-id="70ab3-165">等待 48 小时后，尝试创建团队、组或网站，并确认标签不再可见。</span><span class="sxs-lookup"><span data-stu-id="70ab3-165">After the 48 hours wait, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="70ab3-166">如果敏感度标签不可见，则现在可以安全地修改或删除该标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-166">If the sensitivity label isn't visible, you can now safely modify or delete the label.</span></span> <span data-ttu-id="70ab3-167">如果标签仍可见，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。</span><span class="sxs-lookup"><span data-stu-id="70ab3-167">If the label is still visible, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="assign-sensitivity-labels-to-office-365-groups"></a><span data-ttu-id="70ab3-168">分配敏感度标签至 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="70ab3-168">Assign sensitivity labels to Office 365 groups</span></span>

<span data-ttu-id="70ab3-169">你现可将一个或多个敏感度标签应用于 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="70ab3-169">You're now ready to apply the sensitivity label or labels to Office 365 groups.</span></span> <span data-ttu-id="70ab3-170">请返回到 Azure AD 文档查看说明：</span><span class="sxs-lookup"><span data-stu-id="70ab3-170">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="70ab3-171">在 Azure 门户中为新组分配标签</span><span class="sxs-lookup"><span data-stu-id="70ab3-171">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [<span data-ttu-id="70ab3-172">为 Azure 门户中的现有组分配标签</span><span class="sxs-lookup"><span data-stu-id="70ab3-172">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  <span data-ttu-id="70ab3-173">[从 Azure 门户中的现有组中删除标签](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-173">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="70ab3-174">为新团队应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="70ab3-174">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="70ab3-175">在 Microsoft Teams 中创建新团队时，用户可以选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-175">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="70ab3-176">如果用户从“敏感度”\*\*\*\* 下拉列表中选择标签，隐私设置可能会更改，以反映标签配置。</span><span class="sxs-lookup"><span data-stu-id="70ab3-176">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="70ab3-177">根据为标签选择的外部用户访问设置，用户可以或不能将组织外部人员添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="70ab3-177">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="70ab3-178">了解有关 Teams 的敏感度标签的详细信息</span><span class="sxs-lookup"><span data-stu-id="70ab3-178">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![创建新团队时使用的隐私设置](../media/privacy-setting-new-team.png)

<span data-ttu-id="70ab3-180">创建团队后，敏感度标签将显示在所有频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="70ab3-180">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度标签将显示在团队上](../media/privacy-setting-teams.png)

<span data-ttu-id="70ab3-182">该服务会自动将相同的敏感度标签应用于 Office 365 组和连接的 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="70ab3-182">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="70ab3-183">应用敏感度标签至 Outlook 网页版的新组</span><span class="sxs-lookup"><span data-stu-id="70ab3-183">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="70ab3-184">在 Outlook 网页版中，创建新组时可选择或更改已发布的标签的“**敏感度**”选项：</span><span class="sxs-lookup"><span data-stu-id="70ab3-184">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![创建组并选择“敏感度”下的选项](../media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="70ab3-186">为新网站应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="70ab3-186">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="70ab3-187">管理员和最终用户可以在[创建新式团队网站和通信网站时](/sharepoint/create-site-collection)选择敏感度标签，并展开“高级设置”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="70ab3-187">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![创建网站并在“敏感度”下选择一个选项](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="70ab3-189">下拉列表框显示选择的标签名称，帮助图标显示所有标签名称及其工具提示，这可帮助用户确定要应用的正确标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-189">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="70ab3-190">在标签应用后，当用户浏览网站时，可以看到标签名称和所应用的策略。</span><span class="sxs-lookup"><span data-stu-id="70ab3-190">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="70ab3-191">例如，此网站标记为“机密”\*\*\*\*，且隐私设置设为“私有”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="70ab3-191">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![已应用敏感度标签的网站](../media/sensitivity-label-site.png)

## <a name="view-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="70ab3-193">在 SharePoint 管理中心中查看敏感度标签</span><span class="sxs-lookup"><span data-stu-id="70ab3-193">View sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="70ab3-194">若要查看应用的敏感度标签，请使用新 SharePoint 管理中心中的“**活动网站**”页面。</span><span class="sxs-lookup"><span data-stu-id="70ab3-194">To view the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="70ab3-195">可能需要先添加“**敏感度**”列：</span><span class="sxs-lookup"><span data-stu-id="70ab3-195">You might need to first add the **Sensitivity** column:</span></span>

![“活动网站”页面上的“敏感度”列](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="70ab3-197">[了解有关在新 SharePoint 管理中心中管理网站的详细信息](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-197">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="70ab3-198">更改标签的网站和组设置</span><span class="sxs-lookup"><span data-stu-id="70ab3-198">Change site and group settings for a label</span></span>

<span data-ttu-id="70ab3-199">每当您对标签的网站和组设置进行更改时，您必须运行以下 PowerShell 命令，以便团队、网站和组可以使用新设置。</span><span class="sxs-lookup"><span data-stu-id="70ab3-199">Whenever you make a change to site and group settings for a label, you must run the following PowerShell commands so that your teams, sites, and groups can use the new settings.</span></span> <span data-ttu-id="70ab3-200">最佳做法是，在为多个团队、组或网站应用标签后，不要更改标签的网站和组设置。</span><span class="sxs-lookup"><span data-stu-id="70ab3-200">As a best practice, don't the change site and group settings for a label after you've applied the label to several teams, groups, or sites.</span></span>

1. <span data-ttu-id="70ab3-201">运行以下命令，连接到 Office 365 安全与合规中心 PowerShell，获取灵敏度标签及其 GUID 的列表。</span><span class="sxs-lookup"><span data-stu-id="70ab3-201">Run the following commands to connect to Office 365 Security & Compliance Center PowerShell and get the list of sensitivity labels and their GUIDs.</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. <span data-ttu-id="70ab3-202">记下该标签或已更改标签的 GUID。</span><span class="sxs-lookup"><span data-stu-id="70ab3-202">Make a note of the GUID for the label or labels you have changed.</span></span>

3. <span data-ttu-id="70ab3-203">立即连接到 Exchange Online PowerShell 并运行 Get-UnifiedGroup cmdlet，指定标签 GUID，替代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的示例 GUID：</span><span class="sxs-lookup"><span data-stu-id="70ab3-203">Now connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span> 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. <span data-ttu-id="70ab3-204">对于每个组，请重新应用灵敏度标签，指定标签 GUID 来替代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的 GUID 示例：</span><span class="sxs-lookup"><span data-stu-id="70ab3-204">For each group, reapply the sensitivity label, specifying your label GUID in place of the example GUID of "e48058ea-98e8-4940-8db0-ba1310fd955e":</span></span>
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-sensitivity-labels"></a><span data-ttu-id="70ab3-205">敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="70ab3-205">Support for the sensitivity labels</span></span>

<span data-ttu-id="70ab3-206">可将为网站和组设置配置的敏感度标签用于以下应用和服务：</span><span class="sxs-lookup"><span data-stu-id="70ab3-206">You can use the sensitivity labels that you've configured for site and group settings with the following apps and services:</span></span>

- <span data-ttu-id="70ab3-207">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="70ab3-207">SharePoint Online</span></span>
- <span data-ttu-id="70ab3-208">Teams</span><span class="sxs-lookup"><span data-stu-id="70ab3-208">Teams</span></span>
- <span data-ttu-id="70ab3-209">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="70ab3-209">Outlook on the web</span></span>
- <span data-ttu-id="70ab3-210">SharePoint 管理中心</span><span class="sxs-lookup"><span data-stu-id="70ab3-210">SharePoint admin center</span></span>
- <span data-ttu-id="70ab3-211">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="70ab3-211">Azure AD admin center</span></span>

<span data-ttu-id="70ab3-212">其他当前不可使用你为网站和组设置配置的敏感度标签的应用和服务包括：</span><span class="sxs-lookup"><span data-stu-id="70ab3-212">Other apps and services that you can't currently use the sensitivity labels that you've configured for site and group settings include:</span></span>

- <span data-ttu-id="70ab3-213">Outlook for Mac</span><span class="sxs-lookup"><span data-stu-id="70ab3-213">Outlook for the Mac</span></span>
- <span data-ttu-id="70ab3-214">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="70ab3-214">Outlook mobile</span></span>
- <span data-ttu-id="70ab3-215">适用于 Windows 的 Outlook 桌面版</span><span class="sxs-lookup"><span data-stu-id="70ab3-215">Outlook desktop for Windows</span></span>
- <span data-ttu-id="70ab3-216">Forms</span><span class="sxs-lookup"><span data-stu-id="70ab3-216">Forms</span></span>
- <span data-ttu-id="70ab3-217">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="70ab3-217">Dynamics 365</span></span>
- <span data-ttu-id="70ab3-218">Yammer</span><span class="sxs-lookup"><span data-stu-id="70ab3-218">Yammer</span></span>
- <span data-ttu-id="70ab3-219">Stream</span><span class="sxs-lookup"><span data-stu-id="70ab3-219">Stream</span></span>
- <span data-ttu-id="70ab3-220">Planner</span><span class="sxs-lookup"><span data-stu-id="70ab3-220">Planner</span></span>
- <span data-ttu-id="70ab3-221">Project</span><span class="sxs-lookup"><span data-stu-id="70ab3-221">Project</span></span>
- <span data-ttu-id="70ab3-222">PowerBI</span><span class="sxs-lookup"><span data-stu-id="70ab3-222">PowerBI</span></span>
- <span data-ttu-id="70ab3-223">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="70ab3-223">Teams admin center</span></span>
- <span data-ttu-id="70ab3-224">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="70ab3-224">Microsoft 365 admin center</span></span>
- <span data-ttu-id="70ab3-225">Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="70ab3-225">Exchange admin center</span></span>


## <a name="classic-azure-ad-site-classification"></a><span data-ttu-id="70ab3-226">经典 Azure AD 网站分类</span><span class="sxs-lookup"><span data-stu-id="70ab3-226">Classic Azure AD site classification</span></span>

<span data-ttu-id="70ab3-227">启用此预览时，Office 365 不再支持新组和 SharePoint 网站的旧分类。</span><span class="sxs-lookup"><span data-stu-id="70ab3-227">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="70ab3-228">但是，除进行转换以使用敏感度标签外，否则现有组和网站仍会显示旧分类。</span><span class="sxs-lookup"><span data-stu-id="70ab3-228">However, existing groups and sites still display the old classifications unless you convert them to use sensitivity labels.</span></span> <span data-ttu-id="70ab3-229">旧分类包括可能通过 Azure AD PowerShell 或 PnP 核心库设置的“新式”网站分类，这些分类定义了 `ClassificationList` 设置的值。</span><span class="sxs-lookup"><span data-stu-id="70ab3-229">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="70ab3-230">例如，在 PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="70ab3-230">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="70ab3-231">有关旧分类方法的详细信息，请参阅 [SharePoint“新式”网站分类](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-231">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="70ab3-232">若要将旧分类转换为敏感度标签，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="70ab3-232">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="70ab3-233">使用现有标签：通过编辑已发布的现有敏感度标签，指定你希望网站和组使用的标签设置。</span><span class="sxs-lookup"><span data-stu-id="70ab3-233">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="70ab3-234">创建新标签：通过创建和发布与你的现有分类名称相同的新的敏感度标签，指定你希望网站和组使用的标签设置。</span><span class="sxs-lookup"><span data-stu-id="70ab3-234">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="70ab3-235">则：</span><span class="sxs-lookup"><span data-stu-id="70ab3-235">Then:</span></span> 

1. <span data-ttu-id="70ab3-236">使用 PowerShell 将敏感度标签应用至使用名称映射的现有 Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="70ab3-236">Use PowerShell to apply the sensitivity labels to existing Office 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="70ab3-237">相关说明，请参见下一节。</span><span class="sxs-lookup"><span data-stu-id="70ab3-237">See the next section for instructions.</span></span>

2. <span data-ttu-id="70ab3-238">删除现有组和网站中的旧分类。</span><span class="sxs-lookup"><span data-stu-id="70ab3-238">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="70ab3-239">虽然无法阻止用户在尚不支持敏感度标签的应用和服务中创建新组，但可运行定期 PowerShell 标签来查看用户已使用旧分类创建的新组，并转换这些分类以使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-239">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span> 

#### <a name="use-powershell-to-convert-classifications-for-office-365-groups-to-sensitivity-labels"></a><span data-ttu-id="70ab3-240">使用 PowerShell 将 Office 365 组的分类转换为敏感度标签</span><span class="sxs-lookup"><span data-stu-id="70ab3-240">Use PowerShell to convert classifications for Office 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="70ab3-241">确保你正在运行 SharePoint Online 命令行管理程序版本 16.0.19418.12000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="70ab3-241">Ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="70ab3-242">如果已有最新版本，跳至第 4 步。</span><span class="sxs-lookup"><span data-stu-id="70ab3-242">If you already have the latest version, skip to step 4.</span></span>

2. <span data-ttu-id="70ab3-243">如果已从 PowerShell 库安装早期版本的 SharePoint Online 命令行管理程序，可通过运行以下 cmdlet 来更新模块。</span><span class="sxs-lookup"><span data-stu-id="70ab3-243">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>
    
    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

3. <span data-ttu-id="70ab3-244">如果从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，请转到“**添加或删除程序**”并卸载 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="70ab3-244">If you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span> <span data-ttu-id="70ab3-245">然后，从“[下载中心](https://go.microsoft.com/fwlink/p/?LinkId=255251)”安装最新版本的 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="70ab3-245">Then, install the latest SharePoint Online Management Shell from the [Download Center](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="70ab3-246">使用在 Office 365 中拥有全局管理员或 SharePoint 管理员权限的工作或学校帐户，连接到 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="70ab3-246">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="70ab3-247">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-247">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

5. <span data-ttu-id="70ab3-248">运行以下命令以获取敏感度标签及其 GUID 的列表。</span><span class="sxs-lookup"><span data-stu-id="70ab3-248">Run the following commands to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

6. <span data-ttu-id="70ab3-249">记下你想要应用到 Office 365 组的敏感度标签的 Guid。</span><span class="sxs-lookup"><span data-stu-id="70ab3-249">Make a note of the GUIDs for the sensitivity labels you want to apply to your Office 365 groups.</span></span>

7. <span data-ttu-id="70ab3-250">以下列命令为例，获取当前具有“常规”分类的组列表：</span><span class="sxs-lookup"><span data-stu-id="70ab3-250">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="70ab3-251">对于每个组，添加新的敏感度标签 GUID。</span><span class="sxs-lookup"><span data-stu-id="70ab3-251">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="70ab3-252">例如：</span><span class="sxs-lookup"><span data-stu-id="70ab3-252">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="70ab3-253">审核敏感度标签活动</span><span class="sxs-lookup"><span data-stu-id="70ab3-253">Auditing sensitivity label activities</span></span>

<span data-ttu-id="70ab3-254">如果有人将文档上传到受敏感度标签保护的网站上，该文档的敏感度标签的[优先级](sensitivity-labels.md#label-priority-order-matters)比该网站应用的敏感度标签高，且不会阻止此操作。</span><span class="sxs-lookup"><span data-stu-id="70ab3-254">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="70ab3-255">例如，你向 SharePoint 网站应用了“**常规**”标签，并且有人向此网站上传了一个标记为“**机密**”的文档。</span><span class="sxs-lookup"><span data-stu-id="70ab3-255">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="70ab3-256">对于优先级更低的内容来说，具有更高优先级的敏感度标签会识别敏感度高于此内容的内容，因此该情况可能会带来安全隐患。</span><span class="sxs-lookup"><span data-stu-id="70ab3-256">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="70ab3-257">虽然此操作未被阻止，但它会经过审核，因此你可识别存在这种标签优先级不一致情况的文档，并在必要时采取措施。</span><span class="sxs-lookup"><span data-stu-id="70ab3-257">Although the action isn't blocked, it is audited, so you can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="70ab3-258">例如，从网站中删除或移动已上传的文档。</span><span class="sxs-lookup"><span data-stu-id="70ab3-258">For example, delete or move the uploaded document from the site.</span></span> 

<span data-ttu-id="70ab3-259">如果文档的敏感度标签的优先级低于网站应用的敏感度标签，则不会出现安全问题。</span><span class="sxs-lookup"><span data-stu-id="70ab3-259">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="70ab3-260">例如，标有“**常规**”的文档上传到标有“**机密**”的网站上。</span><span class="sxs-lookup"><span data-stu-id="70ab3-260">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="70ab3-261">在这种情况中，不生成审核事件。</span><span class="sxs-lookup"><span data-stu-id="70ab3-261">In this scenario, an auditing event isn't generated.</span></span>

<span data-ttu-id="70ab3-262">要搜索此事件的审核日志，请从“**文件和页面活动**”类别中查找“**检测到文档敏感度不匹配**”。</span><span class="sxs-lookup"><span data-stu-id="70ab3-262">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span> 

<span data-ttu-id="70ab3-263">当有人向网站或组添加敏感度标签或从中删除敏感度标签时，也会审核这些活动。</span><span class="sxs-lookup"><span data-stu-id="70ab3-263">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited.</span></span> <span data-ttu-id="70ab3-264">可在“[敏感度标签活动](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)”类别中找到这些事件。</span><span class="sxs-lookup"><span data-stu-id="70ab3-264">These events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> 

<span data-ttu-id="70ab3-265">有关搜索审核日志的说明，请参阅[在安全与合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-265">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="70ab3-266">敏感度标签部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="70ab3-266">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="70ab3-267">对 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签有疑问？</span><span class="sxs-lookup"><span data-stu-id="70ab3-267">Having problems with sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites?</span></span> <span data-ttu-id="70ab3-268">检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="70ab3-268">Check the following:</span></span>

### <a name="labels-not-visible-after-publishing"></a><span data-ttu-id="70ab3-269">发布后标签不可见</span><span class="sxs-lookup"><span data-stu-id="70ab3-269">Labels not visible after publishing</span></span>
<span data-ttu-id="70ab3-270">如果在启用这些设置或修改敏感度标签的名称或工具提示后无法创建网站或 Office 365 组，请在保存标签后等待几小时，然后再次尝试创建团队或组。</span><span class="sxs-lookup"><span data-stu-id="70ab3-270">If you experience issues when you create a site or Office 365 group after you enable these settings or modify a sensitivity label's name or tooltip, wait a few hours after saving the label changes, and then try to create the team or group again.</span></span> <span data-ttu-id="70ab3-271">有关信息，请参阅[计划在创建或更改敏感度标签后推出](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-271">For information, see [Schedule roll-out after you create or change a sensitivity label](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).</span></span>

<span data-ttu-id="70ab3-272">如果仍无法在 SharePoint Online 中看到新的敏感度标签，请联系 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-272">If you still can't see the new sensitivity label from SharePoint Online, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

### <a name="team-group-or-sharepoint-site-creation-errors"></a><span data-ttu-id="70ab3-273">团队、组或 SharePoint 网站创建错误</span><span class="sxs-lookup"><span data-stu-id="70ab3-273">Team, group, or SharePoint site creation errors</span></span>
<span data-ttu-id="70ab3-274">如果在公共预览版期间遇到创建错误，可按照[在 PowerShell 中启用敏感度标签支持](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)中的相同说明操作，为 Microsoft Teams 网站、Office 365 组和 SharePoint 网站禁用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="70ab3-274">If you experience creation errors during the public preview, you can turn off sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="70ab3-275">但是如果要禁用预览，在第 5 步 中使用 `$setting["EnableMIPLabels"] = "False"` 禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="70ab3-275">However, to disable the preview, in step 5, disable the feature by using `$setting["EnableMIPLabels"] = "False"`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70ab3-276">其他资源</span><span class="sxs-lookup"><span data-stu-id="70ab3-276">Additional resources</span></span>

<span data-ttu-id="70ab3-277">如需有关[通过 Microsoft Teams、O365 组和 SharePoint Online 网站使用敏感度标签](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380)的信息，请参阅网络研讨会的记录和回答的问题。</span><span class="sxs-lookup"><span data-stu-id="70ab3-277">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

