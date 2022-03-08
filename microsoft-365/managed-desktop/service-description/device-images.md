---
title: 设备图像
description: 订购新设备或重新使用现有设备时的图像要求
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
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
ms.openlocfilehash: f1d00c12512b70ffd62372aaeae787acf1911573
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330281"
---
# <a name="device-images"></a>设备图像

无论你是[订购新](#new-devices)设备还是重复使用现有[](#existing-devices)设备，你都有若干选项来确保设备上的图像符合我们的[设备要求](device-requirements.md#check-hardware-requirements)。

## <a name="new-devices"></a>新设备

当你从批准的制造商订购新设备时[](device-requirements.md#minimum-requirements)，请按照以下步骤操作，以确保它们随正确的映像和软件配置Microsoft 托管桌面设备。

每当计划首次在服务中注册特定设备型号时，都应该测试一个示例以确保它将提供你期望的用户体验。 有关详细信息，请参阅验证 [新设备](/microsoft-365/managed-desktop/get-started/validate-device)。

### <a name="dell"></a>Dell

直接与 Dell 销售代表合作。

代表将确保你的订单中Microsoft 托管桌面批准的映像应用到设备。 有关 Dell 设备、映像和订购过程的信息，请与 MMD_at_dell@dell.com。

### <a name="hp"></a>HP

当你从 HP 订购新设备时，请务必使用购买商业版设备页面找到的每个型号的"其他要求"部分中列出的Windows Pro [SKU](https://www.microsoft.com/windows/business/devices#view-all-filter)。 筛选视图以列出Microsoft 托管桌面设备。

如果从 HP 订购的设备已被批准为异常，但当前未在"[](customizing.md)设备列表"页上列出，请请求 SKU 以用于你的型号。 我们将与 HP 合作，通过异常请求获取此信息。 对于有关设备和设备订购说明的任何问题，还可使用这些地址直接与 HP 联系：

- 美洲：mmd-americas@hp.com
- 欧洲/中东/非洲：mmd-emea@hp.com
- 亚太地区/日本：mmd-apj@hp.com
- 全局：mmd@hp.com

### <a name="lenovo"></a>联想

从 Lenovo 订购设备时，必须按顺序指示特定部件号。 请与 Lenovo 销售代表或 Lenovo 渠道合作伙伴联系，让他们使用符合我们的设备要求的系统创建"特殊报价[模型"](device-requirements.md#minimum-requirements)。

若要包含与 Microsoft 托管桌面 兼容的预加载映像，请让销售代表引用"系统构建基块部件号 *SBB0Q94938 - MMD Enablement*"。 与 Lenovo 销售代表或 Lenovo 渠道合作伙伴合作，获得推荐的服务、支持和映像服务。

### <a name="microsoft"></a>Microsoft

满足设备要求的所有 Microsoft 设备都提供与设备Microsoft 托管桌面。 无需执行其他步骤。

若要在 Microsoft 设备上获取工厂中提供的最新映像，请与 Surface 专家一起使用 Surface"已打开的 PO"流程。

## <a name="existing-devices"></a>现有设备

你可以重复使用现有设备，只要它们同时满足两个条件：

- [设备要求](device-requirements.md#minimum-requirements)
- [软件要求](device-requirements.md#installed-software)

按照与制造商相关的步骤操作。

你可以为设备重新映像，使用制造商提供的映像，或通过使用Microsoft 托管桌面映像"。 若要获取相应的制造商映像，请至少订购一台[](#new-devices)您重新使用的模型的新设备。 然后，你可以从该设备获取图像，并应用到完全相同型号的其他设备。

> [!NOTE]
> 你负责创建、测试和部署映像。 我们还建议尽可能使用制造商提供的适当映像，而不是自定义映像;这包括"通用映像"。

### <a name="hp"></a>HP

HP Corporate Ready Image 附带的 HP 商业电脑包含用于 `.WIM` 恢复的文件。 可以使用此映像将工厂还原映像应用于相同模型的其他设备。

以下步骤将删除设备上的所有数据。 在启动之前，应备份要保留的任何数据。

**若要删除设备上的数据，请运行以下操作：**

1. 使用 WinPE [创建可启动 USB](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) 驱动器。
2. 将这些文件从复制到 `C:\\SOURCES` USB 驱动器：
    - 出厂恢复 WIM 文件 (例如， `HP\_EliteBook\_840\_G7\_Notebook\_PC\_CR\_2004.wim`) 
    - `DEPLOY.CMD`
    - `ReCreatePartitions.txt`
3. [将设备启动到 WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB 驱动器。
4. 在命令提示符中，运行 [Diskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references)。
5. 在 Diskpart 中， `list disk`运行 ，然后记下主存储磁盘 (，磁盘 0) 。
6. 通过键入 退出 `exit`Diskpart。
7. 在命令提示符 `deploy.cmd <sys_disk> <recovery_wim>`中，运行 ，其中 `sys_disk` `recovery_wim` `.WIM` 是确定的主存储磁盘的磁盘号，是之前复制的文件的文件名。
8. 删除 USB 驱动器，然后重新启动设备。

### <a name="microsoft"></a>Microsoft

Microsoft Surface 设备包括特定于每个型号的"裸[](https://support.microsoft.com/en-us/surfacerecoveryimage)机恢复"映像。 可以使用这些图像为设备重新创建映像。

这些映像使用 Windows Re (恢复) 。 这是手动过程， (自动化) 。 按照为 [Surface 创建和使用 USB 恢复驱动器中的步骤操作](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)。

### <a name="universal-image"></a>通用映像

Microsoft 托管桌面已创建一个图像，其中包含Windows Pro Microsoft 365 应用版Enterprise可用于其他Microsoft 托管桌面。

但是，最好尽可能使用适合制造商Microsoft 托管桌面的图像，即使这意味着用户登录后必须更新较旧的 Windows 版本。 使用Microsoft 托管桌面通用映像应为最终选项。

- 我们每 30 Windows 60 天更新一次最新质量更新的图像，Microsoft 365 应用版更新Enterprise每年更新两次。
- 映像包含恢复预配包，以确保Microsoft 365 应用版恢复Enterprise恢复Windows恢复。
- 可以使用 USB 驱动器部署映像。 它包含用于插入驱动程序的可编脚本的过程。 图像中包含的文档中概述了此过程。
- 可以使用其他自定义项（如添加特定的累积更新、文件复制代码或执行其他检查）修改包含的脚本和文件夹。
- 驱动程序和质量更新将添加到Windows U 盘部署期间。

> [!NOTE]
> 你有责任添加所有必要的驱动程序，执行所有测试，并确保最终部署的映像没有问题。 我们提供"即点即用"的通用映像，但将提供技术指南和解答问题。 联系 MMDImage@microsoft.com。

通过创建更改请求将通用映像内容和文档提交请求到 [管理门户](../get-started/access-admin-portal.md)。
