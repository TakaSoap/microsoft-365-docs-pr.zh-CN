---
title: 使用Microsoft Defender防病毒功能阻止可能有害的应用程序
description: 启用可能会不需要的应用程序 （PUA） 防病毒软件，以阻止不需要的软件，如 adware。
keywords: pua，启用，不需要的软件，不需要的应用，adware，浏览器工具栏，检测，阻止，Microsoft Defender 防病毒软件
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: m365-security-compliance
ms.openlocfilehash: 67f23d31f50dc20e385f36d4ee4a941db14af7ef
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790671"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>检测并阻止可能不需要的应用程序

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)
- Microsoft Defender 防病毒

**平台**
- Windows

可能不需要的应用程序 (PUA) 用来指代一类软件，它们会导致计算机运行缓慢、显示意外广告，最糟的是，它还会安装其他意外的或不需要的软件。 PUA 不是病毒、恶意软件或其他威胁，但它可能会对终结点进行一些操作，对其性能或使用产生负面的影响。 *PUA* 这个术语也可以指那些由于某些不当行为，被 Microsoft Defender for Endpoint 评估为具有较差信誉的应用程序。

下面是一些示例：

- 显示广告或促销的 **广告软件**，包括将广告插入网页的软件。
- **捆绑软件** ，用于安装不由同一实体进行数字签名的其他软件。 此外，提出安装其他软件的软件属于 PUA。
- 积极尝试逃避安全产品检测的 **规避软件**，包括在存在安全产品的情况下行为不同的软件。

> [!TIP]
> 有关更多示例和讨论我们用于标记应用程序以引起对安全功能特别关注的条件，请参阅 [Microsoft 如何识别恶意软件和可能不需要的应用程序](/windows/security/threat-protection/intelligence/criteria)。

可能不需要的应用程序会增加网络受到实际恶意软件感染的风险，使恶意软件感染更加难以识别，或浪费 IT 资源清理它们。 Windows 10、Windows 11、Windows Server 2019、Windows Server 2022 和 Windows Server 2016 支持 PUA 保护。 在 Windows 10（版本 2004 和更高版本）中，Microsoft Defender 防病毒软件会默认为企业 (E5) 设备阻止 PUA 应用。

## <a name="microsoft-edge"></a>Microsoft Edge

新的 [Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)（基于 Chromium） 会阻止潜在的不需要的应用程序下载和关联的资源 URL。 此功能通过[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)提供。

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>在基于 Chromium 的 Microsoft Edge 中启用 PUA 保护

虽然默认情况下会关闭 Microsoft Edge 中可能不需要的应用程序保护（基于 Chromium 的版本 80.0.361.50），但可在浏览器中轻松启用。

1. 在 Microsoft Edge 浏览器中，选择省略号，然后选择“**设置**”。

2. 选择 **隐私、搜索和服务**。

3. 在" **安全** 部分， **阻止可能不需要的应用**。

