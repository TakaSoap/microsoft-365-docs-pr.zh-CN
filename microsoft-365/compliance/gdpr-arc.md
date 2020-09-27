---
title: 适用于 GDPR 的责任就绪清单
description: 在本文中，你将了解在用户使用 Microsoft 产品和服务时，责任就绪清单访问信息来支持 GDPR。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6952545060a524ef92af6e1e7a063da7091b0860
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214807"
---
# <a name="support-your-gdpr-program-with-accountability-readiness-checklists"></a>通过责任就绪清单支持 GDPR 计划

一般数据保护条例 (GDPR) 引入了新规定，适用于向欧盟 (EU) 民众提供商品和服务的组织，或收集并分析欧盟居民相关数据的组织。无论你或你的企业位于何处，都要遵守这些新规定。 如需了解更多详情，请参阅 [GDPR 摘要主题](gdpr.md)。

## <a name="accountability-readiness-checklists"></a>责任就绪清单

责任就绪清单旨在方便访问在用户使用 Microsoft 产品和服务时支持 GDPR 所需的信息。 此清单列出了根据 GDPR 你可能要履行的义务，并指出了可用于支持组织合规性的信息。

有针对以下四个 Microsoft 产品和服务系列的具体指南：

- [Office 365](gdpr-arc-Office365.md)
- [Dynamics 365](gdpr-arc-Dynamics365.md)
- [Azure](gdpr-arc-Azure.md)
- [Microsoft 支持和专业服务](gdpr-arc-prof-services.md)

可以使用[合规性管理器](compliance-manager.md)来管理此清单中的项目，具体方法是引用 GDPR 磁贴中“客户托管控件”下的控件 ID 和控件标题。

这些清单包括，下列支持 GDPR 的隐私计划的四类基本注意事项，以及示例要求。

1. 数据收集和处理的条件：

    - 何时获得同意？  
    - 确定并记录目的  
    - 隐私影响评估

2. 数据主体权利  

    - 确定 PII 主体（数据主体）的信息  
    - 提供同意修改或撤销机制

3. 经设计默认的隐私  

    - 限制收集  
    - 遵守标识级别  
    - 临时文件

4. 数据保护和安全性  

    - 了解组织及其上下文  
    - 计划  
    - 信息安全策略

## <a name="customer-agreements"></a>客户协议

