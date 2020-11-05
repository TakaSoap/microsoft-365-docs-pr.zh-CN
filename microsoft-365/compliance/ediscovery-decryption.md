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
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft 365 电子数据展示工具如何处理附加到电子邮件的加密文档。
ms.openlocfilehash: 89e6457015289055c56278f5f8650ce022ecf081
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920693"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 电子数据展示工具中的解密

组织使用加密技术来保护组织中的敏感内容，并确保只有适当的人员才能访问该内容。 组织使用各种类型的加密（Microsoft 加密技术和第三方技术）来满足其安全要求并保护其敏感信息。

到目前为止，在 Microsoft 365 中的电子数据展示工作流中管理加密内容需要对加密项进行特殊处理，具体取决于所使用的加密类型和工作流中的特定阶段。 这主要是通过在从内容搜索、核心电子数据展示事例和高级电子数据展示事例中导出电子邮件内容时对其进行解密来实现的。 在导出之前，无法预览使用 Microsoft 加密技术加密的内容。 在高级电子数据展示中，对加密内容进行了处理错误标记，这要求您下载加密的项目，对其进行解密，然后将解密的文件上传到审阅集。

为了更轻松地管理电子数据展示工作流中的加密内容，Microsoft 365 电子数据展示工具可以对附加到电子邮件的加密文件和在 Exchange Online 中发送的加密文件进行解密。 在此新功能之前，只有受权限管理保护的电子邮件的内容 (和未附加的文件) 解密。 现在，如果将使用 Microsoft 加密技术加密的文件附加到与搜索条件匹配的电子邮件，则在准备预览搜索结果时，将对加密文件进行解密。 这样，电子数据展示管理者就可以在预览搜索结果时查看加密电子邮件附件的内容。

> [!NOTE]
> 从2021年1月起，Microsoft 365 电子数据展示工具将支持存储在 SharePoint Online 和 OneDrive for Business 中的加密文档。

## <a name="supported-encryption-technologies"></a>支持的加密技术

Microsoft 电子数据展示工具支持使用 Microsoft 加密技术加密的项。 这些技术包括 Office 邮件加密、Microsoft 信息保护 (敏感标签) 和 Azure 权限管理。 有关 Microsoft 加密技术的详细信息，请参阅 [加密](encryption.md)。 不支持由第三方加密技术加密的内容。 这在预览或导出使用非 Microsoft 技术加密的内容时不提供支持。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>支持加密项目的电子数据展示活动

下表列出了在 Microsoft 365 电子数据展示工具中执行的任务，这些任务支持附加到电子邮件 massages 的加密文件的解密。 可对附加到与搜索条件相匹配的电子邮件的加密文件执行支持任务。 值为 "N/A" 表示该函数在相应的电子数据展示工具中不可用。

|电子数据展示任务  |内容搜索  |核心电子数据展示  |高级电子数据展示  |
|:---------|:---------|:---------|:---------|
|搜索加密文件中的内容     |否      |否      |否      |
|预览加密文件     |是      |是     |是       |
|查看审阅集中的加密文件    |不适用      |不适用        | 是        |
|导出加密文件    |是       |是  |是    |

## <a name="requirements-for-decryption-in-ediscovery"></a>电子数据展示中的解密要求

您必须分配有 RMS 解密角色才能预览、审阅和导出使用 Microsoft 加密技术加密的附加文件。 您还必须分配此角色以查看和查询在高级电子数据展示中添加到审阅集的加密电子邮件附件。

默认情况下，此角色分配给 Office 365 安全 & 合规中心中的电子数据展示管理器角色组。 有关 RMS 解密角色的详细信息，请参阅 [分配电子数据展示权限](assign-ediscovery-permissions.md#rms-decrypt)。
