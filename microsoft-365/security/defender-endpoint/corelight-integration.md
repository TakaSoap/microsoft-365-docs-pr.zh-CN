---
title: 在 Microsoft Defender for Endpoint 中启用 Corelight 集成
description: 启用 Corelight 集成以在网络中未部署 MDE 的区域中获得 IoT/OT 设备的可见性
keywords: 启用 siem 连接器、siem、连接器、安全信息和事件
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bf3095b9178b4ff2e71d4ee5f652d9316f233746
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664581"
---
# <a name="enable-corelight-data-integration"></a>启用 Corelight 数据集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。

Microsoft 已与行业领先的开放网络检测和响应提供商 [Corelight](https://corelight.com/integrations/iot-security) 合作， (NDR) 平台，帮助你在整个组织中发现 IoT/OT 设备。 使用从 Corelight 网络设备发送的数据，Microsoft 365 Defender提高对非托管设备网络活动的可见性，包括与其他非托管设备或外部网络的通信。

启用此数据源后，Corelight 网络设备中的所有事件将发送到Microsoft 365 Defender。 可以在非托管设备时间线中查看这些活动，这些活动在Microsoft Defender for Endpoint设备清单中可用。 有关详细信息，请参阅 [设备发现](device-discovery.md)。

## <a name="enabling-the-corelight-integration"></a>启用 Corelight 集成

若要启用 Corelight 集成，需要执行以下步骤：

[步骤 1：将 Corelight 作为数据源启用](#step-1-turn-on-corelight-as-a-data-source)<br>
[步骤 2：为 Corelight 提供向Microsoft 365 Defender发送事件的权限](#step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender)<br>
[步骤 3：配置 Corelight 设备以将数据发送到Microsoft 365 Defender](#step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender)

### <a name="step-1-turn-on-corelight-as-a-data-source"></a>步骤 1：将 Corelight 作为数据源启用

1. 在门户的 [https://security.microsoft.com](https://security.microsoft.com/)导航窗格中，选择 **设置** \> **设备发现** \> **数据源**。

   :::image type="content" source="images/enable-corelight.png" alt-text="Microsoft 365 Defender门户中的数据源页" lightbox="images/enable-corelight.png":::

2. 选择 **"将 Corelight 数据发送到 M365D** "，然后选择 **"保存**"。

### <a name="step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender"></a>步骤 2：为 Corelight 提供向Microsoft 365 Defender发送事件的权限

> [!NOTE]
> 必须是全局管理员才能授予 Corelight 访问组织中资源的权限。

1. 作为租户全局管理员，请转到此 [链接](<https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=d8be544e-9d1a-4825-a5cb-fb447457f692&response_type=code&sso_reload=true>) 以授予权限。
2. 转到 [https://security.microsoft.com](https://security.microsoft.com/)门户，选择 **设置** \> **Microsoft 365 Defender**，并记下 **租户 ID**。 配置 Corelight 设备时需要此信息。

### <a name="step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender"></a>步骤 3：配置 Corelight 设备以将数据发送到Microsoft 365 Defender

> [!NOTE]
>  集成将在 Corelight Sensor 软件 v24 及更高版本中公开。 

若要在 v23 或 v22.1 中预览，必须执行此操作 `corelight-client configuration update --enable.adfiot 1` 才能在 GUI 中启用配置部分。

除此之外，GUI 验证要求在所有 v23 版本的配置部分中配置代理。  你提供的中转站是必需的，但实际上不会使用。 在 _kafka 中转站_ 字段中输入`127.0.0.1:1234`，以确保在执行以下步骤之前成功验证，以便将数据发送到Microsoft 365 Defender。

> [!NOTE]
> 你需要连接 Internet，传感器才能访问 Defender 和 Corelight 云服务，以便解决方案正常工作。

#### <a name="enabling-in-the-corelight-sensor-gui"></a>在 Corelight 传感器 GUI 中启用

1. 在"Corelight 传感器 GUI 配置"部分中，选择 **"传感器** \> **导出**"。
2. 在列表中，转 **到"导出到 KAFKA** "，然后选择开关将其打开。

   :::image type="content" source="images/exporttokafka.png" alt-text="kafka 导出" lightbox="images/exporttokafka.png":::

3. 接下来，打开 **"导出到 AZURE DEFENDER FOR IOT** "并在"租户 ID"字段中输入步骤 1 中所述的租户 ID。

   :::image type="content" source="images/exporttodiot.png" alt-text="iot 导出" lightbox="images/exporttodiot.png":::

4. 选择“**应用更改**”。

   :::image type="content" source="images/corelightapply.png" alt-text="&quot;应用更改&quot;图标" lightbox="images/corelightapply.png":::

> [!NOTE]
> Kafka (中不包括日志排除和筛选器) 的配置选项不应更改。 所做的任何更改都将被忽略。

#### <a name="enabling-in-the-corelight-client"></a>在 corelight-client 中启用

可以在 corelight-client 中使用以下命令启用 **EXPORT TO KAFKA** 和 **EXPORT TO AZURE DEFENDER FOR IOT** ：

`corelight-client configuration update --bro.export.kafka.defender.enable true --bro.export.kafka.defender.tenant\_id <your tenant>`.

> [!IMPORTANT]
> 如果已在使用 Kafka 导出，请联系 Corelight 支持部门进行备用配置。

配置仅发送最小日志集：

1. 在 Corelight 传感器 GUI 中，转到 Kafka 部分
2. 转到 **Zeek 日志以排除**
3. 选择 **"全部"**
4. 然后在以下日志旁边选择 **x** ，以确保它们继续流向 Microsoft：  
    `dns  conn  files  http  ssl  ssh  x509  snmp  smtp  ftp  sip  dhcp  notice`
5. 选择 **"应用更改**"

流向 Microsoft 的日志列表可能会随时间推移而扩展。

## <a name="see-also"></a>另请参阅

- [设备发现常见问题](device-discovery-faq.md)
