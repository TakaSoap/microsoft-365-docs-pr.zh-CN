---
title: EOP 设置的示例脚本-多租户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解如何使用 PowerShell 将配置设置应用到您在 Microsoft Exchange Online Protection (EOP) 中的租户。
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376563"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>将 EOP 设置应用到多个租户的示例脚本

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


以下示例脚本允许 Microsoft Exchange Online Protection (EOP) 管理员管理多个租户 (公司) 使用 Exchange Online PowerShell 查看和/或将配置设置应用到租户。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>在多个租户上运行脚本或 cmdlet

1. 如果还未安装，请 [安装 Exchange Online V2 模块](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。

2. 使用电子表格应用程序 (例如，Excel) ，创建一个 .csv 文件，其中包含以下详细信息：

   - UserName 列：用于连接 (的帐户例如， `admin@contoso.onmicrosoft.com`) 。
   - Cmdlet 列：要运行的 cmdlet 或命令 (例如， `Get-AcceptedDomain` 或 `Get-AcceptedDomain | FT Name`) 。

   该文件将如下所示：

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. 将 .csv 文件保存到易于查找的位置 (例如，c:\scripts\inputfile.csv) 。

4. 将 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 脚本复制到记事本中，然后将该文件保存到易于查找的位置 (例如，c：\scripts) 。

5. 使用以下语法运行此脚本：

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   下面是一个示例：

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 每个租户都将登录到，脚本将运行。

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> 您可能需要修改 `Connect-IPPSSession` 脚本中的行以匹配您的环境。 例如，Office 365 德国需要一个与脚本中的当前值不同的 _ConnectionUri_ 值。 有关详细信息，请参阅连接到 [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
  
# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
