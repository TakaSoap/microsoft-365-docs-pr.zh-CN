---
title: 将Microsoft 365 Defender事件流式传输存储空间帐户
description: 了解如何配置 Microsoft 365 Defender以将高级搜寻事件流式传输存储空间帐户。
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029653"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="e5c8b-104">配置Microsoft 365 Defender将高级搜寻事件流式传输存储空间帐户</span><span class="sxs-lookup"><span data-stu-id="e5c8b-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e5c8b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5c8b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5c8b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="e5c8b-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="e5c8b-107">Before you begin</span></span>

1. <span data-ttu-id="e5c8b-108">在[租户存储空间](/azure/storage/common/storage-account-overview)帐户。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="e5c8b-109">登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.Insights。**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="e5c8b-110">启用原始数据流</span><span class="sxs-lookup"><span data-stu-id="e5c8b-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="e5c8b-111">以 \* 全局管理员 _ Microsoft 365 Defender _\* () _\* 安全管理员 \*\*登录安全 <https://security.microsoft.com> 门户。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="e5c8b-112">转到 \> **设置Microsoft 365 Defender** \> **流式处理 API。**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="e5c8b-113">若要直接转到流 **式处理 API** 页面，请使用 <https://security.microsoft.com/settings/mtp_settings/raw_data_export> 。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="e5c8b-114">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-114">Click **Add**.</span></span>

4. <span data-ttu-id="e5c8b-115">在出现的 **"添加新的流式 API** 设置"飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="e5c8b-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="e5c8b-116">**名称**：选择新设置的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="e5c8b-117">选择 **转发事件以Azure 存储空间。**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="e5c8b-118">在出现的 **存储空间帐户资源 ID"** 框中，存储空间 **帐户资源 ID"。**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="e5c8b-119">To get your **存储空间 Account Resource ID，** open the Azure portal at <https://portal.azure.com> ， click 存储空间 **accounts** go to the properties tab copy the text under \> 存储空间 Account Resource \> **ID**.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![事件中心资源 ID1 的图像](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="e5c8b-121">返回到" **添加新的流式 API** 设置"飞出菜单 **，选择要流** 式传输的事件类型。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="e5c8b-122">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="e5c8b-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="e5c8b-123">帐户内事件存储空间架构</span><span class="sxs-lookup"><span data-stu-id="e5c8b-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="e5c8b-124">将针对每种事件类型创建 blob 容器：</span><span class="sxs-lookup"><span data-stu-id="e5c8b-124">A blob container will be created for each event type:</span></span>

  ![事件中心资源 ID2 的图像](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="e5c8b-126">blob 中每行的架构为以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="e5c8b-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="e5c8b-127">每个 blob 包含多行。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="e5c8b-128">每行都包含事件名称、Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为"properties"的属性。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="e5c8b-129">有关事件架构Microsoft 365 Defender，请参阅高级[搜寻概述](../defender/advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="e5c8b-130">数据类型映射</span><span class="sxs-lookup"><span data-stu-id="e5c8b-130">Data types mapping</span></span>

<span data-ttu-id="e5c8b-131">为了获取事件属性的数据类型，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e5c8b-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="e5c8b-132">登录到搜索Microsoft 365 Defender门户 <https://security.microsoft.com> () 并转到搜寻 \> **高级搜寻**。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="e5c8b-133">若要直接转到高级 **搜寻页面** ，请使用<security.microsoft.com/advanced-hunting>。</span><span class="sxs-lookup"><span data-stu-id="e5c8b-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="e5c8b-134">在" **查询** "选项卡上，运行以下查询，获取每个事件的数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="e5c8b-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="e5c8b-135">下面是设备信息事件的示例：</span><span class="sxs-lookup"><span data-stu-id="e5c8b-135">Here is an example for Device Info event:</span></span>

  ![事件中心资源 ID3 的图像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="e5c8b-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5c8b-137">Related topics</span></span>

- [<span data-ttu-id="e5c8b-138">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="e5c8b-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="e5c8b-139">Microsoft 365 Defender流式处理 API</span><span class="sxs-lookup"><span data-stu-id="e5c8b-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="e5c8b-140">将Microsoft 365 Defender流式处理到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="e5c8b-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="e5c8b-141">Azure 存储空间帐户文档</span><span class="sxs-lookup"><span data-stu-id="e5c8b-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
