---
title: 步骤 7 - Windows 和 Office 服务
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
description: 了解如何在环境中为实现 Windows 和 Office 服务做好准备。
ms.openlocfilehash: 6f3f5faf4c45829cdb4d2f9ac48ef0c9988ec270
ms.sourcegitcommit: 03828f954b9dddb265f867fa508178ec0d4a6aeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2019
ms.locfileid: "35584558"
---
# <a name="step-7-windows-and-office-servicing"></a>步骤 7：Windows 和 Office 服务

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>步骤 7：Windows 和 Office 服务</strong></p>
<p>Windows 10 和 Office 365 专业增强版都会不断添加新功能，以利用最新的创新来不断提升用户体验和安全性。请了解如何及时获得最新的半年和每月更新、新服务模式的工作原理以及你所拥有的工具和选项。</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Windows 和 Office 服务是我们建议部署过程轮的第七步，其中涉及正在计划的准备半年功能更新的各个方面。。 若要查看完整的桌面部署过程，请访问[桌面部署中心](https://aka.ms/HowToShift)。
>

Windows 10 和 Office 365 专业增强版都引入了新的服务选项、支持模型和更新时间线。 这些更改简化了保持最新功能的过程。 除了这些更新之外，还提供了新的配置选项，以支持满足你需求的服务计划。 了解如何准备半年频道更新，在 Windows 10 和 Office 365 专业增强版中提供新特性和功能，并利用 System Center Configuration Manager (当前分支版本) 中的新功能。

[帮助客户转向 Windows 10 和 Office 365 专业增强版](https://www.microsoft.com/en-us/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>更新类型

更新分为两个主要类别：功能更新，然后是质量和安全更新，其中包含累积安全性、可靠性和 bug 修复。 在频率方面，Windows 和 Office 都提供了一个半年频道，在每年的 3 月和 9 月发布两次新功能，而质量和安全更新则是每月发布一次。 此外，Office 365 应用的独特之处在于，我们提供完全支持的每月频道更新，同时包含新功能和质量更新。

如果你习惯了桌面 OS 和应用更新之间的更长的周期，你可能会思考；

  - 更新是否兼容？

  - 我需要继续对用户进行重新培训吗？

  - 有哪些风险？

为了回答这些问题以及更频繁地交付新功能的基本原理，我们将阐明此方法的一些优点

### <a name="feature-update-benefits"></a>功能更新优势

首先，我们已经弃用了过去的模式，该模式每三年会引发一波巨大的变革浪潮，而现在每年进行两次功能更新，每次更新的增量变化较小。为什么？除了快速演进的安全威胁之外，技术趋势也在快速发展，此做法将保持最新的体验和防护状态。例如，一些与安全相关的更新无法仅通过每月安全更新或反病毒签名文件来提供；它们可能是低级别的变更平台，比如基于虚拟化的安全性。


  [Windows 即服务的快速指南](https://docs.microsoft.com/zh-CN/windows/deployment/update/waas-quick-start)


  [通过使用 Windows 10 安全功能来缓解威胁](https://docs.microsoft.com/zh-CN/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>累积更新模型优势

第二次交付质量和安全更新作为一个累积的更新包修正了过去的许多问题。过去，每月你可能有时会从十几个或更多更新中针对 Windows 和 Office 进行选择。正如你所能想象的，这将创建一个几乎不可能的支持测试矩阵集。另外，如果安装的 Windows 或 Office 版本是一年前或更旧的版本，可能需要几个小时甚至几天的时间来应用自该版本发布以来交付的所有更新。

有了累积模型，你所获得的更新始终次于最新更新，为此你需要部署的每月更新的数量就会减少。每个更新都建立在前几个月的更新之上，并且包含全部所需的最新修复程序。当电脑关闭几个月后，累积更新会特别有用，因为它们在存储中等待被重新分配给其他用户。

### <a name="expanded-validation-of-updates"></a>扩展更新验证

另一个优点是，在我们推出更新以实现广泛部署之前，我们会首先通过 [Office](https://products.office.com/zh-CN/office-insider?tab=Windows-Desktop) 和 [Windows](https://insider.windows.com/en-us/) 的预览体验计划发布内部版本，这让我们可以在广泛发布更新之前收集诊断数据和反馈。 目前，预览体验计划对所有人开放，这样可以预先了解更新。 当发布更新时，我们将从上百万个配置中接收诊断数据，因此当我们推出更新时，质量更易于预测

还有一点，由于 Office 365 专业增强版预览体验版本反映了每月频道更新，因此如果针对 Office 使用半年频道来提供每年两次的功能更新（Windows 同样如此），则可以提前验证这些版本，并使用半年频道定向发布。

### <a name="supporting-management-tools"></a>支持管理工具

我们还考虑了如何无缝部署更新。System Center Configuration Manager (当前分支版本) 会经常更新，以支持推出这些 Windows 和 Office 更新，以及任何新功能。


  [使用 System Center Configuration Manager 部署 Windows 10 更新](https://docs.microsoft.com/zh-CN/windows/deployment/update/waas-manage-updates-configuration-manager)


  [使用 Configuration Manager 管理 Office 365 专业增强版](https://docs.microsoft.com/zh-CN/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Windows 和 Office 频道概述

Windows 10 提供三个服务频道：

- 
  [
  **Windows 预览体验计划**](https://docs.microsoft.com/zh-CN/windows/deployment/update/waas-overview#windows-insider)适合于组织用于对下一次功能更新中所含的功能进行测试和提供反馈
- **半年度频道**每年提供两次的功能更新发布提供新功能
- **长期服务频道**专用于需要更长服务选项的特殊设备

Office 365 提供四个服务频道：

- 
  [
  **Office 预览体验计划**](https://support.office.com/zh-CN/article/What-is-Office-Insider-f4208185-b63a-4b68-9c7a-9a32d2411c16)适合于组织用于对仍在开发中的最新 Office 特性和功能进行测试并提供反馈
- **每月频道**用于为在最新 Office 功能推出后将其立即提供给用户
- **半年频道**只每年提供两次新功能和新特性
- **半年频道（定向）** 是 Office 的完全支持内部版本，支持试点用户和应用程序兼容性测试人员测试和验证下一个半年频道

有关 Windows 和 Office 服务频道的详细信息，请查阅以下文档：

- 
  [Windows 即服务概述](https://docs.microsoft.com/zh-CN/windows/deployment/update/waas-overview#servicing-channels)
- 
  [Office 365 专业增强版的更新频道概述](https://docs.microsoft.com/zh-CN/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a>分阶段部署更新

现在我们换个话题，讨论如何推出这些更新。对于任何版本，我们的建议是至少三个 IT 部署阶段 – 验证、试验和广泛生产部署。一旦在 Windows 10 和 Office 365 专业增强版上启动并运行，你便会使用每月服务来保持最新的关键安全和质量更新，然后切换到半年服务以提供新功能。

### <a name="monthly-updating"></a>每月更新

服务模型旨在让你选择将新功能的发布限制在每年两次，如果需要的话，甚至可以跳过半年更新，继续接收质量和安全更新。如上所述，每月更新的累积特性意味着每个月各更新大小的增加。

#### <a name="express-updates"></a>快速更新

使用 Windows 中名为“快速更新”的技术和 Office 中的二进制增量压缩可以显著减少下载大小。在这两种方法中，更新引擎比较电脑上的内容，并且只查找其中需要更新的内容的差别。

[Windows 10 质量更新说明和增量更新结语](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

适用于企业的 Windows 更新和 Windows Server Update Services 长期以来支持快速更新，但我们现在已将该支持扩展到 System Center Configuration Manager (当前分支版本)，这样它也可以使用快速更新。

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>二进制增量压缩

只有在从 Office 365 专业增强版的最新版本进行更新时，才能在 Office 中使用二进制增量压缩，因此，要使用这种方法，需要从之前的版本进行更新，而且不能跳过更新。

Windows 和 Office 更新通道可以通过 Configuration Manager 使用标准审批和目标流程来管理。此外，还可以在 Office 和 Windows 中使用策略设置来强制使用更新通道，以及相关设置。

### <a name="semi-annual-updates"></a>半年更新

以上便是每月更新的注意事项，现在让我们继续讨论更大规模的半年更新。

正如我们在“设备和应用就绪情况”中所介绍的，你将希望使用我们在“部署过程轮”步骤 1 中设置的相同准备工具开始准备这些更大的更新。

至于工具，你可以使用适用于企业的 Windows 更新中的策略设置、通过 System Center Configuration Manager (当前分支版本) 、Windows Server Update Services (WSUS) 进行软件更新管理或者通过 Microsoft Intune 更新策略设置。如果你担心网络带宽，请参见“步骤 2：目录和网络就绪情况”，了解通过交付优化和其他对等缓存技术来减少网络流量的选项。

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)


  [Windows 半年频道](https://docs.microsoft.com/zh-CN/windows/deployment/update/waas-overview#semi-annual-channel)


  [Office 365 专业增强版的半年频道](https://docs.microsoft.com/zh-CN/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>升级任务序列

通过标准软件更新管理例程来安装更大的功能更新是受支持的选项，但是许多组织将会选择使用 System Center Configuration Manager (当前分支版本) 中的升级任务序列或 Microsoft Deployment Toolkit。

可通过任务序列在安装功能更新之前创建自定义检查或任务，并且可以在更新安装本身完成之后执行自定义任务 – 更新后任务可能包括更新期间暂停服务（如果需要）、驱动程序安装和更换、应用程序升级或任务栏和 Windows 10“开始”菜单的个性化设置。

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

如果已经在使用任务序列将 Windows 7 计算机迁移到 Windows 10，并且非常精通这些工具，那么这是启动和提供最终控制的理想位置。虽然可以为整个升级使用单个任务序列，但是组织使用两个任务序列是很常见的。一个任务序列用于确保计算机已经准备好进行升级，它在目标计算机上以静默方式预先暂存所有所需的安装文件，另一个任务序列则用于实际升级。这种方法可确保用户生产力受到较小影响。


  [在 Configuration Manager 中创建升级 OS 的任务序列](https://docs.microsoft.com/zh-CN/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>对功能更新的半年频道支持

[如 2018 年 9 月所宣布](https://www.microsoft.com/en-us/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)，半年频道更新的支持时间线将使用以下模型。

  - 从版本 1607 开始，所有目前支持的 Windows 10 企业版和教育版功能更新将自初始发布之日起提供 30 个月的支持。

  - 从 1809 开始，所有目标定在 9 月的未来功能更新将自发布之日起提供 30 个月的支持。

  - 从 1903 开始，所有目标定在 3 月的未来功能更新将自发布之日起继续提供 18 个月的支持。

  - Office 365 专业增强版的半年更新将继续支持 18 个月

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>任务序列之外的其他安装自动化选项

如果不使用升级任务序列，现在可以在预安装阶段（在安装程序运行其兼容性检查之前）或者在预提交阶段（在应用升级之前），在功能更新期间运行自定义操作或应用驱动程序文件。


  [Windows 10 安装版本 1803 中的新增功能](https://docs.microsoft.com/zh-CN/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>后续步骤 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a>[步骤 8：用户通信和培训](https://aka.ms/mdd8)

## <a name="previous-step"></a>上一步 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[步骤 6：OS 部署和功能更新](https://aka.ms/mdd6)