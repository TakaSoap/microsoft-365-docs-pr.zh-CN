---
title: 网络钓鱼电子邮件攻击的示例
description: 逐步完成网络钓鱼攻击的示例分析。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 112bfd63a5f3667b22378790b62f3e33fba784d6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320293"
---
# <a name="example-of-a-phishing-email-attack"></a>网络钓鱼电子邮件攻击的示例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender可以帮助检测通过电子邮件传递的恶意附件。 由于 [Office 365](https://protection.office.com/) 安全与合规中心与 Microsoft 365 Defender 集成，因此安全分析师可以了解来自 Office 365 的威胁，例如通过电子邮件附件。

例如，为分析员分配了一个多阶段事件。
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="多阶段事件的示例。"::: 

在 **事件的警报** 选项卡中，将显示来自 Defender for Office 365 和 Microsoft Defender for Cloud Apps 的警报。 分析员可以通过选择电子邮件Office 365深入了解 Defender for Office 365警报。 警报的详细信息显示在侧窗格中。

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="电子邮件警报的示例。":::
 
通过进一步向下滚动，将显示更多信息，显示受到影响的恶意文件和用户。

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="电子邮件警报的用户和文件影响示例。":::
  
选择 **"打开** 警报"页，可让你查看特定警报，通过选择链接可以更详细地查看各种信息。 通过向面板底部选择"在 **资源管理器** 中查看邮件"可以查看实际电子邮件。
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="警报详细信息的示例。"::: 

这会将分析师打开"威胁管理"页，其中显示电子邮件"主题、收件人、发件人和其他信息"。 **"特殊****操作"下的** ZAP 告诉分析师"零时差自动清除"功能已实现。 ZAP 自动检测并删除整个组织邮箱中的恶意邮件和垃圾邮件。 有关详细信息，请参阅 EXCHANGE ONLINE 中的零[时 (ZAP) 清除](../office-365-security/zero-hour-auto-purge.md)。

可以通过选择"操作"，对特定邮件执行其他 **操作**。 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="可以针对电子邮件执行其他操作的示例。"::: 

## <a name="next-step"></a>后续步骤

请参阅 [基于身份的攻击调查](first-incident-path-identity.md) 路径。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
