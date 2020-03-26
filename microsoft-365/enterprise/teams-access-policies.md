---
title: 推荐的团队策略-Microsoft 365 企业版 |Microsoft 文档
description: 介绍有关如何保护团队通信和文件访问的 Microsoft 建议的策略。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 052edafa64f2704fb5a6df525b0ad5609ddc72b9
ms.sourcegitcommit: 8e8230ceab480a5f1506e31de828f04f5590a350
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2020
ms.locfileid: "42959190"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>保护团队聊天、组和文件的策略建议

本文介绍如何实施建议的标识和设备访问策略来保护团队聊天、组和内容（如文件和日历）。 本指南基于[通用标识和设备访问策略](identity-access-policies.md)构建，其中包含特定于团队的其他信息。 由于团队与我们的其他产品集成，因此请参阅[保护 SharePoint 网站和文件](sharepoint-file-access-policies.md)以及[保护电子邮件的策略建议](secure-email-recommended-policies.md)的策略建议。

这些建议基于三种不同的安全层级保护和针对团队的保护，这些团队可根据您需求的粒度进行应用：比较基准、敏感和高度管控。 您可以在[标识和设备访问配置](microsoft-365-policies-configurations.md)中了解有关这些安全层以及这些建议所引用的建议策略的详细信息。

本文中包含特定于团队部署的其他建议，以涵盖特定身份验证环境，包括组织外部的用户。 您需要遵循本指南，以获得完整的安全体验。

## <a name="getting-started-with-teams-before-other-dependent-services"></a>其他相关服务之前的团队入门

您无需启用相关服务即可开始使用 Microsoft 团队。 这些都是正常工作的。 但是，您确实需要准备好管理以下内容：

- Office 365 组
- SharePoint 团队网站
- OneDrive for Business
- 邮箱
- 流式传输视频和 Planner 计划（如果已启用这些服务）

## <a name="updating-common-policies-to-include-teams"></a>更新常见策略以包括团队

下图说明了用于保护团队中的聊天、组和内容的建议策略集。 铅笔图标指示需要重设的策略，以确保在分配云应用程序中包含团队和相关服务。

![演示如何在各种设备上使用 Microsoft 团队的图表。](../media/identity-access-ruleset-teams.png)

以下是要在团队的云应用程序分配中包括的相关服务：

- Microsoft Teams
- SharePoint Online 和 OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream （会议录制）
- Microsoft Planner （Planner 任务和规划数据）

此表列出了需要对其进行访问的策略，并链接到[常见标识和设备访问策略](identity-access-policies.md)中的每个策略，这些策略为所有 Office 应用程序提供了更宽的规则集。

