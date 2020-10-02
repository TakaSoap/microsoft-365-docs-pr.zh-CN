---
title: 在 DLP 策略中使用敏感度标签作为条件（预览版）
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解可在 DLP 策略中使用敏感度标签作为条件的服务和项目类型
ms.openlocfilehash: 561a6cbd7b8aeb9082862319c5cc6419fd79c896
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321107"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a>在 DLP 策略中使用敏感度标签作为条件（预览版）

在以下位置的 DLP 策略中，可使用[敏感度标签](sensitivity-labels.md)作为条件：

- Exchange Online 电子邮件
- SharePoint Online
- OneDrive for Business 站点
- Windows 10 设备

敏感度标签作为一个选项出现在**内容包含**列表中。

![使用敏感度标签作为条件](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a>支持的项目、方案和策略提示

可在这些项目和方案中使用敏感度标签作为条件。

### <a name="supported-items"></a>支持的项目：

|服务  |项目类型  |可用于策略提示  |可强制实施  |
|---------|---------|---------|---------|
|Exchange    |电子邮件         |是         |是         |
|Exchange    |电子邮件附件         |否*         |否*         |
|SharePoint Online     |SharePoint Online 中的列表         |是         |是         |
|OneDrive for Business     |项目         |是         |是         |
|Teams     |Teams 聊天和通道消息         |不适用         |不适用         |
|Teams     |attachments         |是 **         |是 **         |
|Windows 10 设备（预览版）     |项目         |是         |是         |
|MCAS（预览版） |项目         |是         |是         |

\* 支持 DLP 对电子邮件的敏感度标签进行检测。 不支持 DLP 对带有敏感度标签的电子邮件附件进行检测。

\** 在一对一聊天或频道的 Teams 中发送的附件将自动上传到 OneDrive for Business 和 SharePoint。 因此，如果你的 DLP 策略中包含 SharePoint Online 或 OneDrive for Business，则在 Teams 中发送的带标签的附件将自动包含在此条件的范围内。 不需要在 DLP 策略中选择用作位置的 Teams。

### <a name="supported-scenarios"></a>支持的方案

- 当 DLP 管理员选择将一个或多个敏感度标签作为条件时，将能够看到租户中所有敏感度标签的列表。
- 按上述支持矩阵所示，支持在所有工作负载中使用敏感度标签作为条件
- 对于包含敏感度标签作为条件的 DLP 策略，将继续跨工作负载（Outlook Win32 除外）显示 DLP 策略提示。
- 如果与包含敏感度标签的 DLP 策略匹配，则敏感度标签也将显示为事件报告电子邮件的一部分。
- 敏感度标签的详细信息也将显示在 DLP 规则匹配审核日志中，该策略包含敏感度标签作为条件。


### <a name="support-policy-tips"></a>支持策略提示


|工作负载  |受支持或不支持的策略提示  |
|---------|---------|
|OWA |    支持     |
|Outlook Win 32    |  不支持       |
|SharePoint   |   支持      |
|OneDrive for Business    |    支持     |
|终结点设备   |  不支持       |
