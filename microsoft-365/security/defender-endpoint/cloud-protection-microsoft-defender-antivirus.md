---
title: 云传递保护和 Microsoft Defender 防病毒软件
description: 了解云提供的保护和Microsoft Defender 防病毒
keywords: Microsoft Defender 防病毒， 下一代技术， 下一代 av， 机器学习， 反恶意软件， 安全性， defender， 云， 云提供的保护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 06/03/2021
ms.openlocfilehash: a6e4e76f75bc5eebdf17ce4768eb13327abe630d5aff6d66033ffab43d9ad263
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854335"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>云传递保护和 Microsoft Defender 防病毒软件

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防病毒

新一代技术Microsoft Defender 防病毒提供近乎即时的自动化保护，以抵御新出现的威胁。 为了动态识别新威胁，下一代技术使用 Microsoft Intelligent Security Graph 中的大型互连数据集和由高级机器学习模型驱动的强大人工智能 (AI) 系统。 Microsoft Defender 防病毒使用多个检测和防护技术提供准确、实时和智能的保护。 

> [!TIP]
> 想要了解详细信息？ 请参阅博客文章了解 Microsoft Defender for Endpoint 下一代保护 [的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

Microsoft Defender 防病毒 Microsoft 云服务无缝工作。 这些云保护服务（也称为 Microsoft 高级保护服务 (MAPS) ）增强了标准实时保护，从而提供了最好的防病毒防护。 

> [!NOTE]
> Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。 作为云服务，它不仅仅是对存储在云中的文件的保护;相反，云服务使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。

利用云提供的保护，下一代技术可快速识别新威胁，有时甚至在单个计算机受到感染之前。 以下博客文章说明了云提供的保护的工作原理：

- [为什么Microsoft Defender 防病毒部署在企业中最多](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [行为监视与机器学习相结合会损坏大量硬币挖掘活动](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [人工智能如何阻止"Emotet"爆发](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [触发错误的障碍：Microsoft Defender 防病毒和分层机器学习防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender 防病毒云保护服务：高级实时防御功能，防止之前未检测到的恶意软件](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>如何获取云保护 

云保护默认启用。 但是，如果已作为以前的组织策略的一部分禁用，可能需要重新启用它。 若要了解更多信息，请参阅 [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。

运行 Windows 10 E5 的组织还可以利用紧急动态智能更新，这些更新可提供对新兴威胁的近实时保护。 当你打开云提供的保护时，恶意软件问题的修复可以在数分钟内通过云提供，而不是等待下一次更新。 [配置Microsoft Defender 防病毒，以根据云服务中的报告自动接收新的保护更新](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)。

> [!TIP]
> 请访问Windows Defender Testground 网站[demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)以确认该功能是否正常工作并查看其工作方式。

## <a name="next-steps"></a>后续步骤

1. [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。 可以使用云保护启用云保护Microsoft Endpoint Manager (现在包括 Microsoft Endpoint Configuration Manager 和 Microsoft Intune) 、组策略或 PowerShell cmdlet。

2. [指定云提供的保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)。 可以使用组策略或组策略指定云Microsoft Endpoint Manager级别。 保护级别将影响与云共享的信息量以及阻止新文件的级别。

3. [配置并验证 Microsoft Defender 防病毒。](configure-network-connections-microsoft-defender-antivirus.md) 网络和终结点必须能够连接到某些 Microsoft URL，云提供的保护才能有效工作。 本文列出了防火墙或网络筛选规则应允许的 URL，以及用于确认网络在云提供的保护中正确注册的说明。

4. [配置"首次看到时阻止"功能](configure-block-at-first-sight-microsoft-defender-antivirus.md)。 "首次看到时阻止"功能可以在数秒钟内阻止新恶意软件，而无需等待数小时即可获得传统安全智能。 可以使用组策略或组策略Microsoft Endpoint Manager和配置它。

5. [配置云阻止超时时段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 Microsoft Defender 防病毒查询云保护服务时阻止可疑文件运行。 可以使用组策略或组策略配置阻止文件Microsoft Endpoint Manager的时间。