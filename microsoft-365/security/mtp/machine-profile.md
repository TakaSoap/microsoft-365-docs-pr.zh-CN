---
title: Microsoft 365 安全门户中的计算机配置文件
description: 查看组织中设备的风险和暴露级别。 分析过去和目前的威胁，并使用最新的更新保护计算机。
keywords: security、恶意软件、Microsoft 365、M365、Microsoft 威胁防护、MTP、security center、Microsoft Defender ATP、Office 365 ATP、Azure ATP、machine page、machine list、machine profile
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 7ab3f63008c65fca1a99128cc6f11f83bc86b2b4
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857551"
---
# <a name="machine-profile-page"></a>计算机配置文件页

Microsoft 365 安全门户为你提供了计算机配置文件页面，因此你可以评估网络上设备的运行状况和状态。 每个计算机配置文件页包含有关设备的大量信息。

您可以查看有关其正在运行的软件、任何过去和呈现的安全事件或警报的详细信息，并查找相关软件修补程序的链接。

您还可以使用计算机配置文件执行与安全相关的常见任务，并快速查看有关设备的基本详细信息。

## <a name="navigating-the-machine-profile-page"></a>导航计算机配置文件页

可以通过直接选择 "计算机" 列表中的设备名称或通过在 "计算机列表" 浮出控件中选择 "**打开计算机" 页面**来访问计算机配置文件页。

打开页面后，您会发现它分为三个部分。

