---
title: 访问 Microsoft 威胁防护 Api
description: 了解如何访问 Microsoft 威胁防护 Api
keywords: 访问、api、应用程序上下文、用户上下文、aad 应用程序、访问令牌
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: bccf36f46121caceeb6dc6d97c126f48149d9426
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197877"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>访问 Microsoft 威胁防护 Api

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Microsoft 威胁防护通过一组编程 Api 公开其大部分数据和操作。 这些 Api 将使您能够基于 Microsoft 威胁防护功能自动执行工作流和创新。 API 访问需要 OAuth 2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。


一般情况下，您需要执行以下步骤来使用 Api：
- 创建 AAD 应用程序
- 使用此应用程序获取访问令牌
- 使用令牌访问 Microsoft 威胁防护 API


您可以使用 **应用程序上下文** 或 **用户上下文**访问 Microsoft 威胁防护 API。

- **应用程序上下文： (建议的) ** <br>
    由在没有登录用户的情况下运行的应用程序使用。 例如，运行为后台服务或守护程序的应用程序。

    使用应用程序上下文访问 Microsoft 威胁防护 API 时需要执行的步骤：

  1. 创建 AAD Web 应用程序。
  2. 将所需的权限分配给 applicationFor 示例： AdvancedHunting、 **all**、 **AdvancedHunting.Read.All**。 
  3. 为此应用程序创建一个键。
  4. 使用应用程序及其键获取令牌。
  5. 使用令牌访问 Microsoft 威胁防护 API

     有关详细信息，请参阅 [使用应用程序上下文获取访问权限](api-create-app-web.md)。


- **用户上下文：** <br>
    用于代表用户在 API 中执行操作。

    使用应用程序上下文访问 Microsoft 威胁防护 API 时需要执行的步骤：
  1. 创建 AAD 本机应用程序。
  2. 将所需的权限分配给应用程序。 例如，AdvancedHunting、**读取、****读取**。
  3. 使用具有用户凭据的应用程序获取令牌。
  4. 使用令牌访问 Microsoft 威胁防护 API

     有关详细信息，请参阅 [Get access with user context](api-create-app-user-context.md)。


## <a name="related-topics"></a>相关主题
- [Microsoft 威胁防护 Api](api-supported.md)
- [使用应用程序上下文访问 Microsoft 威胁防护](api-create-app-web.md)
- [使用用户上下文访问 Microsoft 威胁防护](api-create-app-user-context.md)
