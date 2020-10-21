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
ms.openlocfilehash: 7f8337d368c5c9de7cf1d9ff90831777c0811b87
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600467"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites. For this container-level classification and protection, use the following label settings:

- 与 Microsoft 365 组连接的团队网站的隐私（公共或专用）
- 外部用户访问
- 非托管设备的访问

> [!IMPORTANT]
> The **Access from unmanaged devices** setting works in conjunction with the SharePoint feature to [control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices). You must configure this dependent SharePoint feature to use a sensitivity label that has this setting configured. Additional information is included in the instructions that follow.

如果你将此敏感度标签应用于受支持的容器，此标签会自动向网站或组应用分类和配置保护设置。

Content in these containers however, do not inherit the labels for the classification or settings for files and emails, such as visual markings and encryption. So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

> [!NOTE]
> Office 365 内容交付网络 (CDN) 不支持容器的敏感度标签。

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>将敏感度标签用于 Microsoft Teams、Microsoft 365 组和 SharePoint 网站

Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users could see and apply sensitivity labels in their apps. For example, from Word:

![Word 桌面应用中显示的敏感度标签](../media/sensitivity-label-word.png)

After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites. For example, when you create a new team site from SharePoint:

![从 SharePoint 中创建团队网站时使用的敏感度标签](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a>如何为容器启用敏感度标签和同步标签

1. 由于此功能使用 Azure AD 功能，因此请按照以下 Azure AD 文档中的说明来启用敏感度标签支持：[在 Azure Active Directory 中向 Microsoft 365 组分配敏感度标签](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。

2. You now need to synchronize your sensitivity labels to Azure AD. First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

   例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录。

3. 然后运行以下命令，以确保可将敏感度标签与 Microsoft 365 组配合使用：

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-groups-and-site-settings"></a>如何配置组和网站设置

Enabling sensitivity labels for containers means that you can now configure protection settings for groups and sites in the sensitivity labeling wizard. Until you enable this support, the settings are visible in the wizard but you can't configure them.

1. 请遵循一般说明来[创建或编辑敏感度标签](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)，并确保为标签的作用域选择“**组和网站**”： 
    
    ![文件和电子邮件的敏感度标签范围选项](../media/groupsandsites-scope-options-sensitivity-label.png)
    
    When only this scope is selected for the label, the label won't be displayed in Office apps that support sensitivity labels and can't be applied to files and emails. Having this separation of labels can be helpful for both users and administrators, but can also add to the complexity of your label deployment.
    
    For example, you need to carefully review your [label ordering](sensitivity-labels.md#label-priority-order-matters) because SharePoint detects when a labeled document is uploaded to a labeled site. In this sceanrio, an audit event and email is automatically generated when the document has a higher priority sensitivity label than the site's label. For more information, see the [Auditing sensitivity label activities](#auditing-sensitivity-label-activities) section on this page. 

2. 然后，在**定义组和网站的保护设置**页面上，选择一个或两个可用选项：
    
    - “**隐私和外部用户访问设置**”用于配置**隐私**和**外部用户访问**设置。 
    - “**设备访问和外部共享设置**”用于配置“**非托管设备的访问**”设置。

3. 如果你选择了“**隐私和外部用户访问设置**”，现在请配置以下设置：
    
    - **隐私**：如果要使组织中的每个人都可访问应用此标签的团队网站或组，请保留“**公用**”的默认设置。
        
        如果要将访问权限限制为仅允许组织中的已批准成员，请选择“**专用**”。
        
        如果要使用敏感度标签保护容器中的内容，但仍允许用户自行配置隐私设置，请选择“**无**”。
        
        The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container. Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container. After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.
    
    - **外部用户访问**：控制组所有者是否可以[向组添加来宾](/office365/admin/create-groups/manage-guest-access-in-groups)。

4. 如果你选择了“**设备访问和外部共享设置**”，现在请配置以下设置：
    
    - **非托管设备的访问**：此选项使用 SharePoint 功能，该功能使用 Azure AD 条件访问来阻止或限制从非托管设备访问 SharePoint 和 OneDrive 内容。有关详细信息，请参阅 SharePoint 文档中的[控制来自非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)。为此标签设置指定的选项等效于针对网站运行 PowerShell 命令，如 SharePoint 说明中[阻止或限制对特定 SharePoint 网站或 OneDrive 的访问](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive)部分的步骤 3-5 所述。
        
        有关其他信息，请参阅本部分末尾的[有关非托管设备选项依赖项的详细信息](#more-information-about-the-dependencies-for-the-unmanaged-devices-option)。

> [!IMPORTANT]
> Only these site and group settings take effect when you apply the label to a team, group, or site. If the [label's scope](sensitivity-labels.md#label-scopes) includes files and emails, other label settings such as encryption and content marking aren't applied to the content within the team, group, or site.

If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy). The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.

##### <a name="more-information-about-the-dependencies-for-the-unmanaged-devices-option"></a>有关非托管设备选项依赖项的详细信息

If you don't configure the dependent conditional access policy for SharePoint as documented in [Use app-enforced restrictions](https://docs.microsoft.com/sharepoint/app-enforced-restrictions), the option you specify here will have no effect. Additionally, it will have no effect if it's less restrictive than a configured setting at the tenant level. If you have configured an organization-wide setting for unmanaged devices, choose a label setting that's either the same or more restrictive

For example, if your tenant is configured for **Allow limited, web-only access**, the label setting that allows full access will have no effect because it's less restrictive. For this tenant-level setting, choose the label setting to block access (more restrictive) or the label setting for limited access (the same as the tenant setting).

Because you can configure the SharePoint settings separately from the label configuration, there's no check in the sensitivity label wizard that the dependencies are in place. These dependencies can be configured after the label is created and published, and even after the label is applied. However, if the label is already applied, the label setting won't take effect until after the user next authenticates.

## <a name="sensitivity-label-management"></a>敏感度标签管理

在创建、修改或删除为网站和组配置的敏感度标签时，请使用以下指南。

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a>创建和发布为网站和组配置的标签

When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour. However, if you modify an existing label, allow up to 24 hours. Use the following guidance to publish a label for your users when that label is configured for site and group settings:

1. 创建并配置敏感度标签后，将此标签添加到仅应用于少数测试用户的标签策略。

2. 等待更改复制：

   - 新标签：等待一小时。
   - 现有标签：等待 24 小时。

3. 在此等待期之后，使用测试用户帐户之一，创建具有在步骤 1 中创建的标签的团队、Microsoft 365 组或 SharePoint 网站。

4. 如果在此创建操作过程中没有错误，表示可以安全地为租户中的所有用户发布标签。

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a>修改为网站和组配置的已发布标签

As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites. If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.

此外，如果所做的更改包括**外部用户访问**设置：

- The new setting applies to new users but not to existing users. For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.

- 组属性 hiddenMembership 和 roleEnabled 的隐私设置不会更新。

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a>删除为网站和组配置的已发布标签

If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites. To avoid this situation, use the following guidance:

1. 从包含敏感度标签的所有标签策略中删除该标签。

2. 等待一小时。

3. 在此等待期之后，尝试创建团队、组或网站，并确认标签不再可见。

4. 如果敏感度标签不可见，则现在可以安全地删除该标签。

## <a name="how-to-apply-sensitivity-labels-to-containers"></a>如何将敏感度标签应用于容器

现在可将一个或多个敏感度标签应用于以下容器：

- [Azure AD 中的 Microsoft 365 组](#apply-sensitivity-labels-to-microsoft-365-groups)
- [Microsoft Teams 团队网站](#apply-a-sensitivity-label-to-a-new-team)
- [Outlook 网页版中的 Microsoft 365 组](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [SharePoint 网站](#apply-a-sensitivity-label-to-a-new-site)

如果需要[将敏感度标签应用于多个网站](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites)，则可以使用 PowerShell。

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a>将敏感度标签应用于 Microsoft 365 组

You're now ready to apply the sensitivity label or labels to Microsoft 365 groups. Return to the Azure AD documentation for instructions:

- [在 Azure 门户中为新组分配标签](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

- [为 Azure 门户中的现有组分配标签](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- [从 Azure 门户中的现有组中删除标签](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)。

### <a name="apply-a-sensitivity-label-to-a-new-team"></a>为新团队应用敏感度标签

Users can select sensitivity labels when they create new teams in Microsoft Teams. When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration. Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.

[了解有关 Teams 的敏感度标签的详细信息](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![创建新团队时使用的隐私设置](../media/privacy-setting-new-team.png)

创建团队后，敏感度标签将显示在所有频道的右上角。

![敏感度标签将显示在团队上](../media/privacy-setting-teams.png)

该服务会自动将相同的敏感度标签应用于 Microsoft 365 组和连接的 SharePoint 团队网站。

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>应用敏感度标签至 Outlook 网页版的新组

在 Outlook 网页版中，创建新组时可选择或更改已发布的标签的“**敏感度**”选项：

![创建组并选择“敏感度”下的选项](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a>为新网站应用敏感度标签

管理员和最终用户可以在[创建新式团队网站和通信网站时](/sharepoint/create-site-collection)选择敏感度标签，并展开“高级设置”****：

![创建网站并在“敏感度”下选择一个选项](../media/sensitivity-label-new-communication-site.png)

下拉列表框显示选择的标签名称，帮助图标显示所有标签名称及其工具提示，这可帮助用户确定要应用的正确标签。

When the label is applied, and users browse to the site, they see the name of the label and applied policies. For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:

![已应用敏感度标签的网站](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a>使用 PowerShell 将敏感度标签应用于多个网站

You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites. The sites can be any SharePoint site collection, or a OneDrive site.

请确保你拥有 SharePoint Online 命令行管理程序的 16.0.19418.12000 或更高版本。

1. 使用“**以管理员身份运行**”选项打开 PowerShell 会话。

2. 如果你不知道标签 GUID：[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)，获取敏感度标签及其 GUID 的列表。

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. Now [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable. For example:

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. Create a new variable that identifies multiple sites that have an identifying string in common in their URL. For example:

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. Run the following command to apply the label to these sites. Using our examples:

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

若要为不同的网站应用不同的标签，请为每个网站重复以下命令：`Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>在 SharePoint 管理中心中查看和管理敏感度标签

To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center. You might need to first add the **Sensitivity** column:

![“活动网站”页面上的“敏感度”列](../media/manage-site-sensitivity-labels.png)

有关从“活动网站”页面管理网站（包括如何添加列）的详细信息，请参阅[管理新 SharePoint 管理中心中的网站](/sharepoint/manage-sites-in-new-admin-center)。

你也可以从此页面更改和应用标签：

1. 单击网站名称以打开“详细信息”窗格。

2. 选择“**策略**”选项卡，然后为“**敏感度**”设置选择“**编辑**”。

3. 从“**编辑敏感度设置**”窗格中，选择要应用于该网站的敏感度标签，然后选择“**保存**”。

## <a name="support-for-sensitivity-labels"></a>敏感度标签支持

以下应用和服务支持为网站和组设置配置的敏感度标签：

- 管理中心：

  - SharePoint 管理中心
  - Azure Active Directory 高级版
  - Microsoft 365 合规中心、Microsoft 365 安全中心、安全与合规中心

- 用户应用和服务：

  - SharePoint
  - Teams
  - Outlook 网页版以及 Windows、MacOS、iOS 和 Android 版 Outlook
  - Forms
  - Stream

以下应用和服务目前不支持为网站和组设置配置的敏感度标签：

- 管理中心：

  - Microsoft 365 管理中心
  - Teams 管理中心
  - Exchange 管理中心

- 用户应用和服务：

  - Dynamics 365
  - Yammer
  - Planner
  - Project
  - Power BI

## <a name="classic-azure-ad-group-classification"></a>经典 Azure AD 组分类

Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers. However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.

有关如何使用 SharePoint 的旧组分类的示例，请参阅 [SharePoint “新式”网站分类](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。

These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting. If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):

```powershell
($setting["ClassificationList"])
```

若要将旧分类转换为敏感度标签，请执行下列操作之一：

- 使用现有标签：通过编辑已发布的现有敏感度标签，指定你希望网站和组使用的标签设置。

- 创建新标签：通过创建和发布与你的现有分类名称相同的新的敏感度标签，指定你希望网站和组使用的标签设置。

则：

1. Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping. See the next section for instructions.

2. 删除现有组和网站中的旧分类。

虽然无法阻止用户在尚不支持敏感度标签的应用和服务中创建新组，但可运行定期 PowerShell 标签来查看用户已使用旧分类创建的新组，并转换这些分类以使用敏感度标签。

为了帮助管理网站和组的敏感度标签与 Azure AD 分类的共存，请参阅[适用于 Microsoft 365 组的 Azure Active Directory 分类和敏感度标签](migrate-aad-classification-sensitivity-labels.md)。

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a>使用 PowerShell 将 Microsoft 365 组的分类转换为敏感度标签

1. 首先，[连接到安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

   例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录：

2. 通过运行 [ Get-Label ](https://docs.microsoft.com/powershell/module/exchange/get-label) cmdlet 获取敏感度标签及 GUID 列表：

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. 记下你想要应用到 Microsoft 365 组的敏感度标签的 Guid。

4. 现在，在单独的 Windows PowerShell 窗口中[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

5. 以下列命令为例，获取当前具有“常规”分类的组列表：

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. For each group, add the new sensitivity label GUID. For example:

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. 对剩下的组分类重复步骤 5 和 6。

## <a name="auditing-sensitivity-label-activities"></a>审核敏感度标签活动

> [!IMPORTANT]
> 如果通过仅为保护容器的标签选择“**组和网站**”作用域来使用标签分离，则：由于本部分描述的**检测到文档敏感度不匹配**审核事件和电子邮件，请考虑在为标签设置“**文件和电子邮件**”作用域之前先[对这些标签进行排序](sensitivity-labels.md#label-priority-order-matters)。 

If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked. For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**. Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.

Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator. As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed. For example, delete or move the uploaded document from the site.

It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site. For example, a document labeled **General** is uploaded to a site labeled **Confidential**. In this scenario, an auditing event and email aren't generated.

要搜索此事件的审核日志，请从“**文件和页面活动**”类别中查找“**检测到文档敏感度不匹配**”。

The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site. It also contains a documentation link that explains how users can change the sensitivity label. Currently, these automated emails cannot be disabled or customized.

当有人向网站或组添加敏感度标签或从中删除敏感度标签时，也会审核这些活动，但不会自动生成电子邮件。

All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category. For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).

## <a name="how-to-disable-sensitivity-labels-for-containers"></a>如何禁用容器的敏感度标签

You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.

In addition to making all the settings unavailable for groups and sites when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration. Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**. When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.

这意味着不会强制实施先前应用到容器的网站和组中的任何标签设置，并且容器不再显示标签。

If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again. Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification. For these containers, and any new containers, you can now apply classification values. For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell).

## <a name="additional-resources"></a>其他资源

如需有关[通过 Microsoft Teams、O365 组和 SharePoint Online 网站使用敏感度标签](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380)的信息，请参阅网络研讨会的记录和回答的问题。

This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI. However, the information for this feature is still accurate, with any new capabilities documented on this page.
