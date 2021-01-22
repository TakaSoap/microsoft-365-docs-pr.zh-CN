---
title: 推荐的 Teams 策略 - Microsoft 365 企业版|Microsoft Docs
description: 介绍了 Microsoft 有关如何保护 Teams 通信和文件访问的策略。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 7724ef76d905cdbaf48f3122d0df7ef28d0b8385
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931622"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>用于保护 Teams 聊天、组和文件的策略建议

本文介绍如何实施推荐的标识和设备访问策略来保护 Microsoft Teams 聊天、组以及文件和日历等内容。 本指南基于通用 [标识和设备访问策略](identity-access-policies.md)，以及特定于 Teams 的其他信息。 由于 Teams 与其他产品集成，因此还请参阅有关保护 [SharePoint](sharepoint-file-access-policies.md) 网站和文件的策略建议，以及用于保护电子邮件 [的策略建议](secure-email-recommended-policies.md)。

这些建议基于针对 Teams 的三个不同安全和保护层，可基于你的需求粒度应用这些层：基线、敏感和高度管控。 可以在标识和设备访问配置中了解有关这些安全层以及这些建议所引用 [的建议策略的更多信息](microsoft-365-policies-configurations.md)。

本文包含特定于 Teams 部署的其他建议，以涵盖特定身份验证情况，包括针对组织外部的用户。 你将需要遵循本指南，获得完整的安全体验。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>在其他相关服务之前开始使用 Teams

无需启用相关服务，就无需开始使用 Microsoft Teams。 这些都将"正常工作"。 但是，您需要准备好管理以下各项：

- Microsoft 365 组
- SharePoint 团队网站
- OneDrive for Business
- Exchange 邮箱
- 如果启用了这些服务， (流视频和 Planner 计划) 

## <a name="updating-common-policies-to-include-teams"></a>更新常见策略以包含 Teams

为了保护 Teams 中的聊天、组和内容，下图说明了从通用标识和设备访问策略更新的策略。 对于要更新的每个策略，请确保 Teams 和依赖服务包含在云应用的分配中。

