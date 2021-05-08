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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: 实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你保护敏感信息。
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259262"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 中的 Microsoft 信息保护

>*[Microsoft 365 安全和合规性许可](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你发现、分类和保护敏感信息。

MIP 功能包含在 Microsoft 365 合规性中，提供了[了解数据](#know-your-data)、[保护数据](#protect-your-data)和[防止数据丢失](#prevent-data-loss)的工具。

![有关 MIP 如何帮助你发现、分类和保护敏感数据的图像](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="了解你的数据":::

有关管理数据的信息，请参阅 [Microsoft 365 中的 Microsoft 信息管理](manage-Information-governance.md)。

## <a name="know-your-data"></a>了解你的数据

> [!NOTE]
> 有关在 Azure Purview 中对数据进行分类和标记的详细信息，请参阅当前处于预览中的[在 Azure Purview 中自动标记内容](/azure/purview/create-sensitivity-label)。
> 
> 有关Azure Purview的发布公告，请参阅以下博客文章：[Microsoft 信息保护和 Microsoft  Azure Purview：中更好地进行协作](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) 和 [IgniteSpring Ignite 2021上的Azure Purview](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919)。

若要了解在混合环境中的数据全景并发现重要数据，请使用以下功能：

:::image type="content" source="../media/knowyourdata-new.png" alt-text="了解你的数据"::: 


|**功能**|**它可以解决哪些问题？**|**入门**|**许可**|
|--|--|--|--|
|[敏感信息类型](sensitive-information-type-entity-definitions.md)| 使用内置或自定义正则表达式或函数，以及包含关键字、可信度水平和接近的补强证据识别敏感数据。 使用敏感信息类型识别组织中特定类型的数据。 使用开箱即用敏感信息类型查找标准类型的数据，如护照号。 创建自定义信息类型以标识环境独有的信息，例如部件号。 | [自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)| |
|[可训练的分类器（预览版）](classifier-learn-about.md)| 使用内置的一个分类器或用自己的内容训练分类器来分类数据 | [可训练的分类器入门（预览版）](classifier-get-started-with.md)| |
|[数据分类](data-classification-overview.md) | 识别具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目及用户对其执行的操作  | [内容资源管理器入门](data-classification-content-explorer.md)<br /><br /> [活动资源管理器入门](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>保护数据

若要应用包含加密、访问限制和视觉标记的灵活保护操作，请使用以下功能：


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="保护数据":::

|**功能**|**它可以解决哪些问题？**|**入门**|**许可**|
|--|--|--|--|
|[敏感度标签](sensitivity-labels.md)| 通过应用、服务和设备提供的单一解决方案，可在你的组织内外进行标记并保护你的数据 <br /><br />示例方案：[在 Power BI 中应用和查看敏感度标签，并保护导出的数据](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[开始使用敏感度标签](get-started-with-sensitivity-labels.md) |
|[Microsoft 云应用安全性](/cloud-app-security/what-is-cloud-app-security)| 发现、标签和保护云中数据存储中的敏感信息 | [发现、分类、标记和保护存储在云中的管控和敏感数据](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Azure 信息保护统一标记扫描器](/azure/information-protection/deploy-aip-scanner)| 发现、标记和保护驻留在本地数据存储区中的敏感信息 | [配置和安装 Azure 信息保护统一标记扫描器](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[活动资源管理器]()||||


## <a name="transition-from-aip-to-mip"></a>从 AIP 转换到 MIP
经典 Azure 信息保护管理体验和客户端将今年初弃。 建议移动到 Microsoft 信息保护。此操作需要迁移所有现有标签和策略。 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="从 AIP 转换到 MIP":::

## <a name="additional-capabilities"></a>其他功能
Microsoft 365 包含以下功能来帮助保护数据：

|**功能**|**它可以解决哪些问题？**|**入门**|
|--|--|--|
| Office 365 邮件加密 (OME) | 请加密发送到任意设备上任何用户的电子邮件和附加文档，以便仅获授权的收件人可阅读电子邮件信息。 <br /><br /> 示例方案：撤销由高级邮件加密加密的电子邮件 | 设置全新的邮件加密功能 |
| 双密钥加密 | 在某些情况下，只有你才能解密受保护的内容，或根据法规要求，必须按地理位置设置加密密钥 | 部署双密钥加密 |  
| 使用客户密钥执行服务加密 | 防止未经授权的系统或人员查看数据，并补充Microsoft数据中心的bitlocker磁盘加密 | 设置 Office 365 的客户密钥 |
| SharePoint 信息权限管理 （IRM） | 保护 SharePoint 列表和库，使用户签出文档时，所下载的文件受到保护，以便只有授权用户能根据指定的策略查看和使用文件 | 在 SharePoint 管理中心设置信息权限管理 (IRM) |
| 权限管理连接器 | 保护使用 Exchange 或 SharePoint Server 和文件分类基础结构 （FCI） 的现有本地部署 | 部署 RMS 连接器的步骤 |



## <a name="prevent-data-loss"></a>防止数据丢失

若要帮助防止意外地过度共享敏感信息，请使用以下功能：

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="防止数据丢失":::

|**步骤**|**说明**|**详细信息**|
|--|--|--|
|[设计 DLP 策略](data-loss-prevention-policies.md)| 规划识别信息（敏感信息类型、标签、其他）模式 <br /><br /> 规划策略的目标位置（服务、客户端、第三方应用。） <br /><br /> 计划策略提示，其他||
||||




|**功能**|**它可以解决哪些问题？**|**入门**|
|--|--|--|
|[了解数据丢失防护](dlp-learn-about-dlp.md)| 帮助防止意外共享敏感项目。 | [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)|
|[了解终结点数据丢失防护](endpoint-dlp-learn-about.md)| 将 DLP 功能扩展到 Windows 10 计算机上使用和共享的项目。 | [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)|
|[了解 Microsoft 合规性扩展（预览版）](dlp-chrome-learn-about.md) | 将 DLP 功能扩展到 Chrome 浏览器 | [Microsoft 合规性扩展（预览版）入门](dlp-chrome-get-started.md)|
|[了解 Microsoft 365 本地扫描仪数据丢失防护（预览）](dlp-on-premises-scanner-learn.md)|将 DLP 对文件活动的监视以及针对这些文件的安全操作扩展到本地文件共享和 SharePoint 文件夹和文档库。|[Microsoft 365 本地扫描仪数据丢失防护入门（预览）](dlp-on-premises-scanner-get-started.md)|
|[保护 Microsoft Teams 聊天和频道消息中的敏感信息](dlp-microsoft-teams.md) | 将一些 DLP 功能扩展到 Teams 聊天和频道消息 | [了解 Microsoft Teams（预览版）中的默认数据丢失防护策略](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>其他资源

许多组织正在使用这些信息保护功能来遵守数据隐私法规。 为了提供帮助，我们设计了指导你通过端到端过程来规划和实施跨 Microsoft 365 功能的工作流，包括安全访问、威胁防护、信息保护和数据管理。 有关详细信息，请参阅[使用 Microsoft 365 为数据隐私法规部署信息保护](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)。 

此外，为帮助规划实施信息保护功能的集成策略，请下载 *Microsoft 365 信息保护与合规性功能* 插图集。  可随时根据自己的使用情况来修改这些插图。

| 项目 | 说明 |
|:-----|:------------|
|[![模型海报：Microsoft 365 信息保护和合规性功能](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [以 PDF 格式下载](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [以 Visio 格式下载](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> 日语：[以 PDF 格式下载](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [以 Visio 格式下载](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> 更新时间：2020年 10 月|包括： <ul><li>  Microsoft 信息保护和数据丢失防护</li><li>保留策略和保留标签 </li><li>信息屏障</li><li>通信合规性</li><li>内部风险管理</li><li>第三方数据摄取</li>|

