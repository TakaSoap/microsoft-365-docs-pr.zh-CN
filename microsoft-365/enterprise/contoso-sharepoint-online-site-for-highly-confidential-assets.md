---
title: Contoso Corporation 高度机密数字资产的 SharePoint Online 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '摘要: Contoso 如何为高度管控的数据实施 SharePoint Online 网站, 以便在研究团队之间更轻松地进行协作。'
ms.openlocfilehash: c20e3a1c4ad0b862e81b897acc1462e3a1d1f776
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289212"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso Corporation 高度机密数字资产的 SharePoint Online 网站

 **摘要:** Contoso 如何为高度管控的数据实施 SharePoint Online 网站, 以便在其研究团队之间实现更好的协作。
  
Contoso 最有价值的资产是采用商业机密的知识产权, 如专用的制造技术和开发中的产品的设计规范。 这些资产采用数字形式, 最初存储为 SharePoint Server 2016 网站上的文件。 当 Contoso 部署了 Microsoft 365 企业版时, 他们希望将其本地数字资产转换为云, 以便在巴黎、莫斯科、纽约、北京和 Bangalore 的研究团队中实现更轻松的访问和更多的开放协作。 
  
但是, 由于其敏感性, 对这些文件的访问权限必须为:

- 限制为允许查看或更改的一组用户, 并且仅拥有由 SharePoint 管理员管理的网站的持续权限。 
- 受数据丢失防护 (DLP) 保护, 以防止用户在网站外部分发这些文件。
- 使用访问控制列表进行加密和保护, 以防止未经授权的用户访问其内容, 即使这些用户在网站外部分发也是如此。

Contoso IT 部门的安全性和 SharePoint 管理员决定将[SharePoint Online 网站用于高度管控的数据](teams-sharepoint-online-sites-highly-regulated-data.md)。
  
Contoso 使用这些步骤为其研究团队创建并保护 SharePoint Online 团队网站。

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>步骤 1: 查看并验证了研究团队组的成员

Contoso IT 管理员对其研究工作组的一组安全组进行了检查。 他们删除了不是研究人员或不需要访问调查资产的任何人。 

它们还创建了以下新的安全组:

- **研究-管理员** 具有对网站的完全控制权限的 SharePoint 管理员集, 包括修改权限的能力。
- **研究-成员** 世界各地的研究团队的一组安全组。
- **研究-查看者** 一组管理用户 (例如, 研究组织中的执行人员), 它只能查看网站上的资产。

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>步骤 2: 创建了独立的 SharePoint Online 团队网站 

Contoso SharePoint 管理员首先创建一个名为 "**信息检索**" 的新团队网站。 然后配置它们:

- 使用 "调查所有者" 的 "完全控制" 权限级别, SharePoint 组将 "**研究管理员**" 安全组作为成员
- "编辑" 权限级别, 以使用 "研究成员" SharePoint 组, 其中的 "**调查成员**" 安全组作为成员
- 使用 "搜索访问者" 的 "读取" 权限级别 (将 "**调查查看**器" 安全组作为成员) 的 SharePoint 组

下面是生成的 sharepoint 权限级别、sharepoint 组及其成员。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

接下来, 他们配置了对网站的其他限制。

有关配置的详细信息, 请参阅[部署独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)。

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>步骤 3: 为受限制的 DLP 策略配置网站

首先, Contoso 管理员将**高度机密**的 Office 365 保留标签应用于**信息检索**网站。

接下来, 他们创建了一个名为 "**调查**" 的新 Office 365 DLP 策略:

- 使用 "**高度机密**" Office 365 保留标签。 
- 将应用于**信息检索**网站。
- 阻止用户共享文档。

有关配置的详细信息, 请参阅[使用 Office 365 标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>步骤 4: 为网站创建了 Azure 信息保护子标签

Contoso admins 在作用域策略中创建了一个新的 Azure 信息保护子标签, 其名称为 "**调查**范围策略" 中的默认**高度机密**标签:

- 需要加密。
- 允许由**研究成员**安全组的成员进行完全访问。
- 允许由**研究查看者**安全组的成员进行读取访问。

接下来, 他们将 Azure 信息保护客户端部署到研究团队成员的设备。

有关配置的详细信息, 请参阅[使用 Azure 信息保护保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。 

以下是针对高度机密资产的**研究**网站的结果配置。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

**搜索**网站的文件夹中的文件受以下保护:

- **研究**Azure 信息保护选项, 它将加密和 permssions 应用于从**搜索**网站移动或复制文件时携带文件的每个文件。
- **研究**DLP 策略, 使用可阻止文件离开网站的**高度敏感**保留标签和设置。
- 一组网站权限, 仅允许对**搜索成员**的成员和研究**者**安全组的成员以及**研究管理员**安全组的成员进行管理。

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>步骤 5: 迁移了本地 SharePoint 研究数据

Contoso admins 将本地 SharePoint Server 2016 网站中的所有本地研究文件移至新的**研究**SharePoint Online 网站中的文件夹。

## <a name="step-6-trained-their-users"></a>步骤 6: 训练有素的用户 

Contoso 安全员工在强制性课程中培训了研究团队, 其中包括:

- 如何访问新的**研究**SharePoint Online 网站及其现有文件。
- 如何在网站上创建新文件和上传本地存储的新文件。
- 有关 DLP 策略如何阻止在外部共享文件的演示。
- 如何使用 Azure 信息保护客户端通过 "**研究**" 子标签为搜索文件添加标签。
- 演示如何使用**研究**子标签保护文件, 即使它是从网站泄漏的也是如此。

最终结果是一个安全的环境, 在该环境中, 研究人员可以在安全环境中跨整个组织进行协作。 

如果与信息检索子标签**** 的研究文档泄露, 则仅对**** 使用有效凭据的**搜索成员**和**研究查看者**安全组的成员进行加密和访问。

## <a name="next-step"></a>后续步骤

[部署](deploy-microsoft-365-enterprise.md)组织中的 Microsoft 365 企业。

