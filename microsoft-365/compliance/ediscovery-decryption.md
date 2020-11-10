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
description: 了解 Microsoft 365 电子数据展示工具如何处理附加到电子邮件的加密文档。
ms.openlocfilehash: 3a4a094f1da28c9a017836c099507f5af739b0b9
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951115"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 电子数据展示工具中的解密

加密是文件保护和信息保护策略的重要组成部分。 所有类型的组织都使用加密技术来保护其组织中的敏感内容，并确保只有适当的人员才能访问该内容。

若要对加密内容执行常见的电子数据展示任务，电子数据展示管理器需要在从内容搜索、核心电子数据展示事例和高级电子数据展示事例中导出时对电子邮件内容进行解密。 使用 Microsoft 加密技术加密的内容在导出之后才可供审阅。

为了便于在电子数据展示工作流中管理加密内容，Microsoft 365 电子数据展示工具现在合并了附加到电子邮件和在 Exchange Online 中发送的加密文件的解密。 在此新功能之前，只有受权限管理保护的电子邮件的内容 (，未对附加的文件) 解密。 现在，如果将使用 Microsoft 加密技术加密的文件附加到与搜索条件匹配的电子邮件，则在准备审阅搜索结果时将对加密的文件进行解密。 这使电子数据展示管理者可以在预览搜索结果时查看加密的电子邮件附件的内容，并在将其添加到高级电子数据展示中的审阅集后查看这些文件的内容。

> [!NOTE]
> 即将启动 Microsoft 365 电子数据展示工具将支持存储在 SharePoint Online 和 OneDrive for Business 中的加密文档。

## <a name="supported-encryption-technologies"></a>支持的加密技术

Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项。 这些技术包括 Office 邮件加密、Microsoft 信息保护 (即将推出) 和 Azure 权限管理。 有关 Microsoft 加密技术的详细信息，请参阅 [加密](encryption.md)。 不支持由第三方加密技术加密的内容。 这在预览或导出使用非 Microsoft 技术加密的内容时不提供支持。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支持加密项目的电子数据展示活动

下表列出了在 Microsoft 365 电子数据展示工具中执行的任务，这些任务支持附加到电子邮件 massages 的加密文件的解密。 可对附加到与搜索条件相匹配的电子邮件的加密文件执行支持任务。 值为 "N/A" 表示该函数在相应的电子数据展示工具中不可用。

|电子数据展示任务  |内容搜索  |核心电子数据展示  |高级电子数据展示  |
|:---------|:---------|:---------|:---------|
|搜索加密文件中的内容     |是      |是      |是      |
|预览加密文件     |是      |是     |是       |
|查看审阅集中的加密文件    |不适用      |不适用        | 是        |
|导出加密文件    |是       |是  |是    |

## <a name="requirements-for-decryption-in-ediscovery"></a>电子数据展示中的解密要求

您必须分配有 RMS 解密角色才能预览、审阅和导出使用 Microsoft 加密技术加密的附加文件。 您还必须分配此角色以查看和查询在高级电子数据展示中添加到审阅集的加密电子邮件附件。

默认情况下，此角色分配给 Office 365 安全 & 合规中心中的电子数据展示管理器角色组。 有关 RMS 解密角色的详细信息，请参阅 [分配电子数据展示权限](assign-ediscovery-permissions.md#rms-decrypt)。
