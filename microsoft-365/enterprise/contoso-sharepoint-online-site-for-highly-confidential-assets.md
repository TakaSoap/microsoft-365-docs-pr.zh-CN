---
title: Contoso 公司的高度机密数字资产的 SharePoint Online 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 摘要： 如何 Contoso 实现的 SharePoint Online 网站高度监管的数据之间其研究更轻松地协作的团队。
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865990"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso 公司的高度机密数字资产的 SharePoint Online 网站

 **摘要：** 如何 Contoso 实现其信息检索团队之间的更轻松地协作的高度管控数据的 SharePoint Online 网站。
  
Contoso 的最有价值资产其知识产权的交易机密，如专有制造技术的窗体，并设计规范中开发的产品。这些资产相关数字形式，最初存储为 SharePoint Server 2016 网站上的文件。当 Contoso 部署 Microsoft 365 企业版时，他们希望跨研究 リ モ ・ 巴黎、 莫斯科，纽约、 北京和班加罗尔转换到云中更轻松地访问和更多 open 协作其内部部署数字资产。 
  
但是，由于其敏感性，必须将访问这些文件：

- 限制为一组允许查看或更改它们与持续仅由 SharePoint 管理员管理网站的权限的人员。 
- 保护与数据丢失防护 (DLP) 若要防止用户分发这些外部网站。
- 加密和与受保护的访问控制列表以防止未经授权的用户访问其内容，即使它们外部网站分发。

Contoso 中的安全和 SharePoint 管理员的 IT 部门决定使用[SharePoint Online 网站高度管控数据](teams-sharepoint-online-sites-highly-regulated-data.md)。
  
Contoso 使用以下步骤来创建和保护其研究团队 SharePoint Online 团队网站。

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>步骤 1： 检查和验证的信息检索团队组成员

Contoso IT 管理员执行的安全组设置查看其研究团队。中删除这些人不是一位研究或不需要对研究资产的访问。 

他们还和创建这些新的安全组：

- **研究管理员** SharePoint 管理员具有完全控制的网站，其中包括可以修改权限集。
- **研究成员** 世界各地的信息检索小组的安全组的集合。
- **研究查看器** 管理用户，例如，可以查看网站的资产的信息检索组织中的执行官集。

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>步骤 2： 创建独立的 SharePoint Online 团队网站 

首次创建新的工作组网站的 Contoso SharePoint admins 名为**研究**。它们然后配置：

- 要使用的信息检索所有者 SharePoint 组中，上面有**研究管理员**安全组成员身份的完全控制权限级别
- 编辑权限级别，以使用研究成员 SharePoint 组中，已作为成员的**信息检索成员**安全组
- 读取权限级别，若要使用的信息检索访问者 SharePoint 组中，上面有**研究查看者**安全组成员身份

下面是生成的 SharePoint 权限级别、 SharePoint 组和及其成员。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

接下来，它们配置网站的其他限制。

有关配置的详细信息，请参阅[部署独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)。

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a>步骤 3： 配置严格的 Office 365 标签 DLP 策略的站点

首先，Contoso admins 应用到**Research**网站的**高度机密**的 Office 365 标签。

接下来，创建一个新 Office 365 DLP 策略名为**Research**的：

- 使用**高度机密**的 Office 365 标签。 
- 应用于**Research**网站。
- 防止用户共享文档。

配置详细信息，请参阅[Office 365 标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>步骤 4： 创建网站 Azure 信息保护子标签

创建一个新的 Azure 信息保护子标签的 Contoso admins 名为**Research**的作用域策略中的默认**高度机密**标签的：

- 要求加密。
- 允许通过**Research 成员**安全组的成员的完全访问权限。
- 允许**研究查看者**安全组的成员的读访问权限。

接下来，它们部署到的设备研究小组成员的 Azure 信息保护客户端。

有关配置详细信息，请参阅[Azure 信息保护保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。 

下面是生成的高度机密资产的**信息检索**网站配置。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>步骤 5： 迁移的本地 SharePoint 研究数据

Contoso admins 移动内部部署的所有调查中新的**研究**SharePoint Online 站点中的文件夹的内部部署 SharePoint Server 2016 网站的文件。

## <a name="step-6-trained-their-users"></a>步骤 6： 培训用户 

Contoso 安全人员培训研究 リ モ ・ 强制课程单它们通过执行：

- 如何访问新的**研究**SharePoint Online 网站和其现有的文件。
- 如何在网站上创建新文件和上传本地存储的新文件。
- 演示如何的 DLP 策略阻止从外部共享文件。
- 如何使用 Azure 信息保护客户端标签研究**信息检索**子标签文件。
- **研究**子标签如何保护文件，即使它从网站泄露演示。

最终结果是安全的环境中文档的科学家可以安全环境中在组织内进行协作。 

如果从**Research**网站被泄露**研究**子标签研究文档，则加密和仅使用有效的凭据的**信息检索成员**和**研究查看者**安全组的成员才能访问。

## <a name="next-step"></a>后续步骤

在组织中[部署](deploy-microsoft-365-enterprise.md) Microsoft 365 企业版。

