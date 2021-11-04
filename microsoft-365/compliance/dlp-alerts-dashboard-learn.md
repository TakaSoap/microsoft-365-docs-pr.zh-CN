---
title: 了解数据丢失防护警报仪表板
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 了解数据丢失防护警报和警报仪表板。
ms.openlocfilehash: 375b16a3072f40ef8f366f7c1c4e8f714f195d63
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754369"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>了解数据丢失防护警报仪表板

当 DLP (数据丢失防护) 策略中的条件与用户对敏感项目采取的操作匹配时，该策略可能会生成警报。 这种情况可能会导致大量警报。 DLP 警报收集在警报仪表板中。 警报仪表板为你提供了一个地方，可以深入调查有关策略匹配的所有详细信息。  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>工作负载

DLP[警报管理仪表板](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)（位于<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>中）显示有关这些工作负载的 DLP 策略警报：

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10 设备 

> [!TIP]
> 使用符合[使用 DLP](endpoint-dlp-learn-about.md)条件Teams终结点[DLP](dlp-microsoft-teams.md)的客户将在 DLP 警报管理仪表板中查看其Teams DLP 策略警报和 DLP 策略警报。

## <a name="single-alert-and-aggregate-alert"></a>单个警报和聚合警报

可以在 DLP 策略中配置两种类型的警报。

单事件警报通常用于监视低量发生的高度敏感事件的策略，例如，在组织外发送一封包含 10 个或多个客户信用卡号的电子邮件。

**聚合事件警报** 通常用于监视一段时间内发生量较高的事件的策略。 例如，在 48 小时内向组织外发送 10 封单独电子邮件（每封电子邮件包含一个客户信用卡号）时，可能会触发聚合警报。

## <a name="types-of-events"></a>事件类型

下面是与警报关联的一些事件。 在 UI 中，你可以选择一个特定的事件来查看其详细信息。 

### <a name="event-details"></a>事件详情

|属性名  |说明  |事件类型  |
|---------|---------|---------|
|ID |与事件关联的唯一 ID |所有事件 |
|位置 |检测到事件的工作负荷|所有事件 |
|活动时间     |符合 DLP 策略条件的用户活动时间 |

### <a name="affected-entities"></a>受影响的实体

|属性名 |说明| 事件类型|
|---------|---------|---------|
|用户 | 执行导致策略匹配的操作的用户 | 所有事件|
|hostname | 发生 DLP 策略匹配的计算机的主机名 | 设备事件|
|IP 地址 | 发生 DLP 策略匹配的计算机的 IP 地址 | 设备事件|
|sha1 |文件的 SHA-1 哈希 | 设备事件|
|sha256 | 文件的 SHA-256 哈希 | 设备事件|
|MDATP 设备 ID | 终结点设备 MDATP ID|
|文件大小 | 文件大小| SharePoint、OneDrive和设备事件|
|文件路径 | DLP 策略匹配所涉及的项目的绝对路径 | SharePoint、OneDrive 和设备事件|
|电子邮件收件人 |如果电子邮件是符合 DLP 策略的敏感项目，则此字段包括该电子邮件的收件人| Exchange事件|
|电子邮件主题 |与 DLP 策略匹配的电子邮件主题 |Exchange事件|
|电子邮件附件 | 电子邮件中匹配 DLP 策略的附件的名称| Exchange事件|
|网站所有者 |网站所有者的名称| SharePoint和OneDrive事件|
|网站 URL |DLP 策略匹配SharePoint或OneDrive的完整 URL |SharePoint和OneDrive事件|
|已创建文件 |创建与 DLP 策略匹配的文件的时间 |SharePoint和OneDrive事件|
|上次修改文件 | 上次更改匹配 DLP 策略的文件的时间 | SharePoint和OneDrive事件|
|文件大小 | 与 DLP 策略匹配的文件大小 |SharePoint和OneDrive事件|
|文件所有者 |与 DLP 策略匹配的文件的所有者 |SharePoint和OneDrive事件|  

### <a name="policy-details"></a>策略详细信息

|属性名 |说明 |事件类型 |
|---------|---------|---------|
|匹配的 DLP 策略 |匹配的 DLP 策略的名称 |所有事件|
|规则匹配 |匹配的 DLP 策略规则的名称 |所有事件|
|检测到 SIT (敏感信息) 类型|检测到作为 DLP 策略匹配的一部分的 SIT |所有事件|
|执行的操作 |导致 DLP 策略匹配的操作| 所有事件|
|违反操作 | 引发 DLP 警报的终结点设备上的操作| 设备事件 | 
|用户过度控制策略 |用户通过策略提示覆盖策略 | 所有事件|
|使用替代理由 |用户为替代提供的原因文本 | 所有事件|   

## <a name="see-also"></a>另请参阅

- [数据丢失防护警报仪表板入门](dlp-alerts-dashboard-get-started.md)
- [从数据丢失防护开始](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)
