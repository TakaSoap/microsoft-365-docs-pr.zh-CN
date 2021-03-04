---
title: 跨 Microsoft 365 配置威胁防护功能的步骤
description: 了解如何跨 Microsoft 365 E5 部署威胁防护服务和功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 01f11ee16c45b171d04fb382f65fa95ff84bf980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424145"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>跨 Microsoft 365 配置威胁防护功能

按照以下步骤在 Microsoft 365 中配置威胁防护。


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>步骤 1：设置多重身份验证和条件访问策略

[MFA (](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) 多重身份验证) 要求用户使用电话呼叫或验证器应用验证其身份。 [条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) 策略定义了用户访问 Microsoft 365 中的应用和数据必须满足的某些要求。 MFA 和条件访问策略协同工作来保护组织。 例如，如果有人尝试使用未启用 MFA 的帐户从移动设备登录，并且条件访问策略要求 MFA 生效，将阻止该用户登录。  

Microsoft 已测试并推荐了一组特定的条件访问和相关策略，用于保护对所有 SaaS 应用程序（尤其是 Microsoft 365）的访问。 建议策略用于基线、敏感和高度管控保护。 首先实现基线保护策略。 


[ ![ 有关配置标识和设备访问的常见策略，](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)请参阅 
 [此映像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>为 Microsoft 365 实施基线保护

![部署基线保护的过程](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [配置先决条件，包括 Azure AD Identity Protection。](../security/office-365-security/identity-access-prerequisites.md)
2. [配置用于基线保护的常见标识](../security/office-365-security/identity-access-policies.md) 和设备访问策略。
3. 为来宾用户 [、Microsoft](../security/office-365-security/identity-access-policies-guest-access.md) [Teams、Exchange](../security/office-365-security/teams-access-policies.md) [Online](../security/office-365-security/secure-email-recommended-policies.md)和 [SharePoint Online 和 OneDrive 配置策略](../security/office-365-security/sharepoint-file-access-policies.md)。

### <a name="more-information-about-protecting-identities"></a>有关保护标识详细信息

- [标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Azure MFA 安全指南](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>步骤 2：配置 Microsoft Defender 的标识

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 是一种基于云的安全解决方案，可与本地 Active Directory 域服务 (AD DS) 信号一起识别、检测和调查针对组织的高级威胁、泄露的身份和恶意内部操作。

Microsoft Defender for Identity 支持安全操作 (SecOps) 分析师和安全专业人员努力检测混合环境中的高级攻击，以：
- 使用基于学习的分析监视用户、实体行为和活动。
- 保护存储在 Active Directory 中的用户标识和凭据。
- 发现并调查整个击杀链中的可疑用户活动和高级攻击。
- 在简单的时间线上提供明确的事件信息，以实现快速会审。

### <a name="to-set-up-microsoft-defender-for-identity"></a>设置 Microsoft Defender for Identity

![部署 Microsoft Defender for Identity 的过程](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [设置 Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) 以保护主要环境。
2. 保护所有[域控制器和](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring)[林](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)。
3. 将 [Microsoft Defender for Identity 警报](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) 集成到 SecOps (安全) 操作中。

### <a name="more-information-about-microsoft-defender-for-identity"></a>有关 Microsoft Defender for Identity 的信息

- [什么是 Microsoft Defender for Identity？](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [视频：Microsoft Defender for Identity 简介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender for Identity 部署](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>步骤 3：打开 Microsoft 365 Defender

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 将信号和编排功能组合到单个解决方案中。 借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以将每个产品接收的威胁信号整合在一起，并确定威胁的完整范围和影响;它如何进入环境、它的影响以及它当前如何影响组织。 Microsoft 365 Defender 采取自动操作来防止或停止攻击，并自行修复受影响的邮箱、终结点和用户标识。

Microsoft 365 Defender 将跨工作负载的警报、事件、自动调查和响应以及高级搜寻 (Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security) 统一到单一的一个面板体验中。 为 Office 365 服务配置一个或多个 Defender 后，打开 Microsoft 365 Defender。 新功能会不断添加到 Microsoft 365 Defender;请考虑选择接收预览功能。

### <a name="to-set-up-microsoft-365-defender"></a>设置 Microsoft 365 Defender

![部署 Microsoft 365 Defender 的过程](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [查看先决条件](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。
2. [打开 Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)。
3. [选择加入预览功能](https://docs.microsoft.com/microsoft-365/security/mtp/preview)。

### <a name="more-information-about-microsoft-365-defender"></a>有关 Microsoft 365 Defender 详细信息

- [什么是 Microsoft 365 Defender？](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Microsoft 365 Defender 的新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>步骤 4：为 Office 365 配置 Microsoft Defender

[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 保护您的组织免受电子邮件、附件 (URL、) 、Office 文档和协作工具中的恶意威胁。 下表列出了 Microsoft 365 E5 中包含的 Microsoft Defender for Office 365 特性和功能：

|配置、保护和检测功能|自动化、调查、修正和教育功能|
|---|---|
|[安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[安全文档](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Defender for Office 365 保护中的防钓鱼](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[威胁跟踪器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[攻击模拟器](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

借助 Microsoft Defender for Office 365，整个组织人员可以更安全地进行通信和协作，并针对他们的电子邮件内容和 Office 文档进行威胁防护。

### <a name="to-set-up-microsoft-defender-for-office-365"></a>设置 Microsoft Defender for Office 365

![部署 Microsoft Defender for Office 365 的过程](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [设置和配置 Microsoft Defender for Office 365 策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。
2. [查看和使用 Microsoft Defender for Office 365 报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。
3. [使用威胁调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。

### <a name="more-information-about-microsoft-defender-for-office-365"></a>有关 Microsoft Defender for Office 365 的信息

- [Microsoft Defender for Office 365 概述](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft Defender for Office 365 的新增功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>步骤 5：为终结点配置 Microsoft Defender

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) 保护组织 (也称为终结点) 网络威胁、高级攻击和数据泄露。 安全团队可以更高效地管理其终结点的安全性。 强大的工具可帮助组织使用漏洞检测和威胁和漏洞管理来跟进 [未修补的系统](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。 自动检测和修正功能（如攻击面减少[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)、下一代[](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)保护、终结点检测和[响应](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)）以及自动调查和[修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)可帮助保护设备免受恶意软件的攻击。 除了这些功能外，客户还可以按需获得主动通知并咨询 Microsoft 威胁专家，这是选择加入托管搜寻服务的一部分。 


### <a name="set-up-microsoft-defender-for-endpoint"></a>设置 Microsoft Defender for Endpoint

![部署 Microsoft Defender for Endpoint 的过程](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [准备你的 Microsoft Defender 终结点部署](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)。
2. [设置 Microsoft Defender for Endpoint 部署](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [载入到 Microsoft Defender for Endpoint 服务](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)。
4. [完成你的顶级安全管理任务](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)。

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>有关 Microsoft Defender for Endpoint 详细信息

- [了解有关 Microsoft Defender for Endpoint 的更多信息](https://docs.microsoft.com/windows/security/threat-protection)。
- [试用 Microsoft Defender for Endpoint 评估实验室](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>步骤 6：配置 Microsoft Cloud App Security

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) 是一款云访问安全代理，支持日志收集、API 连接器和反向代理。 Microsoft Cloud App Security 提供丰富的可见性、对数据旅行的控制以及复杂的分析，以识别和防御所有云服务中的网络威胁。 借助 Microsoft Cloud App Security，安全操作可以保护组织的敏感信息，防止网络威胁和异常，发现和监视访问组织数据的应用，并帮助确保组织的云应用满足合规性要求。

### <a name="set-up-microsoft-cloud-app-security"></a>设置 Microsoft Cloud App Security

![部署 Microsoft Cloud App Security 的过程](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [设置门户和其他基本要求](https://docs.microsoft.com/cloud-app-security/general-setup)。
2. [设置云发现并](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery)[连接应用](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [为特色应用部署条件访问应用控件](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)。
4. [使用调查工具和仪表板](https://docs.microsoft.com/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>有关 Microsoft Cloud App Security 的更多信息

- [查看新的特性和功能](https://docs.microsoft.com/cloud-app-security/release-notes)。
- [了解有关 Microsoft Cloud App Security 的更多信息](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>步骤 7：监视状态并采取措施

设置和部署威胁防护服务和功能后，下一步是监视威胁检测，并采取适当的操作。 最佳起点是 Microsoft 365 安全中心 () ，你可以监视和管理 Microsoft 标识、数据、设备、应用和基础结构的安全性 [https://security.microsoft.com](https://security.microsoft.com) 。 

![Microsoft 365 安全中心](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 安全中心专用于安全管理员和安全运营团队。 在 Microsoft 365 安全中心，你可以：
- 使用安全分数查看组织的整体 [安全运行状况](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。
- [监视和查看](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) 有关标识、数据、设备、应用和基础结构状态的报告。
- 通过事件连接警报 [上的点](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)。
- 使用 [自动调查和修正](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) 来解决威胁。
- [主动搜寻威胁](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)，例如入侵尝试或影响电子邮件、数据、设备和标识的入侵活动。
- [通过威胁分析了解](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) 最新的攻击活动和技术。
- ...等等！

### <a name="more-information-about-the-microsoft-365-security-center"></a>有关 Microsoft 365 安全中心详细信息

- [开始使用 Microsoft 365 安全中心](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。
- [监视和查看报告](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)。
- [请参阅 Microsoft 365 中的安全门户](https://docs.microsoft.com/microsoft-365/security/mtp/portals)。

## <a name="step-8-train-users"></a>步骤 8：培训用户

培训用户可以节省用户和安全运营团队很多时间和沮丧。 浏览用户不太可能打开附件或单击可疑电子邮件中的链接，并且他们更有可能避免可疑网站。 

在贵组织中建立[](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)强大的安全意识文化（包括培训用户识别网络钓鱼攻击）方面，《百万人学校网络安全宣传活动手册》提供了出色的指导。 

Microsoft 365 提供以下资源来帮助通知组织用户：

|概念  |资源  |
|---------|---------|
|Microsoft 365     |[可自定义的学习路径](https://docs.microsoft.com/office365/customlearning/) <p>这些资源可帮助您将针对组织中最终用户的培训整合在一起        |
|Microsoft 365 安全中心 |[学习模块：使用 Microsoft 365 的内置智能安全性保护组织](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>本模块使您能够描述 Microsoft 365 安全功能如何协同工作，并阐述这些安全功能的好处。 |
|多重身份验证     | [两步验证：什么是其他验证页面？](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>本文帮助最终用户了解什么是多重身份验证以及为什么在组织中使用多重身份验证。    |

除了本指南之外，Microsoft 还建议用户执行本文中所述的操作：保护你的帐户和设备免受黑客和 [恶意软件的攻击](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 这些操作包括：
- 使用强密码
- 保护设备 
- 在 Windows 10 和 Mac PC 上为非托管 (启用安全功能) 
    
Microsoft 还建议用户采取以下文章中建议的操作来保护其个人电子邮件帐户：
- [帮助保护Outlook.com电子邮件帐户](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [使用两步验证保护 Gmail 帐户](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
