---
title: 使用 PowerShell 管理 Microsoft 365 组
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: 本文将了解如何在 PowerShell 中为 Microsoft 365 组执行常见管理任务。
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911046"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>使用 PowerShell 管理 Microsoft 365 组

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

本文提供了在 Microsoft PowerShell 中为组执行常见管理任务的步骤。 它还列出了组的 PowerShell cmdlet。 有关管理 SharePoint 网站的信息，请参阅使用 PowerShell 管理 [SharePoint Online 网站](/sharepoint/manage-team-and-communication-sites-in-powershell)。

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>链接到 Microsoft 365 组使用指南
<a name="BK_LinkToGuideLines"> </a>

当用户 [在 Outlook 中创建](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)或编辑组时，您可以向用户显示指向您组织的使用准则的链接。 例如，如果需要将特定前缀或后缀添加到组名称中。

使用 Azure Active Directory (Azure AD) PowerShell 将你的用户指向你组织的 Microsoft 365 组使用准则。 查看[用于配置组设置的 Azure Active Directory cmdlet，](/azure/active-directory/enterprise-users/groups-settings-cmdlets)并按照在目录级别创建设置中的步骤定义使用指南超链接。 运行 AAD cmdlet 后，用户在 Outlook 中创建或编辑组时将看到指向你的指南的链接。

