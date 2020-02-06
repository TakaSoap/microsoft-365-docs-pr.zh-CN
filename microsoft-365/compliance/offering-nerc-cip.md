---
title: 北美电力可靠性协会 (NERC)
description: Azure 和 Azure 政府适用于根据 NERC CIP 标准在云端部署特定工作负载的注册实体。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
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
ms.openlocfilehash: 635918f068a70eb8270f4d8e2f571f1fda962949
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601919"
---
# <a name="north-american-electric-reliability-corporation-nerc"></a>北美电力可靠性协会 (NERC)

## <a name="about-the-nerc"></a>关于 NERC

[北美电力可靠性协会](https://www.nerc.com/) (NERC) 是一家非营利性法规机构，其任务是确保北美大型电力系统的可靠性。 NERC 受到美国联邦能源管理委员会 (FERC) 和加拿大政府机构的监管。 2006 年，FERC 根据 2005 年美国能源政策法案（美国公共法 109-58）向 NERC 授予了电力可靠性组织 (ERO) 的称号。 NERC 制定和实施了被称作 NERC [关键基础设施保护 (CIP) 标准](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)的可靠性标准。

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft 与 NERC CIP 标准

北美电力可靠性协会 (NERC) 是一家非营利性法规机构，其任务是确保北美大型电力系统的可靠性。 NERC 受到美国联邦能源管理委员会 (FERC) 和加拿大政府机构的监管。 2006 年，FERC 根据 2005 年美国能源政策法案（美国公共法 109-58）向 NERC 授予了电力可靠性组织 (ERO) 的称号。 NERC 制定和实施了被称作 NERC [关键基础设施保护 (CIP) 标准](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)的可靠性标准。

所有大型电力系统所有者、运营者和用户都必须[遵守 NERC CIP 标准](https://www.nerc.com/pa/comp/Pages/default.aspx)。 这些实体必须向 NERC 登记。 云服务提供商和第三方供应商不受 NERC CIP 标准制约；但是，CIP 标准载明了当[注册实体](https://www.nerc.com/pa/comp/Pages/Registration.aspx)在大型电子系统 (BES) 的运营中采用供应商时应考虑的目标。 运营大型电力系统的 Microsoft 客户需全权负责确保自己遵循 NERC CIP 标准。 Microsoft Azure 和 Microsoft Azure 政府服务均不构成 BES 或 BES 网络资产。

正如 NERC 在当前这组 [CIP 标准](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf)及 NERC [术语表](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)中所述，BES 网络资产对 BES 进行实时监视或控制，并在 BES 遭到损害后 15 分钟内干涉其可靠运营。 要在云计算中适当纳入 BES 网络资产和受保护的网络资产，[需要修修订](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx) NERC CIP 标准中的现有定义。 但是，有很多工作负载要处理 CIP 敏感数据但却又不受 15 分钟规则限制，这包括 BES 网络系统信息 (BCSI) 的广义范畴。

Azure 和 Azure 政府适用于根据 NERC CIP 标准部署特定工作负载（包括 BCSI 工作负载）的注册实体。 Microsoft 提供了下列文档，供有兴趣在 Azure 或 Azure 政府中根据 NERC CIP 遵循义务部署数据和工作负载的注册实体查看：

- [NERC CIP Standards and Cloud Computing](https://aka.ms/AzureNERC)（NERC CIP 标准和云计算）是一份白皮书，其中探讨了根据适合云服务提供商的既定第三方审计得出的 NERC CIP 要求合规性注意事项，例如 FedRAMP。 它介绍了云操作人员的背景筛查，并解答了注册实体感兴趣的关于逻辑隔离和多租户等的常见问题。 此外，它还阐释了本地部署和云部署的安全注意事项。
- [Cloud Implementation Guide for NERC Audits](https://aka.ms/AzureNERCGuide)（关于 NERC 审计的云实施指南）是一份指导性文档，它在控制层面上将当前这组 NERC CIP 标准要求与构成 FedRAMP 基础的 [NIST SP 800-53 Rev 4](https://nvd.nist.gov/800-53/Rev4) 控制措施相互对应起来。 它被设计成技术操作指南，目的是帮助注册实体应对 NERC CIP 就云端部署的资产所作出的合规性要求。 该文档包含已预填内容的[可靠性标准审计工作表 (RSAW)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx) 文件，它们帮助阐释 Azure 控制措施如何应对 NERC CIP 要求，此外还有指南来引导注册实体如何使用 Azure 服务实施其自己的控制措施。

NERC ERO Enterprise [颁发了](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)合规性监控和实施计划 (CMEP) [实践指南](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)对 ERO Enterprise CMEP 人员在评估注册实体的流程以授予访问指定 BCSI 存储位置的权限以及评估注册实体实施的任何访问控制措施时的操作提供指导方针。 此外，NERC 还审查了与 BCSI 适用的 NERC CIP-004-6 和 CIP-011-2 标准相关的 Azure 控制措施实施详情和 FedRAMP 审计证据。 基于 ERO 为确保注册实体加密其数据而颁发的实践指南和审查的 FedRAMP 控制措施，注册实体无需其他任何指导方针或解释性文件即可在云端部署 BCSI 及相关工作负载。 但是，注册实体需根据自身实际情况和情形最终负责遵守 NERC CIP 标准。 注册实体应查看 [Cloud Implementation Guide for NERC Audits](https://aka.ms/AzureNERCGuide)（关于 NERC 审计的云实施指南），了解如何记录自己用来授予对 BCSI 存储位置的电子版访问权限的流程和证据，包括用于在 Azure 和 Azure 政府中进行 BCSI 加密的加密密钥管理。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内的云服务

- [Azure 与 Azure 政府](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

Microsoft 每年都必须重新证明其云服务，以维持其 P-ATO 和 ATO 认证。 为此，Microsoft 必须持续监视和评估其安全控制措施，并证明其持续合规。

- [Microsoft 云服务授权](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [Microsoft FedRAMP 审计报告](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>如何实现

### <a name="nerc-cip-standards-and-cloud-computing"></a>NERC CIP 标准和云计算

对于考虑根据 NERC CIP 标准在云端处理工作负载的注册实体，解决其合规性问题。

[了解详细信息](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>关于 NERC 审计的云实施指南

技术性指南，对需要就 Azure 或 Azure 政府中部的资产进行 NERC 审计的注册实体提供帮助。 

[了解详细信息](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>常见问题解答

**谁负责遵守 NERC CIP 标准?**

所有大型电力系统所有者、运营者和用户都必须[遵守 NERC CIP 标准](https://www.nerc.com/pa/comp/Pages/default.aspx)。 这些实体必须向 NERC 登记。 云服务提供商和第三方供应商不受 NERC CIP 标准制约；但是，CIP 标准载明了当[注册实体](https://www.nerc.com/pa/comp/Pages/Registration.aspx)在大型电子系统 (BES) 的运营中采用供应商时应考虑的目标。 运营大型电力系统的 Microsoft 客户需全权负责确保自己遵循 NERC CIP 标准。 Azur 和 Microsoft Azure 政府服务均不构成 BES 或 BES 网络资产。

为根据 NERC CIP 标准评估 Azure 和 Azure 政府是否适用于数据和工作负载，注册实体应咨询自己的合规官员和 NERC 审计师。 他们应查看 [Cloud Implementation Guide for NERC Audits](https://aka.ms/AzureNERCGuide)（关于 NERC 审计的云实施指南），了解如何就云端部署的资产记录自己的流程和证据。

**注册实体可在 Azure 和 Azure 政府上部署哪些工作负载？**

NERC [CIP 标准](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf)和[术语表](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)规定，BES 网络资产需实时监视或控制 BES，并在遭到损害后的 15 分钟内干涉 BES 的可靠运营。 要在云计算中适当纳入 BES 网络资产和受保护的网络资产，[需要修修订](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx) NERC CIP 标准中的现有定义。 但是，有很多工作负载要处理 CIP 敏感数据但却又不受 15 分钟规则限制，这包括 BES 网络系统信息 (BCSI) 的广义范畴。

NERC ERO Enterprise [颁发了](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)合规性监控和实施计划 (CMEP) [实践指南](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf)对 ERO Enterprise CMEP 人员在评估注册实体的流程以授予访问指定 BCSI 存储位置的权限以及评估注册实体实施的任何访问控制措施时的操作提供指导方针。 此外，NERC 还审查了与 BCSI 适用的 NERC CIP-004-6 和 CIP-011-2 标准相关的 Azure 控制措施实施详情和 FedRAMP 审计证据。 基于 ERO 为确保注册实体加密其数据而颁发的实践指南和审查的 FedRAMP 控制措施，注册实体无需其他任何指导方针或解释性文件即可在云端部署 BCSI 及相关工作负载。 但是，注册实体需根据自身实际情况和情形最终负责遵守 NERC CIP 标准。

## <a name="resources"></a>资源

- [NERC 合规性指南](https://www.nerc.com/pa/comp/guidance/)
- [NERC 合规性和实施](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [NERC 组织和认证](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft 与 FedRAMP](offering-fedramp.md)
- Microsoft 与 CSA STAR [证明](offering-csa-star-attestation.md)和[认证](offering-csa-star-certification.md)
- [Microsoft 和 SOC 2 报告](offering-soc.md)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
