---
title: 步骤 4 - 用户文件和设置迁移
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何迁移用户文件和设置。
ms.openlocfilehash: a35874121c348dff15a0959aa766b405c75b3d65
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "34814563"
---
# <a name="step-4-user-files-and-settings-migration"></a>步骤 4：用户文件和设置迁移

将用户文件和设置移至新机或刷新后的电脑的流程最为关键；只能成功，不能失败。 你可以对每台电脑进行手动迁移，也可以选择几种方法之一来自动执行该流程。 无论选择哪种迁移方法，都需要解决以下三个问题：用户文件传输、文件设置，以及管理 Windows 10 的“开始”和任务栏布局。

![](media/step-4-user-files-and-settings-migration-media/step-4-user-files-and-settings-migration-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="135" width="135" /></td>
<td><p><strong>步骤 4：用户文件和设置</strong></p>
<p>刷新或更换电脑时，可以通过自动执行用户状态备份和还原来节省时间。针对云文件同步的新选项使你能够将每个用户的桌面、文档和图片文件夹强制同步到 OneDrive，以便从新 Windows 安装上无缝访问文件。</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>虽然在移至 Office 365 专业增强版后可以继续使用过去使用的迁移过程，但我们建议使用 OneDrive 的“已知文件夹移动”（见下方）。 若要查看的完整桌面部署过程，请访问[桌面部署中心](https://aka.ms/HowToShift)。
>

大规模部署最棘手且通常大多数手动执行的任务之一是，转移用户文件和设置。本文将介绍把用户迁移到新电脑、已刷新电脑和重置映像电脑时可用的选项。

## <a name="manual-migration"></a>手动迁移

对于在移动到新电脑或新版本的 Windows 时决定要保留哪些内容，一些用户可能希望保留所有内容，其他人可能想要利用这个机会来清理他们的驱动器。因此，一些 IT 部门选择手动处理用户文件迁移，有时采用的方法是让支持团队访问用户；有时通过设置让用户将其电脑置于支持团队的支持中心。无论是哪种方式，用户都可以参与决定要转移和要放弃的内容。

这是否是组织中的选项将取决于规划的迁移规模。很明显，它仅限于与用户直接合作、理解他们的需求、将文件复制到他们的新电脑或最新更新电脑所涉及的时间和物理。

如果选择手动迁移，可能需要评估是否能够在 Windows 7 支持期截止的 2020 年 1 月之前完成任务。如果不确定，请查看使用以下自动化选项之一，或请求更多人员的帮助。

## <a name="automated-migration-using-usmt"></a>使用 USMT 自动化迁移 

对于大规模部署，可以使用基于任务序列的部署自动化工具（例如 System Center Configuration Manager 或 Microsoft Deployment Toolkit (MDT)）来自动化大部分过程。这两个解决方案使用用户状态迁移工具 (USMT) 作为其端到端部署过程的一部分。USMT 属于 [Windows 评估和部署工具包 (Windows ADK)](https://docs.microsoft.com/zh-CN/windows-hardware/get-started/adk-install)

USMT 捕获用户帐户、用户文件、操作系统设置和应用程序设置，并将它们迁移到新的 Windows 安装。它还向 IT 管理员提供要迁移的内容的精准控制，并且可以排除不需要的文件类型 - 例如音频和视频文件或可执行文件。

在迁移过程中，将需要有足够的服务器存储空间可用，以充当临时迁移存储。USMT 在此提供两个重要功能。首先，它可以估计每台电脑所需的存储量。其次，它允许对迁移存储进行加密，从而在数据存储在文件服务器上时减少数据被破坏的风险。

当你执行电脑刷新而不重新格式化主 Windows 分区，还可以选择使用 USMT 的硬链接迁移存储。当删除和刷新旧操作系统和应用程序时，该过程将保留电脑上的用户状态。由于还原过程来自同一个本地分区，该选项提供了显著的性能改进，并减少了网络流量。

[用户状态迁移工具 (USMT) 概述](https://docs.microsoft.com/zh-CN/windows/deployment/usmt/usmt-overview)

## <a name="onedrive-known-folder-move"></a>OneDrive 已知文件夹移动

如果用户在 OneDrive 上，或者你将添加 OneDrive 作为此部署的一部分，则可以使用新选项。使用云来同步用户文件，OneDrive“已知文件夹移动”功能提供本地基于网络的文件迁移选项所没有的灵活性。如果在迁移之前启用，它将在新的或刷新的电脑上提供安全访问，并消除在自己的服务器上创建临时迁移存储的需要。此外，它也有可能对用户完全透明。

[将 Windows 已知文件夹重定向和移动到 OneDrive](https://docs.microsoft.com/zh-CN/onedrive/redirect-known-folders)

如果已经在使用 OneDrive，你将知道用户可以选择要从 OneDrive 或 SharePoint 同步到其设备的文件夹和位置，但这实际上会给最终用户带来设置负担。通过“已知文件夹移动”，可以在用户配置文件中锁定文档、桌面和图片文件夹，并在 OneDrive 中实施全面保护。用户可以自行操作，或者，对于此重要场景而言，你可以[使用组策略设置来执行此操作](https://docs.microsoft.com/en-us/onedrive/use-group-policy?redirectSourcePath=%252fen-us%252farticle%252fUse-Group-Policy-to-control-OneDrive-sync-client-settings-0ecb2cf5-8882-42b3-a6e9-be6bda30899c)。

使用“已知文件夹移动”，用户不会改变其工作流 – 在完成与 OneDrive 的同步之前、同步期间和同步之后，都没有任何变化。通过组策略，你甚至可以选择是否通知用户有关其文档、图片和桌面在 OneDrive 中受到保护的信息。如果选择不通知，这一切都将在后台默默发生。用户只有在使用新电脑或刷新电脑时才会收到通知。一旦他们登录 OneDrive 账户，这些文件将再次可用，并且会还原到他们的新电脑。当然，OneDrive 意味着，他们将在任何时候从手机和其他设备安全保存文件。

对 Azure Active Directory 支持的 OneDrive 进行身份验证，为了获得额外的安全性，可以轻松启用多重身份验证，并且可以设置策略来控制 OneDrive 用来限制网络活动的上传和下载带宽。

不需要同时迁移每个用途。你可能想要逐步推出组策略设置，或者[将文件同步到已加入域的电脑](https://docs.microsoft.com/en-us/powershell/module/sharepoint-online/Set-SPOTenantSyncClientRestriction?view=sharepoint-ps)。

## <a name="start-menu-and-task-bar-customization"></a>开始菜单和任务栏自定义

OneDrive 旨在同步和保护文件和文件夹；它不同步应用程序或 Windows 设置。为了做到这一点，在过去，你可能使用复制配置文件的方法来为用户的“开始”菜单和任务栏设置配置标准布局。在 Windows 10 专业版、企业版和教育版中，可以使用组策略、MDM、PowerShell 或预配包来部署[自定义开始和任务栏布局](https://docs.microsoft.com/zh-CN/windows/configuration/windows-10-start-layout-options-and-policies)。不需要重新成像，只需简单地通过重写包含布局的 .xml 文件即可更新布局。

若要创建新布局，只需配置一个示例系统，并使用 PowerShell [Export-StartLayout](https://docs.microsoft.com/en-us/powershell/module/startlayout/export-startlayout?view=win10-ps) cmdlet 来生成 XML 文件，然后将该文件置于网络共享中，或者将其作为部署序列的一部分在本地缓存；一旦用户登录，它只需作为只读文件访问。然后可以使用策略或 [Import-StartLayout](https://docs.microsoft.com/en-us/powershell/module/startlayout/import-startlayout?view=win10-ps) cmdlet 来引用此文件。

## <a name="removing-unwanted-in-box-apps"></a>删除不需要的框中应用

作为标准安装的一部分，Windows 10 包含多个有用的内置应用，但你可能想要从托管的电脑中删除部分应用，甚至配置安装以防止这些应用返回，例如，XBOX 或 Zune Music。可以使用 [PowerShell Get-AppxPackage](https://technet.microsoft.com/zh-CN/library/hh856044.aspx) 命令检索一个包含这些应用的列表，然后使用 [Remove-AppxPackage](https://technet.microsoft.com/zh-CN/library/hh856038.aspx) 命令删除不需要的应用。或者，你也可以在部署之前离线装载 Windows 映像 (.img) 文件，然后使用[部署映像服务和管理 (DISM)](https://docs.microsoft.com/zh-CN/windows-hardware/manufacture/desktop/what-is-dism) 命令行工具和 [Remove-AppxProvisionedPackage](https://docs.microsoft.com/en-us/powershell/module/dism/remove-appxprovisionedpackage?view=win10-ps) 命令提取不需要的包。

## <a name="next-step"></a>后续步骤

## <a name="step-5-security-and-compliance-considerationshttpsakamsmdd5"></a>[步骤 5：安全性和合规性注意事项](https://aka.ms/mdd5)

## <a name="previous-step"></a>上一步

## <a name="step-3-office-and-lob-app-deliveryhttpsakamsmdd3"></a>[步骤 3：Office 和 LOB 应用交付](https://aka.ms/mdd3)