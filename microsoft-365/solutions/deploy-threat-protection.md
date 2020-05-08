---
title: 在 Microsoft 365 中部署威胁防护功能
description: 了解如何在 Microsoft 365 E5 中部署威胁保护服务和功能。
ms.author: bcarter
author: brendacarter
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 92a2cc7603a1a49be5ee72fc7b6d132ce46e38d7
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160866"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>在 Microsoft 365 中部署威胁防护功能

[恶意软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)和复杂的 cyberattacks （如[fileless 威胁](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)）是常见事件。 企业需要保护自己及其客户。 此类攻击可能会导致贵组织的主要问题，包括从失去信任到财务 woes、业务威胁停机等。 防御威胁非常重要，但确定组织的时间、工作和资源的位置可能会有很大难度。 

Microsoft 安全解决方案内置在我们的产品和服务中。 自动化和机器学习功能可降低安全团队的负载，以确保解决正确的项目。 Microsoft 安全解决方案的优势是基于我们在我们的[智能安全图形](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)中每天处理的 trillions 信号来构建的。 Microsoft 365 安全解决方案包括[Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)，这是一种解决方案，它将跨电子邮件、数据、设备和标识的信号汇集在一起，以在组织中绘制高级威胁的图片。

观看此视频，了解部署过程的概述。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

使用本文作为实施威胁防护解决方案的指南。

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 中的威胁防护

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab)使你能够使用自适应内置智能来保护你的组织。 使用 Microsoft 365 E5 中的威胁防护功能，可以在内部部署和云环境中检测和调查高级威胁、受到危害的身份和恶意操作。

在 Microsoft 365 E5 中，默认情况下会集成威胁防护功能。 来自每个功能的信号将强度增加到检测和响应威胁的总体能力。 与运行非 Microsoft 产品相比，组合的一组功能为组织提供了最佳保护，尤其是多国组织。 下图描述了 Microsoft 365 E5 中的威胁防护服务和功能，如本文中所述。

