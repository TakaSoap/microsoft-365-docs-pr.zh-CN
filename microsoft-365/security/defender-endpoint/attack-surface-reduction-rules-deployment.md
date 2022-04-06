---
title: ASR 规则部署先决条件
description: 提供有关在 ASR 规则中部署攻击面减少 (概述) 指南。
keywords: 攻击面减少规则部署， ASR 部署， 启用 asr 规则， 配置 ASR， 主机入侵防护系统， 保护规则， 反攻击规则， 反攻击， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则
search.product: eADQiWindows 10XVcnh
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
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 37eb6edb32c78df7ae23fe7cb52b249f81ca18b3
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682165"
---
# <a name="asr-rules-deployment-prerequisites"></a>ASR 规则部署先决条件

## <a name="before-you-begin"></a>准备工作

攻击面是组织易受网络威胁和攻击的所有位置。 组织的攻击面包括攻击者可能破坏组织设备或网络的所有位置。 减少攻击面意味着保护组织的设备和网络，从而让攻击者减少攻击方法。 配置攻击面减少 (ASR) 规则（Microsoft Defender for Endpoint 中的众多安全功能之一）可以提供帮助。

ASR 规则针对某些软件行为，例如：

- 启动尝试下载或运行文件的可执行文件和脚本
- 运行混淆的或可疑的脚本
- 应用在正常日常工作期间通常不会发生的行为

通过减少不同的攻击面，你可以首先帮助防止攻击发生。

在初始准备过程中，了解将放置的系统的功能至关重要。 了解这些功能将帮助您确定哪些 ASR 规则对保护组织最为重要。 此外，在准备 ASR 部署时还必须参与几个先决条件。

>[!IMPORTANT]
>本指南提供了图像和示例，可帮助你确定如何配置 ASR 规则;这些图像和示例可能无法反映适用于您的环境的最佳配置选项。

在启动之前，请查看 [攻击面](overview-attack-surface-reduction.md)减少概述和攻击面减少规则 [- 第 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) 部分，了解基础信息。 若要了解覆盖范围和潜在影响，请熟悉当前的 ASR 规则集;请参阅 [攻击面减少规则参考](attack-surface-reduction-rules-reference.md)。

ASR 规则只是 Microsoft Defender for Endpoint 中攻击面减少功能的一项功能。 本文档将详细介绍如何有效地部署 ASR 规则，以阻止高级威胁，如人为操作的勒索软件和其他威胁。  

### <a name="rules-by-category"></a>按类别分类的规则

如使用攻击面减少 [规则](attack-surface-reduction.md)防止恶意软件感染所述，MDE 中有多个攻击面减少规则，你可以启用这些规则来保护你的组织。 以下是按类别细分的规则：

<br/>

