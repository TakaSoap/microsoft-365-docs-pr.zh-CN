---
title: 使用敏感度标签保护 SharePoint Online 文件
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
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：应用 Azure 信息保护来保护高度机密的 SharePoint Online 团队网站中的文件。
ms.openlocfilehash: b5251d393249e9023f6f437cb3df6c074ebdf436
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "39637710"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>使用敏感度标签保护 SharePoint Online 文件

使用本文中的步骤配置 Office 365 敏感度标签，从而为文件提供加密和各种权限。 你可以将这些文件添加到配置为高度机密保护的 SharePoint 库中。 或者，也可以直接从网站打开文件，并应用相应标签。 加密和权限保护会一直跟随文件，即使从网站上下载下来也是如此。 

为 SharePoint 网站及其中文件配置高度机密保护的大型解决方案采用这些步骤。有关详细信息，请参阅[保护 SharePoint Online 网站和文件](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)。 

对于有些客户而言，不建议对 SharePoint Online 中的文件使用敏感度标签，但对于部分文件需要这种保护级别的客户，这提供了一种选择。

关于此解决方案，请务必注意以下几点：
- 将加密应用于 Office 365 中存储的文件时，该服务无法处理这些文件的内容。 共同创作、电子数据展示、搜索、Delve 和其他协作功能将无法正常使用。 数据丢失防护 (DLP) 策略只适用于元数据（包括 Office 365 标签），但并不适用于这些文件的内容（如文件内的信用卡号）。

- 此解决方案要求用户选择应用相应保护的标签。 如果需要自动加密以及支持 SharePoint 索引和检查文件的功能，请考虑在 SharePoint Online 中使用信息权限管理 (IRM)。 为 IRM 配置 SharePoint 库时，文件会在下载以供进行编辑时自动进行加密。  SharePoint IRM 包含可能会影响你的决策的限制。 有关详细信息，请参阅[在 SharePoint 管理中心设置信息权限管理 (IRM)](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C)。

## <a name="admin-setup"></a>管理员设置

若要以这种方式为特定 SharePoint Online 团队网站中的文件实现更高的安全级别，必须配置一个自定义的敏感度标签，以用作其自身标签，或作为高度管控数据的常规标签的子标签。 只有 SharePoint Online 团队网站的 Office 365 组的成员才能在其标签列表中看到自定义标签或子标签。

- 如果需要将少量标签应用于全局和各个私人团队，请使用敏感度标签。

- 如果你拥有大量标签，或者希望在高度管控标签下整理高度机密团队的标签，请使用敏感度子标签。

按照[这些说明](encryption-sensitivity-labels.md)，使用以下设置配置单独的标签或子标签：

- 标签或子标签名称包含团队网站的名称
- 已启用加密
- 团队网站的 Office 365 组有共同创作权限

创建后，为用户发布新的标签或子标签，用户可在将文件上传到团队之前或文件存储在团队中之后，将其应用到文件。
 
使用后，在 Microsoft Word、Excel 和 PowerPoint 中，可从“**开始**”功能区中的“**敏感度**”选项中选择敏感度标签。
  
> [!NOTE]
> 如果你有多个高度敏感的 SharePoint Online 团队网站，则应创建多个敏感度标签。 
  
## <a name="adding-permissions-for-external-users"></a>为外部用户添加权限
可通过两种方式授予使用敏感度标签进行保护的文件的外部用户访问权限。 在这两种情况下，外部用户均须具有 Azure AD 帐户。 如果外部用户不是使用 Azure AD 的组织的成员，他们可以通过使用此注册页面以个人身份获得 Azure AD 帐户：[https://aka.ms/aip-signup](https://aka.ms/aip-signup)。

 - 将外部用户添加到团队网站的 Office 365 组中。 首先需要将帐户添加为目录中的 B2B 用户。 [通过 Azure Rights Management 缓存组成员身份](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)可能需要数小时。  
 - 将外部用户帐户直接添加到标签配置。 可以添加组织（例如 Fabrikam.com）中的所有用户、一个 Office 365 组（例如组织内的财务组）或单个用户。 例如，可以将外部监管人员团队添加到敏感度标签权限。

## <a name="see-also"></a>另请参阅

[保护 SharePoint Online 网站和文件](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)
  
[Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[云应用和混合解决方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
