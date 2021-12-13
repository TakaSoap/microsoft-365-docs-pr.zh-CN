---
title: '了解 Microsoft Defender for Business 预览版中的下一代 (配置) '
description: '了解 Microsoft Defender for Business 预览版中下一代保护 (配置) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 619d3a03789eab7e525a6d4d07621d7950e907cb
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423259"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business-preview"></a>了解 Microsoft Defender for Business 预览版中的下一代 (配置) 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未 (一些) 。

Microsoft Defender for Business 预览版中的下一代 (包括) 防病毒和反恶意软件保护。 默认策略旨在保护设备和用户，而不受工作效率的影响;但是，您也可以自定义策略以满足业务需求。 

**本文介绍**：

- [下一代保护设置和选项](#next-generation-protection-settings-and-options)
- [其他预配置设置](#additional-preconfigured-settings) 

## <a name="next-generation-protection-settings-and-options"></a>下一代保护设置和选项

下表列出了设置和选项：<br/><br/>

| Setting | 说明 |
|:---|:---|
| **实时保护**  |  |
| **打开实时保护** | 默认情况下启用实时保护，可查找并阻止恶意软件在设备上运行。 *我们建议保持启用实时保护。*<br/><br/>当实时保护打开时，它将配置以下设置：<br/>- 在 [AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender) (中启用行为) <br/>- 所有下载的文件和附件都 ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender)) <br/>- Microsoft 浏览器中使用的脚本在[AllowScriptScanning (扫描) ](/windows/client-management/mdm/policy-csp-defender)   |
| **首次看到时阻止** | 默认情况下启用，"首次看到时阻止"将在检测的几秒钟内阻止恶意软件，增加 (（以秒) 允许提交示例文件进行分析）的时间，并设置检测级别为"高"。 *我们建议将"首次看到时阻止"保持打开。*<br/><br/>当"首次看到时阻止"处于打开时，它会为"首次看到"配置以下Microsoft Defender 防病毒： <br/>- 阻止和扫描可疑文件设置为 [CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender) (高级) <br/>- 在 [CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender) 中，要阻止和检查的文件 (秒数)  <br/><br/>**重要** 提示：如果"首次看到时阻止"处于关闭状态，则会影响和 `CloudBlockLevel` `CloudExtendedTimeout` Microsoft Defender 防病毒。  |
| **启用网络保护功能** | 启用后，网络保护可帮助防范网络钓鱼欺诈、攻击托管网站和 Internet 上的恶意内容。 它还可防止用户关闭网络保护。<br/><br/>网络保护可以设置为以下模式之一：<br/>- **阻止模式** (默认设置，) 阻止用户访问被视为不安全的网站。 *我们建议将网络保护设置为阻止模式。*<br/>- **审核模式**，允许用户访问可能不安全的网站，并跟踪这些站点之间的网络活动 <br/>- **禁用模式**，此模式阻止用户访问可能不安全的网站，或跟踪这些网站中的网络活动 |
| **修正**  |  |
| **针对 PUA 应用中可能不需要 (的操作)** | PUA 可以包括广告软件、捆绑软件，用于安装其他未签名的软件，以及尝试破坏安全功能的恶意软件。 尽管 PUA 不一定是病毒、恶意软件或其他类型的威胁，但 PUA 可能会影响设备性能。<br/><br/>PUA 保护会阻止被检测为 PUA 的项目。 你可以将 PUA 保护设置为以下设置之一： <br/>- **已启用** (此设置是默认) ，可阻止在设备上检测到为 PUA 的项目。 *我们建议保持 PUA 保护启用状态。*<br/>- **审核模式**，对检测为 PUA 的项目不执行任何操作 <br/>- **已禁用**，它不检测可能是 PUA 的项目或对项目采取操作 |
| **扫描**   |  |
| **计划扫描类型** | 请考虑在设备上运行每周防病毒扫描。 可以从以下扫描类型选项中进行选择： <br/>- **快速扫描** 检查注册表项和启动文件夹等位置，其中可以注册恶意软件以从设备开始。 *我们建议使用 quickscan 选项。* <br/>- **Fullscan** 检查设备上的所有文件和文件夹 <br/>- **已禁用** 意味着不会进行计划扫描。 用户仍可在其自己的设备上运行扫描。  (通常，不建议禁用计划的扫描。)  <br/><br/> [详细了解扫描类型](../defender-endpoint/schedule-antivirus-scans.md)。 |
| **运行计划扫描的星期数** | 选择要运行的常规每周防病毒扫描的一天。 |
| **运行计划扫描的一天中的时间** | 选择要运行定期安排的防病毒扫描的时间。 |
| **使用低性能** | 默认情况下，此设置已关闭。 *建议关闭此设置。* 但是，你可以打开此设置以限制计划扫描期间使用的设备内存和资源。 <br/><br/>**重要** 如果打开 **"使用低性能**"，它将为以下配置Microsoft Defender 防病毒： <br/>- 不会在 [AllowArchiveScanning (扫描存档](/windows/client-management/mdm/policy-csp-defender)) <br/>- 为扫描分配较低的 CPU 优先级 ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender))  <br/>- 如果错过完全防病毒扫描，则 [DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender) (不会运行任何)  <br/>- 如果错过快速防病毒扫描，则 [DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender) (不会运行任何)  <br/>- 将防病毒扫描期间的平均 CPU 负载因数从 [AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender) (50%)  |
| **用户体验**   |  |
| **允许用户访问 Windows 安全中心 应用** | 打开此设置以允许用户在设备上Windows 安全中心应用。 用户将无法覆盖在 Microsoft Defender for Business (预览版) 中配置的设置，但如果需要，他们将能够运行快速扫描，或查看任何检测到的威胁。 |
| **防病毒排除项** | 排除项是由扫描跳过的进程、文件或Microsoft Defender 防病毒文件夹。 *通常，不应定义排除项。* Microsoft Defender 防病毒许多基于已知操作系统行为和典型管理文件的自动排除项。<br/><br/>[详细了解排除项](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **进程排除** | 进程排除阻止特定进程打开的文件被特定进程Microsoft Defender 防病毒。 <br/><br/>[了解有关进程排除项更多信息](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **文件扩展名排除项** | 文件扩展名排除阻止特定扩展名的文件被Microsoft Defender 防病毒。<br/><br/>[详细了解文件扩展名排除项](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **文件和文件夹排除项** | 文件和文件夹排除项阻止特定文件夹中的文件被用户扫描Microsoft Defender 防病毒。 <br/><br/>[详细了解文件和文件夹排除项](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="additional-preconfigured-settings"></a>其他预配置设置

在 Defender for Business 预览版中预配置了以下 (下一代) ：

- 在 [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender) (打开可移动驱动器) 
- 每日快速扫描没有预设的时间 ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender)) 
- 在运行防病毒扫描之前检查安全智能更新 ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender)) 
- 使用 [SignatureUpdateInterval (四小时](/windows/client-management/mdm/policy-csp-defender) 进行一次安全) 

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 预览版中响应 (缓解) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)


## <a name="see-also"></a>另请参阅

- [访问 Microsoft 365 Defender 门户](mdb-get-started.md)

- [在 Microsoft Defender for Business 预览版中 (防火墙) ](mdb-custom-rules-firewall.md)

- [策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender)