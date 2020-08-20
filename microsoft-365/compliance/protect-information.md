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
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 通过使用 Microsoft 365 (合规性，) Microsoft 信息保护和功能，以帮助你发现、分类和保护敏感信息（不受保留或出移动）。
ms.openlocfilehash: 96082bc70b093e763be00c847bb6a68ce302c8a9
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815196"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 中的 Microsoft 信息保护

>*[Microsoft 365 安全中心合规性&许可](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

使用 Microsoft 信息保护 (M) IP 密钥来帮助你在其所在位置或传输的敏感信息位置上进行发现、分类和保护。

MIP 功能随 Microsoft 365 合规中心随附，为你提供[了解数据](#know-your-data)[、保护数据](#protect-your-data)[和防止数据丢失的工具](#prevent-data-loss)。

![了解数据，保护数据，防止数据丢失，管理数据](../media/powered-by-intelligent-platform.png)

有关管理数据的信息，请参阅 [Microsoft 365 中的 Microsoft](manage-Information-governance.md)信息管理。

## <a name="know-your-data"></a>了解你的数据

若要了解数据环境的数据环境并识别混合环境中的重要数据，请使用以下功能：
 
|功能|它可以解决什么问题？|入门|
|:------|:------------|:--------------------|:-----------------------------|
|[敏感信息类型](sensitive-information-type-entity-definitions.md)| 使用内置或自定义正则表达式或函数，以及包括关键字、可信度和邻近度的确证性证据来标识敏感数据。| [自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)|
|[可训录的分类器 (预览) ](classifier-getting-started-with.md)| 为你分类数据，使用内置分类器之一或使用自己的内容训录分类器 | [创建可训训的分类器 (预览) ](classifier-creating-a-trainable-classifier.md) |
|[数据分类](data-classification-overview.md) | 标识其具有敏感度标签、保留标签或已在组织中被分类为敏感信息类型的项目以及用户对这些项执行的操作  | [内容资源管理器入门](data-classification-content-explorer.md)<br /><br /> [活动资源管理器入门](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>保护你的数据

若要应用灵活的保护操作，包括加密、访问限制和视觉标记，请使用以下功能：

|功能|它可以解决什么问题？|入门|
|:------|:------------|---------------------|:----------------------------|
|[敏感度标签](sensitivity-labels.md)| 当数据传输到组织内外时，跨应用、服务和设备对数据进行标记和保护的单个解决方案 <br /><br />示例场景 [：在 Power BI 中应用和查看敏感度标签，并在导出数据时保护数据](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|[ 开始使用敏感度标签](get-started-with-sensitivity-labels.md) |
|[Azure 信息保护统一标记客户端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| 对于 Windows 计算机，针对其他特性和功能扩展敏感度标签，包括从文件资源管理器和 PowerShell 标记和保护所有文件类型<br /><br /> 其他功能示例 [：Azure 信息保护统一标记客户端的自定义配置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure 信息保护统一标记客户端管理员指南](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[双密钥加密](double-key-encryption.md)| 在所有情况下，只有你永远可以解密受保护的内容，或者为了符合要求，您必须保留地理边界内加密密钥 | [部署双密钥加密](double-key-encryption.md#deploy-double-key-encryption)|
|[OME 邮件处理 Office (365](ome.md) 邮件) | 对电子邮件进行加密并加密发送给任何设备上的任何用户的附加文档，以便只有授权收件人才能阅读电子邮件信息  <br /><br />示例应用 [场景：吊销使用高级邮件加密进行加密的电子邮件](revoke-ome-encrypted-mail.md) | [Office 365 邮件加密入门](set-up-new-message-encryption-capabilities.md)|
|[使用客户密钥执行服务加密](customer-key-overview.md) | 防止未经授权的系统或人员查看数据，并补充了 Microsoft 数据中心中的 BitLocker 磁盘加密 | [设置 Office 365 的客户密钥](customer-key-set-up.md)|
|[SharePoint 信息权限管理 (IRM) ](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|保护 SharePoint 列表和库，以便用户签出文档时，下载的文件会受到保护，以便只有授权人员才能按照您指定的策略查看和使用该文件 | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[权限管理连接器](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |仅对使用 Exchange 或 SharePoint Server 的现有本地部署，或者运行 Windows Server 和文件分类基础结构且 FCI 文件服务器 (保护)  | [部署 RMS 连接器的步骤](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure 信息保护统一标签扫描程序](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| 发现、添加和保护驻留在本地数据存储中的敏感信息 | [配置和安装 Azure 信息保护统一标签扫描程序](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 发现、添加和保护驻留在云端数据存储中的敏感信息 | [发现、分类、标记和保护存储在云中的管控和敏感数据](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 信息保护 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|将敏感度标签扩展到第三方应用和服务  <br /><br /> 示例方案 [：设置并获取 C++ 的 (敏感) ](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[M) IP 向导 (配置配置的 Microsoft 信息保护](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>防止数据丢失

为了有助于防止意外过度共享敏感信息，请使用以下功能：


|功能|它可以解决什么问题？|入门|
|:------|:------------|:---------------------|:-----------------------------|
|[DLP 的数据丢失 (DLP](data-loss-prevention-policies.md)) | 有助于防止意外共享敏感项 <br /><br />示例场景： [保护 Microsoft Teams 聊天和频道消息中的敏感信息](dlp-microsoft-teams.md) | [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)|
|[终结点数据丢失防护 (预览) ](endpoint-dlp-learn-about.md)| 将 DLP 功能扩展到在 Windows 10 计算机上使用和共享的项目 | [终结点数据丢失防护（预览）入门](endpoint-dlp-getting-started.md)|
