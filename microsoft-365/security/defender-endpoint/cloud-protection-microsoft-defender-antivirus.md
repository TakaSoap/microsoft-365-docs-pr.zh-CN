---
title: 云提供的保护和 Microsoft Defender 防病毒
description: 了解云提供的保护和 Microsoft Defender 防病毒
keywords: Microsoft Defender 防病毒， 下一代技术， 下一代 av， 机器学习， 反恶意软件， 安全性， Defender， 云， 云保护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: f69c66652d86977e5731a61014d5d37377779efd
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689961"
---
# <a name="use-next-generation-technologies-in-microsoft-defender-antivirus-through-cloud-delivered-protection"></a>通过云保护使用 Microsoft Defender 防病毒中的下一代技术

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防病毒

Microsoft Defender 防病毒中的 Microsoft 下一代技术可提供近乎即时的自动化保护，以抵御新出现的威胁。 为动态标识新威胁，这些技术可用于 Microsoft Intelligent Security Graph 中的大型互连数据集和由高级机器学习模型驱动的强大的人工智能 (AI) 系统。  

Microsoft Defender 防病毒使用多个检测和防护技术提供准确、实时和智能的保护。 了解 Microsoft Defender for Endpoint 下一代保护[的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。
![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)  

为了利用这些下一代技术的优势和速度，Microsoft Defender 防病毒可与 Microsoft 云服务无缝协作。 这些云保护服务（也称为 Microsoft 高级保护服务 (MAPS) ）增强了标准实时保护，从而提供了最好的防病毒防护。 

>[!NOTE]
>Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。 尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护，而是使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。

利用云提供的保护，下一代技术可快速识别新威胁，有时甚至在单个计算机受到感染之前。 观看以下有关 Microsoft AI 和 Microsoft Defender 防病毒操作的视频： 
 
<iframe 
src="https://www.microsoft.com/videoplayer/embed/RE1Yu4B" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

若要了解下一代技术如何缩短通过云的保护传递时间，请观看以下视频： 
 
<iframe 
src="https://videoplayercdn.osi.office.net/embed/c2f20f59-ca56-4a7b-ba23-44c60bc62c59" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

阅读以下博客文章，了解涉及云保护和 Microsoft AI 的详细保护情景： 

- [为什么 Microsoft Defender 防病毒在企业中部署最多](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [行为监视与机器学习相结合会损坏大量 Dofoil 硬币挖掘活动](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [人工智能如何阻止 Emotet 爆发](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [触发坏的障碍：Microsoft Defender 防病毒和分层机器学习防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender 防病毒云保护服务：针对从来未检测到的恶意软件的高级实时防御](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="get-cloud-delivered-protection"></a>获取云保护 

云保护默认启用。 但是，如果已作为以前的组织策略的一部分禁用，可能需要重新启用它。

运行 Windows 10 E5 的组织还可以利用紧急动态智能更新，这些更新可提供对新兴威胁的近实时保护。 当你打开云提供的保护时，恶意软件问题的修复可以在数分钟内通过云提供，而不是等待下一次更新。

>[!TIP]
>还可以访问 Testground Windows Defender，demo.wd.microsoft.com 以确认功能[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)是否正常工作并查看其工作方式。

下表介绍了最新版本的 Windows 和 Configuration Manager 之间的云保护差异。

|操作系统版本或服务应用程序 |云保护服务标签  |报告级别 (MAPS 成员资格级别)   |云阻止超时时段  |
|---------|---------|---------|---------|
|Windows 8.1 (组策略)      |Microsoft 高级保护服务   |基本、高级   |否         |
|Windows 10 版本 1607 (组策略)   |Microsoft 高级保护服务      |高级         |否         |
|Windows 10 版本 1703 或 (组策略)       |基于云的保护      |高级         |可配置         |
|System Center 2012 配置管理器  |      不适用         |取决于 Windows 版本         |无法配置 |
|Microsoft Endpoint Manager (Current Branch)          |云保护服务         |取决于 Windows 版本          |可配置         |
|Microsoft Intune     |Microsoft 高级保护服务         |取决于 Windows 版本         |可配置         |

还可以配置 [Microsoft Defender 防病毒，以根据](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)云服务中的报告自动接收新的保护更新。


## <a name="tasks"></a>任务

- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。 可以使用 Microsoft Endpoint Configuration Manager、组策略、Microsoft Intune 和 PowerShell cmdlet 启用云保护。

- [指定云提供的保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)。 可以使用组策略和 Microsoft Endpoint Configuration Manager 指定云提供的保护级别。 保护级别将影响与云共享的信息量以及阻止新文件的级别。

- [配置并验证 Microsoft Defender 防病毒 的网络连接](configure-network-connections-microsoft-defender-antivirus.md)。 网络和终结点必须能够连接到某些 Microsoft URL，云提供的保护才能有效工作。 本文列出了防火墙或网络筛选规则应允许的 URL，以及用于确认网络在云提供的保护中正确注册的说明。

- [配置"首次看到时阻止"功能](configure-block-at-first-sight-microsoft-defender-antivirus.md)。 "首次看到时阻止"功能可以在数秒钟内阻止新恶意软件，而无需等待数小时即可获得传统安全智能。 可以使用 Microsoft Endpoint Manager 和组策略启用和配置它。

- [配置云阻止超时时段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 Microsoft Defender 防病毒可以在查询云提供的保护服务时阻止可疑文件运行。 你可以配置阻止文件与 Microsoft Endpoint Manager 和组策略一起运行的时间。