---
title: NIST SP 800 –171
description: Microsoft 云服务遵循 NIST SP 800 –171准则，以保护 nonfederal 信息系统中的受控制的未分类信息（CUI）。
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
ms.openlocfilehash: e90d5e47c6aa5ac6c2813f150e8136b93214fa3d
ms.sourcegitcommit: b6ab845d64e2801051d249de09ad5059809b649a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42221994"
---
# <a name="nist-sp-800171"></a>NIST SP 800 –171

## <a name="about-nist-sp-800171"></a>关于 NIST SP 800 –171

美国国家标准和技术协会（NIST）促进并维护度量标准和准则，以帮助保护联邦机构的信息和信息系统。 为了响应管理层的未分类信息（CUI）的管理订单13556，它发布了[NIST SP 800 – 171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)，*保护了 Nonfederal 信息系统和组织中的受控制的未分类信息*。 CUI 定义为政府（或代表其代表的实体）创建的信息（无论是数字还是物理），而不是保密的信息仍是敏感的，需要保护。

NIST SP 800 –171最初是在2015年6月发布的，并且自那时起已更新多次，以响应演变的威胁。 它提供了有关如何在 nonfederal 信息系统和组织中安全地访问、传输和存储 CUI 的指南。其要求分为四个主要类别：

- 用于管理和保护的控件和流程
- IT 系统的监控和管理
- 最终用户的明确实践和过程
- 技术和物理安全措施的实施

## <a name="microsoft-and-nist-sp-800171"></a>Microsoft 和 NIST SP 800 –171

经资格鉴定的第三方评估组织，Kratos Secureinfo 和 Coalfire，与 Microsoft 合作以证明其范围内的云服务符合 NIST SP 800 –171中的条件，在*Nonfederal 信息系统和组织中保护受控制的未分类信息（CUI）*，在它们处理 CUI 时。 [Microsoft FedRAMP](offering-fedramp.md)要求的实现有助于确保 microsoft 范围内的云服务符合或超过 NIST SP 800 –171的要求，而这些系统和实践已准备就绪。

NIST SP 800 –171要求是 NIST SP 800-53 的子集，FedRAMP 使用的标准。 在 NIST SP 800 –171的附录 D 中，可将其 CUI 安全要求直接映射到 NIST SP 800-53 中的相关安全控件，该服务已在 FedRAMP 程序下评估并授权了此项范围内的云服务。

处理或存储美国政府 CUI 的任何实体（研究机构、咨询公司、制造承包商）必须遵守 NIST SP 800 –171的严格要求。 此证明意味着 Microsoft 的范围内云服务可以适应希望部署 CUI 工作负荷的客户，并确保 Microsoft 处于完全遵从性。 例如，在其信息系统中使用范围内的 Microsoft 云服务处理、存储或传输 "覆盖的防御信息" 的所有 DoD 承包商都能满足要求遵守安全性的美国国防部 DFARS 条款。NIST SP 800 –171的要求。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 政府](https://aka.ms/AzureCompliance)
- [美国政府 Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 美国政府社区云（GCC）、Office 365 GCC High 和 DoD](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

- [具有 NIST SP 800 –171的 Azure 政府合规性证明](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a>如何实现

- [NIST sp 800 –171蓝图](https://aka.ms/NIST-800-171-Blueprint)：获取在 Azure 中实现符合 NIST SP 800 –171的工作负载支持。

## <a name="frequently-asked-questions"></a>常见问题解答

**对于我的组织，我可以使用 Microsoft 合规性的 NIST SP 800 –171吗？**

是。 Microsoft 客户可以使用来自 FedRAMP 标准的独立第三方评估组织（3PAO）的报告中所述的审核控件，作为其自己的 FedRAMP 和 NIST 风险分析和资格验证工作的一部分。 这些报告证明 Microsoft 已在其范围内的云服务中实现的控制措施的有效性。 客户负责确保其 CUI 工作负载符合 NIST SP 800 –171准则。

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>使用 Microsoft 合规性分数评估风险

[Microsoft 合规性分数](compliance-score.md)是 [Microsoft 365 合规中心](microsoft-365-compliance-center.md)中的一项预览功能，旨在帮助你了解组织的合规情况并采取措施帮助降低风险。 [设置合规性分数](compliance-score-setup.md)后，从 "**模板**" 下拉菜单中选择预配置的[NIST 800-171 模板](https://go.microsoft.com/fwlink/?linkid=2117526)，以帮助您的组织满足此法规的要求。

## <a name="resources"></a>资源

- [Microsoft DoD 认证符合 NIST 800 –171要求](offering-DoD-DISA-L2-L4-L5.md)
- [NIST 800 –171合规性从 Cybersecurity 文档开始](https://www.nist800171.com/)
- [Microsoft 云服务 FedRAMP 授权](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [NIST 800-171 3.3 审核和责任与 Office 365 GCC 高](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [Microsoft 和 NIST Cybersecurity 框架](offering-nist-csf.md)
- [Microsoft 政府云](https://www.microsoft.com/enterprise/government)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下载产品/服务背景信息

需要此产品/服务的背景信息文档？ 请下载 [PDF](https://download.microsoft.com/download/9/8/F/98F1D966-FB62-4B58-B6F0-8F3DCCAC484A/NIST_SP-800-171-Compliance.pdf )。
