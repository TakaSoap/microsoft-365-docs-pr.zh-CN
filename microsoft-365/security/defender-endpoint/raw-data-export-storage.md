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
ms.openlocfilehash: 9ec8c286828fd6b551bf76c8340b58c9a1407bba
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778205"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>配置 Microsoft 365 Defender 以将高级搜寻事件流式传输存储帐户

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="before-you-begin"></a>开始之前：

1. 在[租户存储](/azure/storage/common/storage-account-overview)帐户。

2. 登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.Insights。**

## <a name="enable-raw-data-streaming"></a>启用原始数据流：

1. 以 * [Microsoft 365](https://security.microsoft.com) **_** 或 _* 安全管理员 ** 登录 Defender _安全中心_。

2. 转到"[数据导出设置"页Microsoft Defender 安全中心。](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. 单击"**添加数据导出设置"。**

4. 选择新设置的名称。

5. Choose **Forward events to Azure 存储**.

6. 键入你的 **存储帐户资源 ID。** 若要获取你的 存储 帐户资源 **ID，** 请转到 [Azure](https://ms.portal.azure.com/)门户 > 属性选项卡上的 存储 帐户页面>复制 存储 帐户资源 ID 下 **的文本**：

   ![事件中心资源 ID1 的图像](images/storage-account-resource-id.png)

7. 选择要流式传输的事件，然后单击"保存 **"。**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>帐户内事件存储架构：

- 将针对每种事件类型创建 blob 容器： 

  ![事件中心资源 ID2 的图像](images/storage-account-event-schema.png)

- blob 中每行的架构为以下 JSON： 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- 每个 blob 包含多行。

- 每行都包含事件名称、Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为"properties"的属性。

- 有关 Defender 事件的架构Microsoft 365，请参阅[高级搜寻概述](../defender/advanced-hunting-overview.md)。


## <a name="data-types-mapping"></a>数据类型映射：

为了获取事件属性的数据类型，请执行下列操作：

1. 登录到安全[Microsoft 365，](https://security.microsoft.com)然后转到高级[搜寻页面](https://security.microsoft.com/hunting-package)。

2. 运行以下查询，获取每个事件的数据类型映射： 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 下面是设备信息事件的示例： 

  ![事件中心资源 ID3 的图像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](../defender/advanced-hunting-overview.md)
- [Microsoft 365Defender 流式处理 API](raw-data-export.md)
- [将Microsoft 365 Defender 事件流式传输至 Azure 存储帐户](raw-data-export-storage.md)
- [Azure 存储帐户文档](/azure/storage/common/storage-account-overview)
