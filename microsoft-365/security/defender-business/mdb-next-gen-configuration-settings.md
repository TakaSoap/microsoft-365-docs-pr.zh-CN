---
title: 了解Microsoft Defender 商业版中的下一代保护配置设置
description: 了解Microsoft Defender 商业版中下一代保护的配置设置
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: a39a0a55592ba8f76403f9e8d9aaf7416cb35228
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714232"
---
# <a name="understand-next-generation-configuration-settings-in-microsoft-defender-for-business"></a>了解Microsoft Defender 商业版中的下一代配置设置

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

Defender for Business 中的下一代保护包括强大的防病毒和防恶意软件保护。 默认策略旨在保护设备和用户，而不会妨碍工作效率;但是，还可以根据业务需求自定义策略。 而且，如果使用的是Microsoft Endpoint Manager，则可以使用它来管理安全策略。

**本文介绍**：

- [下一代保护设置和选项](#next-generation-protection-settings-and-options)

- [Defender for Business 中的其他预配置设置](#other-preconfigured-settings-in-defender-for-business) 

- [Defender for Business 默认设置和Microsoft Endpoint Manager](#defender-for-business-default-settings-and-microsoft-endpoint-manager)

## <a name="next-generation-protection-settings-and-options"></a>下一代保护设置和选项

下表列出了设置和选项：<br/><br/>

| 设置 | 说明 |
|:---|:---|
| **实时保护**  |  |
| **启用实时保护** | 默认启用的实时保护可定位和阻止恶意软件在设备上运行。 *建议启用实时保护。*<br/><br/>启用实时保护后，它会配置以下设置：<br/>- 在 [AllowBehaviorMonitoring](/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) (启用行为监视) <br/>- 将扫描所有下载的文件和附件 ([AllowIOAVProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection)) <br/>- 在 Microsoft 浏览器中使用的脚本将扫描 ([AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning))    |
| **首次看到时阻止** | 默认情况下，在检测后几秒内阻止第一次看到时阻止恶意软件，增加 (秒) 允许提交示例文件进行分析的时间，并将检测级别设置为"高"。 *建议在首次看到时保持阻止打开。*<br/><br/>当首次看到阻止时，它会为Microsoft Defender 防病毒配置以下设置： <br/>- 阻止和扫描可疑文件设置为高级阻止级别 ([CloudBlockLevel](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)) <br/>- 要阻止和检查的文件的秒数设置为 50 秒 ([CloudExtendedTimeout](/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout))  <br/><br/>**重要** 提示：如果第一次看到时阻止被关闭，则会影响`CloudBlockLevel`和`CloudExtendedTimeout`Microsoft Defender 防病毒。  |
| **启用网络保护功能** | 启用后，网络保护有助于防范网络钓鱼诈骗、攻击托管网站和 Internet 上的恶意内容。 它还阻止用户关闭网络保护。<br/><br/>网络保护可以设置为以下模式之一：<br/>- 此设置 (**阻止模式** 是默认) ，这会阻止用户访问被视为不安全的站点。 *建议将网络保护设置为"阻止"模式。*<br/>- **审核模式**，允许用户访问可能不安全的站点，并跟踪与此类网站的网络活动 <br/>- **禁用模式**，该模式下界阻止用户访问可能不安全的网站，也无法跟踪与此类网站的网络活动 |
| **修复**  |  |
| **对可能不需要的应用 (PUA) 采取的操作** | PUA 可以包括广告软件、捆绑用于安装其他未签名软件的软件，以及试图规避安全功能的规避软件。 虽然 PUA 不一定是病毒、恶意软件或其他类型的威胁，但 PUA 可能会影响设备性能。<br/><br/>PUA 保护阻止检测为 PUA 的项。 可以将 PUA 保护设置为以下设置之一： <br/>- **启用** (此设置是默认) ，它阻止在设备上检测到的作为 PUA 的项目。 *建议保持启用 PUA 保护。*<br/>- **审核模式**，不会对检测为 PUA 的项执行任何操作 <br/>- **已禁** 用，不会检测或对可能是 PUA 的项采取措施 |
| **扫描**   |  |
| **计划扫描类型** | 请考虑在设备上运行每周防病毒扫描。 可以从以下扫描类型选项中进行选择： <br/>- **快速扫描检查** 位置，例如注册表项和启动文件夹，其中恶意软件可以注册为以设备开头。 *建议使用 quickscan 选项。* <br/>- **Fullscan 检查** 设备上的所有文件和文件夹 <br/>- **禁用** 意味着不会进行计划的扫描。 用户仍然可以在其自己的设备上运行扫描。  (一般情况下，我们不建议禁用计划的扫描。)  <br/><br/> [详细了解扫描类型](../defender-endpoint/schedule-antivirus-scans.md)。 |
| **运行计划扫描的星期几** | 为要运行的定期每周防病毒扫描选择一天。 |
| **运行计划扫描的一天中时间** | 选择运行定期计划的防病毒扫描以运行的时间。 |
| **使用低性能** | 默认情况下，此设置处于关闭状态。 *建议关闭此设置。* 但是，可以启用此设置以限制在计划扫描期间使用的设备内存和资源。 <br/><br/>**重要** 如果打开 **"使用低性能**"，它会为Microsoft Defender 防病毒配置以下设置： <br/>- 存档文件不会扫描 ([AllowArchiveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning)) <br/>- 为扫描分配低 CPU 优先级 ([EnableLowCPUPriority](/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority))  <br/>- 如果未完成防病毒扫描，则不会在 [DisableCatchupFullScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupfullscan) (运行任何追赶扫描)  <br/>- 如果缺少快速防病毒扫描，则不会在 [DisableCatchupQuickScan](/windows/client-management/mdm/policy-csp-defender#defender-disablecatchupquickscan) (运行任何追赶扫描)  <br/>- 将防病毒扫描期间的平均 CPU 负载因子从 50% 降低到 20%， ([AvgCPULoadFactor](/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor))  |
| **用户体验**   |  |
| **允许用户访问Windows 安全中心应用** | 打开此设置，使用户能够在其设备上打开Windows 安全中心应用。 用户将无法替代你在Microsoft Defender 商业版中配置的设置，但如果需要，他们将能够运行快速扫描，或查看任何检测到的威胁。 |
| **防病毒排除项** | 排除项是通过Microsoft Defender 防病毒扫描跳过的进程、文件或文件夹。 *一般情况下，不应定义排除项。* Microsoft Defender 防病毒包括许多基于已知操作系统行为和典型管理文件的自动排除项。<br/><br/>[详细了解排除项](../defender-endpoint/configure-exclusions-microsoft-defender-antivirus.md) |
| **进程排除** | 进程排除可防止由特定进程打开的文件被Microsoft Defender 防病毒扫描。 <br/><br/>[详细了解进程排除项](../defender-endpoint/configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) |
| **文件扩展名排除项** | 文件扩展名排除项可防止Microsoft Defender 防病毒扫描具有特定扩展名的文件。<br/><br/>[详细了解文件扩展名排除项](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |
| **文件和文件夹排除项** | 文件和文件夹排除项会阻止特定文件夹中的文件被Microsoft Defender 防病毒扫描。 <br/><br/>[详细了解文件和文件夹排除项](../defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus.md) |

## <a name="other-preconfigured-settings-in-defender-for-business"></a>Defender for Business 中的其他预配置设置

Defender for Business 中预配置了以下安全设置：

- [在 AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) (启用可移动驱动器扫描) 

- 每日快速扫描没有预设时间 ([ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)) 

- 在防病毒扫描 ([CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan)) 运行之前检查安全智能更新

-  ([SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval)) 每四小时进行一次安全智能检查

## <a name="defender-for-business-default-settings-and-microsoft-endpoint-manager"></a>Defender for Business 默认设置和Microsoft Endpoint Manager

下表介绍了为 Defender for Business 预配置的设置，以及这些设置如何与在Microsoft Endpoint Manager (或Microsoft Intune) 中看到的内容相对应。 如果 [在 Defender for Business](mdb-simplified-configuration.md) (预览) 中使用简化的配置过程，则无需编辑这些设置。
<br/><br/>

| 设置  | 说明  |
|---------|---------|
| [云保护](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)     | 云保护有时称为云传递的保护或 Microsoft 高级保护服务 (MAPS) ，云保护可与Microsoft Defender 防病毒和 Microsoft 云配合使用来识别新威胁，有时甚至在单个设备受到影响之前。 默认情况下， [AllowCloudProtection](/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) 处于打开状态。 <br/><br/>[详细了解云保护](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md)。         |
| [监视传入和传出文件](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)     | 为了监视传入和传出文件， [RealTimeScanDirection](/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection) 设置为监视所有文件。         |
| [扫描网络文件](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) | 默认情况下，不启用 [AllowScanningNetworkFiles](/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) ，并且不会扫描网络文件。 |
| [扫描电子邮件](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) | 默认情况下，不启用 [AllowEmailScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) ，并且不会扫描电子邮件。 |
| [ (0-90) 保留隔离恶意软件的天数](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) | 默认情况下， [DaysToRetainCleanedMalware](/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) 此设置设置为零 (0) 天。 Artifacts隔离区不会自动删除。  |
| [提交示例同意](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) | 默认情况下， [SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) 设置为自动发送安全示例。 安全示例的示例包括`.bat``.scr``.dll``.exe`不包含个人身份信息 (PII) 的文件。 如果文件确实包含 PII，则用户将收到一个请求，以允许继续提交示例。<br/><br/>[详细了解云保护和示例提交](../defender-endpoint/cloud-protection-microsoft-antivirus-sample-submission.md) |
| [扫描可移动驱动器](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) | 默认情况下， [AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) 配置为扫描可移动驱动器，例如设备上的 USB 拇指驱动器。<br/><br/>[详细了解反恶意软件策略设置](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#list-of-antimalware-policy-settings)   |
| [每天运行快速扫描时间](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) | 默认情况下， [ScheduleQuickScanTime](/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) 设置为凌晨 2：00。<br/><br/>[详细了解扫描设置](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。   |
| [在运行扫描之前检查签名更新](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) | 默认情况下， [CheckForSignaturesBeforeRunningScan](/windows/client-management/mdm/policy-csp-defender#defender-checkforsignaturesbeforerunningscan) 配置为在运行防病毒/反恶意软件扫描之前检查安全智能更新。<br/><br/>[详细了解扫描设置](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)[和安全智能更新](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)。   |
| [) 0-24 小时 (检查安全情报更新的频率](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) | 默认情况下， [SignatureUpdateInterval](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) 配置为每四小时检查一次安全智能更新。<br/><br/>[详细了解扫描设置](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)[和安全智能更新](../defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus.md#security-intelligence-updates)。 |


## <a name="next-steps"></a>后续步骤

- [在Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解Microsoft Defender 商业版中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)


## <a name="see-also"></a>另请参阅

- [访问Microsoft 365 Defender门户](mdb-get-started.md)

- [在Microsoft Defender 商业版中管理防火墙设置](mdb-custom-rules-firewall.md)

- [策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender)
