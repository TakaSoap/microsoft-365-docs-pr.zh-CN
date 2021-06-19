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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028871"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="26ccd-104">配置Microsoft 365 Defender将高级搜寻事件流式传输存储空间帐户</span><span class="sxs-lookup"><span data-stu-id="26ccd-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="26ccd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="26ccd-105">**Applies to:**</span></span>
- [<span data-ttu-id="26ccd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26ccd-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="26ccd-107">开始之前：</span><span class="sxs-lookup"><span data-stu-id="26ccd-107">Before you begin:</span></span>

1. <span data-ttu-id="26ccd-108">在[租户存储空间](/azure/storage/common/storage-account-overview)帐户。</span><span class="sxs-lookup"><span data-stu-id="26ccd-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="26ccd-109">登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.Insights。**</span><span class="sxs-lookup"><span data-stu-id="26ccd-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="26ccd-110">启用原始数据流：</span><span class="sxs-lookup"><span data-stu-id="26ccd-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="26ccd-111">以 \* [Microsoft 365 Defender](https://security.microsoft.com) **_** 或 _\* 安全管理员 \*\*登录 _安全_ 中心。</span><span class="sxs-lookup"><span data-stu-id="26ccd-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="26ccd-112">转到"[数据导出设置"页Microsoft Defender 安全中心。](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="26ccd-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="26ccd-113">单击"**添加数据导出设置"。**</span><span class="sxs-lookup"><span data-stu-id="26ccd-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="26ccd-114">选择新设置的名称。</span><span class="sxs-lookup"><span data-stu-id="26ccd-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="26ccd-115">Choose **Forward events to Azure 存储空间**.</span><span class="sxs-lookup"><span data-stu-id="26ccd-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="26ccd-116">键入你的 **存储空间帐户资源 ID。**</span><span class="sxs-lookup"><span data-stu-id="26ccd-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="26ccd-117">若要获取你的 存储空间 帐户资源 **ID，** 请转到 [Azure](https://ms.portal.azure.com/)门户 > 属性选项卡上的 存储空间 帐户页面>复制 存储空间 帐户资源 **ID 下的文本**：</span><span class="sxs-lookup"><span data-stu-id="26ccd-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![事件中心资源 ID1 的图像](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="26ccd-119">选择要流式传输的事件，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="26ccd-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="26ccd-120">帐户内事件存储空间架构：</span><span class="sxs-lookup"><span data-stu-id="26ccd-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="26ccd-121">将针对每种事件类型创建 blob 容器：</span><span class="sxs-lookup"><span data-stu-id="26ccd-121">A blob container will be created for each event type:</span></span> 

  ![事件中心资源 ID2 的图像](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="26ccd-123">blob 中每行的架构为以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="26ccd-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="26ccd-124">每个 blob 包含多行。</span><span class="sxs-lookup"><span data-stu-id="26ccd-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="26ccd-125">每行都包含事件名称、Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为"properties"的属性。</span><span class="sxs-lookup"><span data-stu-id="26ccd-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="26ccd-126">有关事件架构Microsoft 365 Defender，请参阅高级[搜寻概述](../defender/advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="26ccd-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="26ccd-127">数据类型映射</span><span class="sxs-lookup"><span data-stu-id="26ccd-127">Data types mapping</span></span>

<span data-ttu-id="26ccd-128">为了获取事件属性的数据类型，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="26ccd-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="26ccd-129">登录到安全[Microsoft 365，](https://security.microsoft.com)然后转到高级[搜寻页面](https://security.microsoft.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="26ccd-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="26ccd-130">运行以下查询，获取每个事件的数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="26ccd-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="26ccd-131">下面是设备信息事件的示例：</span><span class="sxs-lookup"><span data-stu-id="26ccd-131">Here is an example for Device Info event:</span></span> 

  ![事件中心资源 ID3 的图像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="26ccd-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="26ccd-133">Related topics</span></span>
- [<span data-ttu-id="26ccd-134">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="26ccd-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="26ccd-135">Microsoft 365 Defender流式处理 API</span><span class="sxs-lookup"><span data-stu-id="26ccd-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="26ccd-136">将Microsoft 365 Defender流式处理到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="26ccd-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="26ccd-137">Azure 存储空间帐户文档</span><span class="sxs-lookup"><span data-stu-id="26ccd-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
