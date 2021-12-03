---
title: 导出每个设备的软件清单评估
description: 返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。
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
ms.openlocfilehash: 950892e39d91c1aeaa2179eac56d58bfa2ef9030
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283448"
---
# <a name="export-software-inventory-assessment-per-device"></a>导出每个设备的软件清单评估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。


不同的 API 调用获取不同类型的数据。 由于数据量可能很大，因此有两种方法可以检索数据：

- [导出软件清单评估 **JSON 响应**](#1-export-software-inventory-assessment-json-response) API 将提取组织的所有数据作为 Json 响应。 此方法最适合设备 _数少于 100 K_ 的小组织。 响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。

- [通过文件导出 **软件清单评估**](#2-export-software-inventory-assessment-via-files)  此 API 解决方案允许更快、更可靠地提取大量数据。 因此，建议拥有 100 K 以上设备的大型组织使用。 此 API 将组织的所有数据提取为下载文件。 该响应包含从网站下载所有数据的Azure 存储。 此 API 使你能够按如下方式从 Azure 存储下载你的所有数据：
  - 调用 API 获取包含所有组织数据的下载 URL 列表。
  - 使用下载 URL 下载所有文件并处理您喜欢的数据。

使用 _Json_ 响应 _(通过文件_ 收集的数据) 当前状态的当前快照。 它不包含历史数据。 若要收集历史数据，客户必须将数据保存在自己的数据存储中。

> [!NOTE]
> 除非另有说明，否则列出的所有导出评估方法都是 **** 完全导出和 **** 按设备 (也称为按 **_设备) 。_**

## <a name="1-export-software-inventory-assessment-json-response"></a>1. 导出 JSON 响应 (软件清单) 

### <a name="11-api-method-description"></a>1.1 API 方法说明

此 API 响应包含每个设备已安装软件的所有数据。 返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。

#### <a name="limitations"></a>限制

- 最大页面大小为 200，000。
- 此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。

### <a name="12-permissions"></a>1.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)

权限类型|权限|权限显示名称
---|---|---
应用程序|Software.Read.All|\'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户）|Software.Read|\'阅读威胁和漏洞管理漏洞信息\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 参数

- pageSize (默认值 = 50，000) ：响应中的结果数。
- $top：要返回 (的结果数不会返回 @odata.nextLink，因此不会拉取所有) 

### <a name="15-properties"></a>1.5 属性

> [!NOTE]
>
> - 每条记录大约包含 0.5KB 的数据。 在选择正确的 pageSize 参数时，您应当考虑到这一点。
> - 下表中定义的属性按字母顺序按属性 ID 列出。 运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。
> - 响应中可能会返回其他一些列。 这些列是临时的，可能会被删除，请仅使用记录列。

<br>

****

属性 (ID) |数据类型|说明|返回值的示例
:---|:---|:---|:---
DeviceId|string|服务中设备的唯一标识符。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName|string|设备的完全限定 (FQDN) FQDN。|johnlaptop.europe.contoso.com
DiskPaths|Array[string]|表明产品已安装在设备的磁盘证据。|[ "C： \\Program Files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]
EndOfSupportDate|string|此软件支持已结束或将终止的日期。|2020-12-30
EndOfSupportStatus|string|停止提供支持状态。 可以包含以下可能的值：None、EOS Version、Upcoming EOS Version、EOS Software、Upcoming EOS Software。|即将推出的 EOS
Id|string|记录的唯一标识符。|123ABG55_573AG&mnp！
NumberOfWeaknesses|int|此设备上此软件上漏洞的数量|3
OSPlatform|string|在设备上运行的操作系统的平台。 这些是同一系列中具有变体的特定操作系统，如 Windows 10 和 Windows 11。 有关详细信息，请参阅 tvm 支持的操作系统和平台。|Windows 10 和 Windows 11
RbacGroupName|string|基于角色的访问控制 (RBAC) 组。 如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。 如果组织不包含任何 RBAC 组，则值为"None"。|服务器
RegistryPaths|Array[string]|注册表证据，表明产品已安装在设备中。|[ "HKEY_LOCAL_MACHINE \\SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]
SoftwareFirstSeenTimestamp|string|首次在设备上看到此软件。|2019-04-07 02:06:47
SoftwareName|string|软件产品的名称。|Silverlight
SoftwareVendor|string|软件供应商的名称。|microsoft
SoftwareVersion|string|软件产品的版本号。|81.0.4044.138
|

### <a name="16-examples"></a>1.6 示例

#### <a name="161-request-example"></a>1.6.1 请求示例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="162-response-example"></a>1.6.2 响应示例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10" "Windows_11",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. 通过文件 (导出软件清单) 

### <a name="21-api-method-description"></a>2.1 API 方法说明

此 API 响应包含每个设备已安装软件的所有数据。 返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。

#### <a name="211-limitations"></a>2.1.1 限制

此 API 的速率限制是每分钟 5 个调用和每小时 20 个调用。

### <a name="22-permissions"></a>2.2 权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)

权限类型|权限|权限显示名称
---|---|---
应用程序|Software.Read.All|\'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户）|Software.Read|\'阅读威胁和漏洞管理漏洞信息\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>参数

- sasValidHours：下载 URL 在最长 24 小时 (的有效小时数) 

### <a name="25-properties"></a>2.5 属性

> [!NOTE]
>
> - 文件是 gzip 压缩文件& JSON 格式。
> - 下载 URL 的有效期仅为 3 小时。 否则，可以使用 参数。
> - 为了最大限度提高数据的下载速度，你可以确保从数据所在的同一 Azure 区域进行下载。

<br>

****

属性 (ID) |数据类型|说明|返回值的示例
:---|:---|:---|:---
导出文件|数组 \[ 字符串\]|保存组织当前快照的文件的下载 URL 列表|"[Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|string|导出的生成时间。|2021-05-20T08：00：00Z
|

### <a name="26-examples"></a>2.6 示例

#### <a name="261-request-example"></a>2.6.1 请求示例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 响应示例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>另请参阅

- [导出每个设备的评估方法和属性](get-assessment-methods-properties.md)
- [导出每个设备的安全配置评估](get-assessment-secure-config.md)
- [导出每个设备的软件漏洞评估](get-assessment-software-vulnerabilities.md)

其他相关

- [基于风险的威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [组织中漏洞](tvm-weaknesses.md)
