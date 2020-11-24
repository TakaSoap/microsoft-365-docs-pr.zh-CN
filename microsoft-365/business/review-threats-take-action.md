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
description: 了解如何查看和管理 Windows 10 设备上的 Microsoft Defender 防病毒检测到的威胁。
ms.openlocfilehash: ffdf5cffb50d6145d6059233e0850839f4dfb582
ms.sourcegitcommit: 26b35012c42fef935d6c4a6509dde6c22a9b922a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385236"
---
# <a name="review-detected-threats-and-take-action"></a>查看检测到的威胁并执行操作

一旦检测到恶意文件或软件，Microsoft Defender 防病毒程序将阻止它运行，并阻止其运行。 在启用云提供保护的情况下，新检测到的威胁将添加到防病毒和反恶意软件引擎中，以便其他设备和用户也受到保护。

Microsoft Defender 防病毒检测并防止以下威胁类型：

- 设备上的病毒、恶意软件和基于 web 的威胁
- 网络钓鱼尝试
- 数据盗用尝试

作为 IT 专业人员/管理员，您可以查看在 Microsoft 365 管理中心内在 [Intune 中注册的 Windows 10 设备中的](/mem/intune/enrollment/device-enrollment) 威胁检测的相关信息。 你将看到摘要信息，例如：

- 需要防病毒保护的设备数量
- 有多少台设备不符合安全策略
- 当前活动、缓解或解决的威胁数