- **联机服务条款**：[在线服务条款](https://go.microsoft.com/fwlink/p/?linkid=2052208)中收录了关于 GDPR 的 Microsoft 合同承诺。
- **Microsoft 产品条款**：Microsoft 将 [GDPR 条款承诺](https://go.microsoft.com/fwlink/p/?linkid=2052213)扩展到所有批量许可客户。
- **数据保护附录**：Microsoft 服务[将承诺扩展](https://go.microsoft.com/fwlink/p/?linkid=2052215)到 Microsoft 咨询服务客户和其他客户。

## <a name="gdpr-compliance-controls"></a>GDPR 合规性控制

- **使用合规性管理器**：使用[合规性管理器](compliance-manager.md)来审核并合并 Microsoft 为支持 GDPR 中规定的义务而采用的控制措施。
- **GDPR 控制映射**：访问 Microsoft 控制到 GDPR 义务的[完整映射](https://go.microsoft.com/fwlink/p/?linkid=2052220)。

## <a name="records-of-processing-for-processors"></a>处理器处理的记录

根据我们作为处理器向控制者客户提供的在线服务的规模和广度，我们希望客户在我们提供的在线工具中识别他们寻求处理记录的服务，并检索相关日志。 下面是有关 Azure 处理的记录的一个示例，客户会被请求识别查找其记录的处理活动类型。

### <a name="azure-logs"></a>Azure 日志

通常客户会关注活动日志和诊断日志：

- **活动日志**： [活动日志](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)提供对订阅中的资源执行操作的见解。 活动日志可帮助确定操作的发起人、发生时间和状态。
- **诊断日志**： [诊断日志](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) 所有的记录都由各个资源发出。 这些日志包括 Windows 事件系统日志、Azure 存储日志、密钥保管库审核日志，以及应用程序网关访问和防火墙日志。
- **日志存档**：所有诊断日志均写入集中和已加密的 Azure 存储帐户进行存档。 可通过用户配置保留期（最长 730 天），满足组织特定的保留要求。 这些日志连接到 Azure Monitor 日志，用于处理、存储和仪表板报告。

### <a name="other-logs"></a>其他日志

此外，还会在此体系结构中安装以下监视解决方案。 客户有责任配置这些解决方案，以便与 FedRAMP 安全控制保持一致：

- [AD 评估](https://docs.microsoft.com/azure/azure-monitor/insights/ad-assessment)： Active Directory 运行状况检查解决方案定期评估服务器环境的风险和运行状况，并提供针对已部署服务器基础结构的建议的优先级列表。
- [反恶意软件评估](https://docs.microsoft.com/azure/security-center/security-center-services?tabs=features-windows#supported-endpoint-protection-solutions-)：反恶意软件解决方案报告了恶意软件、威胁和保护状态。
- [Azure 自动化](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker)： Azure 自动化解决方案存储、运行和管理运行手册。
- [安全和审核](https://docs.microsoft.com/azure/security-center/security-center-introduction)：通过提供有关安全域、重要问题、检测、威胁智能和常见安全查询的指标，安全和审核仪表板提供有关资源安全状态的高级见解。
- [SQL 评估](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment)： SQL 运行状况检查解决方案定期评估服务器环境的风险和运行状况，并向客户提供针对已部署服务器基础结构的建议的优先级列表。
- [更新管理](https://docs.microsoft.com/azure/automation/update-management/update-mgmt-overview)：更新管理解决方案允许客户管理操作系统安全更新，包括可用更新的状态和安装所需更新的过程。
- [代理运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)：代理运行状况解决方案报告已部署的代理数及其地理分布，以及无响应代理数和正在提交操作数据的代理数。
- [Azure 活动日志](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log)：活动日志分析解决方案可帮助分析客户所有的 Azure 订阅的 Azure 活动日志。
- [更改跟踪](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log)：更改跟踪解决方案使客户能够轻松识别环境中的更改。

有关 Azure 的技术和安全措施的信息，控制者客户请访问 [Azure 安全文档](https://docs.microsoft.com/azure/security/)。 由于 Microsoft 不知道客户数据是否是个人数据，Azure 会将所有客户数据当做个人数据一样处理，因此客户很可能会考虑到所有相关资料。

### <a name="processor-information"></a>处理器信息

客户可能需要处理器处理信息记录的另一个产品是 Office 365。 若要查看与 Office 365 相关的信息，请参阅[在安全与合规中心文章中搜索审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

你还可以使用安全与合规中心查看有关 Dynamics 365 的信息。  若要查看安全与合规中心页面，请确保你持有正确的许可证。 了解有关许可证的详细信息，请参阅[安全与合规中心服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)文章。 若要搜索 Dynamics 365 事件，请访问[安全与合规中心](https://protection.office.com/unifiedauditlog)中的统一审核日志。

### <a name="professional-services-information"></a>专业服务信息

对于专业服务，将由客户方的客户代表向支持工程师提供专业服务支持数据。  如果客户通过联机产品门户、服务中枢或手机提交服务请求，则可能发生这种情况。

该信息存储在我们的 CRM 系统中，仅用于以下目的：

- 提供专业服务，包括提供技术支持、专业计划、建议、指南、数据迁移、部署和解决方案/软件开发服务。  
- 故障排除（预防、检测、调查、缓解和修复问题，包括安全事件）；而且 
- 持续改进（维护专业服务，包括安装最新更新，以及对可靠性、效能、质量和安全性进行改进）。 

根据支持操作的规模，Microsoft 将运行基于产品组的 CRM 系统。 处理的记录将包含在这些系统中。
在 CRM 系统中维护的记录中反映了处理历史记录。  在大多数情况下，服务请求历史记录在门户或服务中枢上可用。
有关门户或有关数据处理的任何其他查询不可用的具体详细信息，请联系技术帐户经理或联系 [Microsoft 技术支持](https://support.microsoft.com/contactus/)。

## <a name="learn-more"></a>了解更多

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
