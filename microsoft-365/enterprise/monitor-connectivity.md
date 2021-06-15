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
description: 本文将介绍可用于监视和维护连接的工具Microsoft 365技术。
ms.openlocfilehash: 8fa0820cf9b7778001be5184041e5c96930a29dd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924195"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="5a81b-103">监视 Microsoft 365 连接性</span><span class="sxs-lookup"><span data-stu-id="5a81b-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="5a81b-104">一旦部署了Microsoft 365，就可以使用Microsoft 365一些工具和技术来保持连接。</span><span class="sxs-lookup"><span data-stu-id="5a81b-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="5a81b-105">你将希望了解官方服务运行状况和连续性[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)指南，以及我们在慢速网络上Microsoft 365[服务的最佳实践](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。</span><span class="sxs-lookup"><span data-stu-id="5a81b-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="5a81b-106">你还需要获取管理[Microsoft 365，并](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)添加适用于Microsoft 365[管理员帮助的书签](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)。</span><span class="sxs-lookup"><span data-stu-id="5a81b-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="5a81b-107">监视 Microsoft 365 连接</span><span class="sxs-lookup"><span data-stu-id="5a81b-107">Monitoring Microsoft 365 Connectivity</span></span>

|<span data-ttu-id="5a81b-108">监视类型</span><span class="sxs-lookup"><span data-stu-id="5a81b-108">Type of monitoring</span></span> |<span data-ttu-id="5a81b-109">说明</span><span class="sxs-lookup"><span data-stu-id="5a81b-109">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="5a81b-110">**获取新终结点Microsoft 365通知**</span><span class="sxs-lookup"><span data-stu-id="5a81b-110">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="5a81b-111">如果要管理[Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点，那么在发布新终结点时，需要接收通知，可以使用最喜爱的 RSS 阅读器订阅我们的 RSS 源。</span><span class="sxs-lookup"><span data-stu-id="5a81b-111">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="5a81b-112">下面是如何通过[Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416)订阅，或者你可以通过电子邮件将[RSS 源更新通过电子邮件发送给你](https://go.microsoft.com/fwlink/p/?LinkId=532417)。</span><span class="sxs-lookup"><span data-stu-id="5a81b-112">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="5a81b-113">**使用System Center监视Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5a81b-113">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="5a81b-114">如果使用的是 Microsoft System Center，可以下载 System Center [Management Pack Office 365](https://www.microsoft.com/download/details.aspx?id=43708)立即开始Microsoft 365监视。</span><span class="sxs-lookup"><span data-stu-id="5a81b-114">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="5a81b-115">有关更详细的指南，请参阅管理包操作指南。</span><span class="sxs-lookup"><span data-stu-id="5a81b-115">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="5a81b-116">**监视 Azure ExpressRoute 运行状况**</span><span class="sxs-lookup"><span data-stu-id="5a81b-116">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="5a81b-117">如果要使用适用于 Microsoft 365 的 Azure ExpressRoute 连接到 Microsoft 365，需要确保同时使用 Microsoft 365 服务运行状况仪表板和 Azure 减少 Azure 资源运行状况疑难解答[时间](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="5a81b-117">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="5a81b-118">**将 Azure AD Connect Health 与 AD FS 一起使用**</span><span class="sxs-lookup"><span data-stu-id="5a81b-118">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="5a81b-119">如果你将 AD FS 用于 Single Sign-On with Microsoft 365，你将希望开始使用 Azure AD 连接 Health 来监视[AD FS 基础结构](/azure/active-directory/hybrid/how-to-connect-health-adfs)。</span><span class="sxs-lookup"><span data-stu-id="5a81b-119">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="5a81b-120">**以编程方式监视Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5a81b-120">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="5a81b-121">请参阅我们的有关 Microsoft 365[管理 API 的指南](/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="5a81b-121">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="5a81b-122">以下是可以用于返回的简短链接：[https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="5a81b-122">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5a81b-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="5a81b-123">Related topics</span></span>

[<span data-ttu-id="5a81b-124">配置 Microsoft 365 企业版 服务和应用程序</span><span class="sxs-lookup"><span data-stu-id="5a81b-124">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="5a81b-125">使组织准备好进行Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="5a81b-125">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="5a81b-126">Microsoft 365 网络计划和性能优化</span><span class="sxs-lookup"><span data-stu-id="5a81b-126">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="5a81b-127">Microsoft 365与本地环境集成</span><span class="sxs-lookup"><span data-stu-id="5a81b-127">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="5a81b-128">管理Microsoft 365终结点</span><span class="sxs-lookup"><span data-stu-id="5a81b-128">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
