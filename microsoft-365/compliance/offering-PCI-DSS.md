---
title: 支付卡行业 (PCI) 数据安全标准 (DSS)
description: Azure、SharePoint Online 和 OneDrive for Business 符合支付卡行业数据安全标准 Level 1 3.2 版。
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
ms.openlocfilehash: 1b0e4ae933591f41c99a4b88d31eca6504322c92
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "39218691"
---
# <a name="compliance-offering-payment-card-industry-pci-data-security-standard-dss"></a>合规性产品：支付卡行业 (PCI) 数据安全标准 (DSS)

## <a name="pci-dss-overview"></a>PCI DSS 概述

支付卡行业 (PCI) 数据安全标准 (DSS) 是一种全球信息安全标准，旨在通过增强对信用卡数据的控制来预防欺诈。 如果各种规模的组织接受五大信用卡品牌（Visa、MasterCard、American Express、Discover 和 Japan Credit Bureau (JCB)）的支付卡，则他们必须遵循 PCI DSS 标准。 任何存储、处理和传输付款持卡人数据的组织都必须符合 PCI DSS。

## <a name="microsoft-and-pci-dss"></a>Microsoft 和 PCI DSS

Microsoft 由经认可的合格安全性评估师 (QSA) 完成 PCI DSS 年度评估。 审核员审查了 Microsoft Azure、Microsoft OneDrive for Business 和 Microsoft SharePoint Online 环境，其中包括验证基础结构、开发、操作、管理、支持和范围内服务。 PCI DSS 根据交易量指定了四个级别的合规性。 Azure、OneDrive for Business 和 SharePoint Online 被认证为符合 PCI DSS 3.2 版的 Service Provider Level 1（成交量最高，每年超过 600 万）。

通过该评估，我们获得了可向客户提供的合规性证明 (AoC) 和 QSA 颁发的合规性报告 (RoC)。 合规性的有效期开始于通过审核并收到评审员的 AoC，并于签署该 AoC 之日起一年后失效。 

希望开发持卡人环境或卡处理服务的客户可以在许多底层部分中使用这些验证，从而减少获取自己的 PCI DSS 认证的相关工作和成本。

需要注意的重要一点是，明白 Azure、OneDrive for Business 和 SharePoint Online 的 PCI DSS 合规性状态不会自动转化成客户在这些平台上构建或托管的服务的 PCI DSS 认证。 客户负责确保他们自己符合 PCI DSS 要求。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内的云服务

- [Azure 与 Azure 政府](https://aka.ms/AzureCompliance)
- 云应用安全
- Flow 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- Graph
- Intune
- PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- Power BI 云服务，无论是独立服务还是随 Office 365 品牌计划或套件提供的服务
- OneDrive for Business 和 SharePoint Online（仅限美国）

## <a name="audit-reports-and-certificates"></a>审核、报告和证书

- [Azure PCI DSS 合规性证明 (AoC)](https://aka.ms/azure-pci)
- [OneDrive for Business 和 SharePoint Online PCI DSS 合规性证明 (AoC)](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>获取 Azure 上运行的 PCI DSS 解决方案

借助 Azure 安全性和合规性 PCI DSS 蓝图，在云中更快地构建和部署 PCI DSS 解决方案。 获取参考体系结构、部署指南、控制实现映射、自动化脚本等。 [开始使用 Azure PCI DSS 蓝图](https://aka.ms/pciblueprint)

## <a name="frequently-asked-questions"></a>常见问题解答

**为什么合规性证明 (AoC) 封面上写着“2018 年 6 月”？**

封面上的 2018 年 6 月是 AoC 模板发布的日期。 有关评估的日期，请参阅第 2 部分。

**为什么会有多个 Azure 合规性证明 (AoC)？**

Azure AoC 包具有对应于 Azure 公共、德国和政府云的 AoC。 客户应使用与其 Azure 环境对应的 AoC。  

**PA DSS 与 PCI DSS 之间有何关系？**

支付应用程序数据安全标准 (PA DSS) 是一套符合 PCI DSS 的要求，它取代了 Visa 的支付应用程序最佳做法，并整合了其他主要发卡机构的合规性要求。 PA DSS 帮助软件供应商开发第三方应用程序，以在卡授权或结算过程中存储、处理或传输持卡人支付数据。 零售商必须使用经 PA DSS 认证的应用程序，以有效取得 PCI DSS 合规性。 PA DSS 不适用于 Azure。

**什么是收单机构，Azure 是否使用收单机构？**

收单机构是指处理支付卡事务的银行或其他实体。 Azure 不提供支付卡处理服务，因此不使用收单机构。

**PCI DSS 适用于哪些组织和商家？**

PCI DSS 适用于任何接受、传输或存储持卡人数据的公司，不论规模或交易量如何。 也就是说，如果任何客户使用信用卡或借记卡向公司进行了支付，则会应用 PCI DSS 要求。 根据过去 12 个月内总交易量，被确认为四个级别之一的公司。 Level 1 针对一年处理的交易量超过 600 万的公司；Level 2 针对 100 万到 600 万交易量；Level 3 针对 2 万到 100 万交易量；Level 4 针对低于 2 万交易量。

**我的组织从何处着手开展针对部署在 Azure 上的解决方案的 PCI DSS 合规工作？**

支付卡行业数据安全标准委员会提供的信息能够让您很好地了解具体的合规性要求。 该委员会针对商家及参与支付卡处理的人员发布了 [PCI DSS 快速参考指南](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)。 该指南解释了 PCI DSS 如何帮助保护支付卡交易环境以及如何应用该标准。

合规性涉及若干因素，包括评估未托管在 Azure 上的系统和流程。 根据所使用的 Azure 服务及它们在解决方案中用法，个别要求会有所变化。

**OneDrive for Business 和 SharePoint Online 是否有在美国境外实现 PCI DSS 合规性的计划？**

目前，OneDrive for Business 和 SharePoint Online 仅在美国符合 PCI-DSS 要求。 Microsoft 将评估美国以外地区的要求和时间表，并在将或如果有其他地区添加到路线图时提供更新。

**OneDrive for Business 和 SharePoint Online 的范围内是什么？**

目前，只有上载到 OneDrive for Business 和 SharePoint Online 的文件和文档符合 PCI DSS。

## <a name="resources"></a>资源

- [支付卡行业数据安全标准委员会](https://www.pcisecuritystandards.org/)
- [PCI 数据安全标准](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 责任矩阵](https://aka.ms/pciresponsibilitymatrix)
- [PCI DSS 快速参考指南](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下载产品/服务背景信息

需要此产品/服务的背景信息文档？ 请下载 [PDF](https://download.microsoft.com/download/3/7/7/377F1BBC-37D5-4677-AB4A-7C01D089CA67/PCI_DSS_Compliance_Backgrounder.pdf)。
