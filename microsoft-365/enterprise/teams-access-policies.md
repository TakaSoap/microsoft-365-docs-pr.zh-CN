---
title: 推荐的团队策略-适用于企业的 Microsoft 365 |Microsoft 文档
description: 介绍有关如何保护团队通信和文件访问的 Microsoft 建议的策略。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/18/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 570ef098a3989bf42d641b78e325414350b8e5a5
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132108"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>保护团队聊天、组和文件的策略建议

本文介绍如何实现建议的标识和设备访问策略，以保护 Microsoft 团队聊天、组和内容（如文件和日历）。 本指南基于 [通用标识和设备访问策略](identity-access-policies.md)构建，其中包含特定于团队的其他信息。 由于团队与我们的其他产品集成，因此请参阅 [保护 SharePoint 网站和文件](sharepoint-file-access-policies.md) 以及 [保护电子邮件的策略建议](secure-email-recommended-policies.md)的策略建议。

这些建议基于三种不同的安全层级保护和针对团队的保护，这些团队可根据您需求的粒度进行应用：比较基准、敏感和高度管控。 您可以在 [标识和设备访问配置](microsoft-365-policies-configurations.md)中了解有关这些安全层以及这些建议所引用的建议策略的详细信息。

本文中包含特定于团队部署的其他建议，以涵盖特定身份验证环境，包括组织外部的用户。 您需要遵循本指南，以获得完整的安全体验。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>其他相关服务之前的团队入门

您无需启用相关服务即可开始使用 Microsoft 团队。 这些都是 "只是工作"。 但是，您确实需要准备好管理以下内容：

- Microsoft 365 组
- SharePoint 团队网站
- OneDrive for Business
- Exchange 邮箱
- 如果启用这些服务，则 Stream 视频和 Planner 计划 () 

## <a name="updating-common-policies-to-include-teams"></a>更新常见策略以包括团队

若要保护团队中的聊天、组和内容，下图说明了要从公共标识和设备访问策略中更新的策略。 对于要更新的每个策略，请确保在云应用的分配中包含团队和相关服务。

