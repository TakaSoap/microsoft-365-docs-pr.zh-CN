---
title: 跨 Microsoft 365 配置威胁防护功能的步骤
description: 使用本文作为实现威胁防护解决方案的指南。 了解如何跨 Microsoft 365 E5 部署威胁防护服务和功能。
keywords: 安全， 设置， 配置， Microsoft 365 E5， 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 925c62e1c6201c54fcf09d0dd98b06906d9e057f
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599859"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>配置 Microsoft 365 中的威胁防护功能

按照以下步骤在 Microsoft 365 中配置威胁防护。


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>步骤 1：设置多重身份验证和条件访问策略

[MFA (](/azure/active-directory/authentication/concept-mfa-howitworks) 多重) 要求用户使用电话呼叫或验证器应用验证其身份。 [条件访问](/azure/active-directory/conditional-access/overview) 策略定义了用户访问 Microsoft 365 中的应用和数据所必须满足的某些要求。 MFA 和条件访问策略协同工作来保护你的组织。 例如，如果有人尝试使用未启用 MFA 的帐户从移动设备登录，并且条件访问策略要求 MFA 生效，则阻止该用户登录。  

Microsoft 已测试并推荐了一组特定的条件访问和相关策略，用于保护对全部 SaaS 应用程序（尤其是 Microsoft 365）的访问。 建议对基线、敏感和高度管控保护使用策略。 首先实现基准保护策略。 


