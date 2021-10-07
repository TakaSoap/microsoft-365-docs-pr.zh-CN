---
title: 将 Microsoft Defender for Endpoint 事件流式处理到 Azure 事件中心
description: 了解如何配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式处理到事件中心。
keywords: 原始数据导出， 流式 API， API， Azure 事件中心， Azure 存储， 存储帐户， 高级搜寻， 原始数据共享
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: ac97d7a4210d1f498fa82453eb66e01398718c37
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209257"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输至 Azure 事件中心

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)。

## <a name="before-you-begin"></a>准备工作

1. 在 [租户中创建](/azure/event-hubs/) 事件中心。

2. 登录到 [你的 Azure 租户](https://ms.portal.azure.com/)，转到**订阅>你的订阅>资源>注册到 **Microsoft.insights****。

## <a name="enable-raw-data-streaming"></a>启用原始数据流

1. 以 * [Microsoft Defender 安全中心](https://securitycenter.windows.com)**_** 或 _*_安全_ 管理员 **登录安全帐户。

2. 转到"数据[导出设置"页上Microsoft Defender 安全中心。](https://securitycenter.windows.com/interoperability/dataexport)

3. 单击"**添加数据导出设置"。**

4. 选择新设置的名称。

5. 选择 **"将事件转发到 Azure 事件中心"。**

6. 键入 **事件中心名称和** 事件中心资源 **ID。**

   若要获取事件中心资源 **ID，** 请转到 [Azure](https://ms.portal.azure.com/) > 属性选项卡上的 Azure 事件中心命名空间页面，复制资源 \> ID **下的文本**：

   ![事件中心资源 Id1 的图像。](images/event-hub-resource-id.png)

7. 选择要流式传输的事件，然后单击"保存 **"。**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure 事件中心中的事件的架构

```text
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

- Azure 事件中心中的每个事件中心消息都包含记录列表。

- 每条记录都包含事件名称、Microsoft Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为 **"properties"** 的属性。

- 有关 Microsoft Defender for Endpoint 事件的架构详细信息，请参阅 [高级搜寻概述](advanced-hunting-overview.md)。

- 在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。 此处还将用此列修饰每个事件。 有关详细信息 [，请参阅](machine-groups.md) 设备组。

## <a name="data-types-mapping"></a>数据类型映射

若要获取事件属性的数据类型，请执行下列操作：

1. 登录[以Microsoft Defender 安全中心](https://securitycenter.windows.com)转到高级[搜寻页面](https://securitycenter.windows.com/hunting-package)。

2. 运行以下查询，获取每个事件的数据类型映射：

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 下面是设备信息事件的示例：

  ![事件中心资源 Id2 的图像。](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [适用于终结点流 API 的 Microsoft Defender](raw-data-export.md)
- [将 Microsoft Defender for Endpoint 事件流式处理到 Azure 存储帐户](raw-data-export-storage.md)
- [Azure 事件中心文档](/azure/event-hubs/)
- [解决连接问题 - Azure 事件中心](/azure/event-hubs/troubleshooting-guide)