| 多态威胁 | 横向移动&凭据盗窃 | 生产力应用规则 |  电子邮件规则 | 脚本规则 | 杂项规则 |
|:---|:---|:---|:---|:---|:---|
| 阻止可执行文件运行，除非它们满足 (1000 台计算机) 、年龄 (24 小时) 或受信任的列表条件 | 阻止源自 PSExec 和 WMI 命令的进程创建 | 阻止Office创建可执行内容 | 阻止来自电子邮件客户端和 Webmail 的可执行内容 | 阻止混淆的 JS/VBS/PS/宏代码 | 阻止滥用被攻击的易受攻击的已签名驱动程序 <sup>[[1](#fn1)]<sup></sup>  |
| 阻止从 USB 运行的不受信任的和未签名的进程 | 阻止从本地安全Windows (lsass.exe <sup>) [[2](#fn1)]<sup></sup>   | 阻止Office创建子进程 |  仅Office通信应用程序创建子进程 | 阻止 JS/VBS 启动下载的可执行内容 | |
| 使用高级防护抵御勒索软件 | 通过 WMI 事件订阅阻止持久性 | 阻止Office将代码注入其他进程 | 阻止Office通信应用创建子进程 | | |
| | | 阻止 Adobe Reader 创建子进程 | | | |

 (<a id="fn1">1</a>) MEM 终结点安全中目前未提供阻止滥用被攻击的易受攻击的已签名驱动程序。 可以使用 [MEM OMA-URI 配置此规则](enable-attack-surface-reduction.md#mem)。

 (<a id="fn1">2</a>) 某些 ASR 规则会生成大量干扰，但不会阻止功能。 例如，如果你要更新 Chrome;Chrome 将访问lsass.exe;密码存储在设备的 lsass 中。 但是，Chrome 不应访问本地设备lsass.exe。 如果启用规则以阻止对 lsass 的访问，它将生成大量事件。 这些事件是很好的事件，因为软件更新过程不应访问lsass.exe。 启用此规则将阻止 Chrome 更新访问 lsas，但不会阻止 Chrome 更新;对于对应用程序进行不必要的调用的其他应用程序也是如此lsass.exe。 阻止 _访问 lsass_ 规则将阻止对 lsass 的不必要调用，但不阻止应用程序运行。

### <a name="infrastructure-requirements"></a>基础结构要求

虽然实现 ASR 规则的多种方法都可行，但本指南基于由以下各项组成的基础结构：

- Azure Active Directory
- Microsoft Endpoint Management (MEM) 
- Windows 10和 Windows 11 设备
- 适用于终结点 E5 或 Windows E5 的 Microsoft Defender 许可证

若要充分利用 ASR 规则和报告，我们建议使用 Microsoft 365 Defender E5 或 Windows E5 许可证和 A5。 了解更多信息 [：Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)。

>[!Note]
>有多种方法可配置 ASR 规则。 可以使用以下方法配置 ASR 规则：Microsoft Endpoint Manager (MEM) 、PowerShell、组策略、Microsoft System Center Configuration Manager (SCCM) 、MEM OMA-URI。
>如果你使用的基础结构配置与上面 (基础结构要求中列出的基础结构配置不同，你可以在此处了解有关使用其他配置部署攻击面减少规则) ：启用[攻击](enable-attack-surface-reduction.md)面减少规则。  

### <a name="asr-rules-dependencies"></a>ASR 规则依赖项

Microsoft Defender 防病毒必须启用并配置为主要的防病毒解决方案，并且必须具有以下模式：

- 主防病毒/反恶意软件解决方案  
- 状态：活动模式

Microsoft Defender 防病毒不得在下列任一模式下：

- 被动
- 在阻止模式下使用终结点检测和响应 (EDR) 被动模式
- 有限定期扫描 (LPS) 
- 关闭

请参阅：[云提供的保护和Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)。

### <a name="cloud-protection-maps-must-be-enabled"></a>必须启用云 (MAPS) 

Microsoft Defender 防病毒 Microsoft 云服务无缝工作。 这些云保护服务（也称为 Microsoft 高级保护服务 (MAPS) ）增强了标准实时保护，从而可以提供最佳防病毒防护。 云保护对于防止恶意软件的攻击和 ASR 规则的关键组件至关重要。
[在云中打开云保护Microsoft Defender 防病毒](enable-cloud-protection-microsoft-defender-antivirus.md)。

### <a name="microsoft-defender-antivirus-components-must-be-current-versions"></a>Microsoft Defender 防病毒组件必须是当前版本

以下Microsoft Defender 防病毒组件版本必须不超过两个比当前可用版本大的版本：

- **Microsoft Defender 防病毒平台更新版本** - Microsoft Defender 防病毒平台每月更新一次。
- **Microsoft Defender 防病毒引擎版本** - Microsoft Defender 防病毒引擎每月更新一次。
- **Microsoft Defender 防病毒安全** 智能 - Microsoft 持续更新 Microsoft Defender 安全 (，也称为定义和签名) ，以解决最新威胁，并优化检测逻辑。

保持Microsoft Defender 防病毒版本有助于减少 ASR 规则误报结果，并改进Microsoft Defender 防病毒检测功能。 有关当前版本以及如何更新不同组件的详细信息Microsoft Defender 防病毒请访问Microsoft Defender 防病毒[支持](manage-updates-baselines-microsoft-defender-antivirus.md)。

### <a name="caveat"></a>警告

如果未经签名的内部开发的应用程序和脚本使用率较高，某些规则将不起作用。 如果不强制执行代码签名，则更难部署 ASR 规则。

## <a name="asr-rules-deployment-steps"></a>ASR 规则部署步骤

与任何可能会影响业务线操作的新、大规模实施一样，在规划和实施时一定有条理。 由于 ASR 规则在阻止恶意软件方面具有强大的功能，因此需要仔细规划和部署这些规则，以确保它们最适合您独特的客户工作流。 若要在环境中工作，您需要仔细规划、测试、实施和操作 ASR 规则。  

> [!div class="mx-imgBorder"]
> ![ASR 规则部署阶段](images/asr-rules-deployment-phases.png)

>[!Note]
>对于使用非 Microsoft HIPS 并且正在过渡到 Microsoft Defender for Endpoint 攻击面减少规则的客户：Microsoft 建议客户在从审核模式转移到阻止模式之前，并行运行其 HIPS 解决方案及其 ASR 规则部署。 请记住，您必须联系第三方防病毒供应商，获得排除建议。  

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[第 1 阶段：规划](attack-surface-reduction-rules-deployment-plan.md)

[第 2 截断：测试](attack-surface-reduction-rules-deployment-test.md)

[第 3 阶段：实施](attack-surface-reduction-rules-deployment-implement.md)

[第 4 阶段：投入生产](attack-surface-reduction-rules-deployment-operationalize.md)

## <a name="reference"></a>参考

### <a name="blogs"></a>博客

[伪造攻击面减少规则 - 第 1 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[伪造攻击面减少规则 - 第 2 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[伪造攻击面减少规则 - 第 3 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[伪造攻击面减少规则 - 第 4 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-collection"></a>ASR 集合

[减少攻击面概述](overview-attack-surface-reduction.md)

[使用攻击面减少规则来避免感染恶意软件](attack-surface-reduction.md)

[启用攻击面减少规则](enable-attack-surface-reduction.md)

[攻击面减少规则参考](attack-surface-reduction-rules-reference.md)

[关于攻击面减少的常见问题解答](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)

[云传递保护和 Microsoft Defender 防病毒软件](cloud-protection-microsoft-defender-antivirus.md)

[在云中打开云保护Microsoft Defender 防病毒](enable-cloud-protection-microsoft-defender-antivirus.md)

[根据扩展名、名称或位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Microsoft Defender 防病毒平台支持](manage-updates-baselines-microsoft-defender-antivirus.md)

[管理中心中的Microsoft 365 应用版概述](/deployoffice/admincenter/inventory)

[为部署环境创建Windows](/windows/deployment/update/create-deployment-plan)

[在 Intune 中为分布式 IT 使用基于角色 (RBAC) 和范围标记](/mem/intune/fundamentals/scope-tags)

[在 Microsoft Intune 中分配设备配置文件](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>管理网站

[Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)

[减少攻击面](https://security.microsoft.com/asr?viewid=detections)

[ASR 规则 配置](https://security.microsoft.com/asr?viewid=configuration)

[ASR 规则排除项](https://security.microsoft.com/asr?viewid=exclusions)
