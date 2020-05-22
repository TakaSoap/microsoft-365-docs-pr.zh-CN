---
title: 启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签
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
ms.openlocfilehash: 62bc2b748cf004722f94a7231046930d78437603
ms.sourcegitcommit: b18949de721c6eef3521d5f8286d9b926ad4aabe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342514"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，不能在 web 上的 Office 中应用[敏感度标签](sensitivity-labels.md)。 您不会在功能区上看到 "**敏感度**" 按钮，也无法在状态栏上看到应用的标签名称。 此外，如果您使用桌面应用程序标记文件，然后将其保存在 SharePoint 或 OneDrive 中，则该服务将无法处理这些文件的内容（如果标签应用了加密）。 在这些情况下，共同创作、eDiscovery、数据丢失防护、搜索和其他协作功能将不起作用。

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签时，将启用所有这些功能。 除了向用户显示敏感度标签之外，对于应用了敏感标签的新文件和已更改文件，包括使用基于云的密钥进行加密：

- SharePoint 可识别应用于 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件的敏感度标签。当文件存储在 SharePoint 中时，将删除来自 Azure 信息保护的加密，以便可以对文件内容进行处理。 有关在将文档存储在 SharePoint 中时如何保护文档的信息，请参阅[OneDrive For business 和 SharePoint Online 中的数据加密](data-encryption-in-odb-and-spo.md)。

