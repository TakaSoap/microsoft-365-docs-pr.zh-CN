---
title: 使用代表用户访问 Microsoft 365 Defender Api
description: 了解如何使用代表用户访问 Microsoft 365 Defender Api
keywords: 代表用户、api、应用程序、用户、访问令牌、令牌的访问权限
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847352"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a>代表用户访问 Microsoft 365 Defender Api

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


本页面介绍如何创建应用程序以获取用户的对 Microsoft 365 Defender 的编程访问权限。

如果需要以编程方式访问 Microsoft 365 Defender 而不使用用户，请参阅 [Create a app to Access microsoft 365 defender 而无需用户](api-create-app-web.md)。

如果您不确定所需的访问权限，请阅读 [access The Microsoft 365 Defender api](api-access.md)。

Microsoft 365 Defender 通过一组编程 Api 公开其大部分数据和操作。 这些 Api 将使您能够基于 Microsoft 365 Defender 功能自动执行工作流和创新。 API 访问需要 OAuth 2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般情况下，您需要执行以下步骤来使用 Api：
- 创建 AAD 应用程序
- 使用此应用程序获取访问令牌
- 使用令牌访问 Microsoft 365 Defender API

此页说明如何创建 AAD 应用程序、获取 Microsoft 365 Defender 的访问令牌并验证令牌。

>[!NOTE]
> 当代表用户访问 Microsoft 365 Defender API 时，您将需要正确的应用程序权限和用户权限。


>[!TIP]
> 如果您有权在门户中执行某项操作，则您有权在 API 中执行该操作。

## <a name="create-an-app"></a>创建应用程序

1. 使用具有 **全局管理员** 角色的用户登录到 [Azure](https://portal.azure.com) 。

2. 导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册** 。 

   ![Microsoft Azure 的图像和到应用程序注册的导航](../../media/atp-azure-new-app2.png)

3. 在 "注册来源" 中，输入以下信息，然后单击 " **注册** "。

   !["创建应用程序" 窗口的图像](../../media/nativeapp-create2.PNG)

   - **名称：** 您的应用程序名称
   - **应用程序类型：** 公共客户端
   - **重定向 URI：**https://portal.azure.com

4. 若要使您的应用程序能够访问 Microsoft 365 Defender 并分配 it 权限，请在应用程序页上，选择 " **API 权限** "  >  **Add permission**  >  **"添加我的组织使用** > 的权限 api"，键入 **microsoft 365 Defender** ，然后选择 " **microsoft 365 defender** "。

    >[!NOTE]
    > Microsoft 365 Defender 不会显示在原始列表中。 您需要先在文本框中写入其名称，才能看到它的显示。

      ![API 访问和 API 选择的图像](../../media/apis-in-my-org-tab.PNG)

    - 选择 " **委派权限** " > 选择适用于您的方案的相关权限，如 " **事件** "，然后选择 " **添加权限** "。

      ![API 访问和 API 选择的图像](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     >您需要选择相关权限。 

    -  若要确定所需的权限，请查看您想要调用的 API 中的 " **权限** " 部分。

    - 单击 " **授予同意** "

      >[!NOTE]
      >每次添加权限时，都必须单击 " **授予许可** " 以使新权限生效。

      ![授予权限的图像](../../media/grant-consent-delegated.PNG)

6. 记下应用程序 ID 和租户 ID：

   - 在应用程序页上，转到 " **概述** " 并复制以下内容：

   ![已创建应用程序 id 的图像](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a>使用 PowerShell 获取访问令牌

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a>相关主题
- [访问 Microsoft 365 Defender Api](api-access.md)
- [使用应用程序上下文访问 Microsoft 365 Defender](api-create-app-web.md)
