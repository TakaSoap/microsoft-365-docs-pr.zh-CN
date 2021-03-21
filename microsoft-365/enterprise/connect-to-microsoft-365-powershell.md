---
title: 使用 PowerShell 连接 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: 使用 PowerShell for Microsoft 365 连接到 Microsoft 365 租户，从命令行执行管理中心任务。
ms.openlocfilehash: 58af42958e9b50ee8e39cbd7bd5aab53812e444c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919172"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>使用 PowerShell 连接 Microsoft 365

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

PowerShell for Microsoft 365 可让你从命令行管理您的 Microsoft 365 设置。 要连接到 PowerShell，只需安装所需的软件，然后连接到 Microsoft 365 组织。

可以使用两种版本的 PowerShell 模块连接至 Microsoft 365 和管理员用户帐户、组和许可证：

- Azure Active Directory PowerShell for Graph（其 cmdlet 在其名称中包含 *AzureAD*）
- 用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块（其 cmdlet 在其名称中包含 *Msol*）

目前，对于用户、组和许可证管理，Azure Active Directory PowerShell for Graph 模块不能完全替代用于 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块的功能。 在某些情况下，需要同时使用两种版本。 可以在同一计算机上安全地安装两种版本。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，需要知道什么？


**操作系统**

必须使用 64 位版 Windows。 2014 年已终止对 32 位版的用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块的支持。

可以使用下列 Windows 版本：
    
  - Windows 10、Windows 8.1、Windows 8 或 Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 SP1

>[!Note]
>对于 Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 SP1，请下载并安装 [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)。

**PowerShell**

- 对于 Azure Active Directory PowerShell for Graph 模块，必须使用 PowerShell 版本 5.1 或以上版本。

- 对于用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，必须使用 PowerShell 版本 5.1 或以上版本（最高版本 6）。 你无法使用 PowerShell 版本 7。
       
>[!Note]
>这些步骤适合于属于 Microsoft 365 管理员角色成员的用户。 有关详细信息，请参阅[关于管理员角色](../admin/add-users/about-admin-roles.md)。


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>连接到 Azure Active Directory PowerShell Graph 模块

Azure Active Directory PowerShell Graph 模块中的命令在其 cmdlet 名称中包含 *AzureAD*。 可安装[Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) 模块或 [Azure PowerShell](/powershell/azure/install-az-ps)。

有关在 Azure Active Directory PowerShell Graph 模块中需要新 cmdlet 的过程，请按照以下步骤安装该模块并连接到 Microsoft 365 订阅。

> [!Note]
> 有关不同版本的 Microsoft Windows 的支持信息，请参阅 [Azure Active Directory PowerShell Graph 模块](/powershell/azure/active-directory/install-adv2)。

### <a name="step-1-install-the-required-software"></a>步骤 1：安装所需软件

这些步骤只需在计算机上执行一次。 但可能需要定期更新软件。
  
1. 打开提升的 Windows PowerShell 命令提示符窗口（以管理员身份运行 Windows PowerShell）。
    
2. 运行此命令：
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   如果系统提示从不受信任的存储库安装模块，请键入 **Y** 并按 Enter 键。

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>步骤 2：连接到 Microsoft 365 订阅的 Azure AD

若要使用帐户名称和密码或者多重身份验证连接到 Microsoft 365 订阅的 Azure Active Directory (Azure AD)，请在 Windows PowerShell 命令提示符中运行这些命令之一。 （无需提升。）

| Office 365 云 | 命令 |
|:-------|:-----|
| Office 365 全球 (+GCC) | `Connect-AzureAD` |
| 由世纪互联运营的 Office 365 | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 德国 | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 美国政府版 DoD 和 Office 365 美国政府版 GCC 高 | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

在“**登录到你的帐户**”对话框中，键入 Microsoft 365 工作或学校帐户用户名和密码，再选择“**确定**”。

如果使用多重身份验证，请按照说明提供其他身份验证信息，例如验证码。

