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
ms.openlocfilehash: b914f0db277f92d56b651aa23f840865f029fd7e
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623092"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输存储帐户

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink)。

## <a name="before-you-begin"></a>准备工作

1. 在[租户存储](/azure/storage/common/storage-account-overview)帐户。

2. 登录到你的 [Azure 租户，](https://ms.portal.azure.com/)转到订阅>你的订阅>**资源>注册到 Microsoft.insights。**

## <a name="enable-raw-data-streaming"></a>启用原始数据流

1. 以 * 全局管理员 **_** 或 _* 安全管理员 **登录 [Microsoft Defender 终结点](https://securitycenter.windows.com)_门户_。

2. 转到"[数据导出设置"页上Microsoft Defender 安全中心。](https://securitycenter.windows.com/interoperability/dataexport)

3. 单击"**添加数据导出设置"。**

4. 选择新设置的名称。

5. Choose **Forward events to Azure 存储**.

6. 键入你的 **存储帐户资源 ID。** 若要获取你的 存储 帐户资源 **ID，** 请转到 [Azure](https://ms.portal.azure.com/)门户 > 属性选项卡上的 存储 帐户页面>复制 存储 帐户资源 **ID 下的文本**：

   ![事件中心资源 ID1 的图像](images/storage-account-resource-id.png)

7. 选择要流式传输的事件，然后单击"保存 **"。**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>帐户内事件存储架构

- 将针对每种事件类型创建 blob 容器： 

  ![事件中心资源 ID2 的图像](images/storage-account-event-schema.png)

- blob 中每行的架构为以下 JSON： 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- 每个 blob 包含多行。

- 每行都包含事件名称、Defender for Endpoint 收到事件的时间、它所属的租户 (你仅从租户) 获取事件，事件采用 JSON 格式，采用名为"properties"的属性。

- 有关适用于终结点事件的 Microsoft Defender 架构详细信息，请参阅 [高级搜寻概述](advanced-hunting-overview.md)。

- 在高级搜寻中 **，DeviceInfo** 表有一个名为 **MachineGroup** 的列，其中包含设备组。 此处还将用此列修饰每个事件。 有关详细信息 [，请参阅](machine-groups.md) 设备组。

## <a name="data-types-mapping"></a>数据类型映射

为了获取事件属性的数据类型，请执行下列操作：

1. 登录[以Microsoft Defender 安全中心](https://securitycenter.windows.com)转到高级[搜寻页面](https://securitycenter.windows.com/hunting-package)。

2. 运行以下查询，获取每个事件的数据类型映射： 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- 下面是设备信息事件的示例： 

  ![事件中心资源 ID3 的图像](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [适用于终结点流 API 的 Microsoft Defender](raw-data-export.md)
- [将 Microsoft Defender for Endpoint 事件流式处理到 Azure 存储帐户](raw-data-export-storage.md)
- [Azure 存储帐户文档](/azure/storage/common/storage-account-overview)