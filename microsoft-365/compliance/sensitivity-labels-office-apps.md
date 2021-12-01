---
title: 管理 Office 应用中的敏感度标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 适用于管理 Office 应用中针对桌面、移动和 Web 的敏感度标签的 IT 管理员的信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a0dcf7314b6dc2e0906a16a0429c33ad60f77fd
ms.sourcegitcommit: cd3f5e3b7fea37fdcd8c811d01afd60ea68301ca
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2021
ms.locfileid: "61254425"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>管理 Office 应用中的敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

从 Microsoft 365 合规中心或等效标签中心[发布了](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 敏感度标签后，这些标签开始在 Office 应用中显示，以便用户在数据创建或编辑后对其进行分类和保护。

使用本文中的信息可帮助你成功管理 Office 应用中的敏感度标签。 例如，确定支持内置标签所需的应用最低版本，并了解与 Azure 信息保护统一标签客户端的交互，以及与其他应用和服务兼容。

## <a name="labeling-client-for-desktop-apps"></a>桌面应用的标签客户端

若要使用 Windows 和 Mac 版 Office 桌面应用中内置的敏感度标签，必须使用 Office 订阅版本。 此标签客户端不支持 Office 独立版本，例如 Office 2016 或 Office 2019。

若要在 Windows 计算机上使用这些独立版本的 Office，请安装 [Azure 信息保护统一标签客户端](/azure/information-protection/rms-client/aip-clientv2)。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>支持应用中的敏感度标签功能

下表列出了使用内置标签支持敏感度标签所需的最低 Office 版本。 或者，如果标签功能是公共预览版，或正在审查将来的版本。 使用 [Microsoft 365 路线图](https://aka.ms/MIPC/Roadmap)了解有关计划用于未来版本的新功能的详细信息。

不同更新频道在不同时间提供新版本的 Office 应用。 对于 Windows，当使用当前频道或每月企业频道而不是半年企业频道时，将更早地获得新功能。 一个更新频道与下一个更新频道的最低版本号也可能不同。 有关详细信息，请参阅 [Microsoft 365 应用版的更新频道概述](/deployoffice/overview-update-channels)和[Microsoft 365 应用版更新历史记录](/officeupdates/update-history-microsoft365-apps-by-date)。

表中不包括专用预览版中的新功能，但通过选择组织参加 [Microsoft 信息保护专用预览计划，](https://aka.ms/mip-preview)。

Office for iOS 和 Office for Android：敏感度标签内置于 [Office 应用](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)。

安装 Azure 信息保护统一标签客户端（该客户端仅在 Windows 计算机上运行）时，可以使用其他功能。 有关详细信息，请参阅 [Windows 计算机标签客户端](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

> [!TIP]
> 将表格中的最小版本与所拥有的版本进行比较时，请记住发布版本的常见做法是省略前导零。
> 
> 例如，有 4.2128.0 版本，并读取到 4.7.1 以上是最低版本。 为便于比较，请将 4.7.1 (无前导零) 读取为 4.**0007**.1 (而不是 4.**7000**.1)。 4.2128.0 版本高于 4.0007.1，因此支持本版本。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 和 PowerPoint 中的敏感度标签功能

列出的数字是每个功能所需的最低 Office 应用程序版本。 

> [!NOTE]
> 对于 Windows 和半年企业频道，支持的最低版本号可能尚未发布。[了解更多](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)
 
|功能 |Windows |Mac |iOS |Android |Web |
|-----------|-------:|----|----|--------|----|
|[手动应用、更改或删除标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[将默认标签应用于](sensitivity-labels.md#what-label-policies-can-do) 新建文档                                         | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|<[将默认标签应用于](sensitivity-labels.md#what-label-policies-can-do) 已有文档 | 预览： [Beta 频道](https://office.com/insider) | 预览： [Beta 频道](https://office.com/insider) | 审阅中 | 审阅中 | 推出：[是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[需要两端对齐来更改标签](sensitivity-labels.md#what-label-policies-can-do)                     | 当前频道：1910+ <br /><br> 每月企业频道：1910+  <br /><br> 半年企业频道：2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供指向自定义帮助页面的帮助链接](sensitivity-labels.md#what-label-policies-can-do)                       | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[标记内容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[带变量的动态标记](#dynamic-markings-with-variables)                                              | 当前频道：2010+ <br /><br> 每月企业频道：2010+ <br /><br> 半年企业频道：2102+ | 16.42+     | 2.42+ | 16.0.13328+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[现在分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[允许用户分配权限：权限 <br /> - 提示用户](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |当前频道：2004+ <br /><br> 每月企业频道：2004+ <br /><br> 半年企业频道：2008+ | 16.35+   | 审阅中   | 审阅中         | 审阅中                                                        |
|[审核标签相关的用户活动](data-classification-activity-explorer.md)                      | 当前频道：2011+ <br /><br> 每月企业频道：2011+ <br /><br> 半年企业频道：2108+ | 16.43+ | 2.46+ | 16.0.13628+ | 是的 <sup>\*</sup>                                                        |
|[要求用户将标签应用于其电子邮件和文档](#require-users-to-apply-a-label-to-their-email-and-documents)   | 当前频道：2101+ <br /><br> 每月企业频道：2101+ <br /><br> 半年企业频道：2108+ | 16.45+         | 2.47+ | 16.0.13628+ | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md) <br /> - 使用敏感信息类型                    | 当前频道：2009+ <br /><br> 每月企业频道：2009+ <br /><br> 半年企业频道：2102+ | 16.44+  | 审阅中 | 审阅中 | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md) <br /> - 使用可训练分类器                    | 当前频道：2105+ <br /><br> 每月企业频道：2105+ <br /><br> 半年企业频道：2018+ | 审阅中 | 审阅中 | 审阅中 | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[支持对标记文档和加密](sensitivity-labels-coauthoring.md) 创作和自动保存 | 当前频道：2107+ <br /><br> 每月企业频道：2107+ <br /><br> 半年企业频道：正在审阅 |  16.51+ | 审阅中 | 审阅中 | [支持 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**脚注:**

<sup>\*</sup> 目前，不包括用于删除标签或降低分类级别的两端对齐文本

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的敏感度标签功能

列出的数字是每个功能所需的最低 Office 应用程序版本。 

> [!NOTE]
> 对于 Windows 和半年企业频道，支持的最低版本号可能尚未发布。[了解更多](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)

|功能 |Outlook for Windows |Outlook for Mac |iOS 版 Outlook |Android 版 Outlook |Outlook 网页版 |
|-----------|-------------------:|----------------|---------------|-------------------|-------------------|
|[手动应用、更改或删除标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[应用默认标签](sensitivity-labels.md#what-label-policies-can-do)                                         | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[需要两端对齐来更改标签](sensitivity-labels.md#what-label-policies-can-do)                     | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[提供指向自定义帮助页面的帮助链接](sensitivity-labels.md#what-label-policies-can-do)                       | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[标记内容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[带变量的动态标记](#dynamic-markings-with-variables)                                              | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[现在分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[允许用户分配权限： <br /> - 不转发](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 当前频道：1910+ <br /><br> 每月企业频道：1910+ <br /><br> 半年企业频道：2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[允许用户分配权限： <br /> - 仅加密](encryption-sensitivity-labels.md#let-users-assign-permissions)  | 当前频道：2011+ <br /><br> 每月企业频道：2011+ <br /><br> 半年企业频道：2108+ | 16.48+ <sup>\*</sup> | 4.2112.0+  | 4.2112.0+ | 是 |
|[要求用户将标签应用于其电子邮件和文档](#require-users-to-apply-a-label-to-their-email-and-documents)   | 当前频道：2101+ <br /><br> 每月企业频道：2101+ <br /><br> 半年企业频道：2108+ | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | 是                |
|[审核标签相关的用户活动](data-classification-activity-explorer.md) | 当前频道：2011+ <br /><br> 每月企业频道：2011+ <br /><br> 半年企业频道：正在审阅 | 16.51+ <sup>\*</sup> | 4.2126+ | 4.2126+ | 是 |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md) <br /> - 使用敏感信息类型                    | 当前频道：2009+ <br /><br> 每月企业频道：2009+ <br /><br> 半年企业频道：2102+ | 16.44+ <sup>\*</sup>                    | 审阅中           | 审阅中               | 是 |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md) <br /> - 使用可训练分类器                    | 当前频道：2105+ <br /><br> 每月企业频道：2105+ <br /><br> 半年企业频道：2108+ | 审阅中                    | 审阅中           | 审阅中               | 是 |
|[默认标签和强制标签的不同设置](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | 当前频道：2105+ <br /><br> 每月企业频道：2105+ <br /><br> 半年企业频道：2108+ | 16.43+ <sup>\*</sup>                   | 4.2111+           | 4.2111+               | 是 |
|

**Footnotes:**

<sup>\*</sup> 需要新的 [Outlook for Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 内置标签客户端和其他标签解决方案

Office 内置标签客户端从 Microsoft 365 合规中心下载敏感度标签和敏感度标签策略设置。 

若要使用 Office 内置标签客户端，必须具有合规中心发布给用户的一个或多个[标签策略](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)，以及[受支持的 Office 版本](#support-for-sensitivity-label-capabilities-in-apps)。

如果满足以上两个条件，但需要关闭 Office 应用中的内置标签，请使用以下组策略设置：

1. 导航到 **/管理模板/Microsoft Office 2016/安全设置**。

2. 设置 **使用 Office 中的敏感度功能来应用和查看** 0 标签 **0**。 
 
通过使用组策略或 Office 云策略服务中的 [部署此设置](/DeployOffice/overview-office-cloud-policy-service)。 Office 应用重启时，该设置生效。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 内置标签客户端和 Azure 信息保护客户端

如果用户在其 Windows 计算机上安装了 [Azure 信息保护客户端](/azure/information-protection/rms-client/aip-clientv2)，则默认情况下，内置标签在[支持这些标签的 Office 应用](#labeling-client-for-desktop-apps)中处于关闭状态。 由于内置标签不使用由 Azure 信息保护客户端使用的 Office 加载项，因此这些内置标签具有更高的稳定性和更好的性能。 这些内置标签还支持最新功能，例如高级分类器。

我们建议不要卸载 Azure 信息保护客户端，而是防止在 Office 应用中加载 Azure 信息保护加载项。 然后，你可以获取 Office 应用中内置标签的好处，以及 Office 应用之外的 Azure 信息保护客户端标签文件的好处。 例如，Azure 信息保护客户端可以使用文件资源管理器和 PowerShell 标记所有文件类型。 有关 Office 应用外部支持的标签功能的详细信息，请参阅[敏感度标签和 Azure 信息保护](sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)。

若要防止在 Office 应用中加载 Azure 信息保护客户端加载项，请使用组策略设置 **托管加载项列表**，如在 [由于 Office 2013 和 Office 2016 程序的组策略设置而未加载任何加载项](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off)中所述。

对于支持内置标签的 Office 应用，请使用 Microsoft Word 2016、Excel 2016、PowerPoint 2016 和 Outlook 2016 的配置，为 Azure 信息保护客户端指定以下编程标识符 (ProgID)，并将选项设置为 **0 ：始终禁用加载项（阻止）**

|应用程序  |编程标识符  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 

通过使用组策略或 [Office 云策略服务](/DeployOffice/overview-office-cloud-policy-service)部署此设置。

> [!IMPORTANT]
> 若要使用组策略设置“**使用 Office 中的敏感度功能来应用和查看敏感度标签**”，并将其设置为“**1**”，则在某些情况下，Azure 信息保护客户端可能仍会在 Office 应用中加载。在每个应用中阻止加载项加载可阻止这种情况发生。

或者，可以通过交互方式从 Word、Excel、PowerPoint 和 Outlook 禁用或删除“**Microsoft Azure 信息保护**”Office 加载项。 此方法适用于单台计算机和临时测试。 有关说明，请参阅 [Office 程序中查看、管理和安装加载项](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)。 

无论选择哪种方法，更改都将在 Office 应用重新启动时生效。

有关 Azure 信息保护客户端和 Office 内置标签客户端支持哪些功能的详细信息，请参阅从 Azure 信息保护文档中[选择 Windows 标签解决方案](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution)。

## <a name="office-file-types-supported"></a>支持的 Office 文件类型

具有 Word、Excel 和 PowerPoint 文件的内置标签的 Office 应用支持开放 XML 格式（如 .docx 和 .xlsx），但不支持 Microsoft Office 97-2003 格式（如 .doc 和 .xls）、开放文档格式（如 .odt 和 .ods）或其他格式。当文件类型不支持使用内置标签进行标记时，“**敏感度**”按钮在 Office 应用中不可用。

Azure 信息保护统一标签客户端同时支持 Open XML 格式和 Microsoft Office 97-2003 格式。 有关详细信息，请参阅 azure [保护统一标签客户端](/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 管理员指南中支持的类型。

有关其他标签解决方案，请查看其文档，了解支持的文件类型。

## <a name="protection-templates-and-sensitivity-labels"></a>保护模板和敏感度标签

当你使用内置 [时，Office 应用中不会显示管理员定义的](/azure/information-protection/configure-policy-templates)保护模板，例如为 Office 365 邮件加密定义的模板。 这种简化的体验反映无需选择保护模板，因为启用了加密的敏感度标签中包含了相同的设置。

将 [New-Label](/powershell/module/exchange/new-label) cmdlet 与 *EncryptionTemplateId* 参数结合使用时，可以将现有模板转换为敏感度标签。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>信息权限管理 （IRM） 选项和敏感度标签

通过配置以应用加密的敏感度标签，可消除用户指定其加密设置的复杂性。 在许多 Office 应用中，用户仍可使用信息权限管理 （IRM） 选项手动配置这些单独的加密设置。 例如，对于 Windows 应用：

- 对于文档：**文件** > **信息** > **保护** > **限制访问**
- 电子邮件："从" **选项** 选项卡 > **加密** 
  
当用户最初标记文档或电子邮件时，他们可以使用自己的加密设置替代标签配置设置。例如：

- 用户将" **\所有员工"** 标签应用于文档，并且此标签配置为对组织中所有用户应用加密设置。 然后，此用户手动配置 IRM 设置以限制对组织外部用户的访问权限。 结果是一个标记为"机密 **\所有员工** 加密的文档，但您的组织中的用户无法如预期打开它。

- 用户向 **应用"机密\收件人** 标签，此电子邮件配置为应用" **请勿转发"**。 在 Outlook 应用中，此用户随后手动选择“仅加密的 IRM 设置”。 最终结果是虽然电子邮件确实保持加密状态，但收件人仍可以转发此邮件，尽管邮件具有“**机密\仅限收件人**”标签。
    
    作为例外，对于 Outlook 网页版，在当前选定标签应用加密时，用户无法选择“**加密**”菜单中的选项。

- 用户将" **"** 标签应用于文档，并且此标签未配置为应用加密。 然后，此用户手动配置 IRM 设置以限制对文档的访问。 结果是一个标记为"常规 **文档** 这也应用了加密，因此某些用户无法如预期打开它。

如果已标记文档或电子邮件，如果内容尚未加密，或者其具有"导出"或"完全控制" [或完全控制](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) ，用户可以执行这些操作。 

为获得更一致的标签体验和有意义的报告，向用户提供合适的标签和指南，以便仅应用标签以保护文档。例如：

- 对于用户必须分配自己的权限的例外情况，请提供标签 [允许用户向用户分配](encryption-sensitivity-labels.md#let-users-assign-permissions)。 

- 如果用户需要具有相同的分类而无加密标签，则用户无需在选择应用加密的标签后手动删除加密，而是提供子标记替代项。例如：
    - **机密 \ 所有员工**
    - **机密 \ 任何人（无加密）**

- 请考虑禁用 IRM 设置以防止用户选择这些设置：
    - Outlook for Windows： 
        - HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM 中的注册表项 (DWORD:00000001) *DisableDNF* 和 *DisableEO*
        - 确保未配置组策略设置 **配置“加密”按钮的默认加密选项**
    - Outlook for Mac： 
        - 记录在 [设置 Outlook for Mac 首选项](/DeployOffice/mac/preferences-outlook) 中的注册表项 *DisableEncryptOnly* 和 *DisableDoNotForward* 安全设置
    - Outlook 网页版: 
        - 为 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) 记录的参数 *SimplifiedClientAccessDoNotForwardDisabled* 和 *SimplifiedClientAccessEncryptOnlyDisabled*
    - Outlook for iOS 和 Android：这些应用不支持用户在无标签的情况下应用加密，因此无需禁用任何项目。

> [!NOTE]
> 如果用户从存储在SharePoint或OneDrive中的带标签文档中手动删除加密，并且已在[SharePoint和OneDrive中为Office文件启用了敏感性标签](sensitivity-labels-sharepoint-onedrive-files.md)，则下次访问或下载文档时，标签加密将自动恢复。 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>对文件、电子邮件和附件应用敏感度标签

用户一次只能为一个文档或电子邮件应用一个标签。

为包含附件的电子邮件添加标签时，只有当应用于电子邮件的标签应用加密且附件为 Office 文档时，附件才继承此标签。由于继承的标签应用加密，附件将采用新加密方式。

当应用于电子邮件的标签不应用加密或附件已加密时，附件不会继承电子邮件的标签。

标签继承示例，其中标签 **机密** 加密，"常规" **标签** 不适用加密：

- 用户创建新电子邮件，并对此邮件 **机密** 标签。 然后，他们添加未标记或加密的 Word 文档。 继承后，文档新标记 **机密** 标签中应用加密。

- 用户创建新电子邮件，并对此邮件 **机密** 标签。 然后，他们添加一个标记为"常规 **的 Word** 并且此文件未进行加密。 继承后，文档将重新标记为机密 **标签** 已应用加密。

## <a name="sensitivity-label-compatibility"></a>敏感度标签兼容性

**使用 RMS 标记的应用**：如果在 [RMS 支持的应用程序](/azure/information-protection/requirements-applications#rms-enlightened-applications) 中打开标签和加密的文档或电子邮件但不支持敏感度标签，则应用仍实施加密和权限管理。

**使用 Azure 信息保护客户端**：可以使用 Azure 信息保护客户端及其他方式，通过 Office 内置标签客户端查看和更改应用于文档和电子邮件的敏感度标签。

**对于其他版本的 Office**：任何授权用户都可以在其他版本的 Office 中打开标记的文档和电子邮件。 但是，你只能使用 Azure 信息保护客户端查看或更改受支持 Office 版本中的标签。 支持的 Office 应用版本列于上一节 [一](#support-for-sensitivity-label-capabilities-in-apps)。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支持通过敏感度标签保护的 SharePoint 和 OneDrive 文件

若要对 SharePoint 或 OneDrive 中的文档使用 Office 网页内置标签客户端，请确保对 SharePoint 和 OneDrive [中 Office 文件启用了敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="support-for-external-users-and-labeled-content"></a>支持外部用户和标记的内容

标记文档或电子邮件时，标签会存储为包含租户和标签 GUID 的元数据。 支持敏感度标签的 Office 应用打开标记的文档或电子邮件时，只要用户属于同一租户，该标签才显示于其应用中。 例如，对于 Word、PowerPoint 和 Excel 的内置标签，标签名称显示在状态栏上。 

这意味着如果与使用不同标签名称的组织共享文档，则每个组织可应用并查看应用于文档的标签。 但是，应用标签中的以下元素对组织外部用户可见：

- 内容标记。当标签应用页眉、页脚或水印时，这些内容将直接添加到内容中，在某人修改或删除它们之前保持可见。

- 应用加密的标签中的基础保护模板的名称和说明。 此信息显示在文档顶部的消息栏中，提供有关谁有权打开该文档以及其针对该文档的使用权限的信息。

### <a name="sharing-encrypted-documents-with-external-users"></a>与外部用户共享加密文档

除了限制自己组织中用户的访问权限，还可以扩展对 Azure Active Directory 中拥有帐户的其他用户的访问权限。 但是，如果你的组织使用条件访问策略，请参阅 [部分](#conditional-access-policies) 了解其他注意事项。

所有 Office 应用 [RMS 型应用程序](/azure/information-protection/requirements-applications#rms-enlightened-applications) 用户成功验证后，可打开加密文档。 

如果外部用户在 Azure Active Directory 中没有帐户，他们可以通过在租户中使用来宾帐户进行身份验证。 当对 SharePoint 和 OneDrive 中的 Office 文件启用了 [敏感度标签时，这些来宾帐户也可用于访问 SharePoint 或 OneDrive 中的共享](sensitivity-labels-sharepoint-onedrive-files.md)：

- 一个选择是自己创建这些来宾帐户。 你可以指定这些用户已使用的任何电子邮件地址。 例如，他们的 Gmail 地址。
    
    此选项的优点是，可在加密设置中指定特定用户的电子邮件地址，从而限制特定用户的访问和权限。 其费用表示创建帐户和管理标签配置时的管理开销。

- 另一个选项是使用 [SharePoint 和 OneDrive 与 Azure AD B2B 的集成](/sharepoint/sharepoint-azureb2b-integration)，以便用户共享链接时自动创建来宾帐户。
    
    此选项的优点是最低管理开销，因为会自动创建帐户，并且标签配置更简单。 对于此方案，必须先选择加密 [添加任何经过身份验证的用户](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) 因为事先不知道电子邮件地址。 请注意，此设置不允许限制特定用户的访问和使用权限。

使用 Windows 和 Microsoft 365 应用（以前[Office 365 应用](/deployoffice/name-change)）或 Office 2019 独立版本时，外部用户也可使用 Microsoft 帐户打开加密文档。 最近支持在其他平台中打开加密文档，Microsoft 帐户也支持在 macOS（Microsoft 365 应用，版本 16.42+）、Android（版本 16.0.13029+）和 iOS（版本 2.42+）上打开加密文档。 例如，组织中用户与组织外部的用户共享加密文档，并且加密设置为外部用户指定 Gmail 电子邮件地址。 此外部用户可以创建自己的使用其 Gmail 电子邮件地址的 Microsoft 帐户。 然后，在登录此帐户后，可根据指定的使用限制打开并编辑该文档。 有关此方案的演练示例，请参阅 [并编辑受保护的文档](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)。

> [!NOTE]
> Microsoft 帐户的电子邮件地址必须匹配指定用于限制加密设置访问的电子邮件地址。

当具有 Microsoft 帐户的用户如此打开加密文档时，如果同名来宾帐户不存在，将自动为租户创建来宾帐户。 当来宾帐户存在时，除了从支持的桌面和移动 Office 应用打开加密文档外，它还可在 SharePoint 和 OneDrive 中利用 Office 网页版打开文档。

但由于复制延迟，此方案不会立即创建自动来宾帐户。 如果指定个人电子邮件地址作为标签加密设置的一部分，建议在 Azure Active Directory 中创建相应的来宾帐户。 然后告知这些用户必须使用此帐户从组织打开加密文档。

> [!TIP]
> 因为不能确保外部用户将使用受支持的 Office 客户端应用，因此在创建来宾帐户（适用于特定用户）之后或者在使用 [SharePoint 和 OneDrive 与 Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) （任何经过身份验证的用户）集成时，共享 SharePoint 和 OneDrive 中的链接是支持与外部用户安全协作的更可靠方法。

### <a name="conditional-access-policies"></a>条件访问策略

如果你的组织已实施 [Microsoft Azure Active Directory 条件访问策略](/azure/active-directory/conditional-access/overview)，请检查相应策略的配置。如果策略包括 **Microsoft Azure 信息保护** 并且该策略扩展到外部用户，则这些外部用户在租户中必须具有来宾帐户，即使他们在其自己的租户中拥有 Azure AD 帐户。

如不使用该访客帐户，则他们无法打开加密的文档并看到错误消息。消息文本可能会告知他们需要将其帐户添加为租户中的外部用户，且此方案说明不正确 **请注销，然后使用不同的 Azure Active Directory 用户帐户**。

如果无法针对需要打开通过标签加密的文档的外部用户，在租户中创建和配置来宾帐户，则必须从条件访问策略中删除 Azure 信息保护，或者从策略中排除外部用户。

有关条件访问和 Azure 信息保护（敏感度标签使用的加密服务）详细信息，请参阅常见问题 ["Azure 信息保护"列为可用于条件访问的可用云应用 - 此应用是如何工作的？](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office 应用应用标记和加密时

Office 应用应用的内容标记和加密与敏感度标签不同，具体取决于你使用的应用。

| 应用 | 内容标记 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel 和 PowerPoint | 立即 | 立即 |
| Outlook for PC 和 Outlook for Mac | Exchange Online 发送电子邮件后 | 立即 |
| 网页版、iOS 版和 Android 版 Outlook | Exchange Online 发送电子邮件后 | Exchange Online 发送电子邮件后 |
|

将敏感度标签应用于 Office 应用外部文件的解决方案会通过向文件应用标签元数据来实现此限制。 在这种情况下，从标签的配置标记的内容不会插入文件，但会应用加密。 

在 Office 桌面应用中打开这些文件时，首次保存文件时，Azure 信息保护统一标签客户端将自动应用标记的内容。 对桌面、移动或 Web 应用使用内置标签时，标记的内容不会自动应用。

包括应用 Office 应用外部敏感度标签的方案包括：

- 来自 Azure 信息保护统一标签客户端的扫描仪、文件资源管理器和 PowerShell 

- SharePoint 和 OneDrive 的自动标记策略

- 从 Power BI 导出标记和加密的数据

- Microsoft Defender for Cloud Apps

对于这些方案，使用 Office 应用时，具有内置标签的用户可以通过临时删除或替换当前标签，然后重新应用原始标签来应用标签的内容。

### <a name="dynamic-markings-with-variables"></a>带变量的动态标记

> [!IMPORTANT]
> 目前，并非所有平台上的应用都支持动态内容标记，可标记页眉、页脚和水印。 对于不支持此功能的应用，其将标记应用为标签配置中指定的原始文本，而不是解决变量。
> 
> Azure 信息保护统一标签客户端支持动态标记。对于内置于 Office 应用的标签，请参阅此页面上[功能](#support-for-sensitivity-label-capabilities-in-apps)中的表格，了解支持的最低版本。

为标记内容配置敏感度标签时，可以在文本字符串中为页眉、页脚或水印使用以下变量：

| 变量 | 说明 | 应用标签时的示例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 已应用的标签的显示名称 | **常规**|
| `${Item.Name}` | 被标签内容的文件名或电子邮件主题 | **Sales.docx** |
| `${Item.Location}` | 被标签的文档的路径和文件名，或者标记的电子邮件的电子邮件主题 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 显示应用标签的用户名称 | **Richard Simone** |
| `${User.PrincipalName}` | 应用标签的用户的 Azure AD 用户主体名称 （UPN） | **rsimone\@contoso.com** |
| `${Event.DateTime}` | 标记内容的日期和时间，以应用 Microsoft 365 应用中应用标签的用户的本地时区，或 Office Online 和自动标签策略的 UTC（协调世界时）表示 | **2020/8/10 下午 1：30** |

> [!NOTE]
> 这些变量的语法区分大小写。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>为 Word、Excel、PowerPoint 和 Outlook 设置不同的视觉标记

作为一个附加变量，您可以通过在文本字符串中使用"If.App"变量语句来配置每个 Office 应用程序类型的视觉标记，并且使用值 **Word**、 **Excel**、 **PowerPoint** 或 **Outlook** 来标识应用程序类型。 如果要在同一个语句中指定多个值，也可缩简这些值，If.App 值。

使用以下语法：

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

与其他动态视觉标记一样，语法区分大小写，其中包括每个应用程序类型 (WEPO) 的缩写。

示例：

- **仅设置 Word 文档的页眉文本：**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    标签仅应用于 Word 文档标题，可应用标题文本"此 Word 文档很敏感"。 标题文本不应用于其他 Office 应用程序。

- **为 Word、Excel 和 Outlook 设置页脚文本，以及 PowerPoint 的不同页脚文本：**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    在 Word、Excel 和 Outlook 中，标签将应用页脚文本"此内容是机密的"。 在 PowerPoint 中，标签将应用页脚文本"此演示文稿是机密的"。

- **为 Word 和 PowerPoint 设置特定水印文本，然后为 Word、Excel 和 PowerPoint 设置水印文本：**

    `${If.App.WP}This content is ${If.End}Confidential`

    在 Word 和 PowerPoint 中，标签将应用水印文本"此内容为机密"。 在 Excel 中，标签应用水印文字"机密"。 在 Outlook 中，标签不应用任何水印文本，因为 Outlook 不支持水印作为视觉标记。

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>要求用户为其电子邮件和文档应用标签

> [!IMPORTANT]
> 
> [Azure 信息保护统一标签客户端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)支持该配置（也称为“必需标签”）。对于内置于 Office 应用的标签，请参阅此页面上的[功能](#support-for-sensitivity-label-capabilities-in-apps)部分中的表格，了解最低版本要求。
>
> 要对文档而不是电子邮件使用强制标签，请参阅下一节中说明如何配置 Outlook 特定选项的指示。
> 
> 要对 Power BI 使用强制标签，请参阅 [Power BI 的强制标签策略](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy)。

选择 **要求用户将标签应用于其电子邮件和文档** 策略设置后，分配了策略的用户必须在以下情况下选择并应用敏感度标签：

- 对于 Azure 信息保护统一标签客户端：
    - 对于文档（Word、Excel、PowerPoint）：保存未标记的文档时或用户关闭该文档时。
    - 对于电子邮件 （Outlook）：用户发送无标记的邮件。

- 对于内置 Office 应用的标签：
    - 对于文档（Word、Excel、PowerPoint）：打开或保存无标记的文档时。
    - 对于电子邮件 （Outlook）：用户发送无标记的电子邮件。

内置标签的其他信息：

- 当系统提示用户添加敏感度标签时，因为他们打开了一个无标记的文档，他们可添加标签，或者选择在只读模式下打开文档。

- 当强制标签生效时，用户不能从文档中删除敏感度标签，但可以更改现有标签。

有关何时使用此设置的指导，请参阅有关策略 [设置](sensitivity-labels.md#what-label-policies-can-do)。

> [!NOTE]
> 如果要对文档和电子邮件使用默认标签策略设置以及强制标签设置： 
>
> 默认标签始终优先于必需标签。 但是，对于文档，Azure 信息保护统一标签客户端将默认标签应用于所有无标记的文档，而内置标签将默认标签应用于新文档，而非未标记的现有文档。 此行为差异意味着在将强制标签用于默认标签设置时，系统可能提示用户在使用内置标签时比使用 Azure 信息保护统一标签客户端时更频繁地应用敏感度标签。
> 
> 现在推出：使用内置标签并支持现有文档使用默认标签的 Office 应用。 有关详细信息，请参阅 word、Excel 和 PowerPoint 的 [功能表](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)。

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>Outlook 特定的默认标签和强制标签选项

对于内置标签，请使用此页上的 [Outlook 功能表](#sensitivity-label-capabilities-in-outlook)以及 **默认标签和强制标签的不同设置** 行来标识支持这些功能的最低版本 Outlook。Azure 信息保护统一标签客户端的所有版本均支持这些特定于 Outlook 的选项。

Outlook 应用支持的默认标签设置与文档的默认标签设置不同时：

- 在标签策略向导的 **将默认标签应用于电子邮件** 页面，可指定将应用于所有未标记电子邮件的敏感度标签选项，或指定无默认标签。 此设置独立于向导中之前 **文档策略设置** 页面上的 **默认将此标签应用于文档** 设置。

如果 Outlook 应用不支持与文档的默认标签设置不同的默认标签设置：Outlook 将始终使用你为标签策略向导的 **文档策略设置** 页面上 **默认将此标签应用于文档** 指定的值。

当 Outlook 应用支持关闭强制标签时：

- 在标签策略向导的 **策略设置** 页面上，选择 **要求用户向其电子邮件或文档应用标签**。 然后选择“**下一步**” > “**下一步**”，并清除复选框“**要求用户向电子邮件应用标签**”。 如果要对电子邮件和文档应用强制标签，请保持选中复选框。

当 Outlook 应用不支持关闭强制标签时：如果选择“**要求用户向其电子邮件或文档应用标签**”作为策略设置，Outlook 将始终提示用户为未标记的电子邮件选择标签。

> [!NOTE]
> 如果已通过使用 [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) 或 [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy) cmdlet 配置 PowerShell 高级设置 **OutlookDefaultLabel** 和 **DisableMandatoryInOutlook**：
> 
> 为这些 PowerShell 设置选择的值将反映在标签策略向导中，并自动适用于支持这些设置的 Outlook 应用。 其他 PowerShell 高级设置仍然仅支持 Azure 信息保护统一标签客户端。

## <a name="end-user-documentation"></a>最终用户文档

- [在Office 的文件和电子邮件中应用敏感度标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office 中敏感度标签的已知问题](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [向 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [有关自动应用或建议敏感度标签的已知问题](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
