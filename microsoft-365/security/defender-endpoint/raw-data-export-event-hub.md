---
title: 将 Microsoft Defender for Endpoint 事件流式处理到 Azure 事件中心
description: 了解如何配置 Microsoft Defender ATP 以将高级搜寻事件流式传输至事件中心。
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
ms.openlocfilehash: 231ba79e1d66eee263b6c1a4335f0a7b54eeb75d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055360"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="7920e-104">配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输至 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="7920e-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7920e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7920e-105">**Applies to:**</span></span>

- [<span data-ttu-id="7920e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7920e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="7920e-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="7920e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7920e-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7920e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="7920e-109">开始之前：</span><span class="sxs-lookup"><span data-stu-id="7920e-109">Before you begin:</span></span>

1. <span data-ttu-id="7920e-110">在 [租户中创建](https://docs.microsoft.com/azure/event-hubs/) 事件中心。</span><span class="sxs-lookup"><span data-stu-id="7920e-110">Create an [event hub](https://docs.microsoft.com/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="7920e-111">登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到**订阅>你的订阅>资源>**注册到 Microsoft.insights。\*\*</span><span class="sxs-lookup"><span data-stu-id="7920e-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to **Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="7920e-112">启用原始数据流：</span><span class="sxs-lookup"><span data-stu-id="7920e-112">Enable raw data streaming:</span></span>

1. <span data-ttu-id="7920e-113">以 \* 全局管理员 **_** 或 _\* 安全管理员 \*\*登录 [Microsoft Defender](https://securitycenter.windows.com) _安全中心_。</span><span class="sxs-lookup"><span data-stu-id="7920e-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="7920e-114">转到 Microsoft Defender [安全中心上的](https://securitycenter.windows.com/interoperability/dataexport) "数据导出设置"页面。</span><span class="sxs-lookup"><span data-stu-id="7920e-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="7920e-115">单击"**添加数据导出设置"。**</span><span class="sxs-lookup"><span data-stu-id="7920e-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="7920e-116">选择新设置的名称。</span><span class="sxs-lookup"><span data-stu-id="7920e-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="7920e-117">选择 **"将事件转发到 Azure 事件中心"。**</span><span class="sxs-lookup"><span data-stu-id="7920e-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="7920e-118">键入 **事件中心名称和** 事件中心资源 **ID。**</span><span class="sxs-lookup"><span data-stu-id="7920e-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="7920e-119">若要获取事件中心资源 **ID，** 请转到 [Azure](https://ms.portal.azure.com/) > 属性选项卡上的 Azure 事件中心命名空间页面>复制资源 **ID 下的文本**：</span><span class="sxs-lookup"><span data-stu-id="7920e-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![事件中心资源 Id1 的图像](images/event-hub-resource-id.png)

7. <span data-ttu-id="7920e-121">选择要流式传输的事件，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="7920e-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="7920e-122">Azure 事件中心中的事件的架构：</span><span class="sxs-lookup"><span data-stu-id="7920e-122">The schema of the events in Azure Event Hubs:</span></span>

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="7920e-123">Azure 事件中心中的每个事件中心消息都包含记录列表。</span><span class="sxs-lookup"><span data-stu-id="7920e-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="7920e-124">每条记录都包含事件名称、Microsoft Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为 **"properties"** 的属性。</span><span class="sxs-lookup"><span data-stu-id="7920e-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="7920e-125">有关适用于终结点事件的 Microsoft Defender 架构详细信息，请参阅 [高级搜寻概述](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7920e-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="7920e-126">在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。</span><span class="sxs-lookup"><span data-stu-id="7920e-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="7920e-127">此处还将用此列修饰每个事件。</span><span class="sxs-lookup"><span data-stu-id="7920e-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="7920e-128">有关详细信息 [，请参阅](machine-groups.md) 设备组。</span><span class="sxs-lookup"><span data-stu-id="7920e-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="7920e-129">数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="7920e-129">Data types mapping:</span></span>

<span data-ttu-id="7920e-130">若要获取事件属性的数据类型，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7920e-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="7920e-131">登录到 [Microsoft Defender 安全中心，](https://securitycenter.windows.com) 然后转到高级 [搜寻页面](https://securitycenter.windows.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="7920e-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="7920e-132">运行以下查询，获取每个事件的数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="7920e-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="7920e-133">下面是设备信息事件的示例：</span><span class="sxs-lookup"><span data-stu-id="7920e-133">Here is an example for Device Info event:</span></span> 

  ![事件中心资源 Id2 的图像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="7920e-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="7920e-135">Related topics</span></span>
- [<span data-ttu-id="7920e-136">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="7920e-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7920e-137">适用于终结点流 API 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7920e-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="7920e-138">将 Microsoft Defender for Endpoint 事件流式处理到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="7920e-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="7920e-139">Azure 事件中心文档</span><span class="sxs-lookup"><span data-stu-id="7920e-139">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="7920e-140">解决连接问题 - Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="7920e-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
