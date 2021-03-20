---
title: 查看检测到的威胁并执行操作
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 了解如何在 Windows 10 设备上查看和管理 Microsoft Defender 防病毒检测到的威胁。
ms.openlocfilehash: 15e99fb75e4a3ac1af842ca7d0b900e02cbc6bd4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912782"
---
# <a name="review-detected-threats-and-take-action"></a>查看检测到的威胁并执行操作

一旦检测到恶意文件或软件，Microsoft Defender 防病毒就会阻止它并阻止它运行。 启用云保护后，新检测到的威胁将添加到防病毒和反恶意软件引擎，以便其他设备和用户也受到保护。

Microsoft Defender 防病毒可检测并防范以下类型的威胁：

- 设备上基于病毒、恶意软件和基于 Web 的威胁
- 网络钓鱼尝试
- 数据盗窃尝试

作为 IT 专业人员/管理员，可以在 Microsoft 365 管理中心查看在 Intune 中注册的 [跨 Windows 10](/mem/intune/enrollment/device-enrollment) 设备的威胁检测信息。 你将看到摘要信息，例如：

- 需要防病毒保护的设备数
- 多少设备不符合安全策略
- 当前处于活动状态、已缓解或已解决的威胁

有几种选项可以查看有关威胁检测和设备的特定信息：

