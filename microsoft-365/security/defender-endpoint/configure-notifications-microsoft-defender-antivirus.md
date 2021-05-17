---
title: 配置Microsoft Defender 防病毒通知
description: 了解如何在终结点上配置和自定义标准Microsoft Defender 防病毒通知。
keywords: 通知， defender， 防病毒， 终结点， 管理， 管理员
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6e11c9394f250a6f3882183224f53954b1390a23
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274624"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>配置终结点上显示的通知

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

在Windows 10中，有关恶意软件检测和修正的应用程序通知更加可靠、一致且简洁。

完成手动触发和计划的扫描并检测到威胁后，终结点上会显示通知。 这些通知还会显示在 **通知中心** 中，并且扫描和威胁检测的摘要会定期显示。

还可以配置标准通知在终结点上的显示方式，例如重启通知或检测到并修正威胁时的通知。

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>配置终结点上显示的其他通知

可以在应用和组策略中配置其他通知的显示，如Windows 安全中心[威胁](microsoft-defender-security-center-antivirus.md)检测摘要。

> [!NOTE]
> 在 Windows 10 版本 1607 中，该功能称为增强型通知，可以在 Windows 设置  >  **Update & security Windows Defender**  >  **下配置**。 在所有版本的组策略设置中Windows 10，它称为增强 **型通知**。

> [!IMPORTANT]
> 禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。

**使用Windows 安全中心应用禁用其他通知：**

1. 通过Windows 安全中心任务栏中的防护图标或搜索 Defender 的"开始"菜单打开"开始 **"菜单。**

2. 单击病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后单击病毒防护威胁防护 **&标签：**

    ![Windows 安全应用中病毒和威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

3. 滚动到通知 **部分** ，然后单击更改 **通知设置**。

4. 将开关滑动到 **"关闭"** 或" **打开** "以禁用或启用其他通知。

**使用组策略禁用其他通知：**

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

3. 单击 **"管理模板"。**

4. 展开树以Windows **报告> Microsoft Defender 防病毒 >组件**。

5. 双击关闭 **增强型通知，** 将选项设置为 **已启用**。 单击“**确定**”。 这将阻止显示其他通知。

## <a name="configure-standard-notifications-on-endpoints"></a>在终结点上配置标准通知

可以使用组策略：

- 当用户需要执行一个操作时，在终结点上显示其他自定义文本
- 隐藏终结点上的所有通知
- 隐藏终结点上的重启通知

当你无法隐藏整个通知界面时，隐藏通知Microsoft Defender 防病毒很有用。 有关详细信息[，请参阅防止用户查看 Microsoft Defender 防病毒用户界面](prevent-end-user-interaction-microsoft-defender-antivirus.md)或与之交互。 

> [!NOTE]
> 隐藏通知将仅在策略已部署到的终结点上发生。 与在监视仪表板和报告上 (必须) 操作Microsoft Endpoint Manager Endpoint Protection[通知](/configmgr/protect/deploy-use/monitor-endpoint-protection)。 

有关[将自定义联系人信息添加到用户](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)计算机上看到的通知的说明，请参阅为组织自定义 Windows 安全中心 应用。

**使用组策略隐藏通知：**

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。

3. 展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。 

4. 双击"**取消所有通知"，** 将该选项设置为 **"已启用"。** 单击“**确定**”。 这将阻止显示其他通知。

**使用组策略隐藏重启通知：**

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

3. 单击 **"管理模板"。**

4. 展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。

5. 双击取消 **重启通知，** 将选项设置为 **已启用**。 单击“**确定**”。 这将阻止显示其他通知。

## <a name="related-topics"></a>相关主题

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [配置最终用户与最终用户的Microsoft Defender 防病毒](configure-end-user-interaction-microsoft-defender-antivirus.md)