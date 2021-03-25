---
title: 适用于终结点 API 的 Microsoft Defender Hello World
ms.reviewer: ''
description: 通过 Microsoft Defender ATP api 创建对 Microsoft Defender for Endpoint ("Hello world") API 调用。
keywords: api， 受支持的 api， 高级搜寻， 查询
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3b076d0fa6e01be2a810e8fa810cc3e32955388e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199642"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a><span data-ttu-id="4d0df-104">Microsoft Defender for Endpoint API - Hello World</span><span class="sxs-lookup"><span data-stu-id="4d0df-104">Microsoft Defender for Endpoint API - Hello World</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4d0df-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4d0df-105">**Applies to:**</span></span> 
- [<span data-ttu-id="4d0df-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4d0df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


- <span data-ttu-id="4d0df-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4d0df-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d0df-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4d0df-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a><span data-ttu-id="4d0df-109">使用简单的 PowerShell 脚本获取警报</span><span class="sxs-lookup"><span data-stu-id="4d0df-109">Get Alerts using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="4d0df-110">完成此示例需要多久？</span><span class="sxs-lookup"><span data-stu-id="4d0df-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="4d0df-111">只需两个步骤，只需 5 分钟即可完成：</span><span class="sxs-lookup"><span data-stu-id="4d0df-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="4d0df-112">应用程序注册</span><span class="sxs-lookup"><span data-stu-id="4d0df-112">Application registration</span></span>
- <span data-ttu-id="4d0df-113">使用示例：仅需要复制/粘贴短 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="4d0df-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="4d0df-114">是否需要连接权限？</span><span class="sxs-lookup"><span data-stu-id="4d0df-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="4d0df-115">对于应用程序注册阶段，你必须在 Azure  AD 租户的 Azure Active Directory (全局) 角色。</span><span class="sxs-lookup"><span data-stu-id="4d0df-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="4d0df-116">步骤 1 - 在 Azure Active Directory 中创建应用</span><span class="sxs-lookup"><span data-stu-id="4d0df-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="4d0df-117">使用全局管理员 **用户登录到** [Azure。](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="4d0df-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="4d0df-118">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册**。</span><span class="sxs-lookup"><span data-stu-id="4d0df-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的图像和应用程序注册导航](images/atp-azure-new-app2.png)

3. <span data-ttu-id="4d0df-120">在注册表单中，为应用程序选择一个名称，然后单击"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="4d0df-120">In the registration form, choose a name for your application and then click **Register**.</span></span>

4. <span data-ttu-id="4d0df-121">允许应用程序访问适用于终结点的 Defender，并为其分配 **"读取所有警报"** 权限：</span><span class="sxs-lookup"><span data-stu-id="4d0df-121">Allow your Application to access Defender for Endpoint and assign it **'Read all alerts'** permission:</span></span>

   - <span data-ttu-id="4d0df-122">在应用程序页面上，单击 **"API** 权限""添加我的组织使用的权限  >    >  API"> **WindowsDefenderATP"，** 然后单击 **"WindowsDefenderATP"。**</span><span class="sxs-lookup"><span data-stu-id="4d0df-122">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and click on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="4d0df-123">**注意**：WindowsDefenderATP 不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="4d0df-123">**Note**: WindowsDefenderATP does not appear in the original list.</span></span> <span data-ttu-id="4d0df-124">你需要开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="4d0df-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 访问和 API 选择的图像1](images/add-permission.png)

   - <span data-ttu-id="4d0df-126">Choose **Application permissions**  >  **Alert.Read.All** > Click on **Add permissions**</span><span class="sxs-lookup"><span data-stu-id="4d0df-126">Choose **Application permissions** > **Alert.Read.All** > Click on **Add permissions**</span></span>

   ![API 访问和 API 选择的图像2](images/application-permissions.png)

   <span data-ttu-id="4d0df-128">**重要说明**：需要选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="4d0df-128">**Important note**: You need to select the relevant permissions.</span></span> <span data-ttu-id="4d0df-129">"读取所有警报"只是一个示例！</span><span class="sxs-lookup"><span data-stu-id="4d0df-129">'Read All Alerts' is only an example!</span></span>

     <span data-ttu-id="4d0df-130">例如，</span><span class="sxs-lookup"><span data-stu-id="4d0df-130">For instance,</span></span>

     - <span data-ttu-id="4d0df-131">若要 [运行高级查询，请选择](run-advanced-query-api.md)"运行高级查询"权限</span><span class="sxs-lookup"><span data-stu-id="4d0df-131">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
     - <span data-ttu-id="4d0df-132">若要 [隔离计算机，](isolate-machine.md)请选择"隔离计算机"权限</span><span class="sxs-lookup"><span data-stu-id="4d0df-132">To [isolate a machine](isolate-machine.md), select 'Isolate machine' permission</span></span>
     - <span data-ttu-id="4d0df-133">若要确定所需的权限，请查看你感兴趣的 API中的权限部分。</span><span class="sxs-lookup"><span data-stu-id="4d0df-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="4d0df-134">单击 **"授予同意"**</span><span class="sxs-lookup"><span data-stu-id="4d0df-134">Click **Grant consent**</span></span>

    - <span data-ttu-id="4d0df-135">**注意**：每次添加权限时，都必须单击"授予 **许可** ，让新权限生效"。</span><span class="sxs-lookup"><span data-stu-id="4d0df-135">**Note**: Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![授予权限的图像](images/grant-consent.png)

