---
title: Microsoft 威胁防护高级搜寻架构中的数据表
description: 了解高级搜寻架构中的表，以了解可运行威胁搜寻查询的数据
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 数据
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 631b328168003668ed06e37d76177c327794ed18
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808657"
---
# <a name="understand-the-advanced-hunting-schema"></a>了解高级搜寻架构

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高级搜寻](advanced-hunting-overview.md)架构由可提供事件信息或计算机和实体相关信息的多个表组成。 若要高效构建跨多个表的查询，需要了解高级搜寻架构中的表和列。

## <a name="schema-tables"></a>架构表

以下引用列出了架构中的所有表。 每个表名称链接到描述该表的列名称的页面。 表和列名称作为架构表示的一部分列在安全中心的“高级搜寻”屏幕上。

| 表名 | 说明 |
|------------|-------------|
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 计算机信息，包括操作系统信息 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 计算机的网络属性，包括适配器、IP 和 MAC 地址，以及已连接的网络和域 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 过程创建和相关事件 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 网络连接和相关事件 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 文件创建、修改和其他文件系统事件 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 创建和修改注册表项 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 登录和其他身份验证事件 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 加载事件 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | 多个事件类型，包括安全控件（如 Windows Defender 防病毒和 Exploit Protection）触发的事件 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Office 365 电子邮件事件，包括电子邮件送达和阻止事件 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 有关附加到 Office 365 电子邮件的文件的信息 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | 有关 Office 365 电子邮件上的 URL 的信息 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | 设备上的软件清单以及这些软件产品中的任何已知漏洞 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | 公开披露的漏洞的知识库，包括攻击代码是否已公开 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | 威胁和漏洞管理评估事件，指示设备上的各种安全配置的状态 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | 威胁和漏洞管理用于评估设备的各种安全配置的知识库；包括各种标准和基准的映射  |

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
