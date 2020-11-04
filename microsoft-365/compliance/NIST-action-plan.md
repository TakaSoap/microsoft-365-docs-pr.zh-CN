---
title: Microsoft 365 NIST 800-53 行动计划 - 前 30 天、前 90 天以及之后的首要行动
description: 努力符合美国国家标准和技术协会 (NIST) 的要求时可遵循的已确定优先级的行动计划
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, NIST, NIST 800-53
author: BrendaCarter
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/14/2018
f1.keywords:
- NOCSH
ms.author: bcarter
manager: laurawi
audience: itpro
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24c3199847f412600e7d11e863a987d409c22f50
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843422"
---
# <a name="microsoft-365-nist-800-53-action-plan--top-priorities-for-your-first-30-days-90-days-and-beyond"></a>Microsoft 365 NIST 800-53 行动计划 - 前 30 天、前 90 天以及之后的首要行动

Microsoft 365 允许你使用云控制框架来运营企业，该框架将控制与多个监管标准保持一致。 Microsoft 365 包括 Office 365、Windows 10 和企业移动性 + 安全性。 Microsoft 的内部控制系统基于美国国家标准与技术研究院 (NIST) 特刊 800-53，Office 365 已通过最新的 NIST 800-53 标准认证。

Microsoft 被认为是云安全领域的行业领袖。通过多年构建企业软件和运行联机服务的经验，我们的团队一直在不断地学习，并持续更新服务和应用程序，从而交付满足严格行业标准的安全云生产力服务，以实现合规性。Microsoft 的政府云服务（包括 Office 365 美国政府版），满足美国联邦风险和授权管理计划 (FedRAMP) 的要求，使美国联邦机构能够从 Microsoft 云的成本节约和严格的安全性中获益。

本文介绍了致力于符合 NIST 800-53 要求时可遵循的优先行动计划。此行动计划是与专门从事合规性工作的 Microsoft 合作伙伴 Protiviti 共同制定的。 

## <a name="action-plan-outcomes"></a>行动计划结果

这些建议按逻辑顺序分三个阶段提供，具体结果如下： 

|||
|:-----|:-----|
|**阶段**|**结果**|
|30 天|*   了解 NIST 800-53 要求，并考虑与 Microsoft 咨询合作伙伴合作。<br>*   学习并了解 Microsoft 365 内置深层防护策略。  <br>*   保护用户和管理员对 Office 365 的访问。 <br>*   确保所有对系统的访问都可以根据组织的审核和责任制策略进行审核。|
|90 天|*   增强反恶意软件、修补程序和配置管理程序。<br>*   使用 Microsoft 365 安全功能来控制对环境的访问，并保护组织信息和资产。<br>*   利用内置审核功能，监视 Office 365 中的敏感或风险活动。<br>*   为电子邮件和 Office 文档中的链接和附件部署Office 365 防护。|
|90 天后|*   使用 Microsoft 365 高级工具和信息保护，对设备实施持续控制并实现对企业数据的保护。<br>*   监视 Microsoft 365 和其他云应用程序的持续合规性。  <br>*   使用增强的威胁检测和防护功能以及高级威胁分析，为组织提供可靠的分层安全策略。制定事件响应计划以减轻组织中遭破坏的系统的影响。|

## <a name="30-days--powerful-quick-wins"></a>30 天 - 强势速赢

这些任务可快速完成，对用户产生的影响很小。

