---
title: Microsoft 安全功能分数的新增功能
description: 介绍 Microsoft 365 安全中心中 Microsoft 安全功能分数所发生的新变化。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全功能分数， 安全中心， 改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 644e12d3b9dfecc0a31c8d464033e41670bc7b88
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815227"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 安全功能分数的新增功能

为了让 Microsoft 能够更好地体验安全状态，我们做了一些更改。 若要了解计划的更改，请参阅 [Microsoft 安全功能分数中即将发生的变化](microsoft-secure-score-whats-coming.md)？

## <a name="july-2020"></a>2020 年 7 月

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>为 Azure 高级威胁防护添加改进操作

- 有风险的后续移动路径
- 不安全帐户属性
- 启用 Active Directory 信任上的安全功能
- 从实体中删除不安全 SID 历史记录属性

## <a name="june-2020"></a>2020 年 6 月

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender 高级威胁防护中删除了改进操作

* 打开攻击面减少规则

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>新增了 Microsoft Defender 高级威胁防护的改进操作

* 阻止 Adobe Reader 创建子进程
* 使用针对勒索软件的高级保护
* 阻止所有 Office 应用程序创建子进程
* 阻止 Office 应用程序创建可执行内容
* 阻止 JavaScript 或 VBScript 启动下载的可执行文件的内容
* 阻止执行可能混淆的脚本
* 阻止来自电子邮件客户端和 Web 邮件的可执行内容
* 阻止 Office 通信应用程序创建子进程
* 阻止从 USB 运行的未受信任和未签名的进程
* 通过 WMI 事件订阅阻止持久性
* 阻止 Office 应用程序将代码注入其他进程
* 除非可执行文件符合某个有的普及条件、年限或受信任的列表条件，否则阻止它们运行
* 阻止进程创建源自 PSExec 和 WMI 命令
* 阻止来自 Windows 本地安全机构子系统的凭据 (lsass.exe) 
* 阻止从 Office 宏调用 Win32 API

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Identity 安全功能分数和图形 API 不兼容

在最新版本的 Microsoft 安全功能分数中，发布了改进的扫描模型。 这些更改可对安全状态更灵活且更准确地了解。 但是，这些更新让 Microsoft 安全功能分数临时与 Identity 安全功能分数和 Graph API 不兼容。

此时，Identity 安全功能分数和 Graph API 将采用新的分段模型。 在这之前，客户将看到 Microsoft 安全功能分数、Identity Secure Score 和 Graph API 报告的分数差异。 我们对这一原因造成的任何不便表示，我们在努力确保这些体验以后兼容性更好。

## <a name="updated-improvement-actions"></a>更新的改进操作

- 添加了 Azure Active Directory 改进操作
- 添加了 Azure 高级威胁防护改进操作
- 支持 Microsoft Defender ATP [威胁&管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全建议
    - 现在 TVM 提供的所有已发布安全建议均可用

## <a name="updated-interface-and-functionality"></a>已更新的界面和功能

* CISO 和潜在前导级别讨论的所有新的指标和趋势视图
* 跟踪分数和基准的新方法
* 更好地跟踪和了解分数回合
* 筛选、标记、搜索和分组改进操作
* 使用得分和计划的操作管理你的未来目标
* 更多信息！

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的欢迎大利

如果你有任何问题，请通过发布安全、隐私条规 [社区&我们](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 了解我们。 我们正在监控社区并提供帮助。

## <a name="related-resources"></a>相关资源

- [评估你的安全状况](microsoft-secure-score-improvement-actions.md)
- [跟踪 Microsoft 安全功能分数历史记录和达到目标](microsoft-secure-score-history-metrics-trends.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
