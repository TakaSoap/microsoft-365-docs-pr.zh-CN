---
title: 步骤 2 - 目录和网络就绪情况
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何评估环境中的目录和网络就绪情况。
ms.openlocfilehash: 78087b7e0c1cb7031954d3a9ac4188b59879db20
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679010"
---
# <a name="step-2-directory-and-network-readiness"></a>步骤 2：目录和网络就绪情况

Ensure your directory and the network are configured and ready to support to your shift to Windows 10 and Microsoft 365 Apps for enterprise. This will require Azure Active Directory Services to be in place for users, and your network must have the capacity to handle both its regular traffic and the movement of potentially vast amounts of data as PCs are upgraded, and users’ files, settings and applications are restored.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>步骤 2：目录和网络就绪情况</strong></p>
<p>Cloud connected services in Microsoft 365 Apps for enterprise and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>目录和网络就绪情况是我们建议的部署过程轮的第二步，重点是 Azure Active Directory 和优化网络。 若要查看完整的桌面部署过程，请访问[桌面部署中心](https://aka.ms/HowToShift)。
>

Directory and Network readiness is fundamental to ensuring a smooth OS and desktop deployment. As with any automated deployment, it is important to ensure your file shares can be reached, and your network will need to be able to support the transfer of very large files, possibly to hundreds or even thousands of PCs at a time.

With your shift to Windows 10 and Microsoft 365 Apps for enterprise you also now need to make sure that cloud-based identity is set up with Azure Active Directory. This is key not only to activating Microsoft 365 Apps for enterprise, it also allows you to take advantage of modern provisioning solutions like Windows Autopilot.

本文将探讨用于准备目录服务、用户和设备权限的工具和解决方案，以便部署到 Windows 10 和 Microsoft 365 企业应用版。

## <a name="adding-azure-active-directory"></a>添加 Azure Active Directory

如果你的组织已使用 Office 365、Exchange Online、Microsoft Intune 或其他 Microsoft Online 服务，表明你已在使用 Azure Active Directory。 如果是这样的话，只需确保你的桌面部署目标用户位于 Azure Active Directory 中，并且已分配许可证。

如果当前未使用 Azure Active Directory，则有[大量资源](https://docs.microsoft.com/azure/active-directory/)可帮助你进行设置。 你也可以通过 Microsoft FastTrack 获得个性化帮助，这是许可证的权益。 可以在[此处](https://fasttrack.microsoft.com)查看有关 Microsoft FastTrack 的更多信息。

在 Azure Active Directory 准备就绪后，你的用户就可以登录并激活 Microsoft 365 企业应用版应用，你也可以使用 Microsoft Intune 或 Windows Autopilot 部署来自动部署应用和策略。

## <a name="network-readiness"></a>网络就绪情况

规划部署时，必须考虑带宽要求。 部署过程中有三个主要部分会对网络产生影响：电脑映像、软件更新、用户个性化设置。 这意味着初始迁移的每台电脑空间可能超过 20 GB，并且每台电脑每月通常需要 1 GB 或更大空间才能保持最新状态。

我们首先探讨这三个主要部分的要求：

### <a name="pc-imaging"></a>电脑成像

对于没有自定义项的 Windows 映像，通常应规划每台电脑 3 GB 的空间，而对于包含应用的自定义映像，可能需要留出 6 GB 或更大空间。 可能还需要考虑驱动程序包，可以是每台电脑几百 MB，有时高达 1 GB。

### <a name="software-updates"></a>软件更新

需要为软件更新规划网络带宽。 Windows 10 和 Microsoft 365 企业应用版使用新的服务模型来分发每月更新和半年更新。 如果你不熟悉此模型，可以在[此处](https://docs.microsoft.com/windows/deployment/update/waas-overview)了解模型的更多信息。

The new servicing model includes Feature Updates for Windows twice a year, Office Semi-Annual Enterprise Channel Updates, and monthly Quality Updates. Feature Updates are typically 2 – 4GB in size, and Office Semi-Annual Enterprise Channel updates are 300 – 400 MB per update. Then there are the monthly Quality Updates. These may range from a few hundred megabytes to over a gigabyte. This is because monthly updates are cumulative, so these increase in size over the servicing lifetime for each Windows 10 version. That said, there are tools that can help reduce the amount of data that must pass over the network to implement updates. We will cover this in more detail below.

### <a name="user-personalization"></a>用户个性化设置

The third component to consider is user personalization. Here you need to plan network bandwidth to accommodate the restoring of user files, their settings, and their applications as part of the PC refresh or replacement process. Together, these items often exceed 20 GB per PC; for some users these may exceed 100 GB.

## <a name="limiting-bandwidth"></a>限制带宽

One way to limit the impact of deployment-related traffic on the network is to throttle it using the BITS (Background Intelligent Transfer Service) setting on clients. BITS uses an Adaptive Bit Rate (ABR) to adjust bandwidth available for deployment purposes; it can be configured on clients using Group Policy.

[关于 BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits)

如果使用 Microsoft Endpoint Configuration Manager（当前分支版本），还可以配置启用 BITS 的分发点或使用 WDS 启用多播。

Throttling specific traffic means that normal network traffic is less impacted by PCs downloading updates and applications. But carving out a certain percentage of bandwidth for these tasks helps ensure productivity isn’t impacted by Windows or Office deployment and processes continue to run as needed, it can worsen deployment-related downtime, with users locked out of their PCs while a deployment runs.

幸好可以使用一些新工具更轻松地管理大规模桌面部署的网络影响，其中包括用于优化可用带宽使用情况的 LEDBAT，以及将部署流量从网络中心和外围移出的对等 (P2P) 选项

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>清理带宽

Windows Server 2019 和 Microsoft Endpoint Configuration Manager（当前分支版本）中支持的低额外时延背景传输 (LEDBAT) 旨在优化传送到 Windows 客户端的网络流量。

[Windows Server 2019 中的十大网络功能：\#9 LEDBAT - 延迟优化背景传输](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

Unlike traditional throttling, LEDBAT can use all available network bandwidth as a background task, instantly yielding bandwidth when other traffic requests it. Unlike BITS there is no delay; everything is automated – no manual tuning or scheduling required, and everything is setup server side. This affords potentially massive performance gains.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>对等选项

Peer-to-Peer options are increasingly being used in Windows 10 migrations, for PC imaging, software updates and user personalization. They are also valuable in facilitating build-to-build upgrades after your initial Windows 10 deployment. Here we will cover several examples to help move Windows 10 and Office-related traffic away from the center of the network, reducing the need for classic throttling approaches, and allowing PCs to find the update files they need on peers in their local network rather than downloading them from a distribution point or the internet.

**BranchCache** can help you download content in distributed environments without saturating the network. It comes in two options: Hosted Cache Mode, which lets you use local servers to cache content, and Distributed Cache Mode (a mode supported in Configuration Manager), which lets clients share already downloaded content with each other.

**对等缓存** Configuration Manager 支持的客户端也可以使用对等缓存。 这使在网络上可以可靠地使用的电脑可以托管内容分发源。 不必启用所有电脑，只需启用连接了可靠网络的主机（例如台式机、小型立式或立式电脑）。 对等缓存甚至可以在安装过程中用于在 Windows PE 阶段运行的部署任务。

注意：BranchCache 和对等缓存是互补的，可以在同一环境中协同工作。

[BranchCache 与对等缓存](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**传递优化**传递优化是另一种对等缓存技术，为 Windows 部署提供基于网络的控制。 Windows 10 传递优化用于更新内置 UWP 应用，还用于从 Microsoft Store 安装应用程序，以及使用 Express Update 进行软件更新。 它在自早期版本的 Windows 10 发布以来已经可用，但最近才与 Microsoft Endpoint Configuration Manager（当前分支版本）集成。 自 Windows 10 版本 1803 开始，新配置选项意味着现在可以独立设置后台更新和前台作业（例如来自应用商店的应用安装）的带宽限制。 Windows 传递优化现在还支持在客户端更新（通过所有受支持的客户端更新通道提供）期间使用 Microsoft 365 企业应用版。 即将开始支持在客户端初始安装期间使用 Windows 传递优化。  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Microsoft 365 企业应用版的其他注意事项**

除了利用传递优化外，还可以采取下列三项措施，它们有助于减少因 Microsoft 365 企业应用版部署而产生的网络负载。

**Binary Delta Compression** Microsoft 365 Apps for enterprise uses Binary Delta Compression to reduce bandwidth consumed by software updates when updating from the most recent release of Microsoft 365 Apps for enterprise to the next release. By only pulling the binary level changes from the previous release, the impact from month-over-month growth of cumulative updates is minimized. This has the potential of saving several hundred megabytes of data, per PC, each month. In order to use this capability though, you cannot skip releases. If you do, then the full cumulative update must be downloaded.

[下载 Microsoft 365 应用版更新](https://docs.microsoft.com/deployoffice/overview-update-process-microsoft-365-apps#download-the-updates-for-microsoft-365-apps)

**Outlook 数据文件** Outlook 通常配置为在本地缓存用户的整个邮箱以供脱机使用。 在任何 Windows 部署中，只有就地升级需要用户的 Outlook 数据文件在升级后自行重建。 这是一个自动执行过程，但 Outlook 邮箱限制通常设置为最多 100 GB，所有用户在本地重新缓存整个邮箱意味着需要进行大量数据传输。 要减少网络负载，可能需要考虑使用组策略来减少“邮件保持脱机”设置。 在 Microsoft 365 企业应用版或 Office 2016 中，Outlook 的默认值设置为 12 个月。 考虑将脱机缓存设置为持续 1 到 6 个月。 更改此设置不会影响联机邮箱的大小，并且在联机时仍可以通过 Outlook 搜索整个邮箱。

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**OneDrive 文件按需下载和已知文件夹移动** OneDrive 是同步和保护电脑和云中其他设备的用户文件的绝佳方式。 使用“已知文件夹移动”，可以强制执行从用户的“桌面”、“文档”和“图片”文件夹到 OneDrive 的文件同步，从而在登录新设备或重置映像的电脑时使这些文件可用。 但请注意，由于“桌面”、“文档”和“图片”位置中保留的文件大小和数量庞大，需要有计划地推出在电脑上启用和实施 OneDrive 的策略。 一种选择是使用组策略网络控件来限制 OneDrive 同步服务使用的带宽。

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[设置已知文件夹移动](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[OneDrive 文件按需下载](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

如果你还没有推出 OneDrive，那么从 Windows 7 转换到 Windows 10 是启用 OneDrive 的绝佳机会，它可以无缝集成 Microsoft 365 企业应用版。 请考虑在完成应用和设备准备工作的同时开始推出。 在开始移动 Windows 映像并通过网络部署应用之前，将先执行文件同步。

## <a name="next-step"></a>后续步骤 

## <a name="step-3-office-and-lob-app-delivery"></a>[步骤 3：Office 和 LOB 应用交付](https://aka.ms/mdd3)

## <a name="previous-step"></a>上一步：

## <a name="step-1-device-and-app-readiness"></a>[步骤 1：设备和应用就绪情况](https://aka.ms/mdd1)

## <a name="feedback"></a>反馈

We'd love to hear your thoughts. Choose the type you'd like to provide:

产品反馈登录以提供文档反馈

Our new feedback system is built on GitHub Issues. Read about this change in our blog post.
