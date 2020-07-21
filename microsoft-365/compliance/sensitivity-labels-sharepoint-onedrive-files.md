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
ms.openlocfilehash: 8530e3d82fd670eedde9a874b0a87a0bad523fe5
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199522"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，不能在 web 上的 Office 中应用[敏感度标签](sensitivity-labels.md)。 您不会在功能区上看到 "**敏感度**" 按钮，也无法在状态栏上看到应用的标签名称。 此外，如果您使用桌面应用程序标记文件，然后将其保存在 SharePoint 或 OneDrive 中，则该服务将无法处理这些文件的内容（如果标签应用了加密）。 在这些情况下，共同创作、eDiscovery、数据丢失防护、搜索和其他协作功能将不起作用。

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签时，将启用所有这些功能。 除了向用户显示敏感度标签之外，对于应用了敏感标签的新文件和已更改文件，包括使用基于云的密钥进行加密：

- 对于 Word、Excel 和 PowerPoint 文件，SharePoint 会识别该标签，现在可以处理加密文件的内容。

- 从 SharePoint 或 OneDrive 下载或访问这些文件时，将强制应用标签中的敏感度标签和任何加密设置，并在存储文件的任何位置保留这些设置。 确保提供用户指南以仅使用标签来保护文档。 有关详细信息，请参阅[信息权限管理（IRM）选项和敏感度标签](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- 当用户将标记和加密的文件上传到 SharePoint 时，他们必须至少具有对这些文件的查看权限。 例如，他们可以在 SharePoint 外部打开文件。 如果没有合适的最小使用率，则上载将会成功，但 SharePoint 无法识别标签，也无法处理文件内容。

- 使用 web 上的 Office （Word、Excel、PowerPoint）打开和编辑具有应用加密的敏感度标签的 Office 文件。 将强制实施通过加密分配的权限。 在 web 上使用 Word 时，您还可以在编辑这些文档时使用自动标记。

- 外部用户可以使用来宾帐户访问标记为加密的文档。 有关详细信息，请参阅[对外部用户的支持和带标签的内容](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。 

- Office 365 电子数据展示支持对这些文件进行全文搜索。 数据丢失防护（DLP）策略支持这些文件中的内容。

> [!NOTE]
> 如果加密尚未应用于基于云的密钥，而是本地密钥，则密钥管理拓扑通常称为 "保留自己的密钥" （HYOK），用于处理文件内容的 SharePoint 行为不会发生变化。
>
> Sharepoint 中的现有标记和加密文件的 SharePoint 行为也不会更改。 为了使这些文件受益于新功能，必须下载和上载这些文件，或者在运行命令以启用 SharePoint 和 OneDrive 的敏感度标签后对这些文件进行编辑。 然后，SharePoint 可以处理这些文件。 例如，它们将在搜索和电子数据展示结果中返回。

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，可使用三个新的[审核事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)来监视应用于 Sharepoint 和 onedrive 中文档的敏感度标签：
- **已向文件应用敏感度标签**
- **已更改应用于文件的敏感度标签**
- **已从文件除敏感度标签**

观看以下视频（无音频）以查看操作中的新功能：

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

您始终可以选择在 SharePoint 和 OneDrive 中禁用 Office 文件的敏感度[标签（随时退出。](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)

如果当前通过使用 SharePoint 信息权限管理（IRM）保护 SharePoint 中的文档，请务必查看此页上的 " [SharePoint 信息权限管理（irm）和敏感度标签](#sharepoint-information-rights-management-irm-and-sensitivity-labels)" 部分。 

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

## <a name="publishing-and-changing-sensitivity-labels"></a>发布和更改敏感度标签

当您在 SharePoint 和 OneDrive 中使用敏感度标签时，请记住，在发布新的敏感度标签或更新现有的敏感度标签时，需要允许复制时间。 对于适用于加密的新标签，这一点尤其重要。

例如：您创建并发布了一个新的敏感度标签，它将应用加密并快速显示在用户的桌面应用程序中。 用户将此标签应用于文档，然后将其上载到 SharePoint 或 OneDrive。 如果该服务的标签复制尚未完成，则在上载时不会对该文档应用新功能。 因此，不会在搜索或电子数据展示中返回该文档，也不能在 Office for web 中打开该文档。

- 以下更改在一小时内复制：新的和删除的敏感度标签，以及包括哪些标签在策略中的敏感度标签策略设置。

- 以下更改将在24小时内复制：对现有标签的敏感度标签设置的更改。

由于对于新的敏感度标签，复制延迟现在仅为一小时，因此您不太可能会遇到此示例中的情形。 但作为一项安全措施，我们建议先将新标签发布到少数测试用户，再等待一小时，然后在 SharePoint 和 OneDrive 上验证标签行为。 最后一步是，通过向现有标签策略中添加更多用户，或为标准用户将标签添加到现有的标签策略中，使更多的用户可以使用该标签。 当您的标准用户看到标签时，它已同步到 SharePoint 和 OneDrive。


## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint 信息权限管理（IRM）和敏感度标签

[SharePoint 信息权限管理（IRM）](set-up-irm-in-sp-admin-center.md)是一种较旧的技术，可通过在下载文件时应用加密和限制来保护列表和库级别的文件。 此较旧的保护技术旨在防止未经授权的用户在 SharePoint 外部打开该文件。

相比之下，敏感度标签提供了直观标记（页眉、页脚、水印）的保护设置以及加密。 加密设置支持完全范围的[使用权限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights)，以限制用户可以对内容执行的操作，并且[许多方案](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)都支持相同的敏感度标签。 在工作负载和应用中使用具有一致设置的相同保护方法将导致一致的保护策略。

但是，可以同时使用这两个保护解决方案，行为如下所示： 

- 如果您上载的文件具有适用于加密的敏感度标签，SharePoint 将无法处理此文件，因此不能对此文件进行共同创作、电子数据展示、DLP 和搜索。

- 如果使用 web 上的 Office 标记文件，则将强制应用标签中的所有加密设置。 对这些文件、共同创作、电子数据展示、DLP 和搜索均受支持。

- 如果下载使用 web 上的 Office 标记的文件，则会保留标签，并强制实施标签中的所有加密设置，而不是 IRM 限制设置。

- 如果下载未使用敏感度标签加密的 Office 或 PDF 文件，则会应用 IRM 设置。

- 如果已启用任何其他 IRM 库设置，其中包括阻止用户上载不支持 IRM 的文档，则强制实施这些设置。

在这种情况下，您可以确信，如果下载了所有 Office 和 PDF 文件，即使这些文件不带标签，也可以防止未经授权的访问。 但是，已上传的已标记文件不会受益于新功能。

## <a name="search-for-documents-by-sensitivity-label"></a>按敏感度标签搜索文档

使用托管属性**InformationProtectionLabelId**在 SharePoint 或 OneDrive 中查找具有特定灵敏度标签的所有文档。 使用以下语法：`InformationProtectionLabelId:<GUID>`

例如，若要搜索已标记为 "保密" 的所有文档，并且该标签的 GUID 为 "8faca7b8-8d20-48a3-8ea2-0f96310a848e"，请在搜索框中键入以下内容：

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

若要获取敏感度标签的 Guid，请使用 "[获取标签](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps)" cmdlet：
    
1. 首先，[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。 
    
    例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录：
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. 然后运行以下命令：
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

有关使用托管属性的详细信息，请参阅[在 SharePoint 中管理搜索架构](https://docs.microsoft.com/sharepoint/manage-search-schema)。

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>如何禁用 SharePoint 和 OneDrive 的敏感度标签（自愿退出）

如果禁用这些新功能，则在对 SharePoint 和 OneDrive 启用敏感度标签后上载的文件将继续受标签保护，因为仍会继续强制实施标签设置。 在禁用这些新功能之后将灵敏度标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。

若要禁用这些新功能，必须使用 PowerShell。 使用 SharePoint Online 命令行管理程序和[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 指定相同的*EnableAIPIntegration*参数，如[使用 PowerShell 启用对灵敏度标签的支持](#use-powershell-to-enable-support-for-sensitivity-labels)部分中所述。 但这次，请将参数值设置为 false，然后按**Y**确认：

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

如果你拥有 Microsoft 365 多地理位置，则必须为你的每个地理位置运行此命令。

## <a name="next-steps"></a>后续步骤

在 SharePoint 和 OneDrive 中为 Office 文件启用了敏感度标签后，请考虑使用自动标记策略自动标记这些文件。 有关详细信息，请参阅[自动将敏感度标签应用于内容](apply-sensitivity-label-automatically.md)。