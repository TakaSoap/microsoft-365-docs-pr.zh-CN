---
title: Microsoft 365 Lighthouse用户页面概述
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
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，请了解"用户"页面。
ms.openlocfilehash: fad5ff4b41b43efb68c7e230401b80e50cea95a4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329921"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a>Microsoft 365 Lighthouse用户页面概述 

Microsoft 365 Lighthouse，通过选择左侧导航窗格中的"用户"打开"用户"页面，可以跨客户租户帐户管理用户。 在此页中，可以搜索用户，并评估用户帐户的安全状态并采取行动。 您还可以查看风险用户的见解，以及多重身份验证和自助服务密码重置的状态。  
  
## <a name="search-users-tab"></a>"搜索用户"选项卡  
  
从"搜索用户"选项卡中，可以跨租户快速搜索特定用户并执行基本用户管理操作，如重置帐户密码。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="&quot;搜索用户&quot;选项卡的屏幕截图。":::

## <a name="risky-users-tab"></a>"有风险的用户"选项卡

"风险用户"选项卡显示租户中已标记为存在风险行为的用户帐户。 选择任意用户以查看检测到的风险详细信息，或者通过重置用户密码或阻止登录来缓解风险。 有关风险类型和检测功能的信息，请参阅 [什么是风险？](/azure/active-directory/identity-protection/concept-identity-protection-risks)。

"风险用户"选项卡还包括以下选项：
- **导出：** 选择将设备合规性数据导出到Excel逗号分隔值 (.csv) 文件中。
- **刷新：** 选择以检索最新的设备合规性数据。
- **确认 (已) 泄露：** 选择以确认用户受到威胁。
- **消除 (用户) 风险：** 选择可消除用户风险。  
- **重置密码：** 选择更改或重置用户密码。
- **阻止登录：** 选择可阻止任何人以该用户登录。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="&quot;有风险的用户&quot;选项卡的屏幕截图。":::

## <a name="multifactor-authentication-tab"></a>"多重身份验证"选项卡

The Multifactor Authentication tab provides detailed information on the status of multifactor authentication (MFA) enablement across your tenants. 选择列表中的任意租户以查看该租户的更多详细信息，包括已配置哪些需要 MFA 的条件访问策略，以及哪些用户尚未注册 MFA。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="&quot;多重身份验证&quot;选项卡的屏幕截图。":::

## <a name="password-reset-tab"></a>密码重置选项卡

"密码重置"选项卡显示有关租户中自助服务密码重置启用状态的详细信息。 它还提供关于已启用但仍需要注册的用户的见解，然后他们才能自行重置密码。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="&quot;密码重置&quot;选项卡的屏幕截图。":::

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse设备合规性页面概述 (](m365-lighthouse-device-compliance-page-overview.md)文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
