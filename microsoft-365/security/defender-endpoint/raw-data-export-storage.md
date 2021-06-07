---
title: 将 Microsoft Defender for Endpoint 事件流式存储帐户
description: 了解如何配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输存储帐户。
keywords: 原始数据导出， 流式 API， API， 事件中心， Azure 存储， 存储帐户， 高级搜寻， 原始数据共享
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
ms.custom: api
ms.openlocfilehash: 6be79e4991c9e20c46458eacd97ac0b7b7466bc8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771648"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="4a323-104">配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输存储帐户</span><span class="sxs-lookup"><span data-stu-id="4a323-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4a323-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4a323-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a323-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4a323-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="4a323-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4a323-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4a323-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4a323-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="4a323-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="4a323-109">Before you begin</span></span>

1. <span data-ttu-id="4a323-110">在[租户存储](/azure/storage/common/storage-account-overview)帐户。</span><span class="sxs-lookup"><span data-stu-id="4a323-110">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="4a323-111">登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.insights。**</span><span class="sxs-lookup"><span data-stu-id="4a323-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="4a323-112">启用原始数据流</span><span class="sxs-lookup"><span data-stu-id="4a323-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="4a323-113">以 \* 全局管理员 **_** 或 _\* 安全管理员 \*\*登录 [Microsoft Defender 终结点](https://securitycenter.windows.com)_门户_。</span><span class="sxs-lookup"><span data-stu-id="4a323-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="4a323-114">转到"[数据导出设置"页上Microsoft Defender 安全中心。](https://securitycenter.windows.com/interoperability/dataexport)</span><span class="sxs-lookup"><span data-stu-id="4a323-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="4a323-115">单击"**添加数据导出设置"。**</span><span class="sxs-lookup"><span data-stu-id="4a323-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="4a323-116">选择新设置的名称。</span><span class="sxs-lookup"><span data-stu-id="4a323-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="4a323-117">Choose **Forward events to Azure 存储**.</span><span class="sxs-lookup"><span data-stu-id="4a323-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="4a323-118">键入你的 **存储帐户资源 ID。**</span><span class="sxs-lookup"><span data-stu-id="4a323-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="4a323-119">若要获取你的 存储 帐户资源 **ID，** 请转到 [Azure](https://ms.portal.azure.com/)门户 > 属性选项卡上的 存储 帐户页面>复制 存储 帐户资源 **ID 下的文本**：</span><span class="sxs-lookup"><span data-stu-id="4a323-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![事件中心资源 ID1 的图像](images/storage-account-resource-id.png)

7. <span data-ttu-id="4a323-121">选择要流式传输的事件，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="4a323-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="4a323-122">帐户内事件存储架构</span><span class="sxs-lookup"><span data-stu-id="4a323-122">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="4a323-123">将针对每种事件类型创建 blob 容器：</span><span class="sxs-lookup"><span data-stu-id="4a323-123">A blob container will be created for each event type:</span></span> 

  ![事件中心资源 ID2 的图像](images/storage-account-event-schema.png)

- <span data-ttu-id="4a323-125">blob 中每行的架构为以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="4a323-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="4a323-126">每个 blob 包含多行。</span><span class="sxs-lookup"><span data-stu-id="4a323-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="4a323-127">每行都包含事件名称、Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为"properties"的属性。</span><span class="sxs-lookup"><span data-stu-id="4a323-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="4a323-128">有关适用于终结点事件的 Microsoft Defender 架构详细信息，请参阅 [高级搜寻概述](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4a323-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="4a323-129">在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。</span><span class="sxs-lookup"><span data-stu-id="4a323-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="4a323-130">此处还将用此列修饰每个事件。</span><span class="sxs-lookup"><span data-stu-id="4a323-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="4a323-131">有关详细信息 [，请参阅](machine-groups.md) 设备组。</span><span class="sxs-lookup"><span data-stu-id="4a323-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="4a323-132">数据类型映射</span><span class="sxs-lookup"><span data-stu-id="4a323-132">Data types mapping</span></span>

<span data-ttu-id="4a323-133">为了获取事件属性的数据类型，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4a323-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="4a323-134">登录[以Microsoft Defender 安全中心](https://securitycenter.windows.com)转到高级[搜寻页面](https://securitycenter.windows.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="4a323-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="4a323-135">运行以下查询，获取每个事件的数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="4a323-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="4a323-136">下面是设备信息事件的示例：</span><span class="sxs-lookup"><span data-stu-id="4a323-136">Here is an example for Device Info event:</span></span> 

  ![事件中心资源 ID3 的图像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="4a323-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="4a323-138">Related topics</span></span>
- [<span data-ttu-id="4a323-139">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="4a323-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4a323-140">适用于终结点流 API 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4a323-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="4a323-141">将 Microsoft Defender for Endpoint 事件流式处理到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="4a323-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="4a323-142">Azure 存储帐户文档</span><span class="sxs-lookup"><span data-stu-id="4a323-142">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)