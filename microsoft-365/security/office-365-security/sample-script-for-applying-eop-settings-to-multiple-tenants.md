---
title: EOP 设置的示例脚本 - 多个租户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: 本文将了解如何使用 PowerShell 将配置设置应用到 Microsoft Exchange Online Protection (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203841"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="11e71-103">将 EOP 设置应用到多个租户的示例脚本</span><span class="sxs-lookup"><span data-stu-id="11e71-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="11e71-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="11e71-104">**Applies to**</span></span>
-  [<span data-ttu-id="11e71-105">Exchange Online Protection独立</span><span class="sxs-lookup"><span data-stu-id="11e71-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="11e71-106">以下示例脚本允许管理多个租户的 Microsoft Exchange Online Protection (EOP) 管理员 () 使用 Exchange Online PowerShell 查看和/或将配置设置应用到其租户。</span><span class="sxs-lookup"><span data-stu-id="11e71-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="11e71-107">在多个租户上运行脚本或 cmdlet</span><span class="sxs-lookup"><span data-stu-id="11e71-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="11e71-108">如果尚未安装，请安装[Exchange Online V2 模块](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="11e71-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="11e71-109">使用电子表格应用程序 (例如，Excel) ，创建.csv详细信息的电子表格文件：</span><span class="sxs-lookup"><span data-stu-id="11e71-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="11e71-110">UserName 列：用于连接帐户的帐户 (，例如 `admin@contoso.onmicrosoft.com`) 。</span><span class="sxs-lookup"><span data-stu-id="11e71-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="11e71-111">Cmdlet 列：例如，要运行或 (cmdlet `Get-AcceptedDomain` 或 `Get-AcceptedDomain | FT Name`) 。</span><span class="sxs-lookup"><span data-stu-id="11e71-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="11e71-112">该文件将如下所示：</span><span class="sxs-lookup"><span data-stu-id="11e71-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="11e71-113">将.csv文件保存在易于查找的位置，例如 (，c:\scripts\inputfile.csv) 。</span><span class="sxs-lookup"><span data-stu-id="11e71-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="11e71-114">将RunCmdletOnMultipleTenants.ps1[脚本](#runcmdletonmultipletenantsps1)复制到记事本，然后将文件保存到易于查找的位置 (例如 c：\scripts) 。</span><span class="sxs-lookup"><span data-stu-id="11e71-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="11e71-115">使用以下语法运行此脚本：</span><span class="sxs-lookup"><span data-stu-id="11e71-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="11e71-116">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="11e71-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="11e71-117">每个租户都将登录，并且脚本将运行。</span><span class="sxs-lookup"><span data-stu-id="11e71-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="11e71-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="11e71-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="11e71-119">您可能需要修改脚本 `Connect-IPPSSession` 中的行以匹配您的环境。</span><span class="sxs-lookup"><span data-stu-id="11e71-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="11e71-120">例如，Office 365德国需要与脚本中的当前值不同的 _ConnectionUri_ 值。</span><span class="sxs-lookup"><span data-stu-id="11e71-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="11e71-121">有关详细信息，请参阅 连接 Exchange Online [Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="11e71-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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