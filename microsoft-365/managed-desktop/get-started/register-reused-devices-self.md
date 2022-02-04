---
title: 自行注册现有设备
description: 注册你可能已拥有的重复使用的设备，以便它们可以通过Microsoft 托管桌面
ms.service: m365-md
author: tiaraquan
f1.keywords:
  - NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
---

# <a name="register-existing-devices-yourself"></a>自行注册现有设备

>[!NOTE]
>本文介绍了重复使用已拥有的设备的步骤，并在 Microsoft 托管桌面。 如果你使用全新的设备，请改为按照在设备上注册新Microsoft 托管桌面[中的步骤](register-devices-self.md)操作。 <br> <br> 合作伙伴流程记录在合作伙伴 [注册设备的步骤中](register-devices-partner.md)。

Microsoft 托管桌面全新的设备，或者你可以重复使用你可能已有的设备。 如果你重复使用设备，则必须重新映像处理它们。 可以在应用门户中向Microsoft 托管桌面注册Microsoft Endpoint Manager设备。

## <a name="prepare-to-register-existing-devices"></a>准备注册现有设备

**注册现有设备：**

1. [获取每台设备的硬件哈希。](#obtain-the-hardware-hash)
2. [合并哈希数据](#merge-hash-data)。
3. [在设备上注册Microsoft 托管桌面](#register-devices-by-using-the-admin-portal)。
4. [仔细检查图像是否正确。](#check-the-image)
5. [交付设备](#deliver-the-device)。

### <a name="obtain-the-hardware-hash"></a>获取硬件哈希

**若要获取硬件哈希：：**

Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。 有四个选项用于从你已在使用的设备获取此信息：

- 请你的 OEM 供应商提供 AutoPilot 注册文件，该文件将包含硬件哈希。
- 在"管理"[Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)。
- 使用 active [Directory](#active-directory-powershell-script-method) 或手动在每个设备上运行 Windows PowerShell 脚本，并收集[](#manual-powershell-script-method)文件中的结果。
- 启动每台设备，但不完成Windows安装体验，并收集可移动闪存[驱动器上的哈希](#flash-drive-method)。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

可以使用 Microsoft Endpoint Configuration Manager从要注册到 Microsoft 托管桌面 的现有设备收集硬件Microsoft 托管桌面。 如果满足所有这些先决条件，就可以收集信息了。

> [!IMPORTANT]
> 要获取此信息的任何设备都必须在 Windows 10版本 1703 或更高版本上运行。

**若要收集硬件哈希信息，请运行以下代码：**

1. 在 Configuration Manager 控制台中，选择"监控 **"**。
2. 在"监控"工作区中，展开" **报告"** 节点，展开" **报告**"，然后选择" **硬件 - 常规"** 节点。
3. 运行报告，**Windows Autopilot 设备信息**，并查看结果。
4. 在报告查看器中， **选择"导出** "图标，然后选择 **"CSV (逗号** 分隔) 选项。
5. 保存文件后，你需要仅筛选结果，以仅筛选计划向 Microsoft 托管桌面 注册的设备。 然后，将数据上载到Microsoft 托管桌面。
    - 打开Microsoft Endpoint Manager并导航到 **"设备"** 菜单。
    - 在"Microsoft 托管桌面部分中，选择 **"设备"**。
    - 选择 **+ 注册设备**，这将打开一个飞入以注册新设备。

有关详细信息，请参阅下面的 [管理门户注册](#register-devices-by-using-the-admin-portal) 设备。

#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell 脚本方法

在 Active Directory 环境中 `Get-WindowsAutoPilotInfo` ，可以使用 PowerShell cmdlet 通过 WinRM 从 Active Directory 组的设备中远程收集信息。 您还可以使用 `Get-AD Computer` cmdlet 并获取目录中包含的特定硬件型号名称的筛选结果。 在继续之前，请确认这些先决条件，然后继续。

**若要使用 Active Directory PowerShell 脚本方法：**

1. 确保启用了 WinRM。
1. 你想要注册的设备在网络中处于活动状态。 也就是说，它们不会断开连接或关闭。
1. 确保你有一个域凭据参数，该参数有权在设备上远程执行。
1. 确保Windows防火墙允许访问 WMI。 为此，请执行以下步骤：

    - 打开"**Windows Defender防火墙**"控制面板，然后选择"允许应用或功能通过Windows Defender **防火墙"**。
    - 在 **列表中Windows Management Instrumentation (WMI**) ，同时启用 **"** 专用"和"公用"，然后选择"确定 **"**。
1. 使用管理权限打开 PowerShell 提示符。
1. 运行 *以下任* 一脚本：

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

1. 访问可能有设备条目的任何目录。 从所有目录中删除每台设备的条目，Windows Server Active Directory域服务和Azure Active Directory。 可能需要几个小时才能完全处理。
1. 访问管理服务，其中可能有设备条目。 从所有管理服务中删除每台设备的条目，包括 Microsoft Endpoint Configuration Manager、Microsoft Intune 和 Windows Autopilot。 可能需要几个小时才能完全处理。

现在，你可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。

#### <a name="manual-powershell-script-method"></a>手动 PowerShell 脚本方法

**若要使用手动 Powershell 脚本方法：**

1. 使用管理权限打开 PowerShell 提示符。
2. 运行 `Install-Script -Name Get-WindowsAutoPilotInfo`。
3. 运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`。
4. [合并哈希数据。](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash drive 方法

**若要使用闪存驱动器方法，请执行以下操作：**

1. 在注册设备外的其他设备上，插入 USB 驱动器。
2. 使用管理权限打开 PowerShell 提示符。
3. 运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`。
4. 打开你要注册的设备，但不 *启动设置体验*。 如果意外启动设置体验，必须重置或重置设备映像。
5. 插入 USB 驱动器，然后按 Shift + F10。
6. 使用管理权限打开 PowerShell 提示符，然后运行 `cd <pathToUsb>`。
7. 运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`。
8. 运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`。
9. 删除 USB 驱动器，然后通过运行 关闭设备 `shutdown -s -t 0`。
10. [合并哈希数据。](#merge-hash-data)

> [!IMPORTANT]
> 完成注册之前，请勿再次打开要注册的设备。

### <a name="merge-hash-data"></a>合并哈希数据

如果通过手动 PowerShell 或闪存驱动器方法收集了硬件哈希数据，则必须将两个 CSV 文件中的数据合并到一个文件中才能完成注册。 下面是一个简单易行的示例 PowerShell 脚本：

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

将哈希数据合并到一个 CSV 文件中后，现在可以继续 [注册设备](#register-devices-by-using-the-admin-portal)。

## <a name="register-devices-by-using-the-admin-portal"></a>使用管理门户注册设备

在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)**中，选择** 左侧导航窗格中的"设备"。 在"Microsoft 托管桌面部分中，选择 **"设备"**。 在Microsoft 托管桌面设备"工作区中，选择 **" +** 注册设备"，这将打开一个飞入以注册新设备。

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age.](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

**若要使用管理门户注册设备：**

1. 在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。
2. 在 [下拉菜单中选择](../service-description/profiles.md) 设备配置文件。
3. 选择 **注册设备**。 系统会将设备添加到"设备"边栏选项卡上的 **设备列表中**。 设备标记为"正在 **注册"**。 注册通常少于 10 分钟，如果成功，设备将显示为"为用户 **准备就绪"**。 **Ready for user** means it's ready and waiting for a user to start using.

> [!NOTE]
> 如果手动更改设备Azure Active Directory (AAD) 组成员身份，系统会自动将其重新分配给设备配置文件的组，并删除任何冲突组。

你可以监视主页上的设备注册进度。 报告的可能状态包括：

| 状态 | 说明 |
| ----- | ----- |
| Registration Pending | 注册尚未完成。 请稍后再查看。 |
| 注册失败 | 无法完成注册。 有关详细信息，请参阅 [设备注册疑难解答](#troubleshooting-device-registration)。 |
| 为用户准备就绪 | 注册成功。 设备现在已准备好传递给用户。 Microsoft 托管桌面指导用户完成首次设置，因此无需执行任何进一步准备。 |
| 活动 | 设备已传递给用户，并且已在租户中注册。 此状态还指示他们定期使用设备。 |
| 非活动 | 设备已传递给用户，并且已在租户中注册。 但是，用户在最近七天内 (使用过该设备) 。 |

### <a name="troubleshooting-device-registration"></a>设备注册疑难解答

| 错误消息 | 详细信息 |
| ----- | ----- |
| 未找到设备 | 我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。 与设备供应商确认这些值。 |
| 硬件哈希无效 | 你为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希，然后重新提交。 |
| 设备已注册 | 此设备已注册到你的组织。 无需执行其他操作。 |
| 由另一个组织声明的设备 | 此设备已被另一个组织声明。 请与设备供应商联系。 |
| 意外错误 | 无法自动处理你的请求。 联系支持人员并提供请求 ID： `<requestId>` |

## <a name="check-the-image"></a>检查图像

如果你的设备来自合作伙伴Microsoft 托管桌面，则映像应该正确。

如果愿意，也欢迎您自行应用该图像。 To get started， contact the Microsoft representative you're working with and they'll provide you the location and steps for applying the image.

## <a name="deliver-the-device"></a>交付设备

> [!IMPORTANT]
> 在将设备交还给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。

如果应用所有许可证，你可以 [让用户准备好使用设备](get-started-devices.md)。 然后，你的用户可以启动设备并继续执行Windows设置体验。
