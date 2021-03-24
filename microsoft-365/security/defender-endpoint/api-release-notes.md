---
title: Microsoft Defender for Endpoint API 发行说明
description: 对 Microsoft Defender for Endpoint API 集进行更新的发行说明。
keywords: microsoft defender for endpoint api release notes， mde， apis， mdatp api， updates， notes， release
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e37841fa17a5998c431c6a76b878f20ef1b06d10
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054844"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Microsoft Defender for Endpoint API 发行说明

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

以下信息列出了对 Microsoft Defender 终结点 API 的更新以及更新的日期。


> [!TIP]
> RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中： 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a>10.02.2021
<hr>

- 添加了新 API： [批量更新警报](batch-update-alerts.md)。 

<br>

### <a name="25012021"></a>25.01.2021
<hr>

- 更新了高级搜寻 [API](run-advanced-query-api.md) 的速率限制，从每分钟 15 个请求更新为 45 个。 

<br>

### <a name="21012021"></a>21.01.2021
<hr>

- 添加了新 API： [通过 标记 查找设备](machine-tags.md)。 
- 添加了新 API： [导入指示器](import-ti-indicators.md)。 

<br>

### <a name="03012021"></a>03.01.2021
<hr>

- 更新了警报证据：添加了 ***detectionStatus** _*__、parentProcessFilePath_*_ 和 _ *_parentProcessFileName_** 属性。
- 更新 [了 Alert 实体](alerts.md)：添加了 ***一个检测器Id*** 属性。

<br>

### <a name="15122020"></a>15.12.2020
<hr>

- 更新 [了 Device](machine.md) 实体：添加了 ***IpInterfaces*** 列表。 请参阅 [列出设备](get-machines.md)。

<br>

### <a name="04112020"></a>04.11.2020
<hr>

- 添加了新 API： [设置设备值](set-device-value.md)。
- 更新 [了 Device](machine.md) 实体：添加了 ***deviceValue*** 属性。

<br>

### <a name="01092020"></a>01.09.2020
<hr>

- 添加了选项以使用相关证据展开 Alert 实体。 请参阅 [列出警报](get-alerts.md)。

<br>
<br>