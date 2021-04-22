---
title: 访问 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: 了解如何使用 API 根据 Microsoft Defender for Endpoint 功能自动执行工作流创新
keywords: api， api， wdatp， open api， microsoft defender for endpoint api， microsoft defender atp， 公共 api， 受支持的 api， 警报， 设备， 用户， 域， ip， 文件， 高级搜寻， 查询
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 843bd953b97f29a5b9c80fc44a9b19fae60a6fa7
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939762"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>访问 Microsoft Defender for Endpoint API 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**适用于：** 
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。 这些 API 将使您能够基于 Defender for Endpoint 功能自动执行工作流创新。 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

观看此视频，快速概览适用于终结点的 API 的 Defender。 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

通常，你将需要执行以下步骤来使用 API：
- 创建 AAD 应用程序
- 使用此应用程序获取访问令牌
- 使用令牌访问 Defender for Endpoint API


可以使用应用程序上下文或用户 **上下文访问** Defender for Endpoint **API。**

- **应用程序上下文： (推荐)** <br>
    由在没有登录用户存在的情况下运行的应用使用。 例如，作为后台服务或守护程序运行的应用。

    使用应用程序上下文访问 Defender for Endpoint API 需要执行的步骤：

  1. 创建 AAD Web 应用程序。
  2. 为应用程序分配所需的权限，例如，"读取警报"和"隔离计算机"。 
  3. 为此应用程序创建密钥。
  4. 使用应用程序及其密钥获取令牌。
  5. 使用令牌访问 Microsoft Defender 终结点 API

     有关详细信息，请参阅获取 [应用程序上下文的访问权限](exposed-apis-create-app-webapp.md)。


- **用户上下文：** <br>
    用于代表用户执行 API 中的操作。

    使用应用程序上下文访问 Defender for Endpoint API 要执行的步骤：

  1. 创建 AAD Native-Application。
  2. 为应用程序分配所需的权限，例如"读取警报"和"隔离计算机"等。 
  3. 使用具有用户凭据的应用程序获取令牌。
  4. 使用令牌访问 Microsoft Defender 终结点 API

     有关详细信息，请参阅使用 [用户上下文获取访问权限](exposed-apis-create-app-nativeapp.md)。


## <a name="related-topics"></a>相关主题
- [适用于终结点的 Microsoft Defender API](exposed-apis-list.md)
- [使用应用程序上下文访问 Microsoft Defender for Endpoint](exposed-apis-create-app-webapp.md)
- [使用用户上下文访问 Microsoft Defender for Endpoint](exposed-apis-create-app-nativeapp.md)
