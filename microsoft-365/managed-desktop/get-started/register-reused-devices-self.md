---
title: 自行注册现有设备
description: 注册你可能已拥有的重复使用的设备，以便它们可以通过 Microsoft 托管桌面进行管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840511"
---
# <a name="register-existing-devices-yourself"></a>自行注册现有设备

>[!NOTE]
>本主题介绍重复使用已有设备的步骤，并在 Microsoft 托管桌面中注册这些设备。 如果你使用全新的设备，请改为按照 Microsoft 托管桌面中的"注册新设备" [中的](register-devices-self.md) 步骤操作。

合作伙伴的流程记录在合作伙伴 [注册设备的步骤中](register-devices-partner.md)。

Microsoft 托管桌面可以与全新的设备一起使用，或者你可以重复使用你可能已拥有的设备 (这将要求你将它们重新映像) 。 可以在 Microsoft Endpoint Manager 门户中向 Microsoft 托管桌面注册设备。

## <a name="prepare-to-register-existing-devices"></a>准备注册现有设备


若要注册现有设备，请按照以下步骤操作：

1. [获取每个设备的硬件哈希。](#obtain-the-hardware-hash)
2. [合并哈希数据](#merge-hash-data)
3. [在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。
4. [仔细检查图像是否正确。](#check-the-image)
5. [交付设备](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>获取硬件哈希

Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。 有四个选项用于从你已使用的设备获取此信息：

- 向 OEM 供应商询问 AutoPilot 注册文件，该文件将包含硬件哈希。
- 在 [Microsoft Endpoint Configuration Manager 中收集信息](#microsoft-endpoint-configuration-manager)。
- 运行Windows PowerShell脚本（通过使用[Active Directory](#active-directory-powershell-script-method)或在每台设备上[](#manual-powershell-script-method)手动运行）并收集文件中的结果。
- 启动每台设备（但不完成 Windows 设置体验）并收集可移动闪存驱动器 [上的哈希](#flash-drive-method)。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

可以使用 Microsoft Endpoint Configuration Manager 从要注册到 Microsoft 托管桌面的现有设备收集硬件哈希。

> [!IMPORTANT]
> 要获取此信息的任何设备都必须运行 Windows 10 版本 1703 或更高版本。 

如果满足所有这些先决条件，就可以按照以下步骤收集信息：

1. 在 Configuration Manager 控制台中，选择"监控 **"。** 
2. 在"监控"工作区中，展开 **"报告** "节点，展开 **"报告**"，然后选择 **"硬件 - 常规"** 节点。 
3. 运行报告 **、Windows Autopilot 设备信息** 并查看结果。
4. 在报告查看器中 **，选择"** 导出"图标，然后选择 **"CSV** (逗号分隔的) 选项。
5. 保存文件后，你需要仅筛选出计划向 Microsoft 托管桌面注册的设备的结果，并将数据上载到 Microsoft 托管桌面。 打开 Microsoft Endpoint Manager 并导航到 **"设备**"菜单，然后查找"Microsoft 托管桌面"部分并选择 **"设备"。** 选择 **+ 注册设备**，这将打开一个飞入以注册新设备。


有关详细信息 [，请参阅使用管理门户注册](#register-devices-by-using-the-admin-portal) 设备。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell 脚本方法

在 Active Directory 环境中，可以使用 `Get-WindowsAutoPilotInfo` PowerShell cmdlet 通过 WinRM 从 Active Directory 组的设备远程收集信息。 您还可以使用该 cmdlet，并获取目录中包含的特定 `Get-AD Computer` 硬件型号名称的筛选结果。 在继续之前，首先确认这些先决条件，然后继续执行以下步骤：

- WinRM 已启用。
- 要注册的设备在网络设备上处于活动状态 (也就是说，它们未断开连接或) 。
- 请确保你拥有一个域凭据参数，该参数具有在设备上远程执行的权限。
- 确保 Windows 防火墙允许访问 WMI。 为此，请按照以下步骤操作：

    1. 打开 **Windows Defender防火墙** 控制面板，然后选择"允许应用或功能Windows Defender **防火墙"。**
    
    2. 在 **列表中查找 Windows Management Instrumentation (WMI**) ，同时启用 **"** 专用"和"公用"，然后选择"**确定"。**

1.  打开具有管理权限的 PowerShell 提示符。

2.  运行 *以下任* 一脚本：

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. 访问设备可能有条目的任何目录。 从所有目录（包括 Windows  Server Active Directory 域服务和 Azure Active Directory）中删除每台设备的条目。 请注意，删除可能需要几个小时才能完全完成。

4. 可能有设备条目的访问管理服务。 从所有管理服务（包括 Microsoft  Endpoint Configuration Manager、Microsoft Intune 和 Windows Autopilot）中删除每个设备的条目。 请注意，删除可能需要几个小时才能完全完成。

现在你可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。

#### <a name="manual-powershell-script-method"></a>手动 PowerShell 脚本方法

1.  打开具有管理权限的 PowerShell 提示符。
2.  运行 `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [合并哈希数据。](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash 驱动器方法

1. 在除要注册的设备外的其他设备上，插入 U 盘。
2. 打开具有管理权限的 PowerShell 提示符。
3. 运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 打开要注册的设备，但不 *启动安装体验*。 如果意外启动设置体验，必须重置或重置设备映像。
5. 插入 U 盘，然后按 Shift + F10。
6. 打开具有管理权限的 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。
7. 运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. 删除 U 盘，然后通过运行关闭设备 `shutdown -s -t 0`
10. [合并哈希数据。](#merge-hash-data)

>[!IMPORTANT]
>在注册完设备之前，请勿再次打开要注册的设备的电源。 



### <a name="merge-hash-data"></a>合并哈希数据

如果通过手动 PowerShell 或闪存驱动器方法收集硬件哈希数据，则现在需要将 CSV 文件中的数据合并到单个文件中才能完成注册。 下面是一个示例 PowerShell 脚本，可轻松实现：

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

将哈希数据合并到一个 CSV 文件中后，现在可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。


#### <a name="register-devices-by-using-the-admin-portal"></a>使用管理门户注册设备

在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)中， **选择** 左侧导航窗格中的设备。 查找菜单的"Microsoft 托管桌面"部分，然后选择 **"设备"。** 在 Microsoft 托管桌面设备工作区中，选择 **+ 注册** 设备，这将打开一个飞入以注册新设备。

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


请按以下步骤操作：

1. 在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。

1. 选择 **"注册设备"。** 系统会将设备添加到"设备"边栏选项卡上的设备列表，标记为 **"注册挂起"。** 注册通常少于 10 分钟，并且当成功时，设备将显示为"为用户准备就绪"，这意味着它已准备好并等待用户开始使用。


你可以监视主页上的设备注册进度。 报告可能状态包括：

| 状态 | 说明 |
|---------------|-------------|
| 注册挂起 | 注册尚未完成。 请稍后再回来查看。 |
| 注册失败 | 无法完成注册。 有关详细信息 [，请参阅设备注册](#troubleshooting-device-registration) 疑难解答。 |
| 为用户做好准备 | 注册成功，设备现在已准备好传递给用户。 Microsoft 托管桌面将指导用户完成首次设置，因此无需执行任何进一步准备。 |
| 活动文件 | 设备已传递到用户，并且他们已在租户中注册。 这还指示他们定期使用设备。 |
| 非活动 | 设备已传递到用户，并且他们已在租户中注册。 但是，他们最近 7 天内 (使用过) 。  | 

#### <a name="troubleshooting-device-registration"></a>设备注册疑难解答

| 错误消息 | 详细信息 |
|---------------|-------------|
| 未找到设备 | 我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。 与设备供应商确认这些值。 |
| 硬件哈希无效 | 你为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希，然后重新提交。 |
| 设备已注册 | 此设备已注册到组织。 无需执行其他操作。 |
| 由另一个组织声明的设备 | 此设备已被另一个组织声明。 请与设备供应商联系。 |
| 意外错误 | 您的请求无法自动处理。 联系支持人员并提供请求 ID： <requestId> |

### <a name="check-the-image"></a>检查图像

如果你的设备来自 Microsoft 托管桌面合作伙伴供应商，则映像应该正确。

如果愿意，也欢迎您自行应用该图像。 To get started， contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.

### <a name="deliver-the-device"></a>交付设备

> [!IMPORTANT]
> 在将设备上交给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。

如果应用了所有许可证，你可以让用户准备好[](get-started-devices.md)使用设备，然后你的用户可以启动设备并继续 Windows 安装体验。









