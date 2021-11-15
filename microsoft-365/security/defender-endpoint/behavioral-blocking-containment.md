---
title: 行为阻止和控制
description: 了解 Microsoft Defender for Endpoint 中的行为阻止和包含功能
keywords: Microsoft Defender for Endpoint，EDR阻止模式，被动模式阻止
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 99f9756170345941f38918c5f31336c1e6bc5ad7
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962779"
---
# <a name="behavioral-blocking-and-containment"></a>行为阻止和控制

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="overview"></a>概述

如今的威胁形势被无文件恶意软件所溢出[](/windows/security/threat-protection/intelligence/fileless-threats)，并位于陆地外，其变化速度比传统解决方案快的高度多态威胁，以及适应攻击者在遭到入侵的设备上发现的攻击。 传统安全解决方案不足以阻止此类攻击;你需要将人工智能 (AI) 和设备学习 (ML) 支持的功能（如行为阻止和抑制）包含在[Defender for Endpoint 中](/windows/security)。

行为阻止和抑制功能可帮助根据威胁的行为和进程树识别和停止威胁，即使威胁已开始执行。 下一代保护、EDR和适用于终结点的 Defender 组件和功能在行为阻止和抑制功能中协同工作。

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="行为阻止和抑制。":::

行为阻止和抑制功能与 Defender for Endpoint 的多个组件和功能一起协作，可立即停止攻击并阻止攻击的进行。

- [下一代 (](microsoft-defender-antivirus-in-windows-10.md)防护功能Microsoft Defender 防病毒) 分析行为来检测威胁，并停止已开始运行的威胁。

- [终结点检测和响应 (EDR) ](overview-endpoint-detection-response.md)网络、设备和内核行为接收安全信号。 检测到威胁时，将创建警报。 同一类型的多个警报聚合到事件中，这便于安全运营团队调查和响应。

- [Defender for Endpoint](overview-endpoint-detection-response.md)具有广泛的光学系统，包括标识、电子邮件、数据和应用，以及通过 EDR 接收的网络、终结点和内核行为信号。 适用于终结点[Microsoft 365 Defender](../defender/microsoft-365-defender.md)Defender 处理和关联这些信号、引发检测警报以及连接事件中的相关警报的组件。

借助这些功能，可以阻止或阻止更多威胁，即使它们开始运行。 只要检测到可疑行为，就会包含威胁，创建警报，并停止威胁。

下图显示了由行为阻止和抑制功能触发的警报示例：

:::image type="content" alt-text="通过行为阻止和封闭发出警报的示例。" source="images/blocked-behav-alert.png" lightbox="images/blocked-behav-alert.png":::

## <a name="components-of-behavioral-blocking-and-containment"></a>行为阻止和包含的组件

- **客户端上策略驱动的 [攻击面减少规则](attack-surface-reduction.md)** 根据攻击面减少规则，防止执行预定义的常见攻击行为。 当此类行为尝试执行时，可以在信息警报<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>此类行为。 默认情况下不会启用攻击面减少规则;在门户 中配置[Microsoft 365 Defender策略](microsoft-defender-security-center.md)。

- **[客户端行为阻止](client-behavioral-blocking.md)** 终结点上的威胁通过机器学习进行检测，然后自动阻止和修正。  (启用客户端行为阻止。) 

- **[反馈循环阻止](feedback-loop-blocking.md)** (也称为快速保护，) 行为智能观察到威胁检测。 威胁将停止并阻止在其他终结点上运行。  (启用反馈循环阻止。) 

- **[终结点检测和响应 (EDR)](edr-in-block-mode.md)** 阻止模式中通过泄露后保护观察到的恶意项目或行为将被阻止和包含。 EDR阻止模式运行，即使Microsoft Defender 防病毒不是主要的防病毒解决方案。  (EDR在阻止模式下启用此功能;在 Microsoft 365 Defender.) 

随着 Microsoft 继续改进威胁防护特性和功能，预期行为阻止和抑制领域会有更多的变化。 若要了解现在的计划和推出，请访问 Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>操作中的行为阻止和包含的示例

行为阻止和抑制功能阻止了攻击者技术，如下所示：

- 从 LSASS 进行凭据转储
- 跨进程注入
- 进程空心
- 用户帐户控制绕过
- 篡改防病毒程序 (例如禁用它或添加恶意软件作为排除) 
- 联系 Command and Control (C&C) 以下载有效负载
- 硬币挖掘
- 启动记录修改
- 哈希传递攻击
- 根证书的安装
- 利用各种漏洞的尝试

下面是操作中的行为阻止和包含的两个实际示例。

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>示例 1：针对 100 个组织的凭据盗窃攻击

如在热门威胁中所述： [基于 AI](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)驱动行为的阻止会停止其跟踪中的攻击，针对全球 100 个组织的凭据盗窃攻击被行为阻止和封闭功能所停止。 包含恶意文档的 Spear-phishing 电子邮件已发送到目标组织。 如果收件人打开了附件，相关远程文档可以在用户设备上执行代码并加载 Lokibot 恶意软件（该恶意软件会生成凭据、被盗数据被窃取，并等待命令和控制服务器提供进一步的说明）。

Defender for Endpoint 中基于行为的设备学习模型在攻击链中的两个点捕获并停止了攻击者的技术：

- 第一个保护层检测到攻击行为。 云中的设备学习分类器正确地将威胁标识为 并立即指示客户端设备阻止攻击。
- 第二个保护层，帮助阻止攻击通过第一层、检测到进程正在攻击、停止了该进程并删除了相应的文件 (如 Lokibot) 。

在检测到并停止攻击时，警报（如"初始访问警报）"被触发并出现在 Microsoft 365 Defender[门户中](microsoft-defender-security-center.md)。

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="网站门户中的初始Microsoft 365 Defender警报。":::

此示例演示云中基于行为的设备学习模型如何添加抵御攻击的新保护层，即使它们开始运行。

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>示例 2：NTLM 中继 - Juicy Malware 恶意软件变体

如最近的博客文章行为阻止和抑制： [将](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)光学镜头转换为保护中所述，2020 年 1 月，Defender for Endpoint 检测到组织中设备上的权限提升活动。 触发了名为"使用 NTLM 中继的可能特权提升"的警报。

:::image type="content" alt-text="Juicy Malware 恶意软件的 NTLM 警报。" source="images/NTLMalertjuicypotato.png" lightbox="images/NTLMalertjuicypotato.png":::

威胁已变成恶意软件;它是名为 Juicy 为的黑客攻击工具的一个新、之前未见的变体，攻击者使用该工具在设备上获取特权提升。

警报触发后的几分钟内，将分析文件并确认为恶意文件。 其进程已停止和阻止，如下图所示：

:::image type="content" alt-text="项目被阻止。" source="images/Artifactblockedjuicypotato.png" lightbox="images/Artifactblockedjuicypotato.png":::

项目被阻止几分钟后，同一设备的多个同一文件实例被阻止，从而阻止更多攻击者或其他恶意软件在设备上部署。

此示例显示，使用行为阻止和抑制功能，可以自动检测、包含和阻止威胁。

## <a name="next-steps"></a>后续步骤

- [详细了解适用于终结点的 Defender](overview-endpoint-detection-response.md)

- [配置攻击面减少规则](attack-surface-reduction.md)

- [启用EDR阻止模式](edr-in-block-mode.md)

- [查看最近的全球威胁活动](https://www.microsoft.com/wdsi/threats)

- [大致了解Microsoft 365 Defender](../defender/microsoft-365-defender.md)
