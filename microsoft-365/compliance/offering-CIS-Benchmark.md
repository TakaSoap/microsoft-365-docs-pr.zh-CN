---
title: Internet 安全中心 (CIS) 基准
description: Internet 安全中心 (CIS) 发布了一系列适用于 Microsoft 产品和服务的基准
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
ms.openlocfilehash: 264f592357c9030865d3acd6dc138878bedf41bf
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "39860052"
---
# <a name="center-for-internet-security-cis-benchmarks"></a>Internet 安全中心 (CIS) 基准

## <a name="about-cis-benchmarks"></a>关于 CIS 基准

[Internet 安全中心](https://www.cisecurity.org/)是一个非盈利性实体，其任务是“确定、开发、验证、升级和维持针对网络防御的最佳做法解决方案。” 它借鉴了来自世界各地政府、企业和学术界网络安全及 IT 专业人员的专业知识。 为了制定标准和最佳做法（包括 CIS 基准、控制措施和强化映像），他们遵循一致的决策制定模型。  
  
[CIS 基准](https://www.cisecurity.org/cis-benchmarks/)是安全配置系统的配置基线和最佳做法。 每则指导建议都参考了一个或多个 [CIS 控制措施](https://www.cisecurity.org/controls/)，可帮助组织改进其网络防御能力。 CIS 控制措施与许多已建立的标准和规章框架对应，包括 NIST 网络安全框架 (CSF) 和 NIST SP 800-53、ISO 27000 系列标准、PCI DSS、HIPAA 等等。  
  
每个基准都经历了两个阶段的共识评审。 第一个阶段属于初始开发过程，专家聚集在一起，讨论、创建和测试工作草案，直到就基准达成一致。 在第二阶段中，在发布基准后，共识团队将审核 Internet 社区中的反馈，以纳入基准中。  
  
CIS 基准提供两个级别的安全设置：

- “级别 1”推荐可在任何系统上配置的基本安全要求，这些要求应很少或不会导致服务中断或功能降低****。
- “级别 2”推荐需要更高安全性的环境安全设置，这些设置可能会导致功能降低****。

[CIS 强化映像](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/)是安全配置的虚拟机映像，基于强化到级别 1 或级别 2 CIS 基准配置文件的 CI 基准测试进行配置。 强化是一种通过限制使系统易受网络攻击的潜在漏洞，帮助防止未经授权的访问、拒绝服务和其他网络威胁的过程。

## <a name="microsoft-and-the-cis-benchmarks"></a>Microsoft 和 CIS 基准

Internet 安全中心 (CIS) 已发布适用于 Microsoft 产品和服务的基准，其中包括 Microsoft Azure 和 Microsoft 365 Foundations 基准、Windows 10 基准和 Windows Server 2016 基准。  
  
CIS 基准是国际公认的保护 IT 系统和数据免受网络攻击的安全标准。 这些标准被成千上万的企业所使用，为建立安全的基准配置提供了说明性指导。 系统和应用程序管理员、安全专家以及使用 Microsoft 产品和服务开发解决方案的其他人员，都可以使用这些最佳做法来评估和提高其应用程序的安全性。  
  
与所有 CIS 基准一样，Microsoft 基准使用一致的审查流程所创建，汇集了具有多样背景知识（包括软件开发、审核和合规性、安全研究、运营、政府和法律）的主题专家的建议。 Microsoft 在这些 CIS 工作中是不可或缺的合作伙伴。 例如，已针对上架服务对 Office 365 进行了测试，生成的 Microsoft 365 Foundation 基准涵盖了一系列关于设置适当安全策略的建议，包括帐户和身份验证、数据管理、应用程序权限、存储和其他安全策略领域。  
  
除了 Microsoft 产品和服务的基准之外，CIS 还发布了 [CIS 强化映像](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/)，用于配置满足 CIS 基准 Azure 虚拟机。 其中包括经过认证可在 Azure 上运行的适用于 Microsoft Windows Server 2016 的 CIS 强化映像。 CIS 说明：“所有在 [Azure 市场](https://azuremarketplace.microsoft.com/marketplace/apps?search=center%20for%20internet%20security)提供的 CIS 强化映像均经过认证可在 Azure 上运行， 已针对与 Azure 公共云、由服务提供商通过云 OS 网络托管的 Microsoft 云平台和由客户管理的本地私有云 Windows Server Hyper-V 部署的就绪性和兼容性进行了预测试。”

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 与 Azure 政府](https://aka.ms/AzureCompliance)
- [Office 和 Microsoft 365](https://aka.ms/o365-compliance-framework)
- SQL Server
- Windows 10
- Windows Server 2016

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

获取适用于 Microsoft 产品和服务的 [CIS 基准的完整列表](https://www.cisecurity.org/cis-benchmarks/)。

- [CIS Azure Foundations 基准](https://www.cisecurity.org/benchmark/azure/)
- [CIS Microsoft 365 Foundations 基准](https://www.cisecurity.org/benchmark/microsoft_office/)
- [Windows 10 基准](https://www.cisecurity.org/benchmark/microsoft_windows_desktop/)
- [Windows Server 2016 基准](https://www.cisecurity.org/benchmark/microsoft_windows_server/)

## <a name="how-to-implement"></a>如何实现

- [适用于 Azure 的 CIS 基准](https://azure.microsoft.com/mediahandler/files/resourcefiles/cis-microsoft-azure-foundations-security-benchmark/CIS_Microsoft_Azure_Foundations_Benchmark_v1.0.0.pdf)：获取为 Azure 建立安全基线配置的说明性指导。  
- [Office 365 安全路线图](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)：遵循此路线图，可将数据泄露或泄露帐户的可能性降至最低。
- [Windows 安全基线](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)：遵循以下准则，可在组织中有效使用安全基线。
- [CIS 控制措施云配套指南](https://www.cisecurity.org/white-papers/cis-controls-cloud-companion-guide/)：获取有关将 CIS 控制措施版本 7 中的安全最佳做法应用到云环境的指南。

## <a name="frequently-asked-questions"></a>常见问题解答

**以下 CIS 基准设置是否会确保应用程序的安全性？**

CIS 基准为采用范围内 Microsoft 产品和服务的任何人员建立基本级别的安全性。 但是，不要将其视为所有可能的安全配置和体系结构的详尽列表，而应将其作为起点。 每个组织仍必须评估其具体情况、工作负载和合规性要求，并对其环境进行相应调整。

**CIS 基准多久更新一次？**

CIS 基准修订版的发布将因开发它的 IT 专业人员的社区以及该基准所支持技术的发布计划而变化。 CIS 会发布月度报告，宣布新的基准和对现有基准的更新。 如需接收这些报告，请免费注册 [CIS 工作台](https://workbench.cisecurity.org/)，并在个人资料中选中“接收新闻稿”。

**谁参与 Microsoft CIS 基准的开发？**

CIS 指出，“基准是通过主题专家、技术供应商、公共和专用 CIS 基准社区成员以及 CIS 基准开发团队的大量志愿工作制定的。" 例如，在[当前提供的 CIS Microsoft Azure Foundations 基准 v1.0.0](https://www.cisecurity.org/blog/cis-microsoft-azure-foundations-benchmark-v1-0-0-now-available/) 中可找到 Azure 参与者名单。

## <a name="resources"></a>资源

- [安全使用 Microsoft 365 的 CIS 最佳做法](https://www.microsoft.com/security/blog/2019/01/10/best-practices-for-securely-using-microsoft-365-the-cis-microsoft-365-foundations-benchmark-now-available/)
- [Windows 10 安全策略设置](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/security-policy-settings)
- [Windows 10 企业安全性](https://docs.microsoft.com/windows/security/index)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下载产品/服务背景信息

需要此产品/服务的背景信息文档？ 请下载 [PDF](https://download.microsoft.com/download/9/B/7/9B75D846-BDB9-41CB-86FF-F0ADFD15800B/CIS_Benchmarks-Compliance.pdf)。
