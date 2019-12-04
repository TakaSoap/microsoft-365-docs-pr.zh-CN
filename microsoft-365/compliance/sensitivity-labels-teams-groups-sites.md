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
ms.openlocfilehash: a6c187227703395ed5fe3d926dabe30e6203fca5
ms.sourcegitcommit: 909f18d6c497086899fa239b5b5e0bb91f1e7804
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819128"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用

在[microsoft 365 合规性中心](https://protection.office.com/)创建敏感度标签时，现在可以将其应用于 microsoft 团队、Office 365 组和 SharePoint 网站。 您可以将策略与要控制的标签相关联：

- 公共/专用设置
- 来宾访问
- 来自非托管设备的访问

将标签应用于团队或组时，标签将自动应用于连接的 SharePoint 团队网站和其他方法。

现在，您还可以在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签。 [了解详细信息](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>关于 Microsoft 团队、Office 365 组和 SharePoint 网站的公共预览版

Microsoft 团队、Office 365 组和 SharePoint 网站的敏感度标签将逐步推出到租户，并且在最终发布之前可能会发生更改。

公共预览版不适用于 Office 365 内容传递网络（Cdn）。

## <a name="overview"></a>概述

发布敏感度标签时，跨 Office 365 的用户可以访问相同的标签列表。

这些图像显示：

- 从 SharePoint 创建新的团队网站时列表的显示方式

- 在 Word 中查看列表时

![从 SharePoint 创建团队网站时的敏感度标签](media/sensitivity-label-new-team-site.png)

![在 Word 桌面应用程序中显示的敏感度标签](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a>使用 Azure PowerShell 启用此预览

1. 使用 Azure PowerShell 以全局管理员身份登录 Azure。 有关说明，请参阅[使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。

2. 运行以下命令：

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

如果启用此预览，Office 365 将不再使用新组和 SharePoint 网站的旧分类。 如果使用的是[AZURE AD 网站分类](/sharepoint/dev/solution-guidance/modern-experience-site-classification)（$setting ["ClassificationList"]），则现有组和网站仍将显示旧的分类。 若要显示新的分类，请对其进行转换。 有关如何转换它们的信息，请参阅[如果您使用的是经典 AZURE AD 网站分类](#if-you-used-classic-azure-ad-site-classification)。 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>创建或编辑敏感度标签时设置网站和组设置

启用预览后，请按照以下步骤创建或编辑敏感度标签。 您必须完成这些步骤，才能使用网站和组，即使您已定义标签也是如此。 对这些设置所做的更改可能需要长达24小时的同步。

1. 在 Microsoft 365 合规性中心中，选择 "**分类** > **敏感度标签**"。

2. 选择 "**创建标签**"。 如果您已经有一个标签，请跳至下一步。

3. 选择所需的选项，然后在 "**网站和组设置**" 选项卡上选择：

    - 隐私（公用/专用）：私有表示组织中的已批准成员只能查看组内的内容。 组织中的任何其他人都无法查看组中的内容。 [了解更多](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - 来宾访问：您可以控制来宾是否可以添加到组中。 [了解如何在 Office 365 组中管理来宾访问](/office365/admin/create-groups/manage-guest-access-in-groups)
    - 非托管设备：此设置允许您阻止或限制从 Intune 中未加入混合广告或合规性的设备访问 SharePoint 内容。 如果选择非托管设备，则需要转到 Azure AD 以完成策略设置。 有关信息，请参阅[控制来自非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)。

!["网站和组设置" 选项卡](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> 将标签应用于团队、组或网站时，只有网站和组设置才会生效。 其他设置（如加密和内容标记）不适用于团队、组或网站中的所有内容。 同样，如果您创建一个标签但不启用网站和组设置，则在用户创建团队、组和网站时，该标签仍可用，但在用户应用它时，将不会执行任何操作。

[了解如何发布敏感度标签](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a>敏感度标签部署疑难解答

如果您在启用这些设置或对标签的说明进行了更改后遇到问题，请保存标签，等待几小时，然后再次尝试创建团队或 Office 365 组，以确保在您创建团队或 Office 365 组时遇到问题。

如果你仍然无法看到 SharePoint Online 中的新敏感度标签，请立即联系 Microsoft 支持部门。

[了解如何发布敏感度标签](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>将敏感度标签应用于新团队

当用户在 Microsoft 团队中创建新团队时，用户可以选择敏感度标签。 当用户选择敏感度级别时，将根据需要更改隐私设置。 根据为标签选择的来宾访问设置，用户可以或不能将组织外部的人员添加到团队中。

![创建新团队时的隐私设置](media/privacy-setting-new-team.png)

创建团队后，敏感度标签将显示在所有频道的右上角。

![敏感度标签显示在团队中](media/privacy-setting-teams.png)

该服务自动将相同的敏感度标签应用于 Office 365 组和连接的 SharePoint 团队网站。

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>将敏感度标签应用于新组

在 web 上的 Outlook 中，新的 "**敏感度**" 框中包含已发布标签。 如果用户需要更多的信息，可以单击 "帮助" 图标阅读有关可用标签和相关策略的详细信息。

![创建组并选择 "敏感度" 下的选项](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>将敏感度标签应用于新网站

管理员和最终用户可以在创建新式工作组网站和通信网站时选择敏感度标签。

[了解如何在新的 SharePoint 管理中心中创建网站](/sharepoint/create-site-collection)

当用户创建新式团队和通信网站时，默认情况下已选择一个敏感度标签。 用户可以选择 "帮助" 图标以了解有关标签的详细信息。

![创建网站并在 "敏感度" 下选择一个选项](media/sensitivity-label-new-communication-site.png)

当用户浏览到网站时，他们可以看到标签的名称和应用的策略。

![应用了灵敏度标签的网站](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>在 SharePoint 管理中心中管理敏感度标签

若要查看和编辑标签，请使用新 SharePoint 管理中心中的 "活动网站" 页。

!["活动网站" 页上的 "敏感度" 列](media/manage-site-sensitivity-labels.png)

[了解有关在新 SharePoint 管理中心中管理网站的详细信息](/sharepoint/manage-sites-in-new-admin-center)。

## <a name="change-site-and-group-settings-for-a-label"></a>更改标签的网站和组设置

最佳做法是，在将标签应用于多个团队、组或网站后，不要更改设置。 如果必须进行更改，则需要使用 Azure AD PowerShell 脚本手动应用更新。 此方法可确保所有现有团队、网站和组强制实施新设置。

## <a name="support-for-the-new-sensitivity-labels"></a>支持新的敏感度标签

以下应用和服务支持此预览中的敏感度标签：

- Microsoft 365 合规中心
- SharePoint
- Outlook 网页版
- Teams
- SharePoint 管理中心
- Azure AD 管理中心

您不能使用以下应用和服务创建具有新敏感度标签的 Office 365 组：

- Outlook for Mac
- Outlook mobile  
- 适用于 Windows 的 Outlook 桌面
- Forms  
- Dynamics 365  
- Yammer  
- Stream  
- 规划器  
- Project  
- PowerBI  
- 团队管理员中心  
- Microsoft 365 管理中心  
- Exchange 管理中心

## <a name="if-you-used-classic-azure-ad-site-classification"></a>如果你使用的是经典 Azure AD 网站分类

如果启用此预览，Office 365 将不再支持新组和 SharePoint 网站的旧分类。 但是，除非您转换现有的组和网站，否则它们仍会显示旧的分类。 旧分类包括您设置的 "新式" 网站分类，可能通过 Azure AD PowerShell 或 PnP 核心库（定义了`ClassificationList`设置的值）。

例如，在 PowerShell 中：

```powershell
   ($setting["ClassificationList"])
```

有关旧分类方法的详细信息，请参阅[SharePoint "新式" 网站分类](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification)。

根据您的当前部署，您可以通过两种方法将旧分类转换为新的分类。

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>如果您从未对文件和电子邮件使用敏感度标签（统一 Microsoft 信息保护标签）

我们建议您：

1. 在 Microsoft 365 合规性中心创建与现有分类名称相同的新敏感度标签。
2. 使用 PowerShell 将新标签应用于现有的 Office 365 组和 SharePoint 网站（使用名称映射）。
3. 删除旧的分类。

支持新敏感度标签的应用和服务将显示它们。 您可以使用新标签创建新的团队、组和网站。 用户仍可以从不支持新标签的应用和服务创建组。 但是，用户不能将标签应用于这些组。 使用 PowerShell 将新的敏感度标签应用于这些组。

您可以保留旧的分类;但是，强烈建议使用 PowerShell 将新的敏感度标签应用于这些组。

支持新的敏感度标签的应用和服务将使用新标签创建。 当用户从不支持新标签的应用和服务创建组时，他们可以选择一种分类。

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>如果对文件和电子邮件使用敏感度标签（统一 Microsoft 信息保护标签）

一旦启用此预览，请立即转到 Microsoft 365 合规中心中的每个标签，并对网站和组应用所需的策略。 用户将开始查看可用于网站和组的现有标签。

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理程序

在应用新标签之前，请确保您运行的是最新的 SharePoint Online 命令行管理程序。 如果已有最新版本，可以继续[使用新的灵敏度标签重新标记 Office 365 组](#relabel-office-365-groups-with-new-sensitivity-labels)。

为预览准备 SharePoint Online 命令行管理程序：

1. 如果已安装早期版本的 SharePoint Online 命令行管理程序，请转到 "**添加或删除程序**"，并卸载 "SharePoint Online 命令行管理程序"。

2. 在 web 浏览器中，转到 "下载中心" 页面并[下载最新的 SharePoint Online 命令行管理](https://go.microsoft.com/fwlink/p/?LinkId=255251)程序。

3. 选择您的语言，然后单击 "**下载**"。

4. 在 x64 和 x86 .msi 文件之间进行选择。 如果运行的是64位版本的 Windows 或 x86 文件（如果运行的是32位版本），请下载 x64 文件。 如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。

5. 下载文件后，运行文件并按照安装向导中的步骤操作。

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>使用新的灵敏度标签重新标记 Office 365 组

1. 确保您使用的是最新版本的 SharePoint Online 命令行管理程序。 有关说明，请参阅[在重新标记 Office 365 组之前准备 SharePoint Online 命令行管理](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups)程序。

2. 在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户，连接到 SharePoint Online 命令行管理程序。 若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

3. 运行以下命令以获取灵敏度标签及其 Guid 的列表。

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. 记下要覆盖的标签的 GUID。 例如，"常规" 标签。

5. 使用以下命令可获取具有 "常规" 分类的组列表。 运行此命令时，您将连接到 Exchange Online PowerShell 并运行 Remove-unifiedgroup cmdlet。

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. 对于每个组，添加新的敏感度标签 GUID。

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
