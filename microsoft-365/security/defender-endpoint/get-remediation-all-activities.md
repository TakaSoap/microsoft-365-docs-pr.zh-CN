---
title: 列出所有修正活动
description: 返回有关所有修正活动的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务， 所有修正，
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9e06cc5e17aff990da853ce798f24da288bd64ae
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302058"
---
# <a name="list-all-remediation-activities"></a>列出所有修正活动

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

返回有关所有修正活动的信息。

[详细了解修正活动](tvm-remediation.md)。

**URL：** GET： /api/remediationTasks
<br>支持 [OData V4 查询](https://www.odata.org/documentation/)。
<br>OData 支持的运算符：
<br>```$filter``` on：  ```createdon``` 和 ```status``` properties。
<br>```$top``` 最大值为 10，000。
<br>```$skip```.
<br>请参阅 Microsoft [Defender for Endpoint 的 OData 查询示例](exposed-apis-odata-samples.md)。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|RemediationTasks.Read.All|\'阅读威胁和漏洞管理漏洞信息\'
委派（工作或学校帐户）|RemediationTask.Read|\'阅读威胁和漏洞管理漏洞信息\'

## <a name="properties"></a>属性

属性 (ID) |数据类型|说明|返回值的示例
:---|:---|:---|:---
类别|字符串|软件/安全配置 (修正活动的) |软件
completerEmail|String|如果修正活动是由某人手动完成的，此列将包含他们的电子邮件|NULL
completerId|String|如果修正活动是由某人手动完成的，则此列包含其对象 ID|NULL
completionMethod|String|如果所有 (设备都由选择"标记为已完成") 或"手动"进行修补，则修正活动可以"自动"完成。|自动
createdOn|日期时间|创建此修正活动的时间|2021-01-12T18：54：11.5499478Z
说明|String|此修正活动的说明|将 Microsoft Silverlight 更新到更高版本，以减少影响设备的已知漏洞。
dueOn|日期时间|此修正活动的创建者设置的截止日期|2021-01-13T00：00：00Z
fixedDevices|.|已修复的设备数量|2
ID|String|此修正活动的 ID|097d9735-5479-4899-b1b7-77398899df92
nameId|String|相关产品名称|Microsoft Silverlight
优先级|String|针对此修正活动的创建者设置的优先级 (高\中\低) |高
productId|String|相关产品 ID|microsoft-_-silverlight
productivityImpactRemediationType|String|只能请求对不影响用户的设备进行一些配置更改。 此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。|AllExposedAssets
rbacGroupNames|String|相关设备组名称|[ "Windows Servers"、"Windows 11"、"Windows 10" ]
recommendedProgram|String|要升级到的推荐程序|NULL
recommendedVendor|String|建议升级到的供应商|NULL
recommendedVersion|String|要更新/升级到的建议版本|NULL
relatedComponent|String|此修正活动的相关组件 (安全建议服务的相关组件) |Microsoft Silverlight
requesterEmail|String|创建者电子邮件地址|globaladmin@UserName.contoso.com
requesterId|String|Creator 对象 ID|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|String|注释 (为) 修正活动添加的自定义文本|NULL
Scid|String|相关安全建议 SCID|NULL
状态|String|修正活动状态 (/已完成) |活动
statusLastModifiedOn|日期时间|更新状态字段的日期|2021-01-12T18：54：11.5499487Z
targetDevices|长型|此修正适用于的公开设备数量|43
Title|String|此修正活动的标题|更新 Microsoft Silverlight
类型|String|修正类型|更新
vendorId|String|相关供应商名称|Microsoft

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a>响应示例

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a>另请参阅

- [修正方法和属性](get-remediation-methods-properties.md)
- [按 ID 获取修正活动](get-remediation-one-activity.md)
- [列出修正活动的暴露设备](get-remediation-exposed-devices-activities.md)
- [基于风险的威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [组织中漏洞](tvm-weaknesses.md)
