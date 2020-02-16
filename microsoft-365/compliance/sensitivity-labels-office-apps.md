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
description: 了解用户如何使用适用于桌面的 Office 应用程序中的使用敏感度标签、适用于移动的 Office 应用程序以及 web 上的 Office 应用程序。 找出支持灵敏度标签的应用程序。
ms.openlocfilehash: a0bb5d8eea5c929f91b8e303b6c14eb52e0b980a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069859"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>在 Office 应用中使用敏感度标签

当您从 Microsoft 365 合规性中心或等效标签中心发布灵敏度标签时，它们将开始显示在 Office 应用程序中，以便用户可以在创建或编辑数据时对其进行分类和保护。

使用本文中的信息可帮助您成功管理 Office 应用中的使用敏感度标签。 例如，需要支持内置标签的应用程序的最低版本、与 Azure 信息保护的交互统一标签客户端，以及与其他应用程序和服务的兼容性。

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>敏感度标签的订阅和许可要求

用户必须至少已分配以下许可证之一：

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)或更高版本

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software)或更高版本

- [Azure 信息保护高级 P1](https://azure.microsoft.com/pricing/details/information-protection/)或更高版本

Office 内置标签客户端支持具有 Office 订阅版本的敏感度标签。 此标签客户端不支持独立版本的 Office，如 Office 2016 或 Office 2019。 若要在 Windows 计算机上将敏感度标签与这些版本的 Office 配合使用，请安装 Azure 信息保护统一标记客户端。

若要使用自动或建议的敏感度标记，用户需要以下许可证之一：

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)或更高版本

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software)或更高版本

