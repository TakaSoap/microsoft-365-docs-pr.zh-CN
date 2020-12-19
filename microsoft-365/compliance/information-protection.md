---
title: Microsoft 365 中的 Microsoft 信息保护
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: 实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你保护敏感信息。
ms.openlocfilehash: 2a1ec47ce888dc6d31868d65f9c4c113fa9b968c
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709504"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 中的 Microsoft 信息保护

>*[Microsoft 365 安全和合规性许可](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你发现、分类和保护敏感信息。

MIP 功能包含在 Microsoft 365 合规性中，提供了[了解数据](#know-your-data)、[保护数据](#protect-your-data)和[防止数据丢失](#prevent-data-loss)的工具。

![有关 MIP 如何帮助你发现、分类和保护敏感数据的图像](../media/powered-by-intelligent-platform.png)

有关管理数据的信息，请参阅 [Microsoft 365 中的 Microsoft 信息管理](manage-Information-governance.md)。

## <a name="know-your-data"></a>了解你的数据

> [!NOTE]
> 有关在 Azure Purview 中对数据进行分类和标记的详细信息，请参阅当前处于预览中的[在 Azure Purview 中自动标记内容](https://docs.microsoft.com/azure/purview/create-sensitivity-label)。
> 
> 有关此新版本的信息，请参阅博客文章 [Microsoft 信息保护和 Microsoft Azure Purview：珠联璧合](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481)。



若要了解在混合环境中的数据全景并发现重要数据，请使用以下功能：
 
|功能|它能解决什么问题？|开始行动|
|:------|:------------|:--------------------|:-----------------------------|
|[敏感信息类型](sensitive-information-type-entity-definitions.md)| 使用内置或自定义正则表达式或函数，以及包含关键字、可信度水平和接近的补强证据识别敏感数据。| [自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)|
|[可训练的分类器（预览版）](classifier-learn-about.md)| 使用内置的一个分类器或用自己的内容训练分类器来分类数据 | [可训练的分类器入门（预览版）](classifier-get-started-with.md) |
|[数据分类](data-classification-overview.md) | 识别具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目及用户对其执行的操作  | [内容资源管理器入门](data-classification-content-explorer.md)<br /><br /> [活动资源管理器入门](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>保护数据

若要应用包含加密、访问限制和视觉标记的灵活保护操作，请使用以下功能：

|功能|它能解决什么问题？|开始行动|
|:------|:------------|---------------------|:----------------------------|
|[敏感度标签](sensitivity-labels.md)| 通过应用、服务和设备提供的单一解决方案，可在你的组织内外进行标记并保护你的数据 <br /><br />示例方案：[在 Power BI 中应用和查看敏感度标签，并保护导出的数据](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[开始使用敏感度标签](get-started-with-sensitivity-labels.md) |
|[Azure 信息保护统一标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| 对于 Windows 计算机，扩展了其他特性和功能的敏感标签，包括标记和保护文件资源管理器和 PowerShell 中的所有文件类型<br /><br /> 示例附加功能：[自定义配置 Azure 信息保护统一标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure 信息保护统一标记客户端管理员指南](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[双密钥加密](double-key-encryption.md)| 在所有情况下，只有你可以解密受保护的内容，或者为了满足监管要求，你必须在地理范围内持有加密密钥 | [部署双密钥加密](double-key-encryption.md#deploy-dke)|
|[Office 365 邮件加密 (OME)](ome.md)| 加密发送到任意设备上任何用户的电子邮件和附加文档，以便仅授权的收件人可阅读电子邮件信息  <br /><br />示例方案： [撤消通过高级邮件加密进行加密的电子邮件](revoke-ome-encrypted-mail.md) | [设置全新的邮件加密功能](set-up-new-message-encryption-capabilities.md)|
|[使用客户密钥执行服务加密](customer-key-overview.md) | 防止未经授权的系统或人员查看数据，并在 Microsoft 数据中心中补充 BitLocker 磁盘加密 | [设置 Office 365 的客户密钥](customer-key-set-up.md)|
|[SharePoint 信息权限管理 (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|保护 SharePoint 列表和库，以便当用户签出文档时，对下载的文件进行保护，仅授权人员可根据你指定的策略查看和使用该文件 | [在 SharePoint 管理中心设置信息权限管理 (IRM)](set-up-irm-in-sp-admin-center.md)|
[权限管理连接器](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |仅适用于使用 Exchange 或 SharePoint Server 的现有本地部署或运行 Windows Server 和文件分类基础结构的文件服务器 (FCI) | [部署 RMS 连接器的步骤](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure 信息保护统一标记扫描器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| 发现、标记和保护驻留在本地数据存储区中的敏感信息 | [配置和安装 Azure 信息保护统一标记扫描器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 发现、标记和保护驻留在云数据存储区中的敏感信息 | [发现、分类、标记和保护存储在云中的管控和敏感数据](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 信息保护 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|将灵敏度标签扩展到第三方应用和服务  <br /><br /> 示例方案： [设置和获取灵敏度标签 (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft 信息保护 (MIP) SDK 安装和配置](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>防止数据丢失

若要帮助防止意外地过度共享敏感信息，请使用以下功能：


|功能|它能解决什么问题？|开始行动|
|:------|:------------|:---------------------|:-----------------------------|
|[数据丢失防护 (DLP)](data-loss-prevention-policies.md)| 帮助防止意外共享敏感项目 <br /><br />示例方案： [保护 Microsoft Teams 聊天和频道消息中的敏感信息](dlp-microsoft-teams.md) | [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)|
|[了解终结点数据丢失防护](endpoint-dlp-learn-about.md)| 将 DLP 功能扩展到 Windows 10 计算机上使用和共享的项目 | [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)|
