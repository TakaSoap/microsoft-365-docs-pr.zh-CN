---
title: 商品先期备货交易委员会 (CFTC) 规则 1.31 (c-d) 美国
description: 独立评估事务所验证了 Azure 和 Office 365 可以帮助金融公司满足 CFTC Rule 1.31 记录保留和不可变的存储要求。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: bff804e726a62563621b11932e590ffcb631835a
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920394"
---
# <a name="commodity-futures-trading-commission-cftc-rule-131c-d-united-states"></a>商品先期备货交易委员会 (CFTC) 规则 1.31 (c-d) 美国

## <a name="about-cftc-rule-13c-d"></a>关于 CFTC 规则 1.3 (c-d) 

[商品先期备货交易委员会](https://www.cftc.gov/) (CFTC) （一种独立美国联邦代理商）调节商品先期备货和选项市场，以及最近更换的市场。  
  
长期 CFTC 规则1.31 定义了由 SEC Rule 17a-4 (f) 建立的记录保留要求。 此外，它还指定必须保留五年的电子记录，并且原件在前两年内保持 "可随时访问"，并在整个保留期内供佣金或美国司法部门进行检查。  
  
在2017中， [CFTC 修订了其规则](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrfederalregister/documents/file/2017-11014a.pdf)，修改并新式化其保留项法规，以采用更少的规范性标准，从而在维护记录的方式上提供了更大的灵活性。 这使得规则更具特定技术，从而使受管制实体能够选择最适合其业务的技术，同时维护确保保留过程的可靠性的安全措施。 修订后的规则消除了组织在两年中维护原始记录的要求，但保留了五年期维护期，这是由 CFTC 和 SEC 管控的公司的 harmonizes 做法。

## <a name="microsoft-and-cftc-rule-131c-d"></a>Microsoft 和 CFTC Rule 1.31 (c-d) 

金融服务客户（代表世界上最受管控的行业之一）受复杂的规定的制约，如财务事务和不可修改状态中的相关通信保留。 在最具说明性的是美国商品先期交易委员会 (CFTC) 的规则1.31，它 stipulates 在电子存储介质上保留书籍和记录的受管制实体的严格要求。 在指定的保留期之前，存储的记录必须是防篡改的，不能更改或删除它们。 Microsoft Azure 不可变 Blob 存储 with with Policy Lock 和 Microsoft Office 365 with 保留锁定可帮助金融机构满足 CFTC Rule 1.31 (c-d) 的存储要求。

### <a name="microsoft-azure"></a>Microsoft Azure

若要评估符合 CFTC Rule 1.31 (c-d) 的 Azure 合规性，Microsoft 保留了专门从事记录管理和信息治理、Cohasset 关联的独立评估事务所。 在生成的报告中， [CFTC 1.31 (c) – (d) 合规性评估： Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)，Cohasset 使用策略锁定选项验证了 [Azure 不可变 blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) 。当用于保留不可擦除和不可改写 (蠕虫) 格式的基于时间的 blob 时，将满足 CFTC 规则的基于原则的要求。 每个 Blob (记录) 在所需的保留期过期且已释放任何关联的合法保留期之前，将受到保护，不会被修改、覆盖或删除。 具有敏感工作负载的软件提供商和合作伙伴现在可以依赖 Azure 不可变 Blob 存储作为一站式车间解决方案，以实现记录保留。 金融机构现在可以构建自己的应用程序，利用这些功能，同时保持兼容性。

### <a name="microsoft-office-365"></a>Microsoft Office 365

若要评估 Office 365 合规性与 CFTC Rule 1.31 (c-d) ，Microsoft 接洽了专门从事法规问题、Covington & Burling、LLP 的主要独立法律事务所。 在生成的报告中， [Microsoft Office 365 中的存档、数据保留和规则17A-4 合规性](https://go.microsoft.com/fwlink/?linkid=830440)中，Covington 验证了 [Office 365 的保留锁定](retention-preservation-lock.md) 功能是否包括存档功能，这些功能使受管制的客户能够以一种有助于满足 CFTC 的记录保留要求的方式存储数据。

Office 365 中的存档有助于保留广泛的数据，包括电子邮件、语音邮件、共享文档、即时消息和第三方数据。 特别是，Office 365 中的存档使客户能够设置全局或精确的邮件保留策略，以便将数据存储在定义的时间段内，而不是以不可改写、不可擦除的格式存储。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure](https://aka.ms/AzureCompliance)
- [Office 365](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

[Azure & CFTC Rule 1.31-SEC 17a-4 (f) & CFTC 1.31 (c-d) Azure 存储的合规性评估

[Office 365 & CFTC Rule 1.31 — Office 365 中的存档、数据保留和 SEC Rule 17a-4 合规性

## <a name="how-to-implement"></a>如何实现

- [金融服务法规](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)：符合云计算和 Microsoft online services 的关键美国规章原则的合规性地图。
- [风险评估和合规性指南](https://aka.ms/RiskGovernanceGuide)：针对 Microsoft 云服务风险评估和监管机构通知创建一个管理模型。
- [金融用例](https://docs.microsoft.com/azure/industry/financial/)：在案例概述、教程和其他资源的帮助下构建适合金融服务的 Azure 解决方案。

## <a name="resources"></a>资源

- [Microsoft 金融服务合规性计划](https://aka.ms/FSCP-Print)
- [Microsoft 商业云服务和金融服务](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Azure 中的金融服务合规性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融服务云风险评估工具](https://aka.ms/FFIEC-CSDT)
- [Microsoft Office 365 保留策略](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融服务博客](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
