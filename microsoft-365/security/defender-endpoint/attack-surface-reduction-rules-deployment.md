---
title: 攻击面减少 (ASR) 规则部署概述
description: 提供有关部署攻击面减少 (ASR) 规则的概述和先决条件指导。
keywords: 攻击面减少规则部署、ASR 部署、启用 asr 规则、配置 ASR、主机入侵防护系统、保护规则、防攻击规则、反攻击规则、攻击规则、感染预防规则、Pertahanan Microsoft untuk Titik Akhir、配置 ASR 规则
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
ms.openlocfilehash: 8743d13939e73e25cefd08724d9a2f8d5a7fa410
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705529"
---
# <a name="attack-surface-reduction-asr-rules-deployment-overview"></a>攻击面减少 (ASR) 规则部署概述

攻击面是组织容易受到网络威胁和攻击的所有位置。 组织的攻击面包括攻击者可能危及组织设备或网络的所有位置。 减少攻击面意味着保护组织的设备和网络，从而减少攻击者的攻击方式。 配置攻击面减少 (ASR) 规则（Pertahanan Microsoft untuk Titik Akhir中找到的许多安全功能之一）可以提供帮助。

ASR 规则针对某些软件行为，例如：

- 启动尝试下载或运行文件的可执行文件和脚本
- 运行模糊或以其他方式可疑的脚本
- 应用通常不会在正常日常工作中发生的行为

通过减少不同的攻击面，首先可以帮助防止攻击发生。

## <a name="before-you-begin"></a>准备工作

在初始准备过程中，必须了解要实施的系统的功能。 了解这些功能将有助于确定哪些 ASR 规则对于保护组织最为重要。 此外，在准备 ASR 部署时，必须注意几个先决条件。

>[!IMPORTANT]
>本指南提供图像和示例，帮助你决定如何配置 ASR 规则;这些映像和示例可能无法反映环境的最佳配置选项。

