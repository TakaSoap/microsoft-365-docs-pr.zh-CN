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
description: 对于托管服务提供商 (MICROSOFT 365) ，了解如何查看和管理有风险的用户。
ms.openlocfilehash: 708fc0576c85d9b8511ac6b31ed0398fae1b20d3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330774"
---
# <a name="view-and-manage-risky-users"></a>查看和管理有风险的用户

Microsoft 每天收集并分析数万亿用户登录信号。 这些信号用于帮助构建良好的用户登录行为模式和识别潜在的有风险的登录尝试。 Azure Active Directory (Azure AD) Identity Protection 使用这些信号查看用户登录尝试，如果存在可疑活动，请采取措施。

Microsoft 365 Lighthouse 通过提供所有托管租户中风险用户的单一视图，帮助管理 Azure AD Identity Protection 检测到的风险。 通过重置其密码或阻止他们登录其 Microsoft 365 帐户，可以快速保护有风险的用户。 还可以查看见解，以更好地了解用户的风险并确定下一步。

Azure AD Identity Protection 可识别多种类型的风险，包括：

- 泄露的凭据
- 匿名 IP 使用
- 非典型旅行
- 从受感染的设备登录
- 从具有可疑活动的 IP 地址登录
- 从不熟悉的位置登录

## <a name="before-you-begin"></a>准备工作

用户必须先满足以下条件，然后才能显示在有风险的用户列表中：

- 客户租户必须具有每个用户的 Azure AD Premium 许可证。 有关支持 Azure AD Identity Protection 的许可证详细信息，请参阅 [什么是标识保护？](/azure/active-directory/identity-protection/overview-identity-protection)

- 客户租户必须在 Microsoft 365 Lighthouse 中处于活动状态。 若要确定租户是否处于活动状态，请参阅 [Microsoft 365 Lighthouse Tenants 页面概述](m365-lighthouse-tenant-list-overview.md)。

## <a name="review-detected-risks-and-take-action"></a>查看检测到的风险并采取措施

在 Azure AD Identity Protection 中，风险检测包括任何与 Azure AD 中的用户帐户相关的已识别可疑操作。

1. In the left navigation pane in Lighthouse， select **Users**.

2. 选择" **有风险的用户"** 选项卡。

3. 查看列表中风险状态为"有风险 **"的用户**。

4. 选择 **"查看风险** 检测"，获取有关为每个用户检测到的风险的详细信息。 有关风险类型和检测功能的信息，请参阅 [什么是风险？](/azure/active-directory/identity-protection/concept-identity-protection-risks)。

5. 为每个用户评估风险检测，并适当地选择以下操作之一：

    - 重置密码 – 更改或重置用户密码。

    - 阻止登录 - 阻止任何人以该用户登录。

    - 确认用户遭到入侵 - 将风险状态设置为已确认泄露。

    - 消除用户风险 - 将风险状态设置为消除。

## <a name="take-action-on-multiple-user-accounts-at-once"></a>一次对多个用户帐户采取措施

一次对多个受影响的用户采取措施：

1. 从 **"有风险的用户"** 选项卡中，选择要采取操作的用户集。

2. 选择要执行以下操作之一：

    - 重置密码

    - 阻止登录

    - 确认用户遭到入侵

    - 消除用户风险

> [!NOTE]
> 如果你管理的组织具有 Azure AD Premium P2 许可证，建议你启用基于用户风险的条件访问策略。 有关详细信息，请参阅条件 [访问：基于用户风险的条件访问](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk-user)。

## <a name="related-content"></a>相关内容
[教程：使用用户登录的风险检测触发 Azure AD](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) 多重身份验证或密码更改 (文章) \
[什么是风险？](/azure/active-directory/identity-protection/concept-identity-protection-risks)  (文章) \
[修正风险并解除阻止用户 (](/azure/active-directory/identity-protection/howto-identity-protection-remediate-unblock) 文章) 
