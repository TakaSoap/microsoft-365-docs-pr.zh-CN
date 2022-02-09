---
title: '了解 Microsoft Defender for Business 预览版中的下一代 (配置) '
description: '了解 Microsoft Defender for Business 预览版中下一代保护 (配置) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: a4fd47c04e063e049265f037568a768eb05b6cc7
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464562"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business-preview"></a>了解 Microsoft Defender for Business 预览版中的下一代 (配置) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

Defender for Business 预览版中的下一代 (保护) 强大的防病毒和反恶意软件保护。 默认策略旨在保护设备和用户，而不受工作效率的影响;但是，您也可以自定义策略以满足业务需求。 此外，如果你使用的是Microsoft Endpoint Manager，可以使用它来管理安全策略。

**本文介绍**：

- [下一代保护设置和选项](#next-generation-protection-settings-and-options)
- [Defender for Business 预览版中其他预配置 () ](#other-preconfigured-settings-in-defender-for-business) 
- [Defender for Business 默认设置和Microsoft Endpoint Manager](#defender-for-business-default-settings-and-microsoft-endpoint-manager)

## <a name="next-generation-protection-settings-and-options"></a>下一代保护设置和选项

下表列出了设置和选项：<br/><br/>

| 设置 | 说明 |
|:---|:---|
| **实时保护**  |  |
| **打开实时保护** | 默认情况下启用实时保护，可查找并阻止恶意软件在设备上运行。 *我们建议保持启用实时保护。*<br/><br/>当实时保护打开时，它将配置以下设置：<br/>- 在 [AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) (启用行为) <br/>- 在 [AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection) (扫描所有下载的文件和) <br/>- 使用 Microsoft 浏览器使用的脚本在 [AllowScriptScanning (扫描) ](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning)   |
| **首次看到时阻止** | 默认情况下启用，"首次看到时阻止"将在检测的几秒钟内阻止恶意软件，增加 (（以秒) 允许提交示例文件进行分析）的时间，并设置检测级别为"高"。 *我们建议将"首次看到时阻止"保持打开。*<br/><br/>当"首次看到时阻止"处于打开时，它会配置以下Microsoft Defender 防病毒： <br/>- 阻止和扫描可疑文件设置为 [CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel) (高级) <br/>- 要阻止和检查的文件的秒数设置为 50 秒（ ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout))  <br/><br/>**重要** 提示：如果"首次看到时阻止"处于关闭状态，`CloudBlockLevel``CloudExtendedTimeout`则会影响和Microsoft Defender 防病毒。  |
| **启用网络保护功能** | 启用后，网络保护可帮助防范网络钓鱼欺诈、攻击托管网站和 Internet 上的恶意内容。 它还可防止用户关闭网络保护。<br/><br/>网络保护可以设置为以下模式之一：<br/>- **阻止 (** 此设置是默认) ，可防止用户访问被视为不安全的网站。 *我们建议将网络保护设置为阻止模式。*<br/>- **审核** 模式，允许用户访问可能不安全的网站，并跟踪这些站点之间的网络活动 <br/>- **禁用模式**，此模式阻止用户访问可能不安全的网站，或跟踪这些网站中的网络活动 |
| **修正**  |  |
| **针对 PUA 应用中可能不需要 (的操作)** | PUA 可以包括广告软件、捆绑软件，用于安装其他未签名的软件，以及尝试破坏安全功能的恶意软件。 尽管 PUA 不一定是病毒、恶意软件或其他类型的威胁，但 PUA 可能会影响设备性能。<br/><br/>PUA 保护会阻止被检测为 PUA 的项目。 你可以将 PUA 保护设置为以下设置之一： <br/>- **已启用** (此设置是默认) ，可阻止在设备上检测到为 PUA 的项目。 *我们建议保持 PUA 保护启用状态。*<br/>- **审核模式**，对检测为 PUA 的项目不执行任何操作 <br/>- **已** 禁用，不会检测可能是 PUA 的项目或对项目采取操作 |
| **扫描**   |  |
| **计划扫描类型** | 请考虑在设备上运行每周防病毒扫描。 可以从以下扫描类型选项中进行选择： <br/>- **快速扫描** 检查注册表项和启动文件夹等位置，其中可以注册恶意软件以从设备开始。 *我们建议使用 quickscan 选项。* <br/>- **Fullscan** 检查设备上的所有文件和文件夹 <br/>- **已禁用** 意味着不会进行计划扫描。 用户仍可在其自己的设备上运行扫描。  (通常，不建议禁用计划的扫描。)  <br/><br/> [详细了解扫描类型](../defender-endpoint/schedule-antivirus-scans.md)。 |
| **运行计划扫描的星期数** | 选择要运行的常规每周防病毒扫描的一天。 |
| **运行计划扫描的一天中的时间** | 选择要运行定期安排的防病毒扫描的时间。 |
| **使用低性能** | 默认情况下，此设置已关闭。 *建议关闭此设置。* 但是，你可以打开此设置以限制计划扫描期间使用的设备内存和资源。 <br/><br/>**重要** 如果打开 **"使用低性能**"，它将配置以下Microsoft Defender 防病毒： <br/>- 不会在 [AllowArchiveScanning (扫描存档](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning)) <br/>- 为扫描分配较低的 CPU 优先级 ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority))  <br/>- 如果错过完全防病毒扫描，则 [DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan) (不会运行任何)  <br/>- 如果错过快速防病毒扫描，则 [DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan) (不会运行任何)  <br/>- 将防病毒扫描期间的平均 CPU 负载因数从 [AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor) (50%)  |
| **用户体验**   |  |
| **允许用户访问 Windows 安全中心 应用** | 打开此设置以允许用户在设备上Windows 安全中心应用。 用户将无法覆盖在 Microsoft Defender for Business (预览版) 中配置的设置，但如果需要，他们将能够运行快速扫描，或查看任何检测到的威胁。 |
| **防病毒排除项** | 排除项是由扫描跳过的进程、文件或Microsoft Defender 防病毒文件夹。 *通常，你无需定义排除项。* Microsoft Defender 防病毒许多基于已知操作系统行为和典型管理文件的自动排除项。<br/><br/>[详细了解排除项](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **进程排除** | 进程排除阻止特定进程打开的文件被特定进程Microsoft Defender 防病毒。 <br/><br/>[了解有关进程排除项更多信息](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **文件扩展名排除项** | 文件扩展名排除阻止特定扩展名的文件被Microsoft Defender 防病毒。<br/><br/>[详细了解文件扩展名排除项](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **文件和文件夹排除项** | 文件和文件夹排除阻止特定文件夹中的文件被用户扫描Microsoft Defender 防病毒。 <br/><br/>[详细了解文件和文件夹排除项](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Defender for Business 中的其他预配置设置

在 Defender for Business 预览版中预配置 (安全设置) ：

- 在 [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) (打开可移动驱动器) 
- 每日快速扫描没有预设的时间 ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)) 
- 在运行防病毒扫描之前检查安全智能 ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan)) 
- 使用 [SignatureUpdateInterval (四](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) 小时进行一次安全) 

