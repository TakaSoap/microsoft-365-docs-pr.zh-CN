---
title: Microsoft 威胁防护高级搜寻架构中的数据表
description: 了解高级搜寻架构中的表，以了解可运行威胁搜寻查询的数据
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、数据
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0b28cf2ce96e4c040fac0999d669623cef066fe4
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929488"
---
# <a name="understand-the-advanced-hunting-schema"></a>了解高级搜寻架构

**适用于：**
- Microsoft 威胁防护



[高级搜寻](advanced-hunting-overview.md)架构由可提供事件信息或计算机和实体相关信息的多个表组成。 若要高效构建跨多个表的查询，需要了解高级搜寻架构中的表和列。

## <a name="schema-tables"></a>架构表

以下引用列出了架构中的所有表。 每个表名称链接到描述该表的列名称的页面。 表和列名称作为架构表示的一部分列在安全中心的“高级搜寻”屏幕上。

| 表名 | 说明 |
|------------|-------------|
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | 来自 Microsoft Defender ATP、Office 365 ATP、Microsoft 云应用安全性和 Azure ATP 的警报，包括严重信息和威胁分类  |
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | 与警报关联的文件、IP 地址、Url、用户或设备 |
| **[AccountInfo](advanced-hunting-accountinfo-table.md)** | 来自各种源（包括 Azure Active Directory）的帐户信息 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Office 365 电子邮件事件，包括电子邮件送达和阻止事件 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 有关附加到 Office 365 电子邮件的文件的信息 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | 有关 Office 365 电子邮件上的 URL 的信息 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 计算机信息，包括操作系统信息 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 计算机的网络属性，包括适配器、IP 和 MAC 地址，以及已连接的网络和域 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 过程创建和相关事件 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 网络连接和相关事件 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 文件创建、修改和其他文件系统事件 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 创建和修改注册表项 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 登录和其他身份验证事件 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 加载事件 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | 多个事件类型，包括安全控件（如 Windows Defender 防病毒和 Exploit Protection）触发的事件 |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | 从终结点上的证书验证事件获取的签名文件的证书信息 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | 设备上的软件清单以及这些软件产品中的任何已知漏洞 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | 公开披露的漏洞的知识库，包括攻击代码是否已公开 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | 威胁和漏洞管理评估事件，指示设备上的各种安全配置的状态 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | 威胁和漏洞管理用于评估设备的各种安全配置的知识库；包括各种标准和基准的映射  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | 云应用和服务中与文件相关的活动 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | 由 Active Directory 和其他 Microsoft online services 记录的身份验证事件 |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | 对 Active Directory 对象（如用户、组、设备和域）执行的查询活动 |


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
