---
title: 将Microsoft Defender for Endpoint事件流式传输到存储帐户
description: 了解如何配置Microsoft Defender for Endpoint以将高级搜寻事件流式传输到存储帐户。
keywords: 原始数据导出、流式处理 API、API、事件中心、Azure 存储、存储帐户、高级搜寻、原始数据共享
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: d5d4917e2464964da819af0a06f0b8e4883dfea9
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783878"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>配置Microsoft Defender for Endpoint以将高级搜寻事件流式传输到存储帐户

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)。

## <a name="before-you-begin"></a>准备工作

1. 在租户中创建[存储帐户](/azure/storage/common/storage-account-overview)。

2. 登录到 [Azure 租户](https://ms.portal.azure.com/)，转到 **订阅>订阅>资源提供程序>注册到 Microsoft.insights**。

## <a name="enable-raw-data-streaming"></a>启用原始数据流式处理

1. 以 ***Global Administrator** _ 或 _*_Security Administrator_ 身份登录到 [Microsoft 365 Defender](https://security.microsoft.com)。

2. 转到Microsoft 365 Defender中[的数据导出设置页](https://security.microsoft.com/interoperability/dataexport)。

3. 单击 **“添加数据导出设置**”。

4. 为新设置选择名称。

5. 选择 **要Azure 存储的转发事件**。

6. 键 **入存储帐户资源 ID**。 若要获取 **存储帐户资源 ID**，请转到“Azure 门户属性”选项卡\>上的 [“存储](https://ms.portal.azure.com/)\>帐户”页，复制 **存储帐户资源 ID 下的** 文本：

   :::image type="content" source="images/storage-account-resource-id.png" alt-text="具有资源 ID1 的事件中心" lightbox="images/storage-account-resource-id.png":::

7. 选择要流式传输的事件，然后单击 **“保存**”。

## <a name="the-schema-of-the-events-in-the-storage-account"></a>存储帐户中事件的架构

- 将为每个事件类型创建一个 Blob 容器：

  :::image type="content" source="images/storage-account-event-schema.png" alt-text="具有资源 ID2 的事件中心" lightbox="images/storage-account-event-schema.png":::

- Blob 中每行的架构为以下 JSON：

  ```json
  {
    "time": "<The time WDATP received the event>"
    "tenantId": "<Your tenant ID>"
    "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
    "properties": { <WDATP Advanced Hunting event as Json> }
  }
  ```

- 每个 Blob 包含多行。

- 每行都包含事件名称、Defender for Endpoint 接收事件的时间、它所属的租户 (你将仅从租户) 获取事件，以及以 JSON 格式的名为“properties”的属性的事件。

- 有关Microsoft Defender for Endpoint事件架构的详细信息，请参阅[高级搜寻概述](advanced-hunting-overview.md)。

- 在“高级搜寻”中， **DeviceInfo** 表包含一个名为 **MachineGroup** 的列，其中包含设备组。 此处，每个事件也将使用此列进行修饰。 有关详细信息，请参阅 [设备组](machine-groups.md) 。

## <a name="data-types-mapping"></a>数据类型映射

为了获取事件属性的数据类型，请执行以下操作：

1. 登录到[Microsoft 365 Defender](https://security.microsoft.com)并转到[“高级搜寻”页面](https://security.microsoft.com/hunting-package)。

2. 运行以下查询以获取每个事件的数据类型映射：

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- 下面是设备信息事件的示例：

  :::image type="content" source="images/data-types-mapping-query.png" alt-text="具有资源 ID3 的事件中心" lightbox="images/data-types-mapping-query.png":::

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint流式处理 API](raw-data-export.md)
- [将Microsoft Defender for Endpoint事件流式传输到 Azure 存储帐户](raw-data-export-storage.md)
- [Azure 存储帐户文档](/azure/storage/common/storage-account-overview)
