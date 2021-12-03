---
title: Microsoft Defender for Endpoint API 发行说明
description: 对 Microsoft Defender for Endpoint API 集进行更新的发行说明。
keywords: Microsoft Defender for Endpoint API 发行说明， mde， API， 适用于终结点的 Microsoft Defender API， 更新， 注释， 发布
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
ms.openlocfilehash: 2c34add5968021d6a31bffc80ec16e0ebed9baf0
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283649"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Microsoft Defender for Endpoint API 发行说明

**适用于：** 
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

>希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

以下信息列出了对 Microsoft Defender 终结点 API 的更新以及更新的日期。

> [!TIP]
> RSS 源: 通过将以下 URL 复制并粘贴到源阅读器中，可以在页面更新时收到通知: 
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>发行说明 - 最新到最旧 (dd.mm.yyyyy) 

### <a name="06102021"></a>06.10.2021

- 新增了导出评估 API 方法 - _Delta Export software vulnerabilities assessment (JSON response)_ Export assessment methods and properties per [device](get-assessment-methods-properties.md)。

### <a name="05252021"></a>05.25.2021

- 添加了新 API [导出评估方法和属性（每个设备](get-assessment-methods-properties.md)）。

### <a name="03052021"></a>03.05.2021

- 添加了新 API： [修正活动方法和属性](get-remediation-methods-properties.md)。

### <a name="10022021"></a>10.02.2021

- 添加了新 API： [批量更新警报](batch-update-alerts.md)。

### <a name="25012021"></a>25.01.2021

- 更新了高级搜寻 [API](run-advanced-query-api.md) 的速率限制，从每分钟 15 个请求更新为 45 个。

### <a name="21012021"></a>21.01.2021

- 添加了新 API： [通过 标记 查找设备](machine-tags.md)。
- 添加了新 API： [导入指示器](import-ti-indicators.md)。

### <a name="03012021"></a>03.01.2021

- 更新了警报证据：添加了 ***detectionStatus** _*__、parentProcessFilePath_*_ 和 _ *_parentProcessFileName_** 属性。
- 更新 [了 Alert 实体](alerts.md)：添加了 ***一个检测器Id*** 属性。

### <a name="15122020"></a>15.12.2020

- 更新 [了 Device](machine.md) 实体：添加了 ***IpInterfaces*** 列表。 请参阅 [列出设备](get-machines.md)。

### <a name="04112020"></a>04.11.2020

- 添加了新 API： [设置设备值](set-device-value.md)。
- 更新 [了 Device](machine.md) 实体：添加了 ***deviceValue*** 属性。

### <a name="01092020"></a>01.09.2020

- 添加了选项以使用相关证据展开 Alert 实体。 请参阅 [列出警报](get-alerts.md)。
