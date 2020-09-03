---
title: 获取有关基本移动和安全托管设备的详细信息
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用 Windows PowerShell 获取有关您组织中的基本移动性和安全设备的详细信息。
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336737"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>获取有关基本移动和安全托管设备的详细信息

本文介绍如何使用 Windows PowerShell 获取有关您组织中为实现基本移动性和安全性而设置的设备的详细信息。

以下是对你可用的设备详细信息的细目。

|**详细信息**|**要在 PowerShell 中查找的内容**|
|:----------------|:------------------------------------------------------------------------------|
|设备已在基本移动性和安全性中注册。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)|IsManaged 参数的值 *isManaged*   为：<br/>**True**= 设备已注册。<br/>**False**= 设备未注册。 |
|设备符合你的设备安全策略。 有关详细信息，请参阅 [创建设备安全策略](create-device-security-policies-in-basic-mmobility-and-security.md)|IsCompliant 参数的值 *isCompliant*   为：<br/>**True**  = 设备符合策略。<br/>**False**  = 设备不符合策略。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本移动性和安全性 PowerShell 参数":::

>[!NOTE]
>本文中的命令和脚本还返回有关由 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)管理的任何设备的详细信息。

## <a name="before-you-begin"></a>准备工作

您需要设置一些内容，以运行本文中所述的命令和脚本。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>步骤1：下载并安装适用于 Windows PowerShell 的 Azure Active Directory 模块

