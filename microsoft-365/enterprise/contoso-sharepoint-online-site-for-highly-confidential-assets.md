---
title: Contoso Corporation 的高度机密数字资产的 SharePoint 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何为高度管控的数据实现 SharePoint 网站，以便在研究团队之间实现协作。
ms.openlocfilehash: bb3c178ee64d5925f82aef9887c06ceafe51f4ee
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403213"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso Corporation 的高度机密数字资产的 SharePoint 网站

 **摘要：** Contoso 如何为高度管控的数据实现 SharePoint 网站，以便在研究团队之间实现协作。
  
Contoso 最有价值的资产是采用商业机密的知识产权，如专用的制造技术和开发中的产品的设计规范。 这些资产是数字表单，最初存储为 SharePoint Server 2016 网站上的文件。 当 Contoso 部署了 Microsoft 365 企业版时，他们希望将其本地数字资产转换为云，以便在巴黎、莫斯科、纽约、北京和 Bangalore 的研究团队中实现更轻松的访问和更多的开放协作。 
  
但是，由于其敏感性，对这些文件的访问权限必须为：

- 限制为允许访问它们的一组用户。 
- 使用数据丢失防护（DLP）策略进行保护，以防止用户在网站外部分发这些文件。
- 通过对权限进行加密和保护，以防止未经授权的用户访问其内容，即使这些用户在网站外部分发也是如此。

Contoso IT 部门的安全性和 SharePoint 管理员决定将[SharePoint 网站用于高度管控的数据](teams-sharepoint-online-sites-highly-regulated-data.md)。
  
Contoso 使用这些步骤为自己的研究团队创建并保护 SharePoint 工作组网站。

## <a name="step-1-created-a-private-sharepoint-team-site"></a>步骤1：创建了私有 SharePoint 团队网站

若要保护对 SharePoint 网站的访问，Contoso IT 配置了[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。

接下来，Contoso IT 管理员编译了其巴黎、莫斯科、纽约、北京和 Bangalore 办事处中的研究人员的用户帐户列表。 

接下来，Contoso IT 管理员创建了名为 "**信息检索**" 的新私有团队网站，并为其研究人员添加了所有用户帐户。

然后，他们为网站配置了其他权限设置，以防止研究人员共享对网站的访问权限，并阻止非工作人员请求访问网站。

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>步骤2：为受限制的 DLP 策略配置网站

首先，Contoso 管理员将现有的**高机密**Office 365 保留标签应用于**信息检索**网站的 Documents 文件夹。

接下来，他们创建了一个名为 "**调查**" 的新 OFFICE 365 DLP 策略：

- 使用 "**高度机密**" Office 365 保留标签。 
- 当用户尝试在 Contoso 之外的**搜索**网站上共享数字资产时阻止他们。

有关配置的详细信息，请参阅[使用保留标签和 DLP 保护 SharePoint 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。

## <a name="step-4-created-an-office-365-sensitivity-sublabel-for-the-site"></a>步骤4：为网站创建了 Office 365 灵敏度选项

Contoso admins 创建了一个新的 Office 365 灵敏度选项，其中的 "**高度机密**" 标签的名称为 "**调查团队**"：

- 需要加密。
- 允许 "**研究**Office 365" 组的 "共同创作" 权限
- 适用于**研究**Office 365 组

以下是针对高度机密资产的**研究**团队网站的结果配置。

![针对高度机密资产的研究团队网站的结果配置](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

**搜索**网站的文件夹中的文件受以下保护：

- 网站权限，仅允许访问**研究**Office 365 组的成员。
- **研究**DLP 策略，它使用**高度机密**的保留标签和阻止文件与外部用户共享的设置。
- **研究团队**敏感度选项，其中包含在文件移动或复制到**信息检索**网站时携带的加密和权限。

下面的示例展示了一个存储在**研究**网站中的文件，其中包含已分配的**研究团队**敏感度选项。

![针对高度机密资产的研究团队网站的结果配置](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>步骤5：迁移了本地 SharePoint 研究数据

Contoso admins 将本地 SharePoint Server 2016 网站中的所有本地研究文件移至新的**研究**SharePoint 网站中的文件夹。

## <a name="step-6-trained-their-researchers"></a>步骤6：训练有素的研究人员

Contoso 安全员工在强制性课程中培训了**研究**Office 365 组的成员，其中包括：

- 如何访问新的**研究**网站及其现有文件。
- 如何在网站上创建新文件和上传本地存储的新文件。
- 有关**信息检索**DLP 策略如何阻止在外部共享文件的演示。
- 如何使用**研究团队**敏感度选项标记文件。
- 演示如何使用**研究团队**子标签来保护文件，即使它是从网站泄漏的也是如此。

最终结果是一个安全的环境，在该环境中，研究人员可以在包含信息检索信息的文件的安全环境中跨 Contoso 进行协作。 

如果与**研究团队**选项的研究文档保留了**信息检索**网站，则只有具有有效用户帐户凭据的**研究**Office 365 组的成员才能对其进行加密和访问。

## <a name="next-step"></a>后续步骤

[部署](deploy-microsoft-365-enterprise.md)组织中的 Microsoft 365 企业。

## <a name="see-also"></a>另请参阅

[Microsoft 365 生产率库](https://aka.ms/productivitylibrary)（https://aka.ms/productivitylibrary)
