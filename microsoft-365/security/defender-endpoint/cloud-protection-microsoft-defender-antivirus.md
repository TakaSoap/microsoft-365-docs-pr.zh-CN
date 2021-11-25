---
title: 云保护和 Microsoft Defender 防病毒软件
description: 了解云保护和Microsoft Defender 防病毒
keywords: Microsoft Defender 防病毒， 下一代技术， 下一代 av， 机器学习， 反恶意软件， 安全性， defender， 云， 云保护
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 013b189dca95fc63dc8d189d020fcf3f7727cf82
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171685"
---
# <a name="cloud-protection-and-microsoft-defender-antivirus"></a>云保护和 Microsoft Defender 防病毒软件

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

新一代技术Microsoft Defender 防病毒提供近乎即时的自动化保护，以抵御新出现的威胁。 为了动态识别新威胁，下一代技术使用 Microsoft Intelligent Security Graph 中的大型互连数据集和由高级机器学习模型驱动的强大人工智能 (AI) 系统。 云保护与Microsoft Defender 防病毒一起提供准确、实时和智能的保护。 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="显示云保护如何与云解决方案协同工作Microsoft Defender 防病毒":::](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> 我们建议保持启用云保护。 若要了解更多信息，请参阅[为什么应为](why-cloud-protection-should-be-on-mdav.md)用户启用云Microsoft Defender 防病毒。 

## <a name="how-cloud-protection-works"></a>云保护的工作原理

Microsoft Defender 防病毒 Microsoft 云服务无缝工作。 这些云保护服务（也称为 Microsoft 高级保护服务 (MAPS) ）增强了标准实时保护。 借助云保护，下一代技术可快速识别新威胁，有时甚至在单个终结点受到感染之前。 

以下博客文章说明了云保护的工作原理：

- [了解 Microsoft Defender for Endpoint 下一代保护的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

- [为什么Microsoft Defender 防病毒部署在企业中最多](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 

- [行为监视与机器学习相结合会损坏大量硬币挖掘活动](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)

- [人工智能如何阻止"Emotet"爆发](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)

- [触发错误的障碍：Microsoft Defender 防病毒和分层机器学习防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)

- [Microsoft Defender 防病毒云保护服务：高级实时防御功能，防止之前未检测到的恶意软件](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 


> [!NOTE]
> 云Microsoft Defender 防病毒是一种向网络和终结点提供更新保护的机制。 作为云服务，它不仅仅是对存储在云中的文件的保护;相反，云服务使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。

## <a name="how-to-get-cloud-protection"></a>如何获取云保护 

云保护默认启用。 但是，如果已作为以前的组织策略的一部分禁用，可能需要重新启用它。 若要了解更多信息，请参阅 [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。

如果你的订阅包括Windows 10 E5，你可以利用紧急动态智能更新，这些更新可提供对新兴威胁的近实时保护。 当你打开云保护时，恶意软件问题的修复可以在数分钟内通过云提供，而不是等待下一次更新。 请参阅[Configure Microsoft Defender 防病毒 to automatically receive new protection updates based on reports from our cloud service](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)。

## <a name="next-steps"></a>后续步骤

现在，你已大致了解云保护Microsoft Defender 防病毒，下面介绍了一些下一步：

1. 请参阅[为什么应为云保护启用Microsoft Defender 防病毒。](why-cloud-protection-should-be-on-mdav.md)

2. 继续启用 [云保护](enable-cloud-protection-microsoft-defender-antivirus.md)