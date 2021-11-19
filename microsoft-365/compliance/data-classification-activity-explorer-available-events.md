---
title: 标记活动资源管理器中报告的操作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活动资源管理器中可用的标签活动列表。
ms.openlocfilehash: feed9d29deb94263d242967bdef38209cda660e1
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111419"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>活动资源管理器中可用的标记活动

## <a name="sensitivity-label-applied"></a>应用的敏感度标签

每次标记未标记的文档或发送带有敏感度标签的电子邮件时，将生成此事件。

- 在本机应用程序和 Web 应用程序中保存Office捕获它。
- 在 Azure 信息保护加载项中出现时捕获它。
- 还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。

|Source  |在活动资源管理器中报告 | 注意  |
|---------|---------|---------|
| Word、Excel、PowerPoint|是 |
|Outlook| 是 | |
|SharePoint联机，OneDrive|是 | |
|Exchange        |是         | |
|Azure 信息保护 (AIP) 统一客户端和 AIP 统一扫描程序 |是 |AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签   |
|Microsoft 信息保护 (MIP) SDK         |是|AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签|
|权限管理服务 (RMS)          |不适用         | |
|Power BI桌面和 Web        | 否| 在审核日志中Microsoft 365访问         |
|Microsoft Defender for Cloud Apps         |否|         |

## <a name="sensitivity-label-changed"></a>敏感度标签已更改

每次更新文档或电子邮件的敏感度标签时，将生成此事件。

- 对于 AIP 统一客户端、统一扫描程序和 MIP  SDK 源，AIP 升级标签和 *降级* 标签操作映射到活动资源管理器 *标签已更改*

- 在本机应用程序和 Web 应用程序中的保存Office捕获它。
- 在 Azure 信息保护统一客户端加载项和扫描程序实施中出现时捕获
- 还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。 除了 *SharePoint* Online 和 OneDrive 之外，还将捕获对齐文本。
- 在 Office 上的本机应用中Outlook敏感度标记收集在文件保存/电子邮件发送操作之前生成的最后一个操作。 例如，如果用户在发送电子邮件之前多次更改电子邮件的标签，电子邮件发送时找到的最后一个标签将捕获到 审核日志 然后在活动资源管理器中报告。

|Source  |在活动资源管理器中报告|注意  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |是         |
|Outlook         |是         |
|SharePoint Online，OneDrive         |是         |
|Exchange         |是         |
|AIP 统一客户端         |是         |
|AIP 统一扫描程序         |是         |
|MIP SDK         |是         |
|RMS 服务         |不适用         |
|Power BI桌面和 Web         |否         |在审核日志中Microsoft 365访问 |
|Microsoft Defender for Cloud Apps     |否         |         |

## <a name="sensitivity-label-removed"></a>删除了敏感度标签

每次从文件或文档中删除敏感度标签时，将生成此事件。

- 在本机应用程序和 Web 应用程序中保存Office捕获此事件。
- 在 Azure 信息保护加载项中出现时捕获它。
- 敏感度标签（Office本机 MIP 标签Outlook收集在文件保存/电子邮件发送操作之前生成的最后一个标签事件。

|Source  |在活动资源管理器中报告 | 注意  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |是         |
|Outlook         |是         ||
|SharePoint Online，OneDrive         |是         |
|Exchange         |是         |
|AIP 统一客户端         |是         |AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作|
|AIP 统一扫描程序         |是         |AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作 |
|MIP SDK         |是         |AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作 |
|RMS 服务         |不适用         |
|Power BI桌面和 Web         |否         |在审核日志中Microsoft 365访问 |
|Microsoft Defender for Cloud Apps     |否         |         |

## <a name="sensitivity-label-file-read"></a>已读取敏感度标签文件

每次打开标记为或受保护的文档的敏感度文档时，将生成此事件。

|Source  |在活动资源管理器中报告 | 注意  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |是         |
|Outlook         |否         |
|SharePoint Online，OneDrive         |否         |
|Exchange         |否         |
|AIP 统一客户端         |是         |AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作|
|AIP 统一扫描程序         |是         |AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作|
|MIP SDK         |是         |AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作|
|RMS 服务         |是         |访问 *操作* 映射到活动 *资源管理器中的文件读取* 操作 |
|Power BI桌面和 Web         |否         |在审核日志中Microsoft 365访问 |
|Microsoft Defender for Cloud Apps     |否         |         |

## <a name="files-discovered"></a>发现的文件

每次发现文件时，当使用 AIP 扫描程序扫描不同位置的敏感数据并查找文件时，将生成此事件。

|Source  |在活动资源管理器中报告 | 注意  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |不适用         |
|Outlook         |不适用         |
|SharePoint Online，OneDrive         |不适用         |
|Exchange         |不适用         |
|AIP 统一客户端         |不适用       |
|AIP 统一扫描程序         |是         |AIP *发现* 操作映射到活动 *资源管理器中发现* 的文件操作|
|MIP SDK         |是         |AIP *发现* 操作映射到活动 *资源管理器中发现* 的文件操作|
|RMS 服务         |不适用         |
|Power BI桌面和 Web         |不适用         |
|Microsoft Defender for Cloud Apps     |不适用         |         |

## <a name="sensitivity-label-file-renamed"></a>已重命名敏感度标签文件

