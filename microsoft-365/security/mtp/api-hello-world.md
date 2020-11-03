---
title: Microsoft 365 Defender REST API 的 Hello World 版
description: 了解如何创建应用程序并使用令牌访问 Microsoft 365 Defender Api
keywords: 应用程序、令牌、访问、aad、应用程序、应用程序注册、powershell、脚本、全局管理员、权限
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
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844040"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="499b2-104">Microsoft 365 Defender REST API 的 Hello World 版</span><span class="sxs-lookup"><span data-stu-id="499b2-104">Hello World for Microsoft 365 Defender REST API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="499b2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="499b2-105">**Applies to:**</span></span>
- <span data-ttu-id="499b2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="499b2-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="499b2-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="499b2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="499b2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="499b2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="499b2-109">使用简单 PowerShell 脚本获取事件</span><span class="sxs-lookup"><span data-stu-id="499b2-109">Get incidents using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="499b2-110">此示例需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="499b2-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="499b2-111">只需完成以下两个步骤，即可完成5分钟：</span><span class="sxs-lookup"><span data-stu-id="499b2-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="499b2-112">应用程序注册</span><span class="sxs-lookup"><span data-stu-id="499b2-112">Application registration</span></span>
- <span data-ttu-id="499b2-113">使用示例：仅需要复制/粘贴短 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="499b2-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="499b2-114">我是否需要权限才能连接？</span><span class="sxs-lookup"><span data-stu-id="499b2-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="499b2-115">对于 "应用程序注册" 阶段，您必须在 Azure Active Directory 中具有 **全局管理员** 角色 (azure AD) 租户。</span><span class="sxs-lookup"><span data-stu-id="499b2-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="499b2-116">步骤 1-在 Azure Active Directory 中创建应用</span><span class="sxs-lookup"><span data-stu-id="499b2-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="499b2-117">使用 **全局管理员** 用户登录到 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="499b2-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="499b2-118">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册** 。</span><span class="sxs-lookup"><span data-stu-id="499b2-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的图像和到应用程序注册的导航](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="499b2-120">在 "注册" 表单中，选择应用程序的名称，然后选择 " **注册** "。</span><span class="sxs-lookup"><span data-stu-id="499b2-120">In the registration form, choose a name for your application and then select **Register**.</span></span>

4. <span data-ttu-id="499b2-121">允许应用程序访问 Microsoft Defender for Endpoint 并将其分配为 " **读取所有事件** " 权限：</span><span class="sxs-lookup"><span data-stu-id="499b2-121">Allow your Application to access Microsoft Defender for Endpoint and assign it **Read all incidents** permission:</span></span>

   - <span data-ttu-id="499b2-122">在应用程序页上，选择 " **API 权限**  >  **Add permission**  >  **" "添加我的组织使用的权限 api"** > 键入 **microsoft 365 defender** 并在 **microsoft 365 defender** 上选择。</span><span class="sxs-lookup"><span data-stu-id="499b2-122">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft 365 Defender** and select on **Microsoft 365 Defender**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="499b2-123">Microsoft 365 Defender 不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="499b2-123">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="499b2-124">您需要先在文本框中写入其名称，才能看到它的显示。</span><span class="sxs-lookup"><span data-stu-id="499b2-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 访问和 API 选择的图像](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="499b2-126">选择 " **应用程序权限**  >  **事件"。读取。所有** > 选择 " **添加权限** "</span><span class="sxs-lookup"><span data-stu-id="499b2-126">Choose **Application permissions** > **Incident.Read.All** > Select on **Add permissions**</span></span>

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   ><span data-ttu-id="499b2-128">您需要选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="499b2-128">You need to select the relevant permissions.</span></span> 

     <span data-ttu-id="499b2-129">例如，</span><span class="sxs-lookup"><span data-stu-id="499b2-129">For instance,</span></span>

     - <span data-ttu-id="499b2-130">若要确定所需的权限，请查看您想要调用的 API 中的 " **权限** " 部分。</span><span class="sxs-lookup"><span data-stu-id="499b2-130">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="499b2-131">选择 " **授予管理员同意** "</span><span class="sxs-lookup"><span data-stu-id="499b2-131">Select **Grant admin consent**</span></span>

    - >[!NOTE]
      > <span data-ttu-id="499b2-132">每次添加权限时，您都必须选择 " **授予许可** " 以使新权限生效。</span><span class="sxs-lookup"><span data-stu-id="499b2-132">Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![授予权限的图像](../../media/grant-consent.PNG)

6. <span data-ttu-id="499b2-134">向应用程序添加密码。</span><span class="sxs-lookup"><span data-stu-id="499b2-134">Add a secret to the application.</span></span>

    - <span data-ttu-id="499b2-135">选择 " **证书" & 密码** ，将 "说明" 添加到密码，然后选择 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="499b2-135">Select **Certificates & secrets** , add description to the secret and select **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="499b2-136">选择 " **添加** " 后， **复制生成的机密值** 。</span><span class="sxs-lookup"><span data-stu-id="499b2-136">After selecting **Add** , **copy the generated secret value**.</span></span> <span data-ttu-id="499b2-137">你不能在离开后检索！</span><span class="sxs-lookup"><span data-stu-id="499b2-137">You won't be able to retrieve after you leave!</span></span>

    ![创建应用程序密钥的图像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="499b2-139">记下应用程序 ID 和租户 ID：</span><span class="sxs-lookup"><span data-stu-id="499b2-139">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="499b2-140">在应用程序页上，转到 " **概述** " 并复制以下内容：</span><span class="sxs-lookup"><span data-stu-id="499b2-140">On your application page, go to **Overview** and copy the following:</span></span>

   ![已创建应用程序 id 的图像](../../media/app-and-tenant-ids.png)


<span data-ttu-id="499b2-142">为了!</span><span class="sxs-lookup"><span data-stu-id="499b2-142">Done!</span></span> <span data-ttu-id="499b2-143">已成功注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="499b2-143">You have successfully registered an application.</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="499b2-144">步骤 2-使用应用程序获取令牌，并使用此令牌访问 API。</span><span class="sxs-lookup"><span data-stu-id="499b2-144">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="499b2-145">将下面的脚本复制到 PowerShell ISE 或文本编辑器，并将其另存为 " **Get-Token.ps1** "</span><span class="sxs-lookup"><span data-stu-id="499b2-145">Copy the script below to PowerShell ISE or to a text editor, and save it as " **Get-Token.ps1** "</span></span>
-   <span data-ttu-id="499b2-146">运行此脚本将生成一个令牌，并将其保存到名称为 " **Latest-token.txt** " 下的工作文件夹中。</span><span class="sxs-lookup"><span data-stu-id="499b2-146">Running this script will generate a token and will save it in the working folder under the name " **Latest-token.txt** ".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

-   <span data-ttu-id="499b2-147">健全性检查：</span><span class="sxs-lookup"><span data-stu-id="499b2-147">Sanity Check:</span></span><br>
<span data-ttu-id="499b2-148">运行脚本。</span><span class="sxs-lookup"><span data-stu-id="499b2-148">Run the script.</span></span><br>
<span data-ttu-id="499b2-149">在浏览器中，转到： https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="499b2-149">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="499b2-150">将令牌复制 (Latest-token.txt 文件的内容) 。</span><span class="sxs-lookup"><span data-stu-id="499b2-150">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="499b2-151">粘贴在顶部的框中。</span><span class="sxs-lookup"><span data-stu-id="499b2-151">Paste in the top box.</span></span><br>
<span data-ttu-id="499b2-152">查找 "角色" 部分。</span><span class="sxs-lookup"><span data-stu-id="499b2-152">Look for the "roles" section.</span></span> <span data-ttu-id="499b2-153">查找 ```Incidents.Read.All``` 角色。</span><span class="sxs-lookup"><span data-stu-id="499b2-153">Find the ```Incidents.Read.All``` role.</span></span><br>
<span data-ttu-id="499b2-154">下面的示例来自具有和权限的应用 ```Incidents.Read.All``` 程序 ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 。</span><span class="sxs-lookup"><span data-stu-id="499b2-154">The below example is from an app that has ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions.</span></span>

![图像 jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a><span data-ttu-id="499b2-156">允许你获取事件！</span><span class="sxs-lookup"><span data-stu-id="499b2-156">Lets get the Incidents!</span></span>

-   <span data-ttu-id="499b2-157">下面的脚本将使用 **Get-Token.ps1** 访问 API，并将在过去的48小时内获得最后更新的事件。</span><span class="sxs-lookup"><span data-stu-id="499b2-157">The script below will use **Get-Token.ps1** to access the API and will get the incidents last updated in past 48 hours.</span></span>
-   <span data-ttu-id="499b2-158">将此脚本保存在保存以前的脚本 **Get-Token.ps1** 的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="499b2-158">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="499b2-159">脚本中包含数据的 json 文件与脚本位于同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="499b2-159">The script a json file with the data in the same folder as the scripts.</span></span>

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

<span data-ttu-id="499b2-160">你已经完成了！</span><span class="sxs-lookup"><span data-stu-id="499b2-160">You're all done!</span></span> <span data-ttu-id="499b2-161">您已成功：</span><span class="sxs-lookup"><span data-stu-id="499b2-161">You have just successfully:</span></span>
-   <span data-ttu-id="499b2-162">创建并注册和应用</span><span class="sxs-lookup"><span data-stu-id="499b2-162">Created and registered and application</span></span>
-   <span data-ttu-id="499b2-163">授予该应用程序阅读通知的权限</span><span class="sxs-lookup"><span data-stu-id="499b2-163">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="499b2-164">已连接 API</span><span class="sxs-lookup"><span data-stu-id="499b2-164">Connected the API</span></span>
-   <span data-ttu-id="499b2-165">使用 PowerShell 脚本返回在过去48小时内创建的事件</span><span class="sxs-lookup"><span data-stu-id="499b2-165">Used a PowerShell script to return incidents created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="499b2-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="499b2-166">Related topic</span></span>
- [<span data-ttu-id="499b2-167">访问 Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="499b2-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="499b2-168">使用应用程序上下文访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="499b2-168">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="499b2-169">使用用户上下文访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="499b2-169">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
