---
title: 步骤 1 - 设备和应用就绪情况
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何评估环境中的设备和应用就绪情况。
ms.openlocfilehash: eb619cf807c2bd4ad3644dbb26e72b62e30320c7
ms.sourcegitcommit: 03828f954b9dddb265f867fa508178ec0d4a6aeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2019
ms.locfileid: "35584548"
---
# <a name="step-1-device-and-app-readiness"></a>步骤 1：设备和应用就绪情况

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>步骤 1：设备和应用就绪情况</strong></p>
<p>首先为桌面部署项目清查设备和应用，确定进行操作的所需优先顺序，测试按优先顺序排列的应用和设备，然后针对部署所需的先决条件进行查漏补缺。</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>设备和应用就绪情况是我们建议的部署过程周期的第一步，它涵盖了应用程序和硬件兼容性的各个方面。 若要查看完整的桌面部署过程，请访问[桌面部署中心](https://aka.ms/HowToShift)。
>

在过去，升级用户桌面的主要障碍是应用程序和硬件兼容性。好消息是，当你计划转用 Windows 10 和 Office 365 专业增强版时，在最近 10 年内编写的几乎所有应用程序都将在 Windows 10 上运行，而组织在自 Office 2010 以来的 Office 版本上使用的任何 COM 加载项和 VBA 宏都将继续在最新版本的 Office 上运行，无需进行任何修改。

也就是说，根据组织的规模和年龄，验证应用程序和硬件兼容性很有可能仍是我们建议的 8 阶段部署过程中一个必不可少的初始步骤。

我们将在本文中指导你完成第一阶段：设备和应用就绪情况，方法是使用 Microsoft 就绪情况评估工具（包括新的桌面分析升级就绪情况工具），这是一套可通过 Windows 许可证获得的基于云的智能解决方案。

## <a name="windows-10-compatibility-scan"></a>Windows 10 兼容性扫描

在部署 Windows 10 之前，Microsoft 建议检查运行 Windows 7 或 8/8.1 的现有设备的就绪情况。 Windows 10 安装介质支持命令行开关，以便 setup.exe 运行升级，但仅检查兼容性，而非实际执行升级。 ScanOnly 可以作为脚本化批处理文件运行，也可以集成到 System Center Configuration Manager 任务序列中，包括直接从网络运行 ScanOnly 的功能，因此 Windows 10 安装介质不会被流式传输到本地设备。 当 ScanOnly 完成后，通过 Setup.EXE 生成的日志文件中的返回代码返回结果。   

自动完成兼容性扫描的示例 ScanOnly 命令行如下所示：

    Setup.EXE /Auto Upgrade /Quiet /NoReboot /Compat ScanOnly

有关 ScanOnly 和其他 Windows 安装程序命令开关的更多信息，请查看 [Windows 安装程序命令行选项](https://aka.ms/setupswitches)。

## <a name="recommended-tool-desktop-analytics-upgrade-readiness"></a>推荐的工具：桌面分析升级就绪情况

桌面分析升级就绪情况提供许多优于传统桌面管理系统的优势，是我们推荐使用的工具。 它没有代理，可以指导你完成利用通过升级数亿台使用者电脑收集的应用程序和驱动程序兼容性信息所需的操作。 此信息为你提供详细的评估，帮助确定可能会阻止升级的兼容性问题，并提供指向 Microsoft 已知建议修补程序的链接。

若要设置 Window Analytics 升级就绪情况，首先需要设置 Azure 订阅并为其添加一个 Azure Log Analytics 工作区。 运行桌面分析升级就绪情况服务后，便可以通过组策略设置注册任何连接 Internet 的 Windows 7 SP1 或更新系统的设备，非常简单。 不需要部署代理，桌面分析升级就绪情况的可视化工作流可指导你完成从试生产到生产部署的过程。 如果需要，可以将桌面分析升级就绪情况中的数据导出到软件部署工具（如 System Center Configuration Manager (Current Branch)），这样就可以在准备好部署时，直接定位电脑并生成集合。

如果当前环境未设置桌面分析或者想要注册试用版，请转到桌面分析页 http://www.aka.ms/desktopanalytics) 并开始使用。

## <a name="device-and-app-readiness-process"></a>设备和应用就绪情况过程

设备和应用就绪情况由个四个步骤组成：1. 清查，2. 确定优先顺序，3. 测试，4. 修正。 让我们依次了解一下。

### <a name="1-inventory"></a>1\. 清查

桌面分析升级就绪情况服务将使用无代理流程跨桌面空间清查计算机和应用程序。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

它还提供有关经常性访问的 Internet 站点、应用和 Intranet 位置报表，帮助你稍后进行兼容性测试。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. 确定优先顺序

借助清查过程，桌面分析升级就绪情况可帮助你确定组织中最常用的应用和硬件并区分优先次序，以及允许对尽可能多的电脑进行部署要注意的事项。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

此外，还提供在下一步“测试”中解决问题所需的帮助评估更新的指导。

### <a name="3-testing"></a>3\. 测试

你会发现清查的大多数应用程序、驱动程序和加载项将按原样工作。 对于桌面分析升级就绪情况评估出存在问题的项目，它会为你提供已知信息，包括在何处查找版本更新以解决兼容性问题。 可以选择与用户一起停用和替换这些项目，而不是花费时间和资源来解决稀疏部署的非关键型应用程序和较旧设备中的复杂问题。

还可以使用桌面分析升级就绪情况来评估基于浏览器的兼容性问题，识别由仍使用 ActiveX 控件、浏览器帮助程序对象、VBScript 或其他不受 Microsoft Edge 浏览器支持的旧版技术的用户访问的网站和 Web 应用。用户仍需要对这些站点使用 Internet Explorer 11，你可以使用 Enterprise Mode Site List Manager 将它们添加到[企业模式网站列表](https://docs.microsoft.com/zh-CN/microsoft-edge/deploy/emie-to-improve-compatibility)。

此外，为了帮助你迁移到 Office 365 专业增强版，你可能希望使用 [Readiness Toolkit for Office](https://docs.microsoft.com/zh-CN/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) 来测试加载项和 Microsoft Visual Basic for Applications (VBA) 宏的兼容性。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. 修正

设备和应用就绪情况的最后阶段是“修正”。 在此，你将希望收集所需的软件或驱动程序包；作为部署过程的一部分，你将使用这些包来替代或更新较旧版本。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

在处理列表修正问题时，你将看到越来越多的电脑变为“已准备好部署”。这意味着电脑上的驱动程序和应用都被标记为与你要部署的 Windows 10 目标版本兼容。

### <a name="configuration-manager-software-inventory-for-application-prioritization"></a>用于确定应用程序优先顺序的 Configuration Manager 软件清单

Configuration Manager 软件清单是为设备和应用就绪情况使用基于云的分析解决方案的替代方法。 可以使用安装计数并钻取到特定计算机，帮助确定兼容性测试和验证的优先顺序，并通过包设置将应用程序包设置为与 Windows 10 兼容。 虽然此选项无法比较与 Microsoft 的分析服务的已知兼容性信息，但它可以作为一个有效解决方案来定位一组较小的按优先级排列的应用，用于进行手动测试。 

有关更多信息，请参阅 [System Center Configuration Manager 中的软件清单简介](https://docs.microsoft.com/zh-CN/sccm/core/clients/manage/inventory/introduction-to-software-inventory)和 [System Center Configuration Manager 中的包和程序](https://docs.microsoft.com/zh-CN/sccm/apps/deploy-use/packages-and-programs)中的应用程序包的设置平台要求。


## <a name="desktop-app-assure"></a>桌面应用保证

另一个帮助实现 Windows 10 和 Office 365 专业增强版应用兼容性的工具是[桌面应用保证](https://aka.ms/desktopappassure)程序，可通过 FastTrack 中心获取它。 通过桌面应用保证，如果发生有效应用程序问题，Microsoft 工程师将与你协作，帮助修正应用程序不兼容问题，并且无需额外费用。

## <a name="continued-use-of-diagnostic-data-tools"></a>继续使用诊断数据工具

桌面分析升级就绪情况不只是帮助你转移到 Windows 10 和 Office 365 专业增强版的工具。一旦在 Windows 10 和 Office 365 上运行桌面，就可以使用它来维护部署，并管理半年度功能更新，以便掌握最新动态。

## <a name="next-step"></a>后续步骤 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[步骤 2：目录和网络就绪情况](https://aka.ms/mdd2)