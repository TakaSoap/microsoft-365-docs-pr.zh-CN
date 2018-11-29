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
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="487e4-103">步骤 1：设备和应用就绪情况</span><span class="sxs-lookup"><span data-stu-id="487e4-103">Step 1: Device and App Readiness</span></span>

<span data-ttu-id="487e4-104">首先为桌面部署项目配备设备和应用清单，确定进行操作的优先顺序，测试按优先顺序排列的应用和设备，然后修正准备进行部署的必备条件。</span><span class="sxs-lookup"><span data-stu-id="487e4-104">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="487e4-105"><strong>步骤 1：设备和应用就绪情况</strong></span><span class="sxs-lookup"><span data-stu-id="487e4-105"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="487e4-106">首先为桌面部署项目配备设备和应用清单，确定进行操作的优先顺序，测试按优先顺序排列的应用和设备，然后针对部署所需的先决条件进行查漏补缺。</span><span class="sxs-lookup"><span data-stu-id="487e4-106">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="487e4-p101">设备和应用就绪情况是我们建议的部署过程轮的第一步，它涵盖了应用程序和硬件兼容性的各个方面。若要查看完整的桌面部署过程，请访问[新式桌面部署中心](https://aka.ms/HowToShift)。</span><span class="sxs-lookup"><span data-stu-id="487e4-p101">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="487e4-p102">在过去，升级用户桌面的主要障碍是应用程序和硬件兼容性。好消息是，当你计划转用 Windows 10 和 Office 365 专业增强版时，在最近 10 年内编写的几乎所有应用程序都将在 Windows 10 上运行，而组织在自 Office 2010 以来的 Office 版本上使用的任何 COM 加载项和 VBA 宏都将继续在最新版本的 Office 上运行，无需进行任何修改。</span><span class="sxs-lookup"><span data-stu-id="487e4-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="487e4-111">也就是说，根据组织的规模和年龄，验证应用程序和硬件兼容性很有可能仍是我们建议的 8 阶段部署过程中一个必不可少的初始步骤。</span><span class="sxs-lookup"><span data-stu-id="487e4-111">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="487e4-112">我们将在本文指导你完成第一阶段 - 设备和应用就绪情况 - 使用新的 Windows Analytics 升级就绪情况工具，即一套可通过 Windows 许可证获得的基于云的智能解决方案。</span><span class="sxs-lookup"><span data-stu-id="487e4-112">In this article we take you through that first phase – Device and App Readiness – using the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

<span data-ttu-id="487e4-113">如果当前环境未设置 Windows Analytics 或者想要注册试用版，请转到 [Windows Analytics 页](http://www.aka.ms/windowsanalytics)并开始使用。</span><span class="sxs-lookup"><span data-stu-id="487e4-113">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="487e4-114">推荐的工具：Windows Analytics 升级就绪情况</span><span class="sxs-lookup"><span data-stu-id="487e4-114">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="487e4-p103">相比传统桌面管理系统，Windows Analytics 升级就绪情况提供了很多优势，并且是我们推荐的工具。它不需要代理；引导你完成需要完成的操作；它利用通过升级数亿台消费者电脑收集的应用程序和驱动程序兼容性信息来提供详细评估，识别可能阻碍你升级的兼容性问题，并使你链接到 Microsoft 已知的建议修补程序。</span><span class="sxs-lookup"><span data-stu-id="487e4-p103">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool. It is agentless; it guides you through what needs to be done; and, it makes use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs, to give you a detailed assessment, identifying compatibility issues that might block your upgrade, with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="487e4-p104">若要设置 Window Analytics 升级就绪情况，首先需要设置 Azure 订阅并在其中添加 Azure Log Analytics 工作区。在 Windows Analytics 升级就绪情况服务运行后，可以通过“组策略”设置注册任何连接 Internet 的 Windows 7 SP1 或较新设备。就这么简单。无需部署代理，Windows Analytics 升级就绪情况的可视化工作流将引导你完成从试点到生产部署的过程。如果需要，可以将数据从 Windows Analytics 升级就绪情况导出到软件部署工具（如 System Center Configuration Manager），以直接指向电脑，并在准备好进行部署的情况下生成集合。</span><span class="sxs-lookup"><span data-stu-id="487e4-p104">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that. Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings. It’s that simple. There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment. If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="487e4-122">设备和应用就绪过程</span><span class="sxs-lookup"><span data-stu-id="487e4-122">Device and App Readiness Process</span></span>

<span data-ttu-id="487e4-p105">设备和应用就绪情况包含四个步骤：1. 清查，2. 确定优先顺序，3. 测试，4. 修正。现在我们来依次了解各步骤。</span><span class="sxs-lookup"><span data-stu-id="487e4-p105">Device and App Readiness compromises four steps: 1. Inventory, 2. Prioritize, 3. Test, 4. Remediate. Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="487e4-p106">1\. 清查</span><span class="sxs-lookup"><span data-stu-id="487e4-p106">1\. Inventory</span></span>

<span data-ttu-id="487e4-131">Windows Analytics 升级就绪情况服务将使用无代理流程跨桌面空间清查计算机、应用程序和 Office 加载项。</span><span class="sxs-lookup"><span data-stu-id="487e4-131">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="487e4-132">它还提供有关经常性访问的 Internet 站点、应用和 Intranet 位置报表，来帮助你稍后进行兼容性测试。</span><span class="sxs-lookup"><span data-stu-id="487e4-132">It also provides reports on highly visited Internet sites, apps and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="487e4-p107">2\. 确定优先顺序</span><span class="sxs-lookup"><span data-stu-id="487e4-p107">2\. Prioritize</span></span>

<span data-ttu-id="487e4-135">借助清单，Windows Analytics 升级就绪情况可帮助你确定组织中最常用的应用和硬件并区分优先次序，以及允许对尽可能多的电脑进行部署要注意的事项，</span><span class="sxs-lookup"><span data-stu-id="487e4-135">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, and what to focus on to unblock as many PCs as possible for deployment,</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="487e4-136">此外，提供帮助评估更新的指导将用于在下一步“测试”中解决问题。</span><span class="sxs-lookup"><span data-stu-id="487e4-136">also providing guidance to help you assess the updates are necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="487e4-p108">3\. 测试</span><span class="sxs-lookup"><span data-stu-id="487e4-p108">3\. Testing</span></span>

<span data-ttu-id="487e4-p109">你会发现大部分已清点的应用程序、驱动程序和加载项都将按原先方式工作。对于有问题的 Windows Analytics 升级就绪情况评估项，它会提供已知信息，包括查找版本更新以解决兼容性问题的位置。可以选择与用户协作来停用和替换这些项，而不是花时间和资源解决非关键型、稀疏部署的应用程序和较旧设备中的复杂问题。</span><span class="sxs-lookup"><span data-stu-id="487e4-p109">You will find that most of the applications, drivers, and add-ins inventoried, will work as-is. For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information, including where to find version updates to resolve compatibility problems. Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="487e4-p110">还可以使用 Windows Analytics 升级就绪情况来评估基于浏览器的兼容性问题，识别由仍使用 ActiveX 控件、浏览器帮助程序对象、VBScript 或其他不受 Microsoft Edge 浏览器支持的旧版技术的用户访问的网站和 Web 应用。用户仍需要对这些站点使用 Internet Explorer 11，你可以使用 Enterprise Mode Site List Manager 将它们添加到[企业模式网站列表](https://docs.microsoft.com/zh-CN/microsoft-edge/deploy/emie-to-improve-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="487e4-p110">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/zh-CN/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="487e4-144">此外，为了帮助你迁移到 Office 365 专业增强版，你可能希望使用 [Readiness Toolkit for Office](https://docs.microsoft.com/zh-CN/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) 来测试加载项和 Microsoft Visual Basic for Applications (VBA) 宏的兼容性。</span><span class="sxs-lookup"><span data-stu-id="487e4-144">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/zh-CN/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="487e4-p111">4\. 修正</span><span class="sxs-lookup"><span data-stu-id="487e4-p111">4\. Remediation</span></span>

<span data-ttu-id="487e4-p112">设备和应用就绪情况的最后阶段是“修正”。在此，你将希望收集所需的软件或驱动程序包；作为部署过程的一部分，你将使用这些包来替代或更新较旧版本。</span><span class="sxs-lookup"><span data-stu-id="487e4-p112">As the final phase of device and app readiness is to ‘remediate’. Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="487e4-p113">在处理列表修正问题时，你将看到越来越多的电脑变为“已准备好部署”。这意味着电脑上的驱动程序和应用都被标记为与你要部署的 Windows 10 目标版本兼容。</span><span class="sxs-lookup"><span data-stu-id="487e4-p113">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

## <a name="continued-use-of-telemetry-tools"></a><span data-ttu-id="487e4-151">继续使用遥测工具</span><span class="sxs-lookup"><span data-stu-id="487e4-151">Continued use of telemetry tools</span></span>

<span data-ttu-id="487e4-p114">Windows Analytics 升级就绪情况不只是帮助你转移到 Windows 10 和 Office 365 专业增强版的工具。一旦在 Windows 10 和 Office 365 上运行桌面，就可以使用它来维护部署，并管理半年度功能更新，以便掌握最新动态。</span><span class="sxs-lookup"><span data-stu-id="487e4-p114">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="487e4-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="487e4-154">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="487e4-155">步骤 2：目录和网络就绪情况</span><span class="sxs-lookup"><span data-stu-id="487e4-155">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)