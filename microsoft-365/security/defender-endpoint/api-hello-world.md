---
title: 适用于终结点 API 的 Microsoft Defender Hello World
ms.reviewer: ''
description: 创建对 Microsoft Defender for Endpoint API 的"Hello world"样式 API 调用做法。
keywords: api， 受支持的 api， 高级搜寻， 查询， microsoft defender atp， microsoft defender for endpoint
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1e04c9a817bfe799c15e3609e190980bfc4145e7
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58550282"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>Microsoft Defender for Endpoint API - Hello World

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)


- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>使用简单的 PowerShell 脚本获取警报

### <a name="how-long-it-takes-to-go-through-this-example"></a>完成此示例需要多久？

只需两个步骤，只需 5 分钟即可完成：

- 应用程序注册
- 使用示例：仅需要复制/粘贴短 PowerShell 脚本

### <a name="do-i-need-a-permission-to-connect"></a>是否需要连接权限？

对于应用程序注册阶段，你必须在 Azure  AD 租户Azure Active Directory (全局) 角色。

### <a name="step-1---create-an-app-in-azure-active-directory"></a>步骤 1 - 在 Azure Active Directory

1. 使用全局管理员 **用户登录到** [Azure。](https://portal.azure.com)

2. 导航到 **Azure Active Directory** \> **应用注册** \> **""新注册"。**

   ![应用程序注册Microsoft Azure导航的图像。](images/atp-azure-new-app2.png)

3. 在注册表单中，为应用程序选择一个名称，然后单击"注册 **"。**

4. 允许应用程序访问适用于终结点的 Defender，并为其分配 **"读取所有警报"** 权限：

   - 在应用程序页面上，单击 **"API** 权限""添加我的组织使用的权限 \>  \> API"> **WindowsDefenderATP"，** 然后单击 **"WindowsDefenderATP"。**

   - **注意**：WindowsDefenderATP 不会显示在原始列表中。 你需要开始在文本框中写入其名称，以查看其显示。

   ![API 访问和 API 选择 1 的图像。](images/add-permission.png)

   - Choose **Application permissions** \> **Alert.Read.All** > Click on **Add permissions**

   ![API 访问和 API 选择 2 的图像。](images/application-permissions.png)

   **重要说明**：需要选择相关权限。 "读取所有警报"只是一个示例！

     例如，

     - 若要 [运行高级查询，请选择](run-advanced-query-api.md)"运行高级查询"权限
     - 若要 [隔离计算机，](isolate-machine.md)请选择"隔离计算机"权限
     - 若要确定所需的权限，请查看你感兴趣的 API中的权限部分。

5. 单击 **"授予同意"**

   - **注意**：每次添加权限时，都必须单击"授予 **许可** ，让新权限生效"。

   ![授予权限的图像。](images/grant-consent.png)

6. 向应用程序添加密码。

   - 单击 **"&密码"，** 将说明添加到密码，然后单击"添加 **"。**

    **重要** 提示：单击"添加" **后，复制生成的机密值**。 离开后将无法检索！

    ![创建应用密钥的图像。](images/webapp-create-key2.png)

7. 记下应用程序 ID 和租户 ID：

   - 在应用程序页上，转到" **概述"** 并复制以下内容：

   ![已创建应用 ID 的图像。](images/app-and-tenant-ids.png)

完成！ 已成功注册应用程序！

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>步骤 2 - 使用应用获取令牌，并使用此令牌访问 API。

- 将下面的脚本复制到 PowerShell ISE 或文本编辑器，并将其另存为 **"Get-Token.ps1"**
- 运行此脚本将生成一个令牌，并将其保存在名称"Latest-token.txt"**下的工作** 文件夹中。

   ```powershell
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

- 有效性检查：
  - 运行脚本。
  - 在浏览器中转到： <https://jwt.ms/>
  - 复制令牌 (文件Latest-token.txt的内容) 。
  - 粘贴到顶部框中。
  - 查找"角色"部分。 查找 Alert.Read.All 角色。

  ![图像 jwt.ms。](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a>让我们获取警报！

- 下面的 **脚本将使用** Get-Token.ps1访问 API，并获取过去 48 小时的警报。
- 在保存上一脚本的同一文件夹中保存 **此脚本** Get-Token.ps1。
- 该脚本创建两 (json 和 csv) 文件，其中数据与脚本在同一文件夹中。

  ```powershell
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

全部完成！ 你已成功：

- 创建和注册以及应用程序
- 已授予该应用程序读取警报的权限
- 已连接 API
- 使用 PowerShell 脚本返回过去 48 小时内创建的警报

## <a name="related-topic"></a>相关主题

- [适用于终结点的 Microsoft Defender API](exposed-apis-list.md)
- [使用应用程序上下文访问 Microsoft Defender for Endpoint](exposed-apis-create-app-webapp.md)
- [使用用户上下文访问 Microsoft Defender for Endpoint](exposed-apis-create-app-nativeapp.md)
