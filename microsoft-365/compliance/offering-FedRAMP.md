---
title: 联邦风险和授权管理项目 (FedRAMP)
description: Microsoft 被授予美国联邦风险和授权管理计划 P-ATOs 和 ATOs。
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
ms.openlocfilehash: 94e83110ef9761f551fd1401884dbba58a8df107
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208434"
---
# <a name="federal-risk-and-authorization-management-program-fedramp"></a>联邦风险和授权管理项目 (FedRAMP)

## <a name="fedramp-overview"></a>FedRAMP 概述

美国联邦风险和授权管理计划 (FedRAMP) 已建立，以提供一种标准化的方法来评估、监控和授权联邦信息安全管理 (法案（FISMA) ）下的云计算产品和服务，并加速联邦机构采用安全云解决方案。

管理办公室和预算现在要求所有执行联邦机构使用 FedRAMP 来验证云服务的安全性。  (其他机构也采用了它，因此它在公共部门的其他领域也很有用。 ) 美国国家标准 and 技术协会 (NIST) SP 800-53 设置强制性标准、建立信息系统的安全类别（机密性、完整性和可用性），以评估组织的信息系统和信息系统对组织的潜在影响。 FedRAMP 是证明云服务提供商 (CSP) 符合这些标准的程序。

将服务销售给联邦机构的 Csp desiring 可以采用三个途径来证明 FedRAMP 合规性：

- 从联合授权委员会 (JAB) 中获取 (操作) 的临时颁发机构。 JAB 是 FedRAMP 的主要调控和决策主体。 来自国防部门的代表、Homeland 安全部门以及在董事会上的常规服务管理服务。 该委员会向已证明 FedRAMP 合规性的 Csp 授予 P-ATO。
- 接收从联邦机构 (ATO) 操作的权限。
- 或者，单独工作以开发符合程序要求的 CSP 提供的程序包。

这些路径中的每一条都需要由 FedRAMP 计划管理办公室 (PMO) 和由该程序获得资格鉴定的独立第三方组织进行评估。

基于 NIST 指南（低、中和高）的三个影响级别授予 FedRAMP 授权。 这些级别对组织中可能存在的机密性、完整性或可用性的影响（低 (有限影响) 、中型 (严重影响) 以及高 (严重或灾难性影响) ）进行了排序。

## <a name="microsoft-and-fedramp"></a>Microsoft 与 FedRAMP

Microsoft 的政府云服务（包括 Azure 政府、Dynamics 365 政府和 Office 365 美国政府）满足美国联邦风险和授权管理计划 (FedRAMP) 的要求，使美国联邦机构能够从 Microsoft 云的成本节约和严格的安全性中获益。

