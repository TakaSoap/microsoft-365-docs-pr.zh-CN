---
title: 使用集中部署 PowerShell cmdlet 管理加载项
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: 使用集中部署 PowerShell cmdlet 来帮助你为Microsoft 365组织部署和管理Office加载项。
ms.openlocfilehash: 9f9a3e36c6e1c76d99d8abb7dc47f97a04541322
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824731"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>使用集中部署 PowerShell cmdlet 管理加载项

作为Microsoft 365全局管理员，可以通过集中部署功能将Office加载项部署到用户， (在[管理中心查看“部署Office加载项](../admin/manage/manage-deployment-of-add-ins.md)”。 除了通过Microsoft 365 管理中心部署Office外接程序，还可以使用 Microsoft PowerShell。 安装[适用于Windows PowerShell的 O365 集中式Add-In部署模块](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment)。

下载模块后，打开常规Windows PowerShell窗口并运行以下 cmdlet：

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```

## <a name="connect-using-your-admin-credentials"></a>使用管理员凭据连接

在使用集中部署 cmdlet 之前，需要登录。

1. 启动 PowerShell。

2. 使用公司管理员凭据连接到 PowerShell。 运行以下 cmdlet。

  ```powershell
  Connect-OrganizationAddInService
  ```

3. 在 **“输入凭据”** 页中，输入Microsoft 365 **用户管理员** 或 **全局管理员** 凭据。 或者，可以直接在 cmdlet 中输入凭据。

    运行以下 cmdlet，将公司管理员凭据指定为 PSCredential 对象。

  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> 有关使用 PowerShell 的详细信息，请[参阅连接使用 PowerShell Microsoft 365](./connect-to-microsoft-365-powershell.md)。

## <a name="upload-an-add-in-manifest"></a>Upload加载项清单

运行 **New-OrganizationAdd-In** cmdlet 从路径上传加载项清单，该清单可以是文件位置或 URL。 以下示例显示了  _ManifestPath_ 参数值的文件位置。

```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

还可以运行 **New-OrganizationAdd-In** cmdlet 上传加载项，并直接使用  _Members_ 参数将其分配给用户或组，如以下示例所示。 使用逗号分隔成员的电子邮件地址。

```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>从 Office 应用商店Upload加载项

运行 **New-OrganizationAddIn** cmdlet 从 Office Store 上传清单。

在以下示例中，**New-OrganizationAddIn** cmdlet 为美国位置和内容市场指定加载项的 AssetId。

```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

若要确定 _AssetId_ 参数的值，可以从加载项的 Office Store 网页的 URL 复制它。 AssetId 始终以“WA”开头，后跟数字。 例如，在前面的示例中，WA104099688 的 AssetId 值的源是加载项的 Office Store 网页 URL： [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688)

_Locale_ 参数和 _ContentMarket_ 参数的值相同，指示您尝试从中安装外接程序的国家/地区。 格式为 en-US、fr-FR。 等等。

> [!NOTE]
> 从 Office Store 上传的加载项将在最新更新在 Office Store 上可用后的几天内自动更新。

## <a name="get-details-of-an-add-in"></a>获取加载项的详细信息

运行 **Get-OrganizationAddIn** cmdlet，如下所示，获取上传到租户的所有加载项的详细信息，包括外接程序的产品 ID。

```powershell
Get-OrganizationAddIn
```

使用 _ProductId_ 参数的值运行 **Get-OrganizationAddIn** cmdlet，以指定要检索其详细信息的加载项。

```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

若要获取所有加载项以及分配的用户和组的完整详细信息，请将 **Get-OrganizationAddIn cmdlet** 的输出传递给Format-List cmdlet，如以下示例所示。

```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>打开或关闭加载项

若要关闭加载项，以便分配给它的用户和组不再具有访问权限，请运行 **Set-OrganizationAddIn cmdlet** ，将  _ProductId_ 参数和  _Enabled_ 参数设置为  `$false`，如以下示例所示。

```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

若要重新打开加载项，请运行与  _Enabled_ 参数设置为  `$true`相同的 cmdlet。

```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>从加载项添加或删除用户

若要将用户和组添加到特定加载项，请使用 _ProductId_、_Add_ 和 _Members_ 参数运行 **Set-OrganizationAddInAssignments** cmdlet。 使用逗号分隔成员的电子邮件地址。

```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

若要删除用户和组，请使用  _Remove_ 参数运行相同的 cmdlet。

```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

若要向租户上的所有用户分配加载项，请使用将值设置为`$true`的 _AssignToEveryone_ 参数运行同一 cmdlet。

```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

若要不向所有人分配外接程序并还原到以前分配的用户和组，可以运行相同的 cmdlet，并通过将其值设置为`$false`_来关闭 AssignToEveryone_ 参数。

```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>更新加载项

若要从清单更新加载项，请使用 _ProductId_、_ManifestPath_ 和 _Locale_ 参数运行 **Set-OrganizationAddIn** cmdlet，如以下示例所示。

```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> 从 Office Store 上传的加载项将在最新更新在 Office Store 上可用后的几天内自动更新。

## <a name="delete-an-add-in"></a>删除加载项

若要删除加载项，请使用 _ProductId_ 参数运行 **Remove-OrganizationAddIn** cmdlet，如以下示例所示。

```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature.

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters:

    - \<
    -  \>
    -  ;
    -  =

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set -OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg"
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg"
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in's icon (in admin center). |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.|
| \<AppDomains> | A list of domains that the add-in can connect with. |
| \<SupportURL>| The URL users can use to access help and support. |
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.|
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>
    <bt:Images>
          <bt:Image id="img16icon" DefaultValue="https://site.com/img.jpg"
    </bt:Images>
</Resources>
```
In this case, the element id for the image is "img16icon" and the value associated with it is "http:<i></i>//site.<i></i>com/img.jpg."

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{"ElementID" = "New Value"; "NextElementID" = "Next New Value"}
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.

```powershell
Get-OrganizationAddInOverrides
```
If ProductId is specified, then a list of overrides applied to that add-in is returned.

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remove an add-in from cache:

1. Navigate to the "Users" folder in C:\
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>获取每个 cmdlet 的详细帮助

可以使用 Get-help cmdlet 查看每个 cmdlet 的详细帮助。 例如，以下 cmdlet 提供了有关Remove-OrganizationAddIn cmdlet 的详细信息。

```powershell
Get-help Remove-OrganizationAddIn -Full
```
