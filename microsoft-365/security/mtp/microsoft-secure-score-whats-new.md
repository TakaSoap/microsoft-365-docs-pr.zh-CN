---
title: Microsoft 安全分数中的新增功能
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数发生了哪些新更改。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
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
ms.openlocfilehash: 8b0fda2d8a0b7d9cb6b2c6a4cca2e8e34a876fec
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289419"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 安全分数中的新增功能

若要使 Microsoft 安全得分更好地代表安全状态，我们做了一些更改。 若要了解计划的更改，请参阅 [Microsoft Secure 评分中的内容？](microsoft-secure-score-whats-coming.md)。

## <a name="august-2020"></a>2020 年 8 月

### <a name="update-improvement-action-for-azure-active-directory"></a>Azure Active Directory 更新改进操作

- 启用策略以阻止旧版身份验证

## <a name="july-2020"></a>2020 年 7 月

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>为 Azure 高级威胁防护添加改进操作

- 有风险的横向移动路径
- 不安全帐户属性
- 在 Active Directory 信任上启用安全功能
- 从实体中删除不安全的 SID 历史记录属性

## <a name="june-2020"></a>2020 年 6 月

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender 高级威胁防护的已删除改进操作

* 打开攻击面降低规则

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>新增了 Microsoft Defender 高级威胁防护的改进措施

* 阻止 Adobe Reader 创建子流程
* 对勒索软件使用高级防护
* 阻止所有 Office 应用程序创建子进程
* 阻止 Office 应用程序创建可执行内容
* 阻止 JavaScript 或 VBScript 启动下载的可执行内容
* 阻止执行可能模糊的脚本
* 阻止来自电子邮件客户端和 web 邮件的可执行内容
* 阻止 Office 通信应用程序创建子进程
* 阻止从 USB 运行的不受信任和未签名的进程
* 通过 WMI 事件订阅阻止持久化
* 阻止 Office 应用程序将代码注入其他进程
* 阻止可执行文件运行，除非它们满足流行、年龄或受信任的列表条件
* 阻止进程创建源自 PSExec 和 WMI 命令
* 阻止从 Windows 本地安全颁发机构子系统中盗取凭据 ( # A0) 
* 阻止来自 Office 宏的 Win32 API 调用

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>标识安全分数和图形 API 不兼容

在最近发布的 Microsoft 安全分数中，已发布了一个改进的计分模型。 通过这些更改，可以更灵活、准确地查看安全状况。 但是，这些更新已使 Microsoft 安全分数暂时与标识安全分数和 Graph API 不兼容。

在时间中，标识安全分数和图形 API 将采用新的评分模型。 在此之前，客户将看到 Microsoft 安全分数、标识安全分数和图形 API 所报告的分数之间的差异。 对于此导致的不便，我们深表歉意，并在努力确保这些体验在将来更具兼容性。

## <a name="updated-improvement-actions"></a>更新的提高操作

- 添加了 Azure Active Directory 改善操作
- 添加了 Azure 高级威胁防护改进操作
- 对 Microsoft Defender ATP 威胁的支持 [& 漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全建议
    - TVM 提供的所有已发布的安全建议现已推出

## <a name="updated-interface-and-functionality"></a>更新的界面和功能

* CISO 和潜在客户级别讨论的所有新指标和趋势视图
* 跟踪和基准成绩的新方法
* 更好地跟踪和理解分数回归
* 筛选、标记、搜索和分组您的改进操作
* 使用分数预测和计划操作来管理未来目标
* 更多！

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

如果你有任何问题，请通过在 [安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。 我们正在监视社区，并将提供帮助。

## <a name="related-resources"></a>相关资源

- [评估你的安全状况](microsoft-secure-score-improvement-actions.md)
- [跟踪你的 Microsoft 安全分数历史记录并实现目标](microsoft-secure-score-history-metrics-trends.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
