---
title: 将Microsoft 365 Defender流式处理到 Azure 事件中心
description: 了解如何配置Microsoft 365 Defender高级搜寻事件流式传输至事件中心。
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 064ce5f796d59994b9d7ec4c3403711b1d683e56
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500466"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>配置Microsoft 365 Defender将高级搜寻事件流式传输至 Azure 事件中心

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>开始之前

1. 在 [租户中创建](/azure/event-hubs/) 事件中心。

2. 登录到 [你的 Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.Insights**。

3. 创建事件中心命名空间，转到"事件 **中心** ">添加"，然后选择适合预期负载的定价层、吞吐量单位和自动提高。 有关详细信息，请参阅 [事件中心定价](https://azure.microsoft.com/pricing/details/event-hubs/)。

### <a name="add-contributor-permissions"></a>添加参与者权限

创建事件中心命名空间后，你将需要：

1. 将要登录的用户定义为参与者Microsoft 365 Defender用户。

2. 如果要连接到应用程序，将应用注册服务主体添加为读者，Azure 事件中心数据接收器 (此操作也可在资源组或订阅级别) 。

    转到事件 **中心命名空间>访问控制 (IAM) >添加** 并验证角色 **分配下**。

## <a name="enable-raw-data-streaming"></a>启用原始数据流

1. 以 *<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> 或 _*_Security Administrator_** 登录登录门户。

2. 转到" [流式处理 API 设置"页](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。

3. 单击" **添加"**。

4. 选择新设置的名称。

5. 选择 **"将事件转发到 Azure 事件中心"**。

6. 可以选择是希望将事件数据导出到单个事件中心，还是将每个事件表导出到事件中心命名空间中的不同事件中心。

7. 若要将事件数据导出到单个事件中心，请输入事件中心 **名称和****事件中心资源 ID**。

   若要获取事件 **中心资源 ID**，请转到 **AzureProperties** 选项卡上的 [Azure](https://ms.portal.azure.com/) >  事件中心命名空间页面>复制资源 **ID 下的文本**：

   :::image type="content" source="../defender-endpoint/images/event-hub-resource-id.png" alt-text="事件中心资源 ID" lightbox="../defender-endpoint/images/event-hub-resource-id.png":::

8. 转到事件流 [API Microsoft 365 Defender](supported-event-types.md)支持的事件类型，查看事件流 API 中事件Microsoft 365状态。

9. 选择要流式传输的事件，然后单击"保存 **"**。

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>Azure 事件中心中的事件的架构

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

- Azure 事件中心中的每个事件中心消息都包含记录列表。

- 每条记录都包含事件名称、Microsoft 365 Defender接收事件的时间、它所属的租户 (仅从租户) 获取事件，事件以 JSON 格式包含在名为"**properties**"的属性中。

- 有关事件架构Microsoft 365 Defender，请参阅高级[搜寻概述](advanced-hunting-overview.md)。

- 在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。 此处还将用此列修饰每个事件。

## <a name="data-types-mapping"></a>数据类型映射

若要获取事件属性的数据类型，请执行下列操作：

1. 登录<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">以Microsoft 365 Defender</a>转到高级[搜寻页面](https://security.microsoft.com/hunting-package)。

2. 运行以下查询，获取每个事件的数据类型映射：

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- 下面是设备信息事件的示例：

  :::image type="content" source="../defender-endpoint/images/machine-info-datatype-example.png" alt-text="设备信息查询示例" lightbox="../defender-endpoint/images/machine-info-datatype-example.png":::

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [Microsoft 365 Defender流式处理 API](streaming-api.md)
- [事件Microsoft 365 Defender API 中支持的事件类型](supported-event-types.md)
- [将Microsoft 365 Defender流式处理到 Azure 存储帐户](streaming-api-storage.md)
- [Azure 事件中心文档](/azure/event-hubs/)
- [解决连接问题 - Azure 事件中心](/azure/event-hubs/troubleshooting-guide)