|||
|:-----|:-----|
|**区域**|**任务**|
|了解 NIST 800-53 要求，并考虑与 Microsoft 咨询合作伙伴合作。|•    与 Microsoft 合作伙伴合作，共同对组织执行 NIST 800-53 合规性差距分析，并绘制合规性路线图。 <br>•   遵循 [Microsoft 合规性管理器](compliance-manager.md)中的指导，定义和记录与访问控制和信息共享相关的策略和过程，这些策略和过程涉及到目标、范围、角色、责任、组织实体之间的协作和合规性。|
|学习并了解 Microsoft 365 内置深层防护策略。|•   使用[合规性管理器](compliance-manager.md)来评估和管理合规性风险，以对组织进行 NIST 800-53 评估。让管理和减轻风险的 Microsoft 365 安全中心控制与评估结果保持一致。 <br>•    利用 [Microsoft 安全功能分数](/security/office-365-security/office-365-secure-score.md)在一段时间内在 Office 365 中以及 Windows 10 桌面上跟踪组织对 Microsoft 365 安全功能的使用情况。 <br>•  了解用于提供 [Office 365 数据加密](encryption.md)的 Microsoft 技术和策略，以及 Microsoft 云中针对[防御拒绝服务攻击](https://docs.microsoft.com/office365/enterprise/office-365-defending-against-denial-of-service-attacks-overview)的策略。|
|保护用户和管理员对 Office 365 的访问。|• 建立[强凭据管理](https://docs.microsoft.com/azure/security/azure-ad-secure-steps#step-1---strengthen-your-credentials)来保护用户帐户凭据。 <br> •  了解 Office 365 服务[推荐的标识和设备访问策略](../security/office-365-security/microsoft-365-policies-configurations.md)。<br> •  利用 [Office 365 管理角色](https://support.office.com/article/understanding-administrative-roles-52f29955-6a60-435f-aba9-eb69c898606a)实现对管理功能的基于角色的访问，并实现管理职责的分离。注意：Office 365 中的许多管理员角色都在 Exchange Online、SharePoint Online 和 Skype for Business Online 中有对应的角色。分割权限，确保单个管理员不具有超过所需权限的访问权限。|
|确保所有对系统的访问都可以根据组织的审核和责任制策略进行审核。|（针对所有 Exchange 邮箱）启用[审核日志](search-the-audit-log-in-security-and-compliance.md)和[邮箱审核](enable-mailbox-auditing.md)，以监视 Office 365 是否有潜在恶意活动，并启用数据泄露取证分析。|
|||

## <a name="90-days--enhanced-protections"></a>90 天 - 增强保护 
这些任务需要更多时间来规划和实施。 

|||
|:-----|:-----|
|**区域**|**任务**|
|增强反恶意软件、修补程序和配置管理程序。|•   通过向组织部署和启用 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/deploy-windows-defender-antivirus)和利用与 Windows 10 的紧密集成来保护企业资产和桌面设备。<br>•   跟踪隔离受感染的系统并防止进一步损坏，直到执行修正步骤。<br>•   无忧依赖于 Microsoft 365 严格标准更改管理流程以获取受信任的更新、修补程序和补丁。|
|使用 Microsoft 365 安全功能来控制对环境的访问，并保护组织信息和资产。|•   实施[推荐的标识和设备访问策略](../security/office-365-security/microsoft-365-policies-configurations.md)来保护用户和管理帐户。 <br>• 实施 [Office 365 邮件加密 (OME)](ome.md) 功能，以帮助用户在通过电子邮件发送敏感数据时遵守组织策略。<br>•   将 [Windows Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 部署到所有台式机上，以防范恶意代码，防止数据泄露并作出响应。<br>•  配置、测试和部署策略以标识、监视和[自动保护](apply-protection-to-personal-data-in-office-365.md)文档和电子邮件中的超过 80 种常见敏感数据类型，包括财务、医疗和个人身份信息。<br>•   通过配置[策略提示](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)，在电子邮件发件人发送违规邮件之前，自动通知他们可能违反了策略之一。可将策略提示配置为显示简要说明（在 Outlook、Outlook 网页版和适用于设备的 OWA 中），以提供邮件创建期间可能的策略违反信息。<br>• 通过实施对 [SharePoint Online 和 OneDrive for Business 的外部共享](https://docs.microsoft.com/onedrive/manage-sharing)的控制，保护敏感企业数据并满足组织的信息共享策略。确保仅经过身份验证的外部用户可以访问企业数据。|
|利用内置审核功能，监视 Office 365 中的敏感或风险活动。|•   启用 Microsoft 365 安全或合规中心的[警报策略](alert-policies.md)，以在出现敏感活动时（例如用户的帐户权限提升或访问敏感数据）引发自动通知。 应对所有特权功能进行审核和监控。<br>• 在安全或合规中心中定期[搜索的审核日志](search-the-audit-log-in-security-and-compliance.md)，以检查租户配置设置的更改。<br>• 对于长期存储的审核日志数据，使用 Office 365 管理活动 API 参考，与安全信息和事件管理 (SIEM) 工具集成。|
|为电子邮件和 Office 文档中的链接和附件部署Office 365防护。|实施 [Microsoft Defender for Office 365](/security/office-365-security/office-365-atp)，以帮助防范最常见的攻击媒介，包括钓鱼电子邮件和含有恶意链接和附件的 Office 文档。|
|||

## <a name="beyond-90-days--ongoing-security-data-governance-and-reporting"></a>90 天后 - 持续安全、数据管理和报告

这些操作需要更长时间并在之前工作的基础上构建。  

|||
|:-----|:-----|
|**区域**|**任务**|
|使用 Microsoft 365 高级工具和信息保护，对设备实施持续控制并实现对企业数据的保护。|*    使用 [Microsoft Intune](https://docs.microsoft.com/intune/) 保护移动设备上存储和访问的敏感数据，并确保使用合规的公司设备访问云服务。|
|监视 Microsoft 365 和其他云应用程序的持续合规性。|*    若要根据组织定义的策略和过程评估性能，请持续使用[合规性管理器](compliance-manager.md)，以定期对组织强制实现的信息安全策略进行评估。<br>*    使用 [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure) 控制拥有高级权限的所有用户和组（即特权用户或管理用户），并对其执行定期评审。<br>*    部署和配置[特权访问管理](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-overview)，以细化对 Office 365 中特权管理任务的访问控制。  启用后，用户需要通过范围和时间高度受限的审核工作流，请求获取实时访问权限来完成特权提升任务。<br>*    审核[非所有者邮箱访问权限](https://docs.microsoft.com/Exchange/policy-and-compliance/non-owner-mailbox-access-reports)，以标识潜在信息泄漏，并主动检查所有 Exchange Online 邮箱上的非所有者访问权限。<br>*    使用 [Office 365 警报策略、数据丢失防护报告和 Microsoft Cloud App Security](https://docs.microsoft.com/Office365/SecurityCompliance/monitor-for-leaks-of-personal-data)，监视组织的云应用程序使用情况，并实现基于启发和用户活动的高级警报策略。<br>*    使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 自动跟踪有风险的活动，以标识潜在恶意管理员、调查数据泄露或验证是否符合合规性要求。|
|利用增强的威胁检测和防护功能以及高级威胁分析，为组织提供可靠的分层安全策略。制定事件响应计划以减轻组织中遭破坏的系统的影响。|*    部署和配置 [Windows 高级威胁分析](https://docs.microsoft.com/advanced-threat-analytics/)以利用丰富的分析和报告，从而获得关键见解，了解组织中遭攻击的用户，以及被利用的网络攻击方法。<br>*    利用 [Defender for Office 365 的报告和分析](/security/office-365-security/view-reports-for-atp.md)，透过对组织中自动检测到的恶意内容和恶意电子邮件的见解来分析威胁。利用内置报告和邮件跟踪功能，可调查因未知病毒或恶意软件而被阻止的电子邮件。<br>*    使用 [Office 365 威胁智能](/security/office-365-security/office-365-ti.md)从各类源中聚合见解和信息，以获取云安全环境的整体视图。<br>*    [将 Office 365 威胁智能和 Microsoft Defender for Endpoint](/security/office-365-security/integrate-office-365-ti-with-wdatp.md)，以便在调查 Office 365 中的威胁时快速了解用户设备是否存在风险。<br>*    使用 [Office 365 攻击模拟器](/security/office-365-security/attack-simulator.md)模拟 Office 365 环境中常见的攻击手段。  查看攻击模拟器中的结果以识别用户的培训机会并验证组织的事件响应过程。<br>*    配置[安全或合规中心的权限](/security/office-365-security/permissions-in-the-security-and-compliance-center.md)以确保对监视和审核数据的访问仅限批准的用户，并与组织的事件响应措施相集成。|
|||

## <a name="learn-more"></a>了解更多

深入了解 [Microsoft 和 NIST 网络安全框架 (CSF)](offering-nist-csf.md)，包括 NIST 800-53。
