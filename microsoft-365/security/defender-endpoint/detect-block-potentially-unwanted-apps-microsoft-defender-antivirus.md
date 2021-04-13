---
title: 使用 Microsoft Defender 防病毒阻止可能不需要的应用程序
description: 启用可能不需要的应用程序 (PUA) 防病毒功能，以阻止不需要的软件，如广告软件。
keywords: pua， 启用， 不需要的软件， 不需要的应用， 广告软件， 浏览器工具栏， 检测， 阻止， Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690230"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>检测和阻止可能不需要的应用程序

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> PUA (可能不需要) 是一类软件，可能会导致计算机运行缓慢、显示意外广告或最差时安装其他可能意外或不需要的软件。 默认情况下，在 Windows 10 (版本 2004 和更高版本) 中，Microsoft Defender 防病毒会阻止被视为 PUA 的应用，适用于企业版 (E5) 设备。

PUA (可能不需要) 不会被视为病毒、恶意软件或其他类型的威胁，但它们可能在终结点上执行对终结点性能或使用产生不利影响的操作。 _PUA_ 还可以指由于某些类型的不良行为而信誉不佳的应用程序（由 Microsoft Defender for Endpoint 评估）。

下面是一些示例：

- **显示** 广告或促销的广告软件，包括向网页插入广告的软件。
- **提供用于** 安装未由同一实体进行数字签名的其他软件的捆绑软件。 此外，提供用于安装符合 PUA 资格的其他软件的软件。
- **主动** 尝试规避安全产品检测的恶意软件，包括存在安全产品时行为不同的软件。

> [!TIP]
> 有关我们用于标记应用程序以特别注意安全功能的条件的更多示例和讨论，请参阅 Microsoft 如何识别恶意软件和 [可能不需要的应用程序](/windows/security/threat-protection/intelligence/criteria)。

可能不需要的应用程序会增加网络受到实际恶意软件感染的风险，使恶意软件感染更难识别，或浪费 IT 资源来清理它们。 PUA 保护在 Windows 10、Windows Server 2019 和 Windows Server 2016 上受支持。

## <a name="microsoft-edge"></a>Microsoft Edge

新的 [Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)基于 Chromium，可阻止可能不需要的应用程序下载和关联的资源 URL。 此功能通过 Microsoft [Defender SmartScreen 提供](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)。

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>在基于 Chromium 的 Microsoft Edge 中启用 PUA 保护

尽管基于 Chromium 的 Microsoft Edge (版本 80.0.361.50) 中可能不需要的应用程序保护在默认情况下处于关闭状态，但可以轻松地从浏览器内打开它。

1. 选择省略号，然后选择设置 **。**
2. 选择 **"隐私、搜索和服务"。**
3. 在"**安全性"** 部分下，打开"**阻止可能不需要的应用"。**

