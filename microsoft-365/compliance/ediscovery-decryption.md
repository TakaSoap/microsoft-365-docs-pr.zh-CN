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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解电子Microsoft 365工具如何处理附加到电子邮件并存储在 SharePoint Online 和 OneDrive for Business 中的加密OneDrive for Business。
ms.openlocfilehash: 351a6c77d1fc0956c83661132f1111897896a724
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159904"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>电子数据展示Microsoft 365中的解密

加密是文件保护和信息保护策略的重要组成部分。 所有类型的组织都使用加密技术来保护其组织的敏感内容，并确保只有合适的人员可以访问该内容。

若要对加密内容执行常见的电子数据展示任务，电子数据展示管理员需要从内容搜索、核心电子数据展示事例和加密事例导出电子邮件内容时解密Advanced eDiscovery内容。 使用 Microsoft 加密技术加密的内容在导出之前无法查看。

为了更加轻松地管理电子数据展示工作流中的加密内容，Microsoft 365 电子数据展示工具现在包含附加到电子邮件并在 Exchange Online 中发送的加密文件的解密。<sup>1</sup>此外，存储在 SharePoint Online 和 OneDrive for Business 中的加密Advanced eDiscovery。

在此新功能之前，只有受权限管理保护的电子邮件内容 (未附加的文件) 解密。 电子数据展示SharePoint OneDrive加密的文档无法解密。 现在，当准备预览搜索结果、添加到 Advanced eDiscovery 中的审阅集并导出时，使用 Microsoft 加密技术加密的文件位于 SharePoint 或 OneDrive 帐户上，可以搜索和解密这些文件。 此外，还可以SharePoint OneDrive电子邮件中的加密文档。 此解密功能允许电子数据展示管理员在预览搜索结果时查看加密电子邮件附件和网站文档的内容，并在将已添加到 Advanced eDiscovery 审阅集后查看这些内容。

## <a name="supported-encryption-technologies"></a>支持的加密技术

Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项目。 这些技术是 Azure 权限管理，Microsoft 信息保护 (特定敏感度标签) 。 有关 Microsoft 加密技术的信息，[请参阅加密。](encryption.md) 不支持通过第三方加密技术加密的内容。 例如，不支持预览或导出使用非 Microsoft 技术加密的内容。

> [!NOTE]
> Microsoft 电子数据展示工具不支持解密Office 365 邮件加密 ([OME](add-your-organization-brand-to-encrypted-messages.md)) 自定义品牌模板发送的电子邮件。 使用 OME 自定义品牌模板时，电子邮件将传递到 OME 门户，而不是收件人的邮箱。 因此，你将无法使用电子数据展示工具搜索 OME 加密的邮件，因为这些邮件从不由收件人的邮箱接收。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支持加密项目的电子数据展示活动

下表标识了可在 Microsoft 365 电子数据展示工具中对附加到电子邮件的加密文件以及 SharePoint 和 OneDrive 中执行的支持任务。 可以在符合搜索条件的加密文件上执行这些支持的任务。 值 表示功能在相应的电子数据展示 `N/A` 工具中不可用。

|电子数据展示任务  |内容搜索  |核心电子数据展示  |高级电子数据展示  |
|:---------|:---------|:---------|:---------|
|在网站和电子邮件附件<sup>1</sup>中搜索加密文件中的内容     |否      |否      |是      |
|预览附加到电子邮件的加密文件     |是      |是     |是       |
|预览加密的文档SharePoint OneDrive|否      |否    |是       |
|查看审阅集的加密文件    |不适用      |不适用        | 是        |
|导出附加到电子邮件的加密文件    |是       |是  |是    |
|导出加密的文档SharePoint OneDrive    |否       |否  |是    |
|||||