![带有（1）选项卡区域（2）侧栏和（3）操作以红色突出显示的计算机配置文件页的图像](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

主内容区域（1）包含七个选项卡，可以通过切换这些选项卡来查看有关计算机的不同类型的信息。

边栏（2）列出有关计算机的基本详细信息。

在 "边栏" 和 "主内容" 部分前面的头（3）中还提供了响应操作。 您可以使用此标头中的操作执行常见的与安全相关的任务。

## <a name="tabs-section"></a>“选项卡”部分

通过计算机配置文件选项卡，可以切换有关计算机的安全详细信息的概述、包含警报列表的表、时间线、安全建议列表、软件清单、发现的漏洞列表以及丢失Kb （安全更新）。

### <a name="overview-tab"></a>概述选项卡

默认选项卡为**概述**。 它提供了有关设备最重要的安全事实的快速讨论。

![计算机配置文件的 "概述" 选项卡图像](../../media/mtp-machine-profile/overview.png)

您可以在此处找到设备风险级别和活动警报的图表、任何当前登录的用户、最常使用的用户的简短列表以及详细说明设备的暴露程度、安全建议、受影响的软件和安全评估。发现的漏洞。

### <a name="alerts-tab"></a>"通知" 选项卡

"**警报**" 选项卡包含已在设备上报告的警报的列表。

![计算机配置文件的 "警报" 选项卡图像](../../media/mtp-machine-profile/alerts.png)

您可以自定义所显示的项目数，以及为每个项目显示的列。 默认行为是为每个页面列出30个项目，并打开11列切换为显示。

此选项卡中的列包含有关触发警报的威胁的严重性的信息，以及状态、调查状态以及是否已向其分配了警报的人。

*受影响的实体*列指的是当前正在查看其配置文件的计算机（实体），以及受影响的网络中的任何其他计算机。

从该列表中选择一项将打开指向选定警报的链接。

可以按严重性、状态或受托人筛选此列表。

### <a name="timeline-tab"></a>日程表选项卡

"**时间线**" 选项卡包含在设备上引发的事件的交互式、按时间排列的图表。 通过移动图表的突出显示区域，可以查看不同时间范围内的事件。 您还可以键入日期的自定义范围。

图表下面是选定日期范围内的事件的列表。

![计算机配置文件的 "日程表" 选项卡的图像](../../media/mtp-machine-profile/timeline.png)

可以自定义显示的项目数和列表中的列。 默认列列出了事件时间、活动用户、操作类型、实体（进程）以及有关事件的其他信息。

从列表中选择一项将打开一个浮出控件，其中显示事件实体图，显示触发事件的父进程和子进程。

此列表可以按特定类型的事件进行筛选;例如，注册表事件或智能屏幕事件。

### <a name="security-recommendations-tab"></a>"安全性建议" 选项卡

"**安全建议**" 选项卡列出了可用于保护设备的操作。 选择此列表中的项将打开一个浮出控件，您可以在其中获取有关如何应用建议的说明。

![计算机配置文件的 "安全建议" 选项卡的图像](../../media/mtp-machine-profile/security-recs.png)

与以前的选项卡一样，每页显示的项目数和可自定义的列数。

默认视图包含详细介绍了解决安全弱点的列、相关威胁、受威胁影响的相关组件或软件等。 可以按建议的状态筛选项目。

### <a name="software-inventory"></a>软件清单

"**软件清单**" 选项卡列出了设备上安装的软件。

![计算机配置文件的 "软件清单" 选项卡的图像](../../media/mtp-machine-profile/software-inventory.png)

默认视图显示软件供应商、已安装版本号、已知软件弱点数、威胁见解、产品代码和标记。 可以自定义所显示的项目数以及显示的列。

从该列表中选择一项将打开一个浮出控件，其中包含有关所选软件的更多详细信息，以及上次找到该软件时的路径和时间戳。

可以按产品代码筛选此列表。

### <a name="discovered-vulnerabilities-tab"></a>发现的漏洞选项卡

"**发现的漏洞**" 选项卡列出了可能会影响设备的任何常见漏洞和漏洞（cve）。

![计算机配置文件的 "发现漏洞" 选项卡的图像](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

默认视图列出了 CVE 的严重性、常见漏洞得分（CVS）、发布的 CVE 发布时间、CVE 的最后更新时间以及与 CVE 相关的威胁。

与前面的选项卡一样，可以自定义所显示的项目数和可见的列。

从该列表中选择一项将打开一个描述 CVE 的浮出控件。

### <a name="missing-kbs"></a>缺少 Kb

"**缺少 kb** " 选项卡列出了所有尚未应用于计算机的 Microsoft 更新。 相关的 "Kb" 是介绍这些更新的[知识库文章](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query)。例如， [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)。

![缺少计算机配置文件的 kb 选项卡的图像](../../media/mtp-machine-profile/missing-kbs.PNG)

默认视图列出包含更新、OS 版本、受影响的产品、Cve 地址、KB 编号和标记的公告。

每页显示的项目数和可自定义的列数。

选择某个项目将打开一个链接到更新的浮出控件。

## <a name="sidebar"></a>边栏

在计算机配置文件页的主内容区域旁边是侧栏。

![计算机配置文件的边栏选项卡的图像](../../media/mtp-machine-profile/sidebar.png)

侧边栏提供了一些小子部分中的一些重要基本信息，这些信息可以切换为打开或关闭：

* **标记**-与设备关联的任何标记
* **安全信息**-开放事件、活动警报、暴露程度和风险级别
* **设备详细信息**-域、操作系统、资产组、运行状况状态、数据敏感度和 IP 地址
* **网络活动**-首次在网络上显示设备时的时间戳

此部分还包括设备的名称和暴露程度，以及用于指示其当前在网络中是否处于活动状态的图标。

## <a name="response-actions"></a>响应操作

响应操作提供了一种快速防御和分析威胁的方法。

![计算机配置文件的边栏选项卡的图像](../../media/mtp-machine-profile/actions.PNG)

您可以在此处使用的响应操作包括：

* **管理标记**-更新已应用于此设备的自定义标记。
* **隔离计算机**-将计算机与组织的网络隔离，同时保持它连接到 Microsoft Defender 高级威胁防护。 你可以选择允许 Outlook、团队和 Skype for Business 在计算机被隔离的情况下运行，以便进行通信。
* **限制应用程序执行**-阻止未由 Microsoft 签名的应用程序运行
* **运行防病毒扫描**-更新 Windows Defender 防病毒定义，并立即运行防病毒扫描。 在快速扫描或完全扫描之间进行选择。
* 收集有关计算机的**调查包**收集信息。 调查完成后，你可以下载它。
* **启动 Live Response session** -在计算机上加载远程命令行管理程序以进行[深入的安全调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。
* **启动自动调查**-自动[调查和 remediates 威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 尽管您可以手动触发自动调查以从此页面运行，但[某些警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies)会触发自己的自动调查。
* **操作中心**-查看已提交操作的状态。 仅在已选择另一操作时可用。

## <a name="related-topics"></a>相关主题

* [Microsoft 威胁防护概述](microsoft-threat-protection.md)
* [打开 Microsoft 威胁防护](mtp-enable.md)
* [使用实时响应调查计算机上的实体](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Office 365 中的自动化调查和响应（空气）](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
