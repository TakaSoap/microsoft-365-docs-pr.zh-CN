---
title: 建议Teams策略 - Microsoft 365策略|Microsoft Docs
description: 介绍了 Microsoft 建议的策略，这些策略Teams通信和文件访问的安全。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 18044d469e90137ea14fa2dde9a6afe75e5dd0998d67e015e71d20b049ad30fb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53853221"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>用于保护聊天Teams组和文件的策略建议

本文介绍如何实施推荐的标识和设备访问策略来保护聊天Microsoft Teams组以及文件和日历等内容。 本指南基于[通用标识和设备访问](identity-access-policies.md)策略，并包含特定于Teams信息。 由于Teams集成了其他产品，因此另请参阅有关保护 SharePoint[网站](sharepoint-file-access-policies.md)和文件的策略建议和用于保护电子邮件[的策略建议](secure-email-recommended-policies.md)。

这些建议基于三种不同安全层和保护 Teams，可基于你的需求粒度应用这些层：基线、敏感和高度管控。 可以在标识和设备访问配置中了解有关这些安全层以及这些建议所引用 [的策略的更多信息](microsoft-365-policies-configurations.md)。

本文包含特定于 Teams部署的建议，以涵盖特定身份验证情况，包括针对组织外部的用户。 你需要遵循本指南，获得完整的安全体验。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>其他相关Teams服务之前入门

无需启用依赖服务，就无需开始使用Microsoft Teams。 这些服务将全部"正常工作"。 但是，您需要准备好管理以下与服务相关的元素：

- Microsoft 365 组
- SharePoint 团队网站
- OneDrive for Business
- Exchange 邮箱
- Stream videos and Planner plans (if these services are enabled) 

## <a name="updating-common-policies-to-include-teams"></a>更新常用策略以包括Teams

为了保护用户中的聊天、组Teams，下图说明了从通用标识和设备访问策略更新的策略。 对于要更新的每个策略，请确保Teams和依赖服务包含在云应用的分配中。

