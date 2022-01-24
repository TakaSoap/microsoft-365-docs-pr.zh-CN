---
title: 访问Microsoft 365 Defender API
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
ms.custom: api
ms.openlocfilehash: a8406c0ec27c238615b25f60b988efbb50a8d7d7
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172231"
---
# <a name="access-the-microsoft-365-defender-apis"></a>访问Microsoft 365 Defender API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

Microsoft 365 Defender通过一组编程 API 公开其大部分数据和操作。 这些 API 可帮助您自动化工作流，并充分利用Microsoft 365 Defender功能。

通常，你将需要执行以下步骤来使用 API：

- 创建Azure Active Directory应用程序
- 使用此应用程序获取访问令牌
- 使用令牌访问 Microsoft 365 Defender API

> [!NOTE]
> API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

完成这些步骤后，就可以使用特定上下文Microsoft 365 Defender API 了。

## <a name="application-context-recommended"></a>应用上下文 (推荐) 

对于在没有登录用户的情况下运行的应用（如后台服务或守护程序）使用此上下文。

1. 创建Azure Active Directory Web 应用程序。
2. 向应用程序分配所需的权限。
3. 为应用程序创建密钥。
4. 使用应用程序及其密钥获取安全令牌。
5. 使用令牌访问 Microsoft 365 Defender API。

有关详细信息，请参阅创建 **[应用以在没有用户Microsoft 365 Defender访问应用](api-create-app-web.md)**。

## <a name="user-context"></a>用户上下文

使用此上下文代表单个用户执行操作。

1. 创建Azure Active Directory应用程序。
2. 向应用程序分配所需的权限。
3. 使用应用程序的用户凭据获取安全令牌。
4. 使用令牌访问 Microsoft 365 Defender API。

有关详细信息，请参阅创建 **[应用以代表Microsoft 365 Defender访问 API。](api-create-app-user-context.md)**

## <a name="partner-context"></a>合作伙伴上下文

当你需要向多个租户中的许多用户提供应用时，请使用 [此上下文](/azure/active-directory/develop/single-and-multi-tenant-apps)。

1. 创建Azure Active Directory租户应用程序。
2. 向应用程序分配所需的权限。
3. 从 [每个租户](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 获取应用的管理员同意。
4. 使用基于客户的租户 ID 的用户凭据获取安全令牌。
5. 使用令牌访问 Microsoft 365 Defender API。

有关详细信息，请参阅 **[创建具有合作伙伴访问应用 API Microsoft 365 Defender应用](api-partner-access.md)**。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [用户登录和 API 访问的 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [使用 Azure Key Vault 管理服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)
- [创建访问应用程序 API 的"hello world"Microsoft 365应用程序](api-hello-world.md)
