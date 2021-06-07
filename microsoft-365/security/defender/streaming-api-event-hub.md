---
title: 将Microsoft 365 Defender 事件流式处理到 Azure 事件中心
description: 了解如何配置 Microsoft 365 Defender 以将高级搜寻事件流式传输至事件中心。
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
ms.openlocfilehash: b96ae78b0f2decfe7b2c6f695a4456ac93919c35
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772430"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>配置 Microsoft 365 Defender 以将高级搜寻事件流式传输至 Azure 事件中心

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>开始之前：

1. 在 [租户中创建](/azure/event-hubs/) 事件中心。

2. 登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.Insights。**

3. 创建事件中心命名空间，转到"事件 **中心** ">添加"并选择适合预期负载的定价层、吞吐量单位和自动提高。 有关详细信息，请参阅定价[- 事件中心|Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)。  

4. 创建事件中心命名空间后，你需要将应用注册服务主体添加为读者、Azure 事件中心数据接收器以及将登录到 Microsoft 365 Defender 的用户作为参与者 (这也可在资源组或订阅级别) 完成。 转到事件 **中心命名空间>访问控制 (IAM**) >添加并验证角色 **分配下**。

## <a name="enable-raw-data-streaming"></a>启用原始数据流：

1. 以 *[全局Microsoft 365](https://security.microsoft.com) **_** 或 _* 安全管理员 **登录到安全 _中心_。

2. 转到"数据 [导出设置"页](https://security.microsoft.com/settings/mtp_settings/raw_data_export)。

3. 单击"添加 **"。**

4. 选择新设置的名称。

5. 选择 **"将事件转发到 Azure 事件中心"。**

6. 可以选择是希望将事件数据导出到单个事件中心，还是将每个事件表导出到事件中心命名空间中的不同甚至中心。 

7. 若要将事件数据导出到单个事件中心，**请输入事件中心** 名称和 **事件中心资源 ID。**

   若要获取 **事件中心资源 ID，** 请转到 Azure 属性选项卡上的 [Azure](https://ms.portal.azure.com/)事件中心命名空间页面>复制资源  >  ID **下的文本**：

   ![事件中心资源 Id1 的图像](../defender-endpoint/images/event-hub-resource-id.png)

8. 选择要流式传输的事件，然后单击"保存 **"。**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure 事件中心中的事件的架构：

```
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

- 每条记录都包含事件名称、Microsoft 365 Defender 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为 **"properties"** 的属性。

- 有关 Defender 事件的架构Microsoft 365，请参阅[高级搜寻概述](advanced-hunting-overview.md)。

- 在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。 此处还将用此列修饰每个事件。 

9. 若要将每个事件表导出到不同的事件中心，只需将事件中心名称 **留空Microsoft 365** Defender 将执行其余工作。


## <a name="data-types-mapping"></a>数据类型映射：

若要获取事件属性的数据类型，请执行下列操作：

1. 登录到安全[Microsoft 365，](https://security.microsoft.com)然后转到高级[搜寻页面](https://security.microsoft.com/hunting-package)。

2. 运行以下查询，获取每个事件的数据类型映射：
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 下面是设备信息事件的示例： 

  ![事件中心资源 Id2 的图像](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [Microsoft 365Defender 流式处理 API](streaming-api.md)
- [将Microsoft 365 Defender 事件流式传输至 Azure 存储帐户](streaming-api-storage.md)
- [Azure 事件中心文档](/azure/event-hubs/)
- [解决连接问题 - Azure 事件中心](/azure/event-hubs/troubleshooting-guide)
