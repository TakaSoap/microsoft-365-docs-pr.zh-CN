---
title: 调查代理运行状况问题
description: 了解运行 mdatp 运行状况命令时返回的值
keywords: mdatp 运行状况， 命令， 运行状况， 状态， 命令， 载入状态
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
ms.openlocfilehash: f43905fe3487f44d3736e098c19964eaad3bf126
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206967"
---
# <a name="investigate-agent-health-issues"></a>调查代理运行状况问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

下表提供了有关运行命令时返回的值 `mdatp health` 及其相应说明的信息。

<br>

****

|值|说明|
|---|---|
|automatic_definition_update_enabled|如果启用了自动防病毒定义更新，则其参数为 True，否则为 false。|
|cloud_automatic_sample_submission_consent|当前示例提交级别。 可以是下列值之一： <ul><li>**无**：不会向 Microsoft 提交任何可疑示例。</li><li>**保险箱：** 只有不包含个人身份信息或个人身份信息的可疑 (将自动) 提交。 这是此设置的默认值。</li><li>**全部**：所有可疑示例都提交到 Microsoft。</li></ul>|
|cloud_diagnostic_enabled|如果启用可选诊断数据收集，则其参数为 True，否则为 false。 有关适用于终结点的 Defender 以及其他产品和服务（如 Microsoft Defender 防病毒 和 Windows）的信息，请参阅 Microsoft[隐私声明](https://go.microsoft.com/fwlink/?linkid=827576)。|
|cloud_enabled|如果启用云保护，则其参数为 True，否则为 false。|
|conflicting_applications|可能与 Microsoft Defender for Endpoint 冲突的应用程序列表。 此列表包括但不限于其他安全产品和其他已知导致兼容性问题的应用程序。|
|definitions_status|防病毒定义的状态。|
|definitions_updated|上次防病毒定义更新的日期和时间。|
|definitions_updated_minutes_ago|自上次防病毒定义更新以来的分钟数。|
|definitions_version|防病毒定义版本。|
|edr_client_version|设备上EDR客户端的版本。|
|edr_configuration_version|EDR配置版本。|
|edr_device_tags|与设备关联的标记列表。|
|edr_group_ids|设备关联的组 ID。|
|edr_machine_id|设备中使用的设备Microsoft Defender 安全中心。|
|engine_version|防病毒引擎的版本。|
|healthy|如果产品正常运行，则其为 True，否则为 false。|
|许可|如果设备已载入租户，则其为 True，否则为 false。|
|log_level|产品的当前日志级别。|
|machine_guid|防病毒组件使用的唯一计算机标识符。|
|network_protection_status|仅 macOS 中的网络 (状态) 。 可以是下列值之一： <ul><li>**starting** - 网络保护正在启动</li><li>**failed_to_start** - 由于错误，无法启动网络保护</li><li>**started** - 网络保护当前正在设备上运行</li><li>**正在重启** - 网络保护当前正在重新启动</li><li>**stopping** - 网络保护正在停止</li><li>**已停止** - 网络保护未运行</li></ul>|
|org_id|设备载入到的组织。 如果设备尚未载入任何组织，则打印时不可用。 有关载入详细信息，请参阅 [载入到 Microsoft Defender for Endpoint](onboarding.md)。|
|passive_mode_enabled|如果防病毒组件设置为在被动模式下运行，则其为 True，否则为 false。|
|product_expiration|当前产品版本达到支持终止的日期和时间。|
|real_time_protection_available|如果实时保护组件正常运行，则其为 True，否则为 false。|
|real_time_protection_enabled|如果启用了实时防病毒保护，则其参数为 True，否则为 false。|
|real_time_protection_subsystem|用于提供实时保护的子系统。 如果实时保护未如期运行，则打印将不可用。|
|release_ring|释放圈。 有关详细信息，请参阅部署 [圈](deployment-rings.md)。|
|
