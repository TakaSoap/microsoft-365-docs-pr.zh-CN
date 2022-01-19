---
title: 导出每个设备的评估方法和属性
description: 提供有关拉取"危险和漏洞管理"数据的 API 的信息。 不同的 API 调用用于获取不同类型的数据。 通常，每个 API 调用都包含组织中设备的必要数据。
keywords: api， api， 导出评估， 按设备评估， 每计算机评估， 漏洞评估报告， 设备漏洞评估， 设备漏洞报告， 安全配置评估， 安全配置报告， 软件漏洞评估， 软件漏洞报告， 按计算机进行漏洞报告，
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: c10f454919afc725b37537aa354fed05b95cb571
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074470"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>导出每个设备的评估方法和属性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="api-description"></a>API 说明

提供有关基于每个设备拉取数据危险和漏洞管理 API 的方法和属性详细信息。 不同的 API 调用用于获取不同类型的数据。 通常，每个 API 调用都包含组织中设备的必要数据。

> [!NOTE]
> 除非另有说明，否则列出的所有导出评估方法都是 **** 完全导出，**** 按设备 (也称为按 **_设备) 。_**

可以使用导出评估 API 检索 (导出) 类型的信息：

- [1. 导出安全配置评估](#1-export-secure-configurations-assessment)
- [2. 导出软件清单评估](#2-export-software-inventory-assessment)
- [3. 导出软件漏洞评估](#3-export-software-vulnerabilities-assessment)

第 1、2 和 3 节中介绍了与导出信息类型对应的 API。

每个方法都有不同的 API 调用，用于获取不同类型的数据。 由于数据量可能很大，因此有两种方法可以检索数据：

- **JSON 响应**  API 拉取组织的所有数据作为 JSON 响应。 此方法最适合设备 _数少于 100 K_ 的小组织。 响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。

- **通过文件** 此 API 解决方案允许更快、更可靠地提取大量数据。 因此，建议拥有 100 K 以上设备的大型组织使用。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 通过此 API，你可以从以下Azure 存储下载所有数据：
  - 调用 API 获取包含所有组织数据的下载 URL 列表。
  - 使用下载 URL 下载所有文件并处理您喜欢的数据。

使用 _"JSON_ 响应"或" _文件_"收集的数据是当前状态的当前快照。 它不包含历史数据。 若要收集历史数据，客户必须将数据保存在自己的数据存储中。

## <a name="1-export-secure-configurations-assessment"></a>1. 导出安全配置评估

基于每个设备返回所有配置及其状态。

### <a name="11-methods"></a>1.1 方法

Method|数据类型|说明
:---|:---|:---
导出安全配置评估 **(JSON 响应)**|按设备集合的安全配置。 请参阅 [：1.2 JSON (1.2 属性) ](#12-properties-json-response)|返回一个表，该表包含 DeviceId、ConfigurationId 每个唯一组合的条目。 API 拉取组织的所有数据作为 JSON 响应。 此方法最适合设备数少于 100 K 的小组织。 响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。
导出通过文件 **(安全配置)**|按设备集合的安全配置。 请参阅 [：1.3 属性 (文件) ](#13-properties-via-files)|返回一个表，该表包含 DeviceId、ConfigurationId 每个唯一组合的条目。 此 API 解决方案允许更快、更可靠地提取大量数据。 因此，建议拥有 100 K 以上设备的大型组织使用。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 通过此 API，你可以从以下Azure 存储下载所有数据： <ol><li>调用 API 获取包含所有组织数据的下载 URL 列表。</li><li>使用下载 URL 下载所有文件并处理您喜欢的数据。</li></ol>

### <a name="12-properties-json-response"></a>1.2 JSON (属性) 

属性 (ID) |数据类型|说明
:---|:---|:---
configurationCategory|String|配置所属的类别或分组：应用程序、操作系统、网络、帐户、安全控件。
configurationId|String|特定配置的唯一标识符。
configurationImpact|String|配置对总体配置分数的 (为 1-10) 。
configurationName|字符串|配置的显示名称。
configurationSubcategory|String|配置所属的子类别或子组。 在许多情况下，特定功能或功能。
deviceId|String|服务中设备的唯一标识符。
deviceName|String|设备的完全限定 (FQDN) FQDN。
isApplicable|Bool|指示配置或策略是否适用。
isCompliant|Bool|指示配置或策略是否正确配置。
isExpectedUserImpact|Bool|指示将应用配置时用户是否受到影响。
osPlatform|String|在设备上运行的操作系统的平台。 同一系列中具有变体的特定操作系统，如 Windows 10 和 Windows 11。 有关详细信息，请参阅 TVM 支持的操作系统和平台。
osVersion|String|设备上运行的操作系统的特定版本。
rbacGroupName|String|基于角色的访问控制 (RBAC) 组。 如果设备未分配到任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。
rbacGroupId|String|基于角色的访问控制 (RBAC) 组 ID。
recommendationReference|String|对与软件相关的建议 ID 的引用。
timestamp|String|上次在设备上看到配置的时间。

### <a name="13-properties-via-files"></a>1.3 属性 (文件) 

属性 (ID) |数据类型|说明
:---|:---|:---
导出文件|数组 \[ 字符串\]|保存组织当前快照的文件的下载 URL 列表。
GeneratedTime|String|导出的生成时间。

## <a name="2-export-software-inventory-assessment"></a>2. 导出软件清单评估

返回每台设备上安装的所有软件及其详细信息。

### <a name="21-methods"></a>2.1 方法

|Method|数据类型|说明|
|:---|:---|:---|
|导出软件清单评估 **(JSON 响应)**|按设备集合列出软件清单。 请参阅 [：2.2 JSON (2.2 属性) ](#22-properties-json-response)|返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。 API 拉取组织的所有数据作为 JSON 响应。 此方法最适合设备数少于 100 K 的小组织。 响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。 |
| 通过文件库 **导出 (清单)**|按设备文件列出软件清单。 请参阅 [：2.3 属性 (文件) ](#23-properties-via-files)|返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。 此 API 解决方案允许更快、更可靠地提取大量数据。 因此，建议拥有 100 K 以上设备的大型组织使用。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 通过此 API，你可以从 Azure 存储数据，如下所示： <ol><li>调用 API 获取包含组织数据的下载 URL 列表</li><li>使用下载 URL 下载文件并处理您喜欢的数据。</li></ol> |

### <a name="22-properties-json-response"></a>2.2 JSON (2.2 属性) 

属性 (ID) |数据类型|说明
:---|:---|:---
DeviceId|字符串|服务中设备的唯一标识符。
DeviceName|字符串|设备的完全限定 (FQDN) FQDN。
DiskPaths|Array[string]|表明产品已安装在设备的磁盘证据。
EndOfSupportDate|String|此软件支持已结束或将终止的日期。
EndOfSupportStatus|字符串|停止提供支持状态。 可以包含以下可能的值：None、EOS Version、Upcoming EOS Version、EOS Software、Upcoming EOS Software。
NumberOfWeaknesses|Int|此设备上此软件上漏洞的数量。
OSPlatform|String|在设备上运行的操作系统的平台;同一系列中具有变体的特定操作系统，如 Windows 10 和 Windows 11。 有关详细信息，请参阅 tvm 支持的操作系统和平台。
RbacGroupName|字符串|基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。
rbacGroupId|String|基于角色的访问控制 (RBAC) 组 ID。
RegistryPaths|Array[string]|注册表证据，表明产品已安装在设备中。
SoftwareFirstSeenTimestamp|String|首次在设备上看到此软件。
SoftwareName|String|软件产品的名称。
SoftwareVendor|字符串|软件供应商的名称。
SoftwareVersion|String|软件产品的版本号。

### <a name="23-properties-via-files"></a>2.3 通过文件 (的属性) 

属性 (ID) |数据类型|说明
:---|:---|:---
导出文件|数组 \[ 字符串\]|保存组织当前快照的文件的下载 URL 列表。
GeneratedTime|String|导出的生成时间。

## <a name="3-export-software-vulnerabilities-assessment"></a>3. 导出软件漏洞评估

返回设备上所有设备的已知漏洞及其详细信息。

### <a name="31-methods"></a>3.1 方法

Method|数据类型|说明
:---|:---|:---
导出 **JSON 响应 (软件漏洞)**|调查集合，请参阅 [：3.2 属性 (JSON 响应) ](#32-properties-json-response)|返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 每个唯一组合的条目的表。 API 拉取组织的所有数据作为 JSON 响应。 此方法最适合设备数少于 100 K 的小组织。 响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。
通过文件存储导出 **(漏洞评估)**|调查实体 请参阅 [：3.3 属性 (文件) ](#33-properties-via-files)|返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 每个唯一组合的条目的表。 此 API 解决方案允许更快、更可靠地提取大量数据。 因此，建议拥有 100 K 以上设备的大型组织使用。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 通过此 API，你可以从以下Azure 存储下载所有数据： <ol><li>调用 API 获取包含所有组织数据的下载 URL 列表。</li><li>使用下载 URL 下载所有文件并处理您喜欢的数据。</li></ol>
**Delta 导出** 软件漏洞评估 **(JSON 响应)**|调查集合请参阅 [：3.4 Properties Delta export (JSON response) ](#34-properties-delta-export-json-response)|返回一个表，其中每个唯一组合都有一个条目：DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 和 EventTimestamp。 <p> API 拉取你组织的数据作为 JSON 响应。 响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。 JSON 响应 (软件漏洞评估) 用于按设备获取组织的软件漏洞评估的完整快照。 但是，增量导出 API 调用用于仅提取所选日期与当前日期之间发生的更改 ("delta"API 调用) 。 您不会每次获取包含大量数据的完全导出，而只会获取有关新的、已修复和更新的漏洞的特定信息。 Delta 导出 API 调用还可用于计算不同的 KPI，例如"修复了多少漏洞？" 或"向我的组织添加了多少个新漏洞？" <p> 由于软件漏洞的 Delta 导出 API 调用仅返回目标日期范围的数据，因此不被视为完全 _导出_。

### <a name="32-properties-json-response"></a>3.2 JSON (3.2 属性) 

属性 (ID) |数据类型|说明
:---|:---|:---
CveId|String|在 CVE 安全机制的常见漏洞和曝光下分配给 (的唯) 标识符。
CvssScore|字符串|CVE 的 CVSS 分数。
DeviceId|字符串|服务中设备的唯一标识符。
DeviceName|String|设备的完全限定 (FQDN) FQDN。
DiskPaths|数组 \[ 字符串\]|表明产品已安装在设备的磁盘证据。
ExploitabilityLevel|String| (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) 
FirstSeenTimestamp|String|首次在设备上看到此产品的 CVE 时。
Id|字符串|记录的唯一标识符。
LastSeenTimestamp|字符串|上次在设备上看到 CVE 的时间。
OSPlatform|字符串|在设备上运行的操作系统的平台;同一系列中具有变体的特定操作系统，如 Windows 10 和 Windows 11。 有关详细信息，请参阅 tvm 支持的操作系统和平台。
RbacGroupName|字符串|基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。
rbacGroupId|String|基于角色的访问控制 (RBAC) 组 ID。
RecommendationReference|字符串|对此软件相关建议 ID 的引用。
RecommendedSecurityUpdate|字符串|软件供应商提供的用于解决漏洞的安全更新的名称或说明。
RecommendedSecurityUpdateId|字符串|适用安全更新的标识符或相应指南或知识库的标识符 (KB) 文章。
注册表路径 数组 \[ 字符串\]|注册表证据，表明产品已安装在设备中。
SoftwareName|String|软件产品的名称。
SoftwareVendor|String|软件供应商的名称。
SoftwareVersion|String|软件产品的版本号。
VulnerabilitySeverityLevel|String|根据 CVSS 分数和受威胁环境影响的动态因素分配给安全漏洞的严重性级别。

### <a name="33-properties-via-files"></a>3.3 属性 (文件) 

属性 (ID) |数据类型|说明
:---|:---|:---
导出文件|数组 \[ 字符串\]|保存组织当前快照的文件的下载 URL 列表。
GeneratedTime|String|导出的生成时间。

### <a name="34-properties-delta-export-json-response"></a>3.4 delta (JSON 响应属性) 

属性 (ID) |数据类型|说明
:---|:---|:---
CveId |String|在 CVE 安全机制的常见漏洞和曝光下分配给 (的唯) 标识符。
CvssScore|String|CVE 的 CVSS 分数。
DeviceId|字符串|服务中设备的唯一标识符。
DeviceName|String|设备的完全限定 (FQDN) FQDN。
DiskPaths|Array[string]|表明产品已安装在设备的磁盘证据。
EventTimestamp|字符串|找到 delta 事件的时间。
ExploitabilityLevel|String|NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)  (
FirstSeenTimestamp|String|首次在设备上看到产品的 CVE 时。
Id|String|记录的唯一标识符。  
LastSeenTimestamp|字符串|上次在设备上看到 CVE 的时间。
OSPlatform|String|在设备上运行的操作系统的平台;同一系列中具有变体的特定操作系统，如 Windows 10 和 Windows 11。 有关详细信息，请参阅 tvm 支持的操作系统和平台。
RbacGroupName|字符串|基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。
RecommendationReference|字符串|对此软件相关建议 ID 的引用。
RecommendedSecurityUpdate |String|软件供应商提供的用于解决漏洞的安全更新的名称或说明。
RecommendedSecurityUpdateId |String|相应指南或知识库文章适用的安全更新或标识符 (知识库) 标识符
RegistryPaths |Array[string]|注册表证据，表明产品已安装在设备中。
SoftwareName|String|软件产品的名称。
SoftwareVendor|String|软件供应商的名称。
SoftwareVersion|String|软件产品的版本号。
Status|String|**针对** (设备上引入的新漏洞的新增) 。 **修复** (设备上不再存在的漏洞的修复方法，这意味着已) 。 **更新** (已更改的设备上漏洞的信息。 可能的更改包括：CVSS 分数、攻击性级别、严重性级别、DiskPaths、RegistryPaths、RecommendedSecurityUpdate) 。
VulnerabilitySeverityLevel|String|根据 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别。

## <a name="see-also"></a>另请参阅

- [导出每个设备的安全配置评估](get-assessment-secure-config.md)
- [导出每个设备的软件清单评估](get-assessment-software-inventory.md)
- [导出每个设备的软件漏洞评估](get-assessment-software-vulnerabilities.md)

其他相关

- [基于风险的威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [组织中漏洞](tvm-weaknesses.md)
