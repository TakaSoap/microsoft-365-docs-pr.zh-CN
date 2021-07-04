---
title: 将Microsoft 365 Defender流式处理到 Azure 事件中心
description: 了解如何配置Microsoft 365 Defender以将高级搜寻事件流式传输至事件中心。
keywords: 原始数据导出， 流式 API， API， Azure 事件中心， Azure 存储， 存储帐户， 高级搜寻， 原始数据共享
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
ms.openlocfilehash: 2e43b75e49d01a05fdacae0adf63ea3337631dfd
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289231"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a><span data-ttu-id="74a4a-104">配置Microsoft 365 Defender将高级搜寻事件流式传输至 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="74a4a-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74a4a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74a4a-105">**Applies to:**</span></span>
- [<span data-ttu-id="74a4a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74a4a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="74a4a-107">开始之前</span><span class="sxs-lookup"><span data-stu-id="74a4a-107">Before you begin</span></span>

1. <span data-ttu-id="74a4a-108">在 [租户中创建](/azure/event-hubs/) 事件中心。</span><span class="sxs-lookup"><span data-stu-id="74a4a-108">Create an [Event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="74a4a-109">登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.Insights。**</span><span class="sxs-lookup"><span data-stu-id="74a4a-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="74a4a-110">创建事件中心命名空间，转到"事件中心"> **添加** "，然后选择适合预期负载的定价层、吞吐量单位和自动提高。</span><span class="sxs-lookup"><span data-stu-id="74a4a-110">Create an Event Hub Namespace, go to **Event Hub > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="74a4a-111">有关详细信息，请参阅定价[- 事件中心|Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)。</span><span class="sxs-lookup"><span data-stu-id="74a4a-111">For more information, see [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

### <a name="add-contributor-permissions"></a><span data-ttu-id="74a4a-112">添加参与者权限</span><span class="sxs-lookup"><span data-stu-id="74a4a-112">Add contributor permissions</span></span>

<span data-ttu-id="74a4a-113">创建事件中心命名空间后，你将需要：</span><span class="sxs-lookup"><span data-stu-id="74a4a-113">Once the Event Hub namespace is created you will need to:</span></span>

1. <span data-ttu-id="74a4a-114">将要登录的用户定义为Microsoft 365 Defender用户。</span><span class="sxs-lookup"><span data-stu-id="74a4a-114">Define the user who will be logging into Microsoft 365 Defender as Contributor.</span></span>

2. <span data-ttu-id="74a4a-115">如果要连接到应用程序，请添加应用注册服务主体作为读者，Azure 事件中心数据接收器 (此操作也可在资源组或订阅级别) 。</span><span class="sxs-lookup"><span data-stu-id="74a4a-115">If you are connecting to an application, add the App Registration Service Principal as Reader, Azure Event Hub Data Receiver (this can also be done at Resource Group or Subscription level).</span></span> 

    <span data-ttu-id="74a4a-116">转到事件 **中心命名空间>访问控制 (IAM**) >添加并验证角色 **分配** 下。</span><span class="sxs-lookup"><span data-stu-id="74a4a-116">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignments**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="74a4a-117">启用原始数据流</span><span class="sxs-lookup"><span data-stu-id="74a4a-117">Enable raw data streaming</span></span>

1. <span data-ttu-id="74a4a-118">以 \* [Microsoft 365 Defender](https://security.microsoft.com) **_** 或 __\*_ 安全管理员 \*\*登录到安全中心。</span><span class="sxs-lookup"><span data-stu-id="74a4a-118">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="74a4a-119">转到流 [式处理 API 设置页面](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。</span><span class="sxs-lookup"><span data-stu-id="74a4a-119">Go to the [Streaming API settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="74a4a-120">单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="74a4a-120">Click on **Add**.</span></span>

4. <span data-ttu-id="74a4a-121">选择新设置的名称。</span><span class="sxs-lookup"><span data-stu-id="74a4a-121">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="74a4a-122">选择 **"将事件转发到 Azure 事件中心"。**</span><span class="sxs-lookup"><span data-stu-id="74a4a-122">Choose **Forward events to Azure Event Hub**.</span></span>

6. <span data-ttu-id="74a4a-123">可以选择是希望将事件数据导出到单个事件中心，还是将每个事件表导出到事件中心命名空间中的不同事件中心。</span><span class="sxs-lookup"><span data-stu-id="74a4a-123">You can select if you want to export the event data to a single Event Hub, or to export each event table to a different event hub in your Event Hub namespace.</span></span> 

7. <span data-ttu-id="74a4a-124">若要将事件数据导出到单个事件中心，请输入事件中心 **名称和\*\*\*\*事件中心资源 ID。**</span><span class="sxs-lookup"><span data-stu-id="74a4a-124">To export the event data to a single Event Hub, enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="74a4a-125">若要获取 **事件中心资源 ID，** 请转到 [Azure](https://ms.portal.azure.com/)属性选项卡上的 Azure 事件中心命名空间页面>复制资源  >  ID **下的文本**：</span><span class="sxs-lookup"><span data-stu-id="74a4a-125">To get your **Event Hub resource ID**, go to your Azure Event Hub namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![事件中心资源 Id1 的图像](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="74a4a-127">选择要流式传输的事件，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="74a4a-127">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hub"></a><span data-ttu-id="74a4a-128">Azure 事件中心中的事件的架构</span><span class="sxs-lookup"><span data-stu-id="74a4a-128">The schema of the events in Azure Event Hub</span></span>

```JSON
{
   "records": [
               {
                  "time": "<The time Microsoft 365 Defender received the event>"
                  "tenantId": "<The Id of the tenant that the event belongs to>"
                  "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                  "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
               }
               ...
            ]
}
```

- <span data-ttu-id="74a4a-129">Azure 事件中心中的每个事件中心消息都包含记录列表。</span><span class="sxs-lookup"><span data-stu-id="74a4a-129">Each Event Hub message in Azure Event Hub contains list of records.</span></span>

- <span data-ttu-id="74a4a-130">每条记录都包含事件名称、Microsoft 365 Defender接收事件的时间、它所属的租户 (你仅从租户) 获取事件，事件以 JSON 格式包含在名为 **"properties"** 的属性中。</span><span class="sxs-lookup"><span data-stu-id="74a4a-130">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="74a4a-131">有关事件架构Microsoft 365 Defender，请参阅高级[搜寻概述](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="74a4a-131">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="74a4a-132">在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。</span><span class="sxs-lookup"><span data-stu-id="74a4a-132">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="74a4a-133">此处还将用此列修饰每个事件。</span><span class="sxs-lookup"><span data-stu-id="74a4a-133">Here every event will be decorated with this column as well.</span></span> 

## <a name="data-types-mapping"></a><span data-ttu-id="74a4a-134">数据类型映射</span><span class="sxs-lookup"><span data-stu-id="74a4a-134">Data types mapping</span></span>

<span data-ttu-id="74a4a-135">若要获取事件属性的数据类型，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="74a4a-135">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="74a4a-136">登录到安全[Microsoft 365，](https://security.microsoft.com)然后转到高级[搜寻页面](https://security.microsoft.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="74a4a-136">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="74a4a-137">运行以下查询，获取每个事件的数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="74a4a-137">Run the following query to get the data types mapping for each event:</span></span>

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="74a4a-138">下面是设备信息事件的示例：</span><span class="sxs-lookup"><span data-stu-id="74a4a-138">Here is an example for Device Info event:</span></span> 

  ![事件中心资源 Id2 的图像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="74a4a-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="74a4a-140">Related topics</span></span>

- [<span data-ttu-id="74a4a-141">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="74a4a-141">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="74a4a-142">Microsoft 365 Defender流式处理 API</span><span class="sxs-lookup"><span data-stu-id="74a4a-142">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="74a4a-143">将Microsoft 365 Defender流式处理到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="74a4a-143">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="74a4a-144">Azure 事件中心文档</span><span class="sxs-lookup"><span data-stu-id="74a4a-144">Azure Event Hub documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="74a4a-145">解决连接问题 - Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="74a4a-145">Troubleshoot connectivity issues - Azure Event Hub</span></span>](/azure/event-hubs/troubleshooting-guide)
