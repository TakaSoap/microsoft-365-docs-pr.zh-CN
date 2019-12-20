---
title: Service Organization Controls (SOC)
description: Microsoft 云服务符合 Service Organization Controls 操作安全标准。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 380e1b2fadc48c395fbd8c2b10c0d65a6ba01675
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804255"
---
# <a name="service-organization-controls-soc"></a>Service Organization Controls (SOC)

## <a name="soc-1-2-and-3-reports-overview"></a>SOC 1、2 和 3 报告概述

企业越来越多地将基本功能（例如数据存储和应用程序的访问权）外包给云服务提供商 (CSP) 和其他服务组织。 为此，美国注册会计师协会 (AICPA) 开发出了 Service Organization Controls (SOC) 框架，这是一种用于保护云中存储和处理的信息机密性和隐私性的控制措施标准。 该标准符合 International Standard on Assurance Engagements (ISAE)，后者是一种针对国际服务组织的报告标准。

基于 SOC 框架的服务审核分为两类：SOC 1 和 SOC 2，适用于范围内 Microsoft 云服务。

SOC 1 审核针对审计财务报表的 CPA 事务所，可评估 CSP 内部控制措施的有效性，这些内部控制措施会影响使用提供商云服务的客户的财务报告。 《鉴证业务准则公告》(SSAE 18) 和《鉴证业务国际准则 第 3402 号》(ISAE 3402) 是进行审核的标准，也是 SOC 1 报告的基础。

SOC 2 审核基于 AICPA Trust Service Principles and Criteria 来衡量 CSP 系统的有效性。 Attest Engagement under Attestation Standards (AT) 条例 101 是 SOC 2 和 SOC 3 报告的基础。

在 SOC 1 或 SOC 2 审核结尾部分，服务审核员会在 SOC 1 Type 2 或 SOC 2 Type 2 报告中提供评价意见，用于描述 CSP 系统并评估 CSP 对其控制措施描述的公平性。 该结论还会评估 CSP 控制措施是否设计得当、在指定日期是否正常运行，以及在指定时间段内是否有效运行。

审核员还可以创建 SOC 3 报告（SOC 2 Type 2 审核报告的简化版），该报告适用于想要保证 CSP 控制措施但又不需要完整的 SOC 2 报告的用户。 只有在 CSP 的 SOC 2 审核意见为不合格时，才能授予 SOC 3 报告。

## <a name="microsoft-and-soc-1-2-and-3-reports"></a>Microsoft 和 SOC 1、2 和 3 报告

独立的第三方审核员会根据 SOC 报告框架对 Microsoft 涵盖的云服务进行审核，至少每年一次。 Microsoft 云服务的审核涵盖有关数据安全性、可用性、处理完整性和机密性的控制措施（如果每个服务的范围内信任原则适用）。

Microsoft 已获得 SOC 1 Type 2、SOC 2 Type 2 和 SOC 3 报告。 通常，SOC 1 和 SOC 2 报告仅供与 Microsoft 签署了保密协议的客户使用；SOC 3 报告是公开提供的。

