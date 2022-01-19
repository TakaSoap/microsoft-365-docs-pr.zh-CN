---
title: 导出每个设备的安全配置评估
description: 返回 DeviceId、ConfigurationId 每个唯一组合的条目。
keywords: api， api， 导出评估， 按设备评估， 漏洞评估报告， 设备漏洞评估， 设备漏洞报告， 安全配置评估， 安全配置报告， 软件漏洞评估， 软件漏洞报告， 计算机漏洞报告，
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
ms.openlocfilehash: 2fc9870871641bb7239a6dcdcdf9f54334726384
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074710"
---
# <a name="export-secure-configuration-assessment-per-device"></a>导出每个设备的安全配置评估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

基于每个设备返回所有配置及其状态。

不同的 API 调用用于获取不同类型的数据。 由于数据量可能很大，因此有两种方法可以检索数据：

- [导出安全配置评估 **JSON 响应**](#1-export-secure-configuration-assessment-json-response)：API 将提取组织的所有数据作为 Json 响应。 此方法最适合设备 _数少于 100 K_ 的小组织。 响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。

- [通过文件 **导出安全配置评估**](#2-export-secure-configuration-assessment-via-files)：此 API 解决方案允许更快、更可靠地拉取大量数据。 因此，建议拥有 100 K 以上设备的大型组织使用。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 通过此 API，你可以从以下Azure 存储下载所有数据：

  - 调用 API 获取包含所有组织数据的下载 URL 列表。

  - 使用下载 URL 下载所有文件并处理您喜欢的数据。

使用 _JSON_ 响应 (通过文件收集的数据) 当前状态的当前快照，并且不包含历史数据。 为了收集历史数据，客户必须将数据保存在自己的数据存储中。

> [!NOTE]
> 除非另有说明，否则列出的所有导出评估方法都是 **** 完全导出，**** 按设备 (也称为按 **_设备) 。_**

## <a name="1-export-secure-configuration-assessment-json-response"></a>1. 导出 JSON 响应 (安全配置) 

### <a name="11-api-method-description"></a>1.1 API 方法说明

此 API 响应包含公开设备上的安全配置评估，并返回 DeviceId、ConfigurationId 每个唯一组合的条目。

#### <a name="111-limitations"></a>1.1.1 限制

- 最大页面大小为 200，000。

- 此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。

### <a name="12-permissions"></a>1.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。

权限类型|权限|权限显示名称
---|---|---
应用程序|Vulnerability.Read.All|\'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户）|Vulnerability.Read|\'阅读威胁和漏洞管理漏洞信息\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 参数

- pageSize \( default = 50，000： \) 响应中的结果数。
- \$top： Number of results to return \( doesn't return \@ odata.nextLink and therefore doesn't pull all the data \) .

### <a name="15-properties"></a>1.5 属性

> [!NOTE]
>
> - 下表中定义的属性按字母顺序按属性 ID 列出。 运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。
> - 响应中可能会返回其他一些列。 这些列是临时的，可能会被删除，请仅使用记录列。

<br>

****

属性 (ID) |数据类型|说明|返回值的示例
---|---|---|---
ConfigurationCategory|string|配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件|安全控制措施
ConfigurationId|string|特定配置的唯一标识符|scid-10000
ConfigurationImpact|string|配置对总体配置评分的影响程度 (1-10)|9 
ConfigurationName|string|配置的显示名称|将设备载入到 Microsoft Defender for Endpoint
ConfigurationSubcategory|string|配置所属的子类别或子组。 在许多情况下，它用于描述特定的功能。|载入设备
DeviceId|string|服务中设备的唯一标识符。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName|string|设备的完全限定 (FQDN) FQDN。|johnlaptop.europe.contoso.com
IsApplicable|布尔值|指示配置或策略是否适用|true
IsCompliant|布尔值|指示是否正确配置了配置或策略|false
IsExpectedUserImpact|布尔值|指示是否将应用配置时影响用户|true
OSPlatform|string|在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如Windows 10和Windows 11。 有关详细信息，请参阅 tvm 支持的操作系统和平台。|Windows 10 和 Windows 11
RbacGroupName|string|基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。|服务器
RecommendationReference|string|对此软件相关建议 ID 的引用。|sca-_-scid-20000
Timestamp|string|上次在设备上看到配置的时间|2020-11-03 10:13:34.8476880
|

### <a name="16-examples"></a>1.6 示例

#### <a name="161-request-example"></a>1.6.1 请求示例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 响应示例

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol - Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol - Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. 通过文件 (导出安全配置) 

### <a name="21-api-method-description"></a>2.1 API 方法说明

此 API 响应包含公开设备上的安全配置评估，并返回 DeviceId、ConfigurationId 每个唯一组合的条目。

#### <a name="212-limitations"></a>2.1.2 限制

此 API 的速率限制是每分钟 5 个调用和每小时 20 个调用。

### <a name="22-permissions"></a>2.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)

权限类型|权限|权限显示名称
---|---|---
应用程序|Vulnerability.Read.All|\'读取"危险和漏洞管理"漏洞信息\'
委派（工作或学校帐户）|Vulnerability.Read|\'读取"危险和漏洞管理"漏洞信息\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>参数

- sasValidHours：下载 URL 的有效期为 (24 小时) 。

### <a name="25-properties"></a>2.5 属性

> [!NOTE]
>
> - 文件是 gzip 压缩文件& Json 格式。
> - 下载 URL 的有效期仅为 3 小时;否则，可以使用 参数。
> - 为了最大限度提高数据的下载速度，你可以确保从数据所在的同一 Azure 区域进行下载。

<br>

****

属性 (ID) |数据类型|说明|返回值的示例
---|---|---|---
导出文件|数组 \[ 字符串\]|保存组织当前快照的文件的下载 URL 列表|["Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|string|导出的生成时间。|2021-05-20T08：00：00Z
|

### <a name="26-examples"></a>2.6 示例

#### <a name="261-request-example"></a>2.6.1 请求示例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 响应示例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>另请参阅

- [导出每个设备的评估方法和属性](get-assessment-methods-properties.md)
- [导出每个设备的软件清单评估](get-assessment-software-inventory.md)
- [导出每个设备的软件漏洞评估](get-assessment-software-vulnerabilities.md)

其他相关

- [基于风险的威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [组织中漏洞](tvm-weaknesses.md)
