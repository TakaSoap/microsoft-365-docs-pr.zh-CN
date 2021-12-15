---
title: 在 Microsoft Defender for Endpoint 中启用 Corelight 集成
description: 启用 Corelight 集成，以获得针对未部署 MDE 的网络区域 IoT/OT 设备的可见性
keywords: 启用 siem 连接器， siem， 连接器， 安全信息和事件
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
ms.openlocfilehash: 34e8b1f97319e4881175c7d79629dbed83730738
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531698"
---
# <a name="enable-corelight-data-integration"></a>启用 Corelight 数据集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。

Microsoft 与 [Corelight 合作，Corelight](https://corelight.com/integrations/iot-security)是业界领先的开放网络检测和响应 (NDR) 平台提供商，可帮助你发现整个组织的 IoT/OT 设备。 通过使用从 Corelight 网络设备发送的数据，Microsoft 365 Defender可增强非托管设备的网络活动的可见性，包括与其他非托管设备或外部网络的通信。

启用此数据源后，Corelight 网络设备的所有事件将发送到Microsoft 365 Defender。 可以在非托管设备时间线（Microsoft Defender for Endpoint 设备清单中提供）中查看这些活动。 有关详细信息，请参阅设备 [发现](device-discovery.md)。

## <a name="enabling-the-corelight-integration"></a>启用 Corelight 集成

若要启用 Corelight 集成，需要执行以下步骤：

[步骤 1：打开 Corelight 作为数据源](#step-1-turn-on-corelight-as-a-data-source)<br>
[步骤 2：为 Corelight 提供向用户发送事件Microsoft 365 Defender](#step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender)<br>
[步骤 3：配置 Corelight 设备以将数据发送到Microsoft 365 Defender](#step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender)

### <a name="step-1-turn-on-corelight-as-a-data-source"></a>步骤 1：打开 Corelight 作为数据源

1. 在门户的导航窗格中 [https://security.microsoft.com](https://security.microsoft.com/) ，选择"设置 \> **设备发现** \> **数据源"。**

    ![数据源的图像](images/enable-corelight.png)

2. 选择 **"将 Corelight 数据发送到 M365D"，** 然后选择"保存 **"。**

### <a name="step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender"></a>步骤 2：为 Corelight 提供向用户发送事件Microsoft 365 Defender

> [!NOTE]
> 你必须是全局管理员才能授予 Corelight 访问组织中资源的权限。

1. 作为租户全局管理员，转到此 [链接以](<https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=d8be544e-9d1a-4825-a5cb-fb447457f692&response_type=code&sso_reload=true>) 授予权限。
2. 转到 [https://security.microsoft.com](https://security.microsoft.com/) 门户，选择 **"设置Microsoft 365 Defender"，** \> 然后记下租户 **ID。** 配置 Corelight 设备时将需要此信息。

### <a name="step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender"></a>步骤 3：配置 Corelight 设备以将数据发送到Microsoft 365 Defender

> [!NOTE]
>  集成将在 Corelight 传感器软件 v24 及更高版本中公开。 

若要在 v23 或 v22.1 中预览，必须执行 才能在 GUI 中 `corelight-client configuration update --enable.adfiot 1` 启用配置部分。

除此之外，GUI 验证还要求在所有 v23 发行版的配置部分中配置代理。  你提供的代理是必需的，但实际上不会使用。 在 `127.0.0.1:1234` _kafka 代理_ 字段中输入以确保验证成功，然后再执行以下步骤以将数据发送到 Microsoft 365 Defender。

> [!NOTE]
> 你需要将你的传感器连接到 Internet，以同时访问 Defender 和 Corelight 云服务，解决方案可以正常工作。

#### <a name="enabling-in-the-corelight-sensor-gui"></a>在 Corelight 传感器 GUI 中启用

1. 在"Corelight 传感器 GUI 配置"部分，选择"**传感器导出** \> **"。**
2. 从列表中，转到 **"导出到 KAFKA"，** 然后选择开关将其打开。

   ![kafka 导出的图像](images/exporttokafka.png)

3. 接下来，打开 **"导出到 AZURE DEFENDER FOR IOT"，** 在"租户 ID"字段中输入步骤 1 中说明的租户 ID。

   ![iot 导出的图像](images/exporttodiot.png)

4. 选择“**应用更改**”。

   ![应用图像 ](images/corelightapply.png)

> [!NOTE]
> Kafka 中的 (排除日志排除和筛选器) 不应更改。 将忽略做出的任何更改。

#### <a name="enabling-in-the-corelight-client"></a>在 corelight-client 中启用

可以使用 corelight-client 中的以下命令打开 **"导出到 KAFKA"** 和 **"导出到 AZURE DEFENDER FOR IOT"：**

`corelight-client configuration update --bro.export.kafka.defender.enable true --bro.export.kafka.defender.tenant\_id <your tenant>`.

> [!IMPORTANT]
> 如果你已在使用 Kafka 导出，请联系 Corelight 支持人员以使用备用配置。

若要配置仅发送最少日志集，请运行以下操作：

1. 在 Corelight 传感器 GUI 中，转到 Kafka 部分
2. Go to **Zeek logs to exclude**
3. 全 **选**
4. 然后，选择以下日志旁边的 **x** 以确保它们继续流向 Microsoft：  
    `dns  conn  files  http  ssl  ssh  x509  snmp  smtp  ftp  sip  dhcp  notice`
5. 选择 **"应用更改"**

流向 Microsoft 的日志列表可能会随着时间的推移而扩展。

## <a name="see-also"></a>另请参阅

- [设备发现常见问题](device-discovery-faq.md)