- Microsoft  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a>管理中心中的"活动设备"页面。 请参阅 [本文中的在活动设备上管理](#manage-threat-detections-on-the-active-devices-page) 威胁检测。
- Microsoft  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a>管理中心中的"活动威胁"页面。 请参阅 [本文中"活动威胁"页面上的"](#manage-threat-detections-on-the-active-threats-page) 管理威胁检测"。
- Microsoft **Endpoint** Manager 中的 <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">防病毒页面</a>。 请参阅 [本文中的在 Microsoft Endpoint Manager 中管理](#manage-threat-detections-in-microsoft-endpoint-manager) 威胁检测。

若要了解更多信息，请参阅 [Microsoft Defender 防病毒检测到的威胁](threats-detected-defender-av.md)。

## <a name="manage-threat-detections-on-the-active-devices-page"></a>在"活动设备" **页上管理威胁** 检测

以下过程适用于拥有 Microsoft 365 商业高级版的客户。

1. 转到 Microsoft 365 管理中心 ， <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 然后登录。

2. 在导航页中，选择 **"设备**  >  **""活动设备"。** 你将看到活动设备和详细信息的列表，如保护状态、防病毒 (AV) 保护状态以及检测到的活动威胁数量。

3. 选择设备以查看有关该设备和可用操作的详细信息。 将打开一个包含建议和可用操作（如 **更新** 策略、更新防病毒、**运行快速** 扫描、**运行完全** 扫描等）的飞出窗口。

## <a name="manage-threat-detections-on-the-active-threats-page"></a>在"活动威胁" **页上管理威胁** 检测

以下过程适用于拥有 Microsoft 365 商业高级版的客户。 [Windows 10 设备必须是安全的，](./secure-win-10-pcs.md)[并且必须在 Intune 中注册](/mem/intune/enrollment/windows-enrollment-methods)。

> [!NOTE]
> **Microsoft Defender 防病毒** 卡 **和活动** 威胁页面正在阶段推出，因此你可能无法立即访问它们。

1. 转到 Microsoft 365 管理中心 ， <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 然后登录。

2. 在 **Microsoft Defender 防病毒卡** 上，选择查看 **活动威胁**。  (，或者，在导航窗格中，选择"运行状况威胁&  >  **防病毒**.) 

3. 在 **"活动威胁"** 页面上，选择检测到的威胁以了解有关它的信息。 随即打开一个包含有关该威胁的详细信息的飞出图，其中包括受影响的设备。

4. On the flyout， select a device to view available actions， such as **Update policy，** **Update antivirus，** **Run quick scan，** and more.

## <a name="actions-you-can-take"></a>可采取的操作

当你查看有关特定威胁或设备的详细信息时，你将看到建议以及你可以采取的一个或多个操作。 下表介绍了您可能看到的操作。<br><br>

| 操作 | 说明 |
|--|--|
| 配置保护 | 需要配置威胁防护策略。 选择链接以转到策略配置页面。<br><br>需要帮助？ 请参阅 [使用 Microsoft Intune 中的终结点安全策略管理设备安全](/mem/intune/protect/endpoint-security-policy)。 |
| 更新策略 | 需要更新或配置防病毒和实时保护策略。 选择链接以转到策略配置页面。<br><br>需要帮助？ 请参阅 [使用 Microsoft Intune 中的终结点安全策略管理设备安全](/mem/intune/protect/endpoint-security-policy)。 |
| 运行快速扫描 | 在设备上启动快速防病毒扫描，侧重于可能注册恶意软件的常见位置，例如注册表项和已知的 Windows 启动文件夹。 |
| 运行完全扫描 | 在设备上启动完全防病毒扫描，重点关注可能注册恶意软件的常见位置，包括设备上每个文件和文件夹。 结果将发送到 [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 更新防病毒 | 需要设备获取 [防病毒和](https://go.microsoft.com/fwlink/?linkid=2149926) 反恶意软件保护的安全智能更新。 |
| 重新启动设备 | 强制 Windows 10 设备在 5 分钟内重启。<br><br>**重要提示：** 设备所有者或用户不会自动收到重启通知，并且可能会丢失未保存的工作。 |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>在 Microsoft Endpoint Manager 中管理威胁检测

可以使用 Microsoft Endpoint Manager 管理威胁检测。 Windows 10 设备必须在 [Intune](/mem/intune/enrollment/windows-enrollment-methods) 中注册 (Microsoft Endpoint Manager) 。

1. 转到 Microsoft Endpoint Manager 管理中心 ， <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> 然后登录。

2. 在导航窗格中，选择终结点 **安全**。

3. 在 **"管理"** 下，**选择"防病毒"。** 你将看到多个选项卡，如摘要 **、Windows 10 不正常** 终结点和 **Windows 10 检测到的恶意软件**。 

4. 查看可用选项卡上的信息，然后执行任何所需操作。

例如，假设设备列在 **Windows 10** 检测到的恶意软件选项卡上。当你选择设备时，你将具有某些可用的操作，例如重新启动、**快速** 扫描、**完全** 扫描、**同步** 或 **更新签名**。 选择该设备的操作。

下表介绍了你可能会在 Microsoft Endpoint Manager 中看到的操作。<br><br>

| 操作 | 说明 |
|--|--|
| Restart | 强制 Windows 10 设备在 5 分钟内重启。<br><br>**重要提示：** 设备所有者或用户不会自动收到重启通知，并且可能会丢失未保存的工作。 |
| 快速扫描 | 在设备上启动快速防病毒扫描，侧重于可能注册恶意软件的常见位置，例如注册表项和已知的 Windows 启动文件夹。 结果将发送到 [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 完全扫描 | 在设备上启动完全防病毒扫描，重点关注可能注册恶意软件的常见位置，包括设备上每个文件和文件夹。 结果将发送到 [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 同步 | 需要设备在 Microsoft Endpoint Manager (Intune 中) 。 当设备进行检查时，设备会收到分配给该设备的任何挂起的操作或策略。 |
| 更新签名 | 需要设备获取 [防病毒和](https://go.microsoft.com/fwlink/?linkid=2149926) 反恶意软件保护的安全智能更新。 |

> [!TIP]
> 有关详细信息，请参阅 [设备的远程操作](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>如何提交文件进行恶意软件分析

如果你有一个你认为遗漏或错误分类为恶意软件的文件，可以将该文件提交给 Microsoft 进行恶意软件分析。 用户和 IT 管理员可以提交文件进行分析。 访问 [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) 。