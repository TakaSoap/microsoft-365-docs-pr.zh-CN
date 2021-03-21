---
title: 监视 Microsoft 365 连接性
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: 本文将介绍可用于监视和维护 Microsoft 365 连接的工具和技术。
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920772"
---
# <a name="monitor-microsoft-365-connectivity"></a>监视 Microsoft 365 连接性

部署 Microsoft 365 后，可以使用下面的一些工具和技术维护 Microsoft 365 连接。 你将希望了解官方服务运行状况和连续性[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)指南，以及我们在慢速网络上使用 Microsoft [365 的最佳实践](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。 你还需要获取 [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) 管理应用，为 Microsoft [365](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)商业版添加书签 - 管理员帮助 。
  
## <a name="monitoring-microsoft-365-connectivity"></a>监视 Microsoft 365 连接

|||
|:-----|:-----|
|**获取新 Microsoft 365 终结点的通知** <br/> |如果你正在管理 [Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点，你将希望在我们发布新终结点时收到通知，可以使用你最喜爱的 RSS 阅读器订阅我们的 RSS 源。 下面是如何通过 [Outlook 订阅](https://go.microsoft.com/fwlink/p/?LinkId=532416) 的，或者 [你可以通过电子邮件将 RSS 源更新通过电子邮件发送给你](https://go.microsoft.com/fwlink/p/?LinkId=532417)。  <br/> |
|**使用 System Center 监视 Microsoft 365** <br/> |如果使用的是 Microsoft System Center，可以下载适用于 [Office 365](https://www.microsoft.com/download/details.aspx?id=43708) 的 System Center 管理包，立即开始监视 Microsoft 365。 有关更详细的指导，请参阅管理包操作指南或此博客文章 [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**监视 Azure ExpressRoute 运行状况** <br/> |如果使用适用于 Microsoft 365 的 Azure ExpressRoute 连接到 Microsoft 365，需要确保同时使用 Microsoft 365 服务运行状况仪表板和 Azure 减少 Azure 资源运行状况疑难解答 [时间](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**将 Azure AD Connect Health 与 AD FS 一起使用** <br/> |如果你将 AD FS 用于 Microsoft 365 Sign-On，你将希望开始使用 Azure AD Connect Health 监视 [AD FS 基础结构](/azure/active-directory/hybrid/how-to-connect-health-adfs)。  <br/> |
|**以编程方式监视 Microsoft 365** <br/> |请参阅 Microsoft [365](/office/office-365-management-api/office-365-management-apis-overview)管理 API 指南。  <br/> |

以下是可以用于返回的简短链接：[https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>相关主题

[配置 Microsoft 365 企业版服务和应用程序](configure-services-and-applications.md)
  
[让组织为 Microsoft 365 企业版做好准备](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 网络计划和性能优化](network-planning-and-performance.md)
  
[Microsoft 365 与本地环境的集成](microsoft-365-integration.md)
  
[管理 Microsoft 365 终结点](managing-office-365-endpoints.md)