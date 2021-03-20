---
title: 推荐的 Teams 策略 - Microsoft 365 企业版 |Microsoft Docs
description: 介绍了 Microsoft 建议中有关如何保护 Teams 通信和文件访问的策略。
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
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916414"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>用于保护 Teams 聊天、组和文件的策略建议

本文介绍如何实施推荐的标识和设备访问策略来保护 Microsoft Teams 聊天、组以及文件和日历等内容。 本指南基于 [通用标识和设备访问](identity-access-policies.md)策略，并包含特定于 Teams 的其他信息。 由于 Teams 与其他产品集成，因此另请参阅有关保护 [SharePoint](sharepoint-file-access-policies.md) 网站和文件的策略建议和用于保护电子邮件 [的策略建议](secure-email-recommended-policies.md)。

这些建议基于针对 Teams 的三种不同安全和保护层，可基于你的需求粒度应用这些层：基线、敏感和高度管控。 可以在标识和设备访问配置中了解有关这些安全层以及这些建议所引用 [的策略的更多信息](microsoft-365-policies-configurations.md)。

本文包含特定于 Teams 部署的更多建议，以涵盖特定身份验证情况，包括针对组织外部的用户。 你需要遵循本指南，获得完整的安全体验。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>在其他相关服务之前开始使用 Teams

无需启用相关服务，就无需开始使用 Microsoft Teams。 这些服务将全部"正常工作"。 但是，您需要准备好管理以下与服务相关的元素：

- Microsoft 365 组
- SharePoint 团队网站
- OneDrive for Business
- Exchange 邮箱
- Stream videos and Planner plans (if these services are enabled) 

## <a name="updating-common-policies-to-include-teams"></a>更新常见策略以包括 Teams

为了在 Teams 中保护聊天、组和内容，下图说明了从通用标识和设备访问策略更新的策略。 对于要更新的每个策略，请确保 Teams 和依赖服务包含在云应用的分配中。

