---
title: 交易所最低可接受风险标准 (MARS-E) 2.0 框架
description: Microsoft 遵守美国交易所最低可接受风险标准 (MARS-E)。
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
ms.openlocfilehash: 2d2c9862fe5af3eedd9ff90ff5bb6d33e1e06f10
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417516"
---
# <a name="minimum-acceptable-risk-standards-for-exchanges-mars-e-20-framework"></a>交易所最低可接受风险标准 (MARS-E) 2.0 框架

## <a name="mars-e-20-framework-overview"></a>MARS-E 2.0 框架概述

在 2012 年，美国医疗保险和医疗补助服务中心 (CMS) 根据 CMS 信息安全和隐私计划发布了交易所最低可接受风险标准 (MARS-E)。 这套文档（包括指南、要求和模板）旨在遵循《患者保护和大众医疗法》(ACA) 的强制要求以及适用于 ACA 的“卫生和公共服务部”的法规。 国家标准与技术研究院 (NIST) 特刊 800-53 作为父框架，为 ACA 授权的健康交易所和市场之间的所有系统、接口和连接制定安全性和合规性要求。

在 MARS-E 发布后，NIST 发布了一个更新（特刊 800-53r4），以应对日益严峻的在线安全（包括应用程序安全）的挑战、内部威胁和高级持久性威胁、供应链风险，以及移动和云计算系统的可靠性、保证性和弹性。 随后，CMS 修改了 MARS-E 框架，以与 NIST 800.53r4 中更新的控制措施和参数保持一致，并于 2015 年发布了 MARS-E 2.0。

这些更新涉及健康交易所中受保护数据的机密性、完整性和可用性，这些数据包括个人身份信息、受保护健康信息和联邦税收信息。 MARS-E 2.0 框架旨在保护此类受保护数据的安全，并适用于所有 ACA 管理实体，包括交易所或市场（联邦、州、州医疗补助或儿童健康保险计划 (CHIP) 机构），以及支持承包商。

## <a name="microsoft-and-mars-e-20-framework"></a>Microsoft 和 MARS-E 2.0 框架

目前，没有针对 MARS-E 的正式授权和认证过程。 但是，Microsoft Azure 平台服务已在中等影响级别进行了 FedRAMP 独立审核，在高影响级别进行了 Azure 政府审核，并且已根据 FedRAMP 标准进行了授权。 虽然这些标准并非专门针对 MARS-E，但 MARS-E 控制要求和目标相辅相成，可用于保护 Azure 上数据的机密性、完整性和可用性。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 与 Azure 政府](https://aka.ms/AzureCompliance)
- Intune

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

每年会针对 FedRAMP 授权流程对 Microsoft 商业云服务进行监视和评估。

## <a name="frequently-asked-questions"></a>常见问题解答

**此标准适用于哪些对象？**

MARS-E 适用于所有《大众医疗法》管理实体，包括交易所或市场（管理基本健康计划的联邦、州、医疗补助或 CHIP 机构），以及支持承包商和分包商。

**Microsoft 如何通过此标准证明 Azure 和 Azure 政府合规性？**

使用第三方针对 FedRAMP 授权准备的正式审核报告，Microsoft 能够说明这些报告中所述的相关控制措施如何展示 Azure 在满足 MARS-E 安全和隐私控制要求方面的能力。 Microsoft 实施的已审核控制措施旨在保护 Azure 平台上所存储数据的机密性、完整性和可用性，并且符合 MARS-E 中定义的已确定为 Microsoft 责任的适用法规要求。

**Microsoft 对确保符合这一标准负有哪些责任？**

Microsoft 确保 Azure 平台符合管理[在线服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)和适用的服务级别协议 (SLA) 中定义的条款。 这些条款规定了我们在实施和维护足以确保 Azure 平台安全并监视系统的控制措施方面的责任。

**能否在我所在组织的 MARS-E 认证工作中采用 Microsoft 的合规性认证？**

能。 符合 FedRAMP 标准的第三方审核报告可证实 Microsoft 已实施的、用于确保 Azure 平台安全性和隐私的控制措施的有效性。 Azure 和 Azure 政府客户可以在自己的 FedRAMP 和 MARS-E 风险分析和鉴定工作中采用这些相关报告中所述的已审核控制措施。

## <a name="resources"></a>资源

- MARS-E 规章指南, MARS-E 文档套件, 版本 2.0
    - [第 II 卷：交易所最低可接受风险标准](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/2-MARS-E-v2-0-Minimum-Acceptable-Risk-Standards-for-Exchanges-11102015.pdf)
    - [第 III 卷：交易所最低可接受风险安全性和隐私控制措施目录](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/3-MARS-E-v2-0-Catalog-of-Security-and-Privacy-Controls-11102015.pdf)
- [Microsoft 在线服务合规性框架白皮书](https://aka.ms/compliance-framework)
- [Microsoft 在线服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
