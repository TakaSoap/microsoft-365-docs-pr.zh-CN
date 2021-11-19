---
title: Microsoft 365 中的 Microsoft 信息保护
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: 实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你保护敏感信息。
ms.openlocfilehash: d011877bf31e996144b73978337ad63cb3a22c6a
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2021
ms.locfileid: "61071386"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 中的 Microsoft 信息保护

>*[Microsoft 365 安全和合规性许可](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你发现、分类和保护敏感信息。

MIP 功能包含在 Microsoft 365 合规性中，提供了[了解数据](#know-your-data)、[保护数据](#protect-your-data)和[防止数据丢失](#prevent-data-loss)的工具。

![有关 MIP 如何帮助你发现、分类和保护敏感数据的图像。](../media/powered-by-intelligent-platform.png)

有关管理数据的信息，请参阅 [Microsoft 365 中的 Microsoft 信息管理](manage-Information-governance.md)。

## <a name="know-your-data"></a>了解你的数据

若要了解在混合环境中的数据全景并发现重要数据，请使用以下功能：

|功能|它能解决什么问题？|开始行动|
|:------|:------------|:--------------------|
|[敏感信息类型](sensitive-information-type-learn-about.md)| 使用内置或自定义正则表达式或函数识别敏感数据。补强证据包括关键字、可信度和接近度。| [自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)|
|[可训练的分类器](classifier-learn-about.md)| 通过使用您感兴趣的数据示例而不是识别项中的元素来标识敏感数据（模式匹配）。 可使用内置分类器，或使用自己的内容培训分类器。| [可训练的分类器入门](classifier-get-started-with.md) |
|[数据分类](data-classification-overview.md) | 组织中具有敏感度标签、保留标签或已分类的项目的图形标识。 此信息还可用于深入了解用户正在针对这些项目采取的操作。 | [内容资源管理器入门](data-classification-content-explorer.md) <p> [活动资源管理器入门](data-classification-activity-explorer.md) |
|[Azure Purview](/azure/purview/overview) |识别敏感数据并将自动标签应用于 Azure Purview 资产中的任何内容，如 Azure Blob 存储、Azure 文件存储、Azure Data Lake Storage 和多云数据源。 |[在 Azure Purview 中贴标签](/azure/purview/create-sensitivity-label) |

## <a name="protect-your-data"></a>保护数据

若要应用包含加密、访问限制和视觉标记的灵活保护操作，请使用以下功能：

|功能|它能解决什么问题？|开始行动|
|:------|:------------|---------------------|
|[敏感度标签](sensitivity-labels.md)| 跨应用、服务和设备的单一解决方案可在行经组织内外时标记并保护你的数据。 <p> 示例方案： <p> [管理 Office 应用的敏感度标签](sensitivity-labels-office-apps.md) <p> [加密文档和电子邮件](encryption-sensitivity-labels.md) <p> [在 Power BI 中应用和查看标签](/power-bi/admin/service-security-apply-data-sensitivity-labels) <p> 有关敏感度标签的方案综合列表，请参阅入门文档。|[开始使用敏感度标签](get-started-with-sensitivity-labels.md) |
|[Azure 信息保护统一标记客户端](/azure/information-protection/rms-client/aip-clientv2)| 对于 Windows 计算机，扩展了其他特性和功能的敏感标签，包括标记和保护文件资源管理器和 PowerShell 中的所有文件类型 <p> 示例附加功能：[自定义配置 Azure 信息保护统一标记客户端](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure 信息保护统一标记客户端管理员指南](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[双密钥加密](double-key-encryption.md)| 在所有情况下，只有你可以解密受保护的内容，或者为了满足监管要求，你必须在某一地理范围内持有加密的密钥。 | [部署双密钥加密](double-key-encryption.md#deploy-dke)|
|[Office 365 邮件加密 (OME)](ome.md)| 请加密发送到任意设备上任何用户的电子邮件和附加文档，以便仅获授权的收件人可阅读电子邮件信息。 <p> 示例方案： [撤消通过高级邮件加密进行加密的电子邮件](revoke-ome-encrypted-mail.md) | [设置全新的邮件加密功能](set-up-new-message-encryption-capabilities.md)|
|[使用客户密钥执行服务加密](customer-key-overview.md) | 防止未经授权的系统或人员查看数据，并在 Microsoft 数据中心中补充 BitLocker 磁盘加密。 | [设置 Office 365 的客户密钥](customer-key-set-up.md)|
|[SharePoint 信息权限管理 (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|保护 SharePoint 列表和库，以便当用户签出文档时，对下载的文件进行保护，即仅获得授权人员可根据指定策略查看和使用该文件。 | [在 SharePoint 管理中心设置信息权限管理 (IRM)](set-up-irm-in-sp-admin-center.md)|
[权限管理连接器](/azure/information-protection/deploy-rms-connector) |保护 - 仅适用于使用 Exchange 或 SharePoint Server 的现有本地部署，或运行 Windows Server 和文件分类基础结构的文件服务器 (FCI) 的文件服务器。 | [部署 RMS 连接器的步骤](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure 信息保护统一标记扫描器](/azure/information-protection/deploy-aip-scanner)| 发现、标记和保护驻留在本地数据存储区中的敏感信息。 | [配置和安装 Azure 信息保护统一标记扫描器](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| 发现、标记和保护驻留在云中数据存储区内的敏感信息。 | [发现、分类、标记和保护存储在云中的管控和敏感数据](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 信息保护 SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|将灵敏度标签扩展到第三方应用和服务。 <p> 示例方案： [设置和获取灵敏度标签 (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft 信息保护 (MIP) SDK 安装和配置](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>防止数据丢失

若要帮助防止意外地过度共享敏感信息，请使用以下功能：


|功能|它能解决什么问题？|开始行动|
|:------|:------------|:---------------------|
|[数据丢失防护](dlp-learn-about-dlp.md)| 帮助防止意外共享敏感项目。 | [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)|
|[终结点数据丢失防护](endpoint-dlp-learn-about.md)| 将 DLP 功能扩展到 Windows 10 计算机上使用和共享的项目。 | [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)|
|[Microsoft 合规性扩展](dlp-chrome-learn-about.md) | 将 DLP 功能扩展到 Chrome 浏览器 | [Microsoft 合规性扩展入门](dlp-chrome-get-started.md)|
|[Microsoft 365 数据丢失防护本地扫描程序（预览版）](dlp-on-premises-scanner-learn.md)|将 DLP 对文件活动的监视以及针对这些文件的安全操作扩展到本地文件共享和 SharePoint 文件夹和文档库。|[Microsoft 365 本地扫描仪数据丢失防护入门（预览）](dlp-on-premises-scanner-get-started.md)|
|[保护 Microsoft Teams 聊天和频道消息中的敏感信息](dlp-microsoft-teams.md) | 将一些 DLP 功能扩展到 Teams 聊天和频道消息 | [了解 Microsoft Teams（预览版）中的默认数据丢失防护策略](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>许可要求

MIP 的许可证要求取决于所使用的方案和功能，而不是为本页中列出的每个功能设置许可要求。 若要了解 MIP 的许可要求和选项，请参阅 Microsoft 365 许可文档中的[信息保护](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)部分，并下载[相关 PDF 文档](https://go.microsoft.com/fwlink/?linkid=2139145)以了解功能级别许可要求。
