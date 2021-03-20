---
title: 访问 Microsoft 365 Defender API
description: 了解如何访问 Microsoft 365 Defender API
keywords: access， api， 应用程序上下文， 用户上下文， aad 应用程序， 访问令牌
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 17fa47fd9998f4097ff323e670b9e442d7126a94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903972"
---
# <a name="access-the-microsoft-365-defender-apis"></a>访问 Microsoft 365 Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender 通过一组编程 API 公开其大部分数据和操作。 这些 API 可帮助你自动化工作流并充分利用 Microsoft 365 Defender 的功能。

通常，你将需要执行以下步骤来使用 API：

- 创建 Azure Active Directory 应用程序
- 使用此应用程序获取访问令牌
- 使用令牌访问 Microsoft 365 Defender API

> [!NOTE]
> API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码流](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

完成这些步骤后，即可使用特定上下文访问 Microsoft 365 Defender API。

## <a name="application-context-recommended"></a>应用上下文 (推荐) 

对于在没有登录用户的情况下运行的应用（如后台服务或守护程序）使用此上下文。

1. 创建 Azure Active Directory Web 应用程序。
2. 向应用程序分配所需的权限。
3. 为应用程序创建密钥。
4. 使用应用程序及其密钥获取安全令牌。
5. 使用令牌访问 Microsoft 365 Defender API。

有关详细信息，请参阅创建应用以在没有用户的情况下访问 **[Microsoft 365 Defender。](api-create-app-web.md)**

## <a name="user-context"></a>用户上下文

使用此上下文代表单个用户执行操作。

1. 创建 Azure Active Directory 本机应用程序。
2. 向应用程序分配所需的权限。
3. 使用应用程序的用户凭据获取安全令牌。
4. 使用令牌访问 Microsoft 365 Defender API。

有关详细信息，请参阅创建应用以代表用户访问 **[Microsoft 365 Defender API。](api-create-app-user-context.md)**

## <a name="partner-context"></a>合作伙伴上下文

当你需要向多个租户中的许多用户提供应用时， [请使用此上下文](/azure/active-directory/develop/single-and-multi-tenant-apps)。

1. 创建 Azure Active Directory 多租户应用程序。
2. 向应用程序分配所需的权限。
3. 从 [每个租户](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 获取应用的管理员同意。
4. 使用基于客户的租户 ID 的用户凭据获取安全令牌。
5. 使用令牌访问 Microsoft 365 Defender API。

有关详细信息，请参阅创建具有 Microsoft **[365 Defender API](api-partner-access.md)** 合作伙伴访问权限的应用。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [用户登录和 API 访问的 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [使用 Azure Key Vault 管理服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)
- [创建访问 Microsoft 365 API 的"Hello world"应用程序](api-hello-world.md)