- 从 SharePoint 或 OneDrive 下载或访问此文件时，标签中的敏感度标签和任何加密设置都会重新应用于该文件，并且在保存文件的任何位置都将强制执行这些设置。 由于此行为，请确保提供仅使用标签来保护文档的用户指南。 有关详细信息，请参阅[信息权限管理（IRM）选项和敏感度标签](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- 为了使 SharePoint 能够在上载时从文件中删除加密，上载已标记和已加密文件的用户必须至少具有查看该文件的使用权限。 如果用户无法在 SharePoint 外部打开加密，则 SharePoint 不会从文件中删除加密。

- 使用 web 上的 Office （Word、Excel、PowerPoint）打开和编辑具有应用加密的敏感度标签的 Office 文件。 将强制实施通过加密分配的权限。 在 web 上使用 Word 时，您还可以在编辑这些文档时使用自动标记。

- Office 365 电子数据展示支持对这些文件进行全文搜索。 数据丢失防护（DLP）策略涵盖这些文件中的内容。

> [!NOTE]
> 如果加密尚未应用于基于云的密钥，而是本地密钥，则密钥管理拓扑通常称为 "保留自己的密钥" （HYOK），用于处理文件内容的 SharePoint 行为不会发生变化。
>
> Sharepoint 中的现有标记和加密文件的 SharePoint 行为也不会更改。 为了使这些文件受益于新功能，必须下载和上载这些文件，或者在运行命令以启用 SharePoint 和 OneDrive 的敏感度标签后对这些文件进行编辑。 例如，它们将在搜索和电子数据展示结果中返回。

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，可使用三个新的[审核事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)来监视应用于 Sharepoint 和 onedrive 中文档的敏感度标签：
- **已向文件应用敏感度标签**
- **已更改应用于文件的敏感度标签**
- **已从文件除敏感度标签**

观看以下视频（无音频）以查看操作中的新功能：

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

您始终可以选择在 SharePoint 和 OneDrive 中禁用 Office 文件的敏感度[标签（随时退出。](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)

## <a name="requirements"></a>Requirements

这些新功能仅适用于[敏感度标签](sensitivity-labels.md)。 如果你当前有 Azure 信息保护标签，请首先将其迁移到敏感度标签，以便可以为上传的新文件启用这些功能。 有关说明，请参阅[如何将 Azure 信息保护标签迁移到统一敏感度标签](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

在 Windows 上使用 OneDrive 同步应用程序版本19.002.0121.0008 或更高版本，在 Mac 上使用版本19.002.0107.0008 或更高版本。 这两个版本都发布了2019年1月28日，并且当前已发布到所有震铃。 有关详细信息，请参阅[OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，运行较旧版本的同步应用程序的用户将被提示更新它。

## <a name="limitations"></a>限制

- SharePoint 不会自动将灵敏度标签应用于已使用 Azure 信息保护标签加密的现有文件。 相反，若要在为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后运行这些功能，请完成以下任务：
    
    1. 确保已[将 Azure 信息保护标签迁移](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)到了敏感度标签，并[已将其](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)从 Microsoft 365 合规性中心或等效的标签管理中心进行了发布。
    
    2. 下载这些文件，然后将其上传到 SharePoint。

- 当应用了加密的标签具有以下[加密配置](encryption-sensitivity-labels.md#configure-encryption-settings)之一时，SharePoint 将无法处理加密文件：
    - **允许用户在应用标签时分配权限**，并在**Word、PowerPoint 和 Excel 中对复选框进行提示，并在 Word、PowerPoint 和 Excel 中选中 "提示用户指定权限**"。 此设置有时称为 "用户定义的权限"。
    - **用户对内容的访问权限**设置为**永不**过期的值。
    
    对于具有上述任一加密配置的标签，web 上的 Office 用户不会看到这些标签。 此外，不能将新功能用于已拥有这些加密设置的已标记文档。 例如，这些文档不会在搜索结果中返回，即使它们已更新也是如此。

- 对于向用户授予编辑权限的加密文档，不能在 Office 应用程序的 web 版本中阻止复制。

- 不支持 Azure 信息保护文档跟踪网站。

- 对于标记为加密的文件，Office 桌面应用程序和移动应用程序不支持共同创作。 这些应用将继续以独占编辑模式打开带标签和加密的文件。

- 如果管理员更改已应用于下载到用户同步客户端的文件的已发布标签的设置，则用户可能无法在其 OneDrive 同步文件夹中保存对文件所做的更改。 此方案适用于使用加密标记的文件，以及当标签更改来自未对其应用加密的标签的标签时。 用户看到一个[带有白色交叉图标错误的红色圆圈](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，并要求他们将新的更改另存为一个单独副本。 而是可以关闭和重新打开文件，或使用 web 上的 Office。

- 如果将带标签的文档上载到 SharePoint，并使用服务主体名称中的帐户来应用加密，则无法在 web 上的 Office 中打开该文档。 示例方案包括 Microsoft 云应用安全和通过电子邮件发送给团队的文件。

- 用户可以在脱机或进入睡眠模式后遇到保存问题，而不是在使用 Office 的情况下使用 Word、Excel 或 PowerPoint 的桌面和移动应用程序。 对于这些用户，当他们恢复 Office 应用程序会话并尝试保存更改时，他们会看到 "上载失败" 消息，其中包含一个用于保存副本而不是保存原始文件的选项。 

- 以下列方式加密的文档无法在 web 上的 Office 中打开：
    - 使用本地密钥的加密（"保留自己的密钥" 或 HYOK）
    - 独立于标签（例如，通过直接应用权限管理保护模板）应用的加密。

- 如果您删除了应用于 SharePoint 文档的标签，而不是从适用的标签策略中删除标签，则下载的文档不会被标记或加密。 相比之下，如果标记的文档存储在 SharePoint 外部，则在删除该标签时，该文档仍保持加密。 请注意，尽管您可以在测试阶段删除标签，但很少在生产环境中删除标签。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>如何为 SharePoint 和 OneDrive 启用敏感度标签（自愿加入）

您可以通过使用 Microsoft 365 合规性中心或使用 PowerShell 来启用新功能。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>使用合规性中心启用敏感度标签支持

此选项是为 SharePoint 和 OneDrive 启用敏感度标签的最简单方法。

组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。 如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。

1. 登录[Microsoft 365 合规性中心](https://compliance.microsoft.com/)，并导航到 "**解决方案**  >  **信息保护**"
    
    如果看不到此选项，请先选择“**全部显示**”。 

2. 如果您看到一条消息，以打开在 Office online 文件中处理内容的功能，请选择 **"立即打开"**：
    
    ![启用 "立即打开" 按钮以启用 Office Online 的敏感度标签](../media/sensitivity-labels-turn-on-banner.png)
    
    该命令将立即运行，当页面下次刷新时，您将不会再看到该消息或按钮。 

> [!NOTE]
> 如果你有 Microsoft 365 多地理位置，则必须使用 PowerShell 为你的所有地理位置启用这些功能。 有关详细信息，请参阅下一节。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>使用 PowerShell 启用敏感度标签支持

作为使用合规性中心的替代方法，可以使用 SharePoint Online PowerShell 中的[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 启用敏感度标签支持。 

如果你有 Microsoft 365 多地理位置，则必须使用 PowerShell 为你的所有地理位置启用此支持。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>准备 SharePoint Online 命令行管理程序

在运行 PowerShell 命令以在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，请确保您运行的是 SharePoint Online 命令行管理程序版本16.0.19418.12000 或更高版本。 如果已有最新版本，则可以跳至[下一过程](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)以运行 PowerShell 命令。

1. 如果已从 PowerShell 库安装早期版本的 SharePoint Online 命令行管理程序，可通过运行以下 cmdlet 来更新模块。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 或者，如果您已从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到 "**添加或删除程序**"，然后卸载 SharePoint Online 命令行管理程序。

3. 在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 选择语言，然后单击“**下载**”。

5. 在 x64 和 x86.msi 文件之间进行选择。 如果运行的是64位版本的 Windows 或 x86 文件（如果运行32位版本），请下载 x64 文件。 如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. 下载文件后，运行文件并按照安装向导中的步骤操作。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>运行 PowerShell 命令以启用敏感度标签支持

若要启用新功能，请将[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Cmdlet 与*EnableAIPIntegration*参数一起使用：

1. 在 Microsoft 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。
    
    注意：如果你拥有 Microsoft 365 多地理位置，请使用-Url 参数和[connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，并为你的某个地理位置指定 SharePoint Online 管理中心网站 Url。

2. 运行以下命令，然后按**Y**确认：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. 对于 Microsoft 365 多地理位置：对剩下的每个地理位置重复步骤1和2。

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>创建或更改敏感度标签后计划回滚

在 Microsoft 365 合规性中心中创建或更改灵敏度标签后，请分阶段发布它。 如果您发布尚未完全同步的标签，则当用户将标签应用于文件并将其上传到 SharePoint 时，将无法在 Office 应用程序的 web 版本中打开这些文件。 搜索和电子数据展示也不适用于这些文件。

我们建议您按照以下步骤操作：

1. 仅将新的或修改的敏感度标签发布给一个或两个人。

2. 在初始发布后至少等待24小时。 验证标签是否已完全同步。

3. 更广泛地发布标签。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>如何禁用 SharePoint 和 OneDrive 的敏感度标签（自愿退出）

如果禁用这些新功能，则在对 SharePoint 和 OneDrive 启用敏感度标签后上载的文件将继续受标签保护，因为仍会继续强制实施标签设置。 在禁用这些新功能之后将灵敏度标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。

若要禁用这些新功能，必须使用 PowerShell。 使用 SharePoint Online 命令行管理程序和[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 指定相同的*EnableAIPIntegration*参数，如[使用 PowerShell 启用对灵敏度标签的支持](#use-powershell-to-enable-support-for-sensitivity-labels)部分中所述。 但这次，请将参数值设置为 false，然后按**Y**确认：

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

如果你拥有 Microsoft 365 多地理位置，则必须为你的每个地理位置运行此命令。

## <a name="next-steps"></a>后续步骤

在 SharePoint 和 OneDrive 中为 Office 文件启用了敏感度标签后，请考虑使用自动标记策略自动标记这些文件。 有关详细信息，请参阅[自动将敏感度标签应用于内容](apply-sensitivity-label-automatically.md)。