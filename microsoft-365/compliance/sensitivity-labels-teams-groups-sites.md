---
title: 将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用
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
ms.openlocfilehash: 0b5c4e8ef3611b417c59f7ac5b36f83a799e3397
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238439"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用

在 [Microsoft 365 合规中心](https://protection.office.com/)中创建敏感度标签后，可将其应用于 Microsoft Teams、Office 365 组和 SharePoint 网站。 可将策略与标签相关联以控制：

- 公用/专用设置
- 来宾访问权限
- 非托管设备的访问

将标签应用于团队或组时，该标签会自动应用于连接的 SharePoint 团队网站，反之亦然。

现在，你还可以为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签。 有关详细信息，请参阅[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>关于 Microsoft Teams、Office 365 组和 SharePoint 网站的公共预览版

Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签将逐步向租户推出，并且在最终发布之前可能会发生更改。

此公共预览版不适用于 Office 365 内容交付网络 (CDN)。

## <a name="overview"></a>概述

发布敏感度标签时，Office 365 中的用户可以访问相同的标签列表。

这些图像显示：

- 从 SharePoint 中创建新团队网站时列表的显示方式

- 在 Word 中查看列表时

例如：

![从 SharePoint 中创建团队网站时使用的敏感度标签](media/sensitivity-label-new-team-site.png)

![Word 桌面应用程序中显示的敏感度标签](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a>启用此预览

必须使用 [Azure Active Directory PowerShell Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)（模块名称 **AzureADPreview**）的预览版才能启用 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签预览：

- 如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)并按照说明安装公共预览版。

- 如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。

- 如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。

现在，你已启用 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签预览：

1. 在 PowerShell 会话中，使用具有全局管理员权限的工作或学校帐户连接到 Azure Active Directory。 例如，运行：
    
    ```powershell
    Connect-AzureAD
    ````
    
    有关完整说明，请参阅[连接到 Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad)。

2. 运行以下命令：
    
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
    > 启用此预览时，Office 365 不再使用新组和 SharePoint 网站的旧分类。 如果使用 [Azure AD 网站分类](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"])，则现有组和网站仍将显示旧分类。 若要显示新分类，请进行转换。 有关如何转换它们的信息，请参阅[如果使用经典 Azure AD 网站分类](#if-you-used-classic-azure-ad-site-classification)。 

3. 在同一 PowerShell 会话中，通过使用拥有全局管理员权限的工作或学校帐户，立即连接到安全与合规中心。 有关说明，请参阅[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

4. 运行以下命令以将标签同步到 Azure AD，以便它们可与 Office 365 组一起使用：
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>创建或编辑敏感度标签时设置网站和组设置

启用预览后，请使用以下步骤创建或编辑敏感度标签。 即使已经定义标签，也必须完成这些步骤，这样才能将新的敏感度标签与网站和组配合使用。 对这些设置所做的更改最长可能需要 24 小时才能同步。

1. 在 Microsoft 365 合规中心，选择“**分类**” > “**敏感度标签**”。

2. 选择“**创建标签**”。 如果你已拥有标签，请跳至下一步。

3. 选择所需选项，然后在“**网站和组设置**”选项卡上选择：
    
    - 专用（公用/专用）：专用意味着只有组织中获批的成员可以查看组中的内容。 组织中的任何其他人均无法查看组中的内容。 [了解更多](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - 来宾访问：控制是否可以将来宾添加到组中。 [了解如何管理 Office 365 组中的来宾访问](/office365/admin/create-groups/manage-guest-access-in-groups)
    - 非托管设备：通过此设置，可阻止或限制未加入混合 AD 或在 Intune 中不兼容的设备访问 SharePoint 内容。 如果选择“非托管设备”，则必须转到 Azure AD 以完成策略设置。 有关信息，请参阅[控制非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)。
    
    ![网站和组设置选项卡](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> 将标签应用于团队、组或网站时，只有网站和组设置会生效。 其他设置（例如加密和内容标记）不适用于团队、组或网站中的所有内容。
> 
> 同样，如果您已创建标签并且未打开网站和组设置，则当用户创建团队、组和网站时，该标签仍可用，但是它将在不应用任何设置的情况下进行分类。

[了解有关发布敏感度标签的详细信息](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a>敏感度标签管理

> [!WARNING]
> 创建、修改和删除用于 Microsoft Teams、Office 365 组和 SharePoint 网站的敏感度标签时，需要与向用户发布标签策略的操作进行仔细协调。 

使用以下指南，避免可能影响所有用户的网站和组的创建错误。

**创建和发布标签：**

创建并发布敏感度标签后，团队、组和网站中的用户最长可能需要 24 小时才能看到该标签。 使用以下步骤为租户中的所有用户发布标签：

1. 创建敏感度标签，并将其仅发布到租户中的几个用户帐户。

2. 等待 24 小时。

3. 等待 24 小时后，使用在步骤 1 中指定的用户帐户之一，创建具有在步骤 1 中创建的标签的团队、Office 365 组或 SharePoint 网站。

4. 如果在步骤 3 的创建操作过程中没有错误，请为租户中的所有用户发布标签。 如果出现错误，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。

**修改和删除已发布的标签：**

如果修改或删除一个或多个标签策略中包含的敏感度标签，则这些操作可能会导致所有团队、组和网站的创建失败。 若要避免这种情况，请使用以下指南：

1. 从包含敏感度标签的所有标签策略中删除该标签。

2. 等待 48 小时。

3. 等待 48 小时后，尝试创建团队、组或网站，并确认标签不再可见。

4. 如果敏感度标签不可见，则现在可以安全地修改或删除该标签。 如果标签仍可见，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。

## <a name="troubleshoot-sensitivity-label-deployment"></a>敏感度标签部署疑难解答

### <a name="labels-not-visible-after-publishing"></a>发布后标签不可见
如果在启用这些设置或修改敏感度标签的说明后创建团队或 Office 365 组时遇到问题，请保存标签，等待几小时，然后再次尝试创建团队或组。 有关信息，请参阅[计划在创建或更改敏感度标签后推出](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label)。

如果仍无法在 SharePoint Online 中看到新的敏感度标签，请与 [Microsoft 支持部门](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)联系。

### <a name="team-group-or-sharepoint-site-creation-errors"></a>团队、组或 SharePoint 网站创建错误
如果在公共预览期间遇到创建错误，则你有两个选择：

- 确保敏感度标签对任何用户都不是强制性的。

- 你可以按照此页面“[启用此预览](#enable-this-preview)”部分中的相同说明，为 Microsoft Teams、Office 365 组和 SharePoint 网站关闭敏感度标签。 但是，若要禁用预览，请搜索行 `$setting["EnableMIPLabels"] = "True"`，并将 **True** 值更改为 **False**。

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>为新团队应用敏感度标签

在 Microsoft Teams 中创建新团队时，用户可以选择敏感度标签。 当他们选择敏感度级别时，隐私设置会根据需要进行更改。 根据为标签选择的来宾访问设置，用户可以或不能将组织外部人员添加到团队中。

[了解有关 Teams 的敏感度标签的详细信息](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![创建新团队时使用的隐私设置](media/privacy-setting-new-team.png)

创建团队后，敏感度标签将显示在所有频道的右上角。

![敏感度标签将显示在团队上](media/privacy-setting-teams.png)

该服务会自动将相同的敏感度标签应用于 Office 365 组和连接的 SharePoint 团队网站。

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>为新组应用敏感度标签

在 Outlook 网页版中，新的“**敏感度**”框包含已发布的标签。 如果用户需要更多信息，则可以单击帮助图标以阅读有关可用标签和关联策略的详细信息。

![创建组并选择“敏感度”下的选项](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>为新网站应用敏感度标签

管理员和最终用户可在创建新式团队网站和通信网站时选择敏感度标签。

[了解如何在新的 SharePoint 管理中心中创建网站](/sharepoint/create-site-collection)

当用户创建新式团队和通信网站时，默认情况下已选择敏感度标签。 用户可以选择帮助图标，以了解有关标签的详细信息。

![创建网站并选择“敏感度”下的选项](media/sensitivity-label-new-communication-site.png)

当用户浏览网站时，可以查看标签的名称和应用的策略。

![已应用敏感度标签的网站](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>在 SharePoint 管理中心中管理敏感度标签

若要查看和编辑标签，请使用新 SharePoint 管理中心中的“活动网站”页面。

![“活动网站”页面上的“敏感度”列](media/manage-site-sensitivity-labels.png)

[了解有关在新 SharePoint 管理中心中管理网站的详细信息](/sharepoint/manage-sites-in-new-admin-center)。

## <a name="change-site-and-group-settings-for-a-label"></a>更改标签的网站和组设置

每当您对标签的网站和组设置进行更改时，您必须运行以下 PowerShell 命令，以便团队、网站和组可以使用新设置。 最佳做法是，在为多个团队、组或网站应用标签后，不要更改标签的网站和组设置。

1. 运行以下命令，连接到 Office 365 安全与合规中心 PowerShell，获取灵敏度标签及其 GUID 的列表。
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. 记下该标签或已更改标签的 GUID。

3. 立即连接到 Exchange Online PowerShell 并运行 Get-UnifiedGroup cmdlet，指定标签 GUID，替代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的示例 GUID： 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. 对于每个组，请重新应用灵敏度标签，指定标签 GUID 来替代 "e48058ea-98e8-4940-8db0-ba1310fd955e" 的 GUID 示例：
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a>支持新的敏感度标签

以下应用和服务支持此预览版中的敏感度标签：

- Microsoft 365 合规中心
- SharePoint
- Outlook 网页版
- Teams
- SharePoint 管理中心
- Azure AD 管理中心

无法使用以下应用和服务创建具有新敏感度标签的 Office 365 组：

- Outlook for Mac
- Outlook Mobile  
- 适用于 Windows 的 Outlook 桌面版
- Forms  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Teams 管理中心  
- Microsoft 365 管理中心  
- Exchange 管理中心

## <a name="if-you-used-classic-azure-ad-site-classification"></a>如果使用经典 Azure AD 网站分类

启用此预览时，Office 365 不再支持新组和 SharePoint 网站的旧分类。 但是，除非进行转换，否则现有组和网站仍会显示旧分类。 旧分类包括可能通过 Azure AD PowerShell 或 PnP 核心库设置的“新式”网站分类，这些分类定义了 `ClassificationList` 设置的值。

例如，在 PowerShell 中：

```powershell
   ($setting["ClassificationList"])
```

有关旧分类方法的详细信息，请参阅 [SharePoint“新式”网站分类](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。

根据当前部署，可通过两种方法将旧分类转换为新分类。

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>如果从未对文件和电子邮件使用敏感度标签（统一的 Microsoft 信息保护标签）

我们建议你：

1. 在 Microsoft 365 合规中心中创建与现有分类名称相同的新敏感度标签。
2. 使用 PowerShell 通过名称映射将新标签应用于现有的 Office 365 组和 SharePoint 网站。
3. 删除旧分类。

支持新敏感度标签的应用和服务将显示它们。 可以创建具有新标签的新网站、组和网站。 用户仍可以通过不支持新标签的应用和服务创建组。 但是，用户不能为这些组应用标签。 使用 PowerShell 为这些组应用新的敏感度标签。

你可以保留旧分类；但是，我们强烈建议使用 PowerShell 将新的敏感度标签应用于这些组。

支持新敏感度标签的应用和服务将使用新标签进行创建。 当用户通过不支持新标签的应用和服务创建组时，他们可以选择分类。

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>如果对文件和电子邮件使用敏感度标签（统一的 Microsoft 信息保护标签）

一旦启用此预览，请在 Microsoft 365 合规中心中转到每个标签，并为网站和组应用所需的策略。 用户将开始看到对网站和组可用的现有标签。

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理程序

应用新标签之前，请确保你正在运行最新的 SharePoint Online 命令行管理程序。 如果你已拥有最新版本，则可继续操作并[使用新的敏感度标签重新标记 Office 365 组](#relabel-office-365-groups-with-new-sensitivity-labels)。

要准备适用于预览版的 SharePoint Online 命令行管理程序：

1. 如果安装的是早期版本的 SharePoint Online 命令行管理程序，请转到“**添加或删除程序**”并卸载“SharePoint Online 命令行管理程序”。

2. 在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

3. 选择语言，然后单击“**下载**”。

4. 在 x64 和 x86.msi 文件之间进行选择。 如果运行 64 位版本的 Windows，请下载 x64 文件；如果运行 32 位版本，请下载 x86 文件。 如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。

5. 下载文件后，运行该文件并按照安装向导中的步骤进行操作。

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>使用新的敏感度标签重新标记 Office 365 组

1. 确保你使用的是最新版本的 SharePoint Online 命令行管理程序。 有关说明，请参阅[在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理程序](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)。

2. 使用在 Office 365 中拥有全局管理员或 SharePoint 管理员权限的工作或学校帐户，连接到 SharePoint Online 命令行管理程序。 若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

3. 运行以下命令以获取敏感度标签及其 GUID 的列表。

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. 记下要覆盖的标签的 GUID。 例如，“常规”标签。

5. 使用以下命令获取具有“常规”分类的组列表。 运行此命令时，将连接到 Exchange Online PowerShell 并运行 Get-UnifiedGroup cmdlet。

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. 对于每个组，添加新的敏感度标签 GUID。

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
