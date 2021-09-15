---
title: Microsoft 365 Defender流 API 中支持的事件类型
description: 了解流式 API () 哪些搜寻事件类型
keywords: 原始数据导出， 流式处理 API， API， 事件中心， Azure 存储， 存储帐户， 搜寻， 原始数据共享
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93f5d54869c01e9a261fd9b6be7c5e5263a28621
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356201"
---
# <a name="supported-microsoft-365-defender-event-types-in-event-streaming-api"></a>事件Microsoft 365 Defender API 中支持的事件类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


事件流式处理 API 不断扩展，以支持更多事件类型。 了解哪些搜寻表已公开提供、当前处于公共预览状态或尚不受支持。 
**新增 - 电子邮件事件类型/表现已通用**

## <a name="hunting-tables-support-status-in-event-streaming-api"></a>搜寻表支持事件流 API 中的状态

| 表名 | 状态 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | GA |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | GA  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | 尚不支持 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** |GA |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** |GA |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | GA |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | GA |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | GA |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | GA |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** |GA |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | GA |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | GA |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | GA |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | GA |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | GA  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | GA |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | GA |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | GA |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | GA |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | GA |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | GA |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | GA |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | 尚不支持 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** |尚不支持|
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | 尚不支持 |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | 尚不支持 |

