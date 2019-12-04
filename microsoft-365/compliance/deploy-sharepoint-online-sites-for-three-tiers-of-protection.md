---
title: 部署具有三层保护的 SharePoint Online 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 摘要：为各种级别的信息保护创建和配置 SharePoint Online 团队网站。
ms.openlocfilehash: 1396a45103bfbaf6ea2de6c5ba6c4b086da344ec
ms.sourcegitcommit: 58a7bd70a4bcf52530baf5f82507fd5dc4455fd9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "39668860"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a>部署具有三层保护的 SharePoint Online 网站

使用本文中的步骤设计和部署基线、敏感和高度机密的 SharePoint Online 团队网站。 有关三层保护的详细信息，请参阅[保护 SharePoint Online 网站和文件](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)。
  
## <a name="baseline-sharepoint-online-team-sites"></a>基线 SharePoint Online 团队网站

基线保护同时包括公共和专用团队网站。 组织中的任何人均可发现并访问公共团队网站。 只有与团队网站关联的 Office 365 组的成员才可以发现并访问专用网站。 两种类型的团队网站均允许成员与他人共享网站。
  
### <a name="public"></a>公开

要创建具有公共访问和权限的基线 SharePoint Online 团队网站，请按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)操作。

下面是生成的配置。
  
![适用于公共 SharePoint Online 团队网站的基线级保护。](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a>私人

要创建具有专用访问和权限的基线 SharePoint Online 团队网站，请按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)操作。
  
下面是生成的配置。
  
![适用于专用 SharePoint Online 团队网站的基线级保护。](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a>敏感 SharePoint Online 团队网站

敏感的 SharePoint Online 团队网站首先是一个专用团队网站。
  
首先，按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)创建专用 SharePoint Online 团队网站。

接下来，在新的 SharePoint Online 团队网站中，按照以下步骤操作配置其他权限。

1.  在 SharePoint 团队网站的工具栏中，依次单击设置图标和“**网站权限**”。
2.  在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。
3.  在“共享权限”下方，选择“仅网站所有者可以共享文件、文件夹和网站”，然后单击“保存”************。

下面是这些权限设置的结果：

- 已禁用成员间的相互共享功能。
- 启用非成员请求访问的功能。

下面是生成的配置。
  
![适用于独立 SharePoint Online 团队网站的敏感级保护。](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
通过其中一个访问组的组成员身份，网站成员现可对网站资源进行安全协作。
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a>高度机密的 SharePoint Online 团队网站

高度机密的 SharePoint Online 团队网站是一个具有额外权限设置的专用团队网站。

首先，按照[这些说明](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)创建专用 SharePoint Online 团队网站。

接下来，在新的 SharePoint Online 团队网站中，按照以下步骤操作配置其他权限。

1.  在 SharePoint 团队网站的工具栏中，依次单击设置图标和“**网站权限**”。
2.  在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。
3.  在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。
4. 关闭“**允许访问请求**”，然后单击“**保存**”。

下面是这些权限设置的结果：

- 已禁用成员间的相互共享功能。
- 禁用非成员请求访问的功能。

下面是生成的配置。
  
![适用于独立 SharePoint Online 团队网站的高度机密级保护。](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
通过其中一个访问组的组成员身份，网站成员现可对网站资源进行安全协作。
  
## <a name="next-step"></a>后续步骤

[使用 Office 365 标签和 DLP 保护 SharePoint Online 文件](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a>另请参阅

[保护 SharePoint Online 网站和文件](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[云应用和混合解决方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