> [!TIP]
> 如果运行的是 Microsoft Edge（基于 Chromium），您可以通过在我们的 [Microsoft Defender SmartScreen 演示页面之一测试并测试 PUA 保护的 URL 阻止功能](https://demo.smartscreen.msft.net/)。

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>使用 Microsoft Defender SmartScreen 阻止 URL

在启用 PUA 保护的基于 Chromium 的 Microsoft Edge 中，Microsoft Defender SmartScreen 可保护用户免遭 PUA 关联的 URL 的影响。

安全管理员可 [Microsoft Edge](/DeployEdge/configure-microsoft-edge) Microsoft Defender SmartScreen 如何协同工作来保护用户组免遭 PUA 关联的 URL 的威胁。 可显式 [Microsoft Defender SmartScreen](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 多个组策略设置，包括 [PUA 策略设置的](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)。 此外，管理员可 [将 Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 配置成整体，使用组策略设置打开或关闭 Microsoft Defender SmartScreen。

虽然 Microsoft Defender for Endpoint 基于 Microsoft 托管的数据集具有自己的阻止列表，但它也可以基于自己的威胁智能自定义此列表。 若要在 Microsoft Defender for Endpoint 中“[创建和管理指示器](manage-indicators.md)”，Microsoft Defender SmartScreen 将应用新设置。

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender 防病毒和 PUA 保护

Microsoft Defender 防病毒软件中可能不需要的应用程序 (PUA) 保护功能可检测和阻止网络中终结点上的 PUA。

> [!NOTE]
> Windows 10、Windows 11、Windows Server 2019、Windows Server 2022 和 Windows Server 2016 中提供此功能。

Microsoft Defender 防病毒软件阻止检测到 PUA 文件，以及尝试下载、移动、运行或安装它们的任何尝试。 阻止的 PUA 文件随即移动到隔离区。 在终结点上检测到 PUA 文件时，Microsoft Defender 防病毒向用户发送通知（[除非已禁用通知](configure-notifications-microsoft-defender-antivirus.md) 与其他威胁检测相同的格式。 以通知的字体作为 `PUA:` 以指示其内容。

该通知显示在 Windows 安全应用 [中正常出现的隔离](microsoft-defender-security-center-antivirus.md)。

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防病毒软件中配置 PUA 保护

您可以使用[Microsoft Intune](/mem/intune/protect/device-protect)，[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection)，[组策略](/azure/active-directory-domain-services/manage-group-policy)或通过[PowerShell cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)启用PUA保护。

还可在审核模式下使用 PUA 保护检测可能不需要的应用程序，同时不阻止它们。 检测将捕获到 Windows 事件日志中。

> [!TIP]
> 请访问 microsoft Defender for Endpoint 演示网站 [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) 确认该功能是否正常工作，并查看其操作结果。

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

如果你的公司正在进行内部软件安全合规性检查，并且希望避免出现任何误报，则审核模式下的 PUA 保护十分有用。

### <a name="use-intune-to-configure-pua-protection"></a>使用 Intune 配置 PUA 保护

有关详细信息，请参阅[Microsoft Intune](/intune/device-restrictions-configure) 和 [Microsoft Defender Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) Windows 10 防病毒设备限制设置。

### <a name="use-configuration-manager-to-configure-pua-protection"></a>使用配置管理器配置 PUA 保护

在 Microsoft Endpoint Manager （Current Branch） 中默认启用 PUA 保护。

请参阅 [创建和部署反恶意软件策略的信息：计划扫描设置](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 配置 Microsoft Endpoint Manager （Current Branch） 的详细信息。

对于 System Center 2012 Configuration Manager，请参阅 [Configuration Manager 管理中心中如何部署用于终结点保护的潜在的不需要的应用程序保护](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。

> [!NOTE]
> Windows 事件查看器中报告称 Microsoft Defender 防病毒软件阻止的 PUA 事件，而不是 Microsoft Endpoint Configuration Manager 中。

### <a name="use-group-policy-to-configure-pua-protection"></a>使用组策略配置 PUA 保护

1. 下载并安装 [Windows 10 2020 年 10 月更新 （20H2） 管理模板 （.admx）](https://www.microsoft.com/download/details.aspx?id=102157)

2. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

3. 选择要配置的组策略对象，然后选择" **策略**。

4. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

5. 展开树以 **Windows 组件**\>**Microsoft Defender 防病毒**。

6. 双击配置 **中可能不需要的应用程序**。

7. 选择 **启用** 以启用 PUA 保护。

8. 在“**选项**”中，选择“**阻止**”以阻止可能不需要的应用程序，或选择“**审核模式**”以测试设置在环境中的工作方式。选择“**确定**”。

9. 如通常一样部署组策略对象。

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>使用 PowerShell cmdlet 配置 PUA 保护

#### <a name="to-enable-pua-protection"></a>启用 PUA 保护

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

如果已禁用该功能，将此 cmdlet 的值设置为 `Enabled` 将启用该功能。

#### <a name="to-set-pua-protection-to-audit-mode"></a>将 PUA 保护设置为审核模式

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

设置 `AuditMode` 可检测 PUA，且不会阻止它们。

#### <a name="to-disable-pua-protection"></a>禁用 PUA 保护

建议保持启用 PUA 保护。 但是，可以通过以下 cmdlet 将其关闭：

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

如果已启用该功能，将此 cmdlet 的值设置为 `Disabled` 将禁用该功能。

有关详细信息，请参阅[使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender for Cloud cmdlet](/powershell/module/defender/index)。

## <a name="view-pua-events-using-powershell"></a>使用 PowerShell 查看 PUA 事件

PUA 事件在 Windows 事件查看器中报告，但不在 Microsoft 终结点管理器或 Intune 中。 还可使用 `Get-MpThreat` cmdlet 查看 Microsoft Defender 防病毒软件处理的威胁。 下面是一个示例：

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>获取有关 PUA 检测的电子邮件通知

你可以打开电子邮件通知以接收有关 PUA 检测的邮件。

请参阅 [解决事件 ID](troubleshoot-microsoft-defender-antivirus.md) ，了解有关查看 Microsoft Defender 防病毒事件的详细信息。 PUA 事件记录在事件 ID **1160**。

## <a name="view-pua-events-using-advanced-hunting"></a>使用高级搜寻查看 PUA 事件

如果你正在使用 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，则可以使用高级搜寻查询来查看 PUA 事件。以下是查询示例：

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

若要了解高级搜寻的详细信息，请参阅[使用高级搜寻来主动搜寻威胁](advanced-hunting-overview.md)。

## <a name="exclude-files-from-pua-protection"></a>排除来自 PUA 保护的文件

有时文件被 PUA 保护错误阻止，或需要 PUA 的功能才能完成任务。 在这些情况下，可以将文件添加到排除列表。

有关详细信息，请参阅 [扩展名和文件夹位置配置和验证排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [设置 macOS 上 Microsoft Defender for Endpoint 的首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于 Intune 的 Microsoft Defender 防病毒软件的 macOS 防病毒程序策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [设置 Linux 上 Microsoft Defender for Endpoint 的首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置 Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [下一代保护](microsoft-defender-antivirus-in-windows-10.md)
- [配置方案、高要求和实时保护](configure-protection-features-microsoft-defender-antivirus.md)
