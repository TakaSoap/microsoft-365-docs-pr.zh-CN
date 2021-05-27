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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689209"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>导出每个设备的软件漏洞评估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
基于每个设备返回所有已知软件漏洞及其所有设备的详细信息。

不同的 API 调用用于获取不同类型的数据。 由于数据量可能非常大，因此有两种方法可以检索数据：

- [导出软件漏洞评估 OData](#1-export-software-vulnerabilities-assessment-odata)  API 按照 OData 协议提取组织的所有数据作为 Json 响应。 此方法最适合使用少于 _100 K_ 设备的小组织。 响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。

- [通过文件导出软件漏洞评估](#2-export-software-vulnerabilities-assessment-via-files) 此 API 解决方案允许更快、更可靠地提取大量数据。 因此，建议拥有 100 K 以上设备的大型组织使用。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 此 API 使你能够按如下方式从Azure 存储数据：

  - 调用 API 获取包含所有组织数据的下载 URL 列表。

  - 使用下载 URL 下载所有文件并处理您喜欢的数据。

使用 _OData_ 或 (文件收集的数据) 当前状态的当前快照，不包含历史数据。 为了收集历史数据，客户必须将数据保存在自己的数据存储中。

> [!Note]
>
> 除非另有说明，否则列出的所有导出评估方法都是 **** 完全导出 (**** 也称作按设备 **_) 。_**

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. 导出 OData (软件) 

### <a name="11-api-method-description"></a>1.1 API 方法说明

此 API 响应包含每个设备已安装软件的所有数据。 返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 每个唯一组合的条目的表。

#### <a name="limitations"></a>限制

>- 最大页面大小为 200，000。
>
>- 此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。

### <a name="12-permissions"></a>1.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)

权限类型 | 权限 | 权限显示名称
---|---|---
应用程序 | Vulnerability.Read.All | \'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户） | Vulnerability.Read | \'阅读威胁和漏洞管理漏洞信息\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 参数

- pageSize (默认值 = 50，000) – 响应中的结果数
- $top – 要返回 (的结果数不会返回 @odata.nextLink，因此不会拉取所有) 

### <a name="15-properties"></a>1.5 属性
>
>[!Note]
>
>- 每条记录大约包含 1KB 的数据。 在选择正确的 pageSize 参数时，您应当考虑到这一点。
>
>- 响应中可能会返回其他一些列。 这些列是临时的，可能会被删除，请仅使用记录列。
>
>- 下表中定义的属性按字母顺序按属性 ID 列出。  运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。
>

属性 (ID)  | 数据类型 | 说明 | 返回值的示例
:---|:---|:---|:---
CveId | string | 分配给 CVE 安全机制中常见漏洞和 (漏洞) 标识符。 | CVE-2020-15992
CvssScore | string | CVE 的 CVSS 分数。 | 6.2
DeviceId | string | 服务中设备的唯一标识符。 | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | 设备的完全限定 (FQDN) FQDN。 | johnlaptop.europe.contoso.com
DiskPaths  | 数组 \[ 字符串\] | 表明产品已安装在设备的磁盘证据。 | [ "C：\Program Files (x86) \Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | string | 此漏洞的利用级别 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)  | ExploitIsInKit
FirstSeenTimestamp | string | 首次在设备上看到此产品的 CVE 时。 | 2020-11-03 10:13:34.8476880
Id | string | 记录的唯一标识符。 | 123ABG55_573AG&mnp！
LastSeenTimestamp | string | 上次在设备上看到 CVE 的时间。 | 2020-11-03 10:13:34.8476880
OSPlatform | string | 在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 有关详细信息，请参阅 tvm 支持的操作系统和平台。 | Windows 10
RbacGroupName  | string | 基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。 | 服务器
RecommendationReference | string | 对此软件相关建议 ID 的引用。 | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (可选)  | string | 软件供应商提供的用于解决漏洞的安全更新的名称或说明。 | 2020 年 4 月安全更新
RecommendedSecurityUpdateId (可选)  | string | 相应指南或知识库的适用安全更新或标识符的标识符 (KB) 文章 | 4550961
RegistryPaths  | 数组 \[ 字符串\] | 注册表证据，表明产品已安装在设备中。 | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | string | 软件产品的名称。 | chrome
SoftwareVendor | string | 软件供应商的名称。 | google
SoftwareVersion | string | 软件产品的版本号。 | 81.0.4044.138
VulnerabilitySeverityLevel  | string | 根据 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别。 | 中

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. 通过文件 (导出软件漏洞) 

### <a name="21-api-method-description"></a>2.1 API 方法说明

此 API 响应包含每个设备已安装软件的所有数据。 返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 每个唯一组合的条目的表。

#### <a name="212-limitations"></a>2.1.2 限制

此 API 的速率限制是每分钟 5 个调用和每小时 20 个调用。

### <a name="22-permissions"></a>2.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息，包括如何选择权限，请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息](apis-intro.md)。

权限类型 | 权限 | 权限显示名称
---|---|---
应用程序 | Vulnerability.Read.All | \'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户） | Vulnerability.Read | \'阅读威胁和漏洞管理漏洞信息\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 参数

- sasValidHours – 下载 URL 在最长 24 小时 (的有效小时数) 

### <a name="25-properties"></a>2.5 属性

>[!Note]
>
>- 文件是 gzip 压缩文件& Json 格式。
>
>- 下载 URL 的有效期仅为 3 小时;否则，可以使用 参数。
>
>- 为了最大限度提高数据的下载速度，你可以确保从数据所在的同一 Azure 区域进行下载。
>

>[!Note]
>
>- 每条记录大约包含 1KB 的数据。 在选择正确的 pageSize 参数时，您应当考虑到这一点。
>
>- 响应中可能会返回其他一些列。 这些列是临时的，可能会被删除，请仅使用记录列。
>

属性 (ID)  | 数据类型 | 说明 | 返回值的示例
:---|:---|:---|:---
导出文件 | 数组 \[ 字符串\]  | 保存组织当前快照的文件的下载 URL 列表。 | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | string | 导出的生成时间。 | 2021-05-20T08：00：00Z

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

## <a name="see-also"></a>另请参阅

- [导出每个设备的评估方法和属性](get-assessmnt-1methods-properties.md)

- [导出每个设备的安全配置评估](get-assessmnt-secure-cfg.md)

- [导出每个设备的软件清单评估](get-assessmnt-software-inventory.md)

其他相关

- [基于风险的威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)

- [组织中漏洞](tvm-weaknesses.md)
