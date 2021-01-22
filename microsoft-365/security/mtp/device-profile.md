---
title: Microsoft 365 安全门户中的设备配置文件
description: 查看组织中设备的风险和曝光级别。 分析过去和现在的威胁，使用最新更新保护设备。
keywords: 安全， 恶意软件， Microsoft 365， M365， Microsoft 威胁防护， MTP， 安全中心， Microsoft Defender ATP， Office 365 ATP， Azure ATP， 设备页面， 设备配置文件， 计算机页面， 计算机配置文件
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929570"
---
# <a name="device-profile-page"></a>设备配置文件页

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 安全门户提供设备配置文件页面，以便快速评估网络上设备的运行状况和状态。

> [!IMPORTANT]
> 设备配置文件页面可能略有不同，具体取决于设备是注册 Microsoft Defender for Endpoint、Microsoft Defender for Identity 还是同时注册两者。

如果设备在 Microsoft Defender for Endpoint 中注册，则还可以使用设备配置文件页执行一些常见的安全任务。

## <a name="navigating-the-device-profile-page"></a>导航设备配置文件页

配置文件页分为几个广泛的部分。

![设备配置文件页面的图像 (1) 选项卡区域 (2) 边栏和 (3) 操作突出显示为红色](../../media/mtp-device-profile/hybrid-device-overall.png)

边栏 (1) 列出了有关设备的基本详细信息。

第 2 个 (区域) 选项卡，你可以切换这些选项卡以查看有关设备的不同类型的信息。

如果设备在 Microsoft Defender for Endpoint 中注册，你还将看到第 3 部分 (响应) 。 响应操作允许您执行与安全相关的常见任务。

## <a name="sidebar"></a>边栏

设备配置文件页的主要内容区域旁边是边栏。

