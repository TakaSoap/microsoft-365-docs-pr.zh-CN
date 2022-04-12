---
title: 使用攻击面减少规则来避免感染恶意软件
description: 攻击面减少规则可帮助防止利用应用和脚本感染恶意软件的设备。
keywords: 攻击面减少规则，asr，臀部，主机入侵预防系统，保护规则，反开发，反开发，开发，感染预防，Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.technology: mde
ms.topic: article
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: a93563b3758db8346af12978440c16d91f28bed5
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788053"
---
# <a name="attack-surface-reduction-rules-overview"></a>攻击面减少规则概述

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

## <a name="why-attack-surface-reduction-rules-are-important"></a>为什么攻击面减少规则很重要

组织的攻击面包括攻击者可能危及组织设备或网络的所有位置。 减少攻击面意味着保护组织的设备和网络，使攻击者执行攻击的方法更少。 在Microsoft Defender for Endpoint中配置攻击面减少规则会有所帮助！

攻击面减少规则针对某些软件行为，例如：

- 启动尝试下载或运行文件的可执行文件和脚本
- 运行模糊或以其他方式可疑的脚本
- 执行应用通常不会在正常日常工作中启动的行为

此类软件行为有时会在合法的应用程序中出现。 但是，这些行为通常被认为是有风险的，因为它们通常通过恶意软件被攻击者滥用。 攻击面减少规则可以限制基于软件的风险行为，并有助于确保组织的安全。

有关配置攻击面减少规则的详细信息，请参阅 [“启用攻击面减少规则](enable-attack-surface-reduction.md)”。

## <a name="assess-rule-impact-before-deployment"></a>在部署前评估规则影响

