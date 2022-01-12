---
title: 高级搜寻架构中的 DeviceAlertEvents 表
description: 了解高级搜寻架构的 DeviceAlertEvents 表中的警报生成事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， 适用于终结点的 microsoft defender， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， DeviceAlertEvents， 警报， 严重性， 类别
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: 32dbff60a37c31cdbfd492eb5d746a10d9b7a185
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61934377"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)。

高级 `DeviceAlertEvents` 搜寻[架构中的](advanced-hunting-overview.md)表包含有关搜索中警报Microsoft 365 Defender。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。

|列名称|数据类型|说明|
|---|---|---|
|`AlertId`|string|警报的唯一标识符|
|`Timestamp`|datetime|记录事件的日期和时间|
|`DeviceId`|string|服务中设备的唯一标识符|
|`DeviceName`|string|设备的完全限定 (FQDN) FQDN|
|`Severity`|string|指示警报所标识的威胁指示器或违反活动的潜在影响（高、中或低）|
|`Category`|string|由警报标识的威胁指示器或违反活动的类型|
|`Title`|string|警报的标题|
|`FileName`|string|录制操作所应用到的文件的名称|
|`SHA1`|string|录制操作所应用到的文件的 SHA-1|
|`RemoteUrl`|string|连接到的 URL 或完全限定域名 (FQDN)|
|`RemoteIP`|string|连接到的 IP 地址|
|`AttackTechniques`|string|MITRE ATT&触发警报的活动关联的 CK 技术|
|`ReportId`|long|基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一同使用|
|`Table`|string|包含事件详细信息的表|

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
