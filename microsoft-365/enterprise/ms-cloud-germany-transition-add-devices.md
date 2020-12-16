---
title: 从德国 Microsoft 云迁移的其他设备信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云 (德国 microsoft 云) 迁移到新的德国数据中心区域中的 Office 365 服务时，有关服务的其他设备信息。
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688649"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的其他设备信息

## <a name="frequently-asked-questions"></a>常见问题解答

**如何判断我的组织是否受到影响？**

管理员应检查 `https://portal.microsoftazure.de` 以确定他们是否有注册的设备。 如果你的组织已注册设备，你将受到影响。

**我的用户受到什么影响？**

迁移进入"完成 [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移"阶段后，注册设备中的用户将无法再登录。  

在组织与德国 Microsoft 云断开连接之前，请确保你的所有设备都向全球终结点注册。
  
**我的用户何时重新注册其设备？**

在独立于 [Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 云德国迁移阶段，仅注销和重新注册设备对成功至关重要。

**如何在迁移后还原设备状态？**

对于已加入 Azure AD 的混合和在 Azure AD 中注册的公司拥有的 Windows 设备，管理员将能够通过远程触发的工作流管理这些设备的迁移，这些工作流将取消注册旧设备状态。
  
对于所有其他设备，包括在 Azure AD 中注册的个人 Windows 设备，最终用户必须手动执行这些步骤。 对于加入 Azure AD 的设备，用户需要具有本地管理员帐户才能注销，然后重新注册其设备。

Microsoft 将发布有关如何成功还原设备状态的说明。 
 
**我如何知道我的所有设备都注册到公共云中？**

若要检查设备是否已在公共云中注册，应该将设备列表从 Azure AD 门户导出并下载到 Excel 电子表格。 然后，使用 _registeredTime_ 列 (从 [德国 Microsoft](ms-cloud-germany-transition.md#how-is-the-migration-organized) 云迁移阶段) 注册的设备。

迁移租户后，设备注册将停用，并且无法启用或禁用。 如果未使用 Intune，请登录到你的订阅并运行此命令以重新激活此选项：

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows 混合 Azure AD 加入

### <a name="windows-down-level"></a>Windows 下层

_Windows 低_ 级别设备是当前运行较早版本的 Windows (（如 Windows 8.1 或 Windows 7) ）的 Windows 设备，或运行早于 2019 和 2016 的 Windows Server 版本的 Windows 设备。 如果之前注册过此类设备，则需要注销并重新注册这些设备。 

若要确定 Windows 低级别设备之前是否已加入 Azure AD，请对设备使用以下命令：

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

如果设备之前已加入 Azure AD，并且设备具有到全局 Azure AD 终结点的网络连接，你将看到以下输出：

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

受影响的设备将具有值为"Unknown"的"设备状态"。 如果输出为"未加入设备"或其"设备状态"值为"正常"，请忽略以下指南。

仅对于显示设备已通过 deviceId、指纹等) 加入 (且其"设备状态"值为"未知"的设备，管理员应在域用户登录此类低级别设备的上下文中运行以下命令：

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

每个域用户在 Windows 下层设备上登录只需运行一次上述命令。 此命令应在域用户登录的上下文中运行。 

当用户随后登录时，必须非常小心，不要运行此命令。 当上述命令运行时，它将为登录的用户清除加入本地混合 Azure AD 的计算机的状态。 此外，如果计算机仍配置为已加入租户的混合 Azure AD，它将在用户再次登录时尝试加入。

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Unjoin

若要确定 Windows 10 设备之前是否已加入 Azure AD，请对设备运行以下命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果设备已加入混合 Azure AD，管理员将看到以下输出：

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

如果输出为"AzureAdJoined ： 否"，请忽略以下指南。

仅对于显示设备已加入 Azure AD 的设备，以管理员角色运行以下命令以删除设备的加入状态。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上述命令只需在 Windows 设备的管理上下文中运行一次。

#### <a name="hybrid-ad-joinre-registration"></a>混合 AD 加入\重新注册

只要设备具有到全局 Azure AD 终结点的网络连接，设备就会自动加入 Azure AD，无需用户或管理员干预。 


## <a name="windows-azure-ad-join"></a>Windows Azure AD 联接

**重要提示：** 商业迁移后将启用 Intune 服务主体，这意味着激活 Azure AD 设备注册。 如果在迁移之前阻止了 Azure AD 设备注册，则必须使用 PowerShell 禁用 Intune 服务主体，以再次禁用 Azure AD 门户的 Azure AD 设备注册。 可以在 Azure Active Directory PowerShell for Graph 模块中通过此命令禁用 Intune 服务主体。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

若要确定 Windows 10 设备之前是否已加入 Azure AD，用户或管理员可以在设备上运行以下命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果设备已加入 Azure AD，用户或管理员将看到以下输出：

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

如果输出为"AzureAdJoined ： NO"，请忽略以下指南。

用户：如果设备已加入 Azure AD，则用户可以从设置中取消加入设备。 在从 Azure AD 中取消加入设备之前，请验证设备上是否有本地管理员帐户。 需要本地管理员帐户才能重新登录设备。

管理员：如果组织的管理员想要取消加入已加入 Azure AD 的用户设备，他们可以使用组策略等机制在每个设备上运行以下命令。 在从 Azure AD 中取消加入设备之前，管理员必须验证设备上是否有本地管理员帐户。 需要本地管理员帐户才能重新登录设备。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上述命令只需在 Windows 设备的管理上下文中运行一次。 

### <a name="azure-ad-joinre-registration"></a>Azure AD 加入/重新注册

用户可以从 Windows 设置将设备加入 Azure AD：设置>帐户> **访问工作或学校>连接**。
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure公司拥有 (AD 注册) 

若要确定 Windows 10 设备是否已注册 Azure AD，请对设备运行以下命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果设备已注册 Azure AD，你将看到以下输出：

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

若要删除设备上现有的 Azure AD 注册帐户，请执行以下操作：

- 若要删除设备上已注册 Azure AD 的帐户，请使用 CleanupWPJ，一种可从此处下载的工具[：CleanupWPJ.zip。 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)

- 提取 ZIP 文件并运行 **WPJCleanup.cmd。** 此工具将基于设备上 Windows 的版本启动正确的可执行文件。

- 通过使用组策略等机制，管理员可以在设备上运行在设备上登录的任何用户的上下文中的命令。

若要禁用 Web 帐户管理器提示在 Azure AD 中注册设备，请添加以下注册表值： 

- 位置：HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 类型：DWORD (32 位) 
- 名称：BlockAADWorkplaceJoin
- 值数据：1

存在此注册表值应阻止工作区加入，并阻止用户看到加入设备的提示。

## <a name="android"></a>Android

对于 Android，用户需要注销和重新注册其设备。 这可以通过 Microsoft Authenticator 应用或公司门户应用完成。 

- 从 Microsoft Authenticator 应用中，用户可以转到"设备注册 **>设置"。** 用户可以从该服务器注销并重新注册其设备。
 
- 从公司门户，用户可以 **转到"设备** "选项卡并删除设备。 之后，使用公司门户重新注册设备。
 
- 用户还可以从帐户设置页中删除帐户，然后重新添加工作帐户，从而注销和重新注册。

若要使用 Microsoft Authenticator 应用在 Android 上注销和重新注册设备，请运行以下操作：

1.  打开 Microsoft Authenticator 应用并转到"**设置"。**
2.  选择 **设备注册**。
3.  通过选择"注销"取消 **注册设备**。
4.  对于 **设备注册**，请键入您的电子邮件地址重新注册设备，然后选择"注册 **"。**

若要注销 Android 设备，然后重新注册 Android 设备，请通过"Android 设置"页：

1.  打开 **"设备设置**"并转到"**帐户"。**
2.  选择要重新注册的工作帐户，然后选择"删除 **帐户"。**
3.  删除帐户后，从"帐户"**页中，** 选择">**工作帐户"。**
4.  对于 **Workplace Join，** 键入您的电子邮件地址并选择 **"加入** "以完成设备注册。

若要从公司门户注销和重新注册 Android 上的设备：

1.  启动公司门户并转到 **"设备"** 选项卡。
2.  选择设备以查看设备详细信息。
3.  From theellipses (three dots) menu， select **Remove Device，** and complete the removal by confirming in the dialog.
4.  你现在应该从公司门户应用注销。 选择 **"登录** "以重新注册设备。

有关此工作负载的迁移阶段所需的任何操作或对管理或使用情况的影响，请查看有关从德国 Microsoft 云迁移的其他 [Azure AD](ms-cloud-germany-transition-azure-ad.md)信息中的 Azure Active Directory (Azure AD) 的信息。

## <a name="ios"></a>iOS

在 iOS 设备上，用户需要从 Microsoft Authenticator 手动删除所有缓存的帐户，注销设备，然后从设备上的任何本机应用注销。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>步骤 1：如果存在，请从 Microsoft Authenticator 应用中删除帐户

1. 点击 Microsoft Authenticator 应用中的帐户。
2. 点击 **右上角** 的"设置"图标。 如果看不到"设置 **"图标，** 可能没有使用最新版本的 Microsoft Authenticator。
3. 点击 **"删除帐户"** 按钮。
4. 点击 **此设备上的所有应用**。
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>步骤 2：从 Microsoft Authenticator 应用注销设备

1. 点击右上角的菜单图标。
2. 点击 **"** 设置"，然后 **点击"设备注册"。**
4. 如果显示你的帐户，请点击 **"注销设备** "， **然后继续在** 对话框中继续。 之后应该看不到任何帐户。
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>步骤 3：如有必要，从各个应用注销

用户可以转到各个应用（如 Outlook、Teams 和 OneDrive）并从这些应用中删除帐户。

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