[ ![ 配置标识和设备访问的常见策略](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [请参阅此映像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>为 Microsoft 365 实施基线保护

![部署基线保护的过程](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [配置先决条件，包括 Azure AD Identity Protection。](../security/office-365-security/identity-access-prerequisites.md)
2. [配置用于基线保护的常见标识和设备](../security/office-365-security/identity-access-policies.md) 访问策略。
3. 为来宾用户 [、Microsoft](../security/office-365-security/identity-access-policies-guest-access.md) [Teams、Exchange](../security/office-365-security/teams-access-policies.md) [Online](../security/office-365-security/secure-email-recommended-policies.md)和 [SharePoint Online 和 OneDrive 配置策略](../security/office-365-security/sharepoint-file-access-policies.md)。

### <a name="more-information-about-protecting-identities"></a>有关保护标识的信息

- [标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Azure MFA 安全指南](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>步骤 2：为标识配置 Microsoft Defender

[Microsoft Defender for Identity](/defender-for-identity/what-is) 是一种基于云的安全解决方案，它可与本地 Active Directory 域服务 (AD DS) 信号一起识别、检测和调查针对你的组织的高级威胁、泄露的身份和恶意内部操作。

Microsoft Defender for Identity 支持使用 SecOps (安全) 分析人员和安全专业人员，他们努力检测混合环境中的高级攻击，以：
- 使用基于学习的分析监视用户、实体行为和活动。
- 保护存储在 Active Directory 中的用户标识和凭据。
- 发现并调查整个击杀链中的可疑用户活动和高级攻击。
- 在简单的时间线上提供明确的事件信息，以实现快速会审。

### <a name="to-set-up-microsoft-defender-for-identity"></a>设置 Microsoft Defender for Identity

![部署 Microsoft Defender for Identity 的过程](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [设置 Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step1) 以保护主要环境。
2. 保护所有[域控制器和](/azure-advanced-threat-protection/atp-sensor-monitoring)[林](/azure-advanced-threat-protection/atp-multi-forest)。
3. 将 [Microsoft Defender for Identity 警报集成到](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) SecOps (安全) 操作中。

### <a name="more-information-about-microsoft-defender-for-identity"></a>有关 Microsoft Defender for Identity 详细信息

- [什么是 Microsoft Defender for Identity?](/azure-advanced-threat-protection/what-is-atp)
- [视频：Microsoft Defender 标识简介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender for Identity 部署](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>步骤 3：打开 Microsoft 365 Defender

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) 将信号和安排功能组合到单个解决方案中。 借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以整合每个产品接收的威胁信号，并确定威胁的完整范围和影响;它如何进入环境、对环境的影响以及它当前对组织的影响。 Microsoft 365 Defender 采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。

Microsoft 365 Defender 将跨工作负载的警报、事件、自动调查和响应以及高级搜寻 (Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security) 统一为单一的一层体验。 新功能不断添加到 Microsoft 365 Defender;考虑选择接收预览功能。

### <a name="to-set-up-microsoft-365-defender"></a>设置 Microsoft 365 Defender

![部署 Microsoft 365 Defender 的过程](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [查看先决条件](../security/defender/prerequisites.md)。
2. [打开 Microsoft 365 Defender](../security/defender/m365d-enable.md)。
3. [选择加入预览功能](../security/defender/preview.md)。

### <a name="more-information-about-microsoft-365-defender"></a>有关 Microsoft 365 Defender 详细信息

- [什么是 Microsoft 365 Defender？](../security/defender/microsoft-365-defender.md)
- [Microsoft 365 Defender 的新增功能](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>步骤 4：为 Office 365 配置 Microsoft Defender

[Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) 保护您的组织免受电子邮件、附件 (URL、Office 文档和协作) 中的恶意威胁。 下表列出了 Microsoft 365 E5 中包含的 Microsoft Defender for Office 365 特性和功能：

|配置、保护和检测功能|自动化、调查、修正和教育功能|
|---|---|
|[安全附件](../security/office-365-security/safe-attachments.md)<br/>[安全链接](../security/office-365-security/safe-links.md)<br/>[安全文档](../security/office-365-security/safe-docs.md)<br/>[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../security/office-365-security/mdo-for-spo-odb-and-teams.md)<br/>[Defender for Office 365 保护中的防钓鱼](../security/office-365-security/set-up-anti-phishing-policies.md#Exclusive-settings-in-anti-phishing-policies-in Microsoft-Defender-for-Office-365)|[威胁跟踪器](../security/office-365-security/threat-trackers.md)<br/>[威胁资源管理器](../security/office-365-security/threat-explorer.md)<br/>[自动调查和响应](../security/office-365-security/office-365-air.md)<br/>[攻击模拟器](../security/office-365-security/attack-simulator.md)|
|

借助适用于 Office 365 的 Microsoft Defender，整个组织人员可以更安全地进行通信和协作，并针对他们的电子邮件内容和 Office 文档进行威胁防护。

### <a name="to-set-up-microsoft-defender-for-office-365"></a>设置 Microsoft Defender for Office 365

![部署 Microsoft Defender for Office 365 的过程](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [设置和配置适用于 Office 365 的 Microsoft Defender 策略](../security/office-365-security/protect-against-threats.md)。
2. [查看和使用适用于 Office 365](../security/office-365-security/view-reports-for-mdo.md)的 Microsoft Defender 报告。
3. [使用威胁调查和响应功能](../security/office-365-security/office-365-ti.md)。

### <a name="more-information-about-microsoft-defender-for-office-365"></a>有关 Microsoft Defender for Office 365 详细信息

- [Microsoft Defender for Office 365 概述](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Office 365 的新增功能](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>步骤 5：为终结点配置 Microsoft Defender

[Microsoft Defender for Endpoint](/windows/security/threat-protection) 保护组织 (也称为终结点) 网络威胁、高级攻击和数据泄露。 安全团队可以更高效地管理其终结点的安全性。 强大的工具可帮助组织使用漏洞检测与威胁和漏洞管理来跟进 [未修补的系统](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。 自动检测和修正功能（如攻击面减少[](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)、下一代[](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)保护、终结点检测和[响应](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)）以及自动调查和修正可帮助[](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)你的设备免受恶意软件的攻击。 除了这些功能外，客户还可以按需获取主动通知并咨询 Microsoft 威胁专家，这是选择托管搜寻服务的一部分。 


### <a name="set-up-microsoft-defender-for-endpoint"></a>设置 Microsoft Defender for Endpoint

![部署 Microsoft Defender for Endpoint 的过程](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [为 Microsoft Defender 终结点部署准备你的环境](/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)。
2. [设置适用于终结点的 Microsoft Defender 部署](/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)。
3. [载入到 Microsoft Defender for Endpoint 服务](/windows/security/threat-protection/microsoft-defender-atp/onboarding)。
4. [完成顶级安全管理任务](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)。

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>有关 Microsoft Defender for Endpoint 详细信息

- [了解有关适用于终结点的 Microsoft Defender 的更多信息](/windows/security/threat-protection)。
- [尝试 Microsoft Defender for Endpoint 评估实验室](/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>步骤 6：配置 Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security) 是一款云访问安全代理，支持日志收集、API 连接器和反向代理。 Microsoft Cloud App Security 提供丰富的可见性、对数据旅行的控制以及复杂的分析，以识别和防御所有云服务中的网络威胁。 借助 Microsoft Cloud App Security，安全操作可以保护组织的敏感信息，防止网络威胁和异常，发现和监视访问组织数据的应用，并帮助确保组织的云应用满足合规性要求。

### <a name="set-up-microsoft-cloud-app-security"></a>设置 Microsoft Cloud App Security

![部署 Microsoft Cloud App Security 的过程](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [设置门户和其他基本要求](/cloud-app-security/general-setup)。
2. [设置云发现和](/cloud-app-security/set-up-cloud-discovery)[连接应用](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [为特色应用部署条件访问应用控制](/cloud-app-security/proxy-deployment-aad)。
4. [使用调查工具和仪表板](/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>有关 Microsoft Cloud App Security 的更多信息

- [查看新的特性和功能](/cloud-app-security/release-notes)。
- [了解有关 Microsoft Cloud App Security 的更多信息](/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>步骤 7：监视状态并采取措施

设置和部署威胁防护服务和功能后，下一步是监视威胁检测，并采取适当的措施。 最佳起点是 Microsoft 365 安全中心 () ，你可以监视和管理 Microsoft 标识、数据、设备、应用和 [https://security.microsoft.com](https://security.microsoft.com) 基础结构的安全性。 

![Microsoft 365 安全中心](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 安全中心面向安全管理员和安全运营团队。 在 Microsoft 365 安全中心中，你可以：
- 使用安全分数 查看组织的整体 [安全运行状况](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score)。
- [监视和查看](https://docs.microsoft.com/microsoft-365/security/defender/monitoring-and-reporting) 有关标识、数据、设备、应用和基础结构状态的报告。
- 通过事件连接警报 [上的点](https://docs.microsoft.com/microsoft-365/security/defender/incident-queue)。
- 使用 [自动调查和修正](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir) 来解决威胁。
- [主动搜寻威胁](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview)，例如入侵尝试或影响电子邮件、数据、设备和标识的入侵活动。
- [通过威胁分析了解](https://docs.microsoft.com/microsoft-365/security/defender/latest-attack-campaigns) 最新的攻击活动和技术。
- ...等等！

### <a name="more-information-about-the-microsoft-365-security-center"></a>有关 Microsoft 365 安全中心详细信息

- [Microsoft 365 安全中心入门](../security/defender/overview-security-center.md)。
- [监视和查看报告](../security/defender/overview-security-center.md)。
- [请参阅 Microsoft 365 中的安全门户](../security/defender/portals.md)。

## <a name="step-8-train-users"></a>步骤 8：培训用户

培训用户可以节省用户和安全运营团队很多时间和麻烦。 不为人知的用户不太可能打开可疑电子邮件中的附件或单击链接，并且他们更有可能避免可疑网站。 

该学院网络安全 [宣传活动](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 手册提供了有关在组织中建立强大安全意识文化的指导，包括培训用户识别网络钓鱼攻击。 

Microsoft 365 提供以下资源来帮助通知贵组织的用户：

|概念  |资源  |
|---------|---------|
|Microsoft 365     |[可自定义的学习路径](/office365/customlearning/) <p>这些资源可帮助您将针对组织中最终用户的培训整合在一起        |
|Microsoft 365 安全中心 |[学习模块：使用 Microsoft 365 的内置智能安全性保护组织](/learn/modules/security-with-microsoft-365) <p>本模块使您能够描述 Microsoft 365 安全功能如何协同工作，并阐明这些安全功能的好处。 |
|多重身份验证     | [两步验证：什么是附加验证页面？](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>本文帮助最终用户了解什么是多重身份验证以及为什么在组织中使用的多重身份验证。    |

除了本指南之外，Microsoft 还建议你的用户执行本文中所述的操作：保护你的帐户和设备免受黑客和 [恶意软件的攻击](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 这些操作包括：
- 使用强密码
- 保护设备 
- 在 Windows 10 和 Mac PC 上为非托管 (启用安全功能) 
    
Microsoft 还建议用户采取以下文章中建议的操作来保护其个人电子邮件帐户：
- [帮助保护 Outlook.com 电子邮件帐户](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [使用 2 步验证保护 Gmail 帐户](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
