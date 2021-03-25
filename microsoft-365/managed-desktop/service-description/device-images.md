---
title: 设备映像
description: 订购新设备或重新使用现有设备时的图像要求
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
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
ms.openlocfilehash: 9a263cbc6bdd0d521e835f086967a6f7236c6948
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166432"
---
# <a name="device-images"></a>设备映像


无论你是 [订购新](#new-devices) 设备 [还是重复使用现有](#existing-devices) 设备，你都有若干选项来确保设备上的图像满足我们的 [设备要求](device-requirements.md#check-hardware-requirements)。

## <a name="new-devices"></a>新设备
当你从已批准的制造商订购新设备[](device-requirements.md#minimum-requirements)时，请按照以下步骤操作，以确保它们提供的设备具有正确的 Microsoft 托管桌面映像和软件配置。

### <a name="dell"></a>Dell
直接与 Dell 销售代表合作，他们将确保 Microsoft 托管桌面批准的映像适用于你的订单的设备。 有关 Dell 设备、映像和订购流程的更多问题，请与 MMD_at_dell@dell.com。

### <a name="hp"></a>HP 
当你从 HP 订购新设备时，请确保使用每个型号的其他要求部分中列出的特定 SKU，如程序 [设备中所示](device-list.md#hp)。

如果从 HP 订购的设备已被批准为异常，但当前未[](customizing.md)在"设备列表"页上列出，请务必请求 SKU 以用于你的型号。 我们将与 HP 合作，通过异常请求获取此信息。 对于有关设备和设备订购说明的任何问题，还可使用这些地址直接与 HP 联系：
 
- 美洲：mmd-americas@hp.com
- 欧洲/中东/非洲：mmd-emea@hp.com
- 亚太地区/日本：mmd-apj@hp.com
- 全局：mmd@hp.com

### <a name="lenovo"></a>联想
当你从 Lenovo 订购设备以用于 Microsoft 托管桌面时，你需要指示作为订单的一部分包含的特定部件号。 请与 Lenovo 销售代表或 Lenovo 渠道合作伙伴联系，让他们使用符合我们的设备要求的系统创建"特殊报价[模型"。](device-requirements.md#minimum-requirements) 若要包含与 Microsoft 托管桌面兼容的预加载映像，请让销售代表参考" 系统构建基块部件号 *SBB0Q94938 – MMD Enablement*"。

以下产品当前已启用 Microsoft 托管桌面支持：

- L13 Gen 1
- L13 Gen 1
- L14 Gen 1 (Intel) 
- L14 Gen 1 (AMD) 
- L15 Gen 1 (Intel) 
- L15 Gen 1 (AMD) 
- X1 二代
- X1 Gen 5
- T14 Gen 1 (Intel) 
- T14 Gen 1 (AMD) 
- T15 Gen 1
- X13 Gen 1 (Intel) 


### <a name="microsoft"></a>Microsoft
满足设备要求的所有 Microsoft 设备都提供与 Microsoft 托管桌面一起运行的图像。 无需执行其他步骤。

若要在 Microsoft 设备上获取工厂中提供的最新映像，请与 Surface 专家一起使用 Surface"已打开的 PO"流程。

## <a name="existing-devices"></a>现有设备

你可以重复使用现有设备，只要它们同时满足设备  [要求](device-requirements.md#minimum-requirements) 和软件 [要求](device-requirements.md#installed-software)。 按照与制造商相关的步骤操作。

可以使用制造商的图像或 Microsoft 托管桌面"通用映像"对设备重新映像。 若要获取相应的制造商映像，你可以订购至少一台要重新[](#new-devices)使用的模型的新设备。 然后，你可以从该设备获取图像，并应用到完全相同型号的其他设备。

> [!NOTE]
> 你负责创建、测试和部署映像。 我们还建议尽可能使用制造商提供的适当映像，而不是自定义映像，包括"通用映像"。

### <a name="hp"></a>HP

HP 企业就绪映像附带的 HP 商业电脑包括 。用于恢复的 WIM 文件。 可以使用此映像将工厂还原映像应用于相同模型的其他设备。

这些步骤将删除设备上的所有数据，因此在启动之前，你应该备份要保留的任何数据。

1. 使用 WinPE[创建可启动 USB](https://docs.microsoft.com/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive)驱动器。
2. 将这些文件从 C： \\ SOURCES 复制到 USB 驱动器：
    - 出厂恢复 WIM 文件 (例如 HP \_ EliteBook \_ 840 \_ G7 \_ 笔记本 \_ 电脑 CR \_ \_ 2004.wim) 
    - 部署。CMD
    - ReCreatePartitions.txt
3. [将设备启动到 WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB 驱动器。
4. 在命令提示符中， [ 运行 ](https://docs.microsoft.com/windows-server/administration/windows-commands/diskpart#additional-references)Diskpart.exe。
5. 在 Diskpart 中，运行 ，然后记下主 `list disk` 存储磁盘 (，磁盘 0) 。
6. 通过键入 退出 `exit` Diskpart。
7. 在命令提示符中，运行 ，其中 sys_disk 是刚确定的主存储磁盘的磁盘号，recovery_wim是 的 `deploy.cmd <sys_disk> <recovery_wim>` 文件名。  你之前复制的 WIM 文件。
8. 删除 USB 驱动器，然后重新启动设备。

### <a name="microsoft"></a>Microsoft 

Microsoft Surface 设备包括特定于每个型号的[](https://support.microsoft.com/en-us/surfacerecoveryimage)"裸机恢复"映像。 可以使用这些图像为设备重新创建映像。

这些映像使用 Windows 恢复 (WinRE) 这是一个手动过程， (自动化) 。 按照为 [Surface 创建和使用 USB 恢复驱动器中的步骤操作](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)。


### <a name="universal-image"></a>通用映像
Microsoft 托管桌面已创建一个映像，其中包含可用于 Microsoft 托管桌面的 Windows 10 专业版和 Microsoft 365 企业应用版。 但是，最好尽可能使用适合制造商提供的 Microsoft 托管桌面的图像，即使这意味着较旧的 Windows 版本需要在用户登录后更新。 使用 Microsoft 托管桌面通用映像应该是最终的选择。

- 我们每 30-60 天更新一次最新 Windows 每月质量更新的图像，Microsoft 365 企业应用版更新至少每年更新两次。
- 该映像包含一个恢复预配包，以确保 Microsoft 365 企业应用版按照 Windows 恢复方案还原。
- 可以使用 USB 驱动器部署映像。 它包含一个可编脚本的过程，用于插入驱动程序 (映像包中包含的文档中概述了) 。
- 你可以修改包含的脚本和文件夹，以用于其他自定义项，例如添加特定的累积更新、文件复制代码或执行其他检查。
- 驱动程序和质量更新在从 USB 驱动器部署期间添加到 Windows。

> [!NOTE]
> 你有责任添加所有必要的驱动程序，执行所有测试，并确保最终部署的映像没有问题。 我们提供"即点即用"的通用映像，但将提供技术指南和解答问题。 联系 MMDImage@microsoft.com。

在管理门户上创建更改请求，提交通用图像内容和 [文档请求](../get-started/access-admin-portal.md)。