- [Azure 信息保护高级版 P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>支持应用程序中的敏感度标签功能

对于每项功能，下表列出了该应用程序为支持使用内置标记的敏感度标签所需的最低版本。 或者，如果标签功能处于公共预览或正在审阅中，以供将来的版本使用。

新版本的应用程序在不同的时间为不同的更新频道提供。 有关详细信息，包括如何配置更新频道以便能够测试您感兴趣的新标记功能，请参阅[Office 365 专业增强版的更新频道概述](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)。 专用预览中的新功能不包含在表中，但您可能可以通过 nominating 您的组织来加入[Microsoft 信息保护专用预览计划](https://aka.ms/mip-preview)，从而加入这些预览。

在安装仅在 Windows 计算机上运行的 Azure 信息保护统一标记客户端时，可以使用其他功能。 有关这些详细信息，请参阅[比较 Windows 计算机的标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)。

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word、Excel 和 PowerPoint 中的敏感度标签功能

|功能                                                                                                        |Windows 桌面 |Mac 桌面 |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[手动应用、更改或删除标签](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [预览](sensitivity-labels-sharepoint-onedrive-files.md) |
|[应用默认标签](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | 正在审阅                                                        |
|[需要调整以更改标签](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [预览](sensitivity-labels-sharepoint-onedrive-files.md) |
|[提供指向自定义帮助页的 "帮助" 链接](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [预览](sensitivity-labels-sharepoint-onedrive-files.md) |
|[标记内容](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [预览](sensitivity-labels-sharepoint-onedrive-files.md) |
|[立即分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [预览](sensitivity-labels-sharepoint-onedrive-files.md) |
|[允许用户分配权限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 预览：在[Office 预览体验成员](https://office.com/insider)            | 预览：在[Office 预览体验成员](https://office.com/insider)        | 正在审阅   | 正在审阅         | 正在审阅                                                        |
|[查看标签使用情况标签分析](label-analytics.md)并为管理员发送数据                      | 正在审阅            | 正在审阅        | 正在审阅   | 正在审阅         | 正在审阅                                                        |
|[要求用户对其电子邮件和文档应用标签](sensitivity-labels.md#what-label-policies-can-do)   | 正在审阅            | 正在审阅        | 正在审阅   | 正在审阅         | 正在审阅                                                        |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)                    | 预览：在[Office 预览体验成员](https://office.com/insider)                                  | 正在审阅 | 正在审阅 | 正在审阅 | [预览](sensitivity-labels-sharepoint-onedrive-files.md) |
|支持在标签和受保护的文档上的[自动保存](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)和[共同创作](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) | 正在审阅 | 正在审阅 | 正在审阅 | 正在审阅 | [预览](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook 中的敏感度标签功能

|功能                                                                                                        |Windows 桌面上的 Outlook |Mac 桌面上的 Outlook  |iOS 版 Outlook |Android 版 Outlook |Outlook 网页版 |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[手动应用、更改或删除标签](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[应用默认标签](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[需要调整以更改标签](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[提供指向自定义帮助页的 "帮助" 链接](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[标记内容](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[立即分配权限](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[允许用户分配权限](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 是               |
|[查看标签使用情况标签分析](label-analytics.md)并为管理员发送数据                      | 正在审阅                       | 正在审阅                    | 正在审阅           | 正在审阅               | 正在审阅               |
|[要求用户对其电子邮件和文档应用标签](sensitivity-labels.md#what-label-policies-can-do)   | 正在审阅                       | 正在审阅                    | 正在审阅           | 正在审阅               | 正在审阅               |
|[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)                    | 预览：滚动到[Office 预览体验成员](https://office.com/insider)                       | 正在审阅                    | 正在审阅           | 正在审阅               | 是 |
|

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 内置标签客户端和 Azure 信息保护客户端

Office 内置标签客户端从以下管理中心下载灵敏度标签和敏感度标签策略设置：

- Microsoft 365 合规中心
- Microsoft 365 安全中心
- Office 365 安全与合规中心

若要使用 Office 内置标签客户端，必须向用户发布一个或多个从列出的管理中心[发布的标签策略](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。

但是，如果用户安装了其中一个 Azure 信息保护客户端（[统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)或[经典客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)），则默认情况下，在其 Office 应用中关闭内置的标记客户端。 若要使用内置标签而不是 Azure 信息保护客户端 Office 应用程序，请禁用或卸载 Office 外接程序以获取 Azure 信息保护：

1. 完成以下选项之一：
    
    - **对于多台计算机：** 配置在 **Office 中使用敏感度功能以应用并查看敏感度标签**组策略设置。 在 "**用户配置/管理模板/Microsoft Office 2016/安全设置**" 下找到此设置。 通过组策略或使用[Office 云策略服务](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)部署此设置。
    
    - **对于单个计算机：** 有关如何在一台计算机上[永久禁用或删除](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)Azure 信息保护外接程序的信息，请参阅 "查看、管理和安装 Office 程序中的外接程序"。

2. 重新启动所有 Office 应用程序。

当您禁用或卸载此 Office 加载项时，将保持安装的 Azure 信息保护客户端，以便您可以继续标记 Office 应用外部的文件。 例如，通过使用文件资源管理器或 PowerShell。

有关 Azure 信息保护客户端和 Office 内置标签客户端支持的功能的信息，请参阅从 Azure 信息保护文档中[选择用于 Windows 计算机的标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)。

## <a name="protection-templates-and-sensitivity-labels"></a>保护模板和敏感度标签

在使用内置标记时，管理员定义的[保护模板](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)（如您为 Office 365 邮件加密定义的模板）在 Office 应用中不可见。 这种简化的体验反映了无需选择保护模板，因为具有已启用加密功能的敏感度标签中包含相同的设置。

如果需要将现有保护模板转换为标签，请使用 Azure 门户和以下说明：[将模板转换为标签](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)。

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>将敏感度标签应用于文件、电子邮件和附件

用户可以一次仅为每个文档或电子邮件应用一个标签。

当您标记包含附件的电子邮件时，附件不会继承该标签：

- 如果附件具有标签，则会保留单独应用的标签。
- 如果附件不包含标签，则不会在不带标签的情况下保留附件。 但是，如果电子邮件标签应用了保护，则该保护将应用于 Office 附件。

## <a name="sensitivity-label-compatibility"></a>敏感度标签兼容性

**对于智能型应用**：如果在不支持敏感度标签的[RMS 智能型应用程序](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications)中打开已标记和加密的文档或电子邮件，则应用仍强制实施加密和权限管理。

**使用 Azure 信息保护客户端**：您可以使用 Azure 信息保护客户端和其他方法查看和更改应用于 Office 内置标记客户端的文档和电子邮件的敏感度标签。

**与其他版本的 office**：任何授权的用户都可以在其他版本的 office 中打开带标签的文档和电子邮件。 但是，只能在受支持的 Office 版本中或通过使用 Azure 信息保护客户端来查看或更改标签。 [上一节](#support-for-sensitivity-label-capabilities-in-apps)中列出了受支持的 Office 应用程序版本。

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>支持由敏感度标签保护的 SharePoint 和 OneDrive 文件

若要对 OneDrive for Business 或 SharePoint Online 中的文档使用 Office 内置标签客户端与 web 上的文档，请确保已选择预览以在[SharePoint 和 OneDrive 中启用 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。

## <a name="when-office-365-applies-content-marking-and-encryption"></a>当 Office 365 应用内容标记和加密时

Office 365 根据您使用的应用程序以不同的敏感度标签应用内容标记和加密。

| 应用 | 内容标记 | 加密 |
| --- | --- | --- |
| 所有平台上的 Word、Excel 和 PowerPoint | 立即 | 立即 |
| Outlook for PC 和 Outlook for Mac | Exchange Online 发送电子邮件后 | 立即 |
| 网页版、iOS 版和 Android 版 Outlook | Exchange Online 发送电子邮件后 | Exchange Online 发送电子邮件后 |
|

## <a name="end-user-documentation"></a>最终用户文档

- [将敏感度标签应用于 Office 文档和电子邮件](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [将敏感度标签应用于 Office 文件时的已知问题](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
