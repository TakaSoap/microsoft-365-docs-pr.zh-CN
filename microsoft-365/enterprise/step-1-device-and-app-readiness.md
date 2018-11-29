---
title: 步骤 1 - 设备和应用就绪情况
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何评估环境中的设备和应用就绪情况。
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866047"
---
# <a name="step-1-device-and-app-readiness"></a>步骤 1：设备和应用就绪情况

首先为桌面部署项目配备设备和应用清单，确定进行操作的优先顺序，测试按优先顺序排列的应用和设备，然后修正准备进行部署的必备条件。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>步骤 1：设备和应用就绪情况</strong></p>
<p>首先为桌面部署项目配备设备和应用清单，确定进行操作的优先顺序，测试按优先顺序排列的应用和设备，然后针对部署所需的先决条件进行查漏补缺。</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>设备和应用就绪情况是我们建议的部署过程轮的第一步，它涵盖了应用程序和硬件兼容性的各个方面。若要查看完整的桌面部署过程，请访问[新式桌面部署中心](https://aka.ms/HowToShift)。
>

在过去，升级用户桌面的主要障碍是应用程序和硬件兼容性。好消息是，当你计划转用 Windows 10 和 Office 365 专业增强版时，在最近 10 年内编写的几乎所有应用程序都将在 Windows 10 上运行，而组织在自 Office 2010 以来的 Office 版本上使用的任何 COM 加载项和 VBA 宏都将继续在最新版本的 Office 上运行，无需进行任何修改。

也就是说，根据组织的规模和年龄，验证应用程序和硬件兼容性很有可能仍是我们建议的 8 阶段部署过程中一个必不可少的初始步骤。

我们将在本文指导你完成第一阶段 - 设备和应用就绪情况 - 使用新的 Windows Analytics 升级就绪情况工具，即一套可通过 Windows 许可证获得的基于云的智能解决方案。

如果当前环境未设置 Windows Analytics 或者想要注册试用版，请转到 [Windows Analytics 页](http://www.aka.ms/windowsanalytics)并开始使用。

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>推荐的工具：Windows Analytics 升级就绪情况

相比传统桌面管理系统，Windows Analytics 升级就绪情况提供了很多优势，并且是我们推荐的工具。它不需要代理；引导你完成需要完成的操作；它利用通过升级数亿台消费者电脑收集的应用程序和驱动程序兼容性信息来提供详细评估，识别可能阻碍你升级的兼容性问题，并使你链接到 Microsoft 已知的建议修补程序。

若要设置 Window Analytics 升级就绪情况，首先需要设置 Azure 订阅并在其中添加 Azure Log Analytics 工作区。在 Windows Analytics 升级就绪情况服务运行后，可以通过“组策略”设置注册任何连接 Internet 的 Windows 7 SP1 或较新设备。就这么简单。无需部署代理，Windows Analytics 升级就绪情况的可视化工作流将引导你完成从试点到生产部署的过程。如果需要，可以将数据从 Windows Analytics 升级就绪情况导出到软件部署工具（如 System Center Configuration Manager），以直接指向电脑，并在准备好进行部署的情况下生成集合。

## <a name="device-and-app-readiness-process"></a>设备和应用就绪过程

设备和应用就绪情况包含四个步骤：1. 清查，2. 确定优先顺序，3. 测试，4. 修正。现在我们来依次了解各步骤。

### <a name="1-inventory"></a>1\. 清查

Windows Analytics 升级就绪情况服务将使用无代理流程跨桌面空间清查计算机、应用程序和 Office 加载项。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

它还提供有关经常性访问的 Internet 站点、应用和 Intranet 位置报表，来帮助你稍后进行兼容性测试。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. 确定优先顺序

借助清单，Windows Analytics 升级就绪情况可帮助你确定组织中最常用的应用和硬件并区分优先次序，以及允许对尽可能多的电脑进行部署要注意的事项，

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

此外，提供帮助评估更新的指导将用于在下一步“测试”中解决问题。

### <a name="3-testing"></a>3\. 测试

你会发现大部分已清点的应用程序、驱动程序和加载项都将按原先方式工作。对于有问题的 Windows Analytics 升级就绪情况评估项，它会提供已知信息，包括查找版本更新以解决兼容性问题的位置。可以选择与用户协作来停用和替换这些项，而不是花时间和资源解决非关键型、稀疏部署的应用程序和较旧设备中的复杂问题。

还可以使用 Windows Analytics 升级就绪情况来评估基于浏览器的兼容性问题，识别由仍使用 ActiveX 控件、浏览器帮助程序对象、VBScript 或其他不受 Microsoft Edge 浏览器支持的旧版技术的用户访问的网站和 Web 应用。用户仍需要对这些站点使用 Internet Explorer 11，你可以使用 Enterprise Mode Site List Manager 将它们添加到[企业模式网站列表](https://docs.microsoft.com/zh-CN/microsoft-edge/deploy/emie-to-improve-compatibility)。

此外，为了帮助你迁移到 Office 365 专业增强版，你可能希望使用 [Readiness Toolkit for Office](https://docs.microsoft.com/zh-CN/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) 来测试加载项和 Microsoft Visual Basic for Applications (VBA) 宏的兼容性。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. 修正

设备和应用就绪情况的最后阶段是“修正”。在此，你将希望收集所需的软件或驱动程序包；作为部署过程的一部分，你将使用这些包来替代或更新较旧版本。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

在处理列表修正问题时，你将看到越来越多的电脑变为“已准备好部署”。这意味着电脑上的驱动程序和应用都被标记为与你要部署的 Windows 10 目标版本兼容。

## <a name="continued-use-of-telemetry-tools"></a>继续使用遥测工具

Windows Analytics 升级就绪情况不只是帮助你转移到 Windows 10 和 Office 365 专业增强版的工具。一旦在 Windows 10 和 Office 365 上运行桌面，就可以使用它来维护部署，并管理半年度功能更新，以便掌握最新动态。

## <a name="next-step"></a>后续步骤 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[步骤 2：目录和网络就绪情况](https://aka.ms/mdd2)