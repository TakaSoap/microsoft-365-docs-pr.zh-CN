---
title: 将 Microsoft Defender for Endpoint 事件流式存储帐户
description: 了解如何配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输存储帐户。
keywords: 原始数据导出， 流式 API， API， 事件中心， Azure 存储， 存储帐户， 高级搜寻， 原始数据共享
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
ms.openlocfilehash: a9db98456cc971b4ac4179cd4f3460dfe2137b91
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156235"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输存储帐户

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)。

## <a name="before-you-begin"></a>准备工作

1. 在[租户存储](/azure/storage/common/storage-account-overview)帐户。

2. 登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.insights。**

## <a name="enable-raw-data-streaming"></a>启用原始数据流

1. 以 * [Microsoft 365 Defender](https://security.microsoft.com) **_** 或 _*_安全管理员_**登录。

2. 转到"[数据导出设置"页Microsoft 365 Defender。](https://security.microsoft.com/interoperability/dataexport)

3. 单击"**添加数据导出设置"。**

4. 选择新设置的名称。

5. Choose **Forward events to Azure 存储**.

6. 键入你的 **存储帐户资源 ID。** 若要获取你的帐户 **存储 ID，** 请转到 [Azure](https://ms.portal.azure.com/)门户属性选项卡上的你的 存储 帐户页面复制帐户存储 \> ID \> **下的文本**：

   :::image type="content" alt-text="事件中心资源 ID1 的图像。" source="images/storage-account-resource-id.png" lightbox="images/storage-account-resource-id.png":::

7. 选择要流式传输的事件，然后单击"保存 **"。**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>帐户内事件存储架构

- 将针对每种事件类型创建 blob 容器：

  :::image type="content" alt-text="事件中心资源 ID2 的图像。" source="images/storage-account-event-schema.png" lightbox="images/storage-account-event-schema.png":::

- blob 中每行的架构为以下 JSON：

  ```json
  {
      "time": "<The time WDATP received the event>"
      "tenantId": "<Your tenant ID>"
      "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
      "properties": { <WDATP Advanced Hunting event as Json> }
  }
  ```

- 每个 blob 包含多行。

- 每行都包含事件名称、Defender for Endpoint 接收事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为"properties"的属性。

- 有关适用于终结点事件的 Microsoft Defender 架构详细信息，请参阅 [高级搜寻概述](advanced-hunting-overview.md)。

- 在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。 此处还将用此列修饰每个事件。 有关详细信息 [，请参阅](machine-groups.md) 设备组。

## <a name="data-types-mapping"></a>数据类型映射

为了获取事件属性的数据类型，请执行下列操作：

1. 登录[以Microsoft 365 Defender](https://security.microsoft.com)转到高级[搜寻页面](https://security.microsoft.com/hunting-package)。

2. 运行以下查询，获取每个事件的数据类型映射：

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- 下面是设备信息事件的示例：

  ![事件中心资源 ID3 的图像。](images/data-types-mapping-query.png)

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [适用于终结点流 API 的 Microsoft Defender](raw-data-export.md)
- [将 Microsoft Defender for Endpoint 事件流式处理到 Azure 存储帐户](raw-data-export-storage.md)
- [Azure 存储帐户文档](/azure/storage/common/storage-account-overview)
