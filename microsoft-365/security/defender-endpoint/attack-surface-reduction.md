---
title: 使用攻击面减少规则来避免感染恶意软件
description: 攻击面减少规则有助于防止攻击使用应用和脚本感染带恶意软件的设备。
keywords: 攻击面减少规则， asr， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 07159aa287de4194956d37399c73a73d5d3882e7
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61943396"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>使用攻击面减少规则来避免感染恶意软件

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>攻击面减少规则为什么很重要

组织的攻击面包括攻击者可能损害组织设备或网络的所有位置。 减少攻击面意味着保护组织的设备和网络，这使攻击者能够执行攻击的方法更少。 在 Microsoft Defender for Endpoint 中配置攻击面减少规则可以提供帮助！

攻击面减少规则针对某些软件行为，例如：

- 启动尝试下载或运行文件的可执行文件和脚本
- 运行混淆的或可疑的脚本
- 执行应用在正常日常工作期间通常不会启动的行为

此类软件行为有时在合法应用程序中可见。 但是，这些行为通常被视为有风险，因为它们通常被攻击者通过恶意软件滥用。 攻击面减少规则可以限制基于软件的风险行为，并有助于保证组织的安全。

有关配置攻击面减少规则的信息，请参阅启用 [攻击面减少规则](enable-attack-surface-reduction.md)。

## <a name="assess-rule-impact-before-deployment"></a>在部署之前评估规则影响

