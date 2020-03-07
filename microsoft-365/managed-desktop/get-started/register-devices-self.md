---
title: 自行注册新设备
description: 自己注册设备，以便它们可以由 Microsoft 托管桌面管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d4ca01e7b791dafc952b62a5f5dd59263b31546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557550"
---
# <a name="register-new-devices-yourself"></a>自行注册新设备

Microsoft 托管桌面可以与全新设备配合使用，也可以重新使用可能已有的设备（这将需要您对其进行重新映像）。 您可以使用 Azure 门户上的 Microsoft 托管桌面注册设备。

> [!NOTE]
> 与合作伙伴合作获取设备？ 如果是这样，则无需担心获取硬件哈希值。他们将为你负责。 请确保您的合作伙伴在 [合作伙伴中心](https://partner.microsoft.com/dashboard)建立与您的关系，并确保它们包含 Azure Active Directory 和 Office 365 的委派管理权限。 你的合作伙伴可以在 [合作伙伴中心帮助](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)中了解详细信息。 建立此关系后，你的合作伙伴将代表你直接注册设备–无需进一步操作。 如果您想要查看详细信息，或者您的合作伙伴有问题，请参阅[合作伙伴注册设备的步骤](register-devices-partner.md)。 注册设备后，可以继续[检查映像](#check-the-image)并将[设备传递](#deliver-the-device)给用户。

## <a name="prepare-to-register-brand-new-devices"></a>准备注册全新的设备


准备好新设备后，请按照以下步骤操作：

1. [获取每个设备的硬件哈希。](#obtain-the-hardware-hash)
2. [合并哈希数据](#merge-hash-data)
3. [在 Microsoft 托管桌面中注册设备](#register-devices)。
4. [请仔细检查图像是否正确。](#check-the-image)
5. [传递设备](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>获取硬件哈希

Microsoft 托管桌面通过引用其硬件哈希来唯一标识每个设备。 有三个选项可用于获取此信息：

- 向 OEM 提供商咨询 AutoPilot 注册文件，其中将包含硬件哈希值。
- 在每台设备上运行[Windows PowerShell 脚本](#powershell-script-method)，并收集文件中的结果。
- 启动每个设备--但不完成 Windows 安装程序体验，并[收集可移动闪存驱动器上的哈希值](#flash-drive-method)。

#### <a name="powershell-script-method"></a>PowerShell script 方法

1.  打开具有管理权限的 PowerShell 提示。
2.  以`Install-Script -Name Get-MMDRegistrationInfo`
3.  以`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

#### <a name="flash-drive-method"></a>闪存驱动器方法

1. 在要注册的设备以外的其他设备上，插入 u 盘。
2. 打开具有管理权限的 PowerShell 提示。
3. 以`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. 打开要注册的设备，但*不要启动安装程序体验*。 如果您意外启动了设置体验，则必须重置或重新映像设备。
5. 插入 u 盘，然后按 SHIFT + F10。
6. 打开具有管理权限的 PowerShell 提示符，然后运行`cd <pathToUsb>`。
7. 以`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 以`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. 删除 USB 驱动器，然后通过运行来关闭设备`shutdown -s -t 0`

>[!IMPORTANT]
>在完成注册后，请不要再打开要注册的设备。 


### <a name="merge-hash-data"></a>合并哈希数据

您需要将 CSV 文件中的数据组合到单个文件中才能完成注册。 下面是一个示例 PowerShell 脚本，可轻松实现此操作：

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a>注册设备

CSV 文件必须为注册的特定格式。 如果您在前面的步骤中收集数据，则该文件应具有正确的格式;如果从供应商获取文件，则可能需要调整格式。

>[!NOTE]
>为方便起见，可以下载[示例 CSV 文件](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)。

您的文件需要包含与示例1（制造商、模型等）**完全相同的列标题**，但您自己的数据用于其他行。 如果使用模板，请在文本编辑工具（如记事本）中打开它，并考虑仅保留第1行中的所有数据，仅在第2行和更低的行中输入数据。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>如果您忘记更改任何示例数据，则注册将失败。

#### <a name="register-devices-by-using-the-azure-portal"></a>使用 Azure 门户注册设备

在 Microsoft 托管桌面[Azure 门户](https://aka.ms/mmdportal)中，在左侧导航窗格中选择 "**设备**"。 选择 **+ 注册设备**;将打开 "飞入"：

[![选择注册设备后飞入，列出分配的用户的列设备、序列号、状态、上次查看日期和期限](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (遗憾的是这不成立。我们可以删除此注释-但现在将其保留，直到我们有机会聊天它。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


请按以下步骤操作：

1. 在 "**文件上载**" 中，提供以前创建的 CSV 文件的路径。
2. （可选）可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。 这些值没有格式要求。
3. 选择 "**注册设备**"。 系统会将设备添加到**设备边栏**上的设备列表中，并标记为 "**注册挂起**"。 注册通常需要不到10分钟的时间，如果成功，设备将显示为 "已**准备就绪**，以供用户使用"，表示它已准备就绪，正在等待最终用户开始使用。


你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。 可能报告的状态包括：

| 状态 | 说明 |
|---------------|-------------|
| 注册挂起 | 注册尚未完成。 稍后再次查看。 |
| 注册失败 | 无法完成注册。 有关详细信息，请参阅[设备注册故障排除](#troubleshooting-device-registration)。 |
| 为用户准备就绪 | 注册成功，现在设备已准备好传递给最终用户。 Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。 |
| 活动 | 设备已传递给最终用户，并且已向其注册了你的租户。 这也表明它们是定期使用设备的。 |
| 不再 | 设备已传递给最终用户，并且已向其注册了你的租户。 但是，他们最近未使用设备（最近7天）。  | 

#### <a name="troubleshooting-device-registration"></a>设备注册故障排除

| 错误消息 | 详细信息 |
|---------------|-------------|
| 找不到设备 | 无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。 请与设备供应商确认这些值。 |
| 硬件哈希无效 | 为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希，然后重新提交。 |
| 已注册设备 | 此设备已注册到你的组织。 无需执行进一步操作。 |
| 其他组织声明的设备 | 此设备已由其他组织声明。 请与设备供应商联系。 |
| 意外错误 | 无法自动处理你的请求。 联系支持人员并提供请求 ID：<requestId> |

### <a name="check-the-image"></a>检查图像

如果你的设备来自 Microsoft 托管桌面合作伙伴提供商，则该映像应正确。

如果你愿意，也可以在自己自己应用图像。 若要开始，请联系你正在使用的 Microsoft 代表，他们将为你提供应用此图像的位置和步骤。

### <a name="deliver-the-device"></a>传递设备

> [!IMPORTANT]
> 在将设备交给用户之前，请确保已为该用户获取并应用了[相应的许可证](../get-ready/prerequisites.md)。

如果应用了所有许可证，则可以[让用户准备好使用设备](get-started-devices.md)，然后你的用户可以启动设备并继续执行 Windows 安装体验。






