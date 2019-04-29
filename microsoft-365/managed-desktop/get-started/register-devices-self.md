---
title: 自行在 Microsoft 托管桌面中注册设备
description: 自己注册设备, 以便它们可以由 Microsoft 托管桌面管理
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 02b3b7ab32ff92304ab27ca8e8c805ade803c971
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400066"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>在 Microsoft 托管桌面中注册设备

>[!NOTE]
>本主题介绍您自己注册设备的步骤。 在[面向合作伙伴的 Microsoft 托管桌面中的注册设备](register-devices-partner.md)中记录合作伙伴的过程。

Microsoft 托管桌面可以与全新设备配合使用, 也可以重新使用可能已有的设备 (这将需要您对其进行重新映像)。 您可以使用 Azure 门户上的 Microsoft 托管桌面注册设备, 也可以通过使用 API 获得灵活性。

## <a name="prepare-to-register-devices"></a>准备注册设备

如果还没有获得要使用的设备, 请检查[Microsoft 托管桌面设备](../service-description/device-list.md), 并与设备合作伙伴合作以购买支持的设备。

无论您是使用全新的设备还是重新使用现有设备, 若要使用 Microsoft 托管桌面注册它们, 都需要准备一个**逗号分隔 (CSV) 文件**。 此文件应包括每个设备的以下信息:

>[!NOTE]
>此格式仅用于自助注册。 在[面向合作伙伴的 Microsoft 托管桌面中的注册设备](register-devices-partner.md)中记录了合作伙伴应使用的格式。

这些值用于显示目的, 无需完全匹配设备的属性。
- 设备制造商 (示例: SpiralOrbit) 
- 设备模型 (示例: ContosoABC)
- 设备序列号

硬件哈希必须是完全匹配。
- 硬件哈希

若要获取硬件哈希, 可以从 OEM 或合作伙伴寻求帮助, 也可以对每个设备执行以下步骤:

1.  打开具有管理权限的 PowerShell 提示。
2.  以`Install-Script -Name Get-WindowsAutoPilotInfo`
3.  以`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`


或者, 您可以在全新设备上执行以下步骤 (在第一次进入 OOBE 之前):

1. 在其他设备上, 插入 u 盘。
2. 打开具有管理权限的 PowerShell 提示。
3. 以`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. 打开目标设备, 但不要启动安装程序体验。 如果您意外启动了设置体验, 则必须重置或重新映像设备。
5. 插入 u 盘, 然后按 SHIFT + F10。
6. 打开具有管理权限的 PowerShell 提示符, 然后运行`cd <pathToUsb>`。
7. 以`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 以`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
3. 删除 USB 驱动器, 然后通过运行来关闭设备`shutdown -s -t 0`

>[!IMPORTANT]
>在完成对目标设备的注册之前, 请勿再次打开目标设备。 

>[!NOTE]
>为方便起见, 可以下载此 CSV 文件的[模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。

您的文件需要包含与示例 1 (制造商、模型等)**完全相同的列标题**, 但您自己的数据用于其他行。 如果使用模板, 请在文本编辑工具 (如记事本) 中打开它, 并考虑仅保留第1行中的所有数据, 仅在第2行和更低的行中输入数据。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>如果您忘记更改任何示例数据, 则注册将失败。   


## <a name="register-devices-by-using-the-azure-portal"></a>使用 Azure 门户注册设备

在 Microsoft 托管桌面[Azure 门户](https://aka.ms/mmdportal)中, 在左侧导航窗格中选择 "**设备**"。 选择 **+ 注册设备**;将打开 "飞入":

[![选择注册设备后飞入](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (遗憾的是这不成立。我们可以删除此注释-但现在将其保留, 直到我们有机会聊天它。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


请按以下步骤操作：

1. 在 "**文件上载**" 中, 提供以前创建的 CSV 文件的路径。
2. (可选) 可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。 这些值没有格式要求。
3. 选择 "**注册设备**"。 系统会将设备添加到**设备边栏**上的设备列表中, 并标记为 "**注册挂起**"。 注册通常需要不到10分钟的时间, 如果成功, 设备将显示为 "已**准备就绪**, 以供用户使用", 表示它已准备就绪, 正在等待最终用户开始使用。


你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。 可能报告的状态包括:

| 状态 | 说明 |
|---------------|-------------|
| 注册挂起 | 注册尚未完成。 稍后再次查看。 |
| 注册失败 | 无法完成注册。 有关详细信息, 请参阅[故障排除](register-devices-self.md#troubleshooting)。 |
| 为用户准备就绪 | 注册成功, 现在设备已准备好传递给最终用户。 Microsoft 托管桌面将在首次设置时引导他们, 因此无需执行任何进一步的准备。 |
| 活动 | 设备已传递给最终用户, 并且已向其注册了你的租户。 这也表明它们是定期使用设备的。 |
| 不再 | 设备已传递给最终用户, 并且已向其注册了你的租户。 但是, 他们最近未使用设备 (最近7天)。  | 


## <a name="register-devices-by-using-an-api"></a>使用 API 注册设备

REST API 可用于实现更大的灵活性和重复频繁单独的设备注册。 目前, 若要使用 API, 请询问 Microsoft 联系人的帮助, 以加入此功能的预览。



## <a name="troubleshooting"></a>故障排除

| 错误消息 | 详细信息 |
|---------------|-------------|
| 找不到设备 | 无法注册此设备, 因为我们找不到提供的制造商、型号或序列号的匹配项。 请与设备供应商确认这些值。 |
| 找不到设备 | 无法注册此设备, 因为它在你的组织中不存在。 无需执行进一步操作。 |
| 硬件哈希无效 | 为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希, 然后重新提交。 |
| 已注册设备 | 此设备已注册到你的组织。 无需执行进一步操作。 |
| 其他组织声明的设备 | 此设备已由其他组织声明。 请与设备供应商联系。 |
| 意外错误 | 无法自动处理你的请求。 联系支持人员并提供请求 ID:<requestId> |




