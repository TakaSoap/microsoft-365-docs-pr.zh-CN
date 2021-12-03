---
title: 计算机资源类型
description: 了解 Microsoft Defender for Endpoint 中 Machine 资源类型的方法和属性。
keywords: api， 受支持的 api， 获取， 计算机
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 80ac3e9ed43de98d32fd14063261452cfd5b1372
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284045"
---
# <a name="machine-resource-type"></a>计算机资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

<br>

****

|方法|返回类型|说明|
|---|---|---|
|[列出计算机](get-machines.md)|[计算机](machine.md) 集合|列出 [组织中的计算机](machine.md) 实体集。|
|[获取计算机](get-machine-by-id.md)|[计算机](machine.md)|按 [计算机标识](machine.md) 获取计算机。|
|[获取登录用户](get-machine-log-on-users.md)|[user](user.md) 集合|获取登录到 [计算机](user.md) 的用户 [集](machine.md)。|
|[获取相关警报](get-machine-related-alerts.md)|[警报](alerts.md)集合|获取 [计算机上引发](alerts.md) 警报实体 [集](machine.md)。|
|[获取已安装的软件](get-installed-software.md)|[software](software.md) 集合|检索与给定计算机 ID 相关的已安装软件的集合。|
|[发现漏洞](get-discovered-vulnerabilities.md)|[漏洞](vulnerability.md) 集合|检索与给定计算机 ID 相关的已发现漏洞的集合。|
|[获取安全建议](get-security-recommendations.md)|[建议](recommendation.md) 集合|检索与给定计算机 ID 相关的安全建议集合。|
|[添加或删除计算机标记](add-or-remove-machine-tags.md)|[计算机](machine.md)|向特定计算机添加或删除标记。|
|[按 IP 查找计算机](find-machines-by-ip.md)|[计算机](machine.md) 集合|查找使用 IP 查看的计算机。|
|[通过标记查找计算机](find-machines-by-tag.md)|[计算机](machine.md) 集合|按标记 查找 [计算机](machine-tags.md)。|
|[查找缺失的 KBS](get-missing-kbs-machine.md)|KB 集合|获取与计算机 ID 关联的缺失的 KB 列表|
|[设置设备值](set-device-value.md)|[计算机](machine.md) 集合|设置 [设备 的值](tvm-assign-device-value.md)。|
|[更新计算机](update-machine-method.md)|[计算机](machine.md) 集合|获取计算机的更新状态。|
|

## <a name="properties"></a>属性

<br>

****

|属性|类型|说明|
|---|---|---|
|id|String|[计算机](machine.md) 标识。|
|computerDnsName|String|[计算机](machine.md) 完全限定的名称。|
|firstSeen|DateTimeOffset|Microsoft Defender for [](machine.md) Endpoint 观测到计算机的第一个日期和时间。|
|lastSeen|DateTimeOffset|上次接收的完整设备报告的时间和日期。 设备通常每 24 小时发送一次完整报告。|
|osPlatform|String|操作系统平台。|
|onboardingstatus|String|计算机载入的状态。 可能的值是："onboarded"和"offboarded"。|
|osProcessor|String|操作系统处理器。 请改为使用 osArchitecture 属性。|
|version|String|操作系统版本。|
|osBuild|Nullable long|操作系统内部版本编号。|
|lastIpAddress|String|计算机上本地 NIC 上的最后一[个 IP。](machine.md)|
|lastExternalIpAddress|String|计算机访问 Internet [的最后](machine.md) 一个 IP。|
|healthStatus|枚举|[计算机](machine.md) 运行状况状态。 可能的值包括："Active"、"Inactive"、"ImpairedCommunication"、"NoSensorData"、"NoSensorDataImpairedCommunication"和"Unknown"。|
|rbacGroupName|String|计算机组名称。|
|rbacGroupId|String|计算机组 ID。|
|riskScore|Nullable Enum|由 Microsoft Defender 终结点评估的风险评分。 可能的值包括："None"、"Informational"、"Low"、"Medium"和"High"。|
|aadDeviceId|Nullable 表示形式 Guid|AAD加入 ([时，AAD](machine.md)设备 ID) 。|
|machineTags|String collection|计算机 [标记](machine.md) 集。|
|exposureLevel|Nullable Enum|由 Microsoft Defender for Endpoint 评估的曝光级别。 可能的值包括："None"、"Low"、"Medium"和"High"。|
|deviceValue|Nullable Enum|[设备 的值](tvm-assign-device-value.md)。 可能的值包括："Normal"、"Low"和"High"。|
|ipAddresses|IpAddress 集合|***IpAddress 对象*** 集。 请参阅[获取计算机 API。](get-machines.md)|
|osArchitecture|String|操作系统体系结构。 可能的值是："32 位"、"64 位"。 使用此属性，而不是 osProcessor。|
|