你可以评估攻击面减少规则可能会如何影响你的网络，在 危险和漏洞管理 中打开该规则[的安全危险和漏洞管理。](/windows/security/threat-protection/#tvm)

:::image type="content" source="images/asrrecommendation.png" alt-text="攻击面减少规则的安全重新成本。":::

在建议详细信息窗格中，检查用户影响以确定设备可接受在阻止模式下启用规则的新策略的百分比，而不会对工作效率产生不利影响。

有关 [受支持的](enable-attack-surface-reduction.md#requirements) 操作系统和其他要求信息的信息，请参阅"启用攻击面减少规则"文章中的要求。

## <a name="audit-mode-for-evaluation"></a>评估审核模式

使用 [审核模式](audit-windows-defender.md) 评估攻击面减少规则在启用后对组织的影响。 首先在审核模式下运行所有规则，以便了解它们如何影响业务线应用程序。 许多业务线应用程序都是以有限的安全问题编写，它们执行任务的方式可能类似于恶意软件。 通过监视审核数据 [并添加](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要应用程序的排除项，你可以部署攻击面减少规则，而不会降低工作效率。

## <a name="warn-mode-for-users"></a>用户警告模式

 (**新**！) 在警告模式功能之前，已启用的攻击面减少规则可以设置为审核模式或阻止模式。 使用新的警告模式，只要内容被攻击面减少规则阻止，用户就会看到一个指示内容被阻止的对话框。 该对话框还允许用户选择取消阻止内容。 然后，用户可以重试其操作，操作完成。 当用户取消阻止内容时，该内容将保持取消阻止状态 24 小时，然后阻止恢复。

警告模式可帮助组织制定攻击面减少规则，而不会阻止用户访问执行其任务所需的内容。

### <a name="requirements-for-warn-mode-to-work"></a>警告模式运行的要求

运行以下版本的警告的设备上支持警告Windows：

- [Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)或更高版本
- Windows 11
- [Windows Server 版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809)或更高版本

Microsoft Defender 防病毒在活动模式下使用实时[保护运行](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)。

此外，请确保[Microsoft Defender 防病毒反恶意软件更新](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

- 最低平台发布要求： `4.18.2008.9`
- 最低引擎发布要求： `1.1.17400.5`

有关详细信息和获取更新，请参阅 [Microsoft Defender 反恶意软件平台的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。

### <a name="cases-where-warn-mode-is-not-supported"></a>不支持警告模式的情况

当你在三个攻击面减少规则中配置警告模式时，它们不受Microsoft Endpoint Manager。  (如果使用组策略配置攻击面减少规则，则支持警告模式。) 在配置警告模式时不支持警告模式的三个规则Microsoft Endpoint Manager如下所示：

- [阻止 JavaScript 或 VBScript 使用](attack-surface-reduction-rules-reference.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content) GUID (下载的可执行 `d3e037e1-3eb8-44c8-a917-57927947596d`) 
- [通过 WMI 事件订阅和 GUID](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription) (阻止 `e6db77e5-3df2-4cf1-b95a-636979351e5b` 持久性) 
- [使用高级防护抵御勒索软件](attack-surface-reduction-rules-reference.md#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`) 

此外，在运行较早版本的 Windows 设备上不支持警告Windows。 在这种情况下，配置为在警告模式下运行的攻击面减少规则将在阻止模式下运行。

## <a name="notifications-and-alerts"></a>通知和警报

每当触发攻击面减少规则时，都会在设备上显示一条通知。 你可以使用公司的详细信息和联系人信息[自定义通知](attack-surface-reduction-rules-deployment-phase-3.md#customize-attack-surface-reduction-rules)。

此外，当触发某些攻击面减少规则时，将生成警报。

通知和生成的任何通知都可以在 Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中查看</a>。

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>高级搜寻和攻击面减少事件

可以使用高级搜寻来查看攻击面减少事件。 为了简化传入数据的数量，使用高级搜寻仅可查看每小时的唯一进程。 攻击面减少事件的时间是一小时内首次看到该事件。

例如，假设在下午 2：00 小时内在 10 台设备上发生攻击面减少事件。 假设第一个事件在 2：15 发生，最后一个事件在 2：45 发生。 借助高级搜寻，你将看到该事件的一个实例 (即使该事件实际发生在 10 台设备上) ，其时间戳将为下午 2：15。

有关高级搜寻详细信息，请参阅使用高级搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。

## <a name="attack-surface-reduction-features-across-windows-versions"></a>跨版本的攻击面Windows功能

你可以为运行以下任一版本的设备设置攻击面减少规则Windows：

- Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows Server[版本 1803 (半年](/windows-server/get-started/whats-new-in-windows-server-1803)频道) 或更高版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

  >[!NOTE]
  >Windows Server 2016和 Windows Server 2012 R2 将需要按照载入 Windows[服务器中的](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)说明载入，此功能将正常工作。 


尽管攻击面减少规则不需要使用 Windows [E5](/windows/deployment/deploy-enterprise-licenses)许可证，但如果已使用 Windows E5，则获得高级管理功能。 仅在 E5 中提供的高级Windows包括：

- Defender for Endpoint 中提供的监视、 [分析和工作流](microsoft-defender-endpoint.md)
- 中的报告和配置[Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)

这些高级功能不适用于 Windows Professional 或 Windows E3 许可证。 但是，如果你有这些许可证，可以使用事件查看器和Microsoft Defender 防病毒日志查看攻击面减少规则事件。

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>查看攻击门户中的攻击面Microsoft 365 Defender事件

Defender for Endpoint 提供事件和阻止的详细报告，作为警报调查方案的一部分。

可以使用高级搜寻查询 defender 的终结点[Microsoft 365 Defender](microsoft-defender-security-center.md)[中的终结点数据](advanced-hunting-query-language.md)。 如果你运行的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻了解攻击面减少规则可能会如何影响你的环境。

示例查询如下所示:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>查看事件查看器中的攻击Windows事件

你可以查看攻击Windows日志以查看攻击面减少规则生成的事件：

1. 下载 [评估包](https://aka.ms/mp7z2w) ，将文件 *cfa-events.xml* 到设备上易于访问的位置。

2. 在事件查看器 *中* 输入"开始"菜单，以打开Windows事件查看器。

3. 在 **"操作"** 下，**选择"导入自定义视图..."。**

4. 选择从 *cfa-events.xml* 文件的位置创建的文件。 或者，[直接复制 XML。](event-views.md)

5. 选择“**确定**”。

您可以创建一个自定义视图，该视图筛选事件以只显示下列事件，所有这些事件均与受控文件夹访问权限相关：

|事件 ID|描述|
|---|---|
|5007|更改设置时的事件|
|1121|在阻止模式下触发规则时的事件|
|1122|在审核模式下触发规则时的事件|

针对事件日志中的攻击面减少事件列出的"引擎版本"由 Defender for Endpoint 生成，而不是由操作系统生成。 Defender for Endpoint 与 Windows 10 和 Windows 11 集成，因此此功能适用于安装了 Windows 10 或 Windows 11 的所有设备。