有几个选项可以查看有关威胁检测和设备的特定信息：

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中的 "**活动设备**" 页面。 请参阅本文中 [的在活动设备页上管理威胁检测](#manage-threat-detections-on-the-active-devices-page) 。
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中的 "**活动威胁**" 页。 请参阅本文中 [的管理威胁检测中的活动威胁页面](#manage-threat-detections-on-the-active-threats-page) 。
- <a href="https://endpoint.microsoft.com" target="_blank">Microsoft 终结点管理器</a>中的 **防病毒** 页面。 请参阅本文中的在 [Microsoft 终结点管理器中管理威胁检测](#manage-threat-detections-in-microsoft-endpoint-manager) 。

若要了解详细信息，请参阅 [Microsoft Defender 防病毒检测到的威胁](threats-detected-defender-av.md)。

## <a name="manage-threat-detections-on-the-active-devices-page"></a>在 " **活动设备** " 页上管理威胁检测

以下过程适用于拥有 Microsoft 365 商业高级版的客户。

1. 请转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，并登录。

2. 在导航页中，选择 "**设备**  >  **活动设备**"。 你将看到活动设备和详细信息的列表，如保护状态、防病毒 (AV) 保护状态和检测到的活动威胁数。

3. 选择一个设备，以查看有关该设备和可用操作的更多详细信息。 弹出窗口打开，其中包含建议和可用操作，例如， **更新策略**、 **更新防病毒**、 **运行快速扫描**、 **运行完全扫描** 等。

## <a name="manage-threat-detections-on-the-active-threats-page"></a>在 " **活动威胁** " 页上管理威胁检测

以下过程适用于拥有 Microsoft 365 商业高级版的客户。 [在 Intune 中](/mem/intune/enrollment/windows-enrollment-methods)，[必须对 Windows 10 设备进行保护](/microsoft-365/business/secure-win-10-pcs)和注册。

> [!NOTE]
> **Microsoft Defender 防病毒** 卡和 **活动威胁** 页面将分阶段推出，因此你可能无法立即访问它们。

1. 请转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ，并登录。

2. 在 **Microsoft Defender 防病毒** 卡上，选择 " **查看活动威胁**"。  (或者，在导航窗格中，选择 **Health**"  >  **& 防病毒**) 的运行状况威胁"。

3. 在 " **活动威胁** " 页上，选择一个检测到的威胁以了解更多相关信息。 弹出窗口打开，其中包含有关该威胁的详细信息，其中包括受影响的设备。

4. 在浮出控件上，选择一个设备以查看可用操作，例如 **更新策略**、 **更新防病毒**、 **运行快速扫描** 等。

## <a name="actions-you-can-take"></a>您可以执行的操作

当您查看有关特定威胁或设备的详细信息时，您将看到建议以及您可以执行的一个或多个操作。 下表介绍了您可能会看到的操作。<br><br>

| 操作 | 说明 |
|--|--|
| 配置保护 | 需要配置威胁防护策略。 选择要转到策略配置页的链接。<br><br>需要帮助？ 请参阅 [使用 Microsoft Intune 中的终结点安全策略管理设备安全性](/mem/intune/protect/endpoint-security-policy)。 |
| 更新策略 | 您的防病毒和实时保护策略需要更新或配置。 选择要转到 "策略配置" 页的链接。<br><br>需要帮助？ 请参阅 [使用 Microsoft Intune 中的终结点安全策略管理设备安全性](/mem/intune/protect/endpoint-security-policy)。 |
| 运行快速扫描 | 在设备上启动快速防病毒扫描，重点关注恶意软件可能注册的常见位置，如注册表项和已知 Windows 启动文件夹。 |
| 运行完全扫描 | 在设备上启动完整的防病毒扫描，重点关注恶意软件可能注册的常见位置，并包括设备上的每个文件和文件夹。 将结果发送到 [Microsoft 终结点管理器](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 更新防病毒 | 要求设备获取 [安全智能更新](https://go.microsoft.com/fwlink/?linkid=2149926) 以实现防病毒和反恶意软件保护。 |
| 重启设备 | 强制 Windows 10 设备在五分钟内重新启动。<br><br>**重要说明：** 不会自动通知设备所有者或用户重新启动，并且可能会丢失未保存的工作。 |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>在 Microsoft 终结点管理器中管理威胁检测

您可以使用 Microsoft 终结点管理器来管理威胁检测。 Windows 10 设备必须在 Intune (部分 Microsoft 终结点管理器 [中注册](/mem/intune/enrollment/windows-enrollment-methods)) 。

1. 转到 "Microsoft 终结点管理器管理中心" <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> ，然后登录。

2. 在导航窗格中，选择 " **端点安全性**"。

3. 在 " **管理**" 下，选择 " **防病毒**"。 你将看到几个选项卡，如 **摘要**、 **windows 10 不正常的终结点** 和 **windows 10 检测到的恶意软件**。

4. 查看可用选项卡上的信息，然后执行任何所需的操作。

例如，假设 " **Windows 10 检测到的恶意软件** " 选项卡上列出了设备。选择设备时，将执行某些操作，如 **重启**、 **快速扫描**、 **完全扫描**、 **同步** 或 **更新签名**。 为该设备选择操作。

下表介绍了在 Microsoft 终结点管理器中可能会看到的操作。<br><br>

| 操作 | 说明 |
|--|--|
| Restart | 强制 Windows 10 设备在五分钟内重新启动。<br><br>**重要说明：** 不会自动通知设备所有者或用户重新启动，并且可能会丢失未保存的工作。 |
| 快速扫描 | 在设备上启动快速防病毒扫描，重点关注恶意软件可能注册的常见位置，如注册表项和已知 Windows 启动文件夹。 将结果发送到 [Microsoft 终结点管理器](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 完全扫描 | 在设备上启动完整的防病毒扫描，重点关注恶意软件可能注册的常见位置，并包括设备上的每个文件和文件夹。 将结果发送到 [Microsoft 终结点管理器](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。 |
| 同步 | 需要设备在 Microsoft 终结点管理器) 中签入 Intune (部分。 设备签入时，设备会接收任何挂起的操作或分配给该设备的策略。 |
| 更新签名 | 要求设备获取 [安全智能更新](https://go.microsoft.com/fwlink/?linkid=2149926) 以实现防病毒和反恶意软件保护。 |

> [!TIP]
> 有关详细信息，请参阅 [适用于设备的远程操作](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)。

## <a name="how-to-submit-a-file-for-malware-analysis"></a>如何提交文件以进行恶意软件分析

如果您有一个您认为错过或错误地归类为恶意软件的文件，则可以将该文件提交给 Microsoft 进行恶意软件分析。 用户和 IT 管理员可以提交文件进行分析。 访问 [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) 。
