---
title: 步骤 3 - Office 和 LOB 应用交付
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
description: 了解如何交付 Office 和 LOB 应用。
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866053"
---
# <a name="step-3-office-and-lob-app-delivery"></a>步骤 3：Office 和 LOB 应用交付

现在可以准备好交付 Office 和业务线应用了。可以通过很多方法执行此操作，包括一些令人欣喜不已的新选项。花些时间回顾这些方法并选择最佳方法来满足当前需求。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>步骤 3：Office 和 LOB 应用交付</strong></p>
<p>确保应用已打包，且可进行自动安装。了解如何使用 Office 365 专业增强版的即点即用打包，通过新方法来配置、交付和持续更新 Office 应用。</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>Office 和 LOB 应用交付是建议的部署流程轮的第三步，其中涵盖了 Office 和 LOB 安装和管理选项。为了成功部署，请勿跳过前两步。若要查看完整的桌面部署流程，请访问[新式桌面部署中心](https://aka.ms/HowToShift)。
>

虽然一些应用程序只能提供 32 位或 64 位编译版本，但另一些应用程序（包括 Office 365 专业增强版）同时提供 32 位和 64 位本机编译代码。要做出的最大决定之一是，要部署哪个版本。为了利用新设备上的额外计算能力和 RAM，建议使用 64 位版本。不过，在开始前，需要先确定可能会遇到的任何加载项或文件相关兼容性挑战。为此，可能需要在继续操作前，重新转到第 1 步“设备和应用就绪情况”。

如果没有任何障碍，我们建议部署 64 位版本的所有应用，包括 Microsoft Office。64 位本机编译应用提供最佳性能，并且是最经得起未来考验的选择。

在 Windows 上安装应用有很多方法和模型，让我们看看你的交付选项。

[Windows 10 应用程序管理](https://docs.microsoft.com/zh-CN/windows/application-management/)

## <a name="msi-based-deployments"></a>基于 MSI 的部署

对于业务线应用，你可能会使用基于 MSI 的包或可执行文件，并将应用程序安装为 OS 部署任务序列的一部分。Windows 10 会继续使用这些包

像 System Center Configuration Manager 和 Microsoft Intune 这样的软件部署工具也会被优化以交付 MSI 打包的应用。一旦在 Windows 10 上验证了应用，就可以使用 System Center Configuration Manager (Current Branch) 来交付应用。如果使用 Microsoft Intune 的公司门户，可以扩展可供组织使用的 IT 认可的应用选择，以包括最新应用程序，并且用户可以自行选择他们需要的应用。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>电脑成像

另一种流行的应用交付方法是电脑成像。在这种情况下，应用程序要么通过任务序列安装，要么在示例电脑上手动安装，然后用预先安装的所需应用程序捕获系统映像。在预配新电脑时，用于构建和捕捉的成像方法可以节省时间，但要记住，映像中的操作系统和应用程序可能很快就会过时。Windows 10 和 Office 365 专业增强版的累积更新模型有助于解决这个问题，但并不能完全消除。这就是为什么我们建议精简映像方法，在部署时，应用程序从映像外部安装。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

如果你想在映像中包含 Office 365 专业增强版，请记住，此操作使用基于用户的激活；系统管理员不能预先将其激活。使用 Office 部署工具在正在成像的设备上预安装 Office，并跳过用户登录。用户可以登录，向其分配激活，并利用首次使用时利用登录的其他功能。

[创建安装操作系统的任务序列](https://docs.microsoft.com/zh-CN/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a>即点即用 

Office 365 专业增强版使用即点即用安装，在即将发布的 Windows Office 2019 的每个版本中，都可以用即点即用取代基于 MSI 的打包。它提供了许多优势，包括更快的安装速度、运行速度更快、高效更新和干净卸载

通过即点即用交付的程序在计算机的虚拟应用程序环境中执行，因此与其他应用程序共存而不会发生冲突；它们还占用了大约一半的磁盘空间，就像基于 MSI 的包那样。而且由于即点即用支持程序流，首先通过传输最常用的功能，用户可以在几分钟内开始使用 Office 应用程序，而无需等待 Office 完全安装。这不仅对于初始部署至关重要，它还意味着更新可以在后台以无缝方式进行流式处理，对用户的影响很小。

如果使用 System Center Configuration Manager，仍然可以使用它来广泛部署 Office 365 专业增强版。System Center Configuration Manager (Current Branch) 为更新的 Office 自定义工具、安装时的即点即用包自定义，以及软件更新管理后安装提供本机支持。

[Office 365 专业增强版部署指南](https://docs.microsoft.com/zh-CN/deployoffice/deployment-guide-for-office-365-proplus)

[在升级到 Office 365 专业增强版时删除 Office 的现有 MSI 版本](https://docs.microsoft.com/zh-CN/deployoffice/upgrade-from-msi-version)

[使用 Configuration Manager 管理 Office 365 专业增强版](https://docs.microsoft.com/zh-CN/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[使用 Microsoft Intune 将 Office 365 应用分配到 Windows 10 设备](https://docs.microsoft.com/zh-CN/intune/apps-add-office365)

## <a name="browser-based-apps"></a>基于浏览器的应用程序

为了确保基于浏览器的应用程序能够像预期那样继续工作，需注意一些事项。如果你有特定的网站和应用，你知道它们与 Microsoft Edge 存在兼容性问题，则可以使用企业模式网站列表，这样网站就会使用 Internet Explorer 11 自动打开。

此外，如果你知道内部网站不能正常使用 Microsoft Edge，则可以设置所有内部网站自动使用 Internet Explorer 11 打开。该过程使用 XML 文件来管理 IE11 是否用于每个网站，使用组策略来强制实施设置。

到目前为止，我们已经介绍了众所周知的部署方法。但是，你可能想要考虑两种新的应用部署方法。

[什么是企业模式](https://docs.microsoft.com/zh-CN/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store 

适用于企业的 Microsoft Store 提供了一种灵活的方法来发现、获取、管理免费和付费应用，并将其大规模分发到 Windows 10 设备。作为 IT 管理员，可将选定的 Microsoft Store 应用以及你自己的自定义应用发布到自己的专用应用商店，并根据需要分配和重新使用许可证。你的用户只会定向到此应用商店，因此只能查找和安装批准后的应用。

应用商店应用可以在本机构建为 UWP 应用，也可以使用桌面桥重新打包应用商店的现有应用，并为 Windows 10 添加新式体验。除了你用来增强 Windows 10 体验的代码之外，应用程序保持不变，并继续以完全信任的用户模式运行。

## <a name="msix-containerization"></a>MSIX 集装化

应用程序打包的一个新选项是 MSIX。MSIX 使用 Windows 提供的集装化技术，将即点即用、UWP 和 MSI 打包的最佳方面结合在一起。有了将现有安装程序（如 EXE、MSI、APPV 和 APPX）直接迁移到 MSIX 的工具，将看到 MSIX 集装化为目前使用的许多安装技术提供了统一路径。MSIX 支持包含在当前版本的 Windows 中：任何运行 Windows 10 RS5 或更高版本的设备都包含安装和运行 MSIX 打包应用所需的一切内容。Windows 10 动态集成它接收到的 MSIX 容器，同时将应用程序与操作系统相分离。

集装化指的是完全卸载和删除包，不像今天的许多 MSI 和基于 EXE 的包，它们可能会在系统上有残留项。它还意味着只需要标准的用户凭证即可安装应用程序 - 不需要使用管理员凭证来安装 MSIX 容器。此外，MSIX 容器的更新效率更高。当更新发布时，使用块级别差异意味着只应用新的二进制文件，从而减少更新有效负载，以便实现更快部署而减少网络带宽的使用。

有关 MSIX 的详细信息，请访问 [MSIX 技术社区网站](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)

## <a name="next-step"></a>后续步骤

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[步骤 4：用户文件和设置](https://aka.ms/mdd4)

## <a name="previous-step"></a>上一步

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[步骤 2：目录和网络就绪情况](https://aka.ms/mdd2) 