---
title: 自行注册新设备
description: 自己注册设备，以便它们可以通过 Microsoft 托管桌面进行管理
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 4de1d173a26005d32fb07117d93ee78582b77d54
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689205"
---
# <a name="register-new-devices-yourself"></a>自行注册新设备

Microsoft 托管桌面可以与全新的设备一起工作，或者你可以重复使用你可能已有的设备 (这将要求你重新映像它们) 。 可以在 Microsoft Endpoint Manager 门户中向 Microsoft 托管桌面注册设备。

> [!NOTE]
> 与合作伙伴合作获取设备 如果是这样，你无需担心获取硬件哈希;他们会负责你。 请确保你的合作伙伴与你在合作伙伴中心 [建立了关系](https://partner.microsoft.com/dashboard)。 你的合作伙伴可以在合作伙伴中心 [帮助 中了解更多信息](/partner-center/request-a-relationship-with-a-customer)。 建立此关系后，你的合作伙伴将仅代表你注册设备，无需你执行任何进一步的操作。 如果你希望查看详细信息，或者你的合作伙伴有疑问，请参阅合作伙伴注册 [设备的步骤](register-devices-partner.md)。 注册设备后，你可以继续 [检查](#check-the-image) 映像，将设备 [传送](#deliver-the-device) 给用户。

## <a name="prepare-to-register-brand-new-devices"></a>准备注册全新的设备


拥有新设备后，你将按照以下步骤操作：

1. [获取每台设备的硬件哈希。](#obtain-the-hardware-hash)
2. [合并哈希数据](#merge-hash-data)
3. [在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。
4. [仔细检查图像是否正确。](#check-the-image)
5. [交付设备](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>获取硬件哈希

Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。 有三个选项可获取此信息：

- 请你的 OEM 供应商提供 AutoPilot 注册文件，该文件将包含硬件哈希。
- 在每个 [Windows PowerShell](#powershell-script-method) 运行一个脚本，并收集文件中的结果。
- 启动每台设备（但不完成 Windows 设置体验）并收集可移动闪存 [驱动器上的哈希](#flash-drive-method)。

#### <a name="powershell-script-method"></a>PowerShell 脚本方法

可以在 PowerShell [ 库Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell 脚本。 有关设备标识和硬件哈希的信息，请参阅 [将设备添加到 Windows Autopilot](/mem/autopilot/add-devices#device-identification)。

1.  使用管理权限打开 PowerShell 提示符。
2.  运行 `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  运行 `powershell -ExecutionPolicy restricted` 以防止后续不受限制的脚本运行。


#### <a name="flash-drive-method"></a>Flash drive 方法

1. 在注册设备外的其他设备上，插入 USB 驱动器。
2. 使用管理权限打开 PowerShell 提示符。
3. 运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 打开你要注册的设备， *但不启动设置体验*。 如果意外启动设置体验，必须重置或重置设备映像。
5. 插入 USB 驱动器，然后按 Shift + F10。
6. 使用管理权限打开 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。
7. 运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. 删除 USB 驱动器，然后通过运行来关闭设备 `shutdown -s -t 0`

>[!IMPORTANT]
>完成注册之前，请勿再次打开要注册的设备。 


### <a name="merge-hash-data"></a>合并哈希数据

你需要将 CSV 文件中的数据合并到单个文件中才能完成注册。 下面是一个简单易行的示例 PowerShell 脚本：

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>使用管理门户注册设备

在[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)中，选择左侧导航窗格中的"设备"。  查找菜单的"Microsoft 托管桌面"部分，然后选择"**设备"。** 在 Microsoft 托管桌面设备工作区中，选择 **+ 注册设备**，这将打开一个飞入以注册新设备。

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


请按以下步骤操作：

1. 在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。
2. 在 [下拉菜单中选择](../service-description/profiles.md) 设备配置文件。
3. 选择 **注册设备**。 系统将设备添加到设备上设备列表，标记为注册 **挂起。**  注册通常少于 10 分钟，并且成功后，设备将显示为"为用户准备就绪"，这意味着它已准备好并等待用户开始使用。

> [!NOTE]
> 如果你手动将 Azure Active Directory (AAD) 设备组成员身份，它将自动重新分配到组，用于其设备配置文件，并删除任何冲突组。

你可以监视主页上的设备注册进度。 其中报告的可能状态包括：

| 状态 | 说明 |
|---------------|-------------|
| Registration Pending | 注册尚未完成。 请稍后再查看。 |
| 注册失败 | 无法完成注册。 有关详细信息 [，请参阅设备](#troubleshooting-device-registration) 注册疑难解答。 |
| 为用户准备就绪 | 注册成功，设备现在已准备好传递给用户。 Microsoft 托管桌面将指导用户完成首次设置，因此无需执行任何进一步准备。 |
| 活动 | 设备已传递给用户，并且他们已在租户中注册。 此状态还指示他们定期使用设备。 |
| 非活动 | 设备已传递给用户，并且他们已在租户中注册。 但是，他们在最近 7 天内 (使用过该设备) 。  | 

#### <a name="troubleshooting-device-registration"></a>设备注册疑难解答

| 错误消息 | 详细信息 |
|---------------|-------------|
| 未找到设备 | 我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。 与设备供应商确认这些值。 |
| 硬件哈希无效 | 你为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希，然后重新提交。 |
| 设备已注册 | 此设备已注册到你的组织。 无需执行其他操作。 |
| 由另一个组织声明的设备 | 此设备已被另一个组织声明。 请与设备供应商联系。 |
| 意外错误 | 您的请求无法自动处理。 联系支持人员并提供请求 ID： <requestId> |

### <a name="check-the-image"></a>检查图像

如果你的设备来自 Microsoft 托管桌面合作伙伴供应商，则映像应该正确。

如果愿意，也欢迎您自行应用该图像。 To get started， contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.

### <a name="autopilot-group-tag"></a>Autopilot 组标记

当你使用管理门户注册设备时，我们会自动分配Microsoft365Managed_Autopilot **Autopilot** 组标记。
该服务每天监视所有 Microsoft 托管桌面设备，并将组标记分配给任何尚未安装组标记的设备。

### <a name="deliver-the-device"></a>交付设备

> [!IMPORTANT]
> 在将设备交还给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。

如果应用所有许可证，你可以让用户准备好使用[](get-started-devices.md)设备，然后你的用户可以启动设备并继续 Windows 安装体验。