![Microsoft 威胁防护概述](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

一旦您部署任何高级威胁防护功能，您就可以打开 Microsoft 威胁防护，这会将信号和数据集中到一个位置。 

![Microsoft 威胁防护仪表板的概念性图示](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

下图展示了用于部署这些单独功能的推荐途径。 

![M365 威胁防护信号](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|解决方案/功能  |说明  |
|---------|---------|
|多重身份验证和条件访问     |针对泄露的标识和设备进行防护。 从这种保护开始，因为它是基础。 本指南中建议的配置包括作为先决条件的 Azure AD 标识保护。     |
|Azure 高级威胁防护     |  一种基于云的安全解决方案，利用本地 Active Directory 信号识别、检测和调查组织中的高级威胁、已泄露身份和恶意内幕行为。 将重点放在接下来，因为它保护您的本地和云基础结构，没有任何依赖项或先决条件，并且可以提供直接的好处。       | 
|Office 365 高级威胁防护     | 保护您的组织免受电子邮件、链接（Url）和协作工具带来的恶意威胁的侵扰。 针对恶意软件、网络钓鱼、欺骗和其他攻击类型的保护。 这是建议的下一步，因为更改控制、从委任系统迁移设置以及其他注意事项可能需要更长时间才能部署。 <br><br>注意：请确保同时配置所有 Office 365 订阅（Exchange Online Protection）中包含的威胁防护功能。       |
|Microsoft Defender 高级威胁防护    | 一种 endpoint protection 平台，可帮助防止、检测、调查和响应高级威胁。 此过程的部署时间较长，但如果其他管理员负责，则可以与其他功能并行执行。   |
|Microsoft Cloud App Security     |   用于发现、调查和治理的云访问安全代理。 你可以在早期启用此，以开始收集数据和见解。 在您的 SaaS 应用程序中实施信息和其他目标保护涉及规划，并可能需要更多时间。       | 

> [!TIP]
> 具有多个安全团队的组织可以并行实施这些功能。

## <a name="deploy-your-threat-protection-solution"></a>部署威胁防护解决方案

若要确保贵组织能够获得最佳保护，请设置和部署安全解决方案以包括以下步骤：

1. [设置多重身份验证和条件访问策略](#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [配置 Azure 高级威胁防护](#step-2-configure-azure-advanced-threat-protection)
3. [打开 Microsoft 威胁防护](#step-3-turn-on-microsoft-threat-protection)
4. [配置 Office 365 高级威胁防护](#step-4-configure-office-365-advanced-threat-protection)
5. [配置 Microsoft Defender 高级威胁防护](#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [配置 Microsoft 云应用安全](#step-6-configure-microsoft-cloud-app-security)
7. [监视状态并采取操作](#step-7-monitor-status-and-take-actions)
8. [培训用户](#step-8-train-users)

您的威胁防护功能可以并行配置，因此，如果您有多个负责不同服务的安全团队，则可以同时配置组织的保护功能。 下图说明了部署威胁防护功能的高级别过程。 

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>步骤1：设置多重身份验证和条件访问策略

[多重身份验证](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)（MFA）要求用户使用电话呼叫或验证器应用验证其身份。 [条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)定义了必须满足的某些要求，以便用户能够访问 Microsoft 365 中的应用和数据。 MFA 和条件访问策略协同工作以保护您的组织。 例如，如果有人尝试使用未启用 MFA 的帐户从移动设备登录，且条件访问策略要求 MFA 有效，则将阻止该用户登录。  

Microsoft 已测试并建议一组特定的条件访问和相关策略，用于保护对所有 SaaS 应用程序的访问，尤其是 Microsoft 365。 建议将策略用于比较基准、敏感和高度管控保护。 首先实施针对基准保护的策略。 


[![用于配置标识和设备访问](../media/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)
[的常见策略请参阅此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>实施 Microsoft 365 的基准保护

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [配置先决条件，包括 Azure 标识保护](../enterprise/identity-access-prerequisites.md)。
2. 配置用于基准保护的[常用标识和设备访问策略](../enterprise/identity-access-policies.md)。
3. 为[来宾用户](../enterprise/identity-access-policies-guest-access.md)、 [Microsoft 团队](../enterprise/teams-access-policies.md)、 [Exchange Online](../enterprise/secure-email-recommended-policies.md)和[SharePoint online 和 OneDrive](../enterprise/sharepoint-file-access-policies.md)配置策略。

### <a name="more-information-about-protecting-identities"></a>有关保护标识的详细信息

- [标识和设备访问配置](../enterprise/microsoft-365-policies-configurations.md)
- [Azure MFA 的安全指南](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-azure-advanced-threat-protection"></a>步骤2：配置 Azure 高级威胁防护

[Azure 高级威胁防护](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)（azure ATP）是一种基于云的安全解决方案，可与本地[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)信号配合使用，以识别、检测和调查组织中的高级威胁、已泄露身份和恶意内幕行为。

Azure ATP 启用安全操作（SecOps）分析师和安全专业人员，以检测混合环境中的高级攻击：
- 使用基于学习的分析监视用户、实体行为和活动。
- 保护存储在 Active Directory 中的用户标识和凭据。
- 发现并调查整个击杀链中的可疑用户活动和高级攻击。
- 在简单的时间线上提供明确的事件信息，以实现快速会审。

### <a name="to-set-up-azure-atp"></a>设置 Azure ATP

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [设置 AZURE ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1)以保护你的主要环境。
2. 保护所有[域控制器](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring)和[林](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)。
3. 将[AZURE ATP 警报](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external)集成到安全操作（SecOps）工作流中。

### <a name="more-information-about-azure-atp"></a>有关 Azure ATP 的详细信息

- [什么是 Azure ATP？](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [视频： Azure ATP 简介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Azure ATP 部署](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-threat-protection"></a>步骤3：打开 Microsoft 威胁防护

[Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)将信号和协调功能合并到单个解决方案中。 使用集成的 Microsoft 威胁防护解决方案，安全专业人员可以将威胁信号与这些产品中的每个产品一起接收并确定威胁的完整作用域和影响，并将它们结合起来。如何进入环境、受影响的内容以及当前对组织的影响。 Microsoft 威胁防护采用自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户身份。

Microsoft 威胁防护将警报、事件、自动调查和响应以及跨工作负载（Azure ATP、Office 365 ATP、Microsoft Defender ATP 和 Microsoft 云应用安全）的高级调查统一到了单个界面体验中。 配置了一个或多个高级威胁防护服务后，请打开 Microsoft 威胁防护。 新功能将不断添加到 Microsoft 威胁防护中;考虑选择接收预览功能。

### <a name="to-set-up-microsoft-threat-protection"></a>设置 Microsoft 威胁防护

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [查看先决条件](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。
2. [启用 Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)。
3. [选择加入预览功能](https://docs.microsoft.com/microsoft-365/security/mtp/preview)。

### <a name="more-information-about-microsoft-threat-protection"></a>有关 Microsoft 威胁防护的详细信息

- [什么是 Microsoft 威胁防护？](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Microsoft 威胁防护的新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-office-365-advanced-threat-protection"></a>步骤4：配置 Office 365 高级威胁防护

[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（OFFICE 365 ATP）保护您的组织免受电子邮件中的恶意威胁（附件和 url）、Office 文档和协作工具。 下表列出了 Microsoft 365 E5 中包含的 Office 365 ATP 特性和功能：

|||
|---|---|
|配置、保护和检测功能|自动化、调查、修正和教育功能|
|[安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[安全文档](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[ATP 反网络钓鱼防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[威胁跟踪器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[攻击模拟器](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

使用 Office 365 ATP，组织中的人员可以更安全地进行通信和协作，并为其电子邮件内容和 Office 文档提供威胁保护。

### <a name="to-set-up-office-365-atp"></a>设置 Office 365 ATP

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [设置和配置 Office 365 ATP 策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。
2. [查看和使用您的 Office 365 ATP 报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。
3. [使用威胁调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。

### <a name="more-information-about-office-365-atp"></a>有关 Office 365 ATP 的详细信息

- [Office 365 ATP 概述](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Office 365 ATP 的新增功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-advanced-threat-protection"></a>步骤5：配置 Microsoft Defender 高级威胁防护

[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection)（MICROSOFT defender ATP）通过威胁、高级攻击和数据泄露保护组织设备（也称为终结点）。 安全团队在管理其终结点的安全性时可提高效率。 稳健的工具可帮助组织随时使用带有[威胁和漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的漏洞检测功能，从而及时修补系统。 自动检测和修复功能（如[攻击面降低](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)、[下一代保护](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)、[终结点检测和响应](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)）以及[自动调查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)有助于保护设备免受恶意软件的危害。 在这些功能之上，客户可以根据需要获取主动通知并与 Microsoft 威胁专家进行协商，作为自愿加入托管的搜寻服务的一部分。 


### <a name="set-up-microsoft-defender-atp"></a>设置 Microsoft Defender ATP

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [准备 Microsoft DEFENDER ATP 部署](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)。
2. [设置你的 Microsoft Defender ATP 部署](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [在 Microsoft DEFENDER ATP 服务的板载](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)。
4. [完成您的首要安全管理任务](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)。

### <a name="more-information-about-microsoft-defender-atp"></a>有关 Microsoft Defender ATP 的详细信息

- [了解有关 Microsoft DEFENDER ATP 的详细信息](https://docs.microsoft.com/windows/security/threat-protection)。
- [尝试 Microsoft DEFENDER ATP 评估实验室](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>步骤6：配置 Microsoft 云应用安全

[Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security)是支持日志收集、API 连接器和反向代理的云访问安全代理。 Microsoft 云应用安全性提供丰富的可视性、控制数据旅行和完善的分析，以跨所有云服务识别和防御威胁。 通过 Microsoft 云应用安全性，您的安全操作可以保护组织的敏感信息、防止威胁和异常、发现和监视访问组织数据的应用程序，并帮助确保组织的云应用程序符合合规性要求。

### <a name="set-up-microsoft-cloud-app-security"></a>设置 Microsoft 云应用安全性

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [设置门户和其他基本要求](https://docs.microsoft.com/cloud-app-security/general-setup)。
2. [设置云发现](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery)和[连接应用](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [为特色应用程序部署条件访问应用程序控件](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)。
4. [使用调查工具和仪表板](https://docs.microsoft.com/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>有关 Microsoft Cloud App Security 的更多信息

- [查看新的特性和功能](https://docs.microsoft.com/cloud-app-security/release-notes)。
- [了解有关 Microsoft 云应用安全性的详细信息](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>步骤7：监视状态并执行操作

在设置并部署了威胁防护服务和功能之后，下一步是监视威胁检测，并采取适当的措施。 您最好的起点是 Microsoft 365 安全中心（[https://security.microsoft.com](https://security.microsoft.com)），您可以在其中监视和管理整个 Microsoft 标识、数据、设备、应用程序和基础结构中的安全性。 

:::image type="content" source="../media/solutions-architecture-center/m365-security-center.png" alt-text="Microsoft 365 安全中心":::

Microsoft 365 安全中心专为安全管理员和安全操作团队而设计。 在 Microsoft 365 安全中心中，可以执行以下操作：
- 查看[安全得分](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)的组织的整体安全运行状况。
- [监视和查看](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)有关你的标识、数据、设备、应用程序和基础结构的状态报告。
- 通过[事件](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)连接警报上的点。
- 使用[自动调查和修正](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)来解决威胁。
- [主动查找威胁](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)，如入侵尝试或影响您的电子邮件、数据、设备和标识的入侵行为。
- 通过威胁分析[了解最新的攻击活动](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns)和技术。
- ...更多！

### <a name="more-information-about-the-microsoft-365-security-center"></a>有关 Microsoft 365 安全中心的详细信息

- [开始使用 Microsoft 365 安全中心](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。
- [监视和查看报告](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)。
- [请参阅 Microsoft 365 中的安全门户](https://docs.microsoft.com/microsoft-365/security/mtp/portals)。

## <a name="step-8-train-users"></a>步骤8：培训用户

培训用户可将您的用户和安全操作团队保存很多时间和不满。 精通用户不太可能打开附件或单击可疑电子邮件中的链接，并且更有可能避免可疑网站。 

Harvard 肯尼迪 School [Cybersecurity 活动手册](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)提供了有关在组织内建立强大的安全感知文化的最佳指南，包括培训用户以识别网络钓鱼攻击。 

Microsoft 365 提供了以下资源来帮助您在组织中通知用户：

|概念  |资源  |
|---------|---------|
|Microsoft 365     |[可自定义的学习途径](https://docs.microsoft.com/office365/customlearning/) <p>这些资源可帮助您将组织中最终用户的培训放在一起        |
|Microsoft 365 安全中心 |[学习模块：使用 Microsoft 365 内置的智能安全保护您的组织](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>此模块使您能够描述 Microsoft 365 安全功能如何协同工作，并阐明这些安全功能的优势。 |
|多重身份验证     | [双重验证：什么是额外的验证页？](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>本文帮助最终用户了解什么是多重身份验证，以及在您的组织中使用它的原因。    |

除了本指南之外，Microsoft 还建议您的用户执行本文中所述的操作：[保护您的帐户和设备免受黑客和恶意软件的攻击](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 这些操作包括：
- 使用强密码
- 保护设备 
- 在 Windows 10 和 Mac 电脑（针对非托管设备）上启用安全功能
    
Microsoft 还建议用户采取以下文章中建议的操作来保护其个人电子邮件帐户：
- [帮助保护你的 Outlook.com 电子邮件帐户](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [通过2步验证保护你的 Gmail 帐户](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
