---
title: 在 DLP 策略中使用敏感度标签作为条件
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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解可在 DLP 策略中使用敏感度标签作为条件的服务和项目类型
ms.openlocfilehash: 1117471e38b430f1d7289c6aae76994ac5acd494
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806884"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>在 DLP 策略中使用敏感度标签作为条件

在以下位置的 DLP 策略中，可将 [敏感度标签](sensitivity-labels.md) 用作条件：

- Exchange Online 电子邮件
- SharePoint Online
- OneDrive for Business 站点
- Windows 10 设备

敏感度标签作为一个选项出现在 **内容包含** 列表中。

> [!div class="mx-imgBorder"]
> ![使用敏感度标签作为条件。](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> 如果选择 **Teams 聊天和频道消息** 作为应用 DLP 策略的位置，则作为条件的 **灵敏度标签** 将不可用。


## <a name="supported-items-scenarios-and-policy-tips"></a>支持的项目、方案和策略提示

可在这些项目和方案中使用敏感度标签作为条件。

### <a name="supported-items"></a>支持的项目：

|服务  |项目类型  |可用于策略提示  |可强制实施  |
|---------|---------|---------|---------|
|Exchange    |电子邮件         |是         |是         |
|Exchange    |电子邮件附件         |否         |是 **         |
|SharePoint Online     |SharePoint Online 中的列表         |是         |是         |
|OneDrive for Business     |项目         |是         |是         |
|Teams     |Teams 聊天和通道消息         |不适用         |不适用         |
|Teams     |attachments         |是 **         |是 **         |
|Windows 10 设备     |项目         |是         |是         |
|MCAS（预览版） |项目         |是         |是         |

\* 仅 Office 文件类型支持对已添加敏感度标签的电子邮件附件进行 DLP 检测。

\** 在一对一聊天或频道的 Teams 中发送的附件将自动上传到 OneDrive for Business 和 SharePoint。 因此，如果你的 DLP 策略中包含 SharePoint Online 或 OneDrive for Business，则在 Teams 中发送的带标签的附件将自动包含在此条件的范围内。 不需要在 DLP 策略中选择用作位置的 Teams。

> [!NOTE]
> DLP 在 SharePoint 和 OneDrive for Business 中检测敏感度标签的能力有限。 有关详细信息，请参阅 [启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md#limitations)。

### <a name="supported-scenarios"></a>支持的方案

- 当 DLP 管理员选择将一个或多个敏感度标签作为条件时，将能够看到租户中所有敏感度标签的列表。

- 按上述支持矩阵所示，支持在所有工作负载中使用敏感度标签作为条件。

- 对于包含敏感度标签作为条件的 DLP 策略，将继续跨工作负载（Outlook Win32 除外）显示 DLP 策略提示。

- 如果与包含敏感度标签的 DLP 策略匹配，则敏感度标签也将显示为事件报告电子邮件的一部分。

- 对于包含敏感度标签作为条件的 DLP 策略匹配，敏感度标签详细信息也将显示在 DLP 规则匹配审核日志中。


### <a name="support-policy-tips"></a>支持策略提示


|工作负载  |受支持或不支持的策略提示  |
|---------|---------|
|OWA |    支持     |
|Outlook Win 32    |  不支持       |
|SharePoint   |   支持      |
|OneDrive for Business    |    支持     |
|终结点设备   |  不支持       |
