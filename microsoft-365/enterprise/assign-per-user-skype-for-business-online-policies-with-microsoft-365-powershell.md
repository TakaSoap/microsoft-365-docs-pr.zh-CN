---
title: 使用 PowerShell 为用户分配Skype for Business Online 策略Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 摘要：使用 PowerShell Microsoft 365 Online 策略分配每用户Skype for Business设置。
ms.openlocfilehash: c49d465ffe0a6f1379681be0ae4faaf9982b6ef0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178943"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>使用 PowerShell 为用户分配Skype for Business Online 策略Microsoft 365

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

使用 PowerShell for Microsoft 365是使用联机策略分配每用户通信Skype for Business一种有效方法。
  
## <a name="prepare-to-run-the-powershell-commands"></a>准备运行 PowerShell 命令

使用这些说明进行设置，以运行命令 (跳过已完成) ：
  
  > [!Note]
   > Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。

1. 安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 开启 Windows PowerShell 命令提示符并运行以下命令： 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   系统提示时，输入 Skype for Business Online 管理员帐户名称和密码。
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>更新用户帐户的外部通信设置

假设您要更改用户帐户的外部通信设置。 例如，您希望允许 Alex 与联盟用户进行通信 (EnableFederationAccess 等于 True) 但不与 Windows Live 用户 (EnablePublicCloudAccess 等于 False) 。 为此，您需要执行两项操作：
  
1. 找到符合我们的条件的外部访问策略。
    
2. 将该外部访问策略分配给 Alex。
    
如何确定要分配 Alex 的外部访问策略？ 以下命令返回在 EnableFederationAccess 设置为 True 且 EnablePublicCloudAccess 设置为 False 时的所有外部访问策略：
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

除非已创建 ExternalAccessPolicy 的任何自定义实例，否则该命令将返回一个符合 FederationOnly (条件) 。 下面是一个示例：
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

现在，你已了解要分配给 Alex 的策略，可以使用 [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet 分配该策略。 下面是一个示例：
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

分配策略非常简单：只需指定用户的标识和要分配的策略的名称。 
  
对于策略和策略分配，不限于一次使用一个用户帐户。 例如，假设您需要获得可与联盟伙伴和 Windows Live 用户通信的所有用户的列表。 我们已经知道，这些用户已分配有外部用户访问策略 FederationAndPICDefault。 因为我们知道，您可以通过运行一个简单的命令来显示所有这些用户的列表。 命令如下：
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

换句话说，向我们显示 ExternalAccessPolicy 属性设置为 FederationAndPICDefault 的所有用户。  (并且，为了限制屏幕上显示的信息量，请使用 Select-Object cmdlet 向我们仅显示每个用户的 显示名称.)  
  
若要配置所有用户帐户以使用同一策略，请使用此命令：
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

此命令使用 Get-CsOnlineUser 返回已启用 Lync 的所有用户的集合，然后将所有这些信息发送给 Grant-CsExternalAccessPolicy，该策略将 FederationAndPICDefault 策略分配给集合中的每个用户。
  
再如，假设你之前为 Alex 分配了 FederationAndPICDefault 策略，但现在改变了主意，希望他由全局外部访问策略进行管理。 无法将全局策略显式分配给任何人。 如果没有为给定用户分配每用户策略，则全局策略将用于该用户。 因此，如果我们希望 Alex 由全局策略管理，则需要取消分配之前分配给他的任何每用户策略。 下面是一个示例命令：
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

此命令将分配给 Alex 的外部访问策略的名称设置为空值 ($Null) 。 Null 表示"nothing"。 换句话说，没有向 Alex 分配外部访问策略。 未向用户分配外部访问策略时，该用户随后会由全局策略管理。

## <a name="managing-large-numbers-of-users"></a>管理大量用户

若要管理 1000 (或 1000) 用户，您需要使用 [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet 通过脚本块对命令进行批处理。  在之前的示例中，每次执行 cmdlet 时，它必须设置调用，然后等待结果，然后再发送回。  使用脚本块时，这允许远程执行 cmdlet，一旦完成，将数据发送回。

```powershell
$s = Get-PSSession | Where-Object { ($.ComputerName -like '*.online.lync.com' -or $.Computername -eq 'api.interfaces.records.teams.microsoft.com') -and $.State -eq 'Opened' -and $.Availability -eq 'Available' }

$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

这将一次查找 500 个没有客户端策略的用户。 它将授予他们客户端策略"ClientPolicyNoIMURL"和外部访问策略"FederationAndPicDefault"。 结果分为 50 个组，然后每批 50 个发送到远程计算机。
  
## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
