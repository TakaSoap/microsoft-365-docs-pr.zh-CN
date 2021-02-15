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
description: 了解用户在适用于桌面、移动和 Web 的 Office 应用中如何使用敏感度标签，以及哪些应用支持敏感度标签。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95da9753d773e3bb9724a8d0ae2ab0e2f2618c27
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233714"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>在 Office 应用中使用敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

从 Microsoft [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 365 合规中心或等效标签中心发布敏感度标签后，它们开始显示在 Office 应用中，以便用户在创建或编辑数据时对数据进行分类和保护。

使用本文中的信息可帮助您成功管理 Office 应用中的敏感度标签。 例如，确定支持内置标签所需的应用的最低版本，并了解与 Azure 信息保护统一标签客户端的交互以及与其他应用和服务兼容性。

## <a name="labeling-client-for-desktop-apps"></a>桌面应用的标签客户端

若要使用内置于适用于 Windows 和 Mac 的 Office 桌面应用程序中的敏感度标签，必须使用 Office 订阅版本。 此标记客户端不支持 Office 的独立版本，如 Office 2016 或 Office 2019。

若要在 Windows 计算机上将敏感度标签与这些独立版本的 Office 一同使用，请安装 [Azure 信息保护统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)。

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>支持应用中的敏感度标签功能

对于每个功能，下表列出了使用内置标签支持敏感度标签所需的最低 Office 版本。 或者，如果标签功能在公共预览版中或正在针对未来版本进行审阅。 有关 [未来版本的详细信息，请使用 Microsoft 365](https://aka.ms/MIPC/Roadmap) 路线图。

不同更新频道在不同时间提供新版本的 Office 应用。 有关详细信息，包括如何配置更新频道以便测试感兴趣的新标签功能，请参阅 [Microsoft 365](https://docs.microsoft.com/DeployOffice/overview-update-channels)应用版更新频道概述。 专用预览版中的新功能不包括在表中，但你可能能够通过为 Microsoft 信息保护专用预览计划指定组织来加入 [这些预览](https://aka.ms/mip-preview)版。

> [!NOTE]
> Office 应用的更新通道的名称最近已更改。 例如，每月频道现在是当前频道，Office 预览体验成员现在是 Beta 渠道。 有关详细信息，请参阅 [Microsoft 365](https://docs.microsoft.com/deployoffice/update-channels-changes)应用版更新频道的更改。

Office for iOS 和 Office for Android：敏感度标签内置于 [Office 应用中](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)。

在安装 Azure 信息保护统一标签客户端（仅在 Windows 计算机上运行）时，可以使用其他功能。 有关这些详细信息，请参阅 [比较 Windows 计算机的标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 和 PowerPoint 中的敏感度标签功能

列出的数字是每种功能所需的最低 Office 应用程序版本。

|功能                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手动应用、更改或删除标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[应用默认标签](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[需要更改标签的理由](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供指向自定义帮助页的帮助链接](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[标记内容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[具有变量的动态标记](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | 正在审阅 |
|[立即分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|[允许用户分配权限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | 正在审阅   | 正在审阅         | 正在审阅                                                        |
|[数据分类入门和](data-classification-overview.md) 向管理员发送数据                      | 2011+ | 16.43+ | 预览： [当前频道 (预览) ](https://office.com/insider) | 预览： [当前频道 (预览) ](https://office.com/insider) | 是的 <sup>\*</sup>                                                        |
|[要求用户将标签应用于他们的电子邮件和文档](#require-users-to-apply-a-label-to-their-email-and-documents)   | 预览： [当前频道 (预览) ](https://office.com/insider)             | 预览： [当前频道 (预览) ](https://office.com/insider)         | 正在审阅   | 推出：16.0.13628+ | 正在审阅                                            
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)                    | 2009+                                  | 推出：16.44+ | 正在审阅 | 正在审阅 | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|支持 [对已标记](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 和加密 [的文档](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) 进行自动保存和共同授权 | 正在审阅 | 正在审阅 | 正在审阅 | 正在审阅 | [是 - 选择加入](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**脚注：**

<sup>\*</sup> 当前不包含用于删除标签或降低分类级别的对齐文本

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的敏感度标签功能

列出的数字是每种功能所需的最低 Office 应用程序版本。

|功能                                                                                                        |Outlook for Windows |Outlook for Mac |iOS 版 Outlook |Android 版 Outlook |Outlook 网页版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手动应用、更改或删除标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[应用默认标签](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[需要更改标签的理由](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[提供指向自定义帮助页的帮助链接](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[标记内容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[具有变量的动态标记](#dynamic-markings-with-variables)                                              | 正在审阅                     | 正在审阅                 | 正在审阅         | 正在审阅           | 正在审阅               |
|[立即分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[允许用户分配权限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 是               |
|[要求用户将标签应用于他们的电子邮件和文档](#require-users-to-apply-a-label-to-their-email-and-documents)   | 预览：[当前频道 (预览) ) ](https://office.com/insider)                        | 16.43+                     | 正在审阅            | 正在审阅                | 是                |
|[数据分类入门和](data-classification-overview.md) 向管理员发送数据                      | 2011+ | 正在审阅 | 正在审阅           | 正在审阅               | 正在审阅 |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+                    | 正在审阅           | 正在审阅               | 是 |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 内置标记客户端和其他标签解决方案

Office 内置标签客户端从以下管理中心下载敏感度标签和敏感度标签策略设置：

- Microsoft 365 合规中心
- Microsoft 365 安全中心
- Office 365 安全与合规中心

若要使用 Office 内置标签客户端，您必须从列出的管理中心和受支持的 Office[](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)版本之一向用户发布一个或多个标签[策略](#support-for-sensitivity-label-capabilities-in-apps)。

如果满足这两个条件，但需要关闭 Office 内置标签客户端，请使用以下组策略设置：

1. 导航到 **"用户配置/管理模板/Microsoft Office 2016/安全设置"。**

2. 设置 **使用 Office 中的敏感度功能应用敏感度标签，并查看** 敏感度标签 **为 0。** 
 
使用组策略或 Office 云策略服务 [部署此设置](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)。 该设置在 Office 应用重新启动时生效。

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 内置标签客户端和 Azure 信息保护客户端

如果用户安装了 Azure 信息保护客户端之一 ([统](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) 一标记客户端或经典客户端 [) ，](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client) 默认情况下，内置标签客户端在 Office 应用中已关闭。 

若要对 Office 应用使用内置标签，而不是 Azure 信息保护客户端，请使用上一节中的说明，但设置组策略设置 使用 **Office** 中的敏感度功能应用敏感度标签，并查看敏感度标签为 **1。** 

或者，禁用或删除 Office 加载项 **，Azure 信息保护**。 此方法适用于单台计算机和临时测试。 有关说明，请参阅查看、管理和安装 Office 程序中 [的加载项](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)。 

禁用或删除此 Office 外接程序时，Azure 信息保护客户端将保持安装，以便你可以继续标记 Office 应用外部的文件。 例如，通过使用文件资源管理器或 PowerShell。

有关 Azure 信息保护客户端和 Office 内置标签客户端支持哪些功能的信息，请参阅 Azure 信息保护文档中的"选择要用于 [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) 计算机的标记客户端"。

## <a name="office-file-types-supported"></a>支持的 Office 文件类型

具有 Word、Excel 和 PowerPoint 文件的内置标签的 Office 应用支持 Open XML 格式 (，如 .docx 和 .xlsx) ，但不支持 Microsoft Office 97-2003 格式 (如 .doc 和 .xls) 。 当内置标签不支持文件类型时，"敏感度"按钮在 Office应用中不可用。

Azure 信息保护统一标签客户端支持 Open XML 格式和 Microsoft Office 97-2003 格式。 有关详细信息，请参阅该客户端的管理员指南 [中 Azure 信息保护统一标签](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 客户端支持的文件类型。

有关其他标记解决方案，请查看其文档，了解支持的文件类型。

## <a name="protection-templates-and-sensitivity-labels"></a>保护模板和敏感度标签

使用 [内置标签](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)时，管理员定义的保护模板（如为 Office 365 邮件加密定义的模板）在 Office 应用中不可见。 这种简化的体验反映了无需选择保护模板，因为已启用加密的敏感度标签中也包含相同的设置。

如果需要将现有保护模板转换为标签，请使用 Azure 门户和以下说明：将 [模板转换为标签](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>信息权限管理 (IRM) 选项和敏感度标签

配置为应用加密的敏感度标签可消除用户指定自己的加密设置的复杂性。 在许多 Office 应用中，这些单独的加密设置仍可由用户使用信息权限管理或 IRM (手动) 配置。 例如，对于 Windows 应用：

- 对于文档：**文件**  >  **信息**  >  **保护文档**  >  **限制访问**
- 对于电子邮件： **从"选项** "选项卡> **加密** 
  
当用户最初标记文档或电子邮件时，他们始终可以使用自己的加密设置覆盖标签配置设置。 例如：

- 用户将"机密 **"\"** 所有员工"标签应用于文档，并且此标签被配置为为组织中所有用户应用加密设置。 然后，此用户手动配置 IRM 设置以限制对组织外部用户的访问。 最终结果是标记为"机密 **"\"** 所有员工"并加密的文档，但您组织的用户无法如期打开该文档。

- 用户向电子邮件应用"机密 **\** 收件人仅"标签，并且此电子邮件配置为应用"不要 **转发"的加密设置**。 然后，此用户手动配置 IRM 设置，以便电子邮件不受限制。 最终结果是收件人可以转发电子邮件，尽管具有"机密\收件人仅 **"** 标签。

- 用户将常规 **标签应用于文档** ，并且此标签未配置为应用加密。 然后，此用户手动配置 IRM 设置以限制对文档的访问。 最终结果是标记为"常规"的文档，但也应用了加密，以便某些用户无法如期打开它。

如果文档或电子邮件已标记，则如果用户的内容尚未加密，或者其使用权限为"导出"或"完全控制"，则用户可以执行这些操作[](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)中的任意操作。 

若要通过有意义的报告获得更一致的标签体验，请为用户提供适当的标签和指导，以便仅应用标签来保护文档。 例如：

- 对于用户必须分配自己的权限的例外情况，提供允许用户分配自己的权限 [的标签](encryption-sensitivity-labels.md#let-users-assign-permissions)。 

- 当用户需要具有相同分类但无加密的标签时，无需用户在选择应用加密的标签后手动删除加密，而是提供子标签替代项。 例如：
    - **机密 \ 所有员工**
    - **机密 \ (加密)**

> [!NOTE]
> 如果用户从存储在 SharePoint 或 OneDrive 中的已标记文档手动删除加密，并且你已启用 SharePoint 和 [OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)中 Office 文件的敏感度标签，则下次访问或下载文档时，将自动还原标签加密。 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>将敏感度标签应用于文件、电子邮件和附件

用户一次只能对一个文档或电子邮件应用一个标签。

在标记包含附件的电子邮件时，只有在应用于电子邮件的标签应用加密且附件是 Office 文档尚未加密时，附件才继承该标签。 由于继承的标签应用加密，附件将新加密。

当应用于电子邮件的标签不应用加密或附件已加密时，附件不会从电子邮件继承标签。

标签继承示例，其中标签 **"机密** "应用加密，而标签 **"常规** "不应用加密：

- 用户创建新电子邮件，并对此邮件应用 **"** 机密"标签。 然后，他们添加未标记或加密的 Word 文档。 继承后，文档被新标记为"机密"，现在从该标签应用了加密。

- 用户创建新电子邮件，并对此邮件应用 **"** 机密"标签。 然后，他们添加一个标记为"常规"且此文件未加密的 Word 文档。 继承后，文档将重新标记为"机密"，现在从该标签应用了加密。

## <a name="sensitivity-label-compatibility"></a>敏感度标签兼容性

**使用 RMS** 启发式应用：如果在不支持敏感度标签的 [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 启发式应用程序中打开已标记和加密的文档或电子邮件，应用仍强制实施加密和权限管理。

使用 Azure 信息保护客户端：可以使用 **Azure** 信息保护客户端和另一种方式查看和更改应用于 Office 内置标签客户端的文档和电子邮件的敏感度标签。

**使用 Office 的其他版本**：任何授权用户都可以在其他版本的 Office 中打开带标签的文档和电子邮件。 但是，只能查看或更改受支持的 Office 版本或 Azure 信息保护客户端中的标签。 支持的 Office 应用程序版本在上一节中 [列出](#support-for-sensitivity-label-capabilities-in-apps)。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支持受敏感度标签保护的 SharePoint 和 OneDrive 文件

若要将 Office 内置标签客户端与 Office 网页版本一起用于 SharePoint 或 OneDrive 中的文档，请确保为 SharePoint 和 [OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)中的 Office 文件启用敏感度标签。

## <a name="support-for-external-users-and-labeled-content"></a>支持外部用户和标记的内容

在标记文档或电子邮件时，标签存储为包含租户和标签 GUID 的元数据。 当支持敏感度标签的 Office 应用打开已标记的文档或电子邮件时，此元数据是只读的，并且只有在用户属于同一租户时，标签才能显示在其应用中。 例如，对于 Word、PowerPoint 和 Excel 的内置标签，标签名称显示在状态栏上。 

这意味着，如果与其他使用不同标签名称的组织共享文档，则每个组织都可以应用并查看自己的标签是否应用于文档。 但是，已应用标签中的以下元素对组织外部的用户可见：

- 内容标记。 当标签应用页眉、页脚或水印时，这些内容会直接添加到内容中，并一直可见，直到有人修改或删除它们。

- 应用加密的标签中基础保护模板的名称和说明。 此信息显示在文档顶部的消息栏中，以提供有关谁有权打开该文档的信息及其对该文档的使用权限。

### <a name="sharing-encrypted-documents-with-external-users"></a>与外部用户共享加密文档

除了限制对自己组织中用户的访问之外，还可以将访问权限扩展到在 Azure Active Directory 中拥有帐户的其他用户。 用户成功进行身份验证后，所有 Office 应用和其他 [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 启发式应用程序都可以打开加密文档。

如果外部用户在 Azure Active Directory 中没有帐户，他们可以使用租户中的来宾帐户进行身份验证。 当你为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签时，这些来宾帐户还可用于访问 SharePoint 或 [OneDrive 中的共享文档](sensitivity-labels-sharepoint-onedrive-files.md)：

- 一个选项是自己创建这些来宾帐户。 您可以指定这些用户已使用的任何电子邮件地址。 例如，他们的 Gmail 地址。
    
    此选项的优势在于，您可以通过在加密设置中指定特定用户的电子邮件地址来限制对特定用户的访问和权限。 缺点是帐户创建和管理标签配置的管理开销。

- 另一个选项是使用 SharePoint 和 OneDrive 与 [Azure AD B2B (预览版) ， ](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) 以便当用户共享链接时自动创建来宾帐户。
    
    此选项的优点是管理开销最小，因为帐户是自动创建的，并且标签配置更简单。 对于此方案，你必须选择加密选项 ["](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) 添加任何经过身份验证的用户"，因为您事先不知道电子邮件地址。 缺点是此设置不允许将访问权限和使用权限限制为特定用户。

外部用户在 Windows 上使用 Microsoft 365 应用版 (以前是 Office [365](https://docs.microsoft.com/deployoffice/name-change) 应用) ，并且新在 macOS (版本 16.42+) 、Android (版本 16.0.13029+) 和 iOS (版本 2.42+) 上支持时，也可以将 Microsoft 帐户用于加密文档。 例如，有人与用户共享加密文档，加密设置指定其 Gmail 电子邮件地址。 此用户可以创建自己的使用其 Gmail 电子邮件地址的 Microsoft 帐户。 然后，在通过此帐户登录后，他们可根据为该用户指定的使用限制打开和编辑文档。 有关此方案的演练示例，请参阅打开 [和编辑受保护的文档](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)。

> [!NOTE]
> Microsoft 帐户的电子邮件地址必须与为限制加密设置的访问而指定的电子邮件地址相匹配。

当具有 Microsoft 帐户的用户通过此方式打开加密文档时，如果不存在同名来宾帐户，则会自动为租户创建来宾帐户。 当来宾帐户存在时，除了从 Windows 桌面应用程序打开加密文档之外，它还可用于使用浏览器 (Office 网页版) 在 SharePoint 和 OneDrive 中打开文档。 

但是，由于复制延迟，在此方案中不会立即创建自动来宾帐户。 如果你将个人电子邮件地址指定为标签加密设置的一部分，我们建议你在 Azure Active Directory 中创建相应的来宾帐户。 然后让这些用户知道，他们必须使用此帐户从组织打开加密文档。

> [!TIP]
> 由于你无法确保外部用户将使用受支持的 Office 客户端应用程序，因此，为特定用户) 创建来宾帐户 (或将 SharePoint 和 OneDrive 与 [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (集成用于任何经过身份验证的用户) 时，共享 SharePoint 和 OneDrive 的链接是支持与外部用户进行安全协作的更可靠方法。

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>当 Office 应用应用内容标记和加密时

Office 应用使用敏感度标签应用内容标记和加密的方式不同，具体取决于你使用的应用。

| 应用 | 内容标记 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel 和 PowerPoint | 立即 | 立即 |
| Outlook for PC 和 Outlook for Mac | Exchange Online 发送电子邮件后 | 立即 |
| 网页版、iOS 版和 Android 版 Outlook | Exchange Online 发送电子邮件后 | Exchange Online 发送电子邮件后 |
|

将敏感度标签应用于 Office 应用外部文件的解决方案通过向文件应用标签元数据来这样做。 在这种情况下，标签配置中的内容标记不会插入到文件中，而是应用加密。 

当这些文件在 Office 桌面应用程序中打开时，Azure 信息保护统一标签客户端将自动应用内容标记。 当您对桌面、移动或 Web 应用使用内置标签时，不会自动应用内容标记。

在 Office 应用外应用敏感度标签的方案包括：

- Azure 信息保护统一标记客户端中的扫描程序、文件资源管理器和 PowerShell 

- SharePoint 和 OneDrive 的自动标记策略

- 从 Power BI 导出的已标记和加密数据

- Microsoft Cloud App Security

对于这些方案，使用其 Office 应用，具有内置标签的用户可以通过暂时删除或替换当前标签，然后重新应用原始标签来应用标签的内容标记。

### <a name="dynamic-markings-with-variables"></a>具有变量的动态标记

> [!IMPORTANT]
> 目前，并非所有平台上的应用都支持动态内容标记，你可以为页眉、页脚和水印指定动态内容标记。 对于不支持此功能的应用，它们应用标记作为标签配置中指定的原始文本，而不是解析变量。
> 
> Azure 信息保护统一标记客户端支持动态标记。 有关内置于 Office 的标签，请参阅此页上 [的功能](#support-for-sensitivity-label-capabilities-in-apps) 部分中的表。

为内容标记配置敏感度标签时，可以在文本字符串中为页眉、页脚或水印使用以下变量：

| 变量 | 说明 | 应用标签时的示例 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 应用显示名称标签的标签标签| **常规**|
| `${Item.Name}` | 要标记的内容的文件名或电子邮件主题 | **Sales.docx** |
| `${Item.Location}` | 要标记的文档的路径和文件名，或要标记的电子邮件的电子邮件主题 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 应用标签的用户的显示名称| **Richard Richarde** |
| `${User.PrincipalName}` | Azure AD 用户主体名称 (应用) 用户的 UPN 名称 | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | 在应用标签的用户的本地时区中标记内容的日期和时间 | **2020/8/10 1：30 PM** |

> [!NOTE]
> 这些变量的语法区分大小写。

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>为 Word、Excel、PowerPoint 和 Outlook 设置不同的视觉标记

作为附加变量，您可以使用文本字符串中的"If.App"变量语句配置每个 Office 应用程序类型的视觉标记，然后使用Word、Excel、PowerPoint 或 Outlook 值标识应用程序 **类型**。  还可以缩写这些值，如果要在同一个 If.App 语句中指定多个值，这是必需的。

> [!NOTE]
> 为了完整，包括 Outlook 说明，尽管当前仅受 Azure 信息保护统一标记客户端支持。

使用以下语法：

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

与其他动态视觉标记一样，语法区分大小写。

示例：

- **仅设置 Word 文档的标题文本：**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    仅在 Word 文档标题中，标签应用标题文本"此 Word 文档是敏感的"。 不会将标题文本应用于其他 Office 应用程序。

- **设置 Word、Excel 和 Outlook 的页脚文本，以及 PowerPoint 的不同页脚文本：**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    在 Word、Excel 和 Outlook 中，标签应用页脚文本"此内容是机密的"。 在 PowerPoint 中，标签应用页脚文本"此演示文稿是机密的"。

- **设置 Word 和 PowerPoint 的特定水印文本，然后为 Word、Excel 和 PowerPoint 设置水印文本：**

    `${If.App.WP}This content is ${If.End}Confidential`

    在 Word 和 PowerPoint 中，标签应用水印文本"此内容为机密"。 在 Excel 中，标签应用水印文本"机密"。 在 Outlook 中，标签不会应用任何水印文本，因为 Outlook 不支持将水印作为视觉标记。

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>要求用户将标签应用于他们的电子邮件和文档

> [!IMPORTANT]
> 也称为强制标签，并非所有平台上的所有应用当前都支持"要求用户将标签应用于其电子邮件和文档"的策略 **设置**。
> 
> [Azure 信息保护统一标签](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)客户端支持强制标记，对于内置于 Office 应用的标签，请参阅此页上的功能部分中的表[](#support-for-sensitivity-label-capabilities-in-apps)。

选择此策略设置后，分配了该策略的用户必须在以下情况下选择和应用敏感度标签：

- 对于 Azure 信息保护统一标记客户端：
    - 对于 Word (Excel、PowerPoint) 的文档：保存未标记的文档或用户关闭文档时。
    - 对于 Outlook (电子邮件) ：用户发送未标记的邮件时。

- 对于 Office 应用中内置的标签：
    - 对于 Word ( (Excel、PowerPoint) 的文档：打开或保存未标记的文档时。
    - 对于 Outlook (电子邮件) ：当用户发送未标记的电子邮件时。

有关内置标签的其他信息：

- 当由于用户打开未标记的文档而提示用户添加敏感度标签时，他们可以添加标签或选择以只读模式打开文档。

- 强制标签生效后，用户无法从文档中删除敏感度标签，但可以更改现有标签。

有关何时使用此设置的指导，请参阅有关策略 [设置的信息](sensitivity-labels.md#what-label-policies-can-do)。

## <a name="end-user-documentation"></a>最终用户文档

- [将敏感度标签应用于 Office 文档和电子邮件](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [将敏感度标签应用于 Office 文件时的已知问题](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
