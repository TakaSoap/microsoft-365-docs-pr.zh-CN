---
title: Microsoft 365 Defender REST API 的 Hello World
description: 了解如何创建应用并使用令牌访问 Microsoft 365 Defender API
keywords: 应用， 令牌， 访问， aad， 应用， 应用程序注册， powershell， 脚本， 全局管理员， 权限， microsoft 365 defender
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
ms.openlocfilehash: 65319d46871282c454287af225647f89e3535c78
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924334"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="3bc63-104">Microsoft 365 Defender REST API 的 Hello World</span><span class="sxs-lookup"><span data-stu-id="3bc63-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3bc63-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3bc63-105">**Applies to:**</span></span>

- <span data-ttu-id="3bc63-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bc63-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bc63-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="3bc63-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3bc63-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3bc63-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="3bc63-109">使用简单的 PowerShell 脚本获取事件</span><span class="sxs-lookup"><span data-stu-id="3bc63-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="3bc63-110">完成此项目需要 5 到 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="3bc63-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="3bc63-111">此时间估计包括注册应用程序，以及应用 PowerShell 示例脚本中的代码。</span><span class="sxs-lookup"><span data-stu-id="3bc63-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="3bc63-112">在 Azure Active Directory 中注册应用</span><span class="sxs-lookup"><span data-stu-id="3bc63-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="3bc63-113">以具有全局管理员角色的用户 **登录** [Azure。](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="3bc63-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="3bc63-114">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册**。</span><span class="sxs-lookup"><span data-stu-id="3bc63-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的图像和应用程序注册导航](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="3bc63-116">在注册表单中，选择应用程序的名称，然后选择"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="3bc63-117">选择重定向 URI 是可选的。</span><span class="sxs-lookup"><span data-stu-id="3bc63-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="3bc63-118">完成此示例不需要一个。</span><span class="sxs-lookup"><span data-stu-id="3bc63-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="3bc63-119">在应用程序页面上，选择 **"API** 权限""添加我的组织使用>  >    >   API"，键入 **"Microsoft 威胁** 防护"，然后选择 **"Microsoft 威胁防护"。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="3bc63-120">你的应用现在可以访问 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="3bc63-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="3bc63-121">*Microsoft 威胁防护* 是 Microsoft 365 Defender 的以前名称，不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="3bc63-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="3bc63-122">你需要开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="3bc63-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="3bc63-123">![API 权限选择的图像](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="3bc63-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="3bc63-124">选择 **"应用程序权限**  >  **""Incident.Read.All"，** 然后选择"**添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="3bc63-126">选择 **"授予管理员同意"。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="3bc63-127">每次添加权限时，都必须选择"授予管理员 **同意** ，让权限生效"。</span><span class="sxs-lookup"><span data-stu-id="3bc63-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![授予权限的图像](../../media/grant-consent.PNG)

6. <span data-ttu-id="3bc63-129">向应用程序添加密码。</span><span class="sxs-lookup"><span data-stu-id="3bc63-129">Add a secret to the application.</span></span> <span data-ttu-id="3bc63-130">选择 **"&** 密码"，向密码添加说明，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="3bc63-131">选择"添加 **"后**，**选择"复制生成的机密值"。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="3bc63-132">离开后将无法检索密码值。</span><span class="sxs-lookup"><span data-stu-id="3bc63-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![创建应用密钥的图像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="3bc63-134">在安全的地方记录应用程序 ID 和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="3bc63-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="3bc63-135">它们列在应用程序 **页面上的"** 概述"下。</span><span class="sxs-lookup"><span data-stu-id="3bc63-135">They're listed under **Overview** on your application page.</span></span>

   ![已创建应用 ID 的图像](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="3bc63-137">使用应用获取令牌，并使用令牌访问 API</span><span class="sxs-lookup"><span data-stu-id="3bc63-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="3bc63-138">有关 Azure Active Directory 令牌详细信息，请参阅 [Azure AD 教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="3bc63-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bc63-139">尽管此演示应用中的示例鼓励你为了测试目的粘贴密码值，但不应将密码硬编码为在生产中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bc63-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="3bc63-140">第三方可以使用你的密码访问资源。</span><span class="sxs-lookup"><span data-stu-id="3bc63-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="3bc63-141">通过使用 Azure 密钥保管库，可帮助保护 [应用密钥的安全](/azure/key-vault/general/about-keys-secrets-certificates)。</span><span class="sxs-lookup"><span data-stu-id="3bc63-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="3bc63-142">有关如何保护应用的实际示例，请参阅使用 Azure Key Vault 管理 [服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="3bc63-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="3bc63-143">复制下面的脚本并将其粘贴到最喜爱的文本编辑器中。</span><span class="sxs-lookup"><span data-stu-id="3bc63-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="3bc63-144">另存 **为Get-Token.ps1。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="3bc63-145">您还可以在 PowerShell ISE 中像现在一样运行代码，但应保存它，因为我们将在下一节中使用事件提取脚本时再次运行它。</span><span class="sxs-lookup"><span data-stu-id="3bc63-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="3bc63-146">此脚本将生成一个令牌，并将其保存在工作文件夹中的名称下 *，Latest-token.txt。*</span><span class="sxs-lookup"><span data-stu-id="3bc63-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a><span data-ttu-id="3bc63-147">验证令牌</span><span class="sxs-lookup"><span data-stu-id="3bc63-147">Validate the token</span></span>

1. <span data-ttu-id="3bc63-148">将收到的令牌复制并粘贴到 [JWT](https://jwt.ms) 中以解码它。</span><span class="sxs-lookup"><span data-stu-id="3bc63-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="3bc63-149">*JWT* 表示 *JSON Web 令牌*。</span><span class="sxs-lookup"><span data-stu-id="3bc63-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="3bc63-150">解码的令牌将包含许多 JSON 格式的项目或声明。</span><span class="sxs-lookup"><span data-stu-id="3bc63-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="3bc63-151">确保解码 *令牌* 中的角色声明包含所需的权限。</span><span class="sxs-lookup"><span data-stu-id="3bc63-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="3bc63-152">在下图中，你可以看到从应用获取的解码令牌，具有 、 和 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 权限：</span><span class="sxs-lookup"><span data-stu-id="3bc63-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![图像 jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="3bc63-154">获取最近事件的列表</span><span class="sxs-lookup"><span data-stu-id="3bc63-154">Get a list of recent incidents</span></span>

<span data-ttu-id="3bc63-155">下面的 **脚本将使用Get-Token.ps1** 访问 API。</span><span class="sxs-lookup"><span data-stu-id="3bc63-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="3bc63-156">然后，它将检索过去 48 小时内最后更新的事件列表，然后将该列表另存为 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="3bc63-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bc63-157">在保存脚本的同一文件夹中保存此 **Get-Token.ps1。**</span><span class="sxs-lookup"><span data-stu-id="3bc63-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="3bc63-158">全部完成！</span><span class="sxs-lookup"><span data-stu-id="3bc63-158">You're all done!</span></span> <span data-ttu-id="3bc63-159">已成功：</span><span class="sxs-lookup"><span data-stu-id="3bc63-159">You've successfully:</span></span>

- <span data-ttu-id="3bc63-160">创建并注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bc63-160">Created and registered an application.</span></span>
- <span data-ttu-id="3bc63-161">已授予该应用程序读取警报的权限。</span><span class="sxs-lookup"><span data-stu-id="3bc63-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="3bc63-162">已连接到 API。</span><span class="sxs-lookup"><span data-stu-id="3bc63-162">Connected to the API.</span></span>
- <span data-ttu-id="3bc63-163">使用 PowerShell 脚本返回过去 48 小时内更新的事件。</span><span class="sxs-lookup"><span data-stu-id="3bc63-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3bc63-164">相关文章</span><span class="sxs-lookup"><span data-stu-id="3bc63-164">Related articles</span></span>

- [<span data-ttu-id="3bc63-165">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="3bc63-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="3bc63-166">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="3bc63-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3bc63-167">创建应用以在没有用户的情况下访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bc63-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="3bc63-168">创建应用以代表用户访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="3bc63-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="3bc63-169">创建具有对 Microsoft 365 Defender API 的多租户合作伙伴访问权限的应用</span><span class="sxs-lookup"><span data-stu-id="3bc63-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="3bc63-170">使用 Azure Key Vault 管理服务器应用中的密钥</span><span class="sxs-lookup"><span data-stu-id="3bc63-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="3bc63-171">OAuth 2.0 用户登录和 API 访问授权</span><span class="sxs-lookup"><span data-stu-id="3bc63-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)