[![用于保护对服务及其依赖Teams的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

这些服务是分配云应用时要包括的Teams：

- Microsoft Teams
- Sharepoint 和 OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会议录制) 
- Microsoft Planner (Planner 任务和规划数据) 

此表列出了需要重新访问的策略以及指向通用标识和设备访问策略中每个策略的链接[](identity-access-policies.md)，这些策略具有针对所有 Office 应用程序设置更广泛的策略。

|保护级别|策略|有关实现Teams信息|
|---|---|---|
|**Baseline**|[当登录风险为中或高 *时需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|请确保Teams服务及其从属服务包含在应用列表中。 Teams需要考虑来宾访问和外部访问规则，您将在本文的稍后部分了解有关这些规则的更多内容。|
||[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|在Teams应用分配中包括相关服务和相关服务。|
||[高风险用户必须更改密码](identity-access-policies.md#high-risk-users-must-change-password)|强制Teams在登录时更改其密码（如果检测到其帐户存在高风险活动）。 请确保Teams服务及其从属服务包含在应用列表中。|
||[应用 APP 数据保护策略](identity-access-policies.md#apply-app-data-protection-policies)|请确保Teams服务及其从属服务包含在应用列表中。 针对 iOS、Android、 (的每个平台更新Windows) 。|
||[定义设备合规性策略](identity-access-policies.md#define-device-compliance-policies)|在此Teams包括服务及其依赖服务。|
||[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在此Teams包括服务及其依赖服务。|
|**敏感**|[登录风险低、中或高 *时需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams需要考虑来宾访问和外部访问规则，您将在本文的稍后部分了解有关这些规则的更多内容。 在此Teams包括服务及其依赖服务。|
||[要求兼容电脑 *和* 移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在此Teams包括服务及其依赖服务。|
|**高度管控**|[*始终* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|无论用户身份如何，组织都将使用 MFA。 在此Teams包括服务及其依赖服务。 |
|

## <a name="teams-dependent-services-architecture"></a>Teams服务体系结构

为了参考，下图说明了Teams的服务。 有关详细信息和图示，请参阅Microsoft Teams IT 架构师的 Microsoft 365[和相关生产力服务](../../solutions/productivity-illustrations.md)。

[![显示Teams、SharePoint、OneDrive for Business和Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[查看此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>来宾和外部访问Teams

Microsoft Teams定义以下访问类型：

- **来宾访问** 使用 Azure AD B2B 帐户作为来宾或外部用户，可以添加为团队成员，并且具有访问团队通信和资源的所有权限。

- **外部访问** 适用于没有 Azure AD B2B 帐户的外部用户。 外部访问可以包括邀请和参与通话、聊天和会议，但不包括团队成员身份和访问团队资源。

条件访问策略仅适用于 Teams，因为存在相应的 Azure AD B2B 帐户。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

有关允许使用 Azure AD B2B 帐户的来宾和外部用户访问的建议策略，请参阅允许来宾和外部 [B2B 帐户访问的策略](identity-access-policies-guest-access.md)。

### <a name="guest-access-in-teams"></a>Teams 中的来宾访问

除了针对企业或组织内部用户的策略之外，管理员还允许来宾访问以用户为基础，允许企业或组织外部的用户访问 Teams 资源，并与内部人员进行群组对话、聊天和会议等操作。

有关来宾访问以及如何实现它的信息，请参阅Teams[访问](/microsoftteams/guest-access)。

### <a name="external-access-in-teams"></a>外部访问Teams

外部访问有时与来宾访问混淆，因此必须明确这两种非内部访问机制是不同类型的访问。

外部访问是一种Teams域中的用户在外部域中查找、呼叫、聊天和设置Teams。 Teams管理员在组织级别配置外部访问。 有关详细信息，请参阅管理[Microsoft Teams 中的外部访问](/microsoftteams/manage-external-access)。

与通过来宾访问添加的用户相比，外部访问用户具有的访问和功能更少。 例如，外部访问用户可以与内部用户聊天，Teams但不能访问团队频道、文件或其他资源。

外部访问不使用 Azure AD B2B 用户帐户，因此不使用条件访问策略。

## <a name="teams-policies"></a>Teams策略

除了上面列出的常见策略之外，Teams特定策略，这些策略可以且应该配置为管理各种Teams功能。

### <a name="teams-and-channels-policies"></a>Teams和频道策略

Teams 频道和频道是 Microsoft Teams 中常用的两个元素，您可以使用一些策略来控制用户在使用团队和频道时可以执行和不能执行哪些操作。 虽然可以创建一个全局团队，但如果贵组织的用户数小于或小于 5000，则可能会发现，与组织需求一起，让较小的团队和频道用于特定用途可能会很有帮助。

建议更改默认策略或创建自定义策略，你可以在此链接中了解有关管理策略[Microsoft Teams。](/microsoftteams/teams-policies)

### <a name="messaging-policies"></a>消息传递策略

消息或聊天也可通过默认全局策略或自定义策略进行管理，这可帮助用户以适合贵组织的方式相互通信。 可以在管理邮件策略中[查看](/microsoftteams/messaging-policies-in-teams)此信息Teams。

### <a name="meeting-policies"></a>会议策略

如果不规划和Teams有关会议的策略，将无法完成Teams讨论。 会议是会议的重要Teams，允许用户一次正式开会并呈现给许多用户，并共享与会议相关的内容。 为组织围绕会议设置正确的策略至关重要。

有关详细信息，请参阅管理[会议策略Teams。](/microsoftteams/meeting-policies-in-teams)

### <a name="app-permission-policies"></a>应用权限策略

Teams还允许你在各种位置（如频道或个人聊天）使用应用。 对于维护同样安全的内容丰富的环境来说，制定有关可添加和使用的应用的策略以及在何处添加策略至关重要。

有关应用程序权限策略的更多阅读，请查看管理[应用程序权限策略Microsoft Teams。](/microsoftteams/teams-app-permission-policies)

## <a name="next-steps"></a>后续步骤

![步骤 4：云Microsoft 365策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为：配置条件访问策略：

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)