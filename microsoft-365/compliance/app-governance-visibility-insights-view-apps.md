---
title: 查看你的应用
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 查看你的应用。
ms.openlocfilehash: 448ca4cd7fab13ce25c3bcc18c350d227461ee45
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541095"
---
# <a name="view-your-apps"></a>查看你的应用

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

通过 Microsoft 应用治理，可以快速深入了解租户中的 Microsoft 365 应用。例如，你可以查看：

- 租户中使用 Microsoft Graph API，并且已启用 OAuth 的应用列表，以及相关的应用元数据和使用情况数据。
- 通过在列表中选择一个应用，可以看到包含更深入的见解和信息的应用详细信息。

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>获取租户中所有应用的列表

有关租户中应用的摘要，请转到 **“Microsoft 365 合规中心”>“应用保护和治理”>“应用”**。

![Microsoft 365 合规中心内的 MAPG 应用摘要页面](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> 若要查看应用治理数据，你的登录帐户必须具有[这些角色](app-governance-get-started.md#administrator-roles)中的一个。
>

你将看到应用列表和以下信息：

- 应用名称
- 发布者
- M365 认证

  指示应用是否与 Microsoft 技术兼容、是否符合云应用安全最佳实践以及是否受 Microsoft 支持。

- 上次修改日期

  如果在客户端中安装应用治理的日期比上次修改应用的日期更近，则显示安装日期。

- 安装日期
- 权限级别
- 用户数
- 数据访问

  过去一天租户中此应用的数据上传和下载总和以及前一天的更改。

默认情况下，应用治理按 **应用名称** 对应用列表进行排序。 要按其他应用属性对列表排序，请选择对应的属性名称。

你还可以选择“**搜索**”以按名称搜索应用。

## <a name="getting-detailed-information-on-an-app"></a>获取有关应用的详细信息

有关租户中特定应用的详细信息，请转到 **“Microsoft 365 合规中心”>“应用治理”>“应用页面”>“*应用名称”***。

![Microsoft 365 合规中心内的应用治理应用详细信息窗格](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

应用详细信息窗格提供有关这些选项卡的附加信息：

| 选项卡名称 | 说明 |
|:-------|:-----|
| 详细信息 | 查看应用的其他数据，例如首次同意的日期和应用 ID。 要查看在 Azure AD 中注册的应用的属性，请选择“**在 Azure AD 中查看应用**”。 |
| 使用情况 | 查看租户中的应用访问的数据、绘制数据使用情况图，并显示排名靠前的 \<x> 用户和拥有[优先帐户](/microsoft-365/admin/setup/priority-accounts)的用户的使用情况。 |
| 用户 | 查看正在使用该应用的用户列表、他们是否是优先帐户，以及下载和上传的数据量。 |
| 权限 | 查看应用授予和使用的权限的摘要以及特定权限的列表。 有关详细信息，请参阅 [Microsoft Graph 权限参考](/graph/permissions-reference)。 |
|||

对于已启用的应用，还有一个“**禁用应用**”控件和一个“**启用应用**”控件，前者用于禁用所选应用，后者用于启用已禁用应用。 这些操作需要以下管理员角色才能执行：

- 合规管理员
- 全局管理员
- 安全管理员
- 安全操作员

## <a name="next-step"></a>后续步骤

[确定你的整体应用合规状况](app-governance-visibility-insights-compliance-posture.md)。
