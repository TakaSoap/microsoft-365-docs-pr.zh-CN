---
title: 建议的安全文档策略 - Microsoft 365 企业版 | Microsoft Docs
description: 介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72dd50649dba9e290d50c2831557c06db3cb7586
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865684"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>有关保护 SharePoint 网站和文件的策略建议
本文介绍如何实现建议的标识和设备访问策略以保护 SharePoint Online 和 OneDrive for Business。本指南基于[常见标识和访问策略的设备](identity-access-policies.md)。 

这些建议基于三个不同级别的安全和保护可以应用的 SharePoint 文件 （英文） 根据您的需求的粒度：**基线**、**敏感**和**高度管控**。您可以了解有关这些安全层及推荐客户端的操作系统，通过这些建议[概述](microsoft-365-policies-configurations.md)中引用的详细信息。

除了实现本指南，请确保使用适量的保护，包括设置敏感和高度规范化的内容的适当权限配置 SharePoint 网站。创建站点的比较基准，敏感和高度规范化保护的详细信息，请参阅[安全 SharePoint Online 网站和文件](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)。 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>更新常见的策略，以包含 SharePoint 和 OneDrive for Business
下图演示了用来保护中 SharePoint Online 和 OneDrive for Business 的文件的建议策略的组。表示哪些策略应更新或新创建的以添加对 SharePoint Online 和 OneDrive for Business 的保护。

![SharePoint Online 和 OneDrive 策略的摘要。](../images/identity-access-ruleset-sharepoint.png)

如果您包括 SharePoint Online 中创建的常用策略时，您只需要创建新策略。配置条件访问规则，SharePoint Online 中包括的 OneDrive for Business。

新增的策略通过应用到您指定的 SharePoint 网站的特定访问要求实现设备保护敏感和高度规范化的内容。 

下表列出您也需要查看和更新或创建新的 SharePoint Online 的策略。常见策略链接到[常见的标识和设备访问策略](identity-access-policies.md)一文中的关联的配置说明。


|保护级别|Policies|更多信息|
|:---------------|:-------|:----------------|
|**基线**|[*中等*或*高*风险登录时需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 SharePoint Online 中分配的云应用程序|
|        |[阻止客户端不支持现代身份验证](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|包含 SharePoint Online 中分配的云应用程序|
|        |[定义应用程序保护策略](identity-access-policies.md#define-app-protection-policies)|确保所有建议的应用程序都包含在应用程序的列表。一定要更新的策略，为每个平台 (iOS，Android、 Windows)|
|        |[需要符合标准的 Pc](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在列表中的云应用程序包括 SharePoint Online|
|        |[在 SharePoint Online 中使用应用程序强制实施限制](#use-app-enforced-restrictions-in-sharepoint-online)|添加此新策略。这会告诉 Azure AD 以使用 SharePoint Online 中指定的设置。此规则应用于所有用户，但只影响对 SharePoint Online 访问策略中包括的网站的访问|
|**敏感**|[*低*、*中*或*高*风险登录时需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 SharePoint Online 中的云应用程序的分配|
|         |[需要符合标准的 Pc*和*移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|包含列表中的云应用程序的 SharePoint Online|
||[SharePoint Online 访问控制策略](#sharepoint-online-access-control-policies)： 允许从非托管设备仅浏览器访问特定的 SharePoint 网站|这样可以防止编辑和下载文件。使用 PowerShell，可以指定站点|
|**高度管控**|[*始终*需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|包含 SharePoint Online 中分配的云应用程序|
||[SharePoint Online 访问控制策略](#use-app-enforced-restrictions-in-sharepoint-online)： 从非托管设备阻止到特定的 SharePoint 网站的访问|使用 PowerShell，可以指定站点|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>在 SharePoint Online 中使用应用程序强制实施的限制
如果在 SharePoint Online 中实现访问控制，您必须在 Azure AD 以告知 Azure AD 实施 SharePoint Online 中配置的策略创建该条件访问策略。此规则应用于所有用户，但只影响对使用 PowerShell 在 SharePoint Online 中创建的访问控制时指定网站的访问。

本文中配置此策略，请参阅 《 到特定的 SharePoint 网站集或 OneDrive 帐户的阻止或限制访问":[控件从非托管的设备的访问](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。


## <a name="sharepoint-online-access-control-policies"></a>SharePoint Online 访问控制策略
Microsoft 建议您保护敏感和高度规范化与设备访问控件的内容与 SharePoint 网站中的内容。通过创建指定的保护和网站应用到保护级别的策略来执行此操作。 
- 敏感网站： 允许仅浏览器访问权限。这样可以防止用户编辑和下载文件。
- 高度管控网站： 阻止访问从非托管设备。

请参阅本文中的"阻止或限制访问特定的 SharePoint 网站集或 OneDrive 帐户":[控件从非托管的设备的访问](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622)。 

## <a name="how-these-policies-work-together"></a>这些策略如何协同工作
务必要了解 SharePoint 网站权限通常基于业务需要对网站的访问。这些权限由网站所有者管理，可以是高度动态。使用设备访问策略可确保对这些网站，而不管是否将用户分配到 Azure AD 组保护的 SharePoint 相关联比较基准敏感，或者高度管控保护。 

下图提供了一种 SharePoint 设备访问策略如何保护对网站的访问。

![SharePoint 设备访问策略如何保护网站](../images/SharePoint-rules-scenario.png)

在此图中：
- James 被分配给与比较基准保护关联的条件的访问策略，但他可以授予对访问敏感或高度规范化保护与关联的 SharePoint 网站。 
- 如果 James 访问敏感或高度规范化网站他是使用其 PC 的成员，只要其 PC 符合授予其访问。
- 如果 James 访问敏感网站他是成员的使用其非托管的电话，允许对基线用户，则他将收到由于为此站点配置的设备访问策略敏感的网站的浏览器只读访问。 
- 如果 James 访问高度管控的网站他是使用其非托管的电话的成员，则他将被阻止由于为此站点配置的访问策略。他只能访问此网站使用他的管理和合规性 PC。


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>后续步骤
[保护 SharePoint Online 网站和文件](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
