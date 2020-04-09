---
title: 启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理员可以在 SharePoint 和 OneDrive 中为 Word、Excel 和 PowerPoint 文件启用敏感度标签支持。
ms.openlocfilehash: 8f57a680bf5cbd53153cedc339b35bc2712c3f73
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "43188976"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

在此预览之前，您无法将您的[灵敏度标签](sensitivity-labels.md)应用于 web 上的 Office。 您没有在功能区上看到 "**敏感度**" 选项，或者状态栏上的 "应用的标签名称"。 此外，如果您使用桌面应用程序标记文件，然后将其保存在 SharePoint 或 Onedrive 中，则该服务无法处理这些文件的内容（如果标签应用了加密）。 在这些情况下，合著、电子数据丢失、数据丢失防护、搜索、Delve 和其他协作功能不起作用。 

此预览启用了所有这些功能。 除了向用户显示敏感度标签之外，对于应用了敏感标签的新文件和已更改文件，包括使用基于云的密钥进行加密：

- SharePoint 可识别应用于 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件的敏感度标签。当文件存储在 SharePoint 中时，将删除来自 Azure 信息保护的加密，以便可以对文件内容进行处理。 有关在将文档存储在 SharePoint 中时如何保护文档的信息，请参阅[OneDrive For business 和 SharePoint Online 中的数据加密](data-encryption-in-odb-and-spo.md)。

