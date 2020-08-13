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
ms.openlocfilehash: 308337f806d54f1beb7ae6112b2ed883707d4513
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649291"
---
# <a name="understand-the-advanced-hunting-schema"></a>了解高级搜寻架构

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高级搜寻](advanced-hunting-overview.md)架构由多个表组成，这些表提供事件信息或有关设备、警报、标识和其他实体类型的信息。 若要高效构建跨多个表的查询，需要了解高级搜寻架构中的表和列。

## <a name="get-schema-information-in-the-security-center"></a>获取安全中心中的架构信息
构建查询时，请使用内置架构参考快速获取有关架构中每个表的以下信息：

- **表说明**—表中包含的数据类型和数据源。
- **列**—表中的所有列。
- **操作类型**： `ActionType` 表示表支持的事件类型的列中的可能值。 仅为包含事件信息的表提供此信息。
- **示例查询**—示例查询，可介绍如何使用表。

### <a name="access-the-schema-reference"></a>访问架构参考
若要快速访问架构引用，请在 "架构表示" 中选择表名称旁边的 "**查看引用**操作"。 您还可以选择 "**架构引用**" 以搜索表。   

![显示如何访问门户架构引用的图像 ](../../media/mtp-ah/ah-reference.png) 

## <a name="schema-tables"></a>架构表
以下引用列出了架构中的所有表。 每个表名称链接到描述该表的列名称的页面。 表和列名称作为架构表示的一部分列在安全中心的“高级搜寻”屏幕上。

| 表名 | 说明 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | 与警报关联的文件、IP 地址、Url、用户或设备 |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | 来自 Microsoft Defender ATP、Office 365 ATP、Microsoft 云应用安全性和 Azure ATP 的警报，包括严重信息和威胁分类  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | 云应用和服务中与文件相关的活动 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | 多个事件类型，包括安全控件（如 Windows Defender 防病毒和 Exploit Protection）触发的事件 |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | 从终结点上的证书验证事件获取的签名文件的证书信息 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 文件创建、修改和其他文件系统事件 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 加载事件 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 计算机信息，包括操作系统信息 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 设备上的登录和其他身份验证事件 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 网络连接和相关事件 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 计算机的网络属性，包括适配器、IP 和 MAC 地址，以及已连接的网络和域 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 过程创建和相关事件 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 创建和修改注册表项 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | 威胁和漏洞管理评估事件，指示设备上的各种安全配置的状态 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 威胁和漏洞管理用于评估设备的各种安全配置的知识库；包括各种标准和基准的映射  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | 设备上的软件清单以及这些软件产品中的任何已知漏洞 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 公开披露的漏洞的知识库，包括攻击代码是否已公开 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 有关附加到电子邮件的文件的信息 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 电子邮件事件，包括电子邮件传递和阻止事件 |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | 在 Microsoft 365 将电子邮件传递给收件人邮箱之后，在送达后发生的安全事件 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | 有关电子邮件上的 Url 的信息 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | 来自各种源（包括 Azure Active Directory）的帐户信息 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory 和 Microsoft online services 上的身份验证事件 |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | 对 Active Directory 对象（如用户、组、设备和域）执行的查询活动 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识的智能寻线](advanced-hunting-query-emails-devices.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
