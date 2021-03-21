---
title: 安全与合规中心中的报告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: 使用安全&中心获取 SharePoint Online 和 Exchange Online 组织的各种报告，以及 Azure Active Directory 报告。
ms.openlocfilehash: 3e72ecab68ece31c44d99f85806492e788f4cd7c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926150"
---
# <a name="reports-in-the-security--compliance-center"></a>安全与合规中心中的报告

您可以使用 **安全与合规** 中心中的"查看报告"&快速访问 SharePoint Online 和 Exchange Online 组织的审核报告。 还可以从查看报告 (访问 Azure Active Directory) AD) 用户登录报告、用户活动报告和 Azure AD 审核日志 Azure AD **帐户。** 这是因为你的付费 Microsoft 365 订阅包含 Microsoft Azure 的免费订阅。 首次尝试访问这些 Azure 报告时，必须完成一次注册过程。 
  
> [!TIP]
> 若要查看有关组织中活动的其他报告，请参阅 Microsoft [365 管理中心中的活动报表](../admin/activity-reports/activity-reports.md)。 
  
 **开始之前**
  
您需要以下权限才能查看安全与合规中心&报告。
  
- 您必须在 Exchange 管理中心 (EAC) 分配安全读者角色，才能在安全与合规&报告。 默认情况下，此角色分配给 EAC 中的"组织管理"和"安全读者"角色组。
    
- 您必须在安全与合规中心View-Only DLP 合规性管理&查看安全与合规中心中的 DLP &报告。 默认情况下，此角色分配给安全与合规中心中的合规性管理员、组织管理、安全管理员和安全读者&组。

- 此外，您必须在 EAC 中View-Only收件人"角色，以查看 EAC 中的 DLP 报告。 默认情况下，此角色分配给 EAC 中的合规性管理、组织View-Only组织管理角色组。
  
 **若要在安全与合规中心内打开"查看&页面：**
  
1. 转到 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 使用组织中用户帐户的凭据登录。
    
在 **"查看报告** "页上，可以查看以下类型的报告： 
  
- [审核报告](#auditing-reports)
- [监管审核报告](#supervisory-review-report)
- [数据丢失防护报告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>审核报告

下表介绍了安全与合规中心的"查看报告"页上"审核"&报告。 
  
|**报告**|**说明**|
|:-----|:-----|
|**审核日志报告** <br/> |你可以搜索审核日志中的用户和管理员活动。 该报告包含 Exchange Online、SharePoint Online、OneDrive for Business 和 Azure Active Directory（Office 365 的目录服务）中的条目用户和管理员活动。 有关详细信息，请参阅 Search [the 审核日志 in the Office 365](search-the-audit-log-in-security-and-compliance.md)。  <br/> |
|**Azure AD 报告** <br/> |若要查找组织中异常或可疑的登录活动，可以使用 Microsoft Azure 中的登录和活动报告。 还可以查看 Azure AD 服务中的审核日志。 若要查看 Azure 中的报告，只需单击查看 **Azure AD 报告**。 有关详细信息，请参阅： <br/><br/>[使用 Office 365 中的免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)。 <br/> [查看你的访问和使用情况报告](/azure/active-directory/reports-monitoring/overview-reports)。  <br/> |
|**Exchange 审核报告** <br/> | 可以使用 Microsoft 365 中的审核功能跟踪组织的管理员对 Exchange Online 配置所做的更改。 还将记录 Microsoft 数据中心管理员或委派管理员对 Exchange Online 组织所做的更改。 对于 Exchange Online，管理员审核日志记录默认启用，因此不必执行任何操作来启用它。 Exchange Online 还提供邮箱审核日志记录，使你可以跟踪邮箱所有者外的其他用户对邮箱的访问。 对于需要跟踪非所有者访问的每个邮箱，你必须启用邮箱审核日志记录。  <br/>  对于管理员和邮箱审核日志记录，你可以运行审核报告来查看审核日志条目。 你还可以导出邮箱和管理员审核日志，它们会作为电子邮件附件在 24 小时内以 XML 文件格式发送给你。 <br/><br/>有关导出审核日志的详细信息，请参阅：  <br/><br/> [导出邮箱审核日志](/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) <br/> [查看和导出数据中心审核日志](/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) <br/> [搜索角色组更改或管理员审核日志](/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) <br/>   [Exchange 审核报告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)。  <br/> |
   
## <a name="supervisory-review-report"></a>监管审核报告

使用监管审核报告，可以看到组织中所有监管审核策略的状态。 有关详细信息，请参阅 [为组织配置监管审核策略](./communication-compliance-configure.md)。
  
## <a name="data-loss-prevention-reports"></a>数据丢失防护报告

DLP 报告 (DLP) 报告包含有关已应用于组织中包含敏感数据的内容的 DLP 策略和规则的信息。 你还可以配置报告，以显示有关基于你的 DLP 策略和规则的 DLP 操作的信息。 有关详细信息，请参阅 [查看数据丢失防护报告](view-the-dlp-reports.md)。