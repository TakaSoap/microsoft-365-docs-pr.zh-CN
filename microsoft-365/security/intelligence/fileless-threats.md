---
title: 无文件威胁
ms.reviewer: ''
description: 了解生活在陆地上的无文件威胁和恶意软件的类别
keywords: 无文件，无文件恶意软件，生活在陆地上，lolbins，amsi，行为监视，内存扫描，启动扇区保护，安全，恶意软件，Windows Defender ATP，防病毒，AV，Microsoft Defender ATP，下一代保护
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 4db82cfc20bb1e27b2ef9a75793170c451c3868a
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665329"
---
# <a name="fileless-threats"></a>无文件威胁

什么是无文件威胁？ 术语"无文件"表示威胁不会出现在文件中，例如仅存在于计算机内存中的后门。 但是，没有针对无文件恶意软件的定义。 该术语广泛使用，有时用于描述依赖文件操作的恶意软件系列。

攻击涉及 [多个功能阶段](https://attack.mitre.org/wiki/ATT&CK_Matrix) ，例如执行、持久性或信息盗窃。 攻击链的某些部分可能是无文件的，而其他部分可能以某种形式涉及文件系统。

为清楚起见，无文件威胁分为不同的类别。

![无文件恶意软件的综合关系图。](../../media/security-intelligence-images/fileless-malware.png)<br>
*图 1.无文件恶意软件的综合关系图*

无文件威胁可按其入口点进行分类，该入口点指示无文件恶意软件如何到达计算机上。 它们可以通过攻击、受攻击的硬件或通过定期执行应用程序和脚本来到达。

接下来，列出入口点的形式。 例如，攻击可以基于文件或网络数据，PCI 外围设备是一种硬件向量，脚本和可执行文件是执行向量的子类别。

最后，对感染的宿主进行分类。 例如，Flash 应用程序可能包含各种威胁，例如攻击、简单的可执行文件和来自硬件设备的恶意固件。

分类有助于划分和分类各种无文件威胁。 有些更危险，但也更难实施，而另一些则更常用，尽管 (或正是因为) 不是很先进。

从此分类中，可以根据受感染计算机上的指纹数量来收集三种主要类型的无文件威胁。

## <a name="type-i-no-file-activity-performed"></a>类型 I：未执行文件活动

完全无文件恶意软件可以视为永远不需要在磁盘上写入文件的恶意软件。 此类恶意软件首先会如何感染计算机？ 例如，目标计算机接收恶意网络数据包，这些数据包会利用 EternalBlue 漏洞。 此漏洞允许安装 DoublePulsar 后门，该后门最终仅驻留在内核内存中。 在这种情况下，没有文件或文件上写入的任何数据。

受攻击的设备可能还具有隐藏在设备固件 (（如 BIOS) 、USB 外围 (（如 BadUSB 攻击) ）或网络卡固件中的恶意代码。 所有这些示例不需要磁盘上的文件才能运行，理论上只能在内存中生存。 恶意代码会在重新启动、磁盘重新安装和 OS 重新安装后生存下来。

这种类型的感染可能特别难以检测，因为大多数防病毒产品都无法检查固件。 如果产品确实能够检查和检测恶意固件，则此级别的威胁修正仍存在重大挑战。 这种类型的无文件恶意软件需要高度复杂，并且通常取决于特定的硬件或软件配置。 这不是一个可以轻松可靠地利用的攻击向量。 虽然存在危险，但此类威胁并不常见，对大多数攻击并不实际。

## <a name="type-ii-indirect-file-activity"></a>类型 II：间接文件活动

恶意软件可以通过其他方式在计算机上实现无文件状态，而无需大量的工程工作。 此类的无文件恶意软件不会直接在文件系统上写入文件，但最终可能会间接使用文件。 例如， [使用 Poshspy 后门](https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html) 攻击者在 WMI 存储库中安装了恶意 PowerShell 命令，并将 WMI 筛选器配置为定期运行该命令。

可以通过命令行执行此类安装，而无需在文件上已有后门。 可以安装恶意软件并在理论上运行，而无需接触文件系统。 但是，WMI 存储库存储在 CIM 对象管理器管理的中央存储区域中的物理文件上，通常包含合法数据。 尽管感染链在技术上确实使用物理文件，但它被视为无文件攻击，因为 WMI 存储库是一个多用途数据容器，无法检测和删除。

## <a name="type-iii-files-required-to-operate"></a>类型 III：操作所需的文件

某些恶意软件可以有一种无文件持久性，但不能不使用文件进行操作。 此方案的一个示例是 Kovter，它在注册表中为随机文件扩展名创建 shell 打开谓词处理程序。 打开具有此类扩展名的文件将导致通过合法工具mshta.exe执行脚本。

![Kovter 注册表项的图像。](../../media/security-intelligence-images/kovter-reg-key.png)<br>
*图 2.Kovter 的注册表项*

调用打开的谓词时，将启动注册表中的关联命令，从而导致执行小型脚本。 此脚本从其他注册表项中读取数据并执行它，进而导致加载最终有效负载。 但是，若要首先触发打开的谓词，Kovter 必须删除具有上述示例中谓词 (所针对的具有相同扩展名的文件，扩展名为 .bbf5590fd) 。 它还必须设置配置为在计算机启动时打开此类文件的自动运行密钥。

Kovter 被视为无文件威胁，因为文件系统没有实际用途。 具有随机扩展名的文件包含在验证威胁是否存在时不可用的垃圾数据。 存储注册表的文件是无法检测到的容器，如果存在恶意内容，则无法将其删除。

## <a name="categorizing-fileless-threats-by-infection-host"></a>按感染主机对无文件威胁进行分类

在介绍了广泛的类别后，我们现在可以深入了解详细信息，并提供感染宿主的细目。 此综合分类涵盖通常称为无文件恶意软件的全景。 它推动我们努力研究和开发新的保护功能，以消除攻击的类，并确保恶意软件不会在军备竞赛中占上风。

### <a name="exploits"></a>利用

**基于文件** 的 (类型 III：可执行文件、Flash、Java、文档) ：初始文件可以利用操作系统、浏览器、Java 引擎、Flash 引擎等执行 shellcode 并在内存中传递有效负载。 虽然有效负载是无文件的，但初始条目向量是一个文件。

**基于网络的** (类型 I) ：利用目标计算机中的漏洞的网络通信可以在应用程序或内核上下文中实现代码执行。 例如 WannaCry，它利用 SMB 协议中以前修复的漏洞在内核内存中传递后门。

### <a name="hardware"></a>硬件

**基于设备的** (类型 I：网卡、硬盘) ：硬盘和网卡等设备需要芯片集和专用软件才能正常运行。 在设备的芯片集中驻留在和运行的软件称为固件。 虽然任务很复杂，但固件可能受到恶意软件的感染，就像 [公式间谍组织被抓到一](https://www.kaspersky.com/blog/equation-hdd-malware/7623/)样。

**基于 CPU 的** (类型 I) ：新式 CPU 很复杂，可能包括用于管理目的运行固件的子系统。 此类固件可能容易被劫持，并允许执行从 CPU 内部运行的恶意代码。 2017 年 12 月，两位研究人员报告了一个漏洞，该漏洞允许攻击者执行 [管理引擎内的代码 (ME) ](https://en.wikipedia.org/wiki/Intel_Management_Engine) 存在于 Intel 的任何新式 CPU 中。 同时，观察到攻击者组 PLATINUM 能够使用 Intel 的 [Active Management Technology (AMT) ](https://en.wikipedia.org/wiki/Intel_Active_Management_Technology) 绕过安装的操作系统执行 [不可见的网络通信](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/07/platinum-continues-to-evolve-find-ways-to-maintain-invisibility/)。 ME 和 AMT 本质上是位于 CPU 内部且在极低级别运行的自主微计算机。 由于这些技术的目的是提供远程可管理性，因此它们可以直接访问硬件，独立于操作系统，即使计算机已关闭，也可以运行。

除了在固件级别易受攻击外，CPU 还可以使用直接插入硬件线路的后门进行制造。 这种攻击在过去已经 [研究并证明是可能的](https://www.emsec.rub.de/media/crypto/veroeffentlichungen/2015/03/19/beckerStealthyExtended.pdf) 。 据报道，x86 处理器的某些模型包含一个类似于 RISC 的辅助嵌入式 CPU 核心，可以 [有效地提供后门](https://www.theregister.co.uk/2018/08/10/via_c3_x86_processor_backdoor/) ，通过该后门，常规应用程序可以获得特权执行。

**基于 USB 的** (类型 I) ：可以使用恶意固件重新编程各种 USB 设备，这些固件能够以邪恶的方式与操作系统交互。 例如， [BadUSB 技术](https://arstechnica.com/information-technology/2014/07/this-thumbdrive-hacks-computers-badusb-exploit-makes-devices-turn-evil/) 允许重新编程的 USB 摇杆充当键盘，通过击键将命令发送到计算机，或作为网络卡，可以随时重定向流量。

**基于 BIOS 的** (类型 I) ：BIOS 是在芯片集中运行的固件。 它在计算机上启用电源、初始化硬件，然后将控制权传输到启动扇区时执行。 BIOS 是一个重要组件，在低级别运行并在启动扇区之前执行。 可以使用恶意代码重新编程 BIOS 固件，就像过去使用 [Mebromi rootkit](https://www.webroot.com/blog/2011/09/13/mebromi-the-first-bios-rootkit-in-the-wild/) 一样。

**基于虚拟机监控程序的** (类型 I) ：新式 CPU 提供硬件虚拟机监控程序支持，使操作系统能够创建可靠的虚拟机。 虚拟机在封闭的模拟环境中运行，理论上不知道仿真。 接管计算机的恶意软件可能会实现小型虚拟机监控程序，以隐藏在正在运行的操作系统领域之外。 此类恶意软件过去已被理论化，最终 [观察到](http://seclists.org/fulldisclosure/2017/Jun/29)真正的虚拟机监控程序根基，尽管迄今鲜为人知。

### <a name="execution-and-injection"></a>执行和注入

**基于文件** 的 (类型 III：可执行文件、DLL、LNK 文件、计划任务) ：这是标准执行向量。 可以将简单的可执行文件作为第一阶段恶意软件启动，以在内存中运行额外的有效负载，或注入其他合法运行的进程。

**基于宏** 的 (类型 III：Office文档) ：[VBA 语言](/office/vba/Library-Reference/Concepts/getting-started-with-vba-in-office)是一种灵活而强大的工具，旨在自动编辑任务并向文档添加动态功能。 因此，攻击者可能会滥用它来执行恶意操作，例如解码、运行或注入可执行有效负载，甚至实现整个勒索软件，如 [qkG](https://blog.trendmicro.com/trendlabs-security-intelligence/qkg-filecoder-self-replicating-document-encrypting-ransomware/)。 宏在Office进程的上下文中执行， (例如，Winword.exe) 并以脚本语言实现。 防病毒无法检查任何二进制可执行文件。 虽然Office应用需要用户的明确同意才能从文档执行宏，但攻击者使用社会工程技术来欺骗用户允许执行宏。

**基于脚本** 的 (类型 II：文件、服务、注册表、WMI 存储库、shell) ：JavaScript、VBScript 和 PowerShell 脚本语言默认在Windows平台上可用。 脚本与宏具有相同的优势，它们是文本文件 (不是二进制可执行文件) 并在解释器的上下文中运行 (如wscript.exe、powershell.exe) ，这是一个干净而合法的组件。 脚本是通用的，可以通过双击) 或直接在解释器的命令行上执行，从文件 (运行脚本。 在命令行上运行允许恶意软件将恶意脚本编码为 [自动启动注册表项](https://www.gdatasoftware.com/blog/2014/07/23947-poweliks-the-persistent-malware-without-a-file) 内的服务，作为 WMI 存储库中的 [WMI 事件订阅](https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html) 。 此外，获得受感染计算机访问权限的攻击者可能会在命令提示符上输入脚本。

**基于磁盘** 的 (类型 II：启动记录) ：启动记录是磁盘或卷的第一个扇区，包含启动操作系统启动过程所需的可执行代码。 [Petya](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/27/new-ransomware-old-techniques-petya-adds-worm-capabilities/?source=mmpc) 等威胁可以通过使用恶意代码覆盖启动记录来感染该记录。 启动计算机时，恶意软件会立即获得控制。 启动记录位于文件系统外部，但操作系统可访问它。 新式防病毒产品能够对其进行扫描和还原。

## <a name="defeating-fileless-malware"></a>击败无文件恶意软件

在 Microsoft，我们积极监视安全环境，以确定新的威胁趋势，并开发解决方案来缓解各种威胁。 我们检测有效应对各种威胁的持久保护。 通过反恶意软件扫描接口 (AMSI) 、行为监视、内存扫描和启动扇区保护，[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)可以检查无文件威胁，即使存在严重的混淆。 借助云中的机器学习技术，我们能够针对新威胁和新出现的威胁缩放这些保护措施。

若要了解详细信息，请阅读： [看不见但不可见：使用行为监视、AMSI 和下一代 AV 击败无文件恶意软件](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/27/out-of-sight-but-not-invisible-defeating-fileless-malware-with-behavior-monitoring-amsi-and-next-gen-av/)

## <a name="additional-resources-and-information"></a>其他资源和信息

了解如何[跨Microsoft 365 E5部署威胁防护功能](/microsoft-365/solutions/deploy-threat-protection)。