每次重命名具有敏感度标签的文档时，将生成此事件。

|Source  | 在活动资源管理器中报告 | 注意  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |是         |
|Outlook         |不适用         |
|SharePoint Online，OneDrive         |否        |
|Exchange         |不适用         |
|AIP 统一客户端         |否         |
|AIP 统一扫描程序         |否         |
|MIP SDK         |否         |
|RMS 服务         |否      |
|Power BI桌面和 Web         |否         |
|Microsoft Defender for Cloud Apps     |否         |         |

## <a name="file-removed"></a>文件已删除

每次 AIP 扫描程序检测到之前扫描的文件已删除时，将生成此事件。

|Source  |在活动资源管理器中报告 | 注意  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |不适用         |
|Outlook         |不适用         |
|SharePoint Online，OneDrive         |不适用           |
|Exchange         |不适用         |
|AIP 统一客户端         |不适用            |
|AIP 统一扫描程序         |是         |
|MIP SDK         |不适用            |
|RMS 服务         |不适用         |
|Power BI桌面和 Web         |不适用  |
|Microsoft Defender for Cloud Apps     |不适用        |         |

### <a name="protection-applied"></a>已应用保护

此事件生成首次保护时手动添加到没有标签的项。

|Source  |在活动资源管理器中报告 | 注意  |
|---------|---------|---------|
|Word、Excel、PowerPoint         |否         |
|Outlook         |否         |
|SharePoint Online，OneDrive         |不适用           |
|Exchange         |否       |
|AIP 统一客户端         |是            |
|AIP 统一扫描程序         |不适用         |
|MIP SDK         |是            |
|RMS 服务         |不适用         |
|Power BI桌面和 Web         |不适用            |
|Microsoft Defender for Cloud Apps     |不适用        |         |

## <a name="protection-changed"></a>保护已更改

每次手动更改未标记文档的保护时，将生成此事件。

|Source  |在活动资源管理器中报告 |
|---------|---------|
|Word、Excel、PowerPoint         |否         |
|Outlook         |否         |
|SharePoint Online，OneDrive         |不适用           |
|Exchange         |否       |
|AIP 统一客户端         |是            |
|AIP 统一扫描程序         |不适用         |
|MIP SDK         |是            |
|RMS 服务         |不适用         |
|Power BI桌面和 Web         |不适用            |
|Microsoft Defender for Cloud Apps     |不适用        |

## <a name="protection-removed"></a>已删除保护

每次手动更改未标记文档的保护时，将生成此事件。

|Source  |在活动资源管理器中报告 |
|---------|---------|
|Word、Excel、PowerPoint         |否         |
|Outlook         |否         |
|SharePoint Online，OneDrive         |不适用           |
|Exchange         |否       |
|AIP 统一客户端         |是            |
|AIP 统一扫描程序         |不适用         |
|MIP SDK         |是            |
|RMS 服务         |不适用         |
|Power BI桌面和 Web         |不适用            |
|Microsoft Defender for Cloud Apps     |不适用        |

## <a name="dlp-policy-matched"></a>匹配的 DLP 策略

每次在文档或电子邮件上匹配 DLP 策略时，将生成此事件。

|Source  |在活动资源管理器中报告 |
|---------|---------|
|Exchange         |是       |
|SharePoint Online|是          |
|OneDrive |是|
|Teams |是   |
|Windows 10 设备         |是 |
|MAC         |否     |
|本地         |否|
|Microsoft Defender for Cloud Apps     |否        |

终结点 DLP Windows 10 设备 (事件) 为：

- 删除文件
- 已创建文件
- 已复制到剪贴板的文件
- 已修改文件
- 已读文件
- 已打印的文件
- 已重命名文件
- 已复制到网络共享的文件
- 不允许应用访问的文件

## <a name="retention-label-applied"></a>应用的保留标签

每次标记未标记的文档或发送带有保留标签的电子邮件时，将生成此事件。

- 它在保存文档时和发送电子邮件时捕获。

|Source  |在活动资源管理器中报告 |
|---------|---------|
|Exchange         |否       |
|SharePoint Online|是          |
|OneDrive |是|

## <a name="retention-label-changed"></a>已更改保留标签

每次更新文档或电子邮件的标签时，将生成此事件。

- 它在保存文档时和发送电子邮件时捕获。

|Source  |在活动资源管理器中报告 |
|---------|---------|
|Exchange         |否       |
|SharePoint Online|是          |
|OneDrive |是|

## <a name="retention-label-removed"></a>已删除保留标签

每次从文件或文档中删除标签时，将生成此事件。

- 它在保存文档时和发送电子邮件时捕获。

|Source  |在活动资源管理器中报告 |
|---------|---------|
|Exchange         |否       |
|SharePoint Online|是          |
|OneDrive |是|

## <a name="known-issues"></a>已知问题
  
- 向最终用户显示推荐的标签工具提示时，不会捕获它。 但是，如果用户选择应用建议的标签，标签将显示在如何应用 *字段下推荐*。 

- 从敏感度标签降级和从应用降级时，SharePoint OneDrive。

- 敏感信息类型当前不适用于 Word、Excel、PowerPoint 和 Outlook、SharePoint Online 和 OneDrive 中的自动标记OneDrive。