## <a name="defender-for-business-default-settings-and-microsoft-endpoint-manager"></a>Defender for Business 默认设置和Microsoft Endpoint Manager

下表介绍了为 Defender for Business (预览版) 预先配置的设置，以及这些设置如何对应于你可能会在 Microsoft Endpoint Manager (或 Microsoft Intune) 中看到的内容。 如果你使用的是 [Defender for Business](mdb-simplified-configuration.md) 预览版中的简化配置 (预览) ，则无需编辑这些设置。
<br/><br/>

| 设置  | 说明  |
|---------|---------|
| [云保护](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | 有时也称为云保护或 Microsoft 高级保护服务 (MAPS) ，云保护与 Microsoft Defender 防病毒 和 Microsoft 云一起识别新威胁，有时甚至在单个设备受到影响之前。 默认情况下， [AllowCloudProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) 已打开。 <br/><br/>[详细了解云保护](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md)。         |
| [监视传入和传出文件](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | 要监视传入和传出文件， [将 RealTimeScanDirection](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) 设置为监视所有文件。         |
| [扫描网络文件](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | 默认情况下， [AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) 未启用，并且不会扫描网络文件。 |
| [扫描电子邮件](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | 默认情况下， [AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) 未启用，并且不会扫描电子邮件。 |
| [保留隔离 (0-90) 的天数](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | 默认情况下， [DaysToRetainCleanedMalware](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) 此设置设置为零 (0) 天。 Artifacts自动删除隔离中的邮件。  |
| [提交示例同意](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | 默认情况下， [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) 自动发送安全示例。 安全示例的示例包括 `.bat`、 `.scr`、 `.dll``.exe` 和 不包含个人身份信息的文件 (PII) 。 如果文件确实包含 PII，用户将收到允许示例提交继续的请求。<br/><br/>[详细了解云保护和示例提交](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md) |
| [扫描可移动驱动器](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | 默认情况下， [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) 配置为扫描可移动驱动器，例如设备上 U 盘驱动器。<br/><br/>[详细了解反恶意软件策略设置](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings)   |
| [运行每日快速扫描时间](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | 默认情况下， [ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) 设置为 2：00 AM。<br/><br/>[详细了解扫描设置](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。   |
| [在运行扫描之前检查签名更新](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | 默认情况下， [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) 配置为在运行防病毒/反恶意软件扫描之前检查安全智能更新。<br/><br/>[详细了解扫描设置和安全](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)[智能更新](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)。   |
| [每天 (0-24) 检查安全智能更新](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | 默认情况下， [SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) 配置为每四小时检查一次安全智能更新。<br/><br/>[详细了解扫描设置和安全](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)[智能更新](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)。 |


## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [响应和缓解 Microsoft Defender for Business 预览版 (中的威胁) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)


## <a name="see-also"></a>另请参阅

- [访问 Microsoft 365 Defender 门户](mdb-get-started.md)

- [管理 Microsoft Defender for Business 预览版 (防火墙) ](mdb-custom-rules-firewall.md)

- [策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender)