|保护级别|策略|有关团队实施的详细信息|
|:---------------|:-------|:----------------|
|**Baseline**|[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|确保团队和相关服务包含在应用程序列表中。 团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。|
|        |[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在云应用的分配中包括团队和相关服务。|
|        |[高风险用户必须更改密码](identity-access-policies.md#high-risk-users-must-change-password)|强制团队用户在登录时更改其密码（如果为其帐户检测到高风险活动）。 确保团队和相关服务包含在应用程序列表中。|
|        |[定义应用保护策略](identity-access-policies.md#define-app-protection-policies)|确保团队和相关服务包含在应用程序列表中。 更新每个平台（iOS、Android、Windows）的策略。|
|        |[需要支持 Intune 应用保护策略的应用程序](identity-access-policies.md#require-apps-that-support-intune-app-protection-policies)|在此策略中包括团队和相关服务。|
|        |[定义设备合规性策略](identity-access-policies.md#define-device-compliance-policies)|在此策略中包括团队和相关服务。|
|        |[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在此策略中包括团队和相关服务。|
|**敏感**|[当登录风险为*低*、*中*或*高*时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。 在此策略中包括团队和相关服务。|
|         |[需要符合要求*的 pc 和*移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在此策略中包括团队和相关服务。|
|**高度管控**|[*始终*要求进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|无论用户标识如何，你的组织都将使用 MFA。 在此策略中包括团队和相关服务。
| | |

## <a name="teams-dependent-services-architecture"></a>团队相关服务体系结构

为了供参考，下图演示了服务团队所依赖的。 有关详细信息和其他说明，请参阅 microsoft[团队和 microsoft 365 中相关的工作效率服务（针对 IT 架构师](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects)）。

![该图显示了 SharePoint Online、OneDrive for Business 和 Exchange 上的团队相关性。](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>为团队启用来宾和外部访问

在 Azure AD 中，来宾和外部用户是相同的。 这两个用户的用户类型为 "来宾"。 来宾用户是 B2B 用户。 Microsoft 团队在应用程序中区分来宾用户和外部用户。 虽然了解每个用户在团队中的处理方式非常重要，但这两种类型的用户在 Azure AD 中都是 B2B 用户，而 B2B 用户的建议策略适用于这两种用户。 有关允许来宾访问的推荐策略，请参阅[允许来宾和外部 B2B 访问的策略](identity-access-policies-guest-access.md)。

### <a name="guest-access-in-teams"></a>团队中的来宾访问

除了企业或组织内部的用户的策略外，管理员还可以允许来宾访问允许在用户的用户的基础上为您的企业或组织外部的人员访问团队资源并与之交互内部人员，如组对话、聊天和会议等。 您可以通过以下链接了解有关来宾访问的详细信息：[团队来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>团队中的外部访问

外部访问有时会与来宾访问相混淆，因此请务必清楚，这两种非内部访问机制的实际差别很大。 虽然来宾访问是针对每个用户进行的（一次添加一个用户），当管理员启用外部访问时，您可以同时将外部域的所有用户添加到团队中。 但是，这些外部用户的访问和功能比通过来宾访问添加的个人更少。 外部访问用户可以通过团队与您的内部用户聊天。

有关外部访问的详细信息以及如何根据需要实现它，请参阅[管理 Microsoft 团队中的外部访问](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>团队策略

在上面列出的常见策略之外，有一些团队特定的策略可以和应配置为管理各种团队功能。

### <a name="teams-and-channels-policies"></a>团队和频道策略

团队和频道是 Microsoft 团队中的两个常用元素，有一些策略可用于控制用户在使用团队和频道时可以执行和不能执行的操作。 虽然您可以创建一个全局团队，但如果您的组织具有5000用户或更低的用户，那么您很可能会发现，具有更小的团队和渠道来实现特定目的，从而满足您的组织需求。

建议您更改默认策略或创建自定义策略，您可以通过以下链接了解有关管理策略的详细信息：[管理 Microsoft 团队中的团队策略](https://docs.microsoft.com/microsoftteams/teams-policies)。

### <a name="messaging-policies"></a>邮件策略

消息传递或聊天也可以通过默认全局策略或通过自定义策略进行管理，这可以帮助您的用户以适合您组织的方式与其他人进行通信。 可以在[团队中管理邮件策略](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)时查看此信息。

### <a name="meeting-policies"></a>会议策略

无需在团队会议周围规划和实施策略，即可完成团队的讨论。 会议是团队的基本组件，使用户可以一次正式地开会并演示给多个用户，以及共享与会议相关的内容。 在会议周围为组织设置适当的策略是非常重要的。

有关详细信息，请参阅[管理团队中的会议策略](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)。

### <a name="app-permission-policies"></a>应用权限策略

团队还允许您在不同位置使用应用程序，例如频道或个人聊天。 围绕可添加和使用哪些应用程序以及在何处维护内容丰富的环境（也是安全的）有必要的策略。

有关应用程序权限策略的详细信息，请参阅[管理 Microsoft 团队中的应用程序权限策略](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。

## <a name="next-steps"></a>后续步骤

[了解如何为 Exchange Online 启用条件访问](secure-email-recommended-policies.md)


