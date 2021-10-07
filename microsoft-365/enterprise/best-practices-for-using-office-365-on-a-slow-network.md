---
title: 在慢速网络上Office 365的最佳实践
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 本文将指导你完成在慢速网络上使用 Office 365可采用的最佳方案。
ms.openlocfilehash: 0b3b46bcc28b8c25f363268adfa720f4d1df47b8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190601"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>在慢速网络上Office 365的最佳实践

如果 Internet 连接始终快速且从不关闭，那么不很好吗？ 也许这一天将来。 但在此期间，你可以采取一些实际操作来解决不稳定的网络，但仍可以完成日常工作。 尽管Office 365基于云的服务，但它还提供了许多脱机使用内容的方法，并平滑保持更改同步。 此外，有时脱机处理内容效率更高，因为应用程序运行速度更快，用户界面响应更快。 要点是：Office 365两全其美。 下面将了解如何利用这一点。

> [!TIP]
> 想要了解网络连接 (速度) 速度有多慢？ 尝试 [OOKLA 速度测试](https://www.speedtest.net/) 或 [网络速度测试应用](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70)。

## <a name="why-is-my-network-so-slow"></a>为什么我的网络速度很慢？

虽然你无法控制网络性能本身，但它有助于了解幕后所进行操作。 Internet 非常复杂，但有一些概念可以帮助你更好地了解情况。 遵循本文中的最佳实践可帮助解决性能问题并减少沮丧。

### <a name="major-factors-that-affect-network-performance"></a>影响网络性能的主要因素

![网络性能因素。](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)

 **带宽和延迟**：网络性能的两个最重要的度量是带宽和延迟：

- 带宽是以位/秒为单位测量的吞吐量速率。 越大越好。 带宽就像一条管道。 管道越大，可以"放入"的水就越大。

- 延迟是内容从服务器或服务到达设备所花的时间，以毫秒为单位计量。 越快越好。 延迟可能是由许多因素导致的，包括低带宽、稀疏连接或传输时间。

 **常见问题：** 除了带宽和延迟之外，其他问题还影响网络性能，并且通常不可预测。 网络性能可能会因一天中的时间或物理位置而有所波动。 当发生导致 Internet 使用峰值的某些事件（如自然灾害或重大公共事件）时，网络可能会变得阻塞。 所加载页面的大小和复杂性以及要传输的文件的数量和大小会直接影响性能。 Wlan 连接可能会暂时降级：例如，通过同时请求所有人访问推文来轮询成千上万的大型会议。

 **卫星网络的** 注意事项：当卫星网络不可行时（如返回国家/地区、飞行商或远程科学区域）时，卫星网络非常有用。 这些网络依赖于位于距卫星 22，000 英里的地理位置同步轨道中的卫星。 但是，传输实际传输大约 90，000 英里，因此卫星网络的延迟为 (500 毫秒或) 比一个卫星网络低 (20 到 50 毫秒) 。 在最佳情况下，你可能不会注意到此延迟，但对于下载大型文件、流视频和玩游戏，你可能会注意到。 另一个问题就是"衰减"，其中大天气（如风暴和风暴）可能会暂时中断卫星传输。

## <a name="are-you-sure-its-the-network"></a>确定它是网络吗？

每当遇到性能问题时，首先确保你的设备不是问题的根本原因。 有两件事可以做出很大改进：

- 确保你的设备运行良好，并且您的计算机上没有恶意软件。

- 如果可能，请购买更多内存。 添加内存是提高设备性能的最简单且最有效的方式。 在使用大型文件和视频时尤其有用。

有关详细信息，请参阅Windows[性能和维护](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help)以及使用技巧[以提高电脑在Windows 10。](https://support.microsoft.com/help/4002019/windows-10-improve-pc-performance)

## <a name="best-practices-for-using-your-browser"></a>使用浏览器的最佳实践

浏览器是Office 365网关，因此它可能会影响性能，尤其是加载页面的时间以及往返 Office 365 服务的时间。

### <a name="browsers-in-general"></a>浏览器一般

以下是浏览器的一些一般建议：

- 禁用可能会影响性能或不需要的浏览器加载项。

- 增加临时 Internet 文件的缓存大小。

- 登录工作或学校帐户后，请全天打开浏览器窗口。 无需再次登录，即可打开其他选项卡和窗口。 如果你需要登录到另一个帐户，请使用"私人浏览"。

- 下载并打开每个页面后，使用选项卡将其保持打开状态。 在选项卡之间导航和稍后在一天中使用该页面非常简单。 仅在页面上需要最新数据时刷新页面。

- 如果页面打开时间太长，请停止页面下载 (按 ESC) 然后刷新页面 (按 F5) 。

- 如果可能，请减少往返Office 365。 例如，使用搜索查找大型库中的文件，在列表中进行筛选以直接获取想要的结果，而不是分页浏览列表或库。 或者，创建可最大程度地缩短页面加载时间的视图。 有关详细信息，请参阅管理大型[列表和](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)库中Office 365。

- 如果视频性能较差，你或许可以下载视频，然后在你的设备上观看视频。 下载链接可能可用，或者你可以右键单击视频链接，然后选择将目标 **另存为**。

### <a name="browser-specific"></a>特定于浏览器

下面是特定浏览器的一些建议：

- **Internet Explorer：** 升级到 Internet Explorer 版本 11 或更高版本，以显著改进之前版本的性能。 有关详细信息，请参阅疑[难解答指南Internet Explorer。](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)
- **FireFox：** 有关详细信息，请参阅 [Firefox 运行缓慢或停止工作](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)。
- **Safari**：有关详细信息，请参阅 [Apple - Safari](https://www.apple.com/safari/)。
- **Chrome：** 有关详细信息，请参阅 [Chrome 帮助](https://support.google.com/chrome/?hl=en)。

## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>使用解决方案和Outlook Outlook Web App

阅读、编写和组织电子邮件是每个人一天中的重要组成部分。 OWA Outlook Outlook Web App (都) 脱机支持。 在智能手机上使用电子邮件应用是另一个有用的替代方法。 使用以下最符合需要的选项：

- 升级到最新版本的 Outlook，以显著改进早期版本的性能。

- Outlook Web App创建脱机消息、联系人和日历事件，当 OWA 下一步能够连接到 Office 365。 有关在脱机模式下设置和使用 OWA 的信息，请参阅使用脱机Outlook Web App [OWA。](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)

- Outlook允许你在缓存模式下工作，在缓存模式下，它可以尽可能自动连接。 您可以下载Outlook整个邮箱，或仅下载其中一部分。 有关详细信息，请参阅打开缓存模式[Exchange模式和](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c)在[缓存模式下Outlook。](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

- Outlook还提供脱机模式。 若要使用此模式，必须先设置缓存模式，以便从你的帐户将信息复制到计算机。 在脱机模式下，Outlook尝试使用发送和接收设置进行连接，或在手动将其设置为联机工作时进行连接。 有关详细信息，请参阅脱机工作以避免[数据](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)连接费用、在脱机工作时更改[](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)发送和接收设置和从脱机工作切换到[联机](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)。

- 如果你有智能手机，可以使用它通过手机运营商的网络对电子邮件和日历进行会审。

> [!NOTE]
> 下面是有关何时使用 OWA 或 Outlook指南。 如果磁盘空间在你的设备上不是问题，Outlook一组完整的功能，并且可能最适合你。 如果磁盘空间在你的设备上是一个问题，请考虑使用具有部分功能的 OWA，但在联机情况下也最适合。 当然，可以使用这两者，因为它们能很好地协同工作。

## <a name="best-practices-for-using-onedrive-for-business"></a>使用方法的OneDrive for Business

OneDrive for Business从零开始设计，以联机和脱机使用文件。 设置更改后，无论何时何地以及无论何时进行更改，都会自动可靠地进行同步。 如果网络速度较慢，可以使用脱机版本的文件。

the OneDrive for Business sync app with a SharePoint Online and Office 365 business subscription， or you can [download](https://support.microsoft.com/kb/2903984) the OneDrive for Business sync app for free. 此应用还比使用"在资源管理器中打开 **"****或** Upload速度更快。 有关详细信息，请参阅[将计算机设置为](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)在 Office 365 中同步OneDrive for Business文件。

下面是使用同步应用的其他OneDrive for Business指南：

- 如果是首次同步大型库，在非工作时间（例如，夜间）开始同步。
- 可以使用"停止与 OneDrive for Business[同步库"](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330)功能暂时停止同步更新。 但是，使用此功能的时间很短（例如一次几小时）以避免排队大量更新，并尽可能降低多个人员处理同一文档时出现合并冲突的风险。

## <a name="best-practices-for-using-onenote"></a>使用方法的OneNote

每个SharePoint网站都有一个内置的OneNote笔记本，并且可以轻松创建自己的笔记本。 OneNote是收集完成任务所需的及时信息的主要方式。 例如，许多团队OneNote每周会议、项目笔记、想法、计划和状态报告的集合点。 您可以使用页面、节和选项卡完全组织此不同的信息。

其OneNote一点就是，您几乎可以从任何设备（无论是台式机、笔记本电脑、平板电脑还是智能手机）访问内容。 你无需担心保存或同步，因为OneNote会进行保存或同步。

有关详细信息，[请参阅Microsoft OneNote。](https://office.microsoft.com/onenote)

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>使用 Lync Online Skype for Business最佳实践

以下是在网络较慢时Skype for Business Lync Online 或 Lync Online 的一般准则：

- 尽可能使用即时消息，因为它在慢速网络中运行良好。

- 避免通过虚拟专用网络或 RAS (VPN) 远程访问服务 (电话) 呼叫。

- 请确保你的音频设备已获得批准。 有关详细信息，请参阅 Phones [and Devices Qualified for Microsoft Lync。](/skypeforbusiness/lync-cert/ip-phones)

- 在PowerPoint演示文稿时，请减小幻灯片的大小和复杂性。 有关详细信息，请参阅使用技巧[演示文稿的性能。](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)

- 视频性能非常依赖于网络性能。 如果网络较慢，请避免使用视频。

有关详细信息，请参阅[Lync Online 中的音频或视频质量](https://support.microsoft.com/kb/2386655)差，或如何在 lync Online 中排[查Skype for Business。](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)

## <a name="best-practices-for-using-sharepoint-lists"></a>使用列表列表SharePoint最佳实践

脱机使用列表数据以"擦除"、"分析"或报告数据是最大程度地减小慢速网络的影响的一种好方法。 可以通过链接到 Microsoft Access 2019 和 Microsoft Access 2016大多数列表进行读取和写入。 您还可以将列表导出到 Excel Table，这将在表和列表之间创建Excel数据连接。 了解如何脱机[使用链接到列表的SharePoint。](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)

有关详细信息，请参阅管理大型列表和库中的"有关管理大型列表[Office 365。](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784)

## <a name="best-practices-for-customizing-web-pages"></a>自定义网页的最佳实践

自定义网页时，可能会无意中导致页面性能不佳。 许多因素都可能会影响页面，例如页面的复杂性和大小、添加的 Web 部件数量、最初显示的列表或库项目数以及您编码页面的方式。

有关详细信息，请参阅优化[SharePoint Online 性能](tune-sharepoint-online-performance.md)。

## <a name="best-practices-for-using-project-online"></a>使用方法的Project Online

以下指南可帮助改善网络性能。

- Project Online SharePoint Online 需要同步，这非常耗时。 如果项目团队的周转率较低，请禁用Project网站同步以改进Project发布Project详细信息页面性能。 将 Active Directory 同步限制为实际需要使用系统的资源组，并监视在同步大型组后的任何潜在权限问题。

- 如果您的组织使用项目网站，请按需创建这些网站，而不是自动创建。 这将加快第一次发布体验，并避免创建不必要的网站和内容。

- Project详细信息 (PDP) 可触发整个项目的重新计算并启动工作流操作，这两种操作都可能是性能密集型操作。 为避免在同一 PDP 上同时触发两个更新进程，请避免更新日历字段 (开始日期、完成日期、状态日期和当前日期) 以及非计划字段 (项目名称、说明和所有者) 。

- 减少每个 PDP Web 部件自定义字段的数量。 创建具有仅需要更新的字段的专用 PDP，以改进负载并节省时间。

- 使用 OData 进行报告时，使用服务器端筛选限制运行时查询的数据量。

有关详细信息，请参阅优化Project Online[性能](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)。

## <a name="whats-the-best-way-to-report-problems"></a>报告问题的最佳方法是什么？

Microsoft 通过监视网络、测量带宽和延迟、缩短页面加载时间、减少磁盘 I/O、重新设计页面以使用最少下载策略、向数据中心添加硬件以及添加更多数据中心，持续提高 Office 365 的整体性能。 有关检查当前状态和报告问题详细信息，请参阅如何[检查Office 365运行状况](view-service-health.md)。

## <a name="see-also"></a>另请参阅

[Office 365 网络计划和性能优化](network-planning-and-performance.md)

[Office 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[管理 Office 365 终结点](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Office 365 终结点 FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
