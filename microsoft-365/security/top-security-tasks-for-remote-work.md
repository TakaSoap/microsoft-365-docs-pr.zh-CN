---
title: 支持在家工作的安全团队的 12 大任务
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: 保护业务电子邮件和数据免受网络威胁，包括勒索软件、网络钓鱼和恶意附件。
ms.openlocfilehash: a1850438d02042ba5931a6208b82f74766ae0be8
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097266"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>支持在家工作的安全团队的 12 大任务

如果你和 [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) 一样，突然发现自己支持主要在家办公的员工，我们希望帮助你确保你的组织尽可能安全地工作。 本文将确定任务的优先级，以帮助安全团队尽快实现最重要的安全性功能。

![执行这些首要任务以支持在家工作。](../media/security/security-support-remote-work.png)

如果你是使用 Microsoft 业务计划之一的中小型组织，请改为参阅以下资源：

- [保护 Office 365 和 Microsoft 365 商业版计划的十大方法](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 商业](https://docs.microsoft.com/microsoft-365/campaigns/) (包括针对 Microsoft 365 商业版的建议安全) 

对于使用企业计划的客户，Microsoft 建议你完成下表中列出的适用于你的服务计划的任务。 如果正在合并订阅，而不是购买 Microsoft 365 企业版计划，请注意以下事项：

- Microsoft 365 E3 包括企业移动性 + 安全性 (EMS) E3 和 Azure AD P1
- Microsoft 365 E5 包括 EMS E5 和 Azure AD P2

****

|步骤|任务|所有 Office 365 企业版计划|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1 |[在 MFA 中启用 Azure AD 多重 (身份验证) ](#1-enable-azure-ad-multi-factor-authentication-mfa)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2 |[威胁防护](#2-protect-against-threats)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[配置 Microsoft Defender for Office 365](#3-configure-microsoft-defender-for-office-365)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[配置 Microsoft Defender 标识](#4-configure-microsoft-defender-for-identity)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[打开 Microsoft 365 Defender](#5-turn-on-microsoft-365-defender)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[为手机和平板电脑配置 Intune 移动应用保护](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[为来宾配置 MFA 和条件访问，包括 Intune 应用保护](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[将电脑注册到设备管理中，并需要兼容电脑](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[针对云连接优化网络](#9-optimize-your-network-for-cloud-connectivity)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[培训用户](#10-train-users)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Microsoft Cloud App Security 入门](#11-get-started-with-microsoft-cloud-app-security)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[监视威胁并采取措施](#12-monitor-for-threats-and-take-action)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

开始之前，请查看 Microsoft [365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 安全中心中的 Microsoft 365 安全分数。 通过集中式仪表板，你可以监视并改进 Microsoft 365 标识、数据、应用、设备和基础结构的安全性。 您可以获得用于配置建议安全功能、执行与安全相关的任务 (例如查看报告) ，或者使用第三方应用程序或软件解决建议。 本文中推荐的任务将提高分数。

![Microsoft 安全分数屏幕截图](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1：在 MFA (启用 Azure AD 多重) 

为在家工作的员工提高安全性，唯一能做的就是打开 MFA。 如果还没有流程，请视其为紧急试点，并确保准备好支持人员来帮助遇到问题的员工。 由于你可能不会分发硬件安全设备，因此请使用 Windows Hello 生物识别以及智能手机身份验证应用（如 Microsoft Authenticator）。

正常情况下，Microsoft 建议在要求 MFA 之前，让用户在 14 天内注册其设备进行多重身份验证。 但是，如果你的员工突然在家工作，请继续操作，要求将 MFA 作为安全优先级，并准备好帮助需要它的用户。

应用这些策略只需几分钟，但准备在接下来几天内为用户提供支持。

****

|计划|建议|
|---|---|
|Microsoft 365 计划 (Azure AD P1 或 P2) |[在 Azure AD 中启用安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性默认值于用户和管理员的 MFA。|
|Microsoft 365 E3 (Azure AD P1) |使用[常用条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)配置以下策略： <br/>- [要求对管理员执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [要求对所有用户执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [阻止传统身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (Azure AD P2) |利用 Azure AD 标识保护，通过创建以下两个策略开始实施 Microsoft [推荐的一组条件访问和相关策略](./office-365-security/identity-access-policies.md)：<br/> - [要求在登录风险为“中等”或“高”时执行 MFA](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [阻止不支持新式身份验证的客户端](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [高风险用户必须更改密码](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2：防范威胁

所有 Microsoft 365 计划都包括各种威胁防护功能。 为这些功能提供保护只需几分钟。

- 反恶意软件保护
- 防止恶意 URL 和文件
- 防钓鱼保护
- 反垃圾邮件保护

请参阅 ["防止 Office 365](office-365-security/protect-against-threats.md) 中的威胁"，了解可以用作起始点的指南。

## <a name="3-configure-microsoft-defender-for-office-365"></a>3：为 Office 365 配置 Microsoft Defender

Microsoft 365 E5 和 Office 365 E5 中包含的 Microsoft Defender for Office 365 可保护你的组织免受电子邮件、链接 (URL) 和协作工具造成的恶意威胁。 这可能需要几个小时才能配置。

Microsoft Defender for Office 365：

- 使用智能系统实时保护组织免受未知电子邮件威胁，这些智能系统可检查附件和链接中是否有恶意内容。 这些自动化系统包括可靠的触发平台、启发和机器学习模型。
- 当用户协作和共享文件时，通过识别和阻止工作组网站和文档库中的恶意文件来保护组织。
- 应用机器学习模型和高级模拟检测算法来防范网络钓鱼攻击。

有关概述，包括计划摘要，请参阅适用于 Office [365](office-365-security/office-365-atp.md)的 Defender。

全局管理员可以配置以下保护：

- [设置安全链接策略](office-365-security/set-up-atp-safe-links-policies.md)
- [配置安全链接的全局设置](office-365-security/configure-global-settings-for-safe-links.md)
- [设置安全附件策略](office-365-security/set-up-atp-safe-attachments-policies.md)

你需要与 Exchange Online 管理员和 SharePoint Online 管理员一起为这些工作负载配置 Office 365 的 Defender：

- [适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](office-365-security/atp-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4：为标识配置 Microsoft Defender

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 是一种基于云的安全解决方案，可利用本地 Active Directory 信号来识别、检测和调查针对组织的高级威胁、已遭入侵标识和恶意内部行为。 接下来请关注这一点，因为它可保护你的地场和云基础结构，没有任何依赖关系或先决条件，并且可以提供直接的好处。

- 请参阅 [Microsoft Defender 标识快速入门](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) 以快速完成设置
- 观看视频 [：Microsoft Defender 标识简介](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- 查看 [Microsoft Defender 标识部署的三个阶段](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5：打开 Microsoft 365 Defender

现在，你已配置 Microsoft Defender for Office 365 和 Microsoft Defender for Identity，可以在一个仪表板中查看这些功能的组合信号。 [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 将警报、事件、自动调查和响应以及跨工作负载的高级搜寻 (Microsoft Defender for Identity、Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security) 汇集到 security.microsoft.com 上的 [单个窗格中](https://security.microsoft.com)。

![MTP 仪表板图示](../media/top-ten-security-remote-work-mtp-dashboard.png)

为 Office 365 服务配置一个或多个 Defender 后，打开 MTP。 新功能不断添加到 MTP;考虑选择接收预览功能。

- [了解有关 MTP 的更多信息](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [打开 MTP](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
- [选择加入预览功能](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6：为手机和平板电脑配置 Intune 移动应用保护

Microsoft Intune 移动应用 (MAM) 允许你在手机和平板电脑上管理和保护组织数据，而无需管理这些设备。 以下是相应的工作方式：

- 创建应用保护策略 (APP) ，用于确定设备上管理哪些应用以及允许哪些行为 (例如阻止将托管应用的数据复制到非托管应用) 。 你可以为每个平台创建一个策略， (iOS、Android) 。
- 创建应用保护策略后，通过创建 Azure AD 中的条件访问规则来强制执行这些策略，以需要批准的应用和应用数据保护。

应用保护策略包括许多设置。 幸运的是，无需了解每个设置并权衡选项。 Microsoft 通过推荐起始点，可以轻松应用设置配置。 使用 [应用保护策略的数据保护框架包括](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) 三个可供选择的级别。

更好的是，Microsoft 将此应用程序保护框架与一组条件访问和相关策略协调在一起，我们建议所有组织都用作起点。 如果你已使用本文中的指南实现了 MFA，那么你可以有一半了！

若要配置移动应用保护，请使用通用标识和设备访问 [策略中的指南](./office-365-security/identity-access-policies.md)：

 1. 使用 [应用应用数据保护策略指南](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) 创建适用于 iOS 和 Android 的策略。 对于基线 (建议使用级别 2) 增强的数据保护级别。
 2. 创建条件访问规则以 [要求批准的应用和应用保护](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)。

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7：为来宾配置 MFA 和条件访问，包括 Intune 移动应用保护

接下来，让我们确保你可以继续协作并与来宾协作。 如果你使用的是 Microsoft 365 E3 计划，并且为所有用户实施了 MFA，则你已设置。

如果你使用的是 Microsoft 365 E5 计划，并且正在利用 Azure Identity Protection 进行基于风险的 MFA，则需要对 (做一些调整，因为 Azure AD 标识保护不会扩展到来宾) ：

- 创建新的条件访问规则，以始终为来宾和外部用户要求 MFA。
- 更新基于风险的 MFA 条件访问规则以排除来宾和外部用户。

使用更新常见策略中的指南， [允许和保护来宾](./office-365-security/identity-access-policies-guest-access.md) 和外部访问，以了解来宾访问如何与 Azure AD 一起工作，并更新受影响的策略。

你创建的 Intune 移动应用保护策略以及要求批准的应用和应用保护的条件访问规则适用于来宾帐户，并且有助于保护你的组织数据。

> [!NOTE]
> 如果你已经将电脑注册到设备管理中以要求兼容电脑，你还需要从强制执行设备符合性的条件访问规则中排除来宾帐户。

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8：将电脑注册到设备管理中，并需要兼容电脑

有几种方法可注册员工的设备。 每个方法取决于设备的所有权（个人或公司）、设备类型（iOS、Windows、Android）和管理要求（重置、相关性、锁定）。 这可能需要一些时间才能分类。请参阅： [在 Microsoft Intune 中注册设备](https://docs.microsoft.com/mem/intune/enrollment/)。

入门的最快方法为设置 Windows [10 设备的自动注册](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

您还可以利用以下教程：

- [使用 Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [使用 Apple Business Manager 和 ABM (中的 Apple 公司设备注册) 在 Intune 中注册 iOS/iPadOS 设备](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

注册设备后，使用通用标识和设备访问策略 [中的指南](./office-365-security/identity-access-policies.md) 创建以下策略：

- [定义设备合规性策略](./office-365-security/identity-access-policies.md#define-device-compliance-policies) — Windows 10 的建议设置包括要求防病毒保护。 如果你有 Microsoft 365 E5，请使用 Microsoft Defender for Endpoint 监视员工设备的运行状况。 确保其他操作系统的合规性策略包括防病毒保护和终点保护软件。
- [需要合规电脑](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) — 这是 Azure AD 中强制执行设备合规性策略的条件访问规则。

只有一个组织可以管理设备，因此请确保从 Azure AD 中的条件访问规则中排除来宾帐户。 如果未从要求设备符合性的策略中排除来宾用户和外部用户，则这些策略将阻止这些用户。 有关详细信息，请参阅 [更新常见策略以允许和保护来宾和外部访问](./office-365-security/identity-access-policies-guest-access.md)。

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9：针对云连接优化网络

如果你正在快速让大多数员工在家工作，这种突然的连接模式切换会对企业网络基础结构产生显著影响。 许多网络在采用云服务之前进行了扩展和设计。 在许多情况下，网络可容忍远程工作者，但并非设计为由所有用户同时远程使用。

网络元素（如 VPN 控制器、中央网络出口设备 (例如代理和数据丢失防护设备) 、中央 Internet 带宽、回程 MPLS 电路、NAT 功能等）突然因使用它们的整个业务负载而变得极大压力。 最终结果是性能降低和工作效率不佳，加上适应在家工作的用户的用户体验不佳。

一些过去通过企业网络路由回流量提供的保护由用户访问的云应用提供。 如果你已阅读本文中的此步骤，则针对 Microsoft 365 服务和数据实施了一组复杂的云安全控件。 借助这些控件，你可以准备好将远程用户的流量直接路由到 Office 365。 如果仍然需要 VPN 链接才能访问其他应用程序，则可以通过实现拆分隧道来大幅提升性能和用户体验。 在组织中达成一致后，一个协调良好的网络团队可以在一天内完成此操作。

有关详细信息，请参阅 Docs 上的这些资源：

- [概述：使用 VPN 拆分隧道优化远程用户的连接](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [实现 Office 365 的 VPN 拆分隧道](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

有关此主题的最近博客文章：

- [如何快速优化远程员工流量&减少基础结构上的负载](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [安全专业人员和 IT 人员在当今独特的远程工作场景中实现新式安全控制的替代方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10：培训用户

培训用户可以节省用户和安全运营团队大量时间和沮丧。 被怀疑的用户不太可能打开可疑电子邮件中的附件或单击链接，并且他们更有可能避免可疑网站。

《百里学校 [网络安全宣传活动](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) 手册》为在组织内部建立强大的安全意识文化提供了出色的指导，包括培训用户识别网络钓鱼攻击。

Microsoft 365 提供以下资源来帮助通知组织用户：

****

|概念|资源|
|---|---|
|Microsoft 365|[可自定义的学习路径](https://docs.microsoft.com/office365/customlearning/) <p>这些资源可帮助您将针对组织中最终用户的培训整合在一起|
|Microsoft 365 安全中心|[学习模块：使用 Microsoft 365 的内置智能安全性保护组织](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>此模块使您能够描述 Microsoft 365 安全功能如何协同工作，并阐明这些安全功能的好处。|
|多重身份验证|[两步验证：什么是其他验证页面？](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>本文帮助最终用户了解什么是多重身份验证以及为什么在组织中使用多重身份验证。|
|

除了本指南之外，Microsoft 还建议你的用户执行本文中所述的操作：保护你的帐户和设备免受黑客和 [恶意软件的攻击](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 这些操作包括：

- 使用强密码
- 保护设备
- 在 Windows 10 和 Mac 电脑 (非托管设备启用) 

Microsoft 还建议用户采取以下文章中建议的操作来保护其个人电子邮件帐户：

- [帮助保护Outlook.com电子邮件帐户](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [使用两步验证保护 Gmail 帐户](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11：Microsoft Cloud App Security 入门

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) 提供了丰富的可见性、对数据旅行的控制以及复杂的分析，以识别和防御所有云服务中的网络威胁。 开始使用 Cloud App Security 后，将自动启用异常检测策略，但 Cloud App Security 的初始学习期为 7 天，在此期间并非所有异常检测警报都会引发。

现在开始使用 Cloud App Security。 稍后，你可以设置更复杂的监视和控件。

- [快速入门：云应用安全入门](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [获取即时行为分析和异常检测](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [详细了解 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [查看新特性和功能](https://docs.microsoft.com/cloud-app-security/release-notes)
- [请参阅基本设置说明](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12：监视威胁并采取措施

Microsoft 365 包括几种监视状态和采取适当操作的方法。 最佳起点是 Microsoft 365 安全中心 () ，你可以在这里查看组织的 Microsoft 安全分数以及需要你注意的任何警报或 [https://security.microsoft.com](https://security.microsoft.com) 实体[](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。

- [Microsoft 365 安全中心入门](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [监视和查看报表](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [请参阅 Microsoft 365 中的安全门户](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>后续步骤

恭喜！ 你已快速实现了一些最重要的安全保护，并且你的组织更加安全。 现在，你可以进一步使用威胁防护功能 (包括 Microsoft Defender for Endpoint) 、数据分类和保护功能以及保护管理帐户。 有关针对 Microsoft 365 的更深入、有条理的安全建议集，请参阅 [Microsoft 365 ](Microsoft-365-security-for-bdm.md)商业安全决策者 (BDM) 。

此外，请访问 Microsoft 的新安全中心[docs.microsoft.com/security。](https://docs.microsoft.com/security)
