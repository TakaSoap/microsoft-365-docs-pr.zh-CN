---
title: 启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理员可以在 SharePoint 和 OneDrive 中为 Word、Excel 和 PowerPoint 文件启用敏感度标签支持。
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802825"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签

以前，在对存储在 SharePoint 和 OneDrive 中的 Office 文件应用包含加密的敏感度标签时，该服务无法处理这些文件的内容。 在这些情况下，合著、电子数据丢失、数据丢失防护、搜索、Delve 和其他协作功能不起作用。 此预览启用以下功能：

- SharePoint 识别应用于 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件的敏感度标签。 SharePoint 还强制实施与每个标签对应的设置。

- 从 SharePoint 或 OneDrive 下载文件时，敏感度标签与文件一起移动，并且设置仍将强制实施。

- 将敏感度标签应用于 Office 文件，并使用 Word、Excel 和 PowerPoint 的 web 版本打开和编辑已应用灵敏度标签的文件（如果标签的权限允许）。 在 web 上使用 Word 时，您还可以在编辑文档时使用自动标签。

- Office 365 电子数据展示支持在应用了灵敏度标签的文件中进行全文搜索。 数据丢失防护（DLP）策略涵盖这些文件中的内容。

- 有三个新的审核事件可用于监视敏感度标签：
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

现在，您还可以将灵敏度标签应用于 Microsoft 团队、Office 365 组和 SharePoint 网站。 [了解详细信息](sensitivity-labels-teams-groups-sites.md)。

如有必要，可随时退出预览。

## <a name="requirements"></a>Requirements

这些功能仅适用于[敏感度标签](sensitivity-labels.md)。 如果你使用的是 Azure 信息保护标签，则可以将其转换为敏感度标签，以对你上载的新文件启用这些功能。 [了解方法](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

对于此预览，请在 Windows 和版本19.002.0107.0008 或更高版本的 Mac 上使用 OneDrive 同步应用版本19.002.0121.0008 或更高版本。 这两个版本都是在2019年1月28日发布的，并且当前已发布到所有震铃。 [请参阅 OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 启用此预览后，将提示运行较早版本的同步应用的用户进行更新。

## <a name="limitations"></a>限制

- 如果启用此预览，则使用 Office 桌面或移动应用将标签应用于文件的用户可能无法保存对文件所做的其他更改。 相反，应用程序会提示用户另存为或放弃本地更改。 若要避免丢失工作，请执行以下操作之一：

  - 若要应用标签，请使用 Office 应用的 web 版本。

  - 在应用标签后关闭文件，然后重新打开该文件以进行其他更改。

- SharePoint 不会自动将新标签应用于已使用 Azure 信息保护标签加密的现有文件。 若要在启用此预览后获取要运行的功能，请完成以下任务：

  - 将 Azure 信息保护标签转换为敏感度标签。

  - 下载文件并将其上载到 SharePoint。

- SharePoint 无法处理带有过期日期的自定义权限和标签的标签。

- 当用户拥有编辑权限时，无论标签中的副本策略设置如何，Office 应用程序的 web 版本都允许复制。

- 不支持 RMS 吊销、跟踪和报告。

- Office 桌面应用程序和移动应用程序不支持共同创作。 相反，这些应用将继续以独占编辑模式打开文件。

- 如果标签包括加密，Microsoft 云应用安全性无法读取 SharePoint 中文件的标签信息。

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>为预览准备 SharePoint Online 命令行管理程序

在启用预览之前，请确保您运行的是 SharePoint Online 命令行管理程序版本16.0.19418.12000 或更高版本。 如果已有最新版本，可以继续并启用预览。

1. 如果已从 PowerShell 库安装了早期版本的 SharePoint Online 命令行管理程序，则可以通过运行以下 cmdlet 来更新模块。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 或者，如果您已从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到 "**添加或删除程序**"，然后卸载 SharePoint Online 命令行管理程序。

3. 在 web 浏览器中，转到 "下载中心" 页面并[下载最新的 SharePoint Online 命令行管理](https://go.microsoft.com/fwlink/p/?LinkId=255251)程序。

4. 选择您的语言，然后单击 "**下载**"。

5. 在 x64 和 x86 .msi 文件之间进行选择。 如果运行的是64位版本的 Windows 或 x86 文件（如果运行32位版本），请下载 x64 文件。 如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)


6. 下载文件后，运行文件并按照安装向导中的步骤操作。

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>使用 Microsoft PowerShell 启用预览（自愿加入）

若要启用预览，请使用 Set-spotenant cmdlet：

1. 在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

2. 运行以下命令：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>创建或更改敏感度标签后计划回滚

在 Microsoft 365 合规性中心中创建或更改灵敏度标签后，请分阶段发布它。 如果您发布尚未完全同步的标签，则当用户将标签应用于文件并将其上传到 SharePoint 时，将无法在 Office 应用程序的 web 版本中打开这些文件。 搜索和电子数据展示也不适用于这些文件。

我们建议您按照以下步骤操作：

1. 仅将新的或修改的敏感度标签发布给一个或两个人。

2. 在初始发布后至少等待24小时。 验证标签是否已完全同步。

3. 更广泛地发布标签。

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>使用 Microsoft PowerShell 禁用预览（自愿退出）

如果禁用此预览，则在预览过程中上载的文件将继续受标签保护。 将继续强制实施相应的设置。 在禁用预览后将标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。

若要禁用预览，请使用 Set-spotenant cmdlet：

1. 在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

2. 运行以下命令：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
