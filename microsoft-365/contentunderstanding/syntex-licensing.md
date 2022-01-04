---
title: SharePoint Syntex 的许可
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: high
description: 了解 SharePoint Syntex 的许可
ms.openlocfilehash: c8ed6b8b5864e0d859e0cbf8655406966e78ff3b
ms.sourcegitcommit: d7cdbdda9b829c49caa3105eb47d3f26b88a5daf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2022
ms.locfileid: "61660150"
---
# <a name="licensing-for-sharepoint-syntex"></a>SharePoint Syntex 的许可

若要使用 SharePoint 整合，您的组织必须具有 SharePoint Syntex 订阅，并且每个 Syntex 用户必须具有许可证。 如果将来（或试用版过期）取消 SharePoint Syntex 订阅，用户将无法创建、发布或运行文档了解或表单处理模型。 此外，术语库报表、SKOS 分类导入和内容类型推送将不再可用。 将不会删除任何模型、内容或元数据，并且不会更改网站权限。
 
> [!NOTE] 
> SharePoint Syntex 是一个加载项许可证，要求用户还应具有 Microsoft 365 许可证。
 
## <a name="tasks-requiring-a-license"></a>需要许可证的任务
 
以下任务需要执行者拥有 [SharePoint Syntex 许可证](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex)：
 
- 将文档理解模型应用于库。（可以向未经授权的用户授予对内容中心的访问权限，并可在其中创建文档理解模型，但不能将其应用于文档库。）
- 通过库中的入口点创建表单处理模型
- 将内容上传到已应用文档理解或表单处理模型的库
- 按需运行文档理解模型
- 使用文档理解或表单处理模型查看从文件中提取的元数据。 （用户必须获得访问和使用与已处理文件关联的元数据的许可，无论文件移动到何处。）
- 使用高级分类服务。（高级分类服务包括基于 SKOS 的术语集导入、将企业内容类型推送到与中心关联的网站和术语库报表。）

未经许可的用户可以被授予访问内容中心的权限，并可在其中创建文档理解模型，但无法将其应用于文档库。
 
## <a name="cost-of-running-models"></a>运行模型的成本
 
运行文档理解模型的成本包含在 SharePoint Syntex 许可证的成本中。 但是，表单处理模型使用 AI Builder 容量进行训练和运行时处理。 必须将容量分配给要在其中使用 AI 生成器的 Power Apps 环境。
 
如果你的组织中的 SharePoint Syntex有300或更多SharePoint Syntex 许可证，则会分配一百万个 AI 生成器点数。 如果保持最低 300 个许可证，则每月会续订此容量。 （未使用的额度不会累积到下个月。）如果许可证少于 300 个，则必须购买 AI 生成器才能使用表单处理。
 
可使用 [AI 生成器计算器](https://powerapps.microsoft.com/ai-builder-calculator)来估算出适合你的AI 生成器容量。

如果计划使用自定义 Power Platform 环境，必须 [向该环境分配点数](/power-platform/admin/capacity-add-on)。

转到 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/resources/capacity)，以查询点数和使用情况。
  
## <a name="additional-term-store-features"></a>其他术语库功能
 
SharePoint Syntex 订阅具有以下附加术语库功能：
 
- 基于 SKOS 的术语集导入
- 将企业内容类型推送到中心网站，该网站还会将其添加到关联的网站以及任何新创建的列表或库
- 术语库报表提供对已发布术语集及其在租户中的使用情况的见解


## <a name="see-also"></a>另请参阅

[Microsoft Power Platform 的许可概述](/power-platform/admin/pricing-billing-skus)

[Power Apps 和 Power Automate 许可常见问题解答](/power-platform/admin/powerapps-flow-licensing-faq)