![设备配置文件的边栏选项卡的图像](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

边栏列出了设备的全名和曝光级别。 它还在可以打开或关闭的小节中提供一些重要的基本信息，例如：

* **标记** - 任何 Microsoft Defender for Endpoint、Microsoft Defender for Identity 或与设备关联的自定义标记。 Microsoft Defender for Identity 中的标记不可编辑。
* **安全信息** - 打开事件和活动警报。 在 Microsoft Defender for Endpoint 中注册的设备还将显示曝光级别和风险级别。

> [!TIP]
> 曝光级别与设备遵守安全建议的数量相关，而风险级别根据多种因素（包括活动警报的类型和严重性）进行计算。

* **设备详细信息** - 域、操作系统、首次看到设备的时间戳、IP 地址和资源。 在 Microsoft Defender for Endpoint 中注册的设备还显示运行状况状态。 在 Microsoft Defender for Identity 中注册的设备将显示 SAM 名称和首次创建设备的时间戳。
* **网络** 活动 - 第一次和最后一次在网络中看到设备的时间戳。
* **目录数据** (在 Microsoft *Defender for Identity)* 注册的设备 - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) 标志 [、SNS](https://docs.microsoft.com/windows/win32/ad/service-principal-names)和组成员身份。

## <a name="response-actions"></a>响应操作

响应操作提供了一种快速防御和分析威胁的方法。

![设备配置文件的操作栏图像](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [只有设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) 在 Microsoft Defender for Endpoint 中注册时，响应操作才可用。
> * 在 Microsoft Defender for Endpoint 中注册的设备可能会根据设备的操作系统和版本号显示不同数量的响应操作。

设备配置文件页上可用的操作包括：

* **管理标记** - 更新已应用于此设备的自定义标记。
* **隔离设备** - 将设备与组织的网络隔离，同时将其保持与 Microsoft Defender for Endpoint 连接。 你可以选择允许 Outlook、Teams 和 Skype for Business 在设备隔离时运行，以便通信。
* **操作中心** - 查看已提交操作的状态。 仅在已选择其他操作时可用。
* **限制应用执行** - 阻止未由 Microsoft 签名的应用程序运行。
* **运行防病毒扫描** - Windows Defender防病毒定义并立即运行防病毒扫描。 在快速扫描或完全扫描之间选择。
* **收集调查包** - 收集有关设备的信息。 调查完成后，可以下载它。
* **启动实时响应会话** - 在设备上加载远程 shell 进行 [深入的安全调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。
* **启动自动调查** - [自动调查和修正威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 尽管你可以手动触发自动调查以从此页运行，但某些 [警报](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) 策略会自行触发自动调查。
* **操作中心** - 显示有关当前正在运行的任何响应操作的信息。

## <a name="tabs-section"></a>“选项卡”部分

设备配置文件选项卡允许你切换有关设备的安全详细信息的概述，以及包含警报列表的表。

在 Microsoft Defender for Endpoint 中注册的设备还将显示选项卡，这些选项卡具有时间线、安全建议列表、软件清单、发现的漏洞列表和缺少的 (B) 。

### <a name="overview-tab"></a>"概述"选项卡

默认选项卡为 **"概述"。** 它可快速查看有关设备最重要的安全事实。

![设备配置文件的概述选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

你可以在此处快速查看设备的活动警报以及任何当前登录的用户。

如果设备在 Microsoft Defender for Endpoint 中注册，你还将看到设备的风险级别和安全评估的任何可用数据。 安全评估描述设备的曝光级别、提供安全建议，并列出受影响的软件和发现的漏洞。

### <a name="alerts-tab"></a>"警报"选项卡

" **警报"** 选项卡包含从 Microsoft Defender for Identity 和 Microsoft Defender for Endpoint 在设备上引发警报的列表。

![设备配置文件的警报选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

您可以自定义显示的项目数，以及每个项目显示的列数。 默认行为是每页列出 30 个项目。

此选项卡中的列包含有关触发警报的威胁的严重性、状态、调查状态以及警报已分配给谁的信息。

受影响的 *实体* 列是指当前 () 其配置文件的设备实体，以及网络中受影响的任何其他设备。

从此列表选择一个项目将打开一个包含有关所选警报的详细信息的飞出。

此列表可以按严重性、状态或警报已分配给谁进行筛选。

### <a name="timeline-tab"></a>"日程表"选项卡

" **日程表** "选项卡包括设备上引发的所有事件的交互式时间顺序图表。 通过向左或向右移动图表的突出显示区域，可以查看不同时段内的事件。 您还可以从交互式图表和事件列表之间的下拉菜单中选择一个自定义日期范围。

图表下方是所选日期范围的事件列表。

![设备配置文件的时间线选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

显示的项目数和列表上的列都可以自定义。 默认列列出事件时间、活动用户、操作类型、 (处理) 以及事件的其他信息。

从此列表选择一个项目将打开一个显示事件实体图形的飞出图，其中显示事件所涉及的父进程和子进程。

该列表可以按特定类型的事件进行筛选;例如，注册表事件或智能屏幕事件。

列表还可以导出到 CSV 文件进行下载。 虽然文件不受事件数限制，但可以选择导出的最大时间范围是 7 天。

### <a name="security-recommendations-tab"></a>安全建议选项卡

" **安全建议"** 选项卡列出了可用于保护设备的操作。 选择此列表上的项目将打开一个飞出，您可以在其中获取有关如何应用建议的说明。

![设备配置文件的安全建议选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

与前面的选项卡一样，可以自定义每页显示的项目数以及可见的列数。

默认视图包括详细说明解决的安全漏洞、相关威胁、受威胁影响的相关组件或软件等的列。 项目可以按建议的状态进行筛选。

### <a name="software-inventory"></a>软件清单

" **软件清单** "选项卡列出了设备上安装的软件。

![设备配置文件的软件清单选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

默认视图显示软件供应商、已安装的版本号、已知软件漏洞的数量、威胁见解、产品代码和标签。 可以自定义显示的项目数和显示的列数。

从此列表选择一个项目将打开一个飞出，其中包含有关所选软件的更多详细信息，以及上次找到该软件时的路径和时间戳。

此列表可以按产品代码进行筛选。

### <a name="discovered-vulnerabilities-tab"></a>"发现的漏洞"选项卡

" **发现的漏洞"** 选项卡列出了可能影响设备的 (A) 和攻击。

![设备配置文件的已发现漏洞选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

默认视图列出了 CVE 的严重性、常见漏洞分数 (CVS) 、与 CVE 相关的软件、发布 CVE 的时间、上次更新 CVE 的时间以及与 CVE 关联的威胁。

与前面的选项卡一样，可以自定义显示的项目数和可见的列。

从此列表选择一个项目将打开描述 CVE 的飞出。

### <a name="missing-kbs"></a>缺少 KB

" **缺少的 KB"** 选项卡列出了尚未应用于设备的任何 Microsoft 更新。 相关"KBS"是[描述](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query)这些更新的知识库文章;例如[，KB4551762。](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)

![设备配置文件缺少 kbs 选项卡的图像](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

默认视图列出了包含更新、操作系统版本、受影响的产品、已寻址的 CES、KB 编号和标签的公告。

可以自定义每页显示的项目数和显示的列数。

选择项目将打开链接到更新的飞出。

## <a name="related-topics"></a>相关主题

* [Microsoft 365 Defender 概述](microsoft-threat-protection.md)
* [打开 Microsoft 365 Defender](mtp-enable.md)
* [使用实时响应调查设备上的实体](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Office 365 (AIR) 自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
