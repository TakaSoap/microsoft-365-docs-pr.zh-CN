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
description: 了解电子Microsoft 365工具如何处理附加到电子邮件并存储在 SharePoint Online 和 OneDrive for Business 中的加密OneDrive for Business。
ms.openlocfilehash: 7d0f4acd34fc67738258e0f0df23535e759bd8dd
ms.sourcegitcommit: 4582873483bd52bc790bf75b838cc505dc4bbeb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2021
ms.locfileid: "58503043"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>电子数据展示Microsoft 365中的解密

加密是文件保护和信息保护策略的重要组成部分。 所有类型的组织都使用加密技术来保护其组织的敏感内容，并确保只有合适的人员可以访问该内容。

若要对加密内容执行常见的电子数据展示任务，电子数据展示管理员需要从内容搜索、核心电子数据展示事例和加密事例导出电子邮件内容时解密Advanced eDiscovery内容。 使用 Microsoft 加密技术加密的内容在导出之前无法查看。

为了更加轻松地管理电子数据展示工作流中的加密内容，Microsoft 365电子数据展示工具现在合并对附加到电子邮件并发送到 Exchange Online 中的加密文件的解密。<sup>1</sup>此外，存储在 SharePoint Online 和 OneDrive for Business 中的加密Advanced eDiscovery。

在此新功能之前，只有受权限管理保护的电子邮件内容 (未附加的文件) 解密。 电子数据展示SharePoint OneDrive加密的文档无法解密。 现在，当准备预览搜索结果、添加到 Advanced eDiscovery 中的审阅集并导出时，可以使用 Microsoft 加密技术加密的文件位于 SharePoint 或 OneDrive 帐户上，并可以搜索和解密这些文件。 此外，可SharePoint OneDrive电子邮件的加密文档和加密文档。 此解密功能允许电子数据展示管理员在预览搜索结果时查看加密电子邮件附件和网站文档的内容，并在将已添加到 Advanced eDiscovery 审阅集后查看这些内容。

## <a name="supported-encryption-technologies"></a>支持的加密技术

Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项目。 这些技术是 Azure 权限管理和Microsoft 信息保护 (特定敏感度标签) 。 有关 Microsoft 加密技术的信息，[请参阅加密。](encryption.md) 不支持通过第三方加密技术加密的内容。 例如，不支持预览或导出使用非 Microsoft 技术加密的内容。

> [!NOTE]
> Microsoft 电子数据展示工具不支持解密Office 365 邮件加密 (OME) 加密的电子邮件。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支持加密项目的电子数据展示活动

下表标识了可以在 Microsoft 365 电子数据展示工具中对附加到电子邮件的加密文件以及 SharePoint 和 OneDrive 中执行的支持任务。 可以在符合搜索条件的加密文件上执行这些支持的任务。 值 表示功能在相应的电子数据展示 `N/A` 工具中不可用。

|电子数据展示任务  |内容搜索  |核心电子数据展示  |高级电子数据展示  |
|:---------|:---------|:---------|:---------|
|在电子邮件和网站<sup>1</sup>中搜索加密文件中的内容     |是      |是      |是      |
|预览附加到电子邮件的加密文件     |是      |是     |是       |
|预览加密的文档SharePoint OneDrive|否      |否    |是       |
|查看审阅集的加密文件    |不适用      |不适用        | 是        |
|导出附加到电子邮件的加密文件    |是       |是  |是    |
|导出加密的文档SharePoint和OneDrive    |否       |否  |是    |
|||||

> [!NOTE]
> <sup>1</sup>不为电子数据展示对位于本地计算机 (且未存储在 SharePoint 或 OneDrive 站点) 的加密文件编制索引。 这意味着，如果加密的本地文件附加到电子邮件，则关键字搜索查询不会返回该文件，即使该文件包含与搜索查询匹配的关键字。 但是，如果电子邮件属性 (如发送日期、发件人、收件人或主题邮件与搜索查询匹配，则电子数据展示搜索可以返回包含本地加密文件) 电子邮件。

### <a name="decryption-limitations-with-sensitivity-labels"></a>敏感度标签的解密限制

当应用了加密的敏感度标签配置了以下任一设置时SharePoint电子数据展示不支持 SharePoint 和 OneDrive 中的加密文件：

- 用户可以在手动将标签应用于文档时分配权限。 这有时称为用户 *定义权限*。

- 用户对文档的访问具有设置为"从不"的值的过期 **设置**。

有关这些设置详细信息，请参阅使用敏感度标签应用加密来限制对内容的访问中的"配置 [加密设置"部分](encryption-sensitivity-labels.md#configure-encryption-settings)。

使用以前的设置加密的文档仍可由电子数据展示搜索返回。 当文档属性匹配搜索 (，例如标题、作者或修改日期) 可能会发生这种情况。 尽管这些文档可能包含在搜索结果中，但无法预览或查看它们。 这些文档在导出时也会保持加密Advanced eDiscovery。

## <a name="requirements-for-decryption-in-ediscovery"></a>电子数据展示中的解密要求

您必须获得 RMS 解密角色，以预览、查看和导出使用 Microsoft 加密技术加密的文件。 还必须分配有此角色，以审阅和查询已添加到 Advanced eDiscovery 审阅集的加密Advanced eDiscovery。

默认情况下，此角色分配给"管理员"角色组中"权限"页上的"电子数据展示Microsoft 365 合规中心。 有关 RMS 解密角色详细信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md#rms-decrypt)。