> [!NOTE]
> <sup>1</sup> 不针对电子数据展示解密和索引位于本地计算机和复制到电子邮件的云附件的加密文件。 有关这些方案的详细信息和解决方法，请参阅本文中的解密 [电子邮件](#decryption-limitations-with-email-attachments) 附件限制部分。

## <a name="decryption-limitations-with-sensitivity-labels-in-sharepoint-and-onedrive"></a>SharePoint 和 OneDrive 中的敏感度标签的解密OneDrive

当应用了加密的敏感度标签配置为以下任一设置时SharePoint电子数据展示不支持 SharePoint 和 OneDrive 中的加密文件：

- 用户可以在手动将标签应用于文档时分配权限。 这有时称为用户 *定义权限*。

- 用户对文档的访问具有设置为"从不"的值的过期 **设置**。

有关这些设置详细信息，请参阅使用敏感度标签应用加密来限制对内容的访问中的"配置 [加密设置"部分](encryption-sensitivity-labels.md#configure-encryption-settings)。

使用以前的设置加密的文档仍可由电子数据展示搜索返回。 当文档属性匹配搜索 (，例如标题、作者或修改日期) 可能会发生这种情况。 尽管这些文档可能包含在搜索结果中，但无法预览或查看它们。 这些文档在导出时也会保持加密Advanced eDiscovery。

## <a name="decryption-limitations-with-email-attachments"></a>电子邮件附件的解密限制

以下方案描述了电子邮件附加文件的解密限制。 这些方案说明还包括缓解这些限制的解决方法。

- 如果本地计算机 (中未存储在 SharePoint 站点或 OneDrive 帐户) 中的文件附加到电子邮件，并且对电子邮件应用加密的敏感度标签，则电子数据展示无法解密附加的文件。 这意味着，如果对收件人邮箱运行关键字搜索查询，则关键字搜索查询不会返回加密文件附件。

  此限制的解决方法是搜索发件人邮箱中的相同文件附件。 这是因为在电子邮件传输过程中应用了敏感度标签应用的加密。 这意味着在发送电子邮件时附件会进行加密。 结果是发件人邮箱中附加文件的实例未加密，即使收件人邮箱中的同一文件已加密。

- 同样，云附件 (SharePoint 站点或 OneDrive 帐户) 中通过使用 Outlook) 中的"作为副本附加"选项复制到电子邮件 (中的文件无法由电子数据展示解密。 这也是因为发送电子邮件时应用了敏感度标签应用的加密。 在发件人邮箱中搜索云附件副本的未加密实例也是此限制的解决方法。

在这两种方案中，如果电子邮件属性 (（如发送日期、发件人、收件人或主题) ）与搜索查询匹配，电子数据展示搜索可以返回带加密文件附件的电子邮件。

## <a name="requirements-for-decryption-in-ediscovery"></a>电子数据展示中的解密要求

您必须获得 RMS 解密角色，以预览、查看和导出使用 Microsoft 加密技术加密的文件。 还必须分配有此角色，以审阅和查询已添加到 Advanced eDiscovery 审阅集的加密Advanced eDiscovery。

默认情况下，此角色分配给"管理员"角色组中"权限"页上的"电子数据展示Microsoft 365 合规中心。 有关 RMS 解密角色详细信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md#rms-decrypt)。

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments-using-content-search-or-core-ediscovery"></a>使用内容搜索或核心电子数据展示解密受 RMS 保护的电子邮件和加密文件附件

导出内容 (结果) 受 RMS 保护的任何受 RMS 保护的电子邮件都将被解密。 此外，任何使用 [Microsoft](encryption.md) 加密技术加密并附加到包含在搜索结果中的电子邮件的文件在导出时将被解密。 默认情况下，为电子数据展示管理员角色组的成员启用此解密功能。 这是因为默认情况下，RMS 解密管理角色已分配给此角色组。 导出加密电子邮件和附件时，请记住以下事项：
  
- 如前所述，若要在导出受 RMS 保护的邮件时解密这些邮件，您必须将搜索结果导出为单个邮件。 如果将搜索结果导出到 PST 文件，受 RMS 保护的邮件将保持加密状态。

- 解密的邮件在 **ResultsLog** 报告中进行标识。 此报告包含一个名为 **Decode Status** 的列，并且 **Decoded** 的值标识已解密的消息。

- 除了在导出搜索结果时解密文件附件之外，还可以在预览搜索结果时预览解密的文件。 导出后，只能查看受权限保护的电子邮件。

- 如果需要阻止某人解密受 RMS 保护的邮件和加密文件附件，您必须通过复制内置电子数据展示管理器角色组) 创建自定义角色组 (，然后从自定义角色组中删除 RMS 解密管理角色。 然后将不希望解密邮件的人添加为自定义角色组的成员。
