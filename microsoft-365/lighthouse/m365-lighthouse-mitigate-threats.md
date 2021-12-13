---
title: 使用威胁缓解Microsoft Defender 防病毒
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，请了解使用托管服务提供商Microsoft Defender 防病毒。
ms.openlocfilehash: 3d7eeb54c6f11e73bca71271faa7c09b30627ec2
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61424025"
---
# <a name="mitigate-threats-with-microsoft-defender-antivirus"></a>使用威胁缓解Microsoft Defender 防病毒

> [!NOTE]
> 本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅注册[Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse合作伙伴可以跨所有租户调查和缓解威胁。 还可以在设备上启动防病毒扫描，确保设备正在获取最新 Microsoft Defender 防病毒，并查看防病毒扫描后挂起的操作。 Lighthouse 仅支持运行 Windows 10或更高版本的设备。

## <a name="before-you-begin"></a>准备工作

- Microsoft 365 Lighthouse仅在合作伙伴租户中部署，而不是在客户租户中，但请确保你和客户租户满足 Microsoft 365 Lighthouse[要求中列出的要求](m365-lighthouse-requirements.md)。

- 用户必须运行 Microsoft Defender 防病毒 (中包含的Windows) 。 Lighthouse 不支持非 Microsoft 防病毒软件。 有关详细信息，请参阅打开[Microsoft Defender 防病毒。](/mem/intune/user-help/turn-on-defender-windows)

- 你必须是要登录的合作伙伴租户中的全局管理员。

## <a name="investigate-active-threats"></a>调查活动威胁

若要调查特定威胁：

1. In the left navigation pane in Lighthouse， select **Threat management**.

2. 选择" **威胁"** 选项卡。

3. 从威胁列表中，选择要调查的威胁。

威胁详细信息窗格提供以下信息：

| 类别                                      | Definition                                                                                                   |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| 设备和租户                             | 找到威胁的设备名称和租户。 选择设备名称以查看其他信息。 |
| 威胁状态                                 | 威胁的状态。                                                                                    |
| 威胁类型                                   | 威胁的类型。                                                                                              |
| 威胁严重性                               | 威胁严重性 (严重、高、中等、低、未知)                                                     |
| 实例                                     | 设备上存在此威胁的实例数。                                                    |
| 首次检测到                                | 在此设备上首次检测到威胁时。                                                           |
| 文档                                 | 指向有关威胁的其他信息的链接。                                                             |
| 此租户上具有此威胁的其他设备 | 同一租户中具有相同活动威胁的其他设备列表。                                      |
| 具有此威胁的其他租户                | 具有相同活动威胁的其他租户的列表。                                                         |

调查特定设备上的威胁：

1. In the left navigation pane in Lighthouse， select **Threat management**.

2. 选择 **"防病毒保护"** 选项卡。

3. 从列表中选择设备。

4. 从设备详细信息窗格中，选择" **当前威胁"** 选项卡。

Lighthouse 显示设备上发现的所有威胁。 若要查看详细信息，请选择威胁。

## <a name="scan-for-threats-on-a-device"></a>扫描设备上的威胁

快速扫描可搜索恶意软件可能位于的常见位置，例如注册表项，并知道启动文件夹。 完全扫描将搜索整个设备。 在大多数情况下，快速扫描已足够，是计划扫描的推荐选项。

1. In the left navigation pane in Lighthouse， select **Threat management**.

2. 选择 **"防病毒保护"** 选项卡。

3. 从设备列表中，选择设备。

4. 在设备详细信息窗格中，选择运行 **完全扫描** 或 **运行快速扫描**。

通过选中列表中每个设备名称旁边的复选框，然后选择"运行完全扫描"或"运行快速扫描"，还可以 **扫描多个设备**。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>获取更新Microsoft Defender 防病毒

若要在Microsoft Defender 防病毒设备上更新设备：：

1. In the left navigation pane in Lighthouse， select **Threat management**.

2. 选择 **"防病毒保护"** 选项卡。

3. 从设备列表中，选择设备。

4. 在设备详细信息窗格中，选择 **更新防病毒**。

可以通过选中列表中每个设备名称旁边的复选框获取多个设备的更新，然后选择"**更新防病毒"。**

如果需要创建新策略，请从设备详细信息 **窗格中** 选择"更新策略"。 Lighthouse 会将你重定向到Microsoft Endpoint Manager (MEM) 。 有关创建策略的信息，[请参阅在策略](/mem/intune/protect/create-compliance-policy)Microsoft Intune。

## <a name="check-pending-antivirus-actions-on-a-device"></a>检查设备上挂起的防病毒操作

当连续操作应用于设备时，你将收到操作挂起消息。 检查设备上挂起的操作：

1. In the left navigation pane in Lighthouse， select **Threat management**.

2. 选择 **"防病毒保护"** 选项卡。

3. 从设备列表中，选择设备。

4. 在设备详细信息窗格中，选择" **设备操作状态"** 选项卡以查看挂起的操作。

## <a name="restart-a-device"></a>重新启动设备

某些更新可能需要重新启动设备才能正确安装。

1. In the left navigation pane in Lighthouse， select **Threat management**.

2. 选择 **"防病毒保护"** 选项卡。

3. 从设备列表中，选择设备。

4. 在设备详细信息窗格中，选择重启 **设备**。

还可以重新启动多个设备，只需选中列表中每个设备名称旁边的复选框，然后选择"**重新启动设备"。**

## <a name="related-content"></a>相关内容

[本文Microsoft 365 Lighthouse (](m365-lighthouse-requirements.md)要求) \
[威胁管理页面概述 (](m365-lighthouse-threat-management-page-overview.md) 文章) \
[在本文Microsoft Intune (](/mem/intune/protect/create-compliance-policy)创建合规性) \
[打开Microsoft Defender 防病毒 (](/mem/intune/user-help/turn-on-defender-windows)文章) \
[Microsoft 安全智能](https://www.microsoft.com/wdsi/threats)