[![用于保护对 Teams 及其从属服务的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[查看此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

这些是分配 Teams 云应用时要包括的依赖服务：

- Microsoft Teams
- Sharepoint 和 OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会议录制) 
- Microsoft Planner (Planner 任务和规划) 

此表列出了需要重新访问的策略以及指向通用标识和设备访问策略中每个策略的链接[](identity-access-policies.md)，这些策略具有针对所有 Office 应用程序的较宽策略集。

|保护级别|策略|有关 Teams 实施的进一步信息|
|---|---|---|
|**Baseline**|[当登录风险为中或高 *时需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|请确保 Teams 和从属服务包含在应用列表中。 Teams 还有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。|
||[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在分配云应用时包括 Teams 和从属服务。|
||[高风险用户必须更改密码](identity-access-policies.md#high-risk-users-must-change-password)|如果检测到其帐户存在高风险活动，则强制 Teams 用户在登录时更改其密码。 请确保 Teams 和从属服务包含在应用列表中。|
||[应用 APP 数据保护策略](identity-access-policies.md#apply-app-data-protection-policies)|请确保 Teams 和从属服务包含在应用列表中。 为 iOS、 (Android、Windows) 的每个平台更新) 。|
||[定义设备合规性策略](identity-access-policies.md#define-device-compliance-policies)|在此策略中包括 Teams 和依赖服务。|
||[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在此策略中包括 Teams 和从属服务。|
|**敏感**|[当登录风险较低、中等或高时需要MFA ](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams 还有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。 在此策略中包括 Teams 和依赖服务。|
||[要求 *兼容电脑和* 移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在此策略中包括 Teams 和依赖服务。|
|**高度管控**|[*始终* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|无论用户标识如何，组织都将使用 MFA。 在此策略中包括 Teams 和从属服务。 |
|

## <a name="teams-dependent-services-architecture"></a>与 Teams 相关的服务体系结构

为了参考，下图说明了 Teams 所依赖的服务。 有关详细信息和其他插图，请参阅适用于 IT 架构师的 [Microsoft 365 中的 Microsoft Teams 和相关生产力服务](../../solutions/productivity-illustrations.md)。

[![显示 SharePoint、OneDrive for Business 和 Exchange 上的 Teams 依赖项的关系图](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[查看此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Teams 的来宾和外部访问

Microsoft Teams 定义以下内容：

- **来宾访问** 使用 Azure AD B2B 帐户作为来宾或外部用户，可添加为团队成员，并拥有访问团队通信和资源的所有权限。

- **外部访问** 适用于没有 Azure AD B2B 帐户的外部用户。 外部访问可以包括邀请和参与通话、聊天和会议，但不包括团队成员身份和访问团队资源。

条件访问策略仅适用于 Teams 中的来宾访问，因为存在相应的 Azure AD B2B 帐户。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

有关允许使用 Azure AD B2B 帐户的来宾和外部用户访问的建议策略，请参阅用于允许来宾和外部 [B2B 帐户访问的策略](identity-access-policies-guest-access.md)。

### <a name="guest-access-in-teams"></a>Teams 中的来宾访问

除了针对企业或组织内部用户的策略外，管理员还可能会启用来宾访问，以允许企业或组织外部的用户以用户为基础访问 Teams 资源，并与内部人员进行群组对话、聊天和会议等操作。

有关来宾访问以及如何实现它的信息，请参阅  [Teams 来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)。

### <a name="external-access-in-teams"></a>Teams 中的外部访问

外部访问有时与来宾访问混淆，因此必须明确这两个非内部访问机制实际上截然不同。

外部访问是一种供整个外部域中的 Teams 用户在 Teams 中查找、呼叫、聊天和设置与用户的会议的方法。 Teams 管理员在组织级别配置外部访问。 有关详细信息，请参阅"在[Microsoft Teams 中管理外部访问"。](https://docs.microsoft.com/microsoftteams/manage-external-access)

与通过来宾访问添加的用户相比，外部访问用户具有的访问和功能更少。 例如，外部访问用户可以使用 Teams 与内部用户聊天，但无法访问团队频道、文件或其他资源。

外部访问不使用 Azure AD B2B 用户帐户，因此不使用条件访问策略。

## <a name="teams-policies"></a>Teams 策略

除了上面列出的常见策略外，还可以且应该将 Teams 特定的策略配置为管理各种 Teams 功能。

### <a name="teams-and-channels-policies"></a>Teams 和频道策略

Teams 和频道是 Microsoft Teams 中常用的两个元素，你可以制定一些策略来控制用户在使用团队和频道时可以和不能执行哪些操作。 虽然可以创建全局团队，但如果贵组织的用户数小于或小于 5000，则可能会发现在组织需求内，将较小的团队和频道用于特定用途会很有帮助。

建议更改默认策略或创建自定义策略，你可以在此链接中了解有关管理策略的更多信息：在 Microsoft Teams 中 [管理团队策略](https://docs.microsoft.com/microsoftteams/teams-policies)。

### <a name="messaging-policies"></a>邮件策略

消息或聊天也可通过默认全局策略或自定义策略进行管理，这可帮助用户以适合组织的方式相互通信。 可以在 Teams 中管理 [邮件策略中查看此信息](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)。

### <a name="meeting-policies"></a>会议策略

如果不规划和实施有关 Teams 会议的策略，就无法完成有关 Teams 的讨论。 会议是 Teams 的一个基本组件，允许用户一次正式开会并呈现给许多用户，并共享与会议相关的内容。 为组织围绕会议设置正确的策略至关重要。

有关详细信息， [请查看 Teams 中的](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) "管理会议策略"。

### <a name="app-permission-policies"></a>应用权限策略

Teams 还允许你在各种位置（如频道或个人聊天）使用应用。 制定有关可以添加和使用的应用的策略以及在何处，对于维护同样安全的丰富内容环境至关重要。

有关应用权限策略的更多阅读，请查看[Microsoft Teams 中的"管理应用权限策略"。](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)

## <a name="next-steps"></a>后续步骤

![步骤 4：Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为：

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
