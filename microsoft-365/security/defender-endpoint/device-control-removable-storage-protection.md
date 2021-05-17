---
title: Microsoft Defender for Endpoint 设备控制可移动存储保护
description: 了解有助于防止用户或计算机或两者使用未经授权的可移动存储媒体的功能
keywords: 可移动存储媒体
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300119"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint 设备控制可移动存储保护

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint 设备控制 可移动存储保护可防止用户或计算机或两者使用未经授权的可移动存储媒体。

**适用于终结点可移动存储保护的 Microsoft Defender**


|策略  |功能 |说明  |
|---------|---------|---------|
|设备安装    |  阻止安装（带排除或不排除） - 允许基于各种属性的特定设备;有关详细信息，请参阅下面的 [设备属性](#device-properties) 部分。        |    适用于计算机：同一策略将限制登录到同一台计算机的不同用户。 有关信息，请参阅 [如何使用 Microsoft Defender for Endpoint](control-usb-devices-using-intune.md)控制 USB 设备和其他可移动媒体。     |
|可移动存储访问控制      |  (1) 基于各种设备属性对可移动存储执行审核读取或写入或执行访问，有或无例外。 有关详细信息，请参阅下面的 [设备属性](#device-properties) 部分。  (2) 阻止读取或写入或执行访问（带或不排除 ） - 允许基于各种设备属性的特定设备;有关设备属性的详细信息，请参阅下面的 [设备属性](#device-properties) 部分。     |     适用于计算机或用户或两者：仅允许对特定计算机上特定可移动存储执行读/写/执行访问的特定人员;有关 Windows 中的功能，请参阅 [可移动存储访问控制](device-control-removable-storage-access-control.md);有关 Mac 中的功能，请参阅 [macOS 的设备控件](mac-device-control-overview.md)。     |
|终结点 DLP 可移动存储      |    审核或警告用户或阻止用户将项目或信息复制到可移动媒体或 USB 设备。     |  有关详细信息，请参阅[Microsoft Endpoint DLP。](/compliance/endpoint-dlp-learn-about.md)       |
|BitLocker    |     阻止要写入到不受 BitLocker 保护的可移动驱动器的数据：除非在组织拥有的计算机上对可移动驱动器进行了加密，否则阻止访问可移动驱动器。    |   有关详细信息，请参阅 BitLocker – [可移动驱动器设置](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md)。      |

## <a name="device-properties"></a>设备属性

Microsoft Defender for Endpoint 设备控制 可移动存储保护允许你根据下表中描述的属性限制可移动存储访问：


|属性名  |适用的策略  |适用于操作系统  |说明  |
|---------|---------|---------|---------|
|设备类    |     [如何使用 Microsoft Defender for Endpoint 控制 USB 设备和其他可移动媒体](control-usb-devices-using-intune.md)     |   Windows      |  有关设备 ID 格式的信息，请参阅 [设备设置类](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。 **注意**：设备安装可以应用于任何设备，而不仅是可移动存储。       |
|主 ID   |     可移动存储访问控制    |   Windows      |      主 ID 包括可移动存储和 CD/DVD。   |
|设备 ID     |  如何使用 Microsoft Defender for Endpoint 控制[USB 设备和其他可移动媒体](control-usb-devices-using-intune.md);可移动存储访问控制       |      Windows   |    有关设备 ID 格式的信息，请参阅标准 [USB](/windows-hardware/drivers/install/standard-usb-identifiers)标识符，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|硬件 ID     |     如何使用 Microsoft Defender for Endpoint 控制[USB 设备和其他可移动媒体](control-usb-devices-using-intune.md);可移动存储访问控制    |     Windows    |    一个标识系统中设备的字符串，例如 USBSTOR\DiskGeneric_Flash_Disk______8.07; **注意**：硬件 ID 不是唯一的;不同设备可能共享相同的值。|
|实例 ID    | 设备安装;可移动存储访问控制     |     Windows    |   唯一标识系统中设备的字符串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|友好名称     |     可移动存储访问控制    |   Windows      |    附加到设备的字符串，例如通用闪存磁盘 USB 设备     |
|供应商 ID/产品 ID     |  可移动存储访问控制       |   Windows Mac      |     供应商 ID 是 USB 委员会分配给供应商的四位数供应商代码。 产品 ID 是供应商分配给设备的四位数产品代码;支持通配符。    |
|Serial NumberId     |     可移动存储访问控制    |      Windows Mac   |     例如 <SerialNumberId>，002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>相关主题

- [Microsoft Defender for Endpoint 设备控制可移动存储访问控制](device-control-removable-storage-access-control.md)
