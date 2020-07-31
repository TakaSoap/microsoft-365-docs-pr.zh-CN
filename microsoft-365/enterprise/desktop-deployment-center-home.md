---
title: 桌面部署中心
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 08/14/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 桌面部署中心概述。
ms.openlocfilehash: 3559a32db71d2cceaf3ab4dc67701d5f5f00e7fe
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528104"
---
# <a name="desktop-deployment-center"></a><span data-ttu-id="c1b58-103">桌面部署中心</span><span class="sxs-lookup"><span data-stu-id="c1b58-103">Desktop Deployment Center</span></span>

<span data-ttu-id="c1b58-104"><strong>从 Windows 7 升级到 Windows 10</strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-104"><strong>Upgrading from Windows 7 to Windows 10</strong></span></span>
<p><span data-ttu-id="c1b58-105">Windows 7 扩展支持已于 2020 年 1 月 14 日结束。</span><span class="sxs-lookup"><span data-stu-id="c1b58-105">Windows 7 extended support ended on January 14, 2020.</span></span> <span data-ttu-id="c1b58-106">就地从 Windows 7 升级到 Windows 10 是部署速度最快的方法。</span><span class="sxs-lookup"><span data-stu-id="c1b58-106">In-place upgrade from Windows 7 to Windows 10 is the fastest method to deploy.</span></span> <span data-ttu-id="c1b58-107">可使用 Microsoft Endpoint Configuration Manager <a href="https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-manual">升级单台电脑</a>或<a href="https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated">升级数以千计的电脑</a>。</span><span class="sxs-lookup"><span data-stu-id="c1b58-107">You can <a href="https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-manual">upgrade a single PC</a> or <a href="https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated">upgrade thousands of PCs using Microsoft Endpoint Configuration Manager</a>.</span></span> <span data-ttu-id="c1b58-108">无需专注于应用的交付、文件迁移、自定义映像或通过就地升级启用基于云的服务。</span><span class="sxs-lookup"><span data-stu-id="c1b58-108">You don’t need to focus on app delivery, file migration, custom imaging, or enabling cloud-based services with in-place upgrades.</span></span> <span data-ttu-id="c1b58-109">可以使用已有的工具升级现有电脑，并关注升级的以下部署步骤：</span><span class="sxs-lookup"><span data-stu-id="c1b58-109">You can use tools you already have to upgrade existing PCs and focus on the following deployment steps for upgrades:</span></span> </p>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" width="36" height="36" alt="Upgrade ConfigMgr" /> | <span data-ttu-id="c1b58-110">**[将 ConfigMgr 升级到当前分支](https://docs.microsoft.com/microsoft-365/enterprise/step-2-directory-and-network-readiness)**</span><span class="sxs-lookup"><span data-stu-id="c1b58-110">**[Upgrade ConfigMgr to Current Branch](https://docs.microsoft.com/microsoft-365/enterprise/step-2-directory-and-network-readiness)**</span></span> <p><span data-ttu-id="c1b58-111">使用 Configuration Manager 的组织的目录和网络就绪情况的一部分</span><span class="sxs-lookup"><span data-stu-id="c1b58-111">Part of Directory and Network Readiness for organizations using Configuration Manager</span></span></p> | <img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" width="36" height="36" alt="Device and App Readiness" /> | <span data-ttu-id="c1b58-112">**[验证设备和应用就绪情况](/microsoft-365/enterprise/step-1-device-and-app-readiness)**</span><span class="sxs-lookup"><span data-stu-id="c1b58-112">**[Validate device and app readiness](/microsoft-365/enterprise/step-1-device-and-app-readiness)**</span></span> <p><span data-ttu-id="c1b58-113">设备和应用就绪情况的一部分；可通过桌面应用保证获得帮助</span><span class="sxs-lookup"><span data-stu-id="c1b58-113">Part of Device and App Readiness; help is available via Desktop App Assure</span></span></p> | <img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" width="36" height="36" alt="Upgrade Windows 7 PCs" /> | <span data-ttu-id="c1b58-114">**[将 Windows 7 电脑升级到 Windows 10](/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated)**</span><span class="sxs-lookup"><span data-stu-id="c1b58-114">**[Upgrade Windows 7 PCs to Windows 10](/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated)**</span></span> <p><span data-ttu-id="c1b58-115">设备和应用就绪情况的一部分；可通过桌面应用保证获得帮助</span><span class="sxs-lookup"><span data-stu-id="c1b58-115">Part of Device and App Readiness; help is available via Desktop App Assure</span></span></p> |

<img align="middle" src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-2.png" alt="Desktop Deployment Wheel" height="450" width="802" align="middle" style="background-color: #fff;" />


