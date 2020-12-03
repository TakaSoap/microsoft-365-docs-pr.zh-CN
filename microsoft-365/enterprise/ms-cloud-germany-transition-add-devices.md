---
title: 从 Microsoft 云德国迁移的其他设备信息
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
description: 摘要：在 (Microsoft 云德国中移动时服务的其他设备信息。) 到新的德国数据中心区域中的 Office 365 服务。
ms.openlocfilehash: 941b836871f4ffb7f39f6e144675e9ee15510270
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560848"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>从 Microsoft 云德国迁移的其他设备信息

## <a name="frequently-asked-questions"></a>常见问题解答

**如何判断我的组织是否受到影响？**

管理员应 `https://portal.microsoftazure.de` 进行检查以确定他们是否有任何已注册的设备。 如果你的组织已注册设备，则会受到影响。

**对我的用户有什么影响？**

迁移进入 [Finalize AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段后，已注册设备的用户将无法再登录。  

确保在您的组织从 Microsoft 云德国断开连接之前，向全球终结点注册所有设备。
  
**我的用户何时重新注册其设备？**

您的成功只是在 [独立 Microsoft 云德国](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段注销和重新注册设备，这一点非常关键。

**如何在迁移后还原设备状态？**

对于使用 Azure AD 注册的混合 Azure AD （已加入和公司拥有的 Windows 设备），管理员将能够通过将注销旧设备状态的远程触发工作流来管理这些设备的迁移。
  
对于所有其他设备（包括在 Azure AD 中注册的个人 Windows 设备），最终用户必须手动执行这些步骤。 对于已加入 Azure AD 的设备，用户需要具有本地管理员帐户，才能注销并重新注册其设备。

Microsoft 将发布有关如何成功还原设备状态的说明。 
 
**我如何知道我的所有设备都已在公共云中注册？**

若要检查你的设备在公共云中是否已注册，应将设备列表从 Azure AD 门户导出并下载到 Excel 电子表格。 然后，在 [独立于 Microsoft 云德国](ms-cloud-germany-transition.md#how-is-the-migration-organized)迁移阶段之后，使用 _registeredTime_ 列) 对注册 (的设备进行筛选。

在迁移租户后，设备注册将停用，并且不能启用或禁用。 如果未使用 Intune，请登录订阅并运行以下命令以重新激活该选项：

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows 混合 Azure AD 加入

### <a name="windows-down-level"></a>Windows 低级别

_Windows 下层设备_ 是当前运行 windows 的早期版本的 windows 设备 (如 windows 8.1 或 windows 7) ，或者运行低于2019和2016的 windows Server 版本。 如果在之前注册了此类设备，则需要注销并重新注册这些设备。 

若要确定 Windows 下层设备以前是否已加入到 Azure AD，请在设备上使用以下命令：

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

如果设备以前已加入 Azure AD，并且该设备具有与全局 Azure AD 终结点的网络连接，则会看到以下输出：

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

受影响的设备将具有值为 "Unknown" 的 "设备状态"。 如果输出为 "设备未联接" 或 "设备状态" 值为 "正常"，请忽略以下指南。

仅对于显示该设备通过 deviceId、指纹等) 进行联接 (的设备，并且其 "设备状态" 值为 "Unknown" 时，管理员应在此类下层设备上的域用户登录上下文中运行以下命令：

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

上述命令只需要在每个域用户在 Windows 下层设备上登录时运行一次。 应在域用户登录的上下文中运行此命令。 

若要在用户随后登录时不运行此命令，则必须执行足够的小心。 运行上述命令时，它将清除登录的用户的本地混合 Azure AD –加入的计算机的加入状态。 此外，如果计算机仍配置为在租户中加入混合 Azure AD，它将在用户再次登录时尝试加入。

### <a name="windows-current"></a>Windows 当前

#### <a name="unjoin"></a>脱离

若要确定 Windows 10 设备之前是否已加入 Azure AD，请在设备上运行以下命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果设备是混合 Azure AD –已加入，则管理员将看到以下输出：

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

如果输出是 "AzureAdJoined： No"，请忽略以下指南。

仅对于显示设备已加入 Azure AD 的设备，以管理员身份运行以下命令以删除设备的加入状态。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上面的命令只需在 Windows 设备的管理上下文中运行一次。

#### <a name="hybrid-ad-joinre-registration"></a>混合 AD Join\Re-Registration

只要设备具有到全局 Azure AD 终结点的网络连接，该设备就会自动加入 Azure AD，而无需用户或管理员干预。 


## <a name="windows-azure-ad-join"></a>Windows Azure AD 加入

**重要说明：** 在商业迁移之后，将启用 Intune 服务主体，这意味着激活 Azure AD 设备注册。 如果在迁移之前阻止了 Azure AD 设备注册，则必须使用 PowerShell 禁用 Intune service 主体，以使用 Azure AD 门户再次禁用 azure ad 设备注册。 您可以使用 Azure Active Directory PowerShell for Graph 模块中的此命令禁用 Intune service 主体。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>脱离

若要确定 Windows 10 设备之前是否已加入 Azure AD，用户或管理员可以在设备上运行以下命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果设备已加入 Azure AD，则用户或管理员将看到以下输出：

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

如果输出是 "AzureAdJoined： NO"，请忽略以下指南。

用户：如果设备已加入 Azure AD，则用户可以从设置中脱离设备。 在从 Azure AD unjoining 设备之前，请确认设备上是否有本地管理员帐户。 登录回设备需要本地管理员帐户。

管理员：如果组织的管理员想要脱离已加入 Azure AD 的用户设备，则可以通过使用组策略等机制在每个设备上运行以下命令来执行此操作。 管理员必须先验证设备上是否有本地管理员帐户，然后再 unjoining Azure AD 中的设备。 登录回设备需要本地管理员帐户。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上面的命令只需在 Windows 设备的管理上下文中运行一次。 

### <a name="azure-ad-joinre-registration"></a>Azure AD 加入/重新注册

用户可以从 Windows 设置中将设备加入 Azure AD： **settings > 帐户 > 访问工作或学校 > 连接**。
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD 注册 (公司拥有) 

若要确定 Windows 10 设备是否已注册为 Azure AD，请在设备上运行以下命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果设备已注册 Azure AD，则会看到以下输出：

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

若要删除设备上现有的 Azure AD 注册帐户，请执行以下操作：

- 若要删除设备上的 Azure AD 注册帐户，请使用 CleanupWPJ，可从此处下载的工具： [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)。

- 解压缩 ZIP 文件并运行 **WPJCleanup**。 此工具将根据设备上的 Windows 版本启动正确的可执行文件。

- 通过使用像组策略这样的机制，管理员可以在设备上的任何登录的用户上下文中运行此命令。

若要禁用 Web 帐户管理器提示以在 Azure AD 中注册设备，请添加以下注册表值： 

- 位置： HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 类型： DWORD (32 位) 
- 名称： BlockAADWorkplaceJoin
- 值数据：1

此注册表值的存在应阻止 workplace join，并防止用户看到加入设备的提示。

## <a name="android"></a>Android

对于 Android，用户将需要注销并重新注册其设备。 可以通过 Microsoft 验证器应用或公司门户应用来完成此操作。 

- 在 Microsoft 身份验证器应用中，用户可以转到 " **设备注册" >** 的 "设置"。 用户可以从此处注销和重新注册其设备。
 
- 在公司门户中，用户可以转到 " **设备** " 选项卡并删除该设备。 然后，使用公司门户重新注册该设备。
 
- 用户还可以通过从 "帐户设置" 页删除帐户，然后重新添加工作帐户来取消注册和重新注册。

若要使用 Microsoft 验证器应用在 Android 上注销并重新注册设备，请执行以下操作：

1.  打开 Microsoft 身份验证器应用，然后转到 " **设置**"。
2.  选择 " **设备注册**"。
3.  通过选择 " **注销**" 注销设备。
4.  对于 **设备注册**，请通过键入电子邮件地址重新注册该设备，然后选择 " **注册**"。

若要使用 Android 设置页面注销和重新注册 Android 设备，请执行以下操作：

1.  打开 " **设备设置** "，然后转到 " **帐户**"。
2.  选择要重新注册的工作帐户，然后选择 " **删除帐户**"。
3.  删除帐户后，从 " **帐户** " 页中，选择 " **添加帐户" > 工作帐户**。
4.  对于 " **Workplace Join**"，键入您的电子邮件地址，然后选择 " **加入** " 以完成设备注册。

若要从公司门户注销并重新注册 Android 上的设备，请执行以下操作：

1.  启动 "公司门户" 并转到 " **设备** " 选项卡。
2.  选择设备以查看设备详细信息。
3.  从省略号 (三个点) "菜单中，选择" **删除设备**"，然后通过在对话框中确认来完成删除操作。
4.  现在应注销公司门户应用程序。 选择 **"登录"** 以重新注册设备。

有关在此工作负荷的迁移阶段中所需的任何操作或对管理或使用的影响的详细信息，请查看有关 [从 Microsoft 云德国迁移的其他一般信息](ms-cloud-germany-transition-add-general.md#azure-active-directory)中的 Azure Active Directory 的信息。

## <a name="ios"></a>iOS

在 iOS 设备上，用户需要手动从 Microsoft 身份验证器中删除任何缓存帐户，注销该设备，然后从设备上的任何本机应用注销。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>步骤1：如果存在，请从 Microsoft 身份验证器应用中删除帐户

1. 在 Microsoft 身份验证应用程序中点击该帐户。
2. 在右上角点击 " **设置** " 图标。 如果看不到 " **设置** " 图标，则可能是因为没有使用 Microsoft 身份验证器的最新版本。
3. 点击 " **删除帐户** " 按钮。
4. 点击 **此设备上的所有应用**。
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>步骤2：从 Microsoft 身份验证器应用注销设备

1. 点击右上角的 "菜单" 图标。
2. 点击 " **设置** "，然后单击 " **设备注册**"。
4. 如果显示了你的帐户，请点击 " **取消注册设备** 并 **继续** " 对话框。 之后，您将不会看到任何帐户。
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>步骤3：在必要时注销单个应用

用户可以转到 Outlook、团队和 OneDrive 等各个应用，并从这些应用中删除帐户。

## <a name="more-information"></a>详细信息

入门：

- [从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移过程中的客户体验](ms-cloud-germany-transition-experience.md)

在转换中移动：

- [迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预备工作](ms-cloud-germany-transition-add-pre-work.md)
- [服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
