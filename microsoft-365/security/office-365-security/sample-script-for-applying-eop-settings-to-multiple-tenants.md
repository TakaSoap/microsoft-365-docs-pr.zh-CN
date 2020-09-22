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
ms.openlocfilehash: 6e33ceb6a9daa88bfefd4ec08ac9f2a9f34a942f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198675"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="7dbd5-103">将 EOP 设置应用到多个租户的示例脚本</span><span class="sxs-lookup"><span data-stu-id="7dbd5-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7dbd5-104">以下示例脚本允许管理多个租户（公司）的 Microsoft Exchange Online Protection (EOP) 管理员使用 Windows PowerShell 将配置设置应用到租户。</span><span class="sxs-lookup"><span data-stu-id="7dbd5-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="7dbd5-105">在多个租户上运行脚本或 cmdlet</span><span class="sxs-lookup"><span data-stu-id="7dbd5-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="7dbd5-106">使用 Excel 等应用程序创建 .csv 文件（例如，c:\scripts\inputfile.csv）：</span><span class="sxs-lookup"><span data-stu-id="7dbd5-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="7dbd5-107">在 .csv 文件中，指定两个列名称：UserName 和 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7dbd5-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="7dbd5-p101">对于 .csv 文件中的每一行，在 UserName 列中添加租户的管理员名称，在 Cmdlet 列中添加对该租户运行的 cmdlet。例如，使用 admin@contoso.com 和 Get-AcceptedDomain。</span><span class="sxs-lookup"><span data-stu-id="7dbd5-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="7dbd5-110">将 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) 脚本复制到记事本中，然后将该文件保存到易于查找的位置 (例如，c：\scripts) 。</span><span class="sxs-lookup"><span data-stu-id="7dbd5-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="7dbd5-111">使用以下语法运行此脚本：</span><span class="sxs-lookup"><span data-stu-id="7dbd5-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="7dbd5-112">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="7dbd5-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="7dbd5-113">每个租户都将登录到，脚本将运行。</span><span class="sxs-lookup"><span data-stu-id="7dbd5-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="7dbd5-114">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="7dbd5-114">RunCmdletOnMultipleTenants.ps1</span></span>

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
