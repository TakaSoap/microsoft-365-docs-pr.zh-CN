---
title: 支付卡行业 (PCI) 数据安全标准 (DSS)
description: Azure、SharePoint Online 和 OneDrive for Business 符合支付卡行业数据安全标准 Level 1 3.2 版。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
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
ms.openlocfilehash: cb4d1a4c4632763506fd2d3b05431acb9233f744
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071960"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>支付卡行业 (PCI) 数据安全标准 (DSS)

## <a name="pci-dss-overview"></a>PCI DSS 概述

支付卡行业（PCI）数据安全标准（DSS）是一个全球性的信息安全标准，旨在通过加强对信用卡数据的控制来防止欺诈。任何规模的组织如果接受五大信用卡品牌（Visa、MasterCard、American Express、Discover和日本信用局（JCB））的支付卡，都必须遵守PCI DSS标准。任何存储、处理或传输支付和持卡人数据的组织都必须遵守PCI DSS标准。

## <a name="microsoft-and-pci-dss"></a>Microsoft 和 PCI DSS

Microsoft 使用经批准的合格安全评估师（QSA）完成了年度 PCI DSS 评估。审计人员审查了 Microsoft Azure、Microsoft OneDrive for Business 和 Microsoft SharePoint Online 环境，其中包括验证基础设施、开发、运营、管理、支持和范围内服务。PCI DSS 根据交易量指定了四个级别的合规性。认证 Azure、OneDrive for Business 和 SharePoint Online 为符合 PCI DSS 3.2 版的第一级服务提供商（交易量最高的级别 - 每年超过 600 万）。

评估的结果是向客户提供合规证明（AoC），并由质检局出具合规报告（RoC）。合规的有效期限从通过审计并收到评估员的合规证明开始，到合规证明签署之日起一年。 

希望开发持卡人环境或卡处理服务的客户可以在许多底层部分中使用这些验证，从而减少获取自己的 PCI DSS 认证的相关工作和成本。

重要的是要明白，Azure、OneDrive for Business 和 SharePoint Online 的 PCI DSS 合规性状态不会自动转化为客户在这些平台上构建或托管的服务的 PCI DSS 认证。客户有责任确保他们达到 PCI DSS 要求的合规性。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 与 Azure 政府](https://azure.microsoft.com/global-infrastructure/government/)
- Microsoft 云应用安全
- Flow 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- Microsoft Graph
- Intune
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- PowerApps 云服务，作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供
- Power BI 云服务，无论是独立服务还是随 Office 365 品牌计划或套件提供的服务
- OneDrive for Business 和 SharePoint Online（仅限美国）

## <a name="audit-reports-and-certificates"></a>审核、报告和证书

- [Azure PCI DSS 合规性证明 (AoC)](https://aka.ms/azure-pci)
- [OneDrive for Business 和 SharePoint Online PCI DSS 合规性证明 (AoC)](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>获取 Azure 上运行的 PCI DSS 解决方案

借助 Azure 安全性与合规性 PCI DSS 蓝图，在云中更快地构建和部署 PCI DSS 解决方案。获取参考架构、部署指导、控制实施映射、自动脚本等。[开始使用 Azure PCI DSS 蓝图](https://aka.ms/pciblueprint)。

## <a name="frequently-asked-questions"></a>常见问题解答

**为什么合规性证明 (AoC) 封面上写着“2018 年 6 月”？**

封面上 2018 年 6 月的日期是 AoC 模板发布的时间。关于评估日期，请参考第2节。

**为什么会有多个 Azure 合规性证明 (AoC)？**

Azure AoC 包有对应 Azure 公有云、德国云和政府云的 AoC。客户应使用与其 Azure 环境相对应的 AoC。  

**PA DSS 与 PCI DSS 之间有何关系？**

支付应用数据安全标准（PA DSS）是一套符合 PCI DSS 的要求，并取代了 Visa 的支付应用最佳实践，整合了其他主要发卡机构的合规要求。PA DSS 帮助软件供应商开发第三方应用程序，这些应用程序存储、处理或传输持卡人支付数据，作为卡授权或结算流程的一部分。零售商必须使用经过 PA DSS 认证的应用程序来有效地实现其 PCI DSS 的合规性。PA DSS 不适用于 Azure。

**什么是收单机构，Azure 是否使用收单机构？**

Acquirer 是处理支付卡交易的银行或其他实体。Azure 不提供支付卡处理服务，因此不使用 Acquirer。

**PCI DSS 适用于哪些组织和商家？**

PCI DSS 适用于任何接受、传输或存储持卡人数据的公司，无论其规模大小、交易数量多少。也就是说，如果有客户使用信用卡或借记卡向公司付款，则适用 PCI DSS 要求。根据 12 个月内的总交易量，公司将在四个级别中的一个进行验证。第 1 级适用于每年处理超过 600 万笔交易的公司；第 2 级适用于 100 万至 600 万笔交易；第 3 级适用于 2 万至 100 万笔交易；第 4 级适用于少于 2 万笔的交易。

**我的组织从何处着手开展针对部署在 Azure 上的解决方案的 PCI DSS 合规工作？**

PCI 安全标准委员会提供的信息是了解具体合规要求的好地方。该委员会为商家和参与支付卡处理的其他人员发布了[PCI DSS快速参考指南](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)。该指南解释了 PCI DSS 是如何帮助保护支付卡交易环境以及该如何应用它。

合规性涉及多个因素，包括评估未托管在 Azure 上的系统和流程。个别要求根据使用的 Azure 服务及其在解决方案中的应用方式有所不同。

**OneDrive for Business 和 SharePoint Online 是否有在美国境外实现 PCI DSS 合规性的计划？**

目前，OneDrive for Business 和 SharePoint 在线仅在美国（US）符合 PCI-DSS 标准。Microsoft 将评估美国以外地区的要求和时间表，并在其他地区加入路线图时提供更新。

**OneDrive for Business 和 SharePoint Online 的范围内是什么？**

目前，只有上载到 OneDrive for Business 和 SharePoint Online 的文件和文档符合 PCI DSS。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>使用 Microsoft 合规性管理器评估风险

[Microsoft 合规性管理器](compliance-manager.md)是 [Microsoft 365 合规中心](microsoft-365-compliance-center.md)的一项功能，可帮助你了解组织的合规态势，并采取行动以帮助降低风险。合规性管理器提供了一个高级模板，用于构建该法规的评估。在合规性管理器的 **评估模板** 页面中找到该模板。了解如何 [在合规管理器中构建评估](compliance-manager-assessments.md)。

## <a name="resources"></a>资源

- [支付卡行业数据安全标准委员会](https://www.pcisecuritystandards.org/)
- [PCI 数据安全标准](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 蓝图](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [PCI DSS 快速参考指南](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
