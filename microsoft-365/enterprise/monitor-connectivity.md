---
title: 监视 Microsoft 365 连接性
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: 本文将介绍用于监视和维护连接的工具Microsoft 365技术。
ms.openlocfilehash: 783278ad69fbe47afd6ea85fdb70c8bb0057005c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173255"
---
# <a name="monitor-microsoft-365-connectivity"></a>监视 Microsoft 365 连接性

一旦部署了Microsoft 365，就可以使用Microsoft 365一些工具和技术来保持连接。 你将希望了解官方服务运行状况和连续性[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)指南，以及我们在慢速网络上Microsoft 365[服务的最佳实践](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。 你还需要获取管理应用[，Microsoft 365为](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)适用于Microsoft 365[管理员帮助](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)"添加书签。
  
## <a name="monitoring-microsoft-365-connectivity"></a>监视 Microsoft 365 连接

|监视类型 |说明 |
|:-----|:-----|
|**获取新终结点Microsoft 365通知** <br/> |如果要管理[Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点，那么在发布新终结点时，需要接收通知，可以使用最喜爱的 RSS 阅读器订阅我们的 RSS 源。 下面是如何通过[订阅Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416)或者[可以将 RSS 源更新通过电子邮件发送给你](https://go.microsoft.com/fwlink/p/?LinkId=532417)。  <br/> |
|**使用System Center监视Microsoft 365** <br/> |如果你使用的是 Microsoft System Center，可以下载 Microsoft System Center [Operations Manager 管理包Microsoft 365](https://www.microsoft.com/download/details.aspx?id=103379)开始监视Microsoft 365。 有关更详细的指南，请参阅管理包操作指南。 <br/> |
|**监视 Azure ExpressRoute 运行状况** <br/> |如果你使用适用于 Microsoft 365 的 Azure ExpressRoute 连接到 Microsoft 365，你会希望确保同时使用 Microsoft 365 服务运行状况仪表板和 Azure 减少 Azure 资源运行状况疑难解答[时间](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**将 Azure AD Connect Health 与 AD FS 一起使用** <br/> |如果你将 AD FS 用于单一Sign-On Microsoft 365，你将希望开始使用 Azure AD 连接 Health 来监视[AD FS 基础结构](/azure/active-directory/hybrid/how-to-connect-health-adfs)。  <br/> |
|**以编程方式监视Microsoft 365** <br/> |请参阅我们的有关 Microsoft 365[管理 API 的指南](/office/office-365-management-api/office-365-management-apis-overview)。  <br/> |

以下是可以用于返回的简短链接：[https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>相关主题

[配置 Microsoft 365 企业版 服务和应用程序](configure-services-and-applications.md)
  
[使组织准备好进行Microsoft 365 企业版](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 网络计划和性能优化](network-planning-and-performance.md)
  
[Microsoft 365与本地环境集成](microsoft-365-integration.md)
  
[管理Microsoft 365终结点](managing-office-365-endpoints.md)
