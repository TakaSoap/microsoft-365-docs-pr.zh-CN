---
title: 阻止将来宾用户添加到特定组
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 了解如何阻止将来宾用户添加到特定组
ms.openlocfilehash: 91c7560186fb0b954075e9ff9c997b34121951cd
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651346"
---
# <a name="prevent-guest-users-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>阻止将来宾用户添加到特定 Microsoft 365 组或 Microsoft 团队团队

如果要允许来宾访问大多数组和团队，但要阻止来宾访问，则可以阻止对各个组和团队的来宾访问。  (阻止来宾对团队的访问权限是通过阻止对关联组的来宾访问来完成的。 ) 这将阻止添加新的来宾，但不会删除组或团队中已有的来宾。

如果您在组织中使用敏感度标签，我们建议使用它们来控制每组的来宾访问。 有关如何执行此操作的信息，请 [使用敏感度标签来保护 Microsoft 团队、microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。 这是建议的方法。

## <a name="change-group-settings-using-microsoft-powershell"></a>使用 Microsoft PowerShell 更改组设置

您还可以通过使用 PowerShell 阻止向单个组添加新的来宾。

必须使用预览版本的 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module name **AzureADPreview**) 更改组级别的来宾访问设置：

- 如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)并按照说明安装公共预览版。

- 如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。

- 如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。

> [!NOTE]
> 您必须具有全局管理员权限才能运行这些命令。 

运行以下脚本， */<GroupName/>* 将其更改为要阻止来宾访问的组的名称。

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

若要验证设置，请运行以下命令：

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

验证如下所示：
    
![显示 "来宾组访问已设置为 false" 的 PowerShell 窗口的屏幕截图。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>根据其域允许或阻止来宾访问

您可以允许或阻止使用特定域的来宾用户。 例如，如果您的企业 (Contoso) 与另一个业务 (Fabrikam) 有合作关系，则可以将 Fabrikam 添加到您的允许列表，以便您的用户可以将这些来宾添加到他们的组中。

有关详细信息，请参阅 [允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。

## <a name="add-guests-to-the-global-address-list"></a>将来宾添加到全局地址列表

默认情况下，来宾在 Exchange 全局地址列表中不可见。 使用下面列出的步骤使来宾在全局地址列表中可见。

通过运行以下命令查找来宾用户的 ObjectID：

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

然后，使用适用于 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的值运行以下各项。

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>相关文章

[在 Microsoft 365 管理中心中管理组成员身份](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Azure Active Directory 访问审核](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
