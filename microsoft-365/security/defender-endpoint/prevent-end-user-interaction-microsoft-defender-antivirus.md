---
title: 隐藏Microsoft Defender 防病毒接口
description: 可以在应用内隐藏病毒和威胁Windows 安全中心磁贴。
keywords: ui 锁定， 无头模式， 隐藏应用， 隐藏设置， 隐藏界面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/23/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 9a16abdcbc219a950eff6ddc8bb48018c4ba3279
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209305"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>阻止用户查看或Microsoft Defender 防病毒用户界面

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用组策略阻止终结点上的用户看到 Microsoft Defender 防病毒 界面。 还可以阻止他们暂停扫描。

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>隐藏Microsoft Defender 防病毒接口

在 Windows 10 版本 1703 中，隐藏界面将隐藏 Microsoft Defender 防病毒 通知，并防止病毒&威胁防护磁贴显示在 Windows 安全中心 应用中。

将设置设置为"**已启用"：**

:::image type="content" source="../../media/wdav-headless-mode-off-1703.png" alt-text="无防护Windows 安全中心病毒和威胁防护部分的内容屏幕截图。":::

将设置设置为"已 **禁用"** 或未配置：

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="具有防护Windows 安全中心和威胁防护部分的内容屏幕截图。":::

> [!NOTE]
> 隐藏界面还会阻止Microsoft Defender 防病毒在终结点上显示通知。 Microsoft Defender for Endpoint 通知仍将显示。 还可以单独 [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)

在早期版本的 Windows 10 中，该设置将Windows Defender客户端接口。 如果用户尝试打开它，他们将收到一条警告，指出"你的系统管理员已限制对此应用的访问"。

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="在 1703 之前的版本Windows 10无头模式时显示警告消息":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>使用组策略向用户隐藏 Microsoft Defender AV 界面

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**

2. 使用组 **策略管理编辑器转到** 计算机 **配置**。

3. 单击 **"管理模板"。**

4. 展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。

5. 双击启用 **无头 UI 模式** 设置，将选项设置为 **已启用**。 单击“**确定**”。

有关 [阻止用户修改其电脑保护](configure-local-policy-overrides-microsoft-defender-antivirus.md) 的更多选项，请参阅防止用户在本地修改策略设置。

## <a name="prevent-users-from-pausing-a-scan"></a>阻止用户暂停扫描

你可以阻止用户暂停扫描，这有助于确保计划扫描或按需扫描不会被用户中断。

> [!NOTE]
> 此设置在系统上Windows 10。

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>使用组策略阻止用户暂停扫描

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**

2. 使用组 **策略管理编辑器转到** 计算机 **配置**。

3. 单击 **"管理模板"。**

4. 展开树以Windows **扫描** \> **Microsoft Defender 防病毒** \> **组件**。

5. 双击允许用户暂停 **扫描设置** ，将选项设置为 **已禁用**。 单击“**确定**”。

## <a name="related-articles"></a>相关文章

- [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
- [配置最终用户与最终用户的Microsoft Defender 防病毒](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
