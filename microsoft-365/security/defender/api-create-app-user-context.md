---
title: 创建应用以Microsoft 365 Defender访问 API
description: 了解如何代表Microsoft 365 Defender访问 API。
keywords: 访问，代表用户， api， 应用程序， 用户， 访问令牌， 令牌，
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
ms.openlocfilehash: fdba7ee1b1cf2f46bd17c648c7cda48f1ca65490
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755237"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>创建应用以Microsoft 365 Defender访问 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

此页面介绍如何创建应用程序，以代表单个Microsoft 365 Defender访问应用程序。

如果需要在未定义用户 Microsoft 365 Defender的情况下以编程方式访问 (例如，如果要编写后台应用或守护程序) ，请参阅创建应用以在没有用户[的情况下](api-create-app-web.md)访问 Microsoft 365 Defender。 如果你需要为多个租户提供访问权限（例如，如果你为大型组织或一组客户提供服务的话）请参阅创建具有合作伙伴访问 MICROSOFT 365 DEFENDER [API 的应用](api-partner-access.md)。如果不确定需要哪种类型的访问，请参阅[入门](api-access.md)。

Microsoft 365 Defender通过一组编程 API 公开其大部分数据和操作。 这些 API 可帮助您自动化工作流，并充分利用Microsoft 365 Defender功能。 此 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

通常，你将需要执行以下步骤来使用这些 API：

- 创建Azure Active Directory (Azure AD) 应用程序。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Microsoft 365 Defender API。

本文介绍如何：

- 创建 Azure AD 应用程序
- 获取访问令牌以Microsoft 365 Defender
- 验证令牌

> [!NOTE]
> 代表Microsoft 365 Defender访问 API 时，需要正确的应用程序权限和用户权限。

> [!TIP]
> 如果你有权在门户中执行一个操作，则你有权在 API 中执行此操作。

## <a name="create-an-app"></a>创建应用

1. 以具有全局管理员角色的用户 **登录** [Azure](https://portal.azure.com)。

2. 导航到 **Azure Active Directory** >  **App 注册** > **新注册**。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Azure 门户的&quot;管理&quot;窗格中的&quot;新注册&quot;选项" lightbox="../../media/atp-azure-new-app2.png":::

3. 在表单中，为应用程序选择一个名称，然后输入重定向 URI 的以下信息，然后选择"注册 **"**。

   :::image type="content" source="../../media/nativeapp-create2.PNG" alt-text="Azure 门户中的应用程序注册窗格" lightbox="../../media/nativeapp-create2.PNG":::
   

   - **应用程序类型：** 公共客户端
   - **重定向 URI：** https://portal.azure.com

4. 在应用程序页面上，选择 **"API** >  权限 **"** > "我的组织使用的 API">**"Microsoft 威胁** 防护"，然后选择 **"Microsoft 威胁防护"**。 你的应用现在可以访问Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威胁防护* 是 Microsoft 威胁防护Microsoft 365 Defender名称，不会显示在原始列表中。 你需要开始在文本框中写入其名称，以查看其显示。

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="企业门户中的组织的 API Microsoft 365 Defender窗格" lightbox="../../media/apis-in-my-org-tab.PNG":::

   - 选择 **"委派权限"**。 为方案选择相关权限，例如 (**Incident.Read**) ，然后选择" **添加权限"**。

     :::image type="content" source="../../media/request-api-permissions-delegated.PNG" alt-text="Microsoft 365 Defender门户中的&quot;委派Microsoft 365 Defender窗格" lightbox="../../media/request-api-permissions-delegated.PNG":::

    > [!NOTE]
    > 您需要为方案选择相关权限。 *读取所有事件* 只是一个示例。 若要确定所需的权限，请查看要调用的 API 中的"权限"部分。
    >
    > 例如，若要 [运行高级查询，](api-advanced-hunting.md)请选择"运行高级查询"权限;若要 [隔离设备，](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)请选择"隔离计算机"权限。

5. 选择 **"授予管理员同意"**。 每次添加权限时，都必须选择"授予管理员 **同意** ，让权限生效"。

   :::image type="content" source="../../media/grant-consent-delegated.PNG" alt-text="管理门户中的管理员同意Microsoft 365 Defender窗格" lightbox="../../media/grant-consent-delegated.PNG":::

6. 在安全的地方记录应用程序 ID 和租户 ID。 它们列在应用程序 **页面上的"** 概述"下。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender门户中的&quot;概述&quot;窗格" lightbox="../../media/app-and-tenant-ids.png":::

## <a name="get-an-access-token"></a>获取访问令牌

有关令牌Azure Active Directory，请参阅Azure AD[教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

### <a name="get-an-access-token-using-powershell"></a>使用 PowerShell 获取访问令牌

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>验证令牌

1. 将令牌复制并粘贴到 [JWT](https://jwt.ms) 中以解码它。
1. 确保解码 *令牌* 中的角色声明包含所需的权限。

在下图中，你可以看到从应用获取的解码令牌，具有 ```Incidents.Read.All``````Incidents.ReadWrite.All```、 和 ```AdvancedHunting.Read.All``` 权限：

:::image type="content" source="../../media/defender-endpoint/webapp-decoded-token.png" alt-text="应用程序门户中&quot;解码令牌&quot;窗格中Microsoft 365 Defender部分" lightbox="../../media/defender-endpoint/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>使用令牌访问 Microsoft 365 Defender API

1. 选择要用于事件或高级 (API) 。 有关详细信息，请参阅受支持的[Microsoft 365 Defender API](api-supported.md)。
2. 在即将发送的 `"Bearer" <token>`http 请求中，将授权标头设置为 ， *Bearer* 为授权方案， *令牌* 为经过验证的令牌。
3. 令牌将在一小时内过期。 在此期间，可以使用同一令牌发送多个请求。

以下示例演示如何发送请求，以使用事件 **C#。**

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [访问Microsoft 365 Defender API](api-access.md)
- [创建"Hello world"应用](api-hello-world.md)
- [创建应用以在没有用户Microsoft 365 Defender访问用户](api-create-app-web.md)
- [创建具有对 API 的多租户合作伙伴访问权限Microsoft 365 Defender应用程序](api-partner-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [用户登录和 API 访问的 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