在 Microsoft 云上了解 SOC 1、2、3 的优势：[下载 SOC 1 和 SOC 2 Type 2 报告背景信息](https://aka.ms/soc_backgrounder)

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内的云服务

### <a name="covered-services-for-soc-1-and-soc-2"></a>SOC 1 和 SOC 2 覆盖的服务

- Azure、Azure 政府和 Azure 德国[详细列表](https://aka.ms/AzureCompliance)
- 云应用安全
- Dynamics 365 和 Dynamics 365 美国政府版[详细列表](https://aka.ms/d365-compliance-list)
- Graph
- Intune
- Microsoft Flow 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- Office 365、Office 365 美国政府版和 Office 365 美国政府国防版[详细列表](https://go.microsoft.com/fwlink/p/?LinkID=2077751)；Yammer 已完成 SOC 1 Type 1 报告
- Office 365 德国
- PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- Power BI 云服务，作为独立服务提供，或者随 Office 365 品牌计划或套件一并提供
- Stream
- Azure DevOps Services

### <a name="covered-services-for-soc-3"></a>SOC 3 涵盖的服务

- Azure、Azure 政府和 Azure 德国[详细列表](https://aka.ms/AzureCompliance)
- 云应用安全
- Graph
- Intune
- Microsoft Flow 云服务，作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- Power BI
- Stream

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

### <a name="audit-cycle"></a>审核周期

Microsoft 云服务会根据 SOC 1（SSAE18，ISAE 3402）和 SOC 2（AT 条例 101）标准每年至少进行一次审核。

#### <a name="azure-cloud-app-security-flow-graph-intune-power-bi-powerapps-stream-and-microsoft-datacenters"></a>Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、Stream 和 Microsoft 数据中心

- [Azure 和 Azure 政府的 SOC 1 Type 2 报告](https://go.microsoft.com/fwlink/p/?linkid=2099601)
- [Azure 和 Azure 政府的 SOC 2 Type 2 报告](https://aka.ms/azuresoc2auditreport)
- [Azure 和 Azure 政府的 SOC 3 报告](https://aka.ms/azuresoc3auditreport)

#### <a name="dynamics-365"></a>Dynamics 365

- [Dynamics 365 SOC 1 Type 2 报告](https://aka.ms/Dynamics365SOC1AuditReport)
- [Dynamics 365 SOC 2 AT 101 Type II 审核报告](https://aka.ms/Dynamics365SOC2AuditReport)
- [请参阅 Bridge Letter 和其他审核报告](https://aka.ms/auditreports)

#### <a name="office-365"></a>Office 365

- [Office 365 SOC 1 SSAE 16 Type II 审核报告](https://aka.ms/office365soc1auditreport)
- [Office 365 SOC 2 AT 101 Type II 审核报告](https://aka.ms/Office365SOC2AuditReport)
- [Office 365 客户密码箱 SOC 1 SSAE 16 审核报告](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [Yammer SOC 2 AT 101 Type II 审核报告](https://aka.ms/YammerSOC2AuditReport)
- [Yammer SOC 2 AT 101 Type I 审核报告](https://aka.ms/YammerSOC2Type1AuditReport)
- [请参阅 Bridge Letter 和其他审核报告](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a>常见问题解答

**如何获得 SOC 报告的副本？**

使用这些报告，您的审核员可以将 Microsoft 商务云服务结果与你自己的法律和法规要求相比较。

- 可通过[服务信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)查看所有 SOC 报告。
- 无法访问[服务信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)的 Azure DevOps 服务客户可以向 [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) 发送电子邮件来获取其 SOC 1 和 SOC 2 报告。 此电子邮件仅用于请求 Azure DevOps SOC 报告。

**Azure SOC 报告多久发布一次？**

Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、Stream 和 Microsoft 数据中心的 SOC 报告基于滚动的 12 个月运行时间窗（审计期），且每半年（周期结束日期是 3 月 31 日和 9 月 30 日）发布一次新报告。 Bridge Letter 将在 1 月（涵盖 10/1 – 12/31 这段时间）和 7 月（涵盖 4/1 – 6/30 这段时间）发布。 客户可从服务信任门户[下载](https://aka.ms/stp)最新报告。

**是否需要对 Microsoft 数据中心执行我自己的审核流程？**

否。 Microsoft 会与客户共享独立的审核报告与认证，以便客户能够检验 Microsoft 是否符合自己的安全承诺。

**能否在我自己组织的认证过程中使用 Microsoft 的合规性认证？**

是。 当您将应用程序和数据迁移到所覆盖的 Microsoft 云服务时，您可以把 Microsoft 所持有的审核与认证作为构建基础。 独立报告可证实 Microsoft 已实施用于维护您数据的安全性和隐私的控制措施的有效性。

**从何处着手开展我自己组织的合规工作？**

[面向服务组织的 SOC 工具套件](https://aka.ms/soc-toolkit)对了解 SOC 报告过程和推动组织利用这些报告是非常有用的资源。

## <a name="resources"></a>资源

 - [使用 Microsoft 云服务更好地保护你的数据](https://www.microsoft.com/trustcenter/guidance/protect-data)
 - [Service Organization Control (SOC) 报告](https://aka.ms/mssocreports)
 - [SSAE 16 审核标准](https://www.ssae-16.com/)
 - [ISAE 3402 标准](https://isae3402.com/)
 - [Microsoft 公共控制中心合规性框架](https://www.microsoft.com/trustcenter/common-controls-hub)
 - [Microsoft 联机服务条款](https://aka.ms/Online-Services-Terms)
 - [Microsoft 政府云](https://go.microsoft.com/fwlink/p/?linkid=2087246)
 - [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下载产品/服务背景信息

需要此产品/服务的背景信息文档？ 请下载 [PDF](https://download.microsoft.com/download/F/E/1/FE10DD69-B5A9-4DA7-A86A-1F565D2B6472/SOC_backgrounder-2018.pdf)。
