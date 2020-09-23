---
title: NIST SP 800-171
description: Microsoft 云服务遵循 NIST SP 800-171 准则来保护受控的未分类信息 (CUI) 在 nonfederal 信息系统中。
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
ms.openlocfilehash: 9874a68978e5755e8e86ff476ec96170878a10da
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208084"
---
# <a name="nist-sp-800-171"></a>NIST SP 800-171

## <a name="about-nist-sp-800-171"></a>关于 NIST SP 800-171

美国国家标准和技术协会 (NIST) 促进并维护度量标准和准则，以帮助保护联邦机构的信息和信息系统。 为了响应执行官订单13556管理受控制的未分类信息 (CUI) ，it 发布了 [NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)， *保护了 Nonfederal 信息系统和组织中的受控制的未分类信息*。 CUI 定义为由政府 (或代表其代表的实体创建的信息（数字和物理）) ，而不是保密的信息仍是敏感的，需要保护。

NIST SP 800-171 最初在6月2015发布，并在接下来更新几次，以响应演变的威胁。 它提供了有关如何在 nonfederal 信息系统和组织中安全地访问、传输和存储 CUI 的指南。其要求分为四个主要类别：

- 用于管理和保护的控件和流程
- IT 系统的监控和管理
- 最终用户的明确实践和过程
- 技术和物理安全措施的实施

## <a name="microsoft-and-nist-sp-800-171"></a>Microsoft 和 NIST SP 800-171

经资格鉴定的第三方评估组织、Kratos Secureinfo 和 Coalfire 与 Microsoft 合作，以证明其范围内的云服务符合 NIST SP 800-171 中的条件， *保护受控制的未分类信息 (CUI 在 Nonfederal 信息系统和组织中) 在*处理 CUI 时。 [Microsoft 实施 FedRAMP](offering-fedramp.md)要求有助于确保 microsoft 范围内的云服务使用已实施的系统和做法满足或超过 NIST SP 800-171 的要求。

NIST SP 800-171 要求是 NIST SP 800-53 （FedRAMP 使用的标准）的子集。 在 NIST SP 800-171 的附录 D 中，可将其 CUI 安全要求直接映射到 NIST SP 800-53 中的相关安全控件，该服务已在 FedRAMP 程序下评估并授权了此项范围内的云服务。

处理或存储美国政府 CUI 的任何实体（研究机构、咨询公司、制造承包商）必须符合 NIST SP 800-171 的严格要求。 此证明意味着 Microsoft 的范围内云服务可以适应希望部署 CUI 工作负荷的客户，并确保 Microsoft 处于完全遵从性。 例如，在其信息系统中使用范围内的 Microsoft 云服务处理、存储或传输 "覆盖的防御信息" 的所有 DoD 承包商都将满足美国国防部的 DFARS 条款要求符合 NIST SP 800-171 的安全要求。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 政府](https://aka.ms/AzureCompliance)
- [美国政府 Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 美国政府社区云 (GCC) 、Office 365 GCC High 和 DoD](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

- [与 NIST SP 800-171 兼容性的 Azure 政府合规性证明](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a>如何实现

- [Azure 蓝图示例](https://docs.microsoft.com/azure/governance/blueprints/samples/)：获取对实施符合 NIST 的控件的工作负荷的支持。

## <a name="frequently-asked-questions"></a>常见问题解答

**是否可以对我的组织使用 NIST SP 800-171 的 Microsoft 合规性？**

是。 Microsoft 客户可以使用来自独立第三方评估组织的报告中所述的审核的控件 (3PAO) 在 FedRAMP 标准中，作为其自己的 FedRAMP 和 NIST 风险分析和资格努力的一部分。 这些报告证明 Microsoft 已在其范围内的云服务中实现的控制措施的有效性。 客户负责确保其 CUI 工作负载符合 NIST SP 800-171 指南。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>使用 Microsoft 合规性管理器评估风险

[Microsoft 合规性管理器](compliance-manager.md) 是 [microsoft 365 合规性中心](microsoft-365-compliance-center.md) 中的一项功能，可帮助您了解组织的合规性状况并采取措施帮助降低风险。 合规性管理器提供了一个用于为此法规建立评估的高级模板。 在合规性管理器的 " **评估模板** " 页中查找模板。 了解如何 [在合规性管理器中构建评估](compliance-manager-assessments.md)。

## <a name="resources"></a>资源

- [Microsoft DoD 认证符合 NIST 800-171 要求](offering-DoD-DISA-L2-L4-L5.md)
- [NIST 800-171 合规性从 Cybersecurity 文档中开始](https://www.nist800171.com/)
- [Microsoft 云服务 FedRAMP 授权](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [NIST 800-171 3.3 审核和责任与 Office 365 GCC 高](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [Microsoft 和 NIST Cybersecurity 框架](offering-nist-csf.md)
- [Microsoft 政府云](https://www.microsoft.com/enterprise/government)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