> [!TIP]
> 如果你运行的是基于 Chromium (Chromium) ，可以通过在我们的 Microsoft [Defender SmartScreen](https://demo.smartscreen.msft.net/)演示页面上测试 PUA 保护的 URL 阻止功能来安全地浏览它。

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>使用 Microsoft Defender SmartScreen 阻止 URL

在启用 PUA 保护的基于 Chromium 的边缘中，Microsoft Defender SmartScreen 可保护你免受与 PUA 关联的 URL 的影响。

安全 [管理员可以配置](/DeployEdge/configure-microsoft-edge) Microsoft Edge 和 Microsoft Defender SmartScreen 如何协同工作，以保护用户组免受与 PUA 关联的 URL 影响。 Microsoft Defender SmartScreen [明确提供了](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 多个组策略设置，其中包括 [一个用于阻止 PUA 的组策略设置](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)。 此外，管理员可以使用组策略设置来打开或关闭 Microsoft Defender SmartScreen，将 [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 配置为一个整体。

尽管 Microsoft Defender for Endpoint 具有自己的基于由 Microsoft 管理的数据集的阻止列表，但你可以根据自己的威胁情报自定义此列表。 如果你在 Microsoft Defender [终结点门户](/microsoft-365/security/defender-endpoint/manage-indicators) 创建和管理指示器，Microsoft Defender SmartScreen 将遵守新设置。

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender 防病毒

Microsoft Defender 防病毒 (PUA) 保护功能可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA。

> [!NOTE]
> 此功能在 Windows 10、Windows Server 2019 和 Windows Server 2016 中可用。

Microsoft Defender 防病毒阻止检测到的 PUA 文件以及下载、移动、运行或安装这些文件的任何尝试。 然后，阻止的 PUA 文件移动到隔离区。 当在终结点上检测到 PUA 文件时，Microsoft Defender 防病毒会向用户 (除非通知已禁用[](configure-notifications-microsoft-defender-antivirus.md)) ，格式与其他威胁检测相同。 通知的前言以 `PUA:` 指示其内容。

通知显示在 Windows 安全中心 [应用内常用的隔离列表中](microsoft-defender-security-center-antivirus.md)。

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防病毒中配置 PUA 保护

可以使用[Microsoft Intune、Microsoft](/mem/intune/protect/device-protect)Endpoint [Configuration Manager、](/mem/configmgr/protect/deploy-use/endpoint-protection)[组](/azure/active-directory-domain-services/manage-group-policy)策略或[PowerShell cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)启用 PUA 保护。

还可以在审核模式下使用 PUA 保护来检测可能不需要的应用程序，而不会阻止它们。 检测在 Windows 事件日志中捕获。

> [!TIP]
> 请访问 Microsoft Defender for Endpoint 演示 [网站，demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) 以确认该功能是否正常工作，并查看它是否正在操作。

如果你的公司正在执行内部软件安全合规性检查，并且你要避免任何误报，则审核模式下的 PUA 保护非常有用。

#### <a name="use-intune-to-configure-pua-protection"></a>使用 Intune 配置 PUA 保护

有关详细信息 [，请参阅在 Microsoft Intune 中](/intune/device-restrictions-configure) 配置设备限制设置和 Intune 中 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 的 Microsoft Defender 防病毒设备限制设置。

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>使用 Configuration Manager 配置 PUA 保护

默认情况下，PuA 保护在 Microsoft Endpoint Manager (Current Branch) 。

请参阅 [如何创建和部署反恶意软件策略：计划](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 扫描设置，了解有关配置 Microsoft Endpoint Manager (Current Branch) 。

有关System Center 2012管理器，请参阅如何在 Configuration Manager 中为 Endpoint Protection 部署可能不需要 [的应用程序保护策略](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。

> [!NOTE]
> Microsoft Defender 防病毒阻止的 PUA 事件在 Windows 事件查看器中报告，而不是在 Microsoft Endpoint Configuration Manager 中报告。

#### <a name="use-group-policy-to-configure-pua-protection"></a>使用组策略配置 PUA 保护

1. 下载并安装 Windows [10 (.admx) 2020 年 10](https://www.microsoft.com/download/details.aspx?id=102157)月更新 (20H2) 

2. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

3. 选择要配置的组策略对象，然后选择"编辑 **"。**

4. 在组 **策略管理编辑器中**，转到计算机 **配置，** 然后选择 **管理模板**。

5. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**。

6. 双击配置 **对可能不需要的应用程序的检测**。

7. 选择 **"已启用** "以启用 PUA 保护。

8. 在 **"选项**"**中**，选择"阻止"以阻止可能不需要的应用程序，或选择"审核模式"以测试该设置在环境中的工作方式。 选择“**确定**”。

9. 像通常一样部署组策略对象。

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>使用 PowerShell cmdlet 配置 PUA 保护

##### <a name="to-enable-pua-protection"></a>启用 PUA 保护

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

如果禁用此功能，则设置此 cmdlet `Enabled` 的值以打开该功能。

##### <a name="to-set-pua-protection-to-audit-mode"></a>将 PUA 保护设置为审核模式

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

设置 `AuditMode` 可检测 PUA 而不阻止它们。

##### <a name="to-disable-pua-protection"></a>禁用 PUA 保护

我们建议保持 PUA 保护打开。 但是，您可以使用以下 cmdlet 将其关闭：

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

设置此 cmdlet 的值 `Disabled` 可关闭该功能（如果已启用）。

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/index) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

## <a name="view-pua-events"></a>查看 PUA 事件

PUA 事件在 Windows 事件查看器中报告，但不在 Microsoft Endpoint Manager 或 Intune 中报告。 您还可以使用 `Get-MpThreat` cmdlet 查看 Microsoft Defender 防病毒处理的威胁。 下面是一个示例：

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

你可以打开电子邮件通知以接收有关 PUA 检测的邮件。

有关查看 Microsoft Defender 防病毒事件的详细信息，请参阅事件 [ID](troubleshoot-microsoft-defender-antivirus.md) 疑难解答。 PUA 事件记录在事件 ID **1160 下**。

## <a name="excluding-files"></a>排除文件

有时 PUA 保护错误地阻止了文件，或者需要 PUA 的功能才能完成任务。 在这些情况下，可以将文件添加到排除列表。

有关详细信息，请参阅配置和 [验证基于文件扩展名和文件夹位置的排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>另请参阅

- [下一代保护](microsoft-defender-antivirus-in-windows-10.md)
- [配置行为、启发式和实时保护](configure-protection-features-microsoft-defender-antivirus.md)