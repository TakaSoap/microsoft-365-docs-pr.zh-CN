---
title: 在 Office 365 组中管理来宾访问
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 了解如何将来宾添加到 Office 365 组，查看来宾用户，以及如何使用 PowerShell 控制来宾访问。
ms.openlocfilehash: 3314746e4d12c318eaae8fbfa34c2ed0b4d31aed
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610609"
---
# <a name="manage-guest-access-in-office-365-groups"></a>在 Office 365 组中管理来宾访问

默认情况下，为您的组织启用对 Office 365 组的来宾访问。 管理员可以控制是否允许来宾访问整个组织或单个组的组。

当它打开时，组成员可以通过 Web 上的 Outlook 将来宾用户邀请到 Office 365 组。 邀请将发送给组所有者以供审批。

> [!Note]
> 处于本机模式或[欧盟地区](https://go.microsoft.com/fwlink/?linkid=2107357)的 Yammer 企业网络不支持网络来宾。
> Office 365 连接的 Yammer 组目前不支持来宾访问，但您可以在 Yammer 网络中创建未连接的外部组。 有关说明，请参阅[在 Yammer 中创建和管理外部组](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx)。

### <a name="edit-guest-information"></a>编辑来宾信息

批准后，会将来宾用户添加到目录和组中。

组中的来宾访问通常用作包括 SharePoint 或团队的更广泛方案的一部分。 这些服务具有自己的来宾共享设置。 有关在组、SharePoint 和团队中设置来宾共享的完整说明，请参阅：

- [在网站中与来宾协作](../../solutions/collaborate-in-site.md)
- [在团队中与来宾协作](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>管理组来宾访问

如果要启用或禁用组中的来宾访问，可以在 Microsoft 365 管理中心中执行此操作。

1. 在 "管理中心" 中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务" & "加载项</a>" 页面。

2. 选择 " **Office 365 组**"。
  
3. 在 " **Office 365 组**" 页上，选择是否要让组织外部的用户访问组资源，或允许组所有者将组织外部的人员添加到组中。

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a>从管理中心向 Office 365 组添加来宾

如果来宾已经存在于目录中，则可以从 Microsoft 365 管理中心将其添加到你的组。
  
1. 在 "管理中心" 中，转到 "**组** > **组**" 页面。
  
2. 选择要向其添加来宾的组，然后选择 "**成员**" 选项卡上的 "**查看全部和管理成员**"。 
  
4. 选择 "**添加成员**"，然后选择要添加的来宾的名称。
    
5. 选择“**保存**”。

如果要直接将来宾添加到目录中，可以[在 azure 门户中添加 Azure Active DIRECTORY B2B 协作用户](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。

如果要编辑任何来宾的信息，可以[使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。
  
## <a name="block-guest-users-from-a-specific-group"></a>阻止特定组中的来宾用户

如果要允许来宾访问大多数组，但要阻止来宾访问，则可以使用 Microsoft PowerShell 阻止对各个组的来宾访问。

您必须使用预览版本的[Azure Active Directory PowerShell For Graph （AzureAD）](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （模块名称**AzureADPreview**）更改组级别的来宾访问设置：

- 如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)并按照说明安装公共预览版。

- 如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。

- 如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。

> [!NOTE]
> 您必须具有全局管理员权限才能运行这些命令。 

运行以下脚本，将其* / *更改为要阻止来宾访问的组的名称。

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
    
![显示 "来宾组访问已设置为 false" 的 PowerShell 窗口的屏幕截图。](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>根据其域允许或阻止来宾访问

您可以允许或阻止使用特定域的来宾用户。 例如，如果您的企业（Contoso）与另一个业务（Fabrikam）有合作关系，则可以将 Fabrikam 添加到您的允许列表，以便您的用户可以将这些来宾添加到他们的组中。

有关详细信息，请参阅[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。

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

[在 Microsoft 365 管理中心中管理组成员身份](add-or-remove-members-from-groups.md)
  
[Azure Active Directory 访问审核](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