有关这些步骤的详细信息，请参阅 [Connect To Microsoft 365 With PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。

1. 转到 [适用于 IT 专业人员的 Microsoft Online Services 登录助手 RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   并选择 **"下载 Microsoft online services 登录助手"**。   

2. 安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，具体步骤如下：   

    1. 打开管理员级 PowerShell 命令提示符。  

    2. 运行 Install-Module MSOnline 命令。
    
    3. 如果系统提示安装 NuGet 提供程序，请键入 Y，然后按 Enter 键。   

    4. 如果系统提示从 PSGallery 安装模块，请键入 Y，然后按 Enter 键。   

    5. 安装完成后，关闭 PowerShell 命令窗口。
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>步骤2：连接到 Microsoft 365 订阅

1. 在 windows PowerShell 的 Windows Azure Active Directory 模块中，运行以下命令。  

    $UserCredential = Get-Credential

2. 在 "Windows PowerShell 凭据请求" 对话框中，键入 Microsoft 365 全局管理员帐户的用户名和密码，然后选择 **"确定"**。
    
3. 运行以下命令。
    
    Connect-msolservice-Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>步骤3：确保你能够运行 PowerShell 脚本

>[!NOTE]
>如果您已经设置了运行 PowerShell 脚本，则可以跳过此步骤。

若要运行 Get-MsolUserDeviceComplianceStatus.ps1 脚本，需要启用 PowerShell 脚本的运行。

1. 在 Windows 桌面上，选择 " **开始**"，然后键入 Windows PowerShell。 右键单击 "Windows PowerShell"，然后选择 " **以管理员身份运行**"。

2. 运行以下命令。
    
    Set-ExecutionPolicy RemoteSigned

3. 出现提示时，键入 Y，然后按 Enter。
    
**运行 MsolDevice cmdlet 以显示组织中所有设备的详细信息**

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。  

2. 运行以下命令。
    
    MsolDevice-ReturnRegisteredOwners |其中-对象 {$ _。RegisteredOwners-gt 0}

有关更多示例，请参阅  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)。

## <a name="run-a-script-to-get-device-details"></a>运行脚本以获取设备详细信息

首先，将脚本保存到您的计算机。

1. 将以下文本复制并粘贴到记事本中。  

2.  param (
    

3.  [PSObject []] $users = @ ( # A1，
    

4.  [Switch] $export，
    

5.  [String] $exportFileName = "UserDeviceComplianceStatus_" + (获取日期格式 "yyMMdd_HHMMss" ) + ".csv"，
    

6.  [String] $exportPath = [环境]：： GetFolderPath ( "桌面" ) 
    

7.  )
    

9.  [System.object] $script： schema = @ {
    

11.  DeviceId = ' '
    

12.  DeviceOSType = ' '
    

13.  DeviceOSVersion = ' '
    

14.  DeviceTrustLevel = ' '
    

15.  DisplayName = ' '
    

16.  IsCompliant = ' '
    

17.  IsManaged = ' '
    

18.  ApproximateLastLogonTimestamp = ' '
    

19.  DeviceObjectId = ' '
    

20.  RegisteredOwnerUpn = ' '
    

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  函数 createResultObject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object-TypeName PSObject-Property $script： schema
    

30.  返回 $resultObject
    

31.  }
    

33.  如果 ($users。Count-eq 0) 
    

34.  {
    

35.  $users = Get-msoluser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u in $users) 
    

39.  {
    

41.  [PSObject] $devices = msoldevice-RegisteredOwnerUpn $u
    

42.  foreach ($d $devices) 
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult DeviceId = $d DeviceId
    

46.  $deviceResult DeviceOSType = $d。 DeviceOSType
    

47.  $deviceResult DeviceOSVersion = $d。 DeviceOSVersion
    

48.  $deviceResult DeviceTrustLevel = $d。 DeviceTrustLevel
    

49.  $deviceResult DisplayName = $d DisplayName
    

50.  $deviceResult IsCompliant $d = GraphDeviceObject。 IsCompliant
    

51.  $deviceResult IsManaged $d = GraphDeviceObject。 IsManaged
    

52.  $deviceResult DeviceObjectId = $d。
    

53.  $deviceResult RegisteredOwnerUpn = $u UserPrincipalName
    

54.  $deviceResult RegisteredOwnerObjectId = $u。
    

55.  $deviceResult RegisteredOwnerDisplayName = $u DisplayName
    

56.  $deviceResult ApproximateLastLogonTimestamp = $d。 ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  如果 ($export) 
    

64.  {
    

65.  $result |Export-Csv-path ($exportPath + " \" +" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  使用文件扩展名 ps1 将其另存为 Windows PowerShell 脚本文件。例如，Get-MsolUserDeviceComplianceStatus.ps1。   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>运行脚本以获取单个用户帐户的设备信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。
    
2. 转到保存该脚本的文件夹。 例如，如果您已将其保存到 C:\PS-Scripts，请运行以下命令。
    
    cd C:\PS-Scripts

3. 运行以下命令以确定要获取其设备详细信息的用户。 此示例获取 bar@example.com 的详细信息。
    
    $u = Get-msoluser-UserPrincipalName bar@example.com

4. 运行以下命令以启动脚本。

    .\Get-MsolUserDeviceComplianceStatus.ps1 用户 $u 导出

该信息将作为 CSV 文件导出到 Windows 桌面。 您可以使用其他参数指定 CSV 的文件名和路径。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>运行脚本以获取一组用户的设备信息

1. 打开用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块。
    
2. 转到保存该脚本的文件夹。 例如，如果您已将其保存到 C:\PS-Scripts，请运行以下命令。   

    cd C:\PS-Scripts

3. 运行以下命令以确定要为其获取设备详细信息的组。 此示例获取 FinanceStaff 组中用户的详细信息。 

    $u = MsolGroupMember-SearchString "FinanceStaff" |% {Get-msoluser-ObjectId $ _。ObjectId

4. 运行以下命令以启动脚本。   

    .\Get-MsolUserDeviceComplianceStatus.ps1 用户 $u 导出

该信息将作为 CSV 文件导出到 Windows 桌面。 您可以使用其他参数指定 CSV 的文件名和路径。

## <a name="related-topics"></a>相关主题

[Microsoft Connect 已停用](https://docs.microsoft.com/collaborate/connect-redirect)

[基本移动性和安全性概述](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)