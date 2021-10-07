---
title: 使用Microsoft 365本地扫描程序的数据丢失防护
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 了解如何使用 Microsoft 365 本地扫描仪扫描停止的数据，并执行本地文件共享和本地 SharePoint 文件夹和文档库的安全操作。
ms.openlocfilehash: d726bfccf7dff2e95e3ccf996544f1db26bf09a2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203143"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner"></a>使用Microsoft 365本地扫描程序数据丢失防护

为帮助熟悉 DLP 本地功能，以及如何在 DLP 策略中显示这些功能，我们汇集了一些方案供你遵循。

> [!IMPORTANT]
> 这些 DLP 本地方案不是创建和调整 DLP 策略的正式过程。 当你需要在常规情况下使用 DLP 策略，请参阅以下主题：
>
> - [了解数据丢失防护](dlp-learn-about-dlp.md)
> - [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)
> - [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
> - [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>方案：发现与 DLP 规则相匹配的文件

DLP 本地扫描仪在几个区域出现数据

#### <a name="activity-explorer"></a>活动资源管理器

 本地 Microsoft DLP 可检测 DLP 规则匹配项，并报告它们 [活动资源管理器](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)。

#### <a name="microsoft-365-audit-log"></a>Microsoft 365 审核日志

审核日志 UI 中提供了 DLP 规则匹配项，请参阅 [在合规中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md)  或可由 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell 访问。

#### <a name="aip"></a>AIP

发现数据以 csv 格式的本地报告提供，存储在以下格式：

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv**。

 查找以下列：

- DLP 模式
- DLP 状态
- DLP 批注
- DLP 规则名称
- DLP 操作
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

- [了解 DLP 本地扫描程序](dlp-on-premises-scanner-learn.md)
- [开始使用 DLP 本地扫描程序](dlp-on-premises-scanner-get-started.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
