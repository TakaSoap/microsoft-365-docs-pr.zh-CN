---
title: 将Microsoft 365 Defender 事件流式传输存储帐户
description: 了解如何配置 Microsoft 365 Defender 以将高级搜寻事件流式传输存储帐户。
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
ms.openlocfilehash: 1a1d6b63bcdf21535f36b23d4a30e5ea01833c36
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729988"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="6c07c-104">配置 Microsoft 365 Defender 以将高级搜寻事件流式传输存储帐户</span><span class="sxs-lookup"><span data-stu-id="6c07c-104">Configure  Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c07c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c07c-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c07c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c07c-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="6c07c-107">开始之前：</span><span class="sxs-lookup"><span data-stu-id="6c07c-107">Before you begin:</span></span>

1. <span data-ttu-id="6c07c-108">在[租户存储](/azure/storage/common/storage-account-overview)帐户。</span><span class="sxs-lookup"><span data-stu-id="6c07c-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="6c07c-109">登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.Insights。**</span><span class="sxs-lookup"><span data-stu-id="6c07c-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="6c07c-110">启用原始数据流：</span><span class="sxs-lookup"><span data-stu-id="6c07c-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="6c07c-111">以 \* [Microsoft 365](https://security.microsoft.com) **_** 或 _\* 安全管理员 \*\* 登录 Defender _安全中心_。</span><span class="sxs-lookup"><span data-stu-id="6c07c-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="6c07c-112">转到"[数据导出设置"页Microsoft Defender 安全中心。](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="6c07c-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="6c07c-113">单击"**添加数据导出设置"。**</span><span class="sxs-lookup"><span data-stu-id="6c07c-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="6c07c-114">选择新设置的名称。</span><span class="sxs-lookup"><span data-stu-id="6c07c-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="6c07c-115">Choose **Forward events to Azure 存储**.</span><span class="sxs-lookup"><span data-stu-id="6c07c-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="6c07c-116">键入你的 **存储帐户资源 ID。**</span><span class="sxs-lookup"><span data-stu-id="6c07c-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="6c07c-117">若要获取你的 存储 帐户资源 **ID，** 请转到 [Azure](https://ms.portal.azure.com/)门户 > 属性选项卡上的 存储 帐户页面>复制 存储 帐户资源 ID 下 **的文本**：</span><span class="sxs-lookup"><span data-stu-id="6c07c-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![事件中心资源 ID1 的图像](images/storage-account-resource-id.png)

7. <span data-ttu-id="6c07c-119">选择要流式传输的事件，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="6c07c-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="6c07c-120">帐户内事件存储架构：</span><span class="sxs-lookup"><span data-stu-id="6c07c-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="6c07c-121">将针对每种事件类型创建 blob 容器：</span><span class="sxs-lookup"><span data-stu-id="6c07c-121">A blob container will be created for each event type:</span></span> 

  ![事件中心资源 ID2 的图像](images/storage-account-event-schema.png)

- <span data-ttu-id="6c07c-123">blob 中每行的架构为以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="6c07c-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="6c07c-124">每个 blob 包含多行。</span><span class="sxs-lookup"><span data-stu-id="6c07c-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="6c07c-125">每行都包含事件名称、Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为"properties"的属性。</span><span class="sxs-lookup"><span data-stu-id="6c07c-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="6c07c-126">有关 Defender 事件的架构Microsoft 365，请参阅[高级搜寻概述](../defender/advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6c07c-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="6c07c-127">数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="6c07c-127">Data types mapping:</span></span>

<span data-ttu-id="6c07c-128">为了获取事件属性的数据类型，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6c07c-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="6c07c-129">登录到安全[Microsoft 365，](https://security.microsoft.com)然后转到高级[搜寻页面](https://security.microsoft.com/hunting-package)。</span><span class="sxs-lookup"><span data-stu-id="6c07c-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="6c07c-130">运行以下查询，获取每个事件的数据类型映射：</span><span class="sxs-lookup"><span data-stu-id="6c07c-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="6c07c-131">下面是设备信息事件的示例：</span><span class="sxs-lookup"><span data-stu-id="6c07c-131">Here is an example for Device Info event:</span></span> 

  ![事件中心资源 ID3 的图像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="6c07c-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="6c07c-133">Related topics</span></span>
- [<span data-ttu-id="6c07c-134">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="6c07c-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="6c07c-135">Microsoft 365Defender 流式处理 API</span><span class="sxs-lookup"><span data-stu-id="6c07c-135">Microsoft 365 Defender Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="6c07c-136">将Microsoft 365 Defender 事件流式传输至 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="6c07c-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="6c07c-137">Azure 存储帐户文档</span><span class="sxs-lookup"><span data-stu-id="6c07c-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
