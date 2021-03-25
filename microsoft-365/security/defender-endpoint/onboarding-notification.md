---
title: 创建载入或载出通知规则
description: 在使用本地载入或载出脚本时获取通知。
keywords: 载入， 载出， 本地， 脚本， 通知， 规则
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
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187062"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a><span data-ttu-id="b8786-104">使用本地载入或载出脚本时创建通知规则</span><span class="sxs-lookup"><span data-stu-id="b8786-104">Create a notification rule when a local onboarding or offboarding script is used</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8786-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b8786-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8786-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b8786-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8786-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8786-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="b8786-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b8786-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b8786-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b8786-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="b8786-110">创建通知规则，以便当使用本地载入或载出脚本时，将通知你。</span><span class="sxs-lookup"><span data-stu-id="b8786-110">Create a notification rule so that when a local onboarding or offboarding script is used, you'll be notified.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="b8786-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="b8786-111">Before you begin</span></span>
<span data-ttu-id="b8786-112">你将需要有权访问：</span><span class="sxs-lookup"><span data-stu-id="b8786-112">You'll need to have access to:</span></span>
 - <span data-ttu-id="b8786-113">Microsoft Flow (Flow Plan 1 至少为) 。</span><span class="sxs-lookup"><span data-stu-id="b8786-113">Microsoft Flow (Flow Plan 1 at a minimum).</span></span> <span data-ttu-id="b8786-114">有关详细信息，请参阅 Flow [pricing page](https://flow.microsoft.com/pricing/)。</span><span class="sxs-lookup"><span data-stu-id="b8786-114">For more information, see [Flow pricing page](https://flow.microsoft.com/pricing/).</span></span>
 - <span data-ttu-id="b8786-115">Azure 表或 SharePoint 列表或库/SQL DB</span><span class="sxs-lookup"><span data-stu-id="b8786-115">Azure Table or SharePoint List or Library / SQL DB</span></span>

## <a name="create-the-notification-flow"></a><span data-ttu-id="b8786-116">创建通知流</span><span class="sxs-lookup"><span data-stu-id="b8786-116">Create the notification flow</span></span>

1. <span data-ttu-id="b8786-117">在 [flow.microsoft.com](https://flow.microsoft.com/)中。</span><span class="sxs-lookup"><span data-stu-id="b8786-117">In [flow.microsoft.com](https://flow.microsoft.com/).</span></span>

2. <span data-ttu-id="b8786-118">从空白 **导航到"我的>">计划的新流"。**</span><span class="sxs-lookup"><span data-stu-id="b8786-118">Navigate to **My flows > New > Scheduled - from blank**.</span></span> 

    ![流的图像](images/new-flow.png)


3. <span data-ttu-id="b8786-120">构建计划流。</span><span class="sxs-lookup"><span data-stu-id="b8786-120">Build a scheduled flow.</span></span>
   1. <span data-ttu-id="b8786-121">输入流名称。</span><span class="sxs-lookup"><span data-stu-id="b8786-121">Enter a flow name.</span></span>
   2. <span data-ttu-id="b8786-122">指定开始时间和时间。</span><span class="sxs-lookup"><span data-stu-id="b8786-122">Specify the start and time.</span></span>
   3. <span data-ttu-id="b8786-123">指定频率。</span><span class="sxs-lookup"><span data-stu-id="b8786-123">Specify the frequency.</span></span> <span data-ttu-id="b8786-124">例如，每 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="b8786-124">For example, every 5 minutes.</span></span>

    ![通知流的图像](images/build-flow.png)

4. <span data-ttu-id="b8786-126">选择" +"按钮以添加新操作。</span><span class="sxs-lookup"><span data-stu-id="b8786-126">Select the + button to add a new action.</span></span> <span data-ttu-id="b8786-127">新操作将是向 Defender for Endpoint 安全中心设备发送的 HTTP (API) API。</span><span class="sxs-lookup"><span data-stu-id="b8786-127">The new action will be an HTTP request to the Defender for Endpoint security center device(s) API.</span></span> <span data-ttu-id="b8786-128">还可以将其替换为开箱即用"WDATP 连接器" (操作："计算机 - 获取计算机列表") 。</span><span class="sxs-lookup"><span data-stu-id="b8786-128">You can also replace it with the out-of-the-box "WDATP Connector" (action: "Machines - Get list of machines").</span></span> 

    ![重复和添加操作的图像](images/recurrence-add.png)


5. <span data-ttu-id="b8786-130">输入以下 HTTP 字段：</span><span class="sxs-lookup"><span data-stu-id="b8786-130">Enter the following HTTP fields:</span></span>

   - <span data-ttu-id="b8786-131">方法："GET"作为获取设备列表的值。</span><span class="sxs-lookup"><span data-stu-id="b8786-131">Method: "GET" as a value to get the list of devices.</span></span>
   - <span data-ttu-id="b8786-132">URI：输入 `https://api.securitycenter.microsoft.com/api/machines` 。</span><span class="sxs-lookup"><span data-stu-id="b8786-132">URI: Enter `https://api.securitycenter.microsoft.com/api/machines`.</span></span>
   - <span data-ttu-id="b8786-133">身份验证：选择"Active Directory OAuth"。</span><span class="sxs-lookup"><span data-stu-id="b8786-133">Authentication: Select "Active Directory OAuth".</span></span>
   - <span data-ttu-id="b8786-134">租户：登录并导航到 https://portal.azure.com Azure **Active Directory >应用注册并** 获取租户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="b8786-134">Tenant: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>
   - <span data-ttu-id="b8786-135">访问群体： `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span><span class="sxs-lookup"><span data-stu-id="b8786-135">Audience: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span></span>
   - <span data-ttu-id="b8786-136">客户端 ID：登录并导航到 https://portal.azure.com **Azure Active Directory >应用注册并** 获取客户端 ID 值。</span><span class="sxs-lookup"><span data-stu-id="b8786-136">Client ID: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and  get the Client ID value.</span></span>
   - <span data-ttu-id="b8786-137">凭据类型：选择"机密"。</span><span class="sxs-lookup"><span data-stu-id="b8786-137">Credential Type: Select "Secret".</span></span>
   - <span data-ttu-id="b8786-138">密码：登录并导航到 https://portal.azure.com Azure **Active Directory >应用注册并** 获取租户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="b8786-138">Secret: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>

    ![HTTP 条件的图像](images/http-conditions.png)


6. <span data-ttu-id="b8786-140">通过选择"添加新操作"，然后 **搜索"数据** 操作"并选择"**分析 JSON"添加新步骤**。 </span><span class="sxs-lookup"><span data-stu-id="b8786-140">Add a new step by selecting **Add new action** then search for **Data Operations** and select **Parse JSON**.</span></span>

    ![数据操作的图像](images/data-operations.png)

7. <span data-ttu-id="b8786-142">在"内容" **字段中添加** 正文。</span><span class="sxs-lookup"><span data-stu-id="b8786-142">Add Body in the **Content** field.</span></span>

    ![分析 JSON 的图像](images/parse-json.png)

8. <span data-ttu-id="b8786-144">选择" **使用示例有效负载生成架构"** 链接。</span><span class="sxs-lookup"><span data-stu-id="b8786-144">Select the **Use sample payload to generate schema** link.</span></span>

    ![使用有效负载分析 json 的图像](images/parse-json-schema.png)

9. <span data-ttu-id="b8786-146">复制并粘贴以下 JSON 代码段：</span><span class="sxs-lookup"><span data-stu-id="b8786-146">Copy and paste the following JSON snippet:</span></span>

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  <span data-ttu-id="b8786-147">从 JSON 调用中提取值，并检查已载入 (设备) /是否已在 SharePoint 列表中注册为示例：</span><span class="sxs-lookup"><span data-stu-id="b8786-147">Extract the values from the JSON call and check if the onboarded device(s) is / are already registered at the SharePoint list as an example:</span></span>
- <span data-ttu-id="b8786-148">如果是，则不触发任何通知</span><span class="sxs-lookup"><span data-stu-id="b8786-148">If yes, no notification will be triggered</span></span>
- <span data-ttu-id="b8786-149">如果否，将在 SharePoint (注册) 新载入的设备，并且会向 Defender for Endpoint 管理员发送通知</span><span class="sxs-lookup"><span data-stu-id="b8786-149">If no, will register the new onboarded device(s) in the SharePoint list and a notification will be sent to the Defender for Endpoint admin</span></span>

    ![适用于每个图像的图像](images/flow-apply.png)

    ![适用于每个具有 get 项的图像](images/apply-to-each.png)

11. <span data-ttu-id="b8786-152">在 **"条件**"下，添加以下表达式："length (body ('Get_items') ？['value']) "，将条件设置为等于 0。</span><span class="sxs-lookup"><span data-stu-id="b8786-152">Under **Condition**, add the following expression: "length(body('Get_items')?['value'])" and set the condition to equal to 0.</span></span>

    <span data-ttu-id="b8786-153">![适用于每个条件的图像](images/apply-to-each-value.png)</span><span class="sxs-lookup"><span data-stu-id="b8786-153">![Image of apply to each condition](images/apply-to-each-value.png)</span></span>  
    <span data-ttu-id="b8786-154">![condition1 ](images/conditions-2.png) 
     ![ 的图像 condition2 的图像](images/condition3.png)</span><span class="sxs-lookup"><span data-stu-id="b8786-154">![Image of condition1](images/conditions-2.png) 
    ![Image of condition2](images/condition3.png)</span></span>  
<span data-ttu-id="b8786-155">![发送电子邮件的图像](images/send-email.png)</span><span class="sxs-lookup"><span data-stu-id="b8786-155">![Image of send email](images/send-email.png)</span></span>

## <a name="alert-notification"></a><span data-ttu-id="b8786-156">警报通知</span><span class="sxs-lookup"><span data-stu-id="b8786-156">Alert notification</span></span>
<span data-ttu-id="b8786-157">下图是电子邮件通知的一个示例。</span><span class="sxs-lookup"><span data-stu-id="b8786-157">The following image is an example of an email notification.</span></span>

![电子邮件通知的图像](images/alert-notification.png)


## <a name="tips"></a><span data-ttu-id="b8786-159">提示</span><span class="sxs-lookup"><span data-stu-id="b8786-159">Tips</span></span>

- <span data-ttu-id="b8786-160">你可以在此处仅使用 lastSeen 进行筛选：</span><span class="sxs-lookup"><span data-stu-id="b8786-160">You can filter here using lastSeen only:</span></span>
    - <span data-ttu-id="b8786-161">每 60 分钟：</span><span class="sxs-lookup"><span data-stu-id="b8786-161">Every 60 min:</span></span>
      - <span data-ttu-id="b8786-162">使用过去 7 天内最后看到的所有设备。</span><span class="sxs-lookup"><span data-stu-id="b8786-162">Take all devices last seen in the past 7 days.</span></span> 

- <span data-ttu-id="b8786-163">对于每个设备：</span><span class="sxs-lookup"><span data-stu-id="b8786-163">For each device:</span></span> 
    - <span data-ttu-id="b8786-164">如果最后一次看到属性的时间间隔为 [-7 天，-7 天 + 60 分钟 ] ->发生载出可能性的警报。</span><span class="sxs-lookup"><span data-stu-id="b8786-164">If last seen property is on the one hour interval of [-7 days, -7days + 60 minutes ] -> Alert for offboarding possibility.</span></span>
    - <span data-ttu-id="b8786-165">如果第一次看到是过去一小时 ->载入警报。</span><span class="sxs-lookup"><span data-stu-id="b8786-165">If first seen is on the past hour -> Alert for onboarding.</span></span>

<span data-ttu-id="b8786-166">在此解决方案中，你将没有重复的警报：存在具有大量设备的租户。</span><span class="sxs-lookup"><span data-stu-id="b8786-166">In this solution you will not have duplicate alerts: There are tenants that have numerous devices.</span></span> <span data-ttu-id="b8786-167">获取所有这些设备可能非常昂贵，并且可能需要分页。</span><span class="sxs-lookup"><span data-stu-id="b8786-167">Getting all those devices might be very expensive and might require paging.</span></span>

<span data-ttu-id="b8786-168">您可以拆分为两个查询：</span><span class="sxs-lookup"><span data-stu-id="b8786-168">You can split it to two queries:</span></span> 
1.  <span data-ttu-id="b8786-169">对于载出，使用 OData $filter此间隔，并且仅在满足条件时通知。</span><span class="sxs-lookup"><span data-stu-id="b8786-169">For offboarding take only this interval using the OData $filter and only notify if the conditions are met.</span></span>
2.  <span data-ttu-id="b8786-170">查看过去一小时内最后看到的所有设备，并检查第一次看到的属性 (如果第一次看到的属性是过去一小时，则最后一次看到的设备必须位于) 。</span><span class="sxs-lookup"><span data-stu-id="b8786-170">Take all devices last seen in the past hour and check first seen property for them (if the first seen property is on the past hour, the last seen must be there too).</span></span> 