[![用于保护对 Teams 及其从属服务的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

这些服务是分配 Teams 云应用时要包括的从属服务：

- Microsoft Teams
- Sharepoint 和 OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会议录制) 
- Microsoft Planner (Planner 任务和规划数据) 

此表列出了需要重新访问的策略以及指向通用标识和设备访问策略中每个策略的链接[](identity-access-policies.md)，这些策略具有针对所有 Office 应用程序的更大策略集。

|保护级别|策略|有关 Teams 实施的进一步信息|
|---|---|---|
|**Baseline**|[当登录风险为中或高 *时需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|请确保 Teams 和从属服务包含在应用列表中。 Teams 也有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。|
||[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|分配云应用时包括 Teams 和从属服务。|
||[高风险用户必须更改密码](identity-access-policies.md#high-risk-users-must-change-password)|如果为 Teams 用户的帐户检测到高风险活动，则强制 Teams 用户在登录时更改其密码。 请确保 Teams 和从属服务包含在应用列表中。|
||[应用 APP 数据保护策略](identity-access-policies.md#apply-app-data-protection-policies)|请确保 Teams 和从属服务包含在应用列表中。 针对 iOS、Android、Windows () 的每个平台更新) 。|
||[定义设备合规性策略](identity-access-policies.md#define-device-compliance-policies)|在此策略中包括 Teams 和从属服务。|
||[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在此策略中包括 Teams 和从属服务。|
|**敏感**|[登录风险低、中或高 *时需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams 也有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。 在此策略中包括 Teams 和从属服务。|
||[要求兼容电脑 *和* 移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在此策略中包括 Teams 和从属服务。|
|**高度管控**|[*始终* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|无论用户身份如何，组织都将使用 MFA。 在此策略中包括 Teams 和从属服务。 |
|

## <a name="teams-dependent-services-architecture"></a>Teams 相关服务体系结构

为了参考，下图说明了 Teams 所依赖的服务。 有关详细信息和图示，请参阅适用于 IT 架构师的 Microsoft Teams 和 [Microsoft 365 中的相关生产力服务](../../solutions/productivity-illustrations.md)。

[![显示 SharePoint、OneDrive for Business 和 Exchange 上的 Teams 依赖项的关系图](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[查看此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Teams 的来宾和外部访问

Microsoft Teams 定义以下访问类型：

- **来宾访问** 使用 Azure AD B2B 帐户作为来宾或外部用户，可以添加为团队成员，并且具有访问团队通信和资源的所有权限。

- **外部访问** 适用于没有 Azure AD B2B 帐户的外部用户。 外部访问可以包括邀请和参与通话、聊天和会议，但不包括团队成员身份和访问团队资源。

条件访问策略仅适用于 Teams 中的来宾访问，因为存在相应的 Azure AD B2B 帐户。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

有关允许使用 Azure AD B2B 帐户的来宾和外部用户访问的建议策略，请参阅允许来宾和外部 [B2B 帐户访问的策略](identity-access-policies-guest-access.md)。

### <a name="guest-access-in-teams"></a>Teams 中的来宾访问

除了针对企业或组织内部用户的策略之外，管理员还允许来宾访问以用户为基础，允许企业或组织外部人员访问 Teams 资源，并与内部人员进行群组对话、聊天和会议等操作。

有关来宾访问以及如何实现它的信息，请参阅  [Teams 来宾访问](/microsoftteams/guest-access)。

### <a name="external-access-in-teams"></a>Teams 中的外部访问

外部访问有时与来宾访问混淆，因此必须明确这两种非内部访问机制是不同类型的访问。

外部访问是整个外部域中的 Teams 用户在 Teams 中查找、呼叫、聊天和设置与用户的会议的一种方式。 Teams 管理员在组织级别配置外部访问。 有关详细信息，请参阅在 [Microsoft Teams 中管理外部访问](/microsoftteams/manage-external-access)。

与通过来宾访问添加的用户相比，外部访问用户具有的访问和功能更少。 例如，外部访问用户可以使用 Teams 与内部用户聊天，但不能访问团队频道、文件或其他资源。

外部访问不使用 Azure AD B2B 用户帐户，因此不使用条件访问策略。

## <a name="teams-policies"></a>Teams 策略

除了上面列出的常见策略之外，还可以且应该配置特定于 Teams 的策略来管理各种 Teams 功能。

### <a name="teams-and-channels-policies"></a>Teams 和频道策略

Teams 和频道是 Microsoft Teams 中常用的两个元素，你可以制定一些策略来控制用户在使用团队和频道时可以执行和不能执行哪些操作。 虽然可以创建一个全局团队，但如果贵组织的用户数小于或小于 5000，则可能会发现，与组织需求一起，让较小的团队和频道用于特定用途可能会很有帮助。

建议更改默认策略或创建自定义策略，你可以在此链接中了解有关管理策略的更多信息： [在 Microsoft Teams](/microsoftteams/teams-policies)中管理团队策略。

### <a name="messaging-policies"></a>邮件策略

消息或聊天也可通过默认全局策略或自定义策略进行管理，这可帮助用户以适合贵组织的方式相互通信。 可以在管理 Teams 中的消息传递 [策略中查看此信息](/microsoftteams/messaging-policies-in-teams)。

### <a name="meeting-policies"></a>会议策略

如果不规划和实施有关 Teams 会议的策略，就无法完成有关 Teams 的讨论。 会议是 Teams 的一个基本组件，允许用户一次正式开会并呈现给许多用户，并共享与会议相关的内容。 为组织围绕会议设置正确的策略至关重要。

有关详细信息，请参阅在 [Teams 中管理会议策略](/microsoftteams/meeting-policies-in-teams)。

### <a name="app-permission-policies"></a>应用程序权限策略

Teams 还允许你在各种位置（如频道或个人聊天）使用应用。 对于维护同样安全的内容丰富的环境来说，制定有关可添加和使用的应用的策略以及在何处添加策略至关重要。

有关应用权限策略的更多阅读，请查看在 [Microsoft Teams 中管理应用权限策略](/microsoftteams/teams-app-permission-policies)。

## <a name="next-steps"></a>后续步骤

![步骤 4：Microsoft 365 云应用策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为：配置条件访问策略：

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)