连接后，可对 [Azure Active Directory PowerShell Graph 模块](/powershell/module/azuread)使用这些 cmdlet。

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>与用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块连接

>[!Note]
>用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块中的 cmdlet 名称中具有 *Msol*。

PowerShell 版本 7 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。 对于 PowerShell 版本 7 和更高版本，必须使用 Azure Active Directory PowerShell for Graph 模块或 Azure PowerShell。

PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。 从 Windows PowerShell 运行这些 cmdlet。
    
### <a name="step-1-install-the-required-software"></a>步骤 1：安装所需软件

这些步骤只需在计算机上执行一次。 但可能需要定期更新软件。
  
1.  如果您运行的不是 Windows 10，则请安装 64 位版 Microsoft Online Services 登录助手：[适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手](https://www.microsoft.com/Download/details.aspx?id=28177)。
    
2. 请按照以下步骤，安装用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块：
    
   1. 打开提升的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell）。
   1.  运行 **Install-Module MSOnline** 命令。
   1. 如果系统提示安装 NuGet 提供程序，请键入 **Y**，然后按 Enter 键。
   1. 如果系统提示从 PSGallery 安装模块，请键入 **Y**，然后按 Enter 键。
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>步骤 2：连接到 Microsoft 365 订阅的 Azure AD

若要使用帐户名称和密码或者多重身份验证连接到 Microsoft 365 订阅的 Azure AD，请在 Windows PowerShell 命令提示符中运行这些命令之一。 （无需提升。）

| Office 365 云 | 命令 |
|:-------|:-----|
| Office 365 全球 (+GCC) | `Connect-MsolService` |
| 由世纪互联运营的 Office 365 | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 德国 | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 美国政府版 DoD 和 Office 365 美国政府版 GCC 高 | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

在“**登录到你的帐户**”对话框中，键入 Microsoft 365 工作或学校帐户用户名和密码，再选择“**确定**”。

如果使用多重身份验证，请按照说明提供其他身份验证信息，例如验证码。

### <a name="how-do-you-know-it-worked"></a>如何知道它是正常工作的？

如果你没有收到错误消息，则表明你已成功连接。 若要快速测试，请运行 Microsoft 365 cmdlet，例如 **Get-MsolUser**，然后查看结果。
  
如果收到错误消息，请检查以下问题：
  
- **常见问题是密码错误**。 再次运行[步骤 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)，并密切注意您输入的用户名和密码。
    
- **用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块要求在计算机上启用 Microsoft .NET Framework 3.5.* x*。很可能你的计算机已安装了较新的版本（例如 4 或 4.5.* x*）。 但可以启用或禁用与 .NET Framework 的早期版本的向后兼容性。 有关详细信息，请参阅以下文章：
    
  - 对于 Windows Server 2012 或 Windows Server 2012 R2，请参阅[使用“添加角色和功能”向导启用 .NET Framework 3.5](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10))。
    
  - 对于 Windows 7 或 Windows Server 2008 R2，请参阅[不能打开用于 Windows PowerShell 的 Azure Active Directory 模块](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell)。

  - 对于 Windows 10、Windows 8.1 和 Windows 8，请参阅[在 Windows 10、Windows 8.1 和 Windows 8 上安装 .NET Framework 3.5](/dotnet/framework/install/dotnet-35-windows-10)。

  
- **你的用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块版本可能已过期。** 若要进行检查，请在 PowerShell for Microsoft 365 或用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块中运行以下命令：
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    如果返回的版本号低于 *1.0.8070.2*，请卸载用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块，并通过上述 [第 1 步](#step-1-install-the-required-software)进行安装。

- **如果收到连接错误，请参阅**[“Connect-MsolService：抛出类型异常”错误](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception)。
    
- **如果收到“Get-Item：找不到路径”错误消息**，请运行以下命令：


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a>另请参阅

- [使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
- [PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
- [在单个 Windows PowerShell 窗口中连接所有 Microsoft 365 服务](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)