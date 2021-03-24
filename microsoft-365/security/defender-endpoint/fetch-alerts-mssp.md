---
title: 从 MSSP 客户租户提取警报
description: 了解如何从客户租户获取警报
keywords: 托管安全服务提供程序， mssp， 配置， 集成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee2a5e1815dd552753ac7f3dee30df11ac4332e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056535"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="01b55-104">从 MSSP 客户租户提取警报</span><span class="sxs-lookup"><span data-stu-id="01b55-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="01b55-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="01b55-105">**Applies to:**</span></span>
- [<span data-ttu-id="01b55-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="01b55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="01b55-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="01b55-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01b55-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="01b55-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="01b55-109">此操作由 MSSP 执行。</span><span class="sxs-lookup"><span data-stu-id="01b55-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="01b55-110">有两种方法可以提取警报：</span><span class="sxs-lookup"><span data-stu-id="01b55-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="01b55-111">使用 SIEM 方法</span><span class="sxs-lookup"><span data-stu-id="01b55-111">Using the SIEM method</span></span>
- <span data-ttu-id="01b55-112">使用 API</span><span class="sxs-lookup"><span data-stu-id="01b55-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="01b55-113">将警报提取到 SIEM 中</span><span class="sxs-lookup"><span data-stu-id="01b55-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="01b55-114">若要将警报提取到 SIEM 系统中，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="01b55-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="01b55-115">步骤 1：创建第三方应用程序</span><span class="sxs-lookup"><span data-stu-id="01b55-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="01b55-116">步骤 2：从客户的租户获取访问和刷新令牌</span><span class="sxs-lookup"><span data-stu-id="01b55-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="01b55-117">步骤 3：允许 Microsoft Defender 安全中心上的应用程序</span><span class="sxs-lookup"><span data-stu-id="01b55-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="01b55-118">步骤 1：在 Azure Active Directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="01b55-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="01b55-119">你需要创建一个应用程序，并授予它从客户的适用于终结点租户的 Microsoft Defender 获取警报的权限。</span><span class="sxs-lookup"><span data-stu-id="01b55-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="01b55-120">登录到 Azure [AD 门户](https://aad.portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="01b55-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="01b55-121">选择 **"Azure Active Directory**  >  **应用注册"。**</span><span class="sxs-lookup"><span data-stu-id="01b55-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="01b55-122">单击"**新建注册"。**</span><span class="sxs-lookup"><span data-stu-id="01b55-122">Click **New registration**.</span></span>

4. <span data-ttu-id="01b55-123">指定以下值：</span><span class="sxs-lookup"><span data-stu-id="01b55-123">Specify the following values:</span></span>

    - <span data-ttu-id="01b55-124">名称 \<Tenant_name\> ：SIEM MSSP 连接器 (租户Tenant_name SIEM MSSP 连接器显示名称) </span><span class="sxs-lookup"><span data-stu-id="01b55-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="01b55-125">支持的帐户类型：仅此组织目录中的帐户</span><span class="sxs-lookup"><span data-stu-id="01b55-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="01b55-126">重定向 URI：选择"Web"，然后 `https://<domain_name>/SiemMsspConnector` ("<domain_name>租户名称") </span><span class="sxs-lookup"><span data-stu-id="01b55-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="01b55-127">单击“**注册**”。</span><span class="sxs-lookup"><span data-stu-id="01b55-127">Click **Register**.</span></span> <span data-ttu-id="01b55-128">应用程序显示在你拥有的应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="01b55-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="01b55-129">选择应用程序，然后单击"概述 **"。**</span><span class="sxs-lookup"><span data-stu-id="01b55-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="01b55-130">将值从应用程序客户端 **(ID) 复制到** 安全位置，下一步中将需要此值。</span><span class="sxs-lookup"><span data-stu-id="01b55-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="01b55-131">Select **Certificate & secrets** in the new application panel.</span><span class="sxs-lookup"><span data-stu-id="01b55-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="01b55-132">单击 **"新建客户端密码"。**</span><span class="sxs-lookup"><span data-stu-id="01b55-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="01b55-133">说明：输入密钥的说明。</span><span class="sxs-lookup"><span data-stu-id="01b55-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="01b55-134">过期：在 **1 年后选择**</span><span class="sxs-lookup"><span data-stu-id="01b55-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="01b55-135">单击 **"** 添加"，将客户端密码的值复制到安全位置，下一步中将需要此密码。</span><span class="sxs-lookup"><span data-stu-id="01b55-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="01b55-136">步骤 2：从客户的租户获取访问和刷新令牌</span><span class="sxs-lookup"><span data-stu-id="01b55-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="01b55-137">本部分指导你如何使用 PowerShell 脚本从客户的租户获取令牌。</span><span class="sxs-lookup"><span data-stu-id="01b55-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="01b55-138">此脚本使用上一步中的应用程序，使用 OAuth 授权代码流获取访问令牌和刷新令牌。</span><span class="sxs-lookup"><span data-stu-id="01b55-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="01b55-139">提供凭据后，你需要同意应用程序，以便应用程序在客户的租户中预配。</span><span class="sxs-lookup"><span data-stu-id="01b55-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="01b55-140">创建一个新文件夹，并命名它 `MsspTokensAcquisition` ：。</span><span class="sxs-lookup"><span data-stu-id="01b55-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="01b55-141">下载 [LoginBrowser.psm1 模块](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) 并将其保存在 `MsspTokensAcquisition` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="01b55-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="01b55-142">在行 30 中，将 `authorzationUrl` 替换为 `authorizationUrl` 。</span><span class="sxs-lookup"><span data-stu-id="01b55-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="01b55-143">创建包含以下内容的文件，并将其与文件夹中 `MsspTokensAcquisition.ps1` 的名称一起保存：</span><span class="sxs-lookup"><span data-stu-id="01b55-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="01b55-144">在 文件夹中打开提升的 PowerShell 命令 `MsspTokensAcquisition` 提示符。</span><span class="sxs-lookup"><span data-stu-id="01b55-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="01b55-145">运行以下命令：`Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="01b55-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="01b55-146">输入以下命令： `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="01b55-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="01b55-147">将 \<client_id\> 替换为 **上一 ()** 应用程序客户端客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="01b55-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="01b55-148">将 \<app_key\> 替换为在上一步中创建的客户端密码。</span><span class="sxs-lookup"><span data-stu-id="01b55-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="01b55-149">将 \<customer_tenant_id\> 替换为客户的租户 **ID。**</span><span class="sxs-lookup"><span data-stu-id="01b55-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="01b55-150">你将被要求提供你的凭据和同意。</span><span class="sxs-lookup"><span data-stu-id="01b55-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="01b55-151">忽略页面重定向。</span><span class="sxs-lookup"><span data-stu-id="01b55-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="01b55-152">在 PowerShell 窗口中，您将收到访问令牌和刷新令牌。</span><span class="sxs-lookup"><span data-stu-id="01b55-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="01b55-153">保存刷新令牌以配置 SIEM 连接器。</span><span class="sxs-lookup"><span data-stu-id="01b55-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="01b55-154">步骤 3：允许 Microsoft Defender 安全中心上的应用程序</span><span class="sxs-lookup"><span data-stu-id="01b55-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="01b55-155">你需要允许你在 Microsoft Defender 安全中心中创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="01b55-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="01b55-156">你需要具有管理门户 **系统设置权限** 才能允许应用程序。</span><span class="sxs-lookup"><span data-stu-id="01b55-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="01b55-157">否则，你将需要请求客户允许应用。</span><span class="sxs-lookup"><span data-stu-id="01b55-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="01b55-158">转到 `https://securitycenter.windows.com?tid=<customer_tenant_id>` (客户租户 ID \<customer_tenant_id\> 替换。</span><span class="sxs-lookup"><span data-stu-id="01b55-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="01b55-159">单击 **设置**  >  **SIEM**。</span><span class="sxs-lookup"><span data-stu-id="01b55-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="01b55-160">选择 **"MSSP"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="01b55-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="01b55-161">输入 **第一步** 中的应用程序 ID 和租户 **ID。**</span><span class="sxs-lookup"><span data-stu-id="01b55-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="01b55-162">单击"**授权应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="01b55-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="01b55-163">现在，你可以下载 SIEM 的相关配置文件并连接到 Defender for Endpoint API。</span><span class="sxs-lookup"><span data-stu-id="01b55-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="01b55-164">有关详细信息，请参阅将 [警报拉取到 SIEM 工具](configure-siem.md)。</span><span class="sxs-lookup"><span data-stu-id="01b55-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="01b55-165">在 ArcSight 配置文件/Splunk 身份验证属性文件中，通过设置密码值手动编写应用程序密钥。</span><span class="sxs-lookup"><span data-stu-id="01b55-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="01b55-166">使用上一步中的脚本获取刷新令牌，而不是在门户中获取刷新令牌 (或通过其他方法获取刷新) 。</span><span class="sxs-lookup"><span data-stu-id="01b55-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="01b55-167">使用 API 从 MSSP 客户的租户提取警报</span><span class="sxs-lookup"><span data-stu-id="01b55-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="01b55-168">有关如何使用 REST API 获取警报的信息，请参阅 [使用 REST API 拉取警报](pull-alerts-using-rest-api.md)。</span><span class="sxs-lookup"><span data-stu-id="01b55-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="01b55-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01b55-169">See also</span></span>
- [<span data-ttu-id="01b55-170">授予对门户的 MSSP 访问权限</span><span class="sxs-lookup"><span data-stu-id="01b55-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="01b55-171">访问 MSSP 客户门户</span><span class="sxs-lookup"><span data-stu-id="01b55-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="01b55-172">配置警报通知</span><span class="sxs-lookup"><span data-stu-id="01b55-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