![使用使用指南链接创建新组](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![单击"组使用指南"查看组织的 Office 365 组指南](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>允许用户以 Microsoft 365 组发送
<a name="BK_LinkToGuideLines"> </a>

如果要将 Microsoft 365 组启用为"发送方式"，请使用 [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) 和 [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlet 配置此配置。 启用此设置后，Microsoft 365 组用户可以使用 Outlook 或 Outlook 网页版以 Microsoft 365 组发送和答复电子邮件。 用户可以转到组、创建新电子邮件，并将"发送为"字段更改为组的电子邮件地址。

 ([您还可以在 Exchange 管理中心 .) ](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

使用以下脚本，将 替换为要更新的组的别名以及要授予权限的用户 *\<GroupAlias\>* *\<UserAlias\>* 的别名。 [连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 以运行此脚本。

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

执行 cmdlet 后，用户可以通过将组电子邮件地址添加到"自"字段，转到 Outlook 或 Web 上的 Outlook 以作为 **组发送。**

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>为贵组织的 Microsoft 365 组创建分类

你可以创建组织中用户在创建 Microsoft 365 组时可以设置的敏感度标签。 如果要对组进行分类，我们建议使用敏感度标签，而不是以前的组分类功能。 有关使用敏感度标签的信息，请参阅使用敏感度标签保护 [Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)。

> [!IMPORTANT]
> 如果当前正在使用分类标签，则启用敏感度标签后，创建组的用户将不再可以使用分类标签。

您仍可以使用以前的组分类功能。 可以创建组织中用户在创建 Microsoft 365 组时可以设置的分类。 例如，可以允许用户在创建的组上设置"标准"、"机密"和"顶级密码"。 默认情况下不会设置组分类，你需要创建它，以便用户进行设置。 使用 Azure Active Directory PowerShell 将用户指向组织的 Microsoft 365 组使用准则。

请查看用于配置组[设置的 Azure Active Directory cmdlet，](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)并按照在目录级别创建设置中的步骤定义 Microsoft 365 组的分类。

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

若要将说明与每个分类关联，可以使用 settings 属性  *ClassificationDescriptions* 进行定义。

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

其中 Classification 与 ClassificationList 中的字符串匹配。

示例：

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

运行上述 Azure Active Directory cmdlet 设置分类后，如果要为特定组设置分类，请运行 [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet。

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

或者创建一个分类的新组。

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

有关使用 Exchange Online PowerShell[](/powershell/exchange/connect-to-exchange-online-powershell)的更多详细信息，请参阅将[PowerShell](/powershell/exchange/exchange-online-powershell)与 Exchange Online 一同使用和连接到 Exchange Online PowerShell。

启用这些设置后，组所有者将能够从 Outlook 网页版和 Outlook 中的下拉菜单中选择分类，然后从"编辑组" **页保存分类** 。

![选择 Microsoft 365 组分类](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>从全局地址列表中隐藏 Microsoft 365 组。
<a name="BKMK_CreateClassification"> </a>

可以指定 Microsoft 365 组是否显示在全局地址列表中， (GAL) 组织的其他列表中。 例如，如果您具有不希望在地址列表中显示的法律部门组，您可以阻止该组显示在 GAL 中。 运行 Set-Unified Group cmdlet，将组从地址列表中隐藏，如下所示：

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>仅允许内部用户向 Microsoft 365 组发送邮件
<a name="BKMK_CreateClassification"> </a>

如果不希望其他组织的用户向 Microsoft 365 组发送电子邮件，可以更改该组的设置。 它将仅允许内部用户向你的组发送电子邮件。 如果外部用户尝试向该组发送邮件，邮件将被拒绝。

运行 Set-UnifiedGroup cmdlet 以更新此设置，如下所示：

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>向 Microsoft 365 组添加邮件提示
<a name="BKMK_CreateClassification"> </a>

每当发件人尝试向 Microsoft 365 组发送电子邮件时，都可以向用户显示邮件提示。

运行 Set-Unified 组 cmdlet 将邮件提示添加到组：

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

除了邮件提示，还可以设置 MailTipTranslations，它指定邮件提示的其他语言。 假设你想要使用西班牙语翻译，然后运行以下命令：

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>更改显示名称 Microsoft 365 组的成员

The 显示名称 specifies the name of the Microsoft 365 Group. 可以在 Exchange 管理中心或 Microsoft 365 管理中心看到此名称。 可以编辑显示名称组，或显示名称以下命令将组分配给现有 Microsoft 365 Set-UnifiedGroup组：

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>将 Outlook 的 Microsoft 365 组的默认设置更改为公用或专用
<a name="BKMK_CreateClassification"> </a>

默认情况下，Outlook 中的 Microsoft 365 组创建为专用组。 如果你的组织希望默认将 Microsoft 365 组创建为公共组或 (私有) ，请使用以下 PowerShell cmdlet 语法：

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

若要设置为专用：

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

验证设置：

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

若要了解更多信息，请参阅[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)和[Get-OrganizationConfig。](/powershell/module/exchange/get-organizationconfig)

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 组 cmdlet

以下 cmdlet 可用于 Microsoft 365 组。

|**Cmdlet 名称**|**说明**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |使用此 cmdlet 查找现有 Microsoft 365 组，并查看组对象的属性  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |更新特定 Microsoft 365 组的属性  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |创建新的 Microsoft 365 组。 此 cmdlet 提供最少的一组参数。 若要设置扩展属性的值，请使用Set-UnifiedGroup组后使用  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |删除现有 Microsoft 365 组  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |检索 Microsoft 365 组的成员身份和所有者信息  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |向现有 Microsoft 365 组添加成员、所有者和订阅者 <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |从现有 Microsoft 365 组中删除所有者和成员  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |用于查看有关与帐户关联的用户照片的信息。 用户照片存储在 Active Directory 中  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |用于将用户照片与帐户关联。 用户照片存储在 Active Directory 中  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |删除 Microsoft 365 组的照片  <br/> |

## <a name="related-topics"></a>相关主题

[将通讯组列表升级到 Microsoft 365 组](/office365/admin/manage/upgrade-distribution-lists)

[管理可创建 Microsoft 365 组的人员](/office365/admin/create-groups/manage-creation-of-groups)

[管理对 Microsoft 365 组的来宾访问](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[将静态组成员身份更改为 dynamic in](/azure/active-directory/users-groups-roles/groups-change-type)