6. <span data-ttu-id="4d0df-137">向应用程序添加密码。</span><span class="sxs-lookup"><span data-stu-id="4d0df-137">Add a secret to the application.</span></span>

    - <span data-ttu-id="4d0df-138">单击 **"&** 密码"，将说明添加到密码，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="4d0df-138">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    <span data-ttu-id="4d0df-139">**重要** 提示：单击"添加" **后，复制生成的机密值**。</span><span class="sxs-lookup"><span data-stu-id="4d0df-139">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="4d0df-140">离开后将无法检索！</span><span class="sxs-lookup"><span data-stu-id="4d0df-140">You won't be able to retrieve after you leave!</span></span>

    ![创建应用密钥的图像](images/webapp-create-key2.png)

7. <span data-ttu-id="4d0df-142">记下应用程序 ID 和租户 ID：</span><span class="sxs-lookup"><span data-stu-id="4d0df-142">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="4d0df-143">在应用程序页上，转到" **概述"** 并复制以下内容：</span><span class="sxs-lookup"><span data-stu-id="4d0df-143">On your application page, go to **Overview** and copy the following:</span></span>

   ![已创建应用 ID 的图像](images/app-and-tenant-ids.png)


<span data-ttu-id="4d0df-145">完成！</span><span class="sxs-lookup"><span data-stu-id="4d0df-145">Done!</span></span> <span data-ttu-id="4d0df-146">已成功注册应用程序！</span><span class="sxs-lookup"><span data-stu-id="4d0df-146">You have successfully registered an application!</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="4d0df-147">步骤 2 - 使用应用获取令牌，并使用此令牌访问 API。</span><span class="sxs-lookup"><span data-stu-id="4d0df-147">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="4d0df-148">将下面的脚本复制到 PowerShell ISE 或文本编辑器，并将其另存为 **"Get-Token.ps1"**</span><span class="sxs-lookup"><span data-stu-id="4d0df-148">Copy the script below to PowerShell ISE or to a text editor, and save it as "**Get-Token.ps1**"</span></span>
-   <span data-ttu-id="4d0df-149">运行此脚本将生成一个令牌，并将其保存在名称"Latest-token.txt"**下的工作** 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4d0df-149">Running this script will generate a token and will save it in the working folder under the name "**Latest-token.txt**".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
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

-   <span data-ttu-id="4d0df-150">有效性检查：</span><span class="sxs-lookup"><span data-stu-id="4d0df-150">Sanity Check:</span></span><br>
<span data-ttu-id="4d0df-151">运行脚本。</span><span class="sxs-lookup"><span data-stu-id="4d0df-151">Run the script.</span></span><br>
<span data-ttu-id="4d0df-152">在浏览器中转到： https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="4d0df-152">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="4d0df-153">复制令牌 (文件Latest-token.txt的内容) 。</span><span class="sxs-lookup"><span data-stu-id="4d0df-153">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="4d0df-154">粘贴到顶部框中。</span><span class="sxs-lookup"><span data-stu-id="4d0df-154">Paste in the top box.</span></span><br>
<span data-ttu-id="4d0df-155">查找"角色"部分。</span><span class="sxs-lookup"><span data-stu-id="4d0df-155">Look for the "roles" section.</span></span> <span data-ttu-id="4d0df-156">查找 Alert.Read.All 角色。</span><span class="sxs-lookup"><span data-stu-id="4d0df-156">Find the Alert.Read.All role.</span></span>

![图像 jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a><span data-ttu-id="4d0df-158">让我们获取警报！</span><span class="sxs-lookup"><span data-stu-id="4d0df-158">Lets get the Alerts!</span></span>

-   <span data-ttu-id="4d0df-159">以下 **脚本将使用** Get-Token.ps1访问 API，并获取过去 48 小时的警报。</span><span class="sxs-lookup"><span data-stu-id="4d0df-159">The script below will use **Get-Token.ps1** to access the API and will get the past 48 hours Alerts.</span></span>
-   <span data-ttu-id="4d0df-160">将此脚本保存在保存上一脚本的同一文件夹中 **Get-Token.ps1。**</span><span class="sxs-lookup"><span data-stu-id="4d0df-160">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="4d0df-161">该脚本创建两 (json 和 csv) 文件，其中数据与脚本在同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4d0df-161">The script creates two files (json and csv) with the data in the same folder as the scripts.</span></span>

```
# Returns Alerts created in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")       

# The URL contains the type of query and the time filter we create above
# Read more about other query options and filters at   Https://TBD- add the documentation link
$url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the alerts from the results. 
$alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json and as csv
$outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation 
```

<span data-ttu-id="4d0df-162">全部完成！</span><span class="sxs-lookup"><span data-stu-id="4d0df-162">You’re all done!</span></span> <span data-ttu-id="4d0df-163">你已成功：</span><span class="sxs-lookup"><span data-stu-id="4d0df-163">You have just successfully:</span></span>
-   <span data-ttu-id="4d0df-164">创建和注册以及应用程序</span><span class="sxs-lookup"><span data-stu-id="4d0df-164">Created and registered and application</span></span>
-   <span data-ttu-id="4d0df-165">已授予该应用程序读取警报的权限</span><span class="sxs-lookup"><span data-stu-id="4d0df-165">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="4d0df-166">已连接 API</span><span class="sxs-lookup"><span data-stu-id="4d0df-166">Connected the API</span></span>
-   <span data-ttu-id="4d0df-167">使用 PowerShell 脚本返回过去 48 小时内创建的警报</span><span class="sxs-lookup"><span data-stu-id="4d0df-167">Used a PowerShell script to return alerts created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="4d0df-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d0df-168">Related topic</span></span>
- [<span data-ttu-id="4d0df-169">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="4d0df-169">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="4d0df-170">使用应用程序上下文访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4d0df-170">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="4d0df-171">使用用户上下文访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4d0df-171">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
