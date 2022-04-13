---
title: 查看和管理有风险的用户
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，了解如何查看和管理有风险的用户。
ms.openlocfilehash: 0b7567404b909927a80b69184299baae131f8eb7
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824259"
---
# <a name="view-and-manage-risky-users"></a>查看和管理有风险的用户

Microsoft 每天收集和分析数万亿个用户登录信号。 这些信号用于帮助构建良好的用户登录行为模式并识别潜在的有风险的登录尝试。 Azure Active Directory (Azure AD) 标识保护使用这些信号来查看用户登录尝试，并在存在可疑活动时采取措施。

Microsoft 365 Lighthouse通过在所有托管租户中提供风险用户的单一视图来帮助管理Azure AD标识保护检测到的风险。 可以通过重置其密码或阻止他们登录到其Microsoft 365帐户来快速保护有风险的用户。 还可以查看见解，以便更好地了解用户的风险并确定后续步骤。

Azure AD标识保护可识别多种类型的风险，包括：

- 泄露的凭据
- 匿名 IP 使用
- 非典型旅行
- 从受感染的设备登录
- 使用可疑活动从 IP 地址登录
- 从陌生位置登录

## <a name="before-you-begin"></a>准备工作

必须满足以下条件，然后用户才能出现在有风险的用户列表中：

- 客户租户必须具有每个用户的Azure AD Premium许可证。 有关哪些许可证支持Azure AD标识保护的详细信息，[请参阅什么是标识保护？](/azure/active-directory/identity-protection/overview-identity-protection)

- 客户租户必须在Microsoft 365 Lighthouse中处于活动状态。 若要确定租户是否处于活动状态，请[参阅Microsoft 365 Lighthouse租户页面概述](m365-lighthouse-tenant-list-overview.md)。

## <a name="review-detected-risks-and-take-action"></a>查看检测到的风险并采取措施

在Azure AD标识保护中，风险检测包括与Azure AD中的用户帐户相关的任何已识别的可疑操作。

1. 在 Lighthouse 的左侧导航窗格中，选择 **“用户**”。

2. 选择 **“有风险的用户** ”选项卡。

3. 查看列表中风险状态为 **“有风险**”的用户。

4. 选择 **“查看风险检测** ”以获取有关每个用户检测到的风险的详细信息。 有关风险类型和检测的详细信息，[请参阅什么是风险？](/azure/active-directory/identity-protection/concept-identity-protection-risks)

5. 对于每个用户，请评估风险检测，并根据需要选择以下操作之一：

    - 重置密码 - 更改或重置用户密码。

    - 阻止登录 - 阻止任何人以此用户身份登录。

    - 确认用户已泄露 - 将风险状态设置为确认已泄露。

    - 消除用户风险 - 将风险状态设置为消除。

## <a name="take-action-on-multiple-user-accounts-at-once"></a>一次性对多个用户帐户采取措施

一次性对多个受影响的用户执行操作：

1. 在 **“有风险的用户** ”选项卡中，选择要执行操作的用户集。

2. 选择要执行的以下操作之一：

    - 重置密码

    - 阻止登录

    - 确认用户遭到入侵

    - 消除用户风险

> [!NOTE]
> 如果管理的组织具有Azure AD Premium P2许可证，建议启用基于用户风险的条件访问策略。 有关详细信息，请参阅 [条件访问：基于用户风险的条件访问](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk-user)。

## <a name="related-content"></a>相关内容
[教程：使用用户登录的风险检测触发Azure AD多重身份验证或密码更改](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) (文章) \
[什么是风险？](/azure/active-directory/identity-protection/concept-identity-protection-risks)  (文章) \
[修正风险并取消阻止用户](/azure/active-directory/identity-protection/howto-identity-protection-remediate-unblock) (文章) 
