---
title: 行为阻止和控制
description: 了解Microsoft Defender for Endpoint中的行为阻止和遏制功能
keywords: Microsoft Defender for Endpoint，在阻止模式下EDR，被动模式阻止
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
- admindeeplinkDEFENDER
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: 1f598fd1463b6e08c73d7db9ac6d1540a51d6841
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790605"
---
# <a name="behavioral-blocking-and-containment"></a>行为阻止和控制

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="overview"></a>概述

今天的威胁环境被 [无文件恶意软件](/windows/security/threat-protection/intelligence/fileless-threats) 所淹没，这些恶意软件生活在陆地上，高度多态的威胁比传统解决方案能够跟上的变异速度更快，以及人为攻击，这些攻击适应了攻击者在受攻击的设备上发现的情况。 传统的安全解决方案不足以阻止此类攻击;你需要人工智能 (AI) 和设备学习 (ML) 支持的功能，如行为阻止和遏制，包括在 [Defender for Endpoint](/windows/security) 中。

行为阻止和遏制功能可以帮助根据威胁的行为和处理树（即使威胁已开始执行）来识别和阻止威胁。 下一代保护、EDR和 Defender for Endpoint 组件和功能在行为阻止和遏制功能中协同工作。

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Microsoft Defender ATP 门户中的行为阻止和遏制" lightbox="images/mdatp-next-gen-EDR-behavblockcontain.png":::

行为阻止和遏制功能可与 Defender for Endpoint 的多个组件和功能配合使用，以立即停止攻击并防止攻击进行。

