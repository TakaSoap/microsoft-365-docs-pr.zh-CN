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
description: 管理员可以为 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件启用敏感度标签支持。
ms.openlocfilehash: d049cdd61d2155267f4e55c612885929e27adaaa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845718"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，无法在 Office [网页](sensitivity-labels.md) 版中应用敏感度标签。 功能区上不会看到 **"敏感度"** 按钮，也不会在状态栏上看到已应用的标签名称。 此外，如果你使用桌面应用程序标记文件，然后将其保存到 SharePoint 或 OneDrive 上，那么如果标签已应用加密，则服务将无法处理这些文件的内容。 共同创作、电子数据展示、数据丢失防护、搜索和其他协作功能在这些情况下将无法正常工作。

为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签时，会启用所有这些功能。 除了向用户显示敏感度标签，不仅是为应用了敏感度标签的新文件和已更改的文件，该标签包含通过基于云的密钥 (加密，并且不使用 [双密钥加密](double-key-encryption.md)) ：

- 对于 Word、Excel 和 PowerPoint 文件，SharePoint 可识别标签，并且现在能够处理加密文件的内容。

- 从 SharePoint 或 OneDrive 下载或访问这些文件时，将强制执行敏感度标签及标签中任何加密设置，且不随着文件存储在何处保留。 确保提供用户指导，以仅使用标签来保护文档。 有关详细信息，请参阅 [IRM 文件和 () 标签管理工具包的信息权限管理](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。

- 当用户将标记的和加密文件上载到 SharePoint 时，必须至少对这些文件拥有查看权限。 例如，用户可以在 SharePoint 外部打开文件。 如果它们没有此最低使用权限，则上传会成功，但 SharePoint 不会识别标签并且无法处理文件内容。

- 使用 Office 网页版 (Word、Excel、PowerPoint) 打开和编辑具有应用加密的敏感度标签的 Office 文件。 强制实施通过加密分配的权限。 在 Word 网页版中，你还可以在编辑这些文档时使用自动标记功能。

- 外部用户可以通过使用来宾帐户访问标记为加密的文档。 有关详细信息，请参阅 [支持外部用户和标记内容](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。

- Office 365 电子数据展示支持对这些文件和数据丢失防 (DLP 策略) 制支持这些文件中的内容。

> [!NOTE]
> 如果已通过本地密钥 (应用加密是一种通常称为"保留自己的密钥"或 HYOK) 的密钥管理拓扑，或者使用 [双键](double-key-encryption.md)加密，则用于处理文件内容的 SharePoint 行为不会改变。
>
> 对于 SharePoint 中使用单个基于 Azure 的密钥加密进行了标记的现有文件，SharePoint 行为也不会发生改变。 为了使这些文件能够受益于在 SharePoint 和 OneDrive 中为 Office 文件启用了敏感度标签后，必须重新下载和上传这些文件或进行编辑。 例如，在搜索结果中将返回它们。

在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，SharePoint 和 OneDrive 中的文档可用于监视敏感度标签的三种新的审核事件： [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)

- **已向文件应用敏感度标签**
- **已更改应用于文件的敏感度标签**
- **已从文件除敏感度标签**

观看以下没有 (视频，) 查看当前运行的新功能：

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

始终可以选择为 SharePoint 和 OneDrive 中的 Office 文件禁用敏感度标签， ([选择退](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) 出。

如果当前正使用 SharePoint 信息权限管理 (IRM) 来保护 SharePoint 中的文档，请务必查看此 [页面上的"SharePoint 信息权限管理 (IRM) ](#sharepoint-information-rights-management-irm-and-sensitivity-labels) 和敏感度标签"部分。

## <a name="requirements"></a>Requirements

这些新功能 [仅适用于敏感度标签](sensitivity-labels.md) 。 如果目前拥有 Azure 信息保护标签，请首先将它们迁移到敏感度标签，以便为上传的新文件启用这些功能。 有关说明， [请参阅"如何将 Azure 信息保护标签迁移到统一敏感度标签"](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

在 Windows 上使用 OneDrive 同步应用版本 19.002.0121.0008 或更高版本，以及 Mac 版本 19.002.0107.0008 或更高版本。 这两个版本是 2019 年 1 月 28 日发布的，目前已向所有圈发布。 有关详细信息，请参阅 [OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。 为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后，系统会提示运行较早版本的同步应用的用户进行更新。

## <a name="limitations"></a>限制

- SharePoint 不会自动将敏感度标签应用于已使用 Azure 信息保护标签加密的现有文件。 相反，为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后，这些功能的工作方式就完成了以下任务：

    1. 确保已将 [Azure 信息保护标签迁移到](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 敏感度标签，并 [从](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Microsoft 365 合规中心或等效标签管理中心发布了这些标签。

    2. 下载文件，然后将其上载到 SharePoint。

- 当应用加密的标签具有以下加密配置之一时，SharePoint 无法 [处理加密的文件](encryption-sensitivity-labels.md#configure-encryption-settings)：

  - **允许用户在应用标签时分配权限** ，并在 **Word、PowerPoint** 和 Excel 中提示用户指定权限。 此设置有时称为"用户定义权限"。
  - **将用户访问内容的到** 期时间设置为非"从不 **"的值**。
  - **选择双密钥** 加密。

  对于具有其中任意一种加密配置的标签，标签不会向 Office 网页版中的用户显示。 此外，新功能不能与已经具有这些加密设置的已标记文档一起使用。 例如，即使这些文档已更新，搜索结果也不会返回至这些文档。

- 对于向用户授予编辑权限的加密文档，不能在 Office 应用的 Web 版本中阻止复制。

- 不支持 Azure 信息保护文档跟踪网站。

- Office 桌面应用程序和移动应用程序不支持合著文件，但它们具有加密标记。 这些应用继续在独占编辑模式下打开已标记和加密的文件。

- 如果管理员更改已应用于已下载到用户同步客户端的文件的已发布标签的设置，用户可能无法将对文件所做的更改保存在 OneDrive 同步文件夹中。 此方案适用于使用加密标记的文件，而且标签更改情况也适用于未对应用加密应用加密的标签应用加密的标签。 用户会 [看到一个带白色交叉图标错误的](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)红色圆圈，他们会要求将新更改保存为单独的副本。 相反，他们可以关闭并重新打开文件，或使用 Office 网页版。

- 如果标签的文档上传到 SharePoint，且标签使用服务主体名称帐户的帐户应用了加密，则无法在 Office 网页版中打开该文档。 示例方案包括 Microsoft Cloud App Security 和通过电子邮件发送到 Teams 的文件。

- 在脱机运行后或进入睡眠模式而不使用 Office 网页版时，用户可能会遇到保存问题，而对 Word、Excel 或 PowerPoint 使用桌面和移动应用。 对于这些用户，当用户恢复其 Office 应用会话并尝试保存更改时，他们会看到上传失败消息，其中会显示一条上传失败消息，提供保存副本的选项，而不是保存原始文件。

- 在 Office 网页版中，无法以以下方式打开已通过以下方式加密的文档：

  - 使用本地密钥的加密 ("保留自己的密钥"或 HYOK) 
  - 通过双密钥加密 [应用的加密](double-key-encryption.md)
  - 独立于标签应用的加密（例如，通过直接应用权限管理保护模板）。

- 如果从共享中删除已应用到文档的标签，而不是从适用标签策略中删除标签，下载的文档将不会标记或加密。 相比之下，如果标签的文档存储在 SharePoint 外部，则该文档将保持加密状态（如果删除了标签）。 请注意，虽然在测试阶段可能会删除标签，但删除生产环境中的标签非常少。

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>如何为 SharePoint 和 OneDrive 文件启用敏感度 (选择加入) 

可以使用 Microsoft 365 合规中心或使用 PowerShell 启用新功能。

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>使用合规中心启用敏感度标签支持

此选项是为 SharePoint 和 OneDrive 启用敏感度标签的最简单方法。

组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。 如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。

1. 登录到 Microsoft [365 合规中心，](https://compliance.microsoft.com/)然后导航到**Solutions**解决方案  >  **信息保护**

    如果看不到此选项，请先选择“**全部显示**”。

2. 如果看到一条消息显示用于处理 Office 在线文件中的内容，请选择 **"立即启用"**

    ![打开"立即"按钮以为 Office Online 启用敏感度标签](../media/sensitivity-labels-turn-on-banner.png)

    命令立即运行，并且下次刷新页面时，您不再看到消息或按钮。

> [!NOTE]
> 如果你拥有 Microsoft 365 多地理位置，则必须使用 PowerShell 为所有地理位置启用这些功能。 有关详细信息，请参阅下一节。

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>使用 PowerShell 启用敏感度标签支持

作为使用合规中心的替代方法，你可以在 SharePoint Online PowerShell 中使用 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 启用对敏感度标签的支持。

如果你拥有 Microsoft 365 多地理位置，则必须使用 PowerShell 支持所有地理位置。

#### <a name="prepare-the-sharepoint-online-management-shell"></a>准备 SharePoint Online 命令行管理程序

在运行 PowerShell 命令以启用 SharePoint 和 OneDrive 中的 Office 文件的敏感度标签之前，请确保你正在运行 SharePoint Online 命令行管理程序版本 16.0.19418.12000 或更高版本。 如果已有最新版本，可跳到 [下一过程以](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) 运行 PowerShell 命令。

1. 如果已从 PowerShell 库安装早期版本的 SharePoint Online 命令行管理程序，可通过运行以下 cmdlet 来更新模块。

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. 或者，如果从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到" **添加或删除程序"，** 然后卸载 SharePoint Online 命令行管理程序。

3. 在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

4. 选择语言，然后单击“**下载**”。

5. 在 x64 和 x86.msi 文件之间进行选择。 如果运行 64 位版本的 Windows，请下载 x64 文件;如果运行 32 位版本，请下载 x86 文件。 如果你不知道，请参阅 [我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. 下载文件后，运行该文件并按照安装向导中的步骤进行操作。

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>运行 PowerShell 命令启用敏感度标签支持

要启用新功能，请将 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 与 *EnableAIPIntegration 参数一起* 使用：

1. 使用在 Microsoft 365 中拥有全局管理员或 SharePoint 管理员权限的工作或学校帐户，连接到 SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

    注意：如果你有 Microsoft 365 多地理位置，请将 -Url 参数与 [Connect-SPOService 结合使用](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，并为一个地理位置指定 SharePoint Online 管理中心网站 URL。

2. 运行以下命令，然后按 **Y** 以确认：

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```

3. 对于 Microsoft 365 多地理位置：为其余每个地理位置重复步骤 1 和 2。

## <a name="publishing-and-changing-sensitivity-labels"></a>发布和更改敏感度标签

将敏感度标签与 SharePoint 和 OneDrive 一起使用时，请记住，在发布新的敏感度标签或更新现有敏感度标签时，你需要允许复制。 这一点对于应用加密的新标签尤其重要。

例如：你创建并发布一个应用加密的新敏感度标签，此标签会很快地显示在用户的桌面应用中。 用户为文档应用此标签，再将其上传到 SharePoint 或 OneDrive。 如果服务未完成标签复制，则上传时不会向该文档应用新功能。 因此，不会在搜索中或对电子数据展示返回文档，并且无法在 Office 网页版中打开文档。

- 以下更改在一小时内复制："新建和删除的敏感度标签"以及包含标签在策略中的敏感度标签策略设置。

- 以下更改在 24 小时内复制：对现有标签的敏感度标签设置的更改。

因为对于新的敏感度标签，复制延迟现在仅保留一小时，因此在示例中不可能遇到此方案。 但作为一项安全措值，建议首先只向少量测试用户发布新标签，等待一小时，然后验证 SharePoint 和 OneDrive 上的标签行为。 最后，通过向现有标签策略添加更多用户，或将标签添加到标准用户的现有标签策略，使更多用户也可以使用标签。 当标准用户看到标签时，它已同步到 SharePoint 和 OneDrive。

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint IRM 文件和 () 标签 (SharePoint 信息权限管理

[SharePoint 信息权限管理 (IRM) ](set-up-irm-in-sp-admin-center.md) 一种较旧的技术，它在下载文件时应用加密和限制来保护列表和库级别的文件。 这种较旧的保护技术旨在防止未经授权的用户在文件位于 SharePoint 外部时打开该文件。

敏感度标签相比之下，敏感度标签除了加密， (邮件标记、页脚和水印) 保护设置。 加密设置支持整套使用 [权限来](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) 限制用户可以对内容执行的操作，并且许多情况下均支持相同的 [敏感度标签](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)。 使用相同保护方法，使用跨工作负载和应用的一致设置，将导致一致的保护策略。

但是，你可以一起使用两种保护解决方案，且其行为如下所示：

- 如果上载包含应用加密的敏感度标签的文件，SharePoint 就不能处理此文件以便共同创作、电子数据展示、DLP 和搜索将不适用于此文件。

- 如果使用 Office 网页版标记文件，则将强制执行标签中任何加密设置。 支持对这些文件进行共同创作、电子数据展示、DLP 和搜索。

- 如果下载一个使用 Office 网页版标签的文件，将保留标签，并强制实施标签中任何加密设置，而不要强制执行 IRM 限制设置。

- 如果下载未使用敏感度标签加密的 Office 或 PDF 文件，则将应用 IRM 设置。

- 如果已启用任何其他 IRM 库设置（包括防止用户上载不支持 IRM 的文档），则将强制执行这些设置。

通过此行为，你可以确保所有 Office 和 PDF 文件在已下载时受未经授权的访问，即使未进行标记也能受到未授权的访问的影响。 但是，上传的已标记文件不会从新功能中受益。

## <a name="search-for-documents-by-sensitivity-label"></a>按敏感度标签搜索文档

使用托管属性 **InformationProtectionLabelId** 来查找 SharePoint 或 OneDrive 中具有特定敏感度标签的所有文档。 使用以下语法： `InformationProtectionLabelId:<GUID>`

例如，要搜索所有已标记为"机密"的文档，并且该标签的 GUID 为"8faca7b8-8d20-48a3-8ea2-0f96310a848e"，请在搜索框中键入：

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

若要获取敏感度标签的 GUID，请使用 [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet：

1. 首先，[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

    例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录。

2. 然后运行以下命令：

    ```powershell
    Get-Label |ft Name, Guid
    ```

有关使用托管属性的详细信息，请参阅"管理[SharePoint 中的搜索架构"。](https://docs.microsoft.com/sharepoint/manage-search-schema)

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>如何禁用 SharePoint 和 OneDrive 的敏感度标签 (退出) 

如果禁用这些新功能，在为 SharePoint 和 OneDrive 启用敏感度标签后上传的文件会继续受标签保护，因为标签设置会继续强制实施。 如果在禁用这些新功能后，将敏感度标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。

若要禁用这些新功能，必须使用 PowerShell。 使用 SharePoint Online 命令行管理程序和 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 指定相同的 *EnableAIPIntegration* 参数，如 [使用 PowerShell 启用敏感度标签部分中](#use-powershell-to-enable-support-for-sensitivity-labels) 所述。 但这次，请将该参数值设置为 false，并按 **Y** 进行确认：

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

如果你有 Microsoft 365 多地理位置，则必须针对每个地理位置运行此命令。

## <a name="next-steps"></a>后续步骤

为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后，请考虑使用自动标记策略自动标记这些文件。 有关详细信息，请参阅["将敏感度标签自动应用于内容"。](apply-sensitivity-label-automatically.md)
