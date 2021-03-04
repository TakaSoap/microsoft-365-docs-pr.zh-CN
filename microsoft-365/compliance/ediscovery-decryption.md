---
title: 电子数据展示中的解密
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解 Microsoft 365 电子数据展示工具如何处理附加到电子邮件并存储在 SharePoint Online 和 OneDrive for Business 中的加密文档。
ms.openlocfilehash: 4ddc66d595b9d2129a7ba1b75e69586ccbd130f7
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423815"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 电子数据展示工具中的解密

加密是文件保护和信息保护策略的重要组成部分。 所有类型的组织都使用加密技术来保护其组织的敏感内容，并确保只有合适的人员可以访问该内容。

若要对加密内容执行常见的电子数据展示任务，电子数据展示管理员需要解密从内容搜索、核心电子数据展示事例和高级电子数据展示事例导出的电子邮件内容。 使用 Microsoft 加密技术加密的内容在导出之前无法查看。

为了更加轻松地管理电子数据展示工作流中的加密内容，Microsoft 365 电子数据展示工具现在合并了附加到电子邮件并在 Exchange Online 中发送的加密文件的解密。 此外，存储在 SharePoint Online 和 OneDrive for Business 中的加密文档在高级电子数据展示中解密。 

在此新功能之前，只有受权限管理保护的电子邮件的内容 (未附加的文件) 解密。 在电子数据展示工作流期间，SharePoint 和 OneDrive 中的加密文档无法解密。 现在，如果使用 Microsoft 加密技术加密的文件附加到电子邮件或位于 SharePoint 或 OneDrive 帐户上，则当搜索结果准备预览、添加到高级电子数据展示中的审阅集并导出时，将解密这些加密项目。 这允许电子数据展示管理员在预览搜索结果时查看加密电子邮件附件和网站文档的内容，在将加密电子邮件附件和网站文档添加到高级电子数据展示审阅集后对其进行查看。

## <a name="supported-encryption-technologies"></a>支持的加密技术

Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项目。 这些技术是 Azure 权限管理和 Microsoft 信息保护 (特别是敏感度标签) 。 有关 Microsoft 加密技术的信息，请参阅"[加密"。](encryption.md) 不支持由第三方加密技术加密的内容。 例如，不支持预览或导出使用非 Microsoft 技术加密的内容。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支持加密项目电子数据展示活动

下表标识了可在 Microsoft 365 电子数据展示工具中执行的支持任务，这些任务对附加到 SharePoint 和 OneDrive 中的电子邮件加密文件和加密文档的加密文件执行。 这些支持的任务可以在符合搜索条件的加密文件上执行。 值表示功能在相应的电子数据展示工具 `N/A` 中不可用。

|电子数据展示任务  |内容搜索  |核心电子数据展示  |高级电子数据展示  |
|:---------|:---------|:---------|:---------|
|在电子邮件和网站中搜索加密文件中的内容     |是      |是      |是      |
|预览附加到电子邮件的加密文件     |是      |是     |是       |
|在 SharePoint 和 OneDrive 中预览加密文档|否      |否    |是       |
|查看审阅集内加密的文件    |不适用      |不适用        | 是        |
|导出附加到电子邮件的加密文件    |是       |是  |是    |
|在 SharePoint 和 OneDrive 中导出加密文档    |否       |否  |是    |
|||||

**注意：** 当应用加密的敏感度标签配置为以下任一设置时，电子数据展示不支持 SharePoint 和 OneDrive 中的加密文件：

- 用户可以在手动将标签应用于文档时分配权限。 这有时称为用户 *定义权限*。<br/>

- 用户访问文档具有设置为"从不"值而非"从不"值的 **过期设置**。

有关这些设置的信息，请参阅"使用敏感度标签应用加密来限制对内容的访问"一节中的 ["配置加密设置"部分](encryption-sensitivity-labels.md#configure-encryption-settings)。

使用以前的设置加密的文档仍可由电子数据展示搜索返回。 当文档属性（如 (、作者或修改日期）与搜索条件) 时，可能会发生这种情况。 尽管这些文档可能包含在搜索结果中，但无法预览或查看它们。 在高级电子数据展示中导出这些文档时，这些文档也将保持加密状态。

## <a name="requirements-for-decryption-in-ediscovery"></a>电子数据展示中的解密要求

您必须获得 RMS 解密角色，以预览、审阅和导出使用 Microsoft 加密技术加密的文件。 还必须分配有此角色，以审阅和查询添加到高级电子数据展示审阅集的加密文件。

默认情况下，此角色分配给 Office 365 安全与合规中心中"权限"页上&角色组。 有关 RMS 解密角色详细信息，请参阅"分配[电子数据展示权限"。](assign-ediscovery-permissions.md#rms-decrypt)
