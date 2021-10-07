---
title: 导出每个设备的软件漏洞评估
description: API 响应针对每个设备，并且包含安装在公开设备上易受攻击的软件，以及这些软件产品中的任何已知漏洞。 此表还包括操作系统信息、CVE ID 和漏洞严重性信息。
keywords: api， api， 导出评估， 按设备评估， 漏洞评估报告， 设备漏洞评估， 设备漏洞报告， 安全配置评估， 安全配置报告， 软件漏洞评估， 软件漏洞报告， 计算机漏洞报告，
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 6b47f87a1892f7e50b7202871b06a328d5597a88
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192822"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>导出每个设备的软件漏洞评估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

基于每个设备返回所有已知软件漏洞及其所有设备的详细信息。

不同的 API 调用用于获取不同类型的数据。 由于数据量可能非常大，因此有两种方法可以检索数据：

1. [导出软件漏洞评估 **JSON 响应**](#1-export-software-vulnerabilities-assessment-json-response)  API 将提取组织的所有数据作为 Json 响应。 此方法最适合使用少于 _100 K_ 设备的小组织。 响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。

2. [通过文件导出 **软件漏洞评估**](#2-export-software-vulnerabilities-assessment-via-files) 此 API 解决方案允许更快、更可靠地提取大量数据。 对于拥有 100 K 多台设备的大型组织，建议使用 Via-files。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 通过此 API，可以从以下Azure 存储下载所有数据：
   - 调用 API 获取包含所有组织数据的下载 URL 列表。
   - 使用下载 URL 下载所有文件并处理您喜欢的数据。

3. [Delta 导出软件漏洞评估 **JSON 响应**](#3-delta-export-software-vulnerabilities-assessment-json-response)  返回一个表，其中每个唯一组合都有一个条目：DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 和 EventTimestamp。
API 拉取你组织的数据作为 Json 响应。 响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。

   与完整的"软件漏洞评估 (JSON 响应) "不同（用于按设备获取组织的软件漏洞评估的完整快照）不同，增量导出 API 调用仅用于获取所选日期和当前日期之间发生的更改 ("delta"API 调用) 。 您不会每次获取包含大量数据的完全导出，而只会获取有关新的、已修复和更新的漏洞的特定信息。 Delta 导出 JSON 响应 API 调用还可用于计算不同的 KPI，例如"修复了多少漏洞？" 或"向我的组织添加了多少个新漏洞？"

   由于针对软件漏洞的 Delta 导出 JSON 响应 API 调用仅返回目标日期范围的数据，因此不被视为完全 _导出_。

使用 _Json_ 响应 (通过文件收集的数据) 当前状态的当前快照，并且不包含历史数据。 为了收集历史数据，客户必须将数据保存在自己的数据存储中。

> [!NOTE]
> 除非另有说明，否则列出的所有导出评估方法都是 **** 完全导出和 **** 按设备 (也称为按 **_设备) 。_**

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a>1. 导出 JSON 响应 (软件漏洞) 

### <a name="11-api-method-description"></a>1.1 API 方法说明

此 API 响应包含每个设备已安装软件的所有数据。 返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 每个唯一组合的条目的表。

#### <a name="111-limitations"></a>1.1.1 限制

- 最大页面大小为 200，000。
- 此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。

### <a name="12-permissions"></a>1.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)

权限类型|权限|权限显示名称
---|---|---
Application|Vulnerability.Read.All|\'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户）|Vulnerability.Read|\'阅读威胁和漏洞管理漏洞信息\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 参数

- pageSize (默认值 = 50，000) ：响应中的结果数。
- $top：返回 (的结果数不会返回 @odata.nextLink，因此不会拉取所有) 。

### <a name="15-properties"></a>1.5 属性

> [!NOTE]
>
> - 每条记录大约包含 1 KB 的数据。 在选择正确的 pageSize 参数时，您应当考虑到这一点。
> - 响应中可能会返回其他一些列。 这些列是临时的，可能会被删除，请仅使用记录列。
> - 下表中定义的属性按字母顺序按属性 ID 列出。 运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。

<br>

****

属性 (ID) |数据类型|说明|返回值的示例
:---|:---|:---|:---
CveId|string|分配给 CVE 安全机制中常见漏洞和 (漏洞) 标识符。|CVE-2020-15992
CvssScore|string|CVE 的 CVSS 分数。|6.2
DeviceId|string|服务中设备的唯一标识符。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName|string|设备的完全限定 (FQDN) FQDN。|johnlaptop.europe.contoso.com
DiskPaths|数组 \[ 字符串\]|表明产品已安装在设备的磁盘证据。|[ "C：\Program Files (x86) \Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel|string|此漏洞的利用级别 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) |ExploitIsInKit
FirstSeenTimestamp|string|首次在设备上看到此产品的 CVE 时。|2020-11-03 10:13:34.8476880
Id|string|记录的唯一标识符。|123ABG55_573AG&mnp！
LastSeenTimestamp|string|上次在设备上看到 CVE 的时间。|2020-11-03 10:13:34.8476880
OSPlatform|string|在设备上运行的操作系统的平台。 此属性指示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 有关详细信息，请参阅 tvm 支持的操作系统和平台。|Windows 10
RbacGroupName|string|基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。|服务器
RecommendationReference|string|对此软件相关建议 ID 的引用。|va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (可选) |string|软件供应商提供的用于解决漏洞的安全更新的名称或说明。|2020 年 4 月安全更新
RecommendedSecurityUpdateId (可选) |string|适用安全更新的标识符或相应指南或知识库 (KB) 标识符|4550961
RegistryPaths|数组 \[ 字符串\]|注册表证据，表明产品已安装在设备中。|[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName|string|软件产品的名称。|chrome
SoftwareVendor|string|软件供应商的名称。|google
SoftwareVersion|string|软件产品的版本号。|81.0.4044.138
VulnerabilitySeverityLevel|string|根据 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别。|中型
|

### <a name="16-examples"></a>1.6 示例

#### <a name="161-request-example"></a>1.6.1 请求示例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 响应示例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. 导出通过文件 (软件漏洞) 

### <a name="21-api-method-description"></a>2.1 API 方法说明

此 API 响应包含每个设备已安装软件的所有数据。 返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 每个唯一组合的条目的表。

#### <a name="212-limitations"></a>2.1.2 限制

此 API 的速率限制是每分钟 5 个调用和每小时 20 个调用。

### <a name="22-permissions"></a>2.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息，包括如何选择权限，请参阅使用 [适用于终结点的 Microsoft Defender API 了解详细信息](apis-intro.md)。

权限类型|权限|权限显示名称
---|---|---
Application|Vulnerability.Read.All|\'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户）|Vulnerability.Read|\'阅读威胁和漏洞管理漏洞信息\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 参数

- sasValidHours：下载 URL 的有效期为 (24 小时) 。

### <a name="25-properties"></a>2.5 属性

> [!NOTE]
>
> - 文件是 gzip 压缩& Json 格式。
> - 下载 URL 的有效期仅为 3 小时;否则，可以使用 参数。
> - 为了最大限度提高数据的下载速度，你可以确保从数据所在的同一 Azure 区域进行下载。
>
> - 每条记录大约包含 1KB 的数据。 在选择正确的 pageSize 参数时，您应当考虑到这一点。
> - 响应中可能会返回其他一些列。 这些列是临时的，可能会被删除，请仅使用记录列。

<br>

****

属性 (ID) |数据类型|说明|返回值的示例
:---|:---|:---|:---
导出文件|数组 \[ 字符串\]|保存组织当前快照的文件的下载 URL 列表。|["https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|string|导出的生成时间。|2021-05-20T08：00：00Z
|

### <a name="26-examples"></a>2.6 示例

#### <a name="261-request-example"></a>2.6.1 请求示例

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 响应示例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a>3. Delta 导出软件漏洞评估 (JSON 响应) 

### <a name="31-api-method-description"></a>3.1 API 方法说明

返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 每个唯一组合的条目的表。 API 拉取你组织的数据作为 Json 响应。 响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。 与完整的软件漏洞评估 (JSON 响应)  (不同，JSON 响应)  (用于通过设备) 获取组织的软件漏洞评估的完整快照) 增量导出 JSON 响应 API 调用用于仅获取所选日期与当前日期 ("delta"API 调用) 之间发生的更改。 您不会每次获取包含大量数据的完全导出，而只会获取有关新的、已修复和更新的漏洞的特定信息。 Delta 导出 JSON 响应 API 调用还可用于计算不同的 KPI，例如"修复了多少漏洞？" 或"向我的组织添加了多少个新漏洞？"

> [!NOTE]
> 强烈建议你至少每周使用一次通过设备 API 调用评估的完整导出软件漏洞，并且此额外的导出软件漏洞会通过设备 (delta) API 调用一周中的所有其他日期进行更改。 与其他评估 JSON 响应 API 不同，"增量导出"不是完全导出。 增量导出仅包括所选日期与当前日期之间发生的更改 ("delta"API 调用) 。

#### <a name="311-limitations"></a>3.1.1 限制

- 最大页面大小为 200，000。
- sinceTime 参数最长为 14 天。
- 此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。

### <a name="32-permissions"></a>3.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)

权限类型|权限|权限显示名称
---|---|---
Application|Vulnerability.Read.All|"读取威胁和漏洞管理漏洞信息"
委派（工作或学校帐户）|Vulnerability.Read|"读取威胁和漏洞管理漏洞信息"

### <a name="33-url"></a>3.3 URL

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine
```

### <a name="34-parameters"></a>3.4 参数

- sinceTime (必需) ：所选时间和今天之间的数据。
- pageSize (默认值 = 50，000) ：响应中的结果数。
- $top：要返回 (的结果数不会返回 @odata.nextLink，因此不会拉取所有) 。

### <a name="35-properties"></a>3.5 属性

每个返回的记录都包含设备 API 评估的完整导出软件漏洞的所有数据，以及两个附加字段  _**：EventTimestamp**_ 和 _**Status**_。

> [!NOTE]
>
> - 响应中可能会返回其他一些列。 这些列是临时的，可能会被删除，因此请仅使用记录列。
> - 下表中定义的属性按字母顺序按属性 ID 列出。 运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。

<br>

****

属性 (ID) |数据类型|说明|返回值的示例
:---|:---|:---|:---
CveId |string|分配给 CVE 安全机制中常见漏洞和 (漏洞) 标识符。|CVE-2020-15992  
CvssScore|string|CVE 的 CVSS 分数。|6.2  
DeviceId|string|服务中设备的唯一标识符。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1  
DeviceName|string|设备的完全限定 (FQDN) FQDN。|johnlaptop.europe.contoso.com  
DiskPaths|Array[string]|表明产品已安装在设备的磁盘证据。|["C：\Program Files (x86) \Microsoft\Silverlight\Application\silverlight.exe"]  
EventTimestamp|字符串|找到此 delta 事件的时间。|2021-01-11T11：06：08.291Z
ExploitabilityLevel|string|此漏洞的利用级别 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) |ExploitIsInKit  
FirstSeenTimestamp|string|首次在设备上看到此产品的 CVE 时。|2020-11-03 10:13:34.8476880  
Id|string|记录的唯一标识符。|123ABG55_573AG&mnp！  
LastSeenTimestamp|string|上次在设备上看到 CVE 的时间。|2020-11-03 10:13:34.8476880  
OSPlatform|string|在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 有关详细信息，请参阅 tvm 支持的操作系统和平台。|Windows 10  
RbacGroupName|string|基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。|服务器  
RecommendationReference|string|对此软件相关建议 ID 的引用。|va--microsoft--silverlight  
RecommendedSecurityUpdate |string|软件供应商提供的用于解决漏洞的安全更新的名称或说明。|2020 年 4 月安全更新  
RecommendedSecurityUpdateId |string|适用安全更新的标识符或相应指南或知识库的标识符 (KB) 文章|4550961  
RegistryPaths |Array[string]|注册表证据，表明产品已安装在设备中。|[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]  
SoftwareName|string|软件产品的名称。|chrome  
SoftwareVendor|string|软件供应商的名称。|google  
SoftwareVersion|string|软件产品的版本号。|81.0.4044.138  
状态|String|**新建**   (如果设备上不再存在此漏洞（这意味着在设备上已修复此漏洞)  (1) **Fixed** (上引入的新漏洞，请  ) 。  (2)  **更新** (如果设备上漏洞   已更改。 可能的更改包括：CVSS 分数、攻击性级别、严重性级别、DiskPaths、RegistryPaths、RecommendedSecurityUpdate) 。 |Fixed
VulnerabilitySeverityLevel|string|根据 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别。|中型
|

#### <a name="clarifications"></a>说明

- 如果软件从版本 1.0 更新到版本 2.0，并且这两个版本都向 CVE-A 公开，您将收到 2 个单独的事件：
   1. 修复：1.0 版上的 CVE-A 已修复。
   1. 新增：已添加版本 2.0 上的 CVE-A。

- 例如，如果特定漏洞 (（例如，CVE-A) 在 (（例如，) 年 1 月 10 日针对 1.0 版软件）首次看到，而该软件在数天后更新到版本 2.0（也向同一 CVE-A 公开）时，您将收到以下两个分离事件：
   1. 修复：CVE-X、FirstSeenTimestamp 1 月 10 日版本 1，0。
   1. 新增：CVE-X、FirstSeenTimestamp 1 月 10 日版本 2.0。

### <a name="36-examples"></a>3.6 示例

#### <a name="361-request-example"></a>3.6.1 请求示例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>3.6.2 响应示例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)",
    "value": [
        {
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__",
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "google",
            "softwareName": "chrome",
            "softwareVersion": "87.0.4280.88",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome"
            ],
            "lastSeenTimestamp": "2021-01-04 00:29:42",
            "firstSeenTimestamp": "2020-11-06 03:12:44",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-google-_-chrome",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__",
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.18363.1256",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.64.329.3",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-11 19:49:48",
            "firstSeenTimestamp": "2020-12-07 18:25:47",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_",
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "mozilla",
            "softwareName": "firefox",
            "softwareVersion": "83.0.0.0",
            "cveId": "CVE-2020-26971",
            "vulnerabilitySeverityLevel": "High",
            "recommendedSecurityUpdate": "193220",
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)"
            ],
            "lastSeenTimestamp": "2021-01-05 17:04:30",
            "firstSeenTimestamp": "2020-05-06 12:42:19",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-mozilla-_-firefox",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__",
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "project",
            "softwareVersion": "16.0.13701.20000",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us"
            ],
            "lastSeenTimestamp": "2021-01-03 23:38:03",
            "firstSeenTimestamp": "2019-08-01 22:56:12",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-project",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_",
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net",
            "osPlatform": "Windows10",
            "osVersion": "10.0.18363.1256",
            "osArchitecture": "x64",
            "softwareVendor": "google",
            "softwareName": "chrome",
            "softwareVersion": "81.0.4044.138",
            "cveId": "CVE-2020-16011",
            "vulnerabilitySeverityLevel": "High",
            "recommendedSecurityUpdate": "ADV 200002",
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}"
            ],
            "lastSeenTimestamp": "2020-12-10 22:45:41",
            "firstSeenTimestamp": "2020-07-26 02:13:43",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-google-_-chrome",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        }
    ],
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="see-also"></a>另请参阅

- [导出每个设备的评估方法和属性](get-assessment-methods-properties.md)
- [导出每个设备的安全配置评估](get-assessment-secure-config.md)
- [导出每个设备的软件清单评估](get-assessment-software-inventory.md)

其他相关

- [基于风险的威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [组织中漏洞](tvm-weaknesses.md)