- 包括Microsoft Defender 防病毒) 在内的[下一代保护](microsoft-defender-antivirus-in-windows-10.md) (可以通过分析行为来检测威胁，并阻止已开始运行的威胁。

- [终结点检测和响应](overview-endpoint-detection-response.md) (EDR) 通过网络、设备和内核行为接收安全信号。 检测到威胁时，会创建警报。 同一类型的多个警报聚合到事件中，这样安全运营团队就可以更轻松地进行调查和响应。

- [Defender for Endpoint](overview-endpoint-detection-response.md) 除了通过EDR接收的网络、终结点和内核行为信号外，还具有各种标识、电子邮件、数据和应用的光学功能。 [Microsoft 365 Defender](../defender/microsoft-365-defender.md)的一个组件，Defender for Endpoint 进程并关联这些信号，引发检测警报，并在事件中连接相关警报。

借助这些功能，可以阻止或阻止更多的威胁，即使它们开始运行。 每当检测到可疑行为时，威胁就会被包含，警报就会被创建，威胁就会停止。

下图显示了由行为阻止和遏制功能触发的警报示例：

:::image type="content" source="images/blocked-behav-alert.png" alt-text="“警报”页，其中包含通过行为阻止和遏制发出的警报" lightbox="images/blocked-behav-alert.png":::

## <a name="components-of-behavioral-blocking-and-containment"></a>行为阻止和遏制的组件

- **客户端上策略驱动 [的攻击面减少规则](attack-surface-reduction.md)** 根据攻击面减少规则，阻止执行预定义的常见攻击行为。 尝试执行此类行为时，可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>中将其视为信息性警报。 默认情况下不会启用攻击面减少规则;在[Microsoft 365 Defender门户](/microsoft-365/security/defender/microsoft-365-defender)中配置策略。

- **[客户端行为阻止](client-behavioral-blocking.md)** 通过机器学习检测终结点上的威胁，然后自动阻止和修正。 默认情况下启用 (客户端行为阻止。) 

- **[反馈循环阻止](feedback-loop-blocking.md)** (也称为快速保护，) 通过行为智能观察到威胁检测。 威胁会停止并阻止在其他终结点上运行。 默认情况下启用 (反馈循环阻止。) 

- **[阻止和包含在阻止模式下的终结点检测和响应 (EDR)](edr-in-block-mode.md)** 恶意项目或通过违规后保护观察到的行为。 即使Microsoft Defender 防病毒不是主要防病毒解决方案，在阻止模式下EDR也有效。 默认情况下，阻止模式下的 (EDR未启用;Microsoft 365 Defender.) 

随着 Microsoft 不断改进威胁防护功能和功能，预计行为阻止和遏制领域会出现更多情况。 若要查看现在的计划和推出情况，请访问[Microsoft 365路线图](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>行为阻止和包含在操作中的示例

行为阻止和遏制功能阻止了攻击者技术，例如：

- 从 LSASS 倾销凭据
- 跨进程注入
- 进程空心化
- 用户帐户控制旁路
- 篡改防病毒 (，例如禁用或将恶意软件添加为排除) 
- 联系命令和控制 (C&C) 下载有效负载
- 硬币挖掘
- 启动记录修改
- 传递哈希攻击
- 安装根证书
- 针对各种漏洞的剥削尝试

下面是两个实际操作中的行为阻止和遏制示例。

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>示例 1：针对 100 个组织的凭据盗窃攻击

正如 [在热追难以捉摸的威胁中所述：基于 AI 的基于行为的阻止阻止其轨道上的攻击](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)，通过行为阻止和遏制功能阻止了对全球 100 个组织的凭据盗窃攻击。 包含诱惑文档的鱼叉网络钓鱼电子邮件已发送到目标组织。 如果收件人打开附件，相关远程文档能够在用户的设备上执行代码并加载 Lokibot 恶意软件，这些恶意软件窃取了凭据，泄露了被盗数据，并等待来自命令和控制服务器的进一步说明。

Defender for Endpoint 中基于行为的设备学习模型在攻击链中的两个点捕获并阻止了攻击者的技术：

- 第一个保护层检测到攻击行为。 云中的设备学习分类器正确识别了威胁，并立即指示客户端设备阻止攻击。
- 第二个保护层有助于阻止攻击通过第一层的情况，检测到进程空心，停止该进程，并删除对应的文件 (如 Lokibot) 。

当检测到攻击并停止时，警报（如“初始访问警报”）被触发并出现在[Microsoft 365 Defender门户](/microsoft-365/security/defender/microsoft-365-defender)中。

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Microsoft 365 Defender门户中的初始访问警报" lightbox="images/behavblockcontain-initialaccessalert.png":::

此示例演示云中基于行为的设备学习模型如何添加针对攻击的新保护层，即使在它们开始运行之后也是如此。

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>示例 2：NTLM 中继 - 多汁土豆恶意软件变体

如最近的博客文章《 [行为阻止和遏制：将光学转换为保护](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)》中所述，2020 年 1 月，Defender for Endpoint 检测到组织中设备上的特权提升活动。 触发了名为“使用 NTLM 中继可能的特权升级”的警报。

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="多汁土豆恶意软件的 NTLM 警报" lightbox="images/NTLMalertjuicypotato.png":::

威胁原来是恶意软件;这是一个新的，前所未见的变体，一个臭名昭著的黑客工具称为多汁土豆，这是攻击者用来获得特权升级的设备。

触发警报几分钟后，对文件进行了分析，并确认为恶意文件。 其进程已停止和阻止，如下图所示：

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="项目被阻止"  lightbox="images/Artifactblockedjuicypotato.png":::

项目被阻止几分钟后，同一设备上阻止了同一文件的多个实例，从而阻止了更多的攻击者或其他恶意软件在设备上部署。

此示例显示，使用行为阻止和遏制功能，会自动检测、包含和阻止威胁。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="next-steps"></a>后续步骤

- [详细了解 Defender for Endpoint](overview-endpoint-detection-response.md)

- [配置攻击面减少规则](attack-surface-reduction.md)

- [在块模式下启用EDR](edr-in-block-mode.md)

- [查看最近的全球威胁活动](https://www.microsoft.com/wdsi/threats)

- [获取Microsoft 365 Defender概述](../defender/microsoft-365-defender.md)
