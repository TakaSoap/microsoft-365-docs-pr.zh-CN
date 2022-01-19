---
title: 修正活动方法和属性
description: API 响应包含威胁& 漏洞管理租户中创建的修正活动。 你可以为选定的修正任务请求所有修正活动、仅一个修正活动或有关公开的设备的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务， 修正方法， 修正属性，
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
ms.openlocfilehash: 124a44f6a04e4e4e77d80ac91ed4da169e2a4aae
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074554"
---
# <a name="remediation-activity-methods-and-properties"></a>修正活动方法和属性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

API 响应包含[威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)已在租户中创建的修正活动。

## <a name="methods"></a>Methods

方法|数据类型|说明
:---|:---|:---
[列出所有修正活动](get-remediation-all-activities.md)|调查集合|返回有关所有修正活动的信息。
[列出修正活动的暴露设备](get-remediation-exposed-devices-activities.md)|调查实体|返回有关指定修正活动的公开设备的信息。
[按 ID 获取修正活动](get-remediation-one-activity.md)|调查实体|返回指定修正活动的信息。

详细了解修正 [活动](tvm-remediation.md)。

## <a name="properties"></a>属性

属性 ID|数据类型|说明
:---|:---|:---
类别|字符串|软件/安全配置 (修正活动的) 
completerEmail|字符串|如果修正活动是由某人手动完成的，此列将包含他们的电子邮件
completerId|String|如果修正活动是由某人手动完成的，则此列包含其对象 ID
completionMethod|字符串|如果所有设备都由选择"标记为已完成") 或"手动" (，则修正活动可以"自动"完成。
createdOn|DateTime|创建此修正活动的时间
说明|String|此修正活动的说明
dueOn|DateTime|此修正活动的创建者设置的截止日期
fixedDevices||已修复的设备数量
ID|字符串|此修正活动的 ID
nameId|String|相关产品名称
Priority|字符串|针对此修正活动的创建者设置的优先级 (高\中\低) 
productId|字符串|相关产品 ID
productivityImpactRemediationType|字符串|只能请求对不影响用户的设备进行一些配置更改。 此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。
rbacGroupNames|String|相关设备组名称
recommendedProgram|String|要升级到的推荐程序
recommendedVendor|String|建议升级到的供应商
recommendedVersion|String|要更新/升级到的建议版本
relatedComponent|字符串|此修正活动的相关组件 (安全建议计划的相关组件) 
requesterEmail|字符串|创建者电子邮件地址
requesterId|字符串|Creator 对象 ID
requesterNotes|String|注释 (此) 活动添加的自定义文本
Scid|String|相关安全建议 SCID
Status|String|修正活动状态 (/已完成) 
statusLastModifiedOn|DateTime|更新状态字段的日期
targetDevices|长型|此修正适用于的公开设备数量
Title|String|此修正活动的标题
类型|String|修正类型
vendorId|String|相关供应商名称

## <a name="see-also"></a>另请参阅

- [按 ID 获取修正活动](get-remediation-one-activity.md)

- [列出所有修正活动](get-remediation-all-activities.md)

- [列出修正活动的暴露设备](get-remediation-exposed-devices-activities.md)

- [基于风险的威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)

- [组织中漏洞](tvm-weaknesses.md)
