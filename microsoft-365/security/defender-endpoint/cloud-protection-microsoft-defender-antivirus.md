---
title: 云保护和 Microsoft Defender 防病毒软件
description: 了解云保护和Microsoft Defender 防病毒
keywords: Microsoft Defender 防病毒、下一代技术、下一代 av、机器学习、反恶意软件、安全性、defender、云、云保护
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
ms.openlocfilehash: 0cba725ed27d652366e681adccdec8dbefa68ecd
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788075"
---
# <a name="cloud-protection-and-microsoft-defender-antivirus"></a>云保护和 Microsoft Defender 防病毒软件

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒中的下一代技术提供近乎即时的自动保护，防范新威胁和新出现的威胁。 为了动态识别新威胁，下一代技术可在 Microsoft 智能安全Graph和强大的人工智能 (由高级机器学习模型驱动的 AI) 系统中处理大量互连数据。 云保护与Microsoft Defender 防病毒协同工作，提供准确、实时和智能的保护。 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="显示云保护如何与Microsoft Defender 防病毒协同工作的示意图" lightbox="images/mde-cloud-protection.png":::](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> 建议启用云保护。 若要了解详细信息，请参阅[为何应为Microsoft Defender 防病毒启用云保护](why-cloud-protection-should-be-on-mdav.md)。 

## <a name="how-cloud-protection-works"></a>云保护的工作原理

Microsoft Defender 防病毒与 Microsoft 云服务无缝配合使用。 这些云保护服务（也称为 Microsoft 高级保护服务 (MAPS) ）增强了标准的实时保护。 通过云保护，下一代技术可以快速识别新威胁，有时甚至在单个终结点被感染之前。 

以下博客文章演示了云保护的工作原理：

- [了解下一代保护Microsoft Defender for Endpoint核心的先进技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

- [为什么Microsoft Defender 防病毒是企业中部署最多的](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 

- [将行为监视与机器学习相结合会破坏大规模的硬币挖掘活动](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)

- [人工智能如何阻止“Emotet”爆发](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)

- [引爆坏兔子：Microsoft Defender 防病毒和分层机器学习防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)

- [Microsoft Defender 防病毒云保护服务：针对前所未见恶意软件的高级实时防御](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 


> [!NOTE]
> Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。 作为云服务，它不只是保护存储在云中的文件;相反，云服务使用分布式资源和机器学习以远快于传统安全智能更新的速度向终结点提供保护。

## <a name="how-to-get-cloud-protection"></a>如何获取云保护 

默认情况下启用云保护。 但是，如果已将其作为以前的组织策略的一部分禁用，则可能需要重新启用它。 若要了解详细信息，请参阅 [“启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)”。

如果订阅包含 Windows 10 E5，则可以利用紧急动态智能更新，这些更新可提供对新出现的威胁的近实时保护。 启用云保护时，恶意软件问题的修复可以在几分钟内通过云传递，而不是等待下一次更新。 请参阅[配置Microsoft Defender 防病毒，以便根据云服务的报告自动接收新的保护更新](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)。

## <a name="next-steps"></a>后续步骤

现在，你已在Microsoft Defender 防病毒中概述了云保护，下面是一些后续步骤：

1. 了解[为何应为Microsoft Defender 防病毒启用云保护](why-cloud-protection-should-be-on-mdav.md)。

2. 继续 [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)