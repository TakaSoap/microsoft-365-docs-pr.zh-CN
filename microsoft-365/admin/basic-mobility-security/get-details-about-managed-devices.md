---
title: 获取有关基本移动性和安全性托管设备的详细信息
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用Windows PowerShell获取有关组织中基本移动性和安全性设备的详细信息。
ms.openlocfilehash: 4cac15e8377370e4bd2f8b359a39aaf830f13d10
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781064"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>获取有关基本移动性和安全性托管设备的详细信息

本文介绍如何使用Windows PowerShell获取组织中为基本移动性和安全性设置的设备的详细信息。

下面是可供你使用的设备详细信息的细目。

|详情|在 PowerShell 中查找的内容|
|---|---|
|设备已注册到基本移动性和安全性。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device.md)|*isManaged* 参数的值为：<br/>**已注册 True**= 设备。<br/>未注册 **False**= 设备。|
|设备符合设备安全策略。 有关详细信息，请参阅 [“创建设备安全策略”](create-device-security-policies.md)|*isCompliant* 参数的值为：<br/>**True** = 设备符合策略。<br/>**False** = 设备不符合策略。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本移动性和安全性 PowerShell 参数。":::

> [!NOTE]
> 本文中的命令和脚本还返回有关由[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)管理的任何设备的详细信息。

## <a name="before-you-begin"></a>准备工作

若要运行本文中所述的命令和脚本，需要设置一些内容。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>步骤 1：下载并安装用于Windows PowerShell的Azure Active Directory模块

有关这些步骤的详细信息，请参阅[连接使用 PowerShell Microsoft 365](/office365/enterprise/powershell/connect-to-office-365-powershell)。

1. 转到 [Microsoft Online Services Sign-In IT 专业人员的助手 RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) ，然后选择 **“下载 Microsoft Online Services 登录助手**”。

2. 安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，具体步骤如下：

    1. 打开管理员级 PowerShell 命令提示符。

    2. 运行 `Install-Module MSOnline` 命令。

    3. 如果系统提示安装 NuGet 提供程序，请键入 Y，然后按 Enter 键。

    4. 如果系统提示从 PSGallery 安装模块，请键入 Y，然后按 Enter 键。

    5. 安装完成后，关闭 PowerShell 命令窗口。

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>步骤 2：连接到Microsoft 365订阅

1. 在Windows PowerShell Windows Azure Active Directory模块中，运行以下命令。

   ```powershell
   $UserCredential = Get-Credential
   ```

2. 在“Windows PowerShell凭据请求”对话框中，键入Microsoft 365全局管理员帐户的用户名和密码，然后选择 **“确定**”。

3. 运行以下命令：

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>步骤 3：确保能够运行 PowerShell 脚本

> [!NOTE]
> 如果已设置为运行 PowerShell 脚本，则可以跳过此步骤。

若要运行Get-MsolUserDeviceComplianceStatus.ps1脚本，需要启用 PowerShell 脚本的运行。

1. 在Windows桌面中，选择 **“开始**”，然后键入Windows PowerShell。 右键单击Windows PowerShell，然后选择 **“以管理员身份运行**”。

2. 运行以下命令：

   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

3. 出现提示时，键入 Y，然后按 Enter。

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>运行Get-MsolDevice cmdlet 以显示组织中所有设备的详细信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。

2. 运行以下命令：

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

有关更多示例，请参阅 [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)。

## <a name="run-a-script-to-get-device-details"></a>运行脚本以获取设备详细信息

首先，将脚本保存到计算机。

1. 将以下文本复制并粘贴到记事本。

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. 使用文件扩展名.ps1将其另存为Windows PowerShell脚本文件;例如，Get-MsolUserDeviceComplianceStatus.ps1。

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>运行脚本以获取单个用户帐户的设备信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。

2. 转到保存脚本的文件夹。 例如，如果将其保存到 C：\PS-Scripts，请运行以下命令。

   ```powershell
   cd C:\PS-Scripts
   ```

3. 运行以下命令以标识要获取其设备详细信息的用户。 本示例获取有关 bar@example.com 的详细信息。

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. 运行以下命令以启动脚本。

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

信息将作为 CSV 文件导出到Windows桌面。 可以使用其他参数来指定 CSV 的文件名和路径。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>运行脚本以获取一组用户的设备信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。

2. 转到保存脚本的文件夹。 例如，如果将其保存到 C：\PS-Scripts，请运行以下命令。

   ```powershell
   cd C:\PS-Scripts
   ```

3. 运行以下命令以标识要获取其设备详细信息的组。 本示例获取 FinanceStaff 组中用户的详细信息。

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. 运行以下命令以启动脚本。

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

信息将作为 CSV 文件导出到Windows桌面。 可以使用其他参数来指定 CSV 的文件名和路径。

## <a name="related-topics"></a>相关主题

[Microsoft 连接已停用](/collaborate/connect-redirect)

[基本移动性和安全性概览](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
