---
title: 将敏感度标签与 Microsoft Teams、Microsoft 365 组和 SharePoint 网站配合使用
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
description: 使用敏感度标签保护 SharePoint 和 Microsoft Teams 网站以及 Microsoft 365 组中的内容。
ms.openlocfilehash: 4914a5911ffb493eded46631d7682c1e48cf1426
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860871"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="db85b-103">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="db85b-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="db85b-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="db85b-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="db85b-105">除了使用[敏感度标签](sensitivity-labels.md)来分类和保护文档和电子邮件之外，你还可以使用敏感度标签来保护以下容器中的内容：Microsoft Teams 网站、Microsoft 365 组（[以前称为 Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="db85b-106">对于此容器级别分类和保护，请使用以下标签设置：</span><span class="sxs-lookup"><span data-stu-id="db85b-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="db85b-107">与 Microsoft 365 组连接的团队网站的隐私（公共或专用）</span><span class="sxs-lookup"><span data-stu-id="db85b-107">Privacy (public or private) of teams sites and Microsoft 365 groups</span></span>
- <span data-ttu-id="db85b-108">外部用户访问</span><span class="sxs-lookup"><span data-stu-id="db85b-108">External user access</span></span>
- <span data-ttu-id="db85b-109">从 SharePoint 网站进行外部共享</span><span class="sxs-lookup"><span data-stu-id="db85b-109">External sharing from SharePoint sites</span></span>
- <span data-ttu-id="db85b-110">非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="db85b-110">Access from unmanaged devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db85b-111">“**非托管设备的访问**”设置可与 SharePoint 功能配合使用，从而 [控制非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="db85b-111">The **Access from unmanaged devices** setting works in conjunction with the SharePoint feature to [control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span> <span data-ttu-id="db85b-112">必须配置此从属 SharePoint 功能，才能使用配置了此设置的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-112">You must configure this dependent SharePoint feature to use a sensitivity label that has this setting configured.</span></span> <span data-ttu-id="db85b-113">下面的说明中提供了其他信息。</span><span class="sxs-lookup"><span data-stu-id="db85b-113">Additional information is included in the instructions that follow.</span></span>

<span data-ttu-id="db85b-114">如果你将此敏感度标签应用于受支持的容器，此标签会自动向网站或组应用分类和配置保护设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-114">When you apply this sensitivity label to a supported container, the label automatically applies the classification and configured protection settings to the site or group.</span></span>

<span data-ttu-id="db85b-115">但是，这些容器中的内容不会继承用于文件和电子邮件分类或设置的标签，例如视觉标记和加密。</span><span class="sxs-lookup"><span data-stu-id="db85b-115">Content in these containers however, do not inherit the labels for the classification or settings for files and emails, such as visual markings and encryption.</span></span> <span data-ttu-id="db85b-116">这样，用户可以标记 SharePoint 网站或团队网站中的文档，确保[为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="db85b-116">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="db85b-117">Office 365 内容交付网络 (CDN) 不支持容器的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-117">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="db85b-118">将敏感度标签用于 Microsoft Teams、Microsoft 365 组和 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="db85b-118">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="db85b-119">在你为容器启用敏感度标签并为新设置配置敏感度标签之前，用户可在其应用中查看和应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-119">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users could see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="db85b-120">例如，在 Word 中：</span><span class="sxs-lookup"><span data-stu-id="db85b-120">For example, from Word:</span></span>

![Word 桌面应用中显示的敏感度标签](../media/sensitivity-label-word.png)

<span data-ttu-id="db85b-122">为容器启用并配置敏感度标签后，用户还可查看敏感度标签并将其应用于 Microsoft 团队网站、Microsoft 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-122">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="db85b-123">例如，在从 SharePoint 创建新的团队网站时：</span><span class="sxs-lookup"><span data-stu-id="db85b-123">For example, when you create a new team site from SharePoint:</span></span>

![从 SharePoint 中创建团队网站时使用的敏感度标签](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="db85b-125">如何为容器启用敏感度标签和同步标签</span><span class="sxs-lookup"><span data-stu-id="db85b-125">How to enable sensitivity labels for containers and synchronize labels</span></span>

1. <span data-ttu-id="db85b-126">由于此功能使用 Azure AD 功能，因此请按照以下 Azure AD 文档中的说明来启用敏感度标签支持：[在 Azure Active Directory 中向 Microsoft 365 组分配敏感度标签](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="db85b-126">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="db85b-127">现在，你需要将敏感度标签同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="db85b-127">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="db85b-128">首先，[连接到安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="db85b-128">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="db85b-129">例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="db85b-129">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account.</span></span>

3. <span data-ttu-id="db85b-130">然后运行以下命令，以确保可将敏感度标签与 Microsoft 365 组配合使用：</span><span class="sxs-lookup"><span data-stu-id="db85b-130">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-groups-and-site-settings"></a><span data-ttu-id="db85b-131">如何配置组和网站设置</span><span class="sxs-lookup"><span data-stu-id="db85b-131">How to configure groups and site settings</span></span>

<span data-ttu-id="db85b-132">为容器启用敏感度标签意味着你现在可以在敏感度标签向导中为组和网站配置保护设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-132">Enabling sensitivity labels for containers means that you can now configure protection settings for groups and sites in the sensitivity labeling wizard.</span></span> <span data-ttu-id="db85b-133">在启用此支持之前，这些设置在向导中可见，但无法对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="db85b-133">Until you enable this support, the settings are visible in the wizard but you can't configure them.</span></span>

1. <span data-ttu-id="db85b-134">请遵循一般说明来 [创建或编辑敏感度标签](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)，并确保为标签的作用域选择“**组和网站**”：</span><span class="sxs-lookup"><span data-stu-id="db85b-134">Follow the general instructions to [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) and make sure you select **Groups & sites** for the label's scope:</span></span> 
    
    ![文件和电子邮件的敏感度标签作用域选项](../media/groupsandsites-scope-options-sensitivity-label.png)
    
    <span data-ttu-id="db85b-136">如果仅为标签选择此范围，则该标签将不会在支持敏感度标签的 Office 应用中显示，也无法应用于文件和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db85b-136">When only this scope is selected for the label, the label won't be displayed in Office apps that support sensitivity labels and can't be applied to files and emails.</span></span> <span data-ttu-id="db85b-137">分隔标签对于用户和管理员都将有所帮助，但也会增加标签部署的复杂性。</span><span class="sxs-lookup"><span data-stu-id="db85b-137">Having this separation of labels can be helpful for both users and administrators, but can also add to the complexity of your label deployment.</span></span>
    
    <span data-ttu-id="db85b-138">例如，你需要仔细检查[标签顺序](sensitivity-labels.md#label-priority-order-matters)，因为 SharePoint 会检测何时将标签文档上载到标签网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-138">For example, you need to carefully review your [label ordering](sensitivity-labels.md#label-priority-order-matters) because SharePoint detects when a labeled document is uploaded to a labeled site.</span></span> <span data-ttu-id="db85b-139">在这种情况下，当文档具有比网站标签更高的优先级敏感度标签时，会自动生成审核事件和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db85b-139">In this scenario, an audit event and email are automatically generated when the document has a higher priority sensitivity label than the site's label.</span></span> <span data-ttu-id="db85b-140">有关更多信息，请参阅本页上的[审核敏感度标签活动](#auditing-sensitivity-label-activities)部分。</span><span class="sxs-lookup"><span data-stu-id="db85b-140">For more information, see the [Auditing sensitivity label activities](#auditing-sensitivity-label-activities) section on this page.</span></span> 

2. <span data-ttu-id="db85b-141">然后，在 **定义组和网站的保护设置** 页面上，选择一个或两个可用选项：</span><span class="sxs-lookup"><span data-stu-id="db85b-141">Then, on the **Define protection settings for groups and sites** page, select one or both of the available options:</span></span>
    
    - <span data-ttu-id="db85b-142">“**隐私和外部用户访问设置**”用于配置“**隐私**”和“**外部用户访问**”设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-142">**Privacy and external user access settings** to configure the **Privacy** and **External users access** settings.</span></span> 
    - <span data-ttu-id="db85b-143">“**设备访问和外部共享设置**”用于配置“**控制来自标记的 SharePoint 网站的外部共享**”和“**非托管设备的访问**”设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-143">**Device access and external sharing settings** to configure the **Control external sharing from labeled SharePoint sites** and **Access from unmanaged devices** setting.</span></span>

3. <span data-ttu-id="db85b-144">如果你选择了“**隐私和外部用户访问设置**”，现在请配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="db85b-144">If you selected **Privacy and external user access settings**, now configure the following settings:</span></span>
    
    - <span data-ttu-id="db85b-145">**隐私**：如果要使组织中的每个人都可访问应用此标签的团队网站或组，请保留“**公用**”的默认设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-145">**Privacy**: Keep the default of **Public** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>
        
        <span data-ttu-id="db85b-146">如果要将访问权限限制为仅允许组织中的已批准成员，请选择“**专用**”。</span><span class="sxs-lookup"><span data-stu-id="db85b-146">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>
        
        <span data-ttu-id="db85b-147">如果要使用敏感度标签保护容器中的内容，但仍允许用户自行配置隐私设置，请选择“**无**”。</span><span class="sxs-lookup"><span data-stu-id="db85b-147">Select **None** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>
        
        <span data-ttu-id="db85b-148">“**公用**”或“**专用**”的设置可在你将此标签应用到容器时设置和锁定隐私设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-148">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="db85b-149">你选择的设置将替换之前可能已为团队或组配置的任何隐私设置，并锁定隐私值，因此只有先从容器中删除敏感度标签才能更改它。</span><span class="sxs-lookup"><span data-stu-id="db85b-149">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="db85b-150">删除敏感度标签后，标签中的隐私设置仍将保留，用户现在可以再次更改它。</span><span class="sxs-lookup"><span data-stu-id="db85b-150">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>
    
    - <span data-ttu-id="db85b-151">**外部用户访问**：控制组所有者是否可以 [向组添加来宾](/office365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="db85b-151">**External user access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

4. <span data-ttu-id="db85b-152">如果你选择了“**设备访问和外部共享设置**”，现在请配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="db85b-152">If you selected **Device access and external sharing setting**, now configure the following settings:</span></span>
    
    - <span data-ttu-id="db85b-153">**控制来自标记为 SharePoint 网站或网站** 的外部共享：选择此选项，然后选择对任何人、新来宾和现有来宾、现有来宾或仅对组织内部人员的外部共享。</span><span class="sxs-lookup"><span data-stu-id="db85b-153">**Control external sharing from labeled SharePoint sites**: Select this option to then select either external sharing for anyone, new and existing guests, existing guests, or only people in your organization.</span></span> <span data-ttu-id="db85b-154">有关此配置和设置的详细信息，请参阅 SharePoint 文档，[为网站开启或关闭外部共享](/sharepoint/change-external-sharing-site)。</span><span class="sxs-lookup"><span data-stu-id="db85b-154">For more information about this configuration and settings, see the SharePoint documentation, [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
    
    - <span data-ttu-id="db85b-155">**非托管设备的访问**：此选项使用利用 Azure AD 条件访问来阻止或限制从非托管设备访问 SharePoint 和 OneDrive 内容的 SharePoint 功能。</span><span class="sxs-lookup"><span data-stu-id="db85b-155">**Access from unmanaged devices**: This option uses the SharePoint feature that uses Azure AD conditional access to block or limit access to SharePoint and OneDrive content from unmanaged devices.</span></span> <span data-ttu-id="db85b-156">有关详细信息，请参阅 SharePoint 文档中的[控制非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)。</span><span class="sxs-lookup"><span data-stu-id="db85b-156">For more information, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices) from the SharePoint documentation.</span></span> <span data-ttu-id="db85b-157">为此标签设置指定的选项等效于运行针对网站的 PowerShell 命令，如 SharePoint 说明中的[阻止或限制对特定 SharePoint 网站或 OneDrive](/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) 部分的步骤 3-5 所述。</span><span class="sxs-lookup"><span data-stu-id="db85b-157">The option you specify for this label setting is the equivalent of running a PowerShell command for a site, as described in steps 3-5 from the [Block or limit access to a specific SharePoint site or OneDrive](/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive) section from the SharePoint instructions.</span></span>
        
        <span data-ttu-id="db85b-158">有关其他信息，请参阅本部分末尾的[有关非托管设备选项依赖项的详细信息](#more-information-about-the-dependencies-for-the-unmanaged-devices-option)。</span><span class="sxs-lookup"><span data-stu-id="db85b-158">For additional information, see [More information about the dependencies for the unmanaged devices option](#more-information-about-the-dependencies-for-the-unmanaged-devices-option) at the end of this section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db85b-159">将标签应用于团队、组或网站时，只有这些网站和组设置会生效。</span><span class="sxs-lookup"><span data-stu-id="db85b-159">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="db85b-160">如果[标签作用域](sensitivity-labels.md#label-scopes)包括文件和电子邮件，则其他标签设置（例如加密和内容标记）不适用于团队、组或网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="db85b-160">If the [label's scope](sensitivity-labels.md#label-scopes) includes files and emails, other label settings such as encryption and content marking aren't applied to the content within the team, group, or site.</span></span>

<span data-ttu-id="db85b-161">如果尚未发布敏感度标签，现可通过[将其添加到敏感度标签策略](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)进行发布。</span><span class="sxs-lookup"><span data-stu-id="db85b-161">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="db85b-162">分配的敏感度标签策略包含此标签的用户将能够为网站和组选择该标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-162">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

##### <a name="more-information-about-the-dependencies-for-the-unmanaged-devices-option"></a><span data-ttu-id="db85b-163">有关非托管设备选项依赖项的详细信息</span><span class="sxs-lookup"><span data-stu-id="db85b-163">More information about the dependencies for the unmanaged devices option</span></span>

<span data-ttu-id="db85b-164">如果未按照“[使用应用强制实施的限制](/sharepoint/app-enforced-restrictions)”中的文档配置 SharePoint 的相关条件访问策略，则此处指定的选项将无效。</span><span class="sxs-lookup"><span data-stu-id="db85b-164">If you don't configure the dependent conditional access policy for SharePoint as documented in [Use app-enforced restrictions](/sharepoint/app-enforced-restrictions), the option you specify here will have no effect.</span></span> <span data-ttu-id="db85b-165">此外，如果其限制性低于在租户级别配置的设置，则也不会起作用。</span><span class="sxs-lookup"><span data-stu-id="db85b-165">Additionally, it will have no effect if it's less restrictive than a configured setting at the tenant level.</span></span> <span data-ttu-id="db85b-166">如果你已为非托管设备配置了组织范围的设置，请选择相同或更严格的标签设置</span><span class="sxs-lookup"><span data-stu-id="db85b-166">If you have configured an organization-wide setting for unmanaged devices, choose a label setting that's either the same or more restrictive</span></span>

<span data-ttu-id="db85b-167">例如，如果你的租户被配置为“**允许仅限 Web 的受限访问**”，则允许完全访问权限的标签设置将不起作用，因为其限制性较弱。</span><span class="sxs-lookup"><span data-stu-id="db85b-167">For example, if your tenant is configured for **Allow limited, web-only access**, the label setting that allows full access will have no effect because it's less restrictive.</span></span> <span data-ttu-id="db85b-168">对于此租户级设置，请选择可阻止访问的标签设置（限制性更强）或可实现受限访问的标签设置（与租户设置相同）。</span><span class="sxs-lookup"><span data-stu-id="db85b-168">For this tenant-level setting, choose the label setting to block access (more restrictive) or the label setting for limited access (the same as the tenant setting).</span></span>

<span data-ttu-id="db85b-169">由于可以独立于标签配置来配置该 SharePoint 设置，因此在敏感度标签向导中不会检查依赖项是否已就位。</span><span class="sxs-lookup"><span data-stu-id="db85b-169">Because you can configure the SharePoint settings separately from the label configuration, there's no check in the sensitivity label wizard that the dependencies are in place.</span></span> <span data-ttu-id="db85b-170">这些依赖项可在创建和发布标签，甚至应用标签后配置。</span><span class="sxs-lookup"><span data-stu-id="db85b-170">These dependencies can be configured after the label is created and published, and even after the label is applied.</span></span> <span data-ttu-id="db85b-171">但是，如果已应用标签，则标签设置要在用户下次进行身份验证后才会生效。</span><span class="sxs-lookup"><span data-stu-id="db85b-171">However, if the label is already applied, the label setting won't take effect until after the user next authenticates.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="db85b-172">敏感度标签管理</span><span class="sxs-lookup"><span data-stu-id="db85b-172">Sensitivity label management</span></span>

<span data-ttu-id="db85b-173">在创建、修改或删除为网站和组配置的敏感度标签时，请使用以下指南。</span><span class="sxs-lookup"><span data-stu-id="db85b-173">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="db85b-174">创建和发布为网站和组配置的标签</span><span class="sxs-lookup"><span data-stu-id="db85b-174">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="db85b-175">创建并发布新敏感度标签后，团队、组和网站中的用户可在 1 小时内能看到该标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-175">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="db85b-176">但是，如果修改现有标签，最多需要 24 小时才能看到。</span><span class="sxs-lookup"><span data-stu-id="db85b-176">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="db85b-177">为网站和组设置配置标签后，请按照以下指南为你的用户发布标签：</span><span class="sxs-lookup"><span data-stu-id="db85b-177">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="db85b-178">创建并配置敏感度标签后，将此标签添加到仅应用于少数测试用户的标签策略。</span><span class="sxs-lookup"><span data-stu-id="db85b-178">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="db85b-179">等待更改复制：</span><span class="sxs-lookup"><span data-stu-id="db85b-179">Wait for the change to replicate:</span></span>

   - <span data-ttu-id="db85b-180">新标签：等待一小时。</span><span class="sxs-lookup"><span data-stu-id="db85b-180">New label: Wait for one hour.</span></span>
   - <span data-ttu-id="db85b-181">现有标签：等待 24 小时。</span><span class="sxs-lookup"><span data-stu-id="db85b-181">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="db85b-182">在此等待期之后，使用测试用户帐户之一，创建具有在步骤 1 中创建的标签的团队、Microsoft 365 组或 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-182">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="db85b-183">如果在此创建操作过程中没有错误，表示可以安全地为租户中的所有用户发布标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-183">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="db85b-184">修改为网站和组配置的已发布标签</span><span class="sxs-lookup"><span data-stu-id="db85b-184">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="db85b-185">最佳做法是，在为团队、组或网站应用标签后，不要更改敏感度标签的网站和组设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-185">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="db85b-186">如果这样做，请记住等待 24 小时，使更改复制到应用了标签的所有容器。</span><span class="sxs-lookup"><span data-stu-id="db85b-186">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span>

<span data-ttu-id="db85b-187">此外，如果所做的更改包括 **外部用户访问** 设置：</span><span class="sxs-lookup"><span data-stu-id="db85b-187">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="db85b-188">新设置仅适用于新用户，并不适用于现有用户。</span><span class="sxs-lookup"><span data-stu-id="db85b-188">The new setting applies to new users but not to existing users.</span></span> <span data-ttu-id="db85b-189">例如，如果以前选择了此设置，并且来宾用户访问了网站，则在标签配置中清除此设置后，这些来宾用户仍可访问该网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-189">For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="db85b-190">组属性 hiddenMembership 和 roleEnabled 的隐私设置不会更新。</span><span class="sxs-lookup"><span data-stu-id="db85b-190">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="db85b-191">删除为网站和组配置的已发布标签</span><span class="sxs-lookup"><span data-stu-id="db85b-191">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="db85b-192">如果删除已启用网站和组设置的敏感度标签，且该标签包含在一个或多个标签策略中，则此操作可能会导致新团队、组和网站的创建失败。</span><span class="sxs-lookup"><span data-stu-id="db85b-192">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites.</span></span> <span data-ttu-id="db85b-193">若要避免这种情况，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="db85b-193">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="db85b-194">从包含敏感度标签的所有标签策略中删除该标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-194">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="db85b-195">等待一小时。</span><span class="sxs-lookup"><span data-stu-id="db85b-195">Wait for one hour.</span></span>

3. <span data-ttu-id="db85b-196">在此等待期之后，尝试创建团队、组或网站，并确认标签不再可见。</span><span class="sxs-lookup"><span data-stu-id="db85b-196">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="db85b-197">如果敏感度标签不可见，则现在可以安全地删除该标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-197">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="db85b-198">如何将敏感度标签应用于容器</span><span class="sxs-lookup"><span data-stu-id="db85b-198">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="db85b-199">现在可将一个或多个敏感度标签应用于以下容器：</span><span class="sxs-lookup"><span data-stu-id="db85b-199">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="db85b-200">Azure AD 中的 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="db85b-200">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="db85b-201">Microsoft Teams 团队网站</span><span class="sxs-lookup"><span data-stu-id="db85b-201">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="db85b-202">Outlook 网页版中的 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="db85b-202">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="db85b-203">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="db85b-203">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="db85b-204">如果需要[将敏感度标签应用于多个网站](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites)，则可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="db85b-204">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="db85b-205">将敏感度标签应用于 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="db85b-205">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="db85b-206">现在可将一个或多个敏感度标签应用于 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="db85b-206">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="db85b-207">请返回到 Azure AD 文档查看说明：</span><span class="sxs-lookup"><span data-stu-id="db85b-207">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="db85b-208">在 Azure 门户中为新组分配标签</span><span class="sxs-lookup"><span data-stu-id="db85b-208">Assign a label to a new group in Azure portal</span></span>](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

- [<span data-ttu-id="db85b-209">为 Azure 门户中的现有组分配标签</span><span class="sxs-lookup"><span data-stu-id="db85b-209">Assign a label to an existing group in Azure portal</span></span>](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- <span data-ttu-id="db85b-210">[从 Azure 门户中的现有组中删除标签](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="db85b-210">[Remove a label from an existing group in Azure portal](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="db85b-211">为新团队应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="db85b-211">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="db85b-212">在 Microsoft Teams 中创建新团队时，用户可以选择敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-212">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="db85b-213">如果用户从“敏感度”下拉列表中选择标签，隐私设置可能会更改，以反映标签配置。</span><span class="sxs-lookup"><span data-stu-id="db85b-213">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="db85b-214">根据为标签选择的外部用户访问设置，用户可以或不能将组织外部人员添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="db85b-214">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="db85b-215">了解有关 Teams 的敏感度标签的详细信息</span><span class="sxs-lookup"><span data-stu-id="db85b-215">Learn more about sensitivity labels for Teams</span></span>](/microsoftteams/sensitivity-labels)

![创建新团队时使用的隐私设置](../media/privacy-setting-new-team.png)

<span data-ttu-id="db85b-217">创建团队后，敏感度标签将显示在所有频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="db85b-217">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![敏感度标签将显示在团队上](../media/privacy-setting-teams.png)

<span data-ttu-id="db85b-219">该服务会自动将相同的敏感度标签应用于 Microsoft 365 组和连接的 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-219">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="db85b-220">应用敏感度标签至 Outlook 网页版的新组</span><span class="sxs-lookup"><span data-stu-id="db85b-220">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="db85b-221">在 Outlook 网页版中，创建新组时可选择或更改已发布的标签的“**敏感度**”选项：</span><span class="sxs-lookup"><span data-stu-id="db85b-221">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![创建组并选择“敏感度”下的选项](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="db85b-223">为新网站应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="db85b-223">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="db85b-224">管理员和最终用户可以在[创建新式团队网站和通信网站时](/sharepoint/create-site-collection)选择敏感度标签，并展开“高级设置”：</span><span class="sxs-lookup"><span data-stu-id="db85b-224">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![创建网站并在“敏感度”下选择一个选项](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="db85b-226">下拉列表框显示选择的标签名称，帮助图标显示所有标签名称及其工具提示，这可帮助用户确定要应用的正确标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-226">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="db85b-227">在标签应用后，当用户浏览网站时，可以看到标签名称和所应用的策略。</span><span class="sxs-lookup"><span data-stu-id="db85b-227">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="db85b-228">例如，此网站标记为“机密”，且隐私设置设为“私有”：</span><span class="sxs-lookup"><span data-stu-id="db85b-228">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![已应用敏感度标签的网站](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="db85b-230">使用 PowerShell 将敏感度标签应用于多个网站</span><span class="sxs-lookup"><span data-stu-id="db85b-230">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="db85b-231">你可以将 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) 和 [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet 与当前 [SharePoint Online 命令行管理程序](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)中的 *SensitivityLabel* 参数一起使用，以将敏感度标签应用于多个网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-231">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="db85b-232">网站可以是任何 SharePoint 网站集或 OneDrive 网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-232">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="db85b-233">请确保你拥有 SharePoint Online 命令行管理程序的 16.0.19418.12000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="db85b-233">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="db85b-234">使用“**以管理员身份运行**”选项打开 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="db85b-234">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="db85b-235">如果你不知道标签 GUID：[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)，获取敏感度标签及其 GUID 的列表。</span><span class="sxs-lookup"><span data-stu-id="db85b-235">If you don't know your label GUID: [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and get the list of sensitivity labels and their GUIDs.</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="db85b-236">现在，[连接到 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 并将标签 GUID 存储为变量。</span><span class="sxs-lookup"><span data-stu-id="db85b-236">Now [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable.</span></span> <span data-ttu-id="db85b-237">例如：</span><span class="sxs-lookup"><span data-stu-id="db85b-237">For example:</span></span>

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. <span data-ttu-id="db85b-p127">创建一个新变量，用于标识在其 URL 中有共同标识字符串的多个网站。例如：</span><span class="sxs-lookup"><span data-stu-id="db85b-p127">Create a new variable that identifies multiple sites that have an identifying string in common in their URL. For example:</span></span>

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. <span data-ttu-id="db85b-240">运行以下命令以将标签应用于这些网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-240">Run the following command to apply the label to these sites.</span></span> <span data-ttu-id="db85b-241">使用我们的示例：</span><span class="sxs-lookup"><span data-stu-id="db85b-241">Using our examples:</span></span>

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

<span data-ttu-id="db85b-242">通过此系列命令，可使用相同的敏感度标签标记租户中的多个站点，因此可使用 Set-SPOTenant cmdlet，而不是针对每个网站配置的 Set-SPOSite cmdlet。</span><span class="sxs-lookup"><span data-stu-id="db85b-242">This series of commands lets you label multiple sites across your tenant with the same sensitivity label, which is why you use the Set-SPOTenant cmdlet, rather than the Set-SPOSite cmdlet that's for per-site configuration.</span></span> <span data-ttu-id="db85b-243">但是，当需要应用不同标签为特定网站重复以下命令时，请使用 Set-SPOSite cmdlet： `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="db85b-243">However, use the Set-SPOSite cmdlet when you need to apply a different label to specific sites by repeating the following command for each of these sites: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="db85b-244">在 SharePoint 管理中心中查看和管理敏感度标签</span><span class="sxs-lookup"><span data-stu-id="db85b-244">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="db85b-245">若要查看、排序和搜索已应用的敏感度标签，请使用新 SharePoint 管理中心中的“**活动网站**”页面。</span><span class="sxs-lookup"><span data-stu-id="db85b-245">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="db85b-246">可能需要先添加“**敏感度**”列：</span><span class="sxs-lookup"><span data-stu-id="db85b-246">You might need to first add the **Sensitivity** column:</span></span>

![“活动网站”页面上的“敏感度”列](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="db85b-248">有关从“活动网站”页面管理网站（包括如何添加列）的详细信息，请参阅[管理新 SharePoint 管理中心中的网站](/sharepoint/manage-sites-in-new-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="db85b-248">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="db85b-249">你也可以从此页面更改和应用标签：</span><span class="sxs-lookup"><span data-stu-id="db85b-249">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="db85b-250">单击网站名称以打开“详细信息”窗格。</span><span class="sxs-lookup"><span data-stu-id="db85b-250">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="db85b-251">选择“**策略**”选项卡，然后为“**敏感度**”设置选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="db85b-251">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="db85b-252">从“**编辑敏感度设置**”窗格中，选择要应用于该网站的敏感度标签，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="db85b-252">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="db85b-253">敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="db85b-253">Support for sensitivity labels</span></span>

<span data-ttu-id="db85b-254">以下应用和服务支持为网站和组设置配置的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="db85b-254">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="db85b-255">管理中心：</span><span class="sxs-lookup"><span data-stu-id="db85b-255">Admin centers:</span></span>

  - <span data-ttu-id="db85b-256">SharePoint 管理中心</span><span class="sxs-lookup"><span data-stu-id="db85b-256">SharePoint admin center</span></span>
  - <span data-ttu-id="db85b-257">Azure Active Directory 高级版</span><span class="sxs-lookup"><span data-stu-id="db85b-257">Azure Active Directory portal</span></span>
  - <span data-ttu-id="db85b-258">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="db85b-258">Microsoft 365 admin center</span></span>
  - <span data-ttu-id="db85b-259">Microsoft 365 合规中心、Microsoft 365 安全中心、安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="db85b-259">Microsoft 365 compliance center, Microsoft 365 security center, Security & Compliance Center</span></span>

- <span data-ttu-id="db85b-260">用户应用和服务：</span><span class="sxs-lookup"><span data-stu-id="db85b-260">User apps and services:</span></span>

  - <span data-ttu-id="db85b-261">SharePoint</span><span class="sxs-lookup"><span data-stu-id="db85b-261">SharePoint</span></span>
  - <span data-ttu-id="db85b-262">Teams</span><span class="sxs-lookup"><span data-stu-id="db85b-262">Teams</span></span>
  - <span data-ttu-id="db85b-263">Outlook 网页版以及 Windows、macOS、iOS 和 Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="db85b-263">Outlook on the web and for Windows, macOS, iOS, and Android</span></span>
  - <span data-ttu-id="db85b-264">Forms</span><span class="sxs-lookup"><span data-stu-id="db85b-264">Forms</span></span>
  - <span data-ttu-id="db85b-265">Stream</span><span class="sxs-lookup"><span data-stu-id="db85b-265">Stream</span></span>
  - <span data-ttu-id="db85b-266">Planner</span><span class="sxs-lookup"><span data-stu-id="db85b-266">Planner</span></span> 

<span data-ttu-id="db85b-267">以下应用和服务目前不支持为网站和组设置配置的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="db85b-267">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="db85b-268">管理中心：</span><span class="sxs-lookup"><span data-stu-id="db85b-268">Admin centers:</span></span>

  - <span data-ttu-id="db85b-269">Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="db85b-269">Teams admin center</span></span>
  - <span data-ttu-id="db85b-270">Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="db85b-270">Exchange admin center</span></span>

- <span data-ttu-id="db85b-271">用户应用和服务：</span><span class="sxs-lookup"><span data-stu-id="db85b-271">User apps and services:</span></span>

  - <span data-ttu-id="db85b-272">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="db85b-272">Dynamics 365</span></span>
  - <span data-ttu-id="db85b-273">Yammer</span><span class="sxs-lookup"><span data-stu-id="db85b-273">Yammer</span></span>
  - <span data-ttu-id="db85b-274">Project</span><span class="sxs-lookup"><span data-stu-id="db85b-274">Project</span></span>
  - <span data-ttu-id="db85b-275">Power BI</span><span class="sxs-lookup"><span data-stu-id="db85b-275">Power BI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="db85b-276">经典 Azure AD 组分类</span><span class="sxs-lookup"><span data-stu-id="db85b-276">Classic Azure AD group classification</span></span>

<span data-ttu-id="db85b-277">为容器启用敏感度标签后，Microsoft 365 不再支持新 Microsoft 365 组和 SharePoint 网站的旧分类。</span><span class="sxs-lookup"><span data-stu-id="db85b-277">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="db85b-278">但是，除非进行转换以使用敏感度标签，否则支持敏感度标签的现有组和网站仍会显示旧分类值。</span><span class="sxs-lookup"><span data-stu-id="db85b-278">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="db85b-279">有关如何使用 SharePoint 的旧组分类的示例，请参阅 [SharePoint “新式”网站分类](/sharepoint/dev/solution-guidance/modern-experience-site-classification)。</span><span class="sxs-lookup"><span data-stu-id="db85b-279">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="db85b-280">这些分类通过使用 Azure AD PowerShell 或 PnP Core 库以及定义 `ClassificationList` 设置值来进行配置。</span><span class="sxs-lookup"><span data-stu-id="db85b-280">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="db85b-281">如果租户定义了分类值，则在 [AzureADPreview PowerShell 模块](https://www.powershellgallery.com/packages/AzureADPreview)中运行以下命令时，将显示这些分类值：</span><span class="sxs-lookup"><span data-stu-id="db85b-281">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
($setting["ClassificationList"])
```

<span data-ttu-id="db85b-282">若要将旧分类转换为敏感度标签，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="db85b-282">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="db85b-283">使用现有标签：通过编辑已发布的现有敏感度标签，指定你希望网站和组使用的标签设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-283">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="db85b-284">创建新标签：通过创建和发布与你的现有分类名称相同的新的敏感度标签，指定你希望网站和组使用的标签设置。</span><span class="sxs-lookup"><span data-stu-id="db85b-284">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="db85b-285">则：</span><span class="sxs-lookup"><span data-stu-id="db85b-285">Then:</span></span>

1. <span data-ttu-id="db85b-286">使用 PowerShell 将敏感度标签应用至使用名称映射的现有 Microsoft 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="db85b-286">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="db85b-287">相关说明，请参见下一节。</span><span class="sxs-lookup"><span data-stu-id="db85b-287">See the next section for instructions.</span></span>

2. <span data-ttu-id="db85b-288">删除现有组和网站中的旧分类。</span><span class="sxs-lookup"><span data-stu-id="db85b-288">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="db85b-289">虽然无法阻止用户在尚不支持敏感度标签的应用和服务中创建新组，但可运行定期 PowerShell 标签来查看用户已使用旧分类创建的新组，并转换这些分类以使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-289">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span>

<span data-ttu-id="db85b-290">为了帮助管理网站和组的敏感度标签与 Azure AD 分类的共存，请参阅[适用于 Microsoft 365 组的 Azure Active Directory 分类和敏感度标签](migrate-aad-classification-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="db85b-290">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="db85b-291">使用 PowerShell 将 Microsoft 365 组的分类转换为敏感度标签</span><span class="sxs-lookup"><span data-stu-id="db85b-291">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="db85b-292">首先，[连接到安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="db85b-292">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="db85b-293">例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录：</span><span class="sxs-lookup"><span data-stu-id="db85b-293">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>

2. <span data-ttu-id="db85b-294">通过运行 [ Get-Label ](/powershell/module/exchange/get-label) cmdlet 获取敏感度标签及 GUID 列表：</span><span class="sxs-lookup"><span data-stu-id="db85b-294">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](/powershell/module/exchange/get-label) cmdlet:</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="db85b-295">记下你想要应用到 Microsoft 365 组的敏感度标签的 Guid。</span><span class="sxs-lookup"><span data-stu-id="db85b-295">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="db85b-296">现在，在单独的 Windows PowerShell 窗口中[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="db85b-296">Now [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a separate Windows PowerShell window.</span></span>

5. <span data-ttu-id="db85b-297">以下列命令为例，获取当前具有“常规”分类的组列表：</span><span class="sxs-lookup"><span data-stu-id="db85b-297">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="db85b-p134">对于每个组，添加新的敏感度标签 GUID。例如：</span><span class="sxs-lookup"><span data-stu-id="db85b-p134">For each group, add the new sensitivity label GUID. For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="db85b-300">对剩下的组分类重复步骤 5 和 6。</span><span class="sxs-lookup"><span data-stu-id="db85b-300">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="db85b-301">审核敏感度标签活动</span><span class="sxs-lookup"><span data-stu-id="db85b-301">Auditing sensitivity label activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db85b-302">如果通过仅为保护容器的标签选择“**组和网站**”作用域来使用标签分离，则：由于本部分描述的 **检测到文档敏感度不匹配** 审核事件和电子邮件，请考虑在为标签设置“**文件和电子邮件**”作用域之前先 [对这些标签进行排序](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="db85b-302">If you use label separation by selecting just the **Groups & sites** scope for labels that protect containers: Because of the **Detected document sensitivity mismatch** audit event and email described in this section, consider [ordering these labels](sensitivity-labels.md#label-priority-order-matters) before labels that have a scope for **Files & emails**.</span></span> 

<span data-ttu-id="db85b-303">如果有人将文档上传到受敏感度标签保护的网站上，且该文档的敏感度标签的[优先级](sensitivity-labels.md#label-priority-order-matters)比该网站应用的敏感度标签高，则不会阻止此操作。</span><span class="sxs-lookup"><span data-stu-id="db85b-303">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="db85b-304">例如，你向 SharePoint 网站应用了“**常规**”标签，并且有人向此网站上传了一个标记为“**机密**”的文档。</span><span class="sxs-lookup"><span data-stu-id="db85b-304">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="db85b-305">对于优先级更低的内容来说，具有更高优先级的敏感度标签会识别敏感度高于此内容的内容，因此该情况可能会带来安全隐患。</span><span class="sxs-lookup"><span data-stu-id="db85b-305">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="db85b-306">虽然此操作未被阻止，但它经过审核，并会自动生成一封面向上传文档的人员和网站管理员的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db85b-306">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="db85b-307">因此，可识别存在这种标签优先级不一致情况的用户和管理员，并在必要时采取措施。</span><span class="sxs-lookup"><span data-stu-id="db85b-307">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="db85b-308">例如，从网站中删除或移动已上传的文档。</span><span class="sxs-lookup"><span data-stu-id="db85b-308">For example, delete or move the uploaded document from the site.</span></span>

<span data-ttu-id="db85b-309">如果文档的敏感度标签的优先级低于网站应用的敏感度标签，则不会出现安全问题。</span><span class="sxs-lookup"><span data-stu-id="db85b-309">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="db85b-310">例如，标有“**常规**”的文档上传到标有“**机密**”的网站上。</span><span class="sxs-lookup"><span data-stu-id="db85b-310">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="db85b-311">在这种情况中，不生成审核事件和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db85b-311">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="db85b-312">要搜索此事件的审核日志，请从“**文件和页面活动**”类别中查找“**检测到文档敏感度不匹配**”。</span><span class="sxs-lookup"><span data-stu-id="db85b-312">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span>

<span data-ttu-id="db85b-313">自动生成的电子邮件具有主题“**检测到不兼容的敏感度标签**”，该电子邮件将说明标记不匹配，并提供指向已上传文档和网站的链接。</span><span class="sxs-lookup"><span data-stu-id="db85b-313">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="db85b-314">此外，它还包含说明用户可以如何更改敏感度标签的文档链接。</span><span class="sxs-lookup"><span data-stu-id="db85b-314">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="db85b-315">目前，无法禁用或自定义这些自动发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db85b-315">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="db85b-316">当有人向网站或组添加敏感度标签或从中删除敏感度标签时，也会审核这些活动，但不会自动生成电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db85b-316">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span>

<span data-ttu-id="db85b-317">可在“[敏感度标签活动](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)”类别中找到这些审核事件。</span><span class="sxs-lookup"><span data-stu-id="db85b-317">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="db85b-318">有关搜索审核日志的说明，请参阅[在安全与合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="db85b-318">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="db85b-319">如何禁用容器的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="db85b-319">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="db85b-320">你可按照[在 PowerShell 中启用敏感度标签支持](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell)中的相同说明，为 Microsoft Teams、Microsoft 365 组和 SharePoint 网站关闭敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-320">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="db85b-321">但是，若要禁用此功能，请在步骤 5 中指定 `$setting["EnableMIPLabels"] = "False"`。</span><span class="sxs-lookup"><span data-stu-id="db85b-321">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="db85b-322">除了在创建或编辑敏感度标签时使所有设置对组和网站不可用以外，此操作还可恢复容器用于其配置的属性。</span><span class="sxs-lookup"><span data-stu-id="db85b-322">In addition to making all the settings unavailable for groups and sites when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="db85b-323">为 Microsoft Teams、Microsoft 365 组和 SharePoint 网站启用敏感度标签会将使用的属性从“**分类**”（用于 [Azure AD 组分类](#classic-azure-ad-group-classification)）切换为“**敏感度**”。</span><span class="sxs-lookup"><span data-stu-id="db85b-323">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="db85b-324">当禁用容器的敏感度标签时，容器将忽略敏感度属性并再次使用“分类”属性。</span><span class="sxs-lookup"><span data-stu-id="db85b-324">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="db85b-325">这意味着不会强制实施先前应用到容器的网站和组中的任何标签设置，并且容器不再显示标签。</span><span class="sxs-lookup"><span data-stu-id="db85b-325">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="db85b-326">如果这些容器应用了 Azure AD 分类值，则它们将再次恢复为使用分类。</span><span class="sxs-lookup"><span data-stu-id="db85b-326">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="db85b-327">请注意，在启用此功能后创建的任何新网站或组都不会显示标签或具有分类。</span><span class="sxs-lookup"><span data-stu-id="db85b-327">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="db85b-328">对于这些容器以及所有新容器，现在可以应用分类值。</span><span class="sxs-lookup"><span data-stu-id="db85b-328">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="db85b-329">有关详细信息，请参阅 [SharePoint“新式”网站分类](/sharepoint/dev/solution-guidance/modern-experience-site-classification)和[为组织中的 Office 组创建分类](../enterprise/manage-microsoft-365-groups-with-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="db85b-329">For more information, see [SharePoint "modern" sites classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](../enterprise/manage-microsoft-365-groups-with-powershell.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db85b-330">其他资源</span><span class="sxs-lookup"><span data-stu-id="db85b-330">Additional resources</span></span>

<span data-ttu-id="db85b-331">如需有关[通过 Microsoft Teams、O365 组和 SharePoint Online 网站使用敏感度标签](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380)的信息，请参阅网络研讨会的记录和回答的问题。</span><span class="sxs-lookup"><span data-stu-id="db85b-331">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="db85b-332">在录制此网络研讨会时该功能仍处于预览阶段，因此你可能会发现 UI 存在某些差异。</span><span class="sxs-lookup"><span data-stu-id="db85b-332">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="db85b-333">但是，此功能的信息仍准确无误，并且该页面记录了所有新功能。</span><span class="sxs-lookup"><span data-stu-id="db85b-333">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>