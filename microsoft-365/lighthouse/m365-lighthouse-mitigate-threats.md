---
title: 使用Microsoft Defender 防病毒缓解威胁
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
description: 对于使用Microsoft 365 Lighthouse (MSP) 的托管服务提供商，请了解Microsoft Defender 防病毒缓解威胁。
ms.openlocfilehash: 428370ce5e49bba0bc9489143864f9b88b2e8c3f
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824325"
---
# <a name="mitigate-threats-with-microsoft-defender-antivirus"></a>使用Microsoft Defender 防病毒缓解威胁

Microsoft 365 Lighthouse使合作伙伴能够调查和缓解所有租户中的威胁。 还可以在设备上启动防病毒扫描，确保设备获取最新更新以进行Microsoft Defender 防病毒，并查看防病毒扫描后的挂起操作。 Lighthouse 仅支持运行Windows 10或更高版本的设备。

## <a name="before-you-begin"></a>准备工作

- Microsoft 365 Lighthouse仅部署在合作伙伴租户中， 不在客户租户中， 但请确保你和你的客户租户满足[Microsoft 365 Lighthouse要求](m365-lighthouse-requirements.md)中列出的要求。

- 用户必须运行Microsoft Defender 防病毒 (包含在Windows) 中。 Lighthouse 不支持非 Microsoft 防病毒软件。 有关详细信息，请参阅[“打开Microsoft Defender 防病毒](/mem/intune/user-help/turn-on-defender-windows)”。

- 您必须是登录到的合作伙伴租户中的全局管理员。

## <a name="investigate-active-threats"></a>调查活动威胁

若要调查特定威胁，请执行以下操作：

1. 在 Lighthouse 的左侧导航窗格中，选择 **“威胁管理**”。

2. 选择 **“威胁”** 选项卡。

3. 从威胁列表中，选择要调查的威胁。

威胁详细信息窗格提供以下信息：

| 类别                                      | Definition                                                                                                   |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| 设备和租户                             | 发现威胁的设备名称和租户。 选择设备名称以查看其他信息。 |
| 威胁状态                                 | 威胁的状态。                                                                                    |
| 威胁类型                                   | 威胁的类型。                                                                                              |
| 威胁严重性                               | 威胁严重 (严重、高、中、低、未知)                                                     |
| 实例                                     | 设备上存在的此威胁的实例数。                                                    |
| 首次检测到                                | 首次在此设备上检测到威胁时。                                                           |
| 文档                                 | 链接到有关威胁的其他信息。                                                             |
| 此租户上具有此威胁的其他设备 | 同一租户中具有相同活动威胁的其他设备的列表。                                      |
| 具有此威胁的其他租户                | 具有相同活动威胁的其他租户的列表。                                                         |

调查特定设备上的威胁：

1. 在 Lighthouse 的左侧导航窗格中，选择 **“威胁管理**”。

2. 选择 **“防病毒保护** ”选项卡。

3. 从列表中选择设备。

4. 在设备详细信息窗格中，选择“ **当前威胁** ”选项卡。

灯塔显示在设备上找到的所有威胁。 若要查看详细信息，请选择威胁。

## <a name="scan-for-threats-on-a-device"></a>扫描设备上的威胁

快速扫描搜索可能存在恶意软件的常见位置，例如注册表项和已知启动文件夹。 完全扫描会搜索整个设备。 在大多数情况下，快速扫描已足够，是计划扫描的建议选项。

1. 在 Lighthouse 的左侧导航窗格中，选择 **“威胁管理**”。

2. 选择 **“防病毒保护** ”选项卡。

3. 从设备列表中，选择一个设备。

4. 在设备详细信息窗格中，选择 **“运行完整扫描** ”或 **“运行快速扫描**”。

还可以通过选择列表中每个设备名称旁边的复选框，然后选择 **“运行完整扫描** ”或 **“运行快速扫描”** 来扫描多个设备。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>获取Microsoft Defender 防病毒更新

若要在单个设备上更新Microsoft Defender 防病毒：

1. 在 Lighthouse 的左侧导航窗格中，选择 **“威胁管理**”。

2. 选择 **“防病毒保护** ”选项卡。

3. 从设备列表中，选择一个设备。

4. 在“设备详细信息”窗格中，选择 **“更新防病毒”。**

可以通过选择列表中每个设备名称旁边的复选框，然后选择 **“更新防病毒**”来获取多个设备的更新。

如果需要创建新策略，请从设备详细信息窗格中选择 **“更新** 策略”。 Lighthouse 会将你重定向到 Microsoft Endpoint Manager (MEM) 。 有关创建策略的详细信息，请参阅[Microsoft Intune中创建合规性策略](/mem/intune/protect/create-compliance-policy)。

## <a name="check-pending-antivirus-actions-on-a-device"></a>检查设备上挂起的防病毒操作

将连续操作应用到设备时，将收到一条挂起的操作消息。 检查设备上挂起的操作：

1. 在 Lighthouse 的左侧导航窗格中，选择 **“威胁管理**”。

2. 选择 **“防病毒保护** ”选项卡。

3. 从设备列表中，选择一个设备。

4. 在“设备详细信息”窗格中，选择 **“设备操作状态** ”选项卡以查看挂起的操作。

## <a name="restart-a-device"></a>重新启动设备

某些更新可能需要设备重启才能正确安装。

1. 在 Lighthouse 的左侧导航窗格中，选择 **“威胁管理**”。

2. 选择 **“防病毒保护** ”选项卡。

3. 从设备列表中，选择一个设备。

4. 在“设备详细信息”窗格中，选择 **“重启”设备**。

还可以通过选择列表中每个设备名称旁边的复选框，然后选择 **“重启”设备** 来重启多个设备。

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse (](m365-lighthouse-requirements.md)文章) \ 的要求
[威胁管理页概述](m365-lighthouse-threat-management-page-overview.md) (文章) \
[在Microsoft Intune (文章) \ 中创建合规性](/mem/intune/protect/create-compliance-policy)策略
[打开Microsoft Defender 防病毒 (](/mem/intune/user-help/turn-on-defender-windows)文章) \
[Microsoft 安全智能](https://www.microsoft.com/wdsi/threats) (网页) 
