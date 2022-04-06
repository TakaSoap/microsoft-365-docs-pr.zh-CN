---
title: 查看检测到的威胁并执行操作
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 了解如何在设备上查看和管理由Microsoft Defender 防病毒检测到Windows 10威胁。
ms.openlocfilehash: c836554445f56a9a915885d55a4490c6bb5bd1a9
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64633207"
---
# <a name="review-detected-threats-and-take-action"></a>查看检测到的威胁并执行操作

一旦检测到恶意文件或软件，Microsoft Defender 防病毒阻止它并阻止它运行。 启用云保护后，新检测到的威胁将添加到防病毒和反恶意软件引擎，以便其他设备和用户也受到保护。

Microsoft Defender 防病毒检测并防范以下类型的威胁：

- 设备上基于病毒、恶意软件和基于 Web 的威胁
- 网络钓鱼尝试
- 数据盗窃尝试

作为 IT 专业人员/管理员，你可以查看有关在 Windows 10 中注册的跨 Windows 10 设备[Intune威胁Microsoft 365 管理中心](/mem/intune/enrollment/device-enrollment)。 你将看到摘要信息，例如：

- 需要防病毒保护的设备数
- 多少设备不符合安全策略
- 当前处于活动状态、已缓解或已解决的威胁

有几种选项可以查看有关威胁检测和设备的特定信息：