在开始之前，请查看 [攻击面减少](overview-attack-surface-reduction.md)和 [降低攻击面减少规则的概述 - 基础信息第 1 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) 。 若要了解覆盖范围和潜在影响，请熟悉当前一组 ASR 规则：请参阅 [攻击面减少规则参考](attack-surface-reduction-rules-reference.md)。  熟悉 ASR 规则集时，请记下每个规则 GUID 映射：请参阅： [ASR 规则和 GUID 矩阵](attack-surface-reduction-rules-reference.md#asr-rules-and-guids-matrix)。

ASR 规则只是Pertahanan Microsoft untuk Titik Akhir中攻击面减少功能的一个功能。 本文档将更详细地介绍如何有效部署 ASR 规则，以阻止人为操作勒索软件和其他威胁等高级威胁。  

### <a name="rules-by-category"></a>按类别排列的规则

如 [使用攻击面减少规则防止恶意软件感染](attack-surface-reduction.md)中所述，MDE 中有多个攻击面减少规则，你可以启用这些规则来保护组织。 下面是按类别细分的规则：

<br/>

| 多态威胁 | 凭据盗窃&横向移动 | 生产力应用规则 |  电子邮件规则 | 脚本规则 | 错误规则 |
|:---|:---|:---|:---|:---|:---|
| 阻止可执行文件运行，除非它们满足 (1000 台计算机) 、年龄 (24 小时) 或受信任的列表条件 | 阻止源自 PSExec 和 WMI 命令的进程创建 | 阻止Office应用创建可执行内容 | 阻止电子邮件客户端和 Webmail 中的可执行内容 | 阻止模糊化的 JS/VBS/PS/宏代码 | 阻止滥用被剥削的易受攻击的签名驱动程序 <sup>[[1](#fn1)]<sup></sup>  |
| 阻止从 USB 运行的不受信任和未签名的进程 | 阻止从Windows本地安全机构子系统中窃取凭据 (lsass.exe) <sup>[[2](#fn1)]<sup></sup>   | 阻止Office应用创建子进程 |  仅阻止Office通信应用程序创建子进程 | 阻止 JS/VBS 启动下载的可执行内容 | |
| 对勒索软件使用高级保护 | 通过 WMI 事件订阅阻止持久性 | 阻止Office应用将代码注入其他进程 | 阻止Office通信应用创建子进程 | | |
| | | 阻止 Adobe Reader 创建子进程 | | | |

 (<a id="fn1">1</a>) _阻止滥用受攻击的易受攻击的签名驱动程序_ 目前不在 MEM 终结点安全中。 可以使用 [MEM OMA-URI](enable-attack-surface-reduction.md#mem) 配置此规则。

 (<a id="fn1">2</a>) 某些 ASR 规则会产生相当大的噪音，但不会阻止功能。 例如，如果要更新 Chrome;Chrome 将访问lsass.exe;密码存储在设备上的 lsass 中。 但是，Chrome 不应访问本地设备lsass.exe。 如果启用规则来阻止对 lsass 的访问，它将生成大量事件。 这些事件是不错的事件，因为软件更新过程不应访问lsass.exe。 启用此规则将阻止 Chrome 更新访问 lsass，但不会阻止 Chrome 更新;对lsass.exe进行不必要的调用的其他应用程序也是如此。 _阻止对 lsass 规则的访问_ 将阻止对 lsass 的不必要的调用，但不会阻止应用程序运行。

### <a name="infrastructure-requirements"></a>基础结构要求

尽管可以使用多种实现 ASR 规则的方法，但本指南基于由以下内容组成的基础结构：

- Azure Active Directory
- Microsoft Endpoint Management (MEM) 
- Windows 10和Windows 11设备
- Pertahanan Microsoft untuk Titik Akhir E5 或 Windows E5 许可证

若要充分利用 ASR 规则和报告，建议使用 Microsoft 365 Defender E5 或 Windows E5 许可证和 A5。 了解详细信息：[Pertahanan Microsoft untuk Titik Akhir的最低要求](minimum-requirements.md)。

>[!Note]
>有多种方法可配置 ASR 规则。 可以使用以下方式配置 ASR 规则：Microsoft Endpoint Manager (MEM) 、PowerShell、组策略、Microsoft System Center Configuration Manager (SCCM) 、MEM OMA-URI。
>如果使用的基础结构配置不同于) 上面列出的基础 _结构要求_ (，可以在此处了解有关使用其他配置部署攻击面减少规则的详细信息： [启用攻击面减少规则](enable-attack-surface-reduction.md)。  

### <a name="asr-rules-dependencies"></a>ASR 规则依赖项

Microsoft Defender 防病毒必须启用并配置为主要防病毒解决方案，并且必须处于以下模式：

- 主要防病毒/反恶意软件解决方案  
- 状态：活动模式

Microsoft Defender 防病毒不得处于以下任何模式：

- 被动
- 在阻止模式下使用终结点检测和响应 (EDR) 的被动模式
- 有限定期扫描 (LPS) 
- 关闭

请参阅：[云提供的保护和Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)。

### <a name="cloud-protection-maps-must-be-enabled"></a>必须启用云保护 (MAPS) 

Microsoft Defender 防病毒与 Microsoft 云服务无缝配合使用。 这些云保护服务（也称为 Microsoft 高级保护服务 (MAPS) ）增强了标准的实时保护，可以说是提供最佳防病毒防护。 云保护对于防止恶意软件违规和 ASR 规则的关键组件至关重要。
[在Microsoft Defender 防病毒中启用云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md)。

### <a name="microsoft-defender-antivirus-components-must-be-current-versions"></a>Microsoft Defender 防病毒组件必须是当前版本

以下Microsoft Defender 防病毒组件版本不得超过当前可用版本的两个版本：

- **Microsoft Defender 防病毒平台更新版本** - Microsoft Defender 防病毒平台每月更新一次。
- **Microsoft Defender 防病毒引擎版本** - Microsoft Defender 防病毒引擎每月更新一次。
- **Microsoft Defender 防病毒安全智能** - Microsoft 不断更新 Microsoft Defender 安全智能 (也称为定义和签名) ，以解决最新威胁，并优化检测逻辑。

保持当前Microsoft Defender 防病毒版本有助于减少 ASR 规则误报结果，并改进Microsoft Defender 防病毒检测功能。 有关当前版本以及如何更新不同Microsoft Defender 防病毒组件的更多详细信息，请访问[Microsoft Defender 防病毒平台支持](manage-updates-baselines-microsoft-defender-antivirus.md)。

### <a name="caveat"></a>警告

如果未签名的内部开发的应用程序和脚本使用率较高，则某些规则不起作用。 如果未强制执行代码签名，则部署 ASR 规则会更加困难。

## <a name="asr-rules-deployment-steps"></a>ASR 规则部署步骤

与任何可能影响业务线运营的全新大规模实施一样，在规划和实施中必须有条不紊。 由于 ASR 规则在防止恶意软件方面具有强大的功能，因此需要仔细规划和部署这些规则，以确保这些规则最适合你独特的客户工作流。 若要在环境中工作，需要仔细规划、测试、实施和操作 ASR 规则。  

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-deployment-phases.png" alt-text="ASR 规则部署阶段" lightbox="images/asr-rules-deployment-phases.png":::

>[!Note]
>对于使用非 Microsoft HIPS 并正在转换为Pertahanan Microsoft untuk Titik Akhir攻击面减少规则的客户：Microsoft 建议客户在从审核模式转向阻止模式之前，与 ASR 规则部署并行运行 HIPS 解决方案。 请记住，必须联系第三方防病毒供应商以获取排除建议。  

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[测试攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-test.md)

[启用攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-implement.md)

[操作攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-operationalize.md)

[ASR) 规则引用 (攻击面减少](attack-surface-reduction-rules-reference.md)

## <a name="reference"></a>参考

### <a name="blogs"></a>博客

[揭开攻击面减少规则的神秘性 - 第 1 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[揭开攻击面减少规则的神秘性 - 第 2 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[揭开攻击面减少规则的神秘性 - 第 3 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[揭开攻击面减少规则的神秘性 - 第 4 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-collection"></a>ASR 集合

[减少攻击面概述](overview-attack-surface-reduction.md)

[使用攻击面减少规则来避免感染恶意软件](attack-surface-reduction.md)

[启用攻击面减少规则 - 备用配置](enable-attack-surface-reduction.md)

[攻击面减少规则参考](attack-surface-reduction-rules-reference.md)

[关于攻击面减少的常见问题解答](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)

[云传递保护和 Microsoft Defender 防病毒软件](cloud-protection-microsoft-defender-antivirus.md)

[在Microsoft Defender 防病毒中启用云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md)

[根据扩展名、名称或位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Microsoft Defender 防病毒平台支持](manage-updates-baselines-microsoft-defender-antivirus.md)

[Microsoft 365 应用版管理中心的清单概述](/deployoffice/admincenter/inventory)

[为Windows创建部署计划](/windows/deployment/update/create-deployment-plan)

[在 Intune 中使用基于角色的访问控制 (RBAC) 和分布式 IT 的作用域标记](/mem/intune/fundamentals/scope-tags)

[在 Microsoft Intune 中分配设备配置文件](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>管理站点

[Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com/#home)

[减少攻击面](https://security.microsoft.com/asr?viewid=detections)

[ASR 规则配置](https://security.microsoft.com/asr?viewid=configuration)

[ASR 规则排除项](https://security.microsoft.com/asr?viewid=exclusions)
