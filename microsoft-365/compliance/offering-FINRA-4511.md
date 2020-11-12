---
title: 金融行业法规颁发机构 (FINRA) 规则 4511 (c) 美国国家/地区
description: 独立评估事务所验证了 Azure 和 Office 365 可以帮助金融公司满足 FINRA Rule 4511 记录保留和不可变的存储要求。
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
ms.openlocfilehash: 2ba5dc4726f359545d59de7387fc62a3fe897588
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995885"
---
# <a name="financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>金融行业法规颁发机构 (FINRA) 规则 4511 (c) 美国国家/地区

## <a name="about-finra-rule-4511"></a>关于 FINRA 规则4511

[金融行业监管机构 (FINRA) ](https://www.finra.org/#/)是对美国的超过4500的经纪公司进行监督的最大独立团体。 由美国国会授权，通过确保经纪人行业的运营既公平又诚实，来保护美洲的投资者。

在2011中，美国证券和 Exchange 佣金 (SEC) 批准了在电子存储介质上管理书籍和记录的保留期的 FINRA 采用。 [FINRA Rule 4511 (c) ](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf) 指定 "所有必须按照 FINRA 规则进行的书籍和记录应保留为符合海运 (证券交易法案) Rule 17a-4" 的格式和媒体。

此外，FINRA Rule 4511 (c) 要求公司至少保留六年期，在适用的 FINRA 或海洋规则下没有指定保留期的图书和记录。 实际上，如果书籍和记录与某个帐户相关，则保留期规定在帐户关闭后六年。 否则，保留期为在此类书籍和记录创建后六年。

## <a name="microsoft-and-finra-rule-4511c"></a>Microsoft 和 FINRA Rule 4511 (c) 

金融服务客户（代表世界上最受管控的行业之一）受复杂的规定的制约，如财务事务和不可修改状态中的相关通信保留。 其中包括金融行业法规颁发机构的规则 4511 (FINRA) ，stipulates 选择在电子存储媒体上保留书籍和记录的受管制实体的严格要求。 在指定的保留期之前，存储的记录必须是防篡改的，不能更改或删除它们。

Microsoft Azure 永恒 Blob 存储 with with Policy Lock 和 Microsoft Office 365 with 保留锁定可帮助金融机构满足 FINRA Rule 4511 (c) 的不可变的存储要求。

## <a name="microsoft-azure"></a>Microsoft Azure

若要评估符合 FINRA 规则 4511 (c) 的 Azure 合规性，Microsoft 保留了一个独立的评估事务所，专门从事记录管理和信息治理、Cohasset 关联。 生成的报告、 [SEC 17a-4 (f) & CFTC 1.31 (c-d) 合规性评估： Microsoft Azure 存储](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)，包含 FINRA Rule 4511 (c) 中的 azure 合规性，这会遵从 SEC rule 17a-4 (f) 的格式和媒体要求。

Cohasset 使用策略锁定选项验证了 [Azure 不可变 Blob 存储](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) ，在将基于时间的 blob 保留在不可擦除和不可改写的 (WORM) 格式中时，满足相关的 FINRA 存储要求。 每个 Blob (记录) 在所需的保留期过期且已释放任何关联的合法保留期之前，将受到保护，不会被修改、覆盖或删除。

具有敏感工作负载的软件提供商和合作伙伴现在可以依赖 Azure 不可变 Blob 存储作为一种用于记录保留和不可变存储的一站式云解决方案。 金融机构现在可以构建自己的应用程序，利用这些功能，同时保持兼容性。

## <a name="microsoft-365"></a>Microsoft 365

对于 [FINRA 4511 (c) ](retention-regulatory-requirements.md#sec-17a-4f-finra-4511c-and-cftc-131c-d) 要求，Cohasset 验证 Microsoft 365 是否包括存档功能，这些功能可让受管制的客户（包括经纪人代理商）以帮助其符合 SEC 对记录保留的要求的方式存储数据。 Microsoft 365 中的保留功能帮助保留大量数据，包括电子邮件、语音邮件、共享文档、即时消息和第三方数据。 特别是，Microsoft 365 中的存档使客户能够设置全局或精确的邮件保留策略，以便将数据存储在定义的时间段内，而不是以不可改写、不可擦除的格式存储。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

### <a name="azure--finra-rule-4511c"></a>Azure & FINRA Rule 4511 (c) 

[SEC 17a-4 (f) & CFTC 1.31 (c-d) Azure 存储的合规性评估](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 & FINRA Rule 4511 (c) 

[Office 365 中的存档、数据保留和 SEC Rule 17a-4 合规性](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>如何实现

- **金融服务法规** ：符合云计算和 Microsoft online services 的关键美国规章原则的合规性地图。 [了解更多](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **风险评估和合规性指南** ：针对 Microsoft 云服务风险评估和监管机构通知创建一个管理模型。 [了解更多](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **金融用例** ：在案例概述、教程和其他资源的帮助下构建适合金融服务的 Azure 解决方案。 [了解更多](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>资源

- [Microsoft 金融服务合规性计划](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Microsoft 商业云服务和金融服务](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Azure 中的金融服务合规性](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure 金融服务云风险评估工具](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365 保留策略](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft 金融服务博客](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
