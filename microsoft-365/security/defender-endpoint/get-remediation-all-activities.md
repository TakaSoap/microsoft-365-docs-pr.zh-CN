---
title: 列出所有修正活动
description: 返回有关所有修正活动的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务，
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
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061099"
---
# <a name="list-all-remediation-activities"></a>列出所有修正活动

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

返回有关所有修正活动的信息。

[详细了解修正活动](tvm-remediation.md)。

**URL：** GET： /api/remediationTasks

**属性** 详细信息

属性 (id)  | 数据类型 | 说明 | 返回值的示例
:---|:---|:---|:---
“类别” | String | 软件/安全配置 (修正活动的)  | 软件
completerEmail | String | 如果修正活动是由某人手动完成的，此列将包含他们的电子邮件 | 空
completerId | String | 如果修正活动是由某人手动完成的，则此列包含其对象 ID | 空
completionMethod | String | 如果所有设备 (都由选择"标记为已完成) 或"手动"进行修补，则修正活动可以"自动"完成。 | 自动
createdOn | 日期时间 | 创建此修正活动的时间 | 2021-01-12T18：54：11.5499478Z
说明 | String | 此修正活动的说明 | 将 Chrome 更新到更高版本，以缓解影响你的设备的 1248 个已知漏洞。
dueOn | 日期时间 | 此修正活动的创建者设置的截止日期 | 2021-01-13T00：00：00Z
fixedDevices | . | 已修复的设备数量 | 2
id | String | 此修正活动的 ID | 097d9735-5479-4899-b1b7-77398899df92
nameId | String | 相关产品名称 | chrome
priority | String | 为此修正活动设置的创建者设置的优先级 (高\中\低)  | 高
productId | String | 相关产品 ID | google-_-chrome
productivityImpactRemediationType | String | 只能请求对没有用户影响的设备进行一些配置更改。 此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。 | AllExposedAssets
rbacGroupNames | String | 相关设备组名称 | [ "Windows Servers"， "Windows 10" ]
recommendedProgram | String | 要升级到的推荐程序 | 空
recommendedVendor | String | 建议升级到的供应商 | 空
recommendedVersion | String | 要更新/升级到的建议版本 | 空
relatedComponent | String | 此修正活动的相关组件 (安全建议计划的相关组件)  | Google Chrome
requesterEmail | String | 创建者电子邮件地址 | globaladmin@UserName.contoso.com
requesterId | String | Creator 对象 ID | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | String | 注释 (此) 活动的创建者添加的自定义文本 | 空
scid | String | 相关安全建议 SCID | 空
状态 | String | 修正活动状态 (/已完成)  | 活动
statusLastModifiedOn | 日期时间 | 更新状态字段的日期 | 2021-01-12T18：54：11.5499487Z
targetDevices | 长型 | 此修正适用于的公开设备数量 | 43
title | String | 此修正活动的标题 | 更新 Google Chrome
type | String | 修正类型 | 更新
vendorId | String | 相关供应商名称 | google

## <a name="example"></a>示例

**请求** 示例

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

**响应** 示例

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
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
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

- [按 ID 获取一个修正活动](get-remediation-one-activity.md)

- [列出一个修正活动的公开设备](get-remediation-exposed-devices-activities.md)

- [基于风险的威胁&漏洞管理](next-gen-threat-and-vuln-mgt.md)

- [组织中漏洞](tvm-weaknesses.md)
