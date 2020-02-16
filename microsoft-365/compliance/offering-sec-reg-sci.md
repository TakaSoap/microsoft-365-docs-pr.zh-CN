---
title: 有价证券和 Exchange 佣金-法规系统合规性和完整性（SCI）
description: SCI 规则适用于 SCI 实体，其中包括此类自助式组织（SROs）作为股票和选项交换、注册的结算机构和替代贸易系统（ATSs）。
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
ms.openlocfilehash: 4ad74c8d4ec71587f88a80c3ee109500e230be35
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071219"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a>有价证券和 Exchange 佣金：法规系统合规性和完整性（SCI）

## <a name="about-regulation-sci"></a>关于法规 SCI

美国证券和外汇委员会（SEC）是美国联邦政府的独立机构以及美国证券市场的主要 overseer 和调压器。 它 wields 强制实施政府证券法，提出新的证券规则，并监督证券业的市场法规。

2014年11月，SEC 采纳了[法规系统合规性和完整性（SCI）](https://www.sec.gov/rules/final/2014/34-73639.pdf) （并形成 SCI 的 SCI 事件），以加强美国证券市场中的技术基础结构。 该管理法规旨在降低系统中断的频率，在发生此类事件时提高恢复能力，并增加证券市场技术的 SEC 监督并强制实施其管理法规。

SCI 规则适用于 SCI 实体，其中包括此类自助式组织（SROs）作为股票和选项交换、注册的结算机构和替代贸易系统（ATSs）。 这些规则主要规定直接支持关键证券市场职能的系统：贸易、净空和结算、订单布线、市场数据、市场法规和市场监控。

## <a name="microsoft-and-sec-regulation-sci"></a>Microsoft 和 SEC 法规 SCI

美国证券和交换委员会（SEC）采用规章 SCI，以加强运营和支持美国证券市场的金融组织的技术基础结构。 根据 SEC 监督，其要求旨在确保这些系统具有高可用性、强弹性和低延迟（较小的邮件量较小的延迟）。

为了帮助指导我们必须遵守此法规的金融服务客户，Microsoft 已发布[Microsoft AZURE SEC 规章系统合规性和完整性云实施指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)。 本文档中的指导：

- 概述了支持强恢复、高可用性和低延迟的总体 Azure 功能。
- 明确哪些控制领域和法规方面的 Azure 地址。 Azure 功能和服务到 SCI 要求的点对点映射可衡量法规框架对 Azure 的遵从性。 它还可帮助客户了解在哪里可以将安全责任转移到在本地运营本地时它们完全拥有的。 这些功能由 Microsoft 在 Azure Sla 中做出的承诺作为后盾。
- 指定要解决的每个规章 SCI 要求，并提供 Azure 文档和服务，以帮助他们解决这些责任。

本文档提供了关键法规 SCI 焦点领域的完整清单。 此检查表可帮助金融组织了解如何采用 Azure 来帮助确保其机构、客户和领导能够遵守适用的法规要求。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内的云服务

- [Azure](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a>如何实现

- [规章 SCI 实施指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)：将 Azure 功能与法规对应起来，并详细说明合规性的共享责任。
- [设计可靠的 Azure 应用程序](https://docs.microsoft.com/azure/architecture/resiliency/)：有关如何在 Azure 应用程序设计的每个步骤中构建可靠性的简要概述。
- [设计高度可用的应用程序](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs)：开发人员如何帮助确保其 Azure 存储应用程序具有高可用性。
- [风险评估和合规性指南](https://aka.ms/RiskGovernanceGuide)：针对 Microsoft 云服务风险评估和监管机构通知创建一个管理模型。

## <a name="frequently-asked-questions"></a>常见问题解答

**使用云技术时，共享责任意味着什么？**

由于计算环境从本地数据中心迁移到云中的数据中心，因此安全责任也会随之转移—云服务提供商（CSP）和客户现在可以共享这一责任。 对于每个应用程序和解决方案，此责任中的多少取决于客户以及 CSP 上的多少取决于客户部署的 Azure 模型-IaaS、SaaS 或 PaaS。 客户的责任是了解他们对实施所需的安全控制所负责的程度。 但是，Microsoft 提供的指导可帮助客户导航此复杂的动态动态。 有关详细信息，请参阅[云计算的共享职责](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91)。

**哪些金融机构可以利用 Azure 来帮助满足法规 SCI 要求？**

受此法规制约的金融组织或 SCI 实体可以部署 Azure。 SEC 声称其法规适用于自助组织（SROs），其中包括股票和选项交换、注册的清算代理商、FINRA 和 MSRB、备选贸易系统（ATSs）（超出指定的贸易 NMS 和非 NMS 股票）批量阈值、disseminators 的合并市场数据（计划处理器）和某些免税清算机构。

## <a name="resources"></a>资源

- [SEC 对有关法规 SCI 的常见问题的响应](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [业务连续性和灾难恢复（BCDR）： Azure 配对区域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [云计算法规原则和 Microsoft Online Services 的合规性地图](https://aka.ms/FinServ-Guide-US)
- [Microsoft 云金融服务合规性计划](https://aka.ms/FSCP-Print)
- [Azure 中的金融服务合规性](https://aka.ms/FinServ-Compliance-Azure)
- [Microsoft 金融服务](https://aka.ms/FinServ-Compliance)
- [Microsoft 和 SEC Rule 17a-4](offering-SEC-17a-4.md)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下载产品/服务背景信息

需要此产品/服务的背景信息文档？ 请下载 [PDF](https://download.microsoft.com/download/8/1/a/81aa04eb-3c1f-4c1a-ba7d-9d30032acc52/SEC_Reg_SCI-Compliance.pdf)。
