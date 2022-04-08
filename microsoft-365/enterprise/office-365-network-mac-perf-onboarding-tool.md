---
title: Microsoft 365 网络连接测试工具
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 1/18/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 网络连接测试工具
ms.openlocfilehash: 047a1ad10efa20f2c47491a20855a92bf141eb15
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705572"
---
# <a name="microsoft-365-network-connectivity-test-tool"></a>Microsoft 365 网络连接测试工具

Microsoft 365网络连接测试工具位于 <https://connectivity.office.com>。 它是运行状况|下Microsoft 365 管理中心中提供的网络评估和网络见解的辅助工具 **连接** 菜单。

> [!IMPORTANT]
> 登录到Microsoft 365租户非常重要，因为所有测试报表都与管理员共享，并在登录时上传到租户。

> [!div class="mx-imgBorder"]
> ![连接测试工具。](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>网络连接测试工具支持 WW 商业版中的租户，但不支持中等、GCC高、DoD 或中国GCC租户。

Microsoft 365 അഡ്‌മിൻ中心的网络见解基于每天聚合的Microsoft 365租户的常规产品内度量。 相比之下，来自Microsoft 365网络连接测试的网络见解在工具中本地运行。

产品内测试受到限制，在用户本地运行测试会收集更多数据，从而获得更深入的见解。 Microsoft 365 അഡ്‌മിൻ中心的网络见解将显示特定办公位置存在网络问题。 Microsoft 365连接测试有助于确定该问题的根本原因，并提供有针对性的性能改进操作。

我们建议将这些见解一起使用，其中可以评估Microsoft 365 അഡ്‌മിൻ中心内每个办公位置的网络质量状态，并在部署基于Microsoft 365连接测试的测试后找到更多细节。

## <a name="what-happens-at-each-test-step"></a>每个测试步骤中发生的情况

### <a name="office-location-identification"></a>Office位置标识

单击 *"运行测试* "按钮时，我们将显示正在运行的测试页并标识办公室位置。 可以按城市、州和国家/地区键入位置，或者选择为你检测到它。 如果检测到办公室位置，该工具会从 Web 浏览器请求纬度和经度，并在使用前将准确度限制为 300 米（300 米）。 无需比建筑物更准确地标识位置，以度量网络性能。

### <a name="javascript-tests"></a>JavaScript 测试

在办公室位置识别之后，我们将在 JavaScript 中运行 TCP 延迟测试，并从服务请求有关使用中的数据，并建议Microsoft 365服务前门服务器。 完成这些测试后，我们会在地图和详细信息选项卡中显示这些测试，可在下一步之前查看这些测试。

### <a name="download-the-advanced-tests-client-application"></a>下载高级测试客户端应用程序

接下来，开始下载高级测试客户端应用程序。 我们依靠用户来启动客户端应用程序，并且还必须安装 .NET 6.0 运行时。

Microsoft 365网络连接测试有两个部分：网站<https://connectivity.office.com>和运行高级网络连接测试的可下载Windows客户端应用程序。 大多数测试都需要运行应用程序。 它将在运行时将结果填充回网页。

Web 浏览器测试完成后，系统会提示你从网站下载高级客户端测试应用程序。 在出现提示时打开并运行该文件。

> [!div class="mx-imgBorder"]
> ![高级测试客户端应用程序。](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>启动高级测试客户端应用程序

客户端应用程序启动后，网页将更新以显示此结果。 测试数据将开始接收到网页。 每次收到新数据时，页面都会更新，可以在数据到达时查看数据。

### <a name="advanced-tests-completed-and-test-report-upload"></a>高级测试已完成并测试报表上传

测试完成后，网页和高级测试客户端都将显示。 如果用户已登录，测试报告将上传到客户的租户。

## <a name="sharing-your-test-report"></a>共享测试报表

测试报表需要对Microsoft 365帐户进行身份验证。 管理员选择如何共享测试报表。 默认设置允许与组织内的其他用户共享报表，并且 ReportID 链接不可用。 报表将在 90 天后默认过期。

### <a name="sharing-your-report-with-your-administrator"></a>与管理员共享报表

如果在测试报表发生时登录，则报表将与管理员共享。

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>与 Microsoft 帐户团队、支持人员或其他人员共享

测试报告 (排除任何个人标识) 与 Microsoft 员工共享。 默认情况下，此共享已启用，管理员可以在 **运行状况|中禁用此共享Microsoft 365 അഡ്‌മിൻ中心的"网络连接"** 页。

### <a name="sharing-with-other-users-who-sign-in-to-the-same-microsoft-365-tenant"></a>与其他登录到同一Microsoft 365租户的用户共享

可以选择要与之共享报表的用户。 默认情况下，能够选择是启用的，但管理员可以禁用它。

> [!div class="mx-imgBorder"]
> ![与用户共享测试结果的链接。](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>与使用 ReportID 链接的任何人共享

可以通过提供对 ReportID 链接的访问权限，与任何人共享测试报表。 此链接生成一个 URL，你可以将其发送给某人，以便他们可以在不登录的情况下提出测试报表。 默认情况下，此共享处于禁用状态，并且必须由管理员启用。

> [!div class="mx-imgBorder"]
> ![共享测试结果的链接。](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>网络连接测试结果

结果显示在 **摘要** 和 **详细信息** 选项卡中。 摘要选项卡显示检测到的网络外围的地图，以及网络评估与附近其他Microsoft 365客户的比较。 它还允许共享测试报告。 摘要结果视图如下所示:

> [!div class="mx-imgBorder"]
> ![网络连接测试工具摘要结果。](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

下面是详细信息选项卡输出的示例。 在"详细信息"选项卡上，如果结果比较有利，我们将显示一个绿色圆圈复选标记。 如果结果超过指示网络见解的阈值，我们将显示红色三角形感叹号。 以下各节介绍每个详细信息选项卡结果行，并说明用于网络见解的阈值。

> [!div class="mx-imgBorder"]
> ![网络连接测试工具示例测试结果。](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>位置信息

本部分显示与你的位置相关的测试结果。

#### <a name="your-location"></a>你的位置

从用户 Web 浏览器检测到用户位置。 也可以在用户选择时键入它。 它用于标识与企业网络外围特定部分的网络距离。 报表中仅保存从此位置检测到的城市以及与其他网络点的距离。

用户办公室位置显示在地图视图上。

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>网络出口位置 (网络连接到 ISP) 的位置

我们标识服务器端的网络出口 IP 地址。 位置数据库用于查找网络出口的大致位置。 这些数据库通常具有大约 90% 的 IP 地址的准确性。 如果从网络出口 IP 地址查找的位置不准确，将导致错误的结果。 若要验证特定 IP 地址是否发生此错误，可以使用可公开访问的网络 IP 地址位置网站与实际位置进行比较。

#### <a name="your-distance-from-the-network-egress-location"></a>你与网络出口位置之间的距离

我们确定从该位置到办公室位置的距离。 如果距离大于 **500 英里 (800** 公里) ，这会显示为网络见解，因为这可能会使 TCP 延迟增加 25 毫秒以上，并可能影响用户体验。

地图显示与用户办公室位置相关的网络出口位置，该位置指示企业 WAN 内部的网络回流位置。

实现从用户办公室位置到 Internet 的本地和直接网络出口，以实现最佳Microsoft 365网络连接。 改进本地出口和直接出口是解决此网络见解的最佳方法。

#### <a name="proxy-server-information"></a>代理服务器信息

我们确定是否在本地计算机上配置代理服务器 () 以传递 **Optimize 类别中的** Microsoft 365网络流量。 我们确定从用户办公室位置到代理服务器的距离。

ICMP ping 首先测试距离。 如果失败，我们将使用 TCP ping 进行测试，最后在 IP 地址位置数据库中查找代理服务器 IP 地址。 如果代理服务器距离用户办公室位置 **800 公里 (800** 公里) ，则会显示网络见解。

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>用于连接到组织的虚拟专用网络 (VPN) 

此测试检测是否使用 VPN 连接到Microsoft 365。 如果没有 VPN，或者 VPN 具有建议的Microsoft 365拆分隧道配置，则会显示传递结果。

#### <a name="vpn-split-tunnel"></a>VPN 拆分Tunnel

测试Exchange Online、SharePoint联机和Microsoft Teams的每个 **Optimize** 类别路由，以确定它是否在 VPN 上进行隧道。 拆分工作负载可完全避免 VPN。 通过 VPN 发送隧道工作负荷。 选择性隧道工作负荷有一些通过 VPN 发送的路由，有些路由会拆分。传递结果将显示所有工作负载是拆分还是选择性隧道。

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>具有更好性能的大都市区客户

将用户办公室位置与Exchange Online服务之间的网络延迟与同一城区的其他Microsoft 365客户进行比较。 如果同一都会区 10% 或更多客户的性能更好，则会显示网络见解。 这意味着其用户在Microsoft 365用户界面中将具有更好的性能。

生成此网络见解的基础是，城市中的所有用户都有权访问同一电信基础结构，并且与 Internet 线路和 Microsoft 网络的距离相同。

#### <a name="time-to-make-a-dns-request-on-your-network"></a>在网络上发出 DNS 请求的时间

这会显示在运行测试的客户端计算机上配置的 DNS 服务器。 它可能是 DNS 递归解决程序服务器，但这种情况并不常见。 它更有可能是 DNS 转发器服务器，它缓存 DNS 结果并将任何未缓存的 DNS 请求转发到另一个 DNS 服务器。

这仅适用于信息，不有助于任何网络见解。

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>连接到 DNS 递归解析程序的距离和/或时间

使用中的 DNS 递归解决程序是通过发出特定的 DNS 请求，然后向 DNS 名称服务器询问它从中收到相同请求的 IP 地址来标识的。 此 IP 地址是 DNS 递归解析程序，它将在 IP 地址位置数据库中查找位置。 然后计算从用户办公室位置到 DNS 递归解决程序服务器位置的距离。 如果距离大于 **500 英里 (800** 公里) ，这会显示为网络见解。

从网络出口 IP 地址查找的位置可能不准确，这将导致此测试产生错误的结果。 若要验证特定 IP 地址是否发生此错误，可以使用可公开访问的网络 IP 地址位置网站。

此网络见解将具体影响Exchange Online服务前门的选择。 若要解决此见解，本地和直接网络出口应是先决条件，然后 DNS 递归解决程序应位于该网络出口附近。

### <a name="exchange-online"></a>Exchange Online

本部分显示与Exchange Online相关的测试结果。

#### <a name="exchange-service-front-door-location"></a>Exchange服务前门位置

使用中Exchange服务前门的标识方式与Outlook执行此操作的方式相同，我们测量了从用户位置到它的网络 TCP 延迟。 将显示 TCP 延迟，并将使用中的Exchange服务前门与当前位置的最佳服务前门列表进行比较。 如果未使用最佳Exchange服务前门 () 之一，则此功能将显示为网络见解。

不使用最佳Exchange服务前门 () 可能是由企业网络出口之前的网络回流引起的，在这种情况下，我们建议进行本地和直接网络出口。 也可能由使用远程 DNS 递归解析程序服务器导致，在这种情况下，我们建议将 DNS 递归解析程序服务器与网络出口对齐。

我们计算了 TCP 延迟的潜在改进 (ms) 到Exchange服务前门。 为此，请查看已测试的用户办公室位置网络延迟，并将网络延迟从当前位置减去到服务前门Exchange壁橱。 差异表示潜在的改进机会。

#### <a name="best-exchange-service-front-doors-for-your-location"></a>最佳Exchange服务前门 (位置的) 

这列出了按城市列出的最佳Exchange服务前门位置。

#### <a name="service-front-door-recorded-in-the-client-dns"></a>客户端 DNS 中记录的服务前门

这会显示定向到的Exchange服务前门服务器的 DNS 名称和 IP 地址。 它仅提供信息，没有关联的网络见解。

### <a name="sharepoint-online"></a>SharePoint Online

本部分显示与联机和OneDrive SharePoint相关的测试结果。

#### <a name="the-service-front-door-location"></a>服务前门位置

使用中SharePoint服务前门的标识方式与OneDrive客户端的识别方式相同，我们测量了从用户办公室位置到它的网络 TCP 延迟。

#### <a name="download-speed"></a>下载速度

我们从SharePoint服务前门测量 15 Mb 文件的下载速度。 结果以每秒 兆字节为单位显示，指示可以在 **一秒** 内从SharePoint或OneDrive下载的大小文件（以 MB 为单位）。 该数字应类似于每秒兆位的最小线路带宽的十分之一。 例如，如果 Internet 连接为 100mbps，则 (10 MBps) ，每秒可能需要 10 兆字节。

#### <a name="buffer-bloat"></a>缓冲区 Bloat

在 15Mb 下载期间，我们测量到SharePoint服务前门的 TCP 延迟。 这是负载下的延迟，与不加载时的延迟进行比较。 加载时延迟的增加通常归因于 (或膨胀) 加载的使用者网络设备缓冲区。 对于任何 1，000 个或更多 Bloat，将显示一个网络见解。

#### <a name="service-front-door-recorded-in-the-client-dns"></a>客户端 DNS 中记录的服务前门

这会显示定向到的SharePoint服务前门服务器的 DNS 名称和 IP 地址。 它仅提供信息，没有关联的网络见解。

### <a name="microsoft-teams"></a>Microsoft Teams

本部分显示与Microsoft Teams相关的测试结果。

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>媒体连接 (音频、视频和应用程序共享) 

这会测试 UDP 与Microsoft Teams服务前门的连接。 如果阻止此操作，则 Microsoft Teams 可能仍可使用 TCP，但音频和视频将受到影响。 详细了解这些 UDP 网络度量，这些度量也适用于 Skype for Business [Online 中媒体质量和网络连接性能Microsoft Teams](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

#### <a name="packet-loss"></a>数据包丢失

显示从客户端到Microsoft Teams服务前门的 10 秒测试音频调用中测量的 UDP 数据包丢失。 对于传递，此值应低于 **1.00%。**

#### <a name="latency"></a>延迟

显示测量的 UDP 延迟，应小于 **100ms**。

#### <a name="jitter"></a>抖动

显示测量的 UDP 抖动，应小于 **30ms**。

#### <a name="connectivity"></a>连接性

我们测试从用户办公室位置到所有所需的Microsoft 365网络终结点的 HTTP 连接。 这些是发布于 [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md). 对于无法连接到的任何必需网络终结点，会显示网络见解。

代理服务器、防火墙或企业网络外围上的其他网络安全设备可能会阻止连接。 使用 HTTP 请求测试与 TCP 端口 80 的连接，并使用 HTTPS 请求测试与 TCP 端口 443 的连接。 如果没有响应，则 FQDN 标记为失败。 如果有 HTTP 响应代码 407，则 FQDN 标记为失败。 如果有 HTTP 响应代码 403，则检查响应的服务器属性，如果它似乎是代理服务器，我们将此标记为失败。 可以使用Windows命令行工具curl.exe模拟我们执行的测试。

我们在每个必需的Microsoft 365网络终结点测试 SSL 证书，该终结点位于所定义的优化或允许类别中[https://aka.ms/o365ip](./urls-and-ip-address-ranges.md)。 如果任何测试都找不到 Microsoft SSL 证书，则已连接的加密网络必须已被中间网络设备截获。 网络见解显示在任何截获的加密网络终结点上。

如果发现未由 Microsoft 提供的 SSL 证书，我们将显示测试的 FQDN 和正在使用的 SSL 证书所有者。 此 SSL 证书所有者可以是代理服务器供应商，也可以是企业自签名证书。

#### <a name="network-path"></a>网络路径

本部分显示 ICMP 跟踪到Exchange Online服务前门、SharePoint联机服务前门和Microsoft Teams服务前门的结果。 它仅提供信息，没有关联的网络见解。 提供了三个跟踪路由。 到 _outlook.office365.com_ 的跟踪路、到客户SharePoint前端的跟踪路 _，或者未_ 提供 microsoft.sharepoint.com 的跟踪路由，以及 _world.tr.teams.microsoft.com_ 的跟踪路由。

## <a name="connectivity-reports"></a>连接报告

登录后，可以查看之前运行的报表。 还可以共享它们或从列表中删除它们。

> [!div class="mx-imgBorder"]
> ![报告。](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>网络运行状况状态

这显示了 Microsoft 全球网络的任何重大运行状况问题，这可能会影响Microsoft 365客户。

> [!div class="mx-imgBorder"]
> ![网络运行状况状态。](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="testing-from-the-command-line"></a>从命令行进行测试

我们提供可由远程部署和执行工具使用的命令行可执行文件，并运行与Microsoft 365网络连接测试工具网站中提供的测试相同的测试。

可在此处下载命令行测试工具： [命令行工具](https://connectivity.office.com/api/AnonymousConnectivityTest/DownloadStandAloneRichClient)

可以通过双击Windows 文件资源管理器中的可执行文件来运行它，也可以从命令提示符启动它，也可以使用任务计划程序来计划它。

首次启动可执行文件时，系统会提示你在执行测试之前接受最终用户许可协议 (EULA) 。 如果已读取并接受 EULA，则可以在当前工作目录中为可执行过程启动时创建名为Microsoft-365-Network-Connectivity-Test-EULA-accepted.txt的空文件。 若要接受 EULA，可以键入"y"并在出现提示时按在命令行窗口中输入。

可执行文件接受 /h 的命令行参数，以显示此帮助文档的链接。

### <a name="results"></a>结果
结果输出将写入名为 TestResults 的文件夹中的 JSON 文件，该文件夹在进程的当前工作目录中创建，除非该文件已存在。 输出的文件名格式为connectivity_test_result_YYYY-MM-DD-HH-MM-SS.json。 结果位于 JSON 节点中，这些节点与Microsoft 365网络连接测试工具网站网页上显示的输出匹配。 每次运行时都会创建一个新的结果文件，独立可执行文件不会将结果上传到 Microsoft 租户以供在管理中心网络连接页中查看。

### <a name="launching-from-windows-file-explorer"></a>从Windows 文件资源管理器启动
只需双击可执行文件即可启动测试，并显示命令提示符窗口。

### <a name="launching-from-the-command-prompt"></a>从命令提示符启动
在CMD.EXE命令提示符窗口中，可以键入要运行它的可执行文件的路径和名称。 文件名Microsoft.Connectivity.Test.exe

### <a name="launching-from-windows-task-scheduler"></a>从Windows任务计划程序启动
在Windows任务计划程序中，可以添加一个任务来启动独立测试可执行文件。 应将任务的当前工作目录指定为创建 EULA 接受文件的位置，因为在接受 EULA 之前，可执行文件将被阻止。 如果进程在后台启动且没有控制台，则无法以交互方式接受 EULA。

### <a name="more-details-on-the-standalone-executable"></a>有关独立可执行文件的更多详细信息
命令行工具使用Windows位置服务查找用户城市状态国家/地区信息，以确定一些距离。 如果在控制面板中禁用了Windows位置服务，则基于用户位置的评估将是空白的。 在Windows 设置"位置服务"必须处于打开状态，"让桌面应用访问你的位置"也必须处于打开状态。

如果尚未安装，命令行工具将尝试安装.NET Framework。 它还将从Microsoft 365网络连接测试工具下载主测试可执行文件，并启动该工具。

## <a name="faq"></a>常见问题

以下是我们一些常见问题的解答。

### <a name="what-is-required-to-run-the-advanced-test-client"></a>运行高级测试客户端需要什么？

高级测试客户端需要 .NET 6.0 运行时。 如果运行未安装的高级测试客户端，将定向到 [.NET 6.0 安装程序页](https://dotnet.microsoft.com/en-us/download/dotnet/6.0/runtime?utm_source=getdotnetcore)。 请务必从"运行桌面应用"列安装Windows。 安装 .NET 6.0 运行时需要计算机上的管理员权限。

高级测试客户端使用 SignalR 与网页通信。 为此，必须确保 TCP 端口 443 与 **connectivity.service.signalr.net** 的连接已打开。 此 URL 未在其中<https://aka.ms/o365ip>发布，因为Microsoft 365客户端应用程序用户不需要连接。

### <a name="what-is-microsoft-365-service-front-door"></a>什么是服务前门Microsoft 365？

Microsoft 365服务前门是 Microsoft 全球网络上的入口点，Office客户端和服务终止其网络连接。 为了实现与Microsoft 365的最佳网络连接，建议将网络连接终止到城市或地铁最靠近Microsoft 365前门。

> [!NOTE]
> Microsoft 365服务前门与 **Azure 市场中提供的 Azure Front Door 服务** 产品没有直接关系。

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>什么是最佳Microsoft 365服务前门？

最佳Microsoft 365服务前门 (以前称为最佳服务前门) 是离网络出口最近的门，通常位于你的城市或市区。 使用Microsoft 365网络性能工具确定Microsoft 365服务前门和最佳服务前门 () 的位置。 如果该工具确定你使用的前门是最好的门之一，那么你应该期望与 Microsoft 的全球网络建立良好的连接。

### <a name="what-is-an-internet-egress-location"></a>什么是 Internet 出口位置？

Internet 出口位置是网络流量退出企业网络并连接到 Internet 的位置。 这也标识为具有网络地址转换 (NAT) 设备的位置，通常与 Internet 服务提供商 (ISP) 连接的位置。 如果在位置和 Internet 出口位置之间看到较长的距离，则可能会识别出重要的 WAN 后端。

## <a name="related-topics"></a>相关主题

[Microsoft 365 അഡ്‌മിൻ中心的网络连接](office-365-network-mac-perf-overview.md)

[Microsoft 365网络性能见解](office-365-network-mac-perf-insights.md)

[Microsoft 365网络评估](office-365-network-mac-perf-score.md)

[Microsoft 365网络连接位置服务](office-365-network-mac-location-services.md)
