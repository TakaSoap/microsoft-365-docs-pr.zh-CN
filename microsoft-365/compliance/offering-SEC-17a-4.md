---
title: 证券和交换委员会（SEC）规则17a-4 （f）美国
description: 独立评估事务所验证了 Azure 和 Office 365 可以帮助金融公司满足 SEC Rule 17a-4 （f）记录保留和不可变存储要求。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 63a7c4f7385ec3d782ff030374ba344406c6d094
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126661"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>证券和交换委员会（SEC）规则17a-4 （f）美国

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 和 SEC Rule 17a-4 （f）

[美国证券和外汇委员会（SEC）](https://www.sec.gov/)是美国联邦政府的独立机构以及美国证券市场的主要 overseer 和调压器。 它 wields 强制实施政府证券法，提出新的证券规则，并监督证券业的市场法规。

SEC 为那些选择在电子存储媒体上保留书籍和记录的管控实体定义严格的和显式的要求。 它建立了[17 CFR 240.17 a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3)和[17 cfr 240.17 a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64) ，用于控制证券经纪人的保留期（包括保留期）。 后来，SEC[修正](https://www.sec.gov/rules/interp/34-47806.htm)了 17 CFR 240.17 a-4 段落（f），发布了两个 interpretive 发布，以允许在满足特定条件时，在电子存储介质上保留书籍和记录。

如果电子存储系统阻止对所需保留期的记录进行更改或擦除，则该系统将满足这些条件。 保留期将根据记录类型在三到六年之间变化，在前两年中，可以立即提供可访问性强制。 此外，interpretive 版本之一要求存储系统能够保留超过 SEC 建立的保留期的记录，以遵守 subpoenas、法律封存或其他此类要求。

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft 和 SEC Rule 17a-4 （f）

金融服务客户（代表世界上最受管控的行业之一）受复杂的规定的制约，如财务事务和不可修改状态中的相关通信保留。 在最具说明性的是，美国安全和 Exchange 委员会（SEC）的规则 17a-4-4 （f），stipulates 对可选择在电子存储媒体上保留书籍和记录的管控实体的严格要求。 在指定的保留期之前，存储的记录必须是防篡改的，不能更改或删除它们。

Microsoft Azure 不可变 Blob 存储 with with Policy Lock 和 Microsoft Office 365 with 保留锁定可帮助金融机构满足 SEC Rule 17a-4 （f）的不可变的存储要求。

为了评估 Azure 和 Office 365 符合 SEC Rule 17a-4 （f），Microsoft 保留了一个独立的评估事务所，专门从事记录管理和信息治理，Cohasset 相关。 在生成的报告中：

- **Azure**： [SEC 17a-4 （f）合规性评估： Microsoft azure 存储](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)，Cohasset 使用策略锁定选项验证了[Azure 不可变 blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage)，用于保留不可擦除和不可改写（WORM）格式的基于时间的 blob，满足 SEC 规则的不可变存储要求。 每个 Blob （记录）都受到保护，无法进行修改、覆盖或删除，除非所需的保留期已过期，并且已释放所有关联的合法保留期。 具有敏感工作负载的软件提供商和合作伙伴现在可以依赖 Azure 不可变 Blob 存储作为 onestop 云解决方案，以实现记录保留和不可变存储。 金融机构现在可以构建自己的应用程序，利用这些功能，同时保持兼容性。
- **Office 365**：[使用 EXCHANGE Online 符合 SEC 17a-4](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4)，Cohasset 验证了[具有保留锁定的 Office 365](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)包括存档功能，这些功能可让受管制的客户（包括经纪人代理商）以帮助其符合 SEC 对记录保留的要求的方式存储数据。 Office 365 中的保留策略帮助保留一系列数据，包括电子邮件、语音邮件、共享文档、即时消息和第三方数据。 特别是，Office 365 中的存档使客户能够设置全局或精确的邮件保留策略，以将数据存储在定义的时间段内，并在不可重写的 nonerasable 格式的后面。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

### <a name="azure--sec-rule-17"></a>Azure & SEC 规则17

[SEC 17a-4 （f） & CFTC 1.31 （c-d） Azure 存储的合规性评估](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 & SEC 规则17

[SEC 17a-4 （f）合规性评估： Microsoft Security & 合规性中心与 Exchange Online](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>如何实现

### <a name="financial-services-regulation"></a>金融服务法规

云计算和 Microsoft online services 的关键美国法规原则的合规性地图。 [了解更多](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>风险评估 & 合规性指南

创建用于对 Microsoft 云服务进行风险评估和调节器通知的管理模型。 [了解更多](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>财务用例

使用事例概述、教程和其他资源构建用于金融服务的 Azure 解决方案。 [了解更多](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>资源

- [Microsoft Office 365 中的存档、数据保留和规则 17a-4-4](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [合规性 Microsoft 金融服务](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [合规性计划 Microsoft 商业云服务和金融服务](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure 中的金融服务合规性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融服务云风险评估工具](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 保留策略](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融服务博客](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