[![用于保护对团队及其依赖服务的访问权限的策略更新的摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[查看此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

以下是要在团队的云应用程序分配中包括的相关服务：

- Microsoft Teams
- Sharepoint 和 OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (会议录制) 
- Microsoft Planner (Planner 任务和规划数据) 

此表列出了需要对其进行访问的策略，以及在 [常见标识和设备访问策略](identity-access-policies.md)中的每个策略的链接，这些策略为所有 Office 应用程序设置了更宽的策略。

|保护级别|策略|有关团队实施的详细信息|
|:---------------|:-------|:----------------|
|**Baseline**|[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|确保团队和相关服务包含在应用程序列表中。 团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。|
|        |[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在云应用的分配中包括团队和相关服务。|
|        |[高风险用户必须更改密码](identity-access-policies.md#high-risk-users-must-change-password)|强制团队用户在登录时更改其密码（如果为其帐户检测到高风险活动）。 确保团队和相关服务包含在应用程序列表中。|
|        |[应用应用数据保护策略](identity-access-policies.md#apply-app-data-protection-policies)|确保团队和相关服务包含在应用程序列表中。 为每个平台 (iOS、Android、Windows) 更新策略。|
|        |[需要经批准的应用和应用保护](identity-access-policies.md#require-approved-apps-and-app-protection)|在此策略中包括团队和相关服务。|
|        |[定义设备合规性策略](identity-access-policies.md#define-device-compliance-policies)|在此策略中包括团队和相关服务。|
|        |[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在此策略中包括团队和相关服务。|
|**敏感**|[当登录风险为*低*、*中*或*高*时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。 在此策略中包括团队和相关服务。|
|         |[需要符合要求 *的 pc 和* 移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在此策略中包括团队和相关服务。|
|**高度管控**|[*始终* 要求进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|无论用户标识如何，你的组织都将使用 MFA。 在此策略中包括团队和相关服务。 |
| | |

## <a name="teams-dependent-services-architecture"></a>团队相关服务体系结构

为了供参考，下图演示了服务团队所依赖的。 有关详细信息和其他说明，请参阅 microsoft [团队和 microsoft 365 中相关的工作效率服务（针对 IT 架构师](../solutions/productivity-illustrations.md)）。

[![显示 SharePoint、OneDrive for Business 和 Exchange 上的团队相关性的图表](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[查看此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>团队的来宾访问和外部访问

Microsoft 团队定义了以下内容：

- **来宾访问** 使用可作为团队成员添加的来宾或外部用户的 AZURE AD B2B 帐户，并拥有对团队的通信和资源的所有具有独特权限访问权限。

- **外部访问** 适用于没有 AZURE AD B2B 帐户的外部用户。 外部访问可以包括邀请和参与呼叫、聊天和会议，但不包括团队成员资格和对团队资源的访问权限。

条件访问策略仅适用于团队中的来宾访问，因为存在相应的 Azure AD B2B 帐户。

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both. 

--> 

有关使用 Azure AD B2B 帐户为来宾和外部用户授予访问权限的建议策略，请参阅 [允许来宾和外部 B2B 帐户访问的策略](identity-access-policies-guest-access.md)。

### <a name="guest-access-in-teams"></a>Teams 中的来宾访问

除了企业或组织内部用户的策略之外，管理员还可以启用来宾访问以允许在用户的用户的基础上访问团队资源并与内部人员进行交互（如组对话、聊天和会议），从而获得人员。 

有关来宾访问和如何实施来宾的详细信息，请参阅  [团队来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)。

### <a name="external-access-in-teams"></a>团队中的外部访问

外部访问有时会与来宾访问相混淆，因此请务必清楚，这两种非内部访问机制的实际差别很大。 

通过外部访问，团队用户可以从整个外部域中查找、呼叫、聊天和设置与团队用户的会议。 团队管理员在组织级别配置外部访问。 有关详细信息，请参阅 [在 Microsoft 团队中管理外部访问](https://docs.microsoft.com/microsoftteams/manage-external-access)。

外部访问用户的访问权限和功能比通过来宾访问添加的个人更少。 例如，外部访问用户可以与具有团队的内部用户聊天，但无法访问团队频道、文件或其他资源。

外部访问不使用 Azure AD B2B 用户帐户，因此不使用条件访问策略。 

## <a name="teams-policies"></a>团队策略

在上面列出的常见策略之外，有一些团队特定的策略可以和应配置为管理各种团队功能。

### <a name="teams-and-channels-policies"></a>团队和频道策略

团队和频道是 Microsoft 团队中的两个常用元素，有一些策略可用于控制用户在使用团队和频道时可以执行和不能执行的操作。 虽然您可以创建一个全局团队，但如果您的组织具有5000用户或更低的用户，那么您很可能会发现，具有更小的团队和渠道来实现特定目的，从而满足您的组织需求。

建议您更改默认策略或创建自定义策略，您可以通过以下链接了解有关管理策略的详细信息： [管理 Microsoft 团队中的团队策略](https://docs.microsoft.com/microsoftteams/teams-policies)。

### <a name="messaging-policies"></a>邮件策略

消息传递或聊天也可以通过默认全局策略或通过自定义策略进行管理，这可以帮助您的用户以适合您组织的方式与其他人进行通信。 可以在 [团队中管理邮件策略](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)时查看此信息。

### <a name="meeting-policies"></a>会议策略

无需在团队会议周围规划和实施策略，即可完成团队的讨论。 会议是团队的基本组件，使用户可以一次正式地开会并演示给多个用户，以及共享与会议相关的内容。 在会议周围为组织设置适当的策略是非常重要的。

有关详细信息，请参阅 [管理团队中的会议策略](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) 。

### <a name="app-permission-policies"></a>应用权限策略

团队还允许您在不同位置使用应用程序，例如频道或个人聊天。 围绕可添加和使用哪些应用程序以及在何处维护内容丰富的环境（也是安全的）有必要的策略。

有关应用程序权限策略的详细信息，请参阅 [管理 Microsoft 团队中的应用程序权限策略](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。

## <a name="next-steps"></a>后续步骤

![步骤4： Microsoft 365 云应用的策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为以下项配置条件访问策略：

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