Microsoft 政府云服务为公共部门客户提供了一系列符合 FedRAMP 的服务，并提供了强健的指导和实现工具，包括 [FedRAMP 高蓝图](https://aka.ms/fedrampblueprint)，可帮助客户为必须实现 FedRAMP 高控制的任何 Azure 部署体系结构部署一组核心策略。

## <a name="microsoft-azure-p-atos"></a>Microsoft Azure P-ATOs

Azure 和 Azure 政府已在联合授权委员会的 "高影响级别" 中获得了 ATO，这是 FedRAMP 资格鉴定的最高的一条，它可以授权使用 Azure 和 Azure 政府处理高度敏感的数据。

Azure 和 Azure 政府的 FedRAMP 审核包含的信息安全管理系统涵盖了对范围内服务的基础结构、开发、操作、管理和支持。 一旦授予了 ATO，CSP 仍然需要授权 (来自它使用的任何政府机构) 的 ATO。 对于 Azure，政府机构可以在其自己的安全授权过程中使用 Azure ATO，并将其作为颁发机构 ATO （也满足 FedRAMP 要求）的基础。

Azure 继续支持比任何其他云提供商更高的 FedRAMP 高影响级别上的服务。 而在 Azure 公共云中，FedRAMP 高将满足多个美国政府客户的需求，则具有更严格的要求的代理将继续依赖 Azure 政府，后者提供了额外的安全措施，如更高级的人员筛选。 Microsoft 列出了 Azure 政府 [目前提供的所有 azure 公共服务](https://docs.microsoft.com/azure/azure-government/compliance/azure-services-in-fedramp-auditscope#azure-public-services-by-audit-scope) 和 FedRAMP 高边界，以及为今年规划的服务。

## <a name="microsoft-dynamics-365-us-government-ato"></a>Microsoft Dynamics 365 美国政府版 ATO

Dynamics 365 美国政府已向美国的 FedRAMP 机构 ATO 授予美国) 的美国的 HUD 和市内 (开发的高影响级别。 虽然认证范围仅限于政府社区云，但 Dynamics 365 美国政府商业版和企业版计划在同一组严格的 FedRAMP 控件的后面运行。

## <a name="microsoft-office-365-and-office-365-us-government-atos"></a>Microsoft Office 365 和 Office 365 美国政府版 ATOs

- Office 365 和 Office 365 美国政府在美国卫生部门 (DHHS) 中有一个 ATO。
- Office 365 美国政府防御版中有一个 ATO 来自美国国防部的公司 (DISA) 。 任何想要部署 Office 365 美国政府防御的客户都可能使用 DISA P-ATO 来生成一个代理商的 ATO，以记录其对其接受程度。
- Office 365 (企业和企业计划) 和 Office 365 美国政府在检查器常规的 DHHS 办公室中有一个 FedRAMP 机构 ATO，在中等影响级别。 Office 365 美国政府是第一个用于获取此授权的基于云的电子邮件和协作服务。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 与 Azure 政府](https://go.microsoft.com/fwlink/p/?linkid=2095323)
- [美国政府 Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 和 Office 365 美国 Governmen](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- Office 365 美国政府防御版
- Power BI 云服务，作为独立服务提供，或者随 Office 365 品牌计划或套件一并提供
- Microsoft Defender ATP

> [!NOTE]
> 在 Azure 政府中使用 Azure Active Directory 要求使用在 azure 公有云之外部署到 Azure 政府之外的组件。

## <a name="audits-reports-and-certificates"></a>审核、报告和证书

Microsoft 每年都必须重新证明其云服务，以维持其 P-ATO 和 ATO 认证。 为此，Microsoft 必须不断监视和评估其安全控制，并证明其服务的安全性仍符合合规性。

- [Microsoft 云服务 FedRAMP 授权</span>](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [Microsoft FedRAMP 审计报告</span>](https://aka.ms/MicrosoftFedRAMPAuditDocuments)  

若要接收其他 FedRAMP 报告，请将电子邮件发送到 [Azure 联邦文档](mailto:AzFedDoc@microsoft.com)。

## <a name="quickly-deploy-your-fedramp-solutions-on-azure-government"></a>在 Azure 政府上快速部署 FedRAMP 解决方案

让 Microsoft 引导您完成 ATO 过程，并使用 FedRAMP 高蓝图快速部署 FedRAMP 解决方案，这有助于客户为必须实现 FedRAMP 高控制措施的任何 Azure 部署的体系结构实施一组核心策略。

[开始使用 Azure FedRAMP High 蓝图](https://aka.ms/fedrampblueprint)

## <a name="frequently-asked-questions"></a>常见问题解答

**Microsoft 云服务是否符合联邦信息安全管理法案 (FISMA) ？**

FISMA 是一种联邦法律，要求我们的联邦机构及其合作伙伴仅从符合 FISMA 要求的组织购买信息系统和服务。 大多数机构及其供应商指示它们是 FISMA 合规性的，它们都是指它们如何满足由 NIST 在特殊出版物800-53 修订版4中所标识的控制措施。 FISMA 过程 (，但不是基础标准本身) 替换为2011中的 FedRAMP。

**FedRAMP 适用于哪些人？**

对于采用低风险和中等风险影响级别的联邦机构云部署和服务模型，"FedRAMP" 是必需的。 任何想要接洽 CSP 的联邦机构可能都需要满足 FedRAMP 规范。 此外，在联邦政府使用的产品或服务中使用云技术的公司可能需要获取 ATO。

**我的机构在哪里启动其自己的合规性工作？**

若要概述必须采取的步骤才能成功导航 FedRAMP 并满足其要求，请转到 [获得授权：代理授权](https://www.fedramp.gov/agency-authorization/)。

**我可以在代理的授权过程中使用 Microsoft 合规性吗？**

是。 您可以使用 Microsoft 云服务的认证，作为任何需要联邦政府机构 ATO 的计划或计划的基础。 但是，您需要在这些服务之外为自己的组件实现自己的授权。

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>使用 Microsoft 合规性管理器评估风险

[Microsoft 合规性管理器](compliance-manager.md) 是 [microsoft 365 合规性中心](microsoft-365-compliance-center.md) 中的一项功能，可帮助您了解组织的合规性状况并采取措施帮助降低风险。 合规性管理器提供了一个用于为此法规建立评估的高级模板。 在合规性管理器的 " **评估模板** " 页中查找模板。 了解如何 [在合规性管理器中构建评估](compliance-manager-assessments.md)。

## <a name="resources"></a>资源

- [联邦风险和授权管理计划](https://www.fedramp.gov/)
- [FedRAMP 安全评估框架](https://www.fedramp.gov/assets/resources/documents/FedRAMP_Security_Assessment_Framework.pdf)
- [在 Microsoft 云中管理合规性](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Microsoft 政府云](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Azure 合规性服务](https://aka.ms/azurecompliance)
