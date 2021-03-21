---
title: 创建应用以在没有用户的情况下访问 Microsoft 365 Defender
description: 了解如何创建应用以在没有用户的情况下访问 Microsoft 365 Defender。
keywords: 应用， 访问， api， 创建
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
ms.openlocfilehash: b9cee02d921ee4d0b9b0b97a109ac9c7141e8aac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924394"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="098d5-104">创建应用以在没有用户的情况下访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="098d5-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="098d5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="098d5-105">**Applies to:**</span></span>

- <span data-ttu-id="098d5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="098d5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="098d5-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="098d5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="098d5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="098d5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="098d5-109">此页面介绍如何创建应用程序，以在没有定义用户的情况下以编程方式访问 Microsoft 365 Defender，例如，如果你要创建守护程序或后台服务。</span><span class="sxs-lookup"><span data-stu-id="098d5-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="098d5-110">如果你需要代表一个或多个用户以编程方式访问 Microsoft 365 Defender，请参阅创建应用以代表用户访问 [Microsoft 365 Defender](api-create-app-user-context.md) API 和 创建具有 [Microsoft 365 Defender API](api-partner-access.md)合作伙伴访问权限的应用。</span><span class="sxs-lookup"><span data-stu-id="098d5-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="098d5-111">如果你不确定需要哪种类型的访问，请参阅 [入门](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="098d5-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="098d5-112">Microsoft 365 Defender 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="098d5-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="098d5-113">这些 API 可帮助你自动化工作流和利用 Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="098d5-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="098d5-114">此 API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="098d5-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="098d5-115">有关详细信息，请参阅 [OAuth 2.0 授权代码流](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="098d5-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="098d5-116">通常，你将需要执行以下步骤来使用这些 API：</span><span class="sxs-lookup"><span data-stu-id="098d5-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="098d5-117">创建 Azure Active Directory (Azure AD) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="098d5-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="098d5-118">使用此应用程序获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="098d5-118">Get an access token using this application.</span></span>
- <span data-ttu-id="098d5-119">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="098d5-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="098d5-120">本文介绍如何：</span><span class="sxs-lookup"><span data-stu-id="098d5-120">This article explains how to:</span></span>

- <span data-ttu-id="098d5-121">创建 Azure AD 应用程序</span><span class="sxs-lookup"><span data-stu-id="098d5-121">Create an Azure AD application</span></span>
- <span data-ttu-id="098d5-122">获取 Microsoft 365 Defender 的访问令牌</span><span class="sxs-lookup"><span data-stu-id="098d5-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="098d5-123">验证令牌。</span><span class="sxs-lookup"><span data-stu-id="098d5-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="098d5-124">创建应用</span><span class="sxs-lookup"><span data-stu-id="098d5-124">Create an app</span></span>

1. <span data-ttu-id="098d5-125">以具有全局管理员角色的用户 **登录** [Azure。](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="098d5-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="098d5-126">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册**。</span><span class="sxs-lookup"><span data-stu-id="098d5-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的图像和应用程序注册导航](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="098d5-128">在表单中，为应用程序选择一个名称，然后选择"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="098d5-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="098d5-129">在应用程序页面上，选择 **"API** 权限""添加我的组织使用>  >    >   API"，键入 **"Microsoft 威胁** 防护"，然后选择 **"Microsoft 威胁防护"。**</span><span class="sxs-lookup"><span data-stu-id="098d5-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="098d5-130">你的应用现在可以访问 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="098d5-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="098d5-131">*Microsoft 威胁防护* 是 Microsoft 365 Defender 的以前名称，不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="098d5-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="098d5-132">你需要开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="098d5-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 权限选择的图像](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="098d5-134">选择 **"应用程序权限"。**</span><span class="sxs-lookup"><span data-stu-id="098d5-134">Select **Application permissions**.</span></span> <span data-ttu-id="098d5-135">为方案选择相关权限 (例如 **，Incident.Read.All**) ，然后选择"**添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="098d5-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="098d5-137">您需要为方案选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="098d5-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="098d5-138">*读取所有事件* 只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="098d5-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="098d5-139">若要确定所需的权限，请查看要调用的 API中的"权限"部分。</span><span class="sxs-lookup"><span data-stu-id="098d5-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="098d5-140">例如，若要 [运行高级查询](api-advanced-hunting.md)，请选择"运行高级查询"权限;若要 [隔离设备](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)，请选择"隔离计算机"权限。</span><span class="sxs-lookup"><span data-stu-id="098d5-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="098d5-141">选择 **"授予管理员同意"。**</span><span class="sxs-lookup"><span data-stu-id="098d5-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="098d5-142">每次添加权限时，都必须选择"授予管理员 **同意** ，让权限生效"。</span><span class="sxs-lookup"><span data-stu-id="098d5-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![授予权限的图像](../../media/grant-consent.PNG)

7. <span data-ttu-id="098d5-144">若要将密码添加到应用程序，请选择"证书&**密码"，** 向密码添加说明，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="098d5-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="098d5-145">选择"添加 **"后**，**选择"复制生成的机密值"。**</span><span class="sxs-lookup"><span data-stu-id="098d5-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="098d5-146">离开后将无法检索密码值。</span><span class="sxs-lookup"><span data-stu-id="098d5-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![创建应用密钥的图像](../../media/webapp-create-key2.png)

8. <span data-ttu-id="098d5-148">在安全的地方记录应用程序 ID 和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="098d5-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="098d5-149">它们列在应用程序 **页面上的"** 概述"下。</span><span class="sxs-lookup"><span data-stu-id="098d5-149">They're listed under **Overview** on your application page.</span></span>

   ![已创建应用 ID 的图像](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="098d5-151">仅适用于 **Microsoft 365** Defender [](./api-partner-access.md)合作伙伴：按照这些说明通过 Microsoft 365 Defender API 访问合作伙伴，将应用设置为多租户，以便应用在获得管理员同意后可在所有租户中可用。</span><span class="sxs-lookup"><span data-stu-id="098d5-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](./api-partner-access.md) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="098d5-152">第三 **方** 应用需要合作伙伴访问权限，例如，如果你创建一个旨在在多个客户的租户中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="098d5-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="098d5-153">如果 **创建的** 服务仅在租户中运行（例如，供自己使用的应用程序，仅与你自己的数据交互）不需要。</span><span class="sxs-lookup"><span data-stu-id="098d5-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="098d5-154">若要将应用设置为多租户：</span><span class="sxs-lookup"><span data-stu-id="098d5-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="098d5-155">转到 **身份验证**，并添加 https://portal.azure.com 为 **重定向 URI**。</span><span class="sxs-lookup"><span data-stu-id="098d5-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="098d5-156">在页面底部的"支持的帐户类型"下，选择多租户应用的任何组织目录应用程序许可中的"帐户"。</span><span class="sxs-lookup"><span data-stu-id="098d5-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="098d5-157">由于你的应用程序代表你的用户与 Microsoft 365 Defender 交互，它需要针对你打算使用它的每个租户获得批准。</span><span class="sxs-lookup"><span data-stu-id="098d5-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="098d5-158">每个租户的 Active Directory 全局管理员需要选择同意链接并批准你的应用。</span><span class="sxs-lookup"><span data-stu-id="098d5-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="098d5-159">同意链接具有以下结构：</span><span class="sxs-lookup"><span data-stu-id="098d5-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="098d5-160">数字 `00000000-0000-0000-0000-000000000000` 应替换为应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="098d5-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="098d5-161">**完成！**</span><span class="sxs-lookup"><span data-stu-id="098d5-161">**Done!**</span></span> <span data-ttu-id="098d5-162">已成功注册应用程序！</span><span class="sxs-lookup"><span data-stu-id="098d5-162">You've successfully registered an application!</span></span> <span data-ttu-id="098d5-163">有关令牌获取和验证，请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="098d5-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="098d5-164">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="098d5-164">Get an access token</span></span>

<span data-ttu-id="098d5-165">有关 Azure Active Directory 令牌详细信息，请参阅 [Azure AD 教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="098d5-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="098d5-166">尽管本节中的示例鼓励您粘贴机密值以进行测试，但您永远不应将密码硬编码到生产中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="098d5-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="098d5-167">第三方可以使用你的密码访问资源。</span><span class="sxs-lookup"><span data-stu-id="098d5-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="098d5-168">通过使用 Azure 密钥保管库，可帮助保护 [应用密钥的安全](/azure/key-vault/general/about-keys-secrets-certificates)。</span><span class="sxs-lookup"><span data-stu-id="098d5-168">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="098d5-169">有关如何保护应用的实际示例，请参阅使用 Azure Key Vault 管理 [服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="098d5-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="098d5-170">使用 PowerShell 获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="098d5-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="098d5-171">使用 C 获取访问令牌\#</span><span class="sxs-lookup"><span data-stu-id="098d5-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="098d5-172">以下代码已使用 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 进行测试。</span><span class="sxs-lookup"><span data-stu-id="098d5-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="098d5-173">创建新的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="098d5-173">Create a new console application.</span></span>

1. <span data-ttu-id="098d5-174">安装 NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="098d5-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="098d5-175">添加以下行：</span><span class="sxs-lookup"><span data-stu-id="098d5-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="098d5-176">将以下代码复制并粘贴到应用中 (请不要忘记更新三个 `tenantId` `clientId` `appSecret` 变量：、、) ：</span><span class="sxs-lookup"><span data-stu-id="098d5-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="098d5-177">使用 Python 获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="098d5-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="098d5-178">使用令牌获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="098d5-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="098d5-179">在 Windows 10 版本 1803 及更高版本上预安装了小组件。</span><span class="sxs-lookup"><span data-stu-id="098d5-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="098d5-180">对于其他版本的 Windows，请直接从官方网站下载并 [安装该工具](https://curl.haxx.se/windows/)。</span><span class="sxs-lookup"><span data-stu-id="098d5-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="098d5-181">打开命令提示符，CLIENT_ID Azure 应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="098d5-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="098d5-182">将CLIENT_SECRET Azure 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="098d5-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="098d5-183">将TENANT_ID设置为想要使用你的应用访问 Microsoft 365 Defender 的客户的 Azure 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="098d5-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="098d5-184">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="098d5-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="098d5-185">成功的响应如下所示：</span><span class="sxs-lookup"><span data-stu-id="098d5-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="098d5-186">验证令牌</span><span class="sxs-lookup"><span data-stu-id="098d5-186">Validate the token</span></span>

1. <span data-ttu-id="098d5-187">将令牌复制并粘贴到 [JSON Web 令牌验证程序网站 JWT](https://jwt.ms) 中，以解码它。</span><span class="sxs-lookup"><span data-stu-id="098d5-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="098d5-188">确保解码 *令牌* 中的角色声明包含所需的权限。</span><span class="sxs-lookup"><span data-stu-id="098d5-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="098d5-189">在下图中，你可以看到从应用获取的解码令牌，具有 、 和 `Incidents.Read.All` `Incidents.ReadWrite.All` `AdvancedHunting.Read.All` 权限：</span><span class="sxs-lookup"><span data-stu-id="098d5-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![令牌验证图像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="098d5-191">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="098d5-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="098d5-192">选择要用于事件或高级搜寻 () API。</span><span class="sxs-lookup"><span data-stu-id="098d5-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="098d5-193">有关详细信息，请参阅支持的[Microsoft 365 Defender API。](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="098d5-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="098d5-194">在即将发送的 http 请求中，将授权标头设置为 `"Bearer" <token>` *，Bearer* 为授权方案，令牌为经过验证的令牌。</span><span class="sxs-lookup"><span data-stu-id="098d5-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="098d5-195">令牌将在一小时内过期。</span><span class="sxs-lookup"><span data-stu-id="098d5-195">The token will expire within one hour.</span></span> <span data-ttu-id="098d5-196">在此期间，可以使用同一令牌发送多个请求。</span><span class="sxs-lookup"><span data-stu-id="098d5-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="098d5-197">以下示例演示如何发送请求，以使用 C# 获取 **事件列表**。</span><span class="sxs-lookup"><span data-stu-id="098d5-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="098d5-198">相关文章</span><span class="sxs-lookup"><span data-stu-id="098d5-198">Related articles</span></span>

- [<span data-ttu-id="098d5-199">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="098d5-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="098d5-200">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="098d5-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="098d5-201">创建"Hello world"应用程序</span><span class="sxs-lookup"><span data-stu-id="098d5-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="098d5-202">创建应用以代表用户访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="098d5-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="098d5-203">创建具有对 Microsoft 365 Defender API 的多租户合作伙伴访问权限的应用</span><span class="sxs-lookup"><span data-stu-id="098d5-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="098d5-204">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="098d5-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="098d5-205">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="098d5-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="098d5-206">使用 Azure Key Vault 管理服务器应用中的密钥</span><span class="sxs-lookup"><span data-stu-id="098d5-206">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="098d5-207">用户登录和 API 访问的 OAuth 2.0 授权</span><span class="sxs-lookup"><span data-stu-id="098d5-207">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)