---
title: 自行注册现有设备
description: 注册重新使用的设备你可能已经有了你自己的设备，以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9ff0e76448df183ac5c34c5832155e0b135d313
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868981"
---
# <a name="register-existing-devices-yourself"></a>自行注册现有设备

>[!NOTE]
>本主题介绍了重新使用已拥有的设备的步骤，并将其注册到 Microsoft 托管桌面。 如果您正在使用全新的设备，请按照在 [Microsoft 托管桌面中注册新设备](register-devices-self.md) 中的步骤操作。

合作伙伴的过程记录在 [合作伙伴注册设备的步骤](register-devices-partner.md)中。

Microsoft 托管桌面可以与全新设备配合使用，也可以重新使用已有的设备 (这将需要您将其重新映像) 。 您可以使用 Microsoft 托管桌面管理门户注册设备。

## <a name="prepare-to-register-existing-devices"></a>准备注册现有设备


若要注册现有设备，请按照下列步骤操作：

1. [获取每个设备的硬件哈希。](#obtain-the-hardware-hash)
2. [合并哈希数据](#merge-hash-data)
3. [在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。
4. [请仔细检查图像是否正确。](#check-the-image)
5. [传递设备](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>获取硬件哈希

Microsoft 托管桌面通过引用其硬件哈希来唯一标识每个设备。 你可以通过四个选项从已在使用的设备中获取此信息：

- 向 OEM 提供商咨询 AutoPilot 注册文件，其中将包含硬件哈希值。
- 在 [Microsoft 终结点配置管理器](#microsoft-endpoint-configuration-manager)中收集信息。
- 在每台设备上使用 [Active Directory](#active-directory-powershell-script-method) 或 [手动](#manual-powershell-script-method) 运行 Windows PowerShell 脚本--并在文件中收集结果。
- 启动每个设备--但不完成 Windows 安装程序体验，并 [收集可移动闪存驱动器上的哈希值](#flash-drive-method)。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

您可以使用 Microsoft 终结点配置管理器收集要使用 Microsoft 托管桌面注册的现有设备的硬件哈希值。

> [!IMPORTANT]
> 要获取此信息的任何设备都必须运行 Windows 10 版本1703或更高版本。 

如果你已满足所有这些先决条件，则可以按照以下步骤收集信息：

1. 在 Configuration Manager 控制台中，选择 " **监控**"。 
2. 在 "监控" 工作区中，展开 " **报告** " 节点，再展开 " **报告**"，然后选择 " **硬件"-"常规** " 节点。 
3. 运行报告、 **Windows Autopilot 设备信息**并查看结果。
4. 在报表查看器中，选择 " **导出** " 图标，然后选择 **CSV (逗号分隔的) ** 选项。
5. 保存文件后，您需要筛选结果，使其仅包含计划注册 Microsoft 托管桌面的那些设备，并将数据上传到 Microsoft 托管桌面 [管理门户](https://aka.ms/mmdportal)，请在左侧导航窗格中选择 " **设备** "。 选择 **+ 注册设备**;将打开 "飞入"：


有关详细信息，请参阅 [注册设备（使用管理门户](#register-devices-by-using-the-admin-portal) ）。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell 脚本方法

在 Active Directory 环境中，您可以使用 `Get-WindowsAutoPilotInfo` PowerShell cmdlet 从 Active Directory 组中的设备远程收集信息，方法是使用 WinRM。 您还可以使用 `Get-AD Computer` cmdlet 并获取目录中包含的特定硬件模型名称的筛选结果。 为此，请首先确认这些先决条件，然后继续执行以下步骤：

- 启用 WinRM。
- 您要注册的设备在网络 (上是活动的，它们不会断开连接或关闭) 。
- 请确保您有一个具有在设备上远程执行的权限的域凭据参数。
- 请确保 Windows 防火墙允许访问 WMI。 为此，请按照以下步骤操作：

    1. 打开 **Windows Defender 防火墙** 控制面板，然后选择 " **允许通过 Windows defender 防火墙的应用程序或功能**"。
    
    2. 在列表中查找 **Windows Management Instrumentation (WMI) ** ，启用 " **专用" 和 "公共**"，然后选择 **"确定"**。

1.  打开具有管理权限的 PowerShell 提示。

2.  运行以下 *任意一个* 脚本：

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. 访问可能包含设备条目的任何目录。 从 *所有* 目录中删除每个设备的条目，包括 Windows Server Active Directory 域服务和 Azure Active directory。 请注意，此删除操作可能需要几个小时才能完成。

4. 可能包含设备条目的 Access management services。 从 *所有* 管理服务（包括 Microsoft 终结点配置管理器、microsoft Intune 和 Windows Autopilot）中删除每个设备的条目。 请注意，此删除操作可能需要几个小时才能完成。

现在，你可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。

#### <a name="manual-powershell-script-method"></a>手动 PowerShell 脚本方法

1.  打开具有管理权限的 PowerShell 提示。
2.  以 `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  以 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [合并哈希数据。](#merge-hash-data)

#### <a name="flash-drive-method"></a>闪存驱动器方法

1. 在要注册的设备以外的其他设备上，插入 u 盘。
2. 打开具有管理权限的 PowerShell 提示。
3. 以 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 打开要注册的设备，但 *不要启动安装程序体验*。 如果您意外启动了设置体验，则必须重置或重新映像设备。
5. 插入 u 盘，然后按 SHIFT + F10。
6. 打开具有管理权限的 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。
7. 以 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 以 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. 删除 USB 驱动器，然后通过运行来关闭设备 `shutdown -s -t 0`
10. [合并哈希数据。](#merge-hash-data)

>[!IMPORTANT]
>在完成注册后，请不要再打开要注册的设备。 



### <a name="merge-hash-data"></a>合并哈希数据

如果您通过手动 PowerShell 或闪存驱动器方法收集了硬件哈希数据，则您现在需要将 CSV 文件中的数据组合到单个文件中才能完成注册。 下面是一个示例 PowerShell 脚本，可轻松实现此操作：

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

将哈希数据合并到一个 CSV 文件中，现在就可以继续 [注册设备了](#register-devices-by-using-the-admin-portal)。


#### <a name="register-devices-by-using-the-admin-portal"></a>使用管理门户注册设备

在 Microsoft 托管桌面 [管理门户](https://aka.ms/mmdportal)中，选择左侧导航窗格中的 " **设备** "。 选择 **+ 注册设备**;将打开 "飞入"：

[![选择注册设备后飞入，列出分配的用户的列设备、序列号、状态、上次查看日期和期限](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


请按以下步骤操作：

1. 在 " **文件上载**" 中，提供以前创建的 CSV 文件的路径。

1. 选择 " **注册设备**"。 系统会将设备添加到 **设备**上的设备列表中，并标记为 **AutopilotRegistrationRequested**。 注册通常需要不到10分钟的时间，如果成功，设备将显示为 "就绪"，使其可供 **用户** 使用，并等待用户开始使用。


你可以在主 **Microsoft 托管台式机-设备** 页面上监视设备注册的进度。 可能报告的状态包括：

| 状态 | 说明 |
|---------------|-------------|
| AutopilotRegistrationRequested | 注册尚未完成。 稍后再次查看。 |
| 注册失败 | 无法完成注册。 有关详细信息，请参阅 [设备注册故障排除](#troubleshooting-device-registration) 。 |
| 为用户准备就绪 | 注册成功，现在设备已准备好传递给最终用户。 Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。 |
| 活动 | 设备已传递给最终用户，并且已向其注册了你的租户。 这也表明它们是定期使用设备的。 |
| 不再 | 设备已传递给最终用户，并且已向其注册了你的租户。 但是，他们在过去7天内未使用最近 (设备) 。  | 

#### <a name="troubleshooting-device-registration"></a>设备注册故障排除

| 错误消息 | 详细信息 |
|---------------|-------------|
| 找不到设备 | 无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。 请与设备供应商确认这些值。 |
| 硬件哈希无效 | 为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希，然后重新提交。 |
| 已注册设备 | 此设备已注册到你的组织。 无需执行进一步操作。 |
| 其他组织声明的设备 | 此设备已由其他组织声明。 请与设备供应商联系。 |
| 意外错误 | 无法自动处理你的请求。 联系支持人员并提供请求 ID： <requestId> |

### <a name="check-the-image"></a>检查图像

如果你的设备来自 Microsoft 托管桌面合作伙伴提供商，则该映像应正确。

如果你愿意，也可以在自己自己应用图像。 若要开始，请联系你正在使用的 Microsoft 代表，他们将为你提供应用此图像的位置和步骤。

### <a name="deliver-the-device"></a>传递设备

> [!IMPORTANT]
> 在将设备交给用户之前，请确保已为该用户获取并应用了 [相应的许可证](../get-ready/prerequisites.md) 。

如果应用了所有许可证，则可以 [让用户准备好使用设备](get-started-devices.md)，然后你的用户可以启动设备并继续执行 Windows 安装体验。