- "**活动设备"**<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">页Microsoft 365 管理中心。</a> 请参阅 [本文中的在活动设备上管理](#manage-threat-detections-on-the-active-devices-page) 威胁检测。
- 活动 **威胁页面中**<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心。</a> 请参阅 [本文中"活动威胁"页面上的"](#manage-threat-detections-on-the-active-threats-page) 管理威胁检测"。
- "**防病毒"**<a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">页Microsoft Endpoint Manager。</a> 请参阅[本文Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager)中管理威胁检测。

若要了解更多信息，请参阅威胁[检测Microsoft Defender 防病毒](threats-detected-defender-av.md)。

## <a name="manage-threat-detections-on-the-active-devices-page"></a>在"活动设备" **页上管理威胁** 检测

以下过程适用于已购买Microsoft 365 商业高级版。

1. 转到 "Microsoft 365 管理中心"并<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>登录。

2. 在导航页中，选择 **DevicesActive** >  **设备**。 你将看到活动设备和详细信息的列表，例如保护状态、防病毒 (AV) 保护状态以及检测到的活动威胁数量。

3. 选择设备以查看有关该设备和可用操作的详细信息。 将打开一个包含建议和可用操作（如更新策略、更新防病毒、**运行快速扫描**、**运行完全** 扫描等）的飞出窗口。

## <a name="manage-threat-detections-on-the-active-threats-page"></a>在"活动威胁" **页上管理威胁** 检测

以下过程适用于已购买Microsoft 365 商业高级版。 [Windows 10设备必须是安全的，](../setup/secure-win-10-pcs.md)[并且必须在 Intune 中注册](/mem/intune/enrollment/windows-enrollment-methods)。

> [!NOTE]
> the **Microsoft Defender 防病毒** card and **Active threats** page are being rolled out in phases， so you may not have immediate access to them.

1. 转到 "Microsoft 365 管理中心"并<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>登录。

2. 在"**Microsoft Defender 防病毒**"卡上，选择"**查看活动威胁"**。  (，或者，在导航窗格中， > 选择"运行状况""&**防病毒**"。) 

3. 在 **"活动威胁"** 页面上，选择检测到的威胁以了解有关它的信息。 随即打开一个包含有关该威胁的详细信息的飞出图，其中包括受影响的设备。

4. 在飞出上，选择一台设备以查看可用操作，如更新策略、更新防病毒、**运行快速扫描** 等。

## <a name="actions-you-can-take"></a>可采取的操作

当你查看有关特定威胁或设备的详细信息时，你将看到建议以及你可以采取的一个或多个操作。 下表介绍了您可能看到的操作。<br><br>

| 操作 | 说明 |
|--|--|
| 配置保护 | 需要配置威胁防护策略。 选择链接以转到策略配置页面。<br><br>需要帮助？ 请参阅[使用 Microsoft Intune 中的终结点安全策略管理设备Microsoft Intune](/mem/intune/protect/endpoint-security-policy)。 |
| 更新策略 | 需要更新或配置防病毒和实时保护策略。 选择链接以转到策略配置页面。<br><br>需要帮助？ 请参阅[使用 Microsoft Intune 中的终结点安全策略管理设备Microsoft Intune](/mem/intune/protect/endpoint-security-policy)。 |
| 运行快速扫描 | 在设备上启动快速防病毒扫描，重点关注可能注册恶意软件的常见位置，例如注册表项和启动Windows已知位置。 |
| 运行完全扫描 | 在设备上启动完全防病毒扫描，重点关注可能注册恶意软件的常见位置，包括设备上每个文件和文件夹。 结果将发送到[Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 更新防病毒 | 需要设备获取 [防病毒和](https://go.microsoft.com/fwlink/?linkid=2149926) 反恶意软件保护的安全智能更新。 |
| 重启设备 | 强制Windows 10设备在五分钟内重启。<br><br>**重要提示：** 设备所有者或用户不会自动收到重启通知，并且可能会丢失未保存的工作。 |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>管理威胁检测Microsoft Endpoint Manager

可以使用安全Microsoft Endpoint Manager威胁检测。 Windows 10设备必须[注册到Intune (](/mem/intune/enrollment/windows-enrollment-methods)部分Microsoft Endpoint Manager) 。

1. 转到管理Microsoft Endpoint Manager中心，<a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a>然后登录。

2. 在导航窗格中，选择" **终结点安全性"**。

3. 在 **"管理**"下， **选择"防病毒"**。 你将看到多个选项卡，例如"摘要"、Windows 10 **不正常** 的终结点以及Windows 10 **恶意软件**。

4. 查看可用选项卡上的信息，然后执行任何所需操作。

例如，假设设备已列在"检测到Windows 10 **"选项卡** 上。当你选择设备时，你将具有某些可用的操作，例如重新启动、**快速** 扫描、**完全** 扫描、**同步** 或 **更新签名**。 选择该设备的操作。

下表介绍了您可能在操作记录中Microsoft Endpoint Manager。<br><br>

| 操作 | 说明 |
|--|--|
| Restart | 强制Windows 10设备在五分钟内重启。<br><br>**重要提示：** 设备所有者或用户不会自动收到重启通知，并且可能会丢失未保存的工作。 |
| 快速扫描 | 在设备上启动快速防病毒扫描，重点关注可能注册恶意软件的常见位置，例如注册表项和启动Windows已知位置。 结果将发送到[Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 完整扫描 | 在设备上启动完全防病毒扫描，重点关注可能注册恶意软件的常见位置，包括设备上每个文件和文件夹。 结果将发送到[Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 同步 | 需要使用设备签入Intune (部分Microsoft Endpoint Manager) 。 当设备进行检查时，设备会收到分配给该设备的任何挂起的操作或策略。 |
| 更新签名 | 需要设备获取 [防病毒和](https://go.microsoft.com/fwlink/?linkid=2149926) 反恶意软件保护的安全智能更新。 |

> [!TIP]
> 有关详细信息，请参阅 [设备的远程操作](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>如何提交文件进行恶意软件分析

如果你有一个你认为遗漏或错误分类为恶意软件的文件，可以将该文件提交给 Microsoft 进行恶意软件分析。 用户和 IT 管理员可以提交文件进行分析。 访问 [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../../admin/security-and-compliance/secure-your-business-data.md)

[从](../../security/defender-business/mdb-overview.md) 2022 Microsoft Defender 商业版 (2022 年 3 月 1 Microsoft 365 商业高级版，) 