- 从 SharePoint 或 OneDrive 下载或访问此文件时，标签中的敏感度标签和任何加密设置都会重新应用于该文件，并且在保存文件的任何位置都将强制执行这些设置。 由于此行为，请确保提供仅使用标签来保护文档的用户指南。 有关详细信息，请参阅[信息权限管理（IRM）选项和敏感度标签](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- 为了使 SharePoint 能够在上载时从文件中删除加密，上载已标记和已加密文件的用户必须至少具有查看该文件的使用权限。 如果用户无法在 SharePoint 外部打开加密，则 SharePoint 不会从文件中删除加密。

- 使用 web 上的 Office （Word、Excel、PowerPoint）打开和编辑具有应用加密的敏感度标签的 Office 文件。 将强制实施通过加密分配的权限。 在 web 上使用 Word 时，您还可以在编辑这些文档时使用自动标记。

- Office 365 电子数据展示支持对这些文件进行全文搜索。 数据丢失防护（DLP）策略涵盖这些文件中的内容。

> [!NOTE]
> 如果加密尚未应用于基于云的密钥，而是本地密钥，则密钥管理拓扑通常称为 "保留自己的密钥" （HYOK），用于处理文件内容的 SharePoint 行为在此预览中不会发生变化。
>
> 在启用预览之前，sharepoint 行为也不会对 SharePoint 中的现有标记和加密文件进行更改。 为了让这些文件受益于新功能，必须下载和上载这些文件，或在启用预览后再对其进行编辑。 例如，它们将在搜索和电子数据展示结果中返回。

启用此预览时，可以使用以下三个新的[审核事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)来监视在 web 上使用 Office 应用的敏感度标签：
- **已向文件应用敏感度标签**
- **已更改应用于文件的敏感度标签**
- **已从文件除敏感度标签**

观看以下视频（无音频）以查看这些新功能的操作：

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

你随时都可以选择退出此预览。

## <a name="requirements"></a>要求

这些功能仅适用于[敏感度标签](sensitivity-labels.md)。 如果你当前有 Azure 信息保护标签，请首先将其迁移到敏感度标签，以便可以为上传的新文件启用这些功能。 有关说明，请参阅[如何将 Azure 信息保护标签迁移到统一敏感度标签](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

对于此预览，请在 Windows 上使用 OneDrive 同步应用版本19.002.0121.0008 或更高版本，并在 Mac 上使用版本19.002.0107.0008 或更高版本。 这两个版本都发布了2019年1月28日，并且当前已发布到所有震铃。 有关详细信息，请参阅[OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 启用此预览后，系统会提示运行较旧版本的同步应用程序的用户对其进行更新。

## <a name="limitations"></a>限制

- 如果启用此预览，则在 OneDrive 同步文件夹中更改文件上的标签的用户可能无法保存对该文件所做的其他更改。 此方案适用于使用加密标记的文件，以及当标签更改来自未对其应用加密的标签的标签时。 用户看到一个[带有白色交叉图标错误的红色圆圈](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，并要求他们将新的更改另存为一个单独副本。  
    
    除了用户启动的标签更改之外，如果管理员更改已应用于下载到用户同步客户端的文件的已发布标签的设置，也会发生相同的行为。
    
    若要避免在这些情况下丢失工作，请执行以下操作之一：
    - 若要应用标签，请使用 Office 应用的 web 版本。
    - 在应用标签后关闭文件，然后重新打开该文件以进行其他更改。

- SharePoint 不会自动将灵敏度标签应用于已使用 Azure 信息保护标签加密的现有文件。 若要在启用此预览后获取要运行的功能，请完成以下任务：
    
    1. 确保已将 Azure 信息保护标签迁移到了敏感度标签，并已将其从 Microsoft 365 合规性中心或等效的标签管理中心进行了发布。
    
    2. 下载这些文件，然后将其上传到 SharePoint。

- 当应用了加密的标签具有以下加密配置之一时，SharePoint 将无法处理加密文件：
    - **允许用户在应用标签时分配权限**，并在**Word、PowerPoint 和 Excel 中对复选框进行提示，并在 Word、PowerPoint 和 Excel 中选中 "提示用户指定权限**"。 此设置有时称为 "用户定义的权限"。
    - **用户对内容的访问权限**设置为**永不**过期的值。
    
    对于具有上述任一加密配置的标签，web 上的 Office 用户不会看到这些标签。 此外，此预览中的新功能不能用于已有这些加密设置的已标记文档。 例如，这些文档不会在搜索结果中返回，即使它们已更新也是如此。

- 对于向用户授予编辑权限的加密文档，不能在 Office 应用程序的 web 版本中阻止复制。

- 不支持 Azure 信息保护文档跟踪网站。

- 对于标记为加密的文件，Office 桌面应用程序和移动应用程序不支持共同创作。 这些应用将继续以独占编辑模式打开带标签和加密的文件。

- 如果将带标签的文档上载到 SharePoint，并使用服务主体名称中的帐户来应用加密，则无法在 web 上的 Office 中打开该文档。 示例方案包括 Microsoft 云应用安全和通过电子邮件发送给团队的文件。

- 用户可以在脱机或进入睡眠模式后遇到保存问题，而不是在使用 Office 的情况下使用 Word、Excel 或 PowerPoint 的桌面和移动应用程序。 对于这些用户，当他们恢复 Office 应用程序会话并尝试保存更改时，他们会看到 "上载失败" 消息，其中包含一个用于保存副本而不是保存原始文件的选项。 

- 以下列方式加密的文档无法在 web 上的 Office 中打开：
    - 使用本地密钥的加密（"保留自己的密钥" 或 HYOK）
    - 独立于标签（例如，通过直接应用权限管理保护模板）应用的加密。

- 如果您删除了应用于 SharePoint 文档的标签，而不是从适用的标签策略中删除标签，则下载的文档不会被标记或加密。 相比之下，如果标记的文档存储在 SharePoint 外部，则在删除该标签时，该文档仍保持加密。 请注意，尽管您可以在测试阶段删除标签，但很少在生产环境中删除标签。

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>为预览准备 SharePoint Online 命令行管理程序

在启用预览之前，请确保您运行的是 SharePoint Online 命令行管理程序版本16.0.19418.12000 或更高版本。 如果已有最新版本，可以继续并启用预览。

1. 如果已从 PowerShell 库安装早期版本的 SharePoint Online 命令行管理程序，可通过运行以下 cmdlet 来更新模块。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 或者，如果您已从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到 "**添加或删除程序**"，然后卸载 SharePoint Online 命令行管理程序。

3. 在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 选择语言，然后单击“**下载**”。

5. 在 x64 和 x86.msi 文件之间进行选择。 如果运行的是64位版本的 Windows 或 x86 文件（如果运行32位版本），请下载 x64 文件。 如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)


6. 下载文件后，运行文件并按照安装向导中的步骤操作。

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>使用 Microsoft PowerShell 启用预览（自愿加入）

若要启用预览，请使用 Set-spotenant cmdlet：

1. 在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。
    
    注意：如果你拥有 Office 365 多地理位置，请使用-Url 参数和[connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，并为你的某个地理位置指定 SharePoint Online 管理中心网站 Url。

2. 运行以下命令：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. 对于 Office 365 多地理位置：对剩下的每个地理位置重复步骤1和2。

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

## <a name="next-steps"></a>后续步骤

现在，您已对 SharePoint 和 OneDrive 中的 Office 文件启用了敏感度标签，请考虑使用自动标记策略自动标记这些文件。 有关详细信息，请参阅[自动将敏感度标签应用于内容](apply-sensitivity-label-automatically.md)。
