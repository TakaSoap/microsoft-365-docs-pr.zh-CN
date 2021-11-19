---
title: 试用 Microsoft Defender for Cloud Apps with Microsoft 365 Defender
description: 设置你的Microsoft 365 Defender试验实验室或试验环境，以测试并体验旨在保护设备、标识、数据和应用程序的安全解决方案。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4b8293be5123ac57aefa3f8c5a5212e9fc8f1e95
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111047"
---
# <a name="pilot-microsoft-defender-for-cloud-apps-with-microsoft-365-defender"></a>试用 Microsoft Defender for Cloud Apps with Microsoft 365 Defender


**适用于：**
- Microsoft 365 Defender

本文是设置 Microsoft Defender for Cloud Apps 评估环境过程中的第 3 步（第 [3](eval-defender-mcas-overview.md) 步）。 有关此过程详细信息，请参阅 [概述文章](eval-defender-mcas-overview.md)。

使用以下步骤为 Microsoft Defender for Cloud Apps 设置和配置试点。


![试用 Microsoft Defender for Cloud Apps 的步骤。](../../media/defender/m365-defender-mcas-pilot-steps.png)

- 步骤 1. [创建试点组 — 将试点部署的范围缩小到某些用户组](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [步骤 2.配置保护 — 条件访问应用控制](#step-2-configure-protection--conditional-access-app-control)
- [步骤 3.试用功能 - 演练用于保护环境的教程](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>步骤 1. 创建试点组 — 将试点部署的范围缩小到某些用户组

Microsoft Defender for Cloud Apps 使你能够确定你的部署范围。 通过作用域，可以选择要监视的应用或排除在监视之外的某些用户组。 可以包括或排除用户组。 若要确定试点部署的范围，请参阅 [作用域部署](/cloud-app-security/scoped-deployment)。


## <a name="step-2-configure-protection--conditional-access-app-control"></a>步骤 2. 配置保护 — 条件访问应用控制

可以配置的最强大保护之一是条件访问应用控制。 这需要与 Azure Active Directory (Azure AD) 。 它允许你将条件访问策略（包括相关策略 (如要求正常运行的设备) 已批准的云应用。 

使用 Microsoft Defender for Cloud Apps 管理 SaaS 应用的第一步是发现它们，然后将它们添加到你的 Azure AD 租户。 如果需要发现帮助，请参阅 [发现和管理网络中 SaaS 应用](/cloud-app-security/tutorial-shadow-it)。 在发现应用后，将其添加到你的Azure AD[租户。](/azure/active-directory/manage-apps/add-application-portal)

可以通过执行以下操作开始管理这些操作：

- 首先，在Azure AD，创建新的条件访问策略，并配置为"使用条件访问应用控制"。 这会将请求重定向到 Defender for Cloud Apps。 你可以创建一个策略，并添加所有 SaaS 应用到此策略。
- 接下来，在 Defender for Cloud Apps 中，创建会话策略。 为要应用的每个控件创建一个策略。

有关详细信息，包括受支持的应用和客户端，请参阅使用 [Microsoft Defender for Cloud Apps 条件访问应用控制保护应用](/cloud-app-security/proxy-intro-aad)。 

有关示例策略，请参阅适用于 SaaS 应用的推荐 [Microsoft Defender 云应用策略](../office-365-security/mcas-saas-access-policies.md)。 这些策略基于一组 [常见标识](../office-365-security/microsoft-365-policies-configurations.md) 和设备访问策略，这些策略建议作为所有客户的起点。 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>步骤 3. 试用功能 - 演练用于保护环境的教程 

Microsoft Defender for Cloud Apps 文档包括一系列教程，可帮助你发现风险和保护你的环境。 

试用适用于云应用的 Defender 教程：

- [检测可疑用户活动](/cloud-app-security/tutorial-suspicious-activity)
- [调查有风险的用户](/cloud-app-security/tutorial-ueba)
- [调查有风险的 OAuth 应用](/cloud-app-security/investigate-risky-oauth)
- [发现和保护敏感信息](/cloud-app-security/tutorial-dlp)
- [实时保护组织的任何应用](/cloud-app-security/tutorial-proxy)
- [阻止下载敏感信息](/cloud-app-security/use-case-proxy-block-session-aad)
- [使用管理员隔离保护文件](/cloud-app-security/use-case-admin-quarantine)
- [在有风险的操作时要求执行逐步身份验证](/cloud-app-security/tutorial-step-up-authentication)

有关 Microsoft Defender for Cloud Apps 数据中的高级搜寻功能详细信息，请参阅 [视频](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)。

## <a name="next-steps"></a>后续步骤

[在试点环境中使用Microsoft 365 Defender和响应](eval-defender-investigate-respond.md)

返回到评估 Microsoft [Defender for Cloud Apps 的概述](eval-defender-mcas-overview.md)

返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)
