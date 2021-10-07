---
title: Microsoft 365标识模型和Azure Active Directory
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: 了解如何使用仅云或混合标识模型Microsoft 365 Azure AD 用户标识服务。
ms.openlocfilehash: 14f96e2ddb74eb1da8c6937a21e8dcaf72ae0808
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170531"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365标识模型和Azure Active Directory

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft 365使用 Azure Active Directory (Azure AD) （即 Microsoft 365 订阅中包含的基于云的用户标识和身份验证服务）来管理 Microsoft 365 的标识和身份验证。 正确配置标识基础结构对于管理Microsoft 365用户访问权限和权限至关重要。

开始之前，请观看此视频，以获取 Microsoft 365 身份模型和身份验证的概述。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

第一个规划选择是Microsoft 365标识模型。

## <a name="microsoft-365-identity-models"></a>Microsoft 365标识模型

若要规划用户帐户，首先需要了解 Microsoft 365 中的两个标识模型。 你可以仅在云中维护组织的标识，也可以维护本地 Active Directory 域服务 (AD DS) 标识，并使用它们在用户访问 Microsoft 365 云服务时进行身份验证。

下面是两种类型的标识及其最佳匹配和优势。

| 属性 | 仅限云标识 | 混合标识 |
|:-------|:-----|:-----|
| **定义** | 用户帐户仅存在于你的订阅的 Azure AD Microsoft 365中。 | 用户帐户存在于 AD DS 中，并且副本也存在于你的订阅订阅的 Azure AD Microsoft 365中。 Azure AD 中的用户帐户可能还包括已哈希 AD DS 用户帐户密码的哈希版本。 |
| **如何Microsoft 365用户凭据进行身份验证** | 你的订阅的 Azure AD Microsoft 365使用云标识帐户执行身份验证。 | 你的订阅的 Azure AD Microsoft 365处理身份验证过程或将用户重定向到另一个标识提供程序。 |
| **最适用于** | 没有或不需要本地 AD DS 的组织。 | 使用 AD DS 或其他标识提供程序的组织。 |
| **最大优势** | 易于使用。 无需额外的目录工具或服务器。 | 在访问本地或基于云的资源时，用户可以使用相同的凭据。 |
||||

## <a name="cloud-only-identity"></a>仅限云标识

仅限云标识使用仅存在于 Azure AD 中的用户帐户。 仅云标识通常由没有本地服务器或不使用 AD DS 管理本地标识的小组织使用。

以下是仅云标识的基本组件。

![仅云标识的基本组件。](../media/about-microsoft-365-identity/cloud-only-identity.png)

本地和远程 (联机) 用户使用其 Azure AD 用户帐户和密码访问 Microsoft 365 云服务。 Azure AD 根据其存储的用户帐户和密码对用户凭据进行身份验证。

### <a name="administration"></a>管理
由于用户帐户仅存储在 Azure AD 中，因此使用诸如 Microsoft 365 管理中心 和 Windows PowerShell[](/admin)[等工具管理云标识](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)。

## <a name="hybrid-identity"></a>混合标识

混合标识使用源自本地 AD DS 的帐户，这些帐户在 Azure AD 租户中拥有 Microsoft 365 订阅。 但是，大多数更改仅单向流动。 对 AD DS 用户帐户所做的更改将同步到 Azure AD 中的副本。 但是，对 Azure AD 中基于云的帐户所做的更改（如新用户帐户）不会与 AD DS 同步。

Azure AD 连接提供正在进行的帐户同步。 它在本地服务器上运行，检查 AD DS 中的更改，将这些更改转发到 Azure AD。 Azure AD 连接 提供了筛选哪些帐户已同步以及是否同步用户密码的哈希版本（称为密码哈希同步 (PHS) ）。

实现混合标识时，本地 AD DS 是指帐户信息权威源。 这意味着你执行的管理任务大部分是本地的，然后同步到 Azure AD。

下面是混合标识的组件。

![混合标识的组件。](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD 租户具有 AD DS 帐户的副本。 在此配置中，本地用户和访问云服务的远程Microsoft 365 Azure AD 进行身份验证。

> [!NOTE]
> 你始终需要使用 Azure AD 连接同步混合标识的用户帐户。 你需要在 Azure AD 中同步用户帐户才能执行许可证分配和组管理、配置权限以及涉及用户帐户的其他管理任务。

### <a name="administration"></a>管理

因为原始和权威用户帐户存储在本地 AD DS 中，所以使用管理 AD DS 时相同的工具管理标识。

在 Azure AD 中，Microsoft 365 管理中心或 PowerShell Microsoft 365管理同步的用户帐户。

## <a name="next-step"></a>后续步骤

如果你需要仅云标识模型，请参阅仅 [云标识](cloud-only-identities.md)。

如果需要混合标识模型，请参阅混合 [标识](plan-for-directory-synchronization.md)。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)