<span data-ttu-id="c1b58-116">请按照以下步骤来规划和执行大规模的 Windows 10 和 Microsoft 365 企业应用版部署。</span><span class="sxs-lookup"><span data-stu-id="c1b58-116">Follow the steps below to plan and carry out your large-scale deployment of Windows 10 and Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="c1b58-117">下列每个步骤都是总体规划和部署过程的一部分，而且这些步骤通常都是在阶段性部署中同时进行。</span><span class="sxs-lookup"><span data-stu-id="c1b58-117">Each step below is part of the overall planning and deployment process with steps typically running in parallel to each other in a phased deployment.</span></span> <span data-ttu-id="c1b58-118">下载免费的[桌面部署和管理实验室工具包](https://aka.ms/howtoshiftlabs)，以获取有关部署过程中突出显示的工具的实操培训。</span><span class="sxs-lookup"><span data-stu-id="c1b58-118">Download the free [Desktop Deployment and Management Lab Kit](https://aka.ms/howtoshiftlabs) for hands-on training with the tools highlighted in the deployment process.</span></span> <span data-ttu-id="c1b58-119">你也可以[寻求帮助](https://aka.ms/mddhelp)，以通过 Microsoft 合作伙伴和 FastTrack 服务进行桌面部署。</span><span class="sxs-lookup"><span data-stu-id="c1b58-119">You can also [find help](https://aka.ms/mddhelp) for your desktop deployment from Microsoft partners and FastTrack services.</span></span>

<br>

<table>
<tr class="even">
<td><a href="https://aka.ms/mdd0"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-120"><strong><a href="https://aka.ms/mdd0">入门：人员、流程和技术指导</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-120"><strong><a href="https://aka.ms/mdd0">Getting Started: People, Process and Technology Guidance</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-121">了解 Windows 10 和 Microsoft 365 企业应用版的好处、相比之前的部署的主要变化和注意事项以及最佳做法，以确保顺利过渡到 Windows 10 和 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="c1b58-121">Discover the benefits of moving to Windows 10 and Microsoft 365 Apps for enterprise, major changes and considerations versus previous deployments, and best practices to ensure a smooth transition to Windows 10 and Microsoft 365 Apps for enterprise.</span></span></p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="130" width="231" /></a></td>
</tr>
<tbody>
<tr class="odd">
<td><a href="https://aka.ms/mdd1"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-122"><strong><a href="https://aka.ms/mdd1">步骤 1：设备和应用就绪情况</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-122"><strong><a href="https://aka.ms/mdd1">Step 1: Device and App Readiness</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-123">首先为桌面部署项目配备设备和应用清单，确定进行操作的优先顺序，测试按优先顺序排列的应用和设备，然后针对部署所需的先决条件进行查漏补缺。</span><span class="sxs-lookup"><span data-stu-id="c1b58-123">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you need to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd2"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-124"><strong><a href="https://aka.ms/mdd2">步骤 2：目录和网络就绪情况</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-124"><strong><a href="https://aka.ms/mdd2">Step 2: Directory and Network Readiness</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-p103">Microsoft 365 企业应用版中的云连接服务和 Windows Autopilot 等新部署选项都需要安装 Azure Active Directory。在将 Windows 映像、应用、驱动程序和相关文件移动到电脑时，还需要规划网络和连接。请了解新工具和部署选项如何减少和简化网络流量。</span><span class="sxs-lookup"><span data-stu-id="c1b58-p103">Cloud connected services in Microsoft 365 Apps for enterprise and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</span></span></p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><a href="https://aka.ms/mdd3"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-128"><strong><a href="https://aka.ms/mdd3">步骤 3：Office 和 LOB 应用交付</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-128"><strong><a href="https://aka.ms/mdd3">Step 3: Office and LOB App Delivery</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-129">确保应用已打包，且可进行自动安装。</span><span class="sxs-lookup"><span data-stu-id="c1b58-129">Ensure your apps are packaged and ready for automated installation.</span></span> <span data-ttu-id="c1b58-130">了解 Microsoft 365 企业应用版随附的即点即用打包技术提供的配置、交付和持续更新 Office 应用的新方法。</span><span class="sxs-lookup"><span data-stu-id="c1b58-130">Learn how Click-to-Run packaging with Microsoft 365 Apps for enterprise gives you new options to configure, deliver, and keep your Office apps up-to-date.</span></span></p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd4"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-131"><strong><a href="https://aka.ms/mdd4">步骤 4：用户文件和设置</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-131"><strong><a href="https://aka.ms/mdd4">Step 4: User Files and Settings</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-132">刷新或更换电脑时，可以通过自动执行用户状态备份和还原来节省时间。</span><span class="sxs-lookup"><span data-stu-id="c1b58-132">When refreshing or replacing PCs, save time by automating user state backup and restore.</span></span> <span data-ttu-id="c1b58-133">针对云文件同步的新选项使你能够将每个用户的桌面、文档和图片文件夹强制同步到 OneDrive，以便从新 Windows 安装上无缝访问文件。</span><span class="sxs-lookup"><span data-stu-id="c1b58-133">New options for cloud file sync allow you to enforce per user sync of Desktop, Documents, and Pictures folders to OneDrive for seamless file access from new Windows installs.</span></span></p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><a href="https://aka.ms/mdd5"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-134"><strong><a href="https://aka.ms/mdd5">步骤 5：安全性和合规性注意事项</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-134"><strong><a href="https://aka.ms/mdd5">Step 5: Security and Compliance Considerations</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-135">使用 Windows 10 和 Microsoft 365 企业应用版，可通过新方法来保护数据、设备和用户，并快速检测和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="c1b58-135">Windows 10 and Microsoft 365 Apps for enterprise provide new ways to protect your data, devices and users, and quickly detect and respond to threats.</span></span> <span data-ttu-id="c1b58-136">此外，还请了解在迁移到 Windows 10 时，如何处理与磁盘加密、防恶意软件应用和策略相关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="c1b58-136">Also, learn how to deal with common problems associated with disk encryption, anti-malware apps, and policies when moving to Windows 10.</span></span></p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd6"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Step 6" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-137"><strong><a href="https://aka.ms/mdd6">步骤 6：OS 部署和功能更新</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-137"><strong><a href="https://aka.ms/mdd6">Step 6: OS Deployment and Feature Updates</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-138">基于任务序列的部署用于在裸机安装、电脑刷新和电脑更换情况下自动完成大规模的阶段性部署。</span><span class="sxs-lookup"><span data-stu-id="c1b58-138">Task sequence-based deployment is used to automate large scale, phased deployment for bare metal installs, PC refresh, and PC replacement.</span></span> <span data-ttu-id="c1b58-139">升级任务序列还可帮助你及时了解主要的半年更新。</span><span class="sxs-lookup"><span data-stu-id="c1b58-139">Upgrade task sequences will also help you stay current with major semi-annual updates.</span></span> <span data-ttu-id="c1b58-140">Windows Autopilot 是新增的功能，可现代化新设备和现有设备的成像。</span><span class="sxs-lookup"><span data-stu-id="c1b58-140">Windows Autopilot is a recent addition that modernizes imaging new and existing devices.</span></span></p></td>
<td><a href="https://aka.ms/ddev6" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-19.png" alt="Step 6" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><a href="https://aka.ms/mdd7"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-141"><strong><a href="https://aka.ms/mdd7">步骤 7：Windows 和 Office 服务</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-141"><strong><a href="https://aka.ms/mdd7">Step 7: Windows and Office Servicing</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-142">Windows 10 和 Microsoft 365 企业应用版都会不断添加新功能，以利用最新的创新来不断提升用户体验和安全性。</span><span class="sxs-lookup"><span data-stu-id="c1b58-142">Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations.</span></span> <span data-ttu-id="c1b58-143">请了解如何及时获得最新的半年和每月更新、新服务模式的工作原理以及你所拥有的工具和选项。</span><span class="sxs-lookup"><span data-stu-id="c1b58-143">Learn how to stay current with semi-annual and monthly updates, how the new servicing model works, and the tools and options you have.</span></span></p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><a href="https://aka.ms/mdd8"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-11.png" alt="Step 8" height="144" width="144" /></a></td>
<td><p><span data-ttu-id="c1b58-144"><strong><a href="https://aka.ms/mdd8">步骤 8：用户通信和培训</a></strong></span><span class="sxs-lookup"><span data-stu-id="c1b58-144"><strong><a href="https://aka.ms/mdd8">Step 8: User Communication and Training</a></strong></span></span></p>
<p><span data-ttu-id="c1b58-p109">在将你的电脑切换至 Windows 10 和 Microsoft 365 企业应用版后，确保你的用户了解新体验和新的工作方式。请了解如何利用用户采用帮助（通过 Microsoft FastTrack）、培训材料和通信模板，以及如何通过新方法来监控用户的接受和使用情况。</span><span class="sxs-lookup"><span data-stu-id="c1b58-p109">Make sure your users are informed about new experiences and new ways of working as you shift your PCs to Windows 10 and Microsoft 365 Apps for enterprise. Learn how to take advantage of user adoption assistance with Microsoft FastTrack, training materials and communication templates, as well as new ways to monitor user acceptance and usage.</span></span></p></td>
<td><a href="https://aka.ms/ddev8" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-21.png" alt="Step 8" height="130" width="231" /></a></td>
</tr>
</tbody>
</table>
