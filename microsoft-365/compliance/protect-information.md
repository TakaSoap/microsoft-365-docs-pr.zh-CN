---
title: Microsoft 365 中的 microsoft 信息保护
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 实施 Microsoft 信息保护 (MIP) ，可帮助您在任何生存或传播的地方保护敏感信息。
ms.openlocfilehash: 639f41f5d06e78e39071c60d6de0386a87536672
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951125"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 中的 microsoft 信息保护

>*[Microsoft 365 安全 & 合规性许可](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

实施 Microsoft 信息保护 (MIP) ，以帮助您发现、分类和保护任何位置的敏感信息或传播。

MIP 功能包含在 Microsoft 365 合规性中，并提供了用于 [了解数据](#know-your-data)、 [保护数据](#protect-your-data)和 [防止数据丢失](#prevent-data-loss)的工具。

![MIP 如何帮助您发现、分类和保护敏感数据的图像](../media/powered-by-intelligent-platform.png)

有关管理数据的信息，请参阅 microsoft [365 中的 Microsoft 信息管理](manage-Information-governance.md)。

## <a name="know-your-data"></a>了解你的数据

若要了解您的数据在混合环境中的前景和标识重要数据，请使用以下功能：
 
|功能|它会解决什么问题？|入门|
|:------|:------------|:--------------------|:-----------------------------|
|[敏感信息类型](sensitive-information-type-entity-definitions.md)| 使用内置或自定义正则表达式或函数标识敏感数据，以及包含关键字、可信度和邻近度的确定证据。| [自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)|
|[Trainable 类元 (预览) ](classifier-learn-about.md)| 使用内置分类器之一为您分类数据，或使用自己的内容对分类器进行训练 | [可训练的分类器入门（预览版）](classifier-get-started-with.md) |
|[数据分类](data-classification-overview.md) | 标识具有敏感度标签、保留标签或已在组织中将其分类为敏感信息类型的项目，以及用户对其执行的操作  | [内容资源管理器入门](data-classification-content-explorer.md)<br /><br /> [活动资源管理器入门](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>保护你的数据

若要应用包含加密、访问限制和可视标记的灵活保护操作，请使用以下功能：

|功能|它会解决什么问题？|入门|
|:------|:------------|---------------------|:----------------------------|
|[敏感度标签](sensitivity-labels.md)| 跨应用、服务和设备的单一解决方案，以在您的组织内部和外部传输数据时对数据进行标记和保护 <br /><br />示例方案： [在 POWER BI 中应用和查看敏感度标签，并在导出数据时对数据进行保护](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[ 敏感度标签入门](get-started-with-sensitivity-labels.md) |
|[Azure 信息保护统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| 对于 Windows 计算机，扩展敏感度标签以获取其他特性和功能，包括标记和保护文件资源管理器和 PowerShell 中的所有文件类型<br /><br /> 示例其他功能： [Azure 信息保护统一标签客户端的自定义配置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure 信息保护统一标签客户端管理员指南](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[双密钥加密](double-key-encryption.md)| 在所有情况下，只有您可以对受保护的内容进行解密，或者需要在地理边界内保留加密密钥 | [部署双密钥加密](double-key-encryption.md#deploy-dke)|
|[Office 365 邮件加密 (OEM) ](ome.md)| 对发送到任何设备上任何用户的电子邮件和附加文档进行加密，以便只有授权的收件人才能阅读电子邮件信息  <br /><br />示例方案： [撤消由高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md) | [设置全新的邮件加密功能](set-up-new-message-encryption-capabilities.md)|
|[使用客户密钥进行服务加密](customer-key-overview.md) | 防止未经授权的系统或人员查看数据，并补充 Microsoft 数据中心中的 BitLocker 磁盘加密 | [设置 Office 365 的客户密钥](customer-key-set-up.md)|
|[SharePoint 信息权限管理 (IRM) ](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|保护 SharePoint 列表和库，以便在用户签出文档时，已下载的文件受到保护，以便只有授权的用户可以根据您指定的策略查看和使用该文件 | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[权限管理连接器](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |仅对使用 Exchange 或 SharePoint Server 的现有本地部署或运行 Windows Server 和文件分类基础结构的文件服务器的保护， (FCI)  | [部署 RMS 连接器的步骤](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure 信息保护统一标签扫描程序](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| 发现、标记和保护驻留在位于本地的数据存储区中的敏感信息 | [配置和安装 Azure 信息保护统一标签扫描程序](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 发现、标记和保护驻留在位于云中的数据存储中的敏感信息 | [发现、分类、标记和保护存储在云中的管控和敏感数据](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 信息保护 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|将敏感度标签扩展到第三方应用程序和服务  <br /><br /> 示例方案： [设置和获取 (c + +) 的敏感度标签 ](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft 信息保护 (MIP) SDK 安装和配置](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>防止数据丢失

为了帮助防止意外 oversharing 敏感信息，请使用以下功能：


|功能|它会解决什么问题？|入门|
|:------|:------------|:---------------------|:-----------------------------|
|[Data loss prevention (DLP)](data-loss-prevention-policies.md)| 帮助防止意外共享敏感项目 <br /><br />示例方案： [保护 Microsoft 团队聊天和频道消息中的敏感信息](dlp-microsoft-teams.md) | [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)|
|[终结点数据丢失防护 (预览) ](endpoint-dlp-learn-about.md)| 将 DLP 功能扩展到在 Windows 10 计算机上使用和共享的项目 | [终结点数据丢失防护（预览）入门](endpoint-dlp-getting-started.md)|
