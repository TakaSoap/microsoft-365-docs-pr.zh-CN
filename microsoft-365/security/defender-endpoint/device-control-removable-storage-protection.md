---
title: Microsoft Defender for Endpoint设备控制可移动存储保护
description: 了解"有助于防止用户或计算机或同时使用未经授权的可移动存储介质的功能
keywords: 可移动存储介质
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3d679cfa4f09b06e2c7923ee1fe6e47247d90f76
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665065"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint设备控制可移动存储保护


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint中的设备控制可移动存储保护可阻止用户、终结点或两者都使用未经授权的可移动存储介质。

## <a name="protection-policies"></a>保护策略

### <a name="removable-storage-access-control"></a>可移动存储访问控制

**Capabilities**

- *审计* 读取或写入或执行基于各种设备属性（无论是否排除）对可移动存储的访问。
- *防止* 读取或写入或执行具有或不带排除项的访问 - 允许基于各种设备属性的特定设备。

**Windows 10和Windows 11支持详细信息**：

- 在设备级别（用户级别）应用。 或两者兼有。 仅允许对特定计算机上的特定可移动存储执行读/写/执行访问权限的特定人员。
- 支持 MEM OMA-URI 和 GPO。
- 列出支持的"[设备属性](#device-properties)"。
- 有关Windows中的功能，请参阅[可移动存储访问控制](device-control-removable-storage-access-control.md)。

**支持的平台** - Windows 10、Windows 11

**macOS 支持详细信息**：

- 在设备级别应用：同一策略适用于任何登录用户。
- 有关特定于 macOS 的信息，请参阅 [macOS 的设备控件](mac-device-control-overview.md)。

**支持的平台** - 已启用系统扩展的 macOS Catalina 10.15.4+ () 


### <a name="device-installation"></a>设备安装

**功能** - 根据各种设备属性防止使用或不排除安装。

**Windows 10和Windows 11支持详细信息**：

- 在设备级别应用：同一策略适用于任何登录用户。
- 支持Microsoft Endpoint Manager和组策略对象。
- 列出支持的"[设备属性](#device-properties)"。
- 有关Windows的详细信息，请参阅[如何使用Microsoft Defender for Endpoint控制 USB 设备和其他可移动媒体](control-usb-devices-using-intune.md)。

**支持的平台** - Windows 10、Windows 11

**macOS 支持详细信息**：

- 在设备级别应用：同一策略适用于任何登录用户
- 有关特定于 macOS 的信息，请参阅 [macOS 的设备控件](mac-device-control-overview.md)。

**支持的平台** -) 或更高版本启用了系统扩展的 macOS Catalina 10.15.4+ (

### <a name="endpoint-dlp-removable-storage"></a>终结点 DLP 可移动存储

**功能** - 审核、警告或阻止用户将项目或信息复制到可移动媒体或 USB 设备。

**说明** - 有关Windows的详细信息，请 [参阅有关Microsoft 365终结点数据丢失防护的详细](../../compliance/endpoint-dlp-learn-about.md)信息。

**支持的平台** - Windows 10、Windows 11

### <a name="bitlocker"></a>BitLocker

**功能**：

- 阻止将数据写入不受 BitLocker 保护的可移动驱动器。
- 阻止对可移动驱动器的访问，除非它们已在组织拥有的计算机上加密

**说明** - 有关Windows的详细信息，请参阅 [BitLocker - 可移动驱动器设置](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)。

**支持的平台** - Windows 10、Windows 11

## <a name="device-properties"></a>设备属性

Microsoft Defender for Endpoint设备控制可移动存储保护允许根据下表中所述的属性限制可移动存储访问：

<br/><br/>

|属性名|适用的策略|适用于操作系统|说明|
|---|---|---|---|
|设备类|[如何使用Microsoft Defender for Endpoint控制 USB 设备和其他可移动媒体](control-usb-devices-using-intune.md)|Windows|有关设备 ID 格式的信息，请参阅 [设备设置类](/windows-hardware/drivers/install/overview-of-device-setup-classes)。 以下两个链接提供设备设置类的完整列表。 "系统使用"类主要指来自工厂的计算机/计算机的设备，而"供应商"类大多是指可以连接到现有计算机/计算机的设备：[可供供应商使用的系统定义设备安装程序类 - Windows驱动](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)程序和[为系统使用保留的系统定义设备安装程序类 - Windows驱动程序](/windows-hardware/drivers/install/system-defined-device-setup-classes-reserved-for-system-use)。 **注意**：设备安装可以应用于任何设备，而不仅仅是可移动存储。|
|主 ID|[可移动存储访问控制](device-control-removable-storage-access-control.md)|Windows|主 ID 包括可移动存储和 CD/DVD 以及Windows可移植设备/WPD。|
|设备 ID|[可移动存储访问控制](device-control-removable-storage-access-control.md); <p> [如何使用Microsoft Defender for Endpoint控制 USB 设备和其他可移动媒体](control-usb-devices-using-intune.md)|Windows|有关设备 ID 格式的信息，请参阅 [标准 USB 标识符](/windows-hardware/drivers/install/standard-usb-identifiers)，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07|
|硬件 ID|[可移动存储访问控制](device-control-removable-storage-access-control.md) <p> [如何使用Microsoft Defender for Endpoint控制 USB 设备和其他可移动媒体](control-usb-devices-using-intune.md)|Windows|在系统中标识设备的字符串，例如 USBSTOR\DiskGeneric_Flash_Disk___8.07; **注意**：硬件 ID 不是唯一的;不同的设备可能共享相同的值。|
|实例 ID|[可移动存储访问控制](device-control-removable-storage-access-control.md) <p> 设备安装|Windows|字符串唯一标识系统中的设备，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0|
|友好名称|[可移动存储访问控制](device-control-removable-storage-access-control.md)|Windows|附加到设备的字符串，例如泛型闪存磁盘 USB 设备|
|供应商 ID/产品 ID|[可移动存储访问控制](device-control-removable-storage-access-control.md)|Windows <p> macOS|供应商 ID 是 USB 委员会分配给供应商的四位数供应商代码。 产品 ID 是供应商分配给设备的四位数产品代码;支持通配符。|
|Serial NumberId|[可移动存储访问控制](device-control-removable-storage-access-control.md)|Windows <p> macOS |例如，`<SerialNumberId>002324B534BCB431B000058A</SerialNumberId>`|
