---
title: 使用 Microsoft 365 数据丢失防护本地扫描程序（预览版）
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 了解如何使用 Microsoft 365 本地扫描仪扫描停止的数据，并执行本地文件共享和本地 SharePoint 文件夹和文档库的安全操作。
ms.openlocfilehash: 0abe36af5588c1828da106779a144b6e7f37d6a8
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114150"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>使用 Microsoft 365 本地扫描仪的数据丢失防护（预览）

为帮助熟悉 DLP 本地功能，以及如何在 DLP 策略中显示这些功能，我们汇集了一些方案供你遵循。

> [!IMPORTANT]
> 这些 DLP 本地方案不是创建和调整 DLP 策略的正式过程。 当你需要在常规情况下使用 DLP 策略，请参阅以下主题：
>- [了解数据丢失防护](dlp-learn-about-dlp.md)
>- [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)
>- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
>- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>方案：发现与 DLP 规则相匹配的文件

DLP 本地扫描仪在几个区域出现数据

#### <a name="activity-explorer"></a>活动资源管理器

 本地 Microsoft DLP 可检测 DLP 规则匹配项，并报告它们 [活动资源管理器](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)。 
 
#### <a name="microsoft-365-audit-log"></a>Microsoft 365 审核日志

在公共预览期间，DLP 规则匹配项在审核日志 UI 中可用，请参阅 [在合规中心](search-the-audit-log-in-security-and-compliance.md)  中搜索审核日志，或由 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell 访问。

#### <a name="aip"></a>AIP

发现数据以 csv 格式的本地报告提供，存储在以下格式：

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv**。

 查找以下列：
- DLP 模式
- DLP 状态
- DLP 批注
- DLP 规则名称 DLP 操作
- 所有者
- 当前 NTFS 权限 （SDTFS）
- 已应用 NTFS 权限 （SDTF）
- NTFS 权限类型
 
### <a name="scenario-enforce-dlp-rule"></a>方案：强制实施 DLP 规则 

如果要对扫描的文件强制实施 DLP 规则，必须在 AIP 中的内容扫描作业和 DLP 中的策略级别启用强制。


#### <a name="configure-dlp-to-enforce-policy-actions"></a>配置 DLP 以强制实施策略操作

1. 打开 [数据丢失防护页面](https://compliance.microsoft.com/datalossprevention?viewid=policies) 并选择针对在 AIP 中配置本地位置存储库的 DLP 策略。 
2. 编辑策略。
3. 在" **测试"或打开策略** 页上，选择 **是，然后**。 

## <a name="see-also"></a>另请参阅

- [了解 DLP 本地扫描仪（预览）](dlp-on-premises-scanner-learn.md)
- [开始使用 DLP 本地扫描仪（预览）](dlp-on-premises-scanner-get-started.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)