可以通过在[危险和漏洞管理](/windows/security/threat-protection/#tvm)中打开该规则的安全建议来评估攻击面减少规则对网络的影响。

:::image type="content" source="images/asrrecommendation.png" alt-text="ASR 建议" lightbox="images/asrrecommendation.png":::

在“建议详细信息”窗格中，检查用户影响，以确定哪些百分比的设备可以接受在阻止模式下启用规则的新策略，而不会对工作效率产生负面影响。

有关支持的操作系统和其他要求信息的信息，请参阅“启用攻击面减少规则”一文中 [的要求](enable-attack-surface-reduction.md#requirements) 。

## <a name="audit-mode-for-evaluation"></a>评估审核模式

使用 [审核模式](audit-windows-defender.md) 评估攻击面减少规则在启用后对组织的影响。 首先在审核模式下运行所有规则，以便了解它们如何影响业务线应用程序。 许多业务线应用程序都是以有限的安全问题编写的，它们可能以类似于恶意软件的方式执行任务。 通过监视审核数据并为必要的应用程序 [添加排除项](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) ，可以部署攻击面减少规则，而不会降低工作效率。

## <a name="warn-mode-for-users"></a>用户的警告模式

 (**NEW**！) 在警告模式功能之前，启用的攻击面减少规则可以设置为审核模式或阻止模式。 使用新的警告模式时，每当内容被攻击面减少规则阻止时，用户都会看到一个对话框，指示内容被阻止。 对话框还为用户提供了一个取消阻止内容的选项。 然后，用户可以重试其操作，操作完成。 当用户取消阻止内容时，内容将保持 24 小时未阻止，然后阻止恢复。

警告模式可帮助组织制定攻击面减少规则，而不会阻止用户访问执行任务所需的内容。

### <a name="requirements-for-warn-mode-to-work"></a>警告模式运行的要求

运行以下Windows版本的设备支持警告模式：

- [Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)或更高版本
- Windows 11
- [Windows服务器版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809) 或更高版本

Microsoft Defender 防病毒必须在[活动模式](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)下使用实时保护运行。

此外，请确保已安装[Microsoft Defender 防病毒和反恶意软件更新](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

- 最低平台发布要求： `4.18.2008.9`
- 最低引擎发布要求： `1.1.17400.5`

有关详细信息并获取更新，请参阅 [Microsoft Defender 反恶意软件平台的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。

### <a name="cases-where-warn-mode-is-not-supported"></a>不支持警告模式的情况

在Microsoft Endpoint Manager中配置三个攻击面减少规则时，不支持警告模式。  (如果使用组策略配置攻击面减少规则，则支持警告模式。) 在Microsoft Endpoint Manager中配置警告模式时不支持警告模式的三个规则如下所示：

- [阻止 JavaScript 或 VBScript 启动已下载的可执行内容](attack-surface-reduction-rules-reference.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`) 
- [通过 WMI 事件订阅阻止持久性](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`) 
- [对勒索软件](attack-surface-reduction-rules-reference.md#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`) 使用高级保护

此外，运行较旧版本的Windows的设备不支持警告模式。 在这些情况下，配置为在警告模式下运行的攻击面减少规则将在阻止模式下运行。

## <a name="notifications-and-alerts"></a>通知和警报

每当触发攻击面减少规则时，设备上都会显示通知。 你可以使用公司的详细信息和联系人信息[自定义通知](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules)。

此外，当触发某些攻击面减少规则时，会生成警报。

可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>中查看生成的通知和任何警报。

有关通知和警报功能的特定详细信息，请参阅： [根据规则警报和通知详细信息](attack-surface-reduction-rules-reference.md#per-rule-alert-and-notification-details)，请参 **阅文章攻击面减少规则参考**。

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>高级搜寻和攻击面减少事件

可以使用高级搜寻来查看攻击面减少事件。 若要简化传入数据量，只需使用高级搜寻查看每小时的唯一进程。 攻击面减少事件的时间是在一小时内首次看到该事件。

例如，假设在下午 2：00 期间，10 台设备上发生了攻击面减少事件。 假设第一个事件发生在 2：15，最后一个事件发生在 2：45。 使用高级搜寻时，你将看到该事件 (的一个实例，即使它实际上发生在) 的 10 台设备上，并且其时间戳将为下午 2：15。

有关高级搜寻的详细信息，请参阅 [使用高级搜寻主动搜寻威胁](advanced-hunting-overview.md)。

## <a name="attack-surface-reduction-features-across-windows-versions"></a>跨Windows版本的攻击面减少功能

可以为运行以下任一版本和版本Windows的设备设置攻击面减少规则：

- Windows 10 专业版[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本
- Windows 10 企业版[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本
- Windows服务器版本 [1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

  >[!NOTE]
  >Windows Server 2016和Windows Server 2012 R2 需要使用载[入Windows服务器](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)中的说明加入，才能使此功能正常工作。

尽管攻击面减少规则不需要[Windows E5 许可证](/windows/deployment/deploy-enterprise-licenses)，但如果已Windows E5，则会获得高级管理功能。 高级功能（ 仅在 Windows E5 中可用） 包括：

- [Defender for Endpoint](microsoft-defender-endpoint.md) 中提供的监视、分析和工作流
- Microsoft 365 Defender中的报[表](/microsoft-365/security/defender/overview-security-center)和配置功能。

这些高级功能不适用于Windows Professional或Windows E3 许可证。 但是，如果确实拥有这些许可证，则可以使用事件查看器和Microsoft Defender 防病毒日志来查看攻击面减少规则事件。

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中查看攻击面减少事件

Defender for Endpoint 提供有关事件和块的详细报告，作为警报调查方案的一部分。

可以使用[高级搜寻](/microsoft-365/security/defender/advanced-hunting-query-language)在[Microsoft 365 Defender](microsoft-defender-endpoint.md)中查询 Defender for Endpoint 数据。 

示例查询如下所示:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>查看Windows 事件查看器中的攻击面减少事件

可以查看Windows事件日志以查看攻击面减少规则生成的事件：

1. 下载 [评估包](https://aka.ms/mp7z2w) 并将文件 *cfa-events.xml* 提取到设备上易于访问的位置。

2. 在"开始"菜单中输入单词 *事件查看器*，打开Windows 事件查看器。

3. 在 **“操作”** 下，选择 **“导入自定义视图...**”。

4. 从提取文件的位置 *选择文件cfa-events.xml* 。 或者， [直接复制 XML](event-views.md)。

5. 选择“确定”。

可以创建一个自定义视图，用于筛选事件以仅显示以下事件，所有这些事件都与受控文件夹访问相关：

|事件 ID|描述|
|---|---|
|5007|更改设置时的事件|
|1121|规则在阻止模式下触发时的事件|
|1122|在审核模式下触发规则时的事件|

事件日志中针对攻击面减少事件列出的“引擎版本”由 Defender for Endpoint 生成，而不是由操作系统生成。 Defender for Endpoint 与Windows 10和Windows 11集成，因此此功能适用于安装Windows 10或Windows 11的所有设备。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
