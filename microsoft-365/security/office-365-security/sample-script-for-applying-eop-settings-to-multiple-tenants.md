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
ms.openlocfilehash: b18fc71171a93e2a2f415800bcf2b5abd5c5a526
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615860"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="3f9a0-103">将 EOP 设置应用到多个租户的示例脚本</span><span class="sxs-lookup"><span data-stu-id="3f9a0-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3f9a0-104">以下示例脚本允许 Microsoft Exchange Online Protection (EOP) 管理员管理多个租户 (公司) 使用 Exchange Online PowerShell 查看和/或将配置设置应用到租户。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="3f9a0-105">在多个租户上运行脚本或 cmdlet</span><span class="sxs-lookup"><span data-stu-id="3f9a0-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="3f9a0-106">如果还未安装，请 [安装 Exchange Online V2 模块](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="3f9a0-107">使用电子表格应用程序 (例如，Excel) ，创建一个 .csv 文件，其中包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="3f9a0-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="3f9a0-108">UserName 列：用于连接 (的帐户例如， `admin@contoso.onmicrosoft.com`) 。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="3f9a0-109">Cmdlet 列：要运行的 cmdlet 或命令 (例如， `Get-AcceptedDomain` 或 `Get-AcceptedDomain | FT Name`) 。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="3f9a0-110">该文件将如下所示：</span><span class="sxs-lookup"><span data-stu-id="3f9a0-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="3f9a0-111">将 .csv 文件保存到易于查找的位置 (例如，c:\scripts\inputfile.csv) 。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="3f9a0-112">将 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 脚本复制到记事本中，然后将该文件保存到易于查找的位置 (例如，c：\scripts) 。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="3f9a0-113">使用以下语法运行此脚本：</span><span class="sxs-lookup"><span data-stu-id="3f9a0-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="3f9a0-114">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="3f9a0-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="3f9a0-115">每个租户都将登录到，脚本将运行。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="3f9a0-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="3f9a0-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="3f9a0-117">您可能需要修改 `Connect-IPPSSession` 脚本中的行以匹配您的环境。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="3f9a0-118">例如，Office 365 德国需要一个与脚本中的当前值不同的 _ConnectionUri_ 值。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="3f9a0-119">有关详细信息，请参阅连接到 [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3f9a0-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
