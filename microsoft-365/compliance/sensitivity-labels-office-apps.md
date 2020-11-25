---
title: 在 Office 应用中使用敏感度标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解用户如何在 Office 应用程序中使用桌面、移动和 web Office 应用程序中的敏感度标签，以及哪些应用程序支持灵敏度标签。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b616a25f4e130f7b73b82e80bf82136c229d5efd
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409199"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>在 Office 应用中使用敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

当您从 Microsoft 365 合规性中心或等效标签中心 [发布](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 灵敏度标签时，它们将开始显示在 Office 应用程序中，以便用户可以在创建或编辑数据时对其进行分类和保护。

使用本文中的信息可帮助您在 Office 应用程序中成功管理敏感度标签。 例如，确定需要支持内置标签的应用程序的最低版本，并了解与其他应用程序和服务的 Azure 信息保护统一标签客户端和兼容性的交互。

## <a name="labeling-client-for-desktop-apps"></a>为桌面应用程序标记客户端

若要使用内置于 Windows 和 Mac 的 Office 桌面应用程序的敏感度标签，必须使用 Office 的订阅版本。 此标签客户端不支持独立版本的 Office，如 Office 2016 或 Office 2019。

若要在 Windows 计算机上将敏感度标签与这些独立版本的 Office 配合使用，请安装 [Azure 信息保护统一标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>支持应用程序中的敏感度标签功能

对于每项功能，下表列出了该应用程序为支持使用内置标签的敏感度标签所需的最低 Office 版本。 或者，如果标签功能处于公共预览或正在审阅中，以供将来的版本使用。 使用 [Microsoft 365 路线图](https://aka.ms/MIPC/Roadmap) 获取有关未来版本的详细信息。

新版本的 Office 应用程序将在不同的时间为不同的更新频道提供。 有关详细信息，包括如何配置更新频道以便能够测试您感兴趣的新标记功能，请参阅 [Microsoft 365 应用的更新通道概述](https://docs.microsoft.com/DeployOffice/overview-update-channels)。 专用预览中的新功能不包含在表中，但您可能可以通过 nominating 您的组织来加入 [Microsoft 信息保护专用预览计划](https://aka.ms/mip-preview)，从而加入这些预览。

> [!NOTE]
> 最近更改了 Office 应用的更新通道的名称。 例如，"每月频道" 现在是 "当前频道"，Office 预览体验成员现已成为 Beta 频道。 有关详细信息，请参阅 [对 Microsoft 365 应用更新频道的更改](https://docs.microsoft.com/deployoffice/update-channels-changes)。

在安装仅在 Windows 计算机上运行的 Azure 信息保护统一标记客户端时，可以使用其他功能。 有关这些详细信息，请参阅 [比较 Windows 计算机的标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 和 PowerPoint 中的敏感度标签功能

对于 iOS 和 Android：其中列出了最低版本， [Office 应用程序](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)也支持敏感度标签功能。

|功能                                                                                                        |Windows 桌面 |Mac 桌面 |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手动应用、更改或删除标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[应用默认标签](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[需要调整以更改标签](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供指向自定义帮助页的 "帮助" 链接](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[标记内容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[带有变量的动态标记](#dynamic-markings-with-variables)                                              | 2010 +           | 16.42 +     | 2.42 + | 16.0.13328 + | 正在审阅 |
|[立即分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[允许用户分配权限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004 + | 16.35 +   | 正在审阅   | 正在审阅         | 正在审阅                                                        |
|[查看标签使用情况标签分析](label-analytics.md) 并为管理员发送数据                      | 正在审阅            | 正在审阅        | 正在审阅   | 正在审阅         | 是的 <sup>\*</sup>                                                        |
|[要求用户对其电子邮件和文档应用标签](sensitivity-labels.md#what-label-policies-can-do)   | 正在审阅            | 正在审阅        | 正在审阅   | 正在审阅         | 正在审阅                                                        |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)                    | 2009 +                                  | Word 和 PowerPoint 的预览：滚动到 [当前频道 (预览) ](https://office.com/insider) | 正在审阅 | 正在审阅 | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|支持在标签和受保护的文档上的[自动保存](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)和[共同创作](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) | 正在审阅 | 正在审阅 | 正在审阅 | 正在审阅 | [是-自愿加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**脚注**

<sup>\*</sup> 目前，不包含调整文本以删除标签或降低分类级别

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的敏感度标签功能

|功能                                                                                                        |Windows 桌面上的 Outlook |Mac 桌面上的 Outlook  |iOS 版 Outlook |Android 版 Outlook |Outlook 网页版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手动应用、更改或删除标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[应用默认标签](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[需要调整以更改标签](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[提供指向自定义帮助页的 "帮助" 链接](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[标记内容](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[带有变量的动态标记](#dynamic-markings-with-variables)                                              | 正在审阅                     | 正在审阅                 | 正在审阅         | 正在审阅           | 正在审阅               |
|[立即分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[允许用户分配权限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[查看标签使用情况标签分析](label-analytics.md) 并为管理员发送数据                      | 正在审阅                       | 正在审阅                    | 正在审阅           | 正在审阅               | 是               |
|[要求用户对其电子邮件和文档应用标签](sensitivity-labels.md#what-label-policies-can-do)   | 正在审阅                       | 正在审阅                    | 正在审阅           | 正在审阅               | 正在审阅               |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)                    | 2009 +                      | 正在审阅                    | 正在审阅           | 正在审阅               | 是 |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 内置标签客户端和其他标记解决方案

Office 内置标签客户端从以下管理中心下载灵敏度标签和敏感度标签策略设置：

- Microsoft 365 合规中心
- Microsoft 365 安全中心
- Office 365 安全与合规中心

若要使用 Office 内置标签客户端，必须向用户发布一个或多个从列出的管理中心和[受支持的 Office 版本](#support-for-sensitivity-label-capabilities-in-apps)[发布的标签策略](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。

如果满足这两个条件，但需要关闭 Office 内置标签客户端，请使用以下组策略设置：

1. 导航到 " **用户配置/管理模板/Microsoft Office 2016/安全设置**"。

2. Set **使用 Office 中的灵敏度功能将敏感度标签应用于** **0** 并将其查看。 
 
通过使用组策略或使用 [Office 云策略服务](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)部署此设置。 该设置将在 Office 应用程序重新启动时生效。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 内置标签客户端和 Azure 信息保护客户端

如果用户安装了 ([统一标签客户](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) 端或 [经典客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)) 的 Azure 信息保护客户端之一，默认情况下，内置标签客户端在其 Office 应用中处于关闭状态。 

若要使用内置标签而不是 Azure 信息保护客户端的 Office 应用，请使用上一节中的说明，但设置组策略设置 **使用 Office 中的敏感度功能将敏感度标签应用并查看** 为 **1**。 

或者，禁用或删除 Office 加载项 " **Azure 信息保护**"。 此方法适用于一台计算机和临时测试。 有关说明，请参阅 [在 Office 程序中查看、管理和安装加载项](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)。 

当您禁用或删除此 Office 加载项时，将保持安装的 Azure 信息保护客户端，以便您可以继续标记 Office 应用外部的文件。 例如，通过使用文件资源管理器或 PowerShell。

有关 Azure 信息保护客户端和 Office 内置标签客户端支持的功能的信息，请参阅从 Azure 信息保护文档中 [选择用于 Windows 计算机的标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) 。

## <a name="office-file-types-supported"></a>支持的 Office 文件类型

对 Word、Excel 和 PowerPoint 文件使用内置标签的 Office 应用支持 Open XML 格式 (如 .docx 和 .xlsx) ，而不是 Microsoft Office 97-2003 格式 (如 .doc 和 .xls) 。 如果某个文件类型不支持内置标签，则 " **敏感度** " 按钮在 Office 应用中不可用。

Azure 信息保护统一标签客户端支持 Open XML 格式和 Microsoft Office 97-2003 格式。 有关详细信息，请参阅该客户端的管理员指南中的 [Azure 信息保护统一标记客户端支持的文件类型](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 。

有关其他标记解决方案，请查看文档中支持的文件类型。

## <a name="protection-templates-and-sensitivity-labels"></a>保护模板和敏感度标签

在使用内置标记时，管理员定义的 [保护模板](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)（如您为 Office 365 邮件加密定义的模板）在 Office 应用中不可见。 这种简化的体验反映了无需选择保护模板，因为具有已启用加密功能的敏感度标签中包含相同的设置。

如果需要将现有保护模板转换为标签，请使用 Azure 门户和以下说明： [将模板转换为标签](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a> (IRM) 选项和敏感度标签的信息权限管理

为应用加密而配置的敏感度标签消除了用户的复杂性，以指定自己的加密设置。 在许多 Office 应用程序中，用户仍然可以使用信息权限管理 (IRM) 选项手动配置这些单独的加密设置。 例如，对于 Windows 应用：

- 对于文档：**文件**  >  **信息**  >  **保护文档**  >  **限制访问**
- 对于电子邮件：从 " **选项** " 选项卡中 > **加密** 
  
用户最初标记文档或电子邮件时，他们始终可以使用自己的加密设置覆盖您的标签配置设置。 例如：

- 用户将 " **机密 \ 所有雇员** " 标签应用于文档，此标签配置为对组织中的所有用户应用加密设置。 然后，此用户可手动配置 IRM 设置，以限制对组织外部用户的访问。 最终结果是标记为 " **机密 \ 所有员工** 并进行加密" 的文档，但组织中的用户无法按预期方式打开它。

- 用户将 "机密" " **仅限收件人** " 标签应用于电子邮件，此电子邮件配置为应用 "不 **转发**" 的加密设置。 然后，此用户手动配置 IRM 设置，使该电子邮件不受限制。 最终结果是，尽管拥有机密的 " **仅收件人** " 标签，也可以将电子邮件转发给收件人。

- 用户将 " **常规** " 标签应用于文档，并且此标签未配置为 "应用加密"。 然后，此用户可手动配置 IRM 设置以限制对文档的访问。 最终结果是一个标签为 " **常规** " 但也采用加密的文档，以便某些用户无法按预期方式打开它。

如果已标记文档或电子邮件，则用户可以执行这些操作中的任何操作（如果内容尚未加密），或者具有 [使用权限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) 导出或完全控制。 

若要获得具有有意义的报告的更一致的标签体验，请提供适当的标签和指导，以供用户仅应用标签来保护文档。 例如：

- 对于用户必须分配其自己的权限的例外情况，请提供 [允许用户分配其自己的权限](encryption-sensitivity-labels.md#let-users-assign-permissions)的标签。 

- 当用户需要具有相同分类但不加密的标签时，请提供选项替代方法，而不是用户在选择应用了加密的标签后手动删除加密。 例如：
    - **机密 \ 所有员工**
    - **机密 \ 任何人 (无加密)**

> [!NOTE]
> 如果用户从存储在 SharePoint 或 OneDrive 中的标记文档中手动删除加密，并且已 [对 sharepoint 和 onedrive 中的 Office 文件启用了敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)，则下次访问或下载该文档时，将自动还原标签加密。 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>将敏感度标签应用于文件、电子邮件和附件

用户可以一次仅为每个文档或电子邮件应用一个标签。

当您标记包含附件的电子邮件时，附件不会继承标签，但有一个例外：

- 附件是标签不适用的 Office 文档，并且应用于电子邮件的标签将应用加密。 在这种情况下，电子邮件的 Office 文档会将电子邮件的标签继承为其加密设置。

或者： 

- 如果附件具有标签，则保留其最初应用的标签。
- 如果在没有标签的情况下加密附件，则会保留加密但不会对其进行标记。
- 如果附件没有标签，它们将保持未标记。

## <a name="sensitivity-label-compatibility"></a>敏感度标签兼容性

**对于智能型应用**：如果在不支持敏感度标签的 [RMS 智能型应用程序](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 中打开已标记和加密的文档或电子邮件，则应用仍强制实施加密和权限管理。

**使用 Azure 信息保护客户端**：您可以使用 Azure 信息保护客户端和其他方法查看和更改应用于 Office 内置标记客户端的文档和电子邮件的敏感度标签。

**与其他版本的 office**：任何授权的用户都可以在其他版本的 office 中打开带标签的文档和电子邮件。 但是，只能在受支持的 Office 版本中或通过使用 Azure 信息保护客户端来查看或更改标签。 [上一节](#support-for-sensitivity-label-capabilities-in-apps)中列出了受支持的 Office 应用程序版本。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支持由敏感度标签保护的 SharePoint 和 OneDrive 文件

若要对 SharePoint 或 OneDrive 中的文档使用 office 内置标签客户端与 Office 网页版，请确保已 [在 sharepoint 和 onedrive 中为 Office 文件启用了敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="support-for-external-users-and-labeled-content"></a>支持外部用户和带标签的内容

当您标记文档或电子邮件时，该标签将存储为包括租户和标签 GUID 的元数据。 当支持敏感度标签的 Office 应用打开带标签的文档或电子邮件时，将读取此元数据，并且只有当该用户属于同一租户时，该标签才会显示在其应用中。 例如，对于 Word、PowerPoint 和 Excel 的内置标签，标签名称将显示在状态栏上。 

这意味着，如果您与使用不同标签名称的其他组织共享文档，则每个组织都可以应用并查看其自己的标签应用于该文档的标签。 但是，在您的组织外部的用户可以看到已应用标签中的以下元素：

- 内容标记。 当标签应用页眉、页脚或水印时，它们将直接添加到内容中并保持可见，直到有人修改或删除它们。

- 来自应用了加密的标签的基础保护模板的名称和说明。 此信息显示在文档顶部的消息栏中，以提供有关有权打开文档的用户的信息，以及该文档的使用权限。

### <a name="sharing-encrypted-documents-with-external-users"></a>与外部用户共享加密文档

除了限制对自己组织中的用户的访问之外，还可以将访问权限扩展到在 Azure Active Directory 中具有帐户的任何其他用户。 在用户成功通过身份验证后，所有 Office 应用和其他智能型 [应用程序](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 都可以打开加密的文档。

如果外部用户在 Azure Active Directory 中没有帐户，则可以在租户中为其创建一个来宾帐户。 对于其电子邮件地址，您可以指定他们已使用的任何电子邮件地址。 例如，它们的 Gmail 地址。 当您在 [sharepoint 和 onedrive 中为 Office 文件启用了敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)时，也可以使用此来宾帐户访问 Sharepoint 或 onedrive 中的共享文档。

外部用户也可以在使用 Microsoft 365 应用程序时，使用 microsoft 帐户) 在 Windows 上 ([以前的 Office 365 应用程序](https://docs.microsoft.com/deployoffice/name-change) ，并在 macOS (version 16.42 +) 、Android (version 13029 +) 和 iOS (版本 2.42 +) 中新支持。 例如，有人与一个加密的文档共享一个加密的文档，而加密设置则指定其 Gmail 电子邮件地址。 此用户可以创建自己的使用 Gmail 电子邮件地址的 Microsoft 帐户。 然后，在使用此帐户登录后，用户可以打开文档并对其进行编辑，具体取决于为该用户指定的使用限制。 有关此方案的演练示例，请参阅 [打开和编辑受保护的文档](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)。

> [!NOTE]
> Microsoft 帐户的电子邮件地址必须与指定用于限制加密设置访问权限的电子邮件地址相匹配。

当使用 Microsoft 帐户的用户以这种方式打开加密文档时，如果具有相同名称的来宾帐户尚不存在，则会自动为该租户创建来宾帐户。 如果来宾帐户存在，则它可用于在 SharePoint 和 OneDrive 中打开文档，方法是使用 web 上的浏览器 (Office) ，以及从 Windows 桌面应用程序中打开加密的文档。 

但是，由于复制延迟，自动来宾帐户不会立即创建。 如果您将个人电子邮件地址指定为标签加密设置的一部分，我们建议您在 Azure Active Directory 中创建相应的来宾帐户。 然后，让这些用户知道他们必须使用此帐户从您的组织中打开加密的文档。

> [!TIP]
> 由于您无法确定外部用户将使用受支持的 Office 客户端应用程序，因此，在创建来宾帐户后共享 SharePoint 和 OneDrive 中的链接是更可靠的方法来支持与外部用户进行安全协作。

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office 应用程序何时应用内容标记和加密

Office 应用程序使用敏感度标签以不同方式应用内容标记和加密，具体取决于您使用的应用程序。

| 应用 | 内容标记 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel 和 PowerPoint | 立即 | 立即 |
| Outlook for PC 和 Outlook for Mac | Exchange Online 发送电子邮件后 | 立即 |
| 网页版、iOS 版和 Android 版 Outlook | Exchange Online 发送电子邮件后 | Exchange Online 发送电子邮件后 |
|

将敏感度标签应用于 Office 应用程序之外的文件的解决方案通过将标记元数据应用于文件来实现。 在这种情况下，从标签的配置中标记的内容不会插入到文件中，但会应用加密。 

在 Office 桌面应用程序中打开这些文件时，Azure 信息保护统一标记客户端将自动应用内容标记。 将内置标签用于桌面、移动或 web 应用时，不会自动应用内容标记。

包括在 Office 应用程序外部应用敏感度标签的方案包括：

- 来自 Azure 信息保护统一标签客户端的扫描程序、文件资源管理器和 PowerShell 

- SharePoint 和 OneDrive 的自动标记策略

- 从 Power BI 导出的标记和加密的数据

- Microsoft 云应用安全

对于这些方案，使用内置标签的用户可以通过临时删除或替换当前标签，然后重新应用原始标签来应用标签的内容标记。

### <a name="dynamic-markings-with-variables"></a>带有变量的动态标记

> [!IMPORTANT]
> 目前，并非所有平台上的所有应用程序都支持动态内容标记，您可以为页眉、页脚和水印指定这些标记。 对于不支持此功能的应用程序，这些应用程序会将标记应用为标签配置中指定的原始文本，而不是解析这些变量。
> 
> Azure 信息保护统一标签客户端支持动态标记。 有关内置于 Office 的标记，请参阅此页上 " [功能](#support-for-sensitivity-label-capabilities-in-apps) " 部分中的表。

为内容标记配置敏感度标签时，可以在页眉、页脚或水印的文本字符串中使用以下变量：

| 变量 | 说明 | 应用标签的示例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 当前标签显示名称 | **常规**|
| `${Item.Name}` | 当前文件名或电子邮件主题 | **Sales.docx** |
| `${Item.Location}` | 文档的当前路径和文件名，或电子邮件的电子邮件主题 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 当前用户显示名称  | **Richard Simone** |
| `${User.PrincipalName}` | 当前用户的 Azure AD 用户主体名称 (UPN)  | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | 本地时区的当前日期和时间 | **8/10/2020 1:30 PM** |

> [!NOTE]
> 这些变量的语法区分大小写。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>为 Word、Excel、PowerPoint 和 Outlook 设置不同的视觉标记

作为一个额外的变量，可以使用文本字符串中的 "If. App" 变量语句来配置每个 Office 应用程序类型的可视标记，并使用值 **Word**、 **Excel**、 **PowerPoint** 或 **Outlook** 标识应用程序类型。 您还可以缩写这些值，如果要在同一个 If 应用程序语句中指定多个值，则这是必需的。

> [!NOTE]
> 由于目前仅受 Azure 信息保护统一标记客户端支持，因此包含 Outlook 的说明是完整的。

使用以下语法：

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

与其他动态视觉标记一样，语法区分大小写。

示例：

- **仅设置 Word 文档的页眉文本：**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    仅在 Word 文档头中，标签应用标题文本 "此 Word 文档是敏感文档"。 不会向其他 Office 应用程序应用任何标题文本。

- **设置 Word、Excel 和 Outlook 的页脚文本和 PowerPoint 的不同页脚文本：**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    在 Word、Excel 和 Outlook 中，标签应用页脚文本 "此内容是机密"。 在 PowerPoint 中，标签应用页脚文本 "此演示文稿是保密的"。

- **为 word 和 PowerPoint 设置特定的水印文本，然后为 Word、Excel 和 PowerPoint 设置水印文本：**

    `${If.App.WP}This content is ${If.End}Confidential`

    在 Word 和 PowerPoint 中，标签应用水印文本 "此内容是机密"。 在 Excel 中，标签应用水印文本 "保密"。 在 Outlook 中，标签不会应用任何水印文本，因为 Outlook 不支持将水印用作视觉标记。

## <a name="end-user-documentation"></a>最终用户文档

- [将敏感度标签应用于 Office 文档和电子邮件](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [将敏感度标签应用于 Office 文件时的已知问题](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
