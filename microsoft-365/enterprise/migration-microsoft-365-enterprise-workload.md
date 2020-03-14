---
title: 迁移到 Microsoft 365 企业版
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 逐步完成将 Microsoft Office、Office 服务器和 Windows 的版本迁移到组织中的 Microsoft 365 企业版的过程。
ms.openlocfilehash: 06cacbb45a98bb62f53866b0d2ab7ba393e609a0
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633240"
---
# <a name="migration-to-microsoft-365-enterprise"></a><span data-ttu-id="c4928-103">迁移到 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="c4928-103">Migration to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c4928-p101">大多数企业组织拥有带有多种版本的操作系统、客户端软件和服务器软件的异类环境。Microsoft 365 企业版包含这些 IT 基础结构的关键组件的最安全版本，其中生产功能利用云技术设计。</span><span class="sxs-lookup"><span data-stu-id="c4928-p101">Most enterprise organizations have a heterogeneous environment with multiple releases of operating systems, client software, and server software. Microsoft 365 Enterprise includes the most secure versions of these key components of your IT infrastructure with productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="c4928-106">要最大限度提高集成了产品套件的 Microsoft 365 企业版的业务价值，请开始规划并实施迁移以下版本的策略：</span><span class="sxs-lookup"><span data-stu-id="c4928-106">To maximize the business value of the Microsoft 365 Enterprise integrated suite of products, begin planning and implementing a strategy to migrate releases of:</span></span>

- <span data-ttu-id="c4928-107">安装在计算机上的 Office 客户端迁移到 Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="c4928-107">The Office client installed on your computers to Office 365 ProPlus</span></span>
- <span data-ttu-id="c4928-108">安装在服务器上的 Office 服务器迁移到 Office 365 中的等效服务中</span><span class="sxs-lookup"><span data-stu-id="c4928-108">Office servers installed on your servers to their equivalent services in Office 365</span></span>
- <span data-ttu-id="c4928-109">设备上 Windows 7 和 Windows 8.1 迁移到 Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="c4928-109">Windows 7 and Windows 8.1 on your devices to Windows 10 Enterprise</span></span>

>[!Note]
><span data-ttu-id="c4928-110">将于 **2020 年 1 月 14 日**结束对 Windows 7 的支持。</span><span class="sxs-lookup"><span data-stu-id="c4928-110">Windows 7 reaches end of support on **January 14, 2020**.</span></span> <span data-ttu-id="c4928-111">有关详细信息，请单击[此处](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。</span><span class="sxs-lookup"><span data-stu-id="c4928-111">For more information, click [here](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).</span></span>
>

<span data-ttu-id="c4928-112">随着时间的推移，完成所有这些迁移使你的组织更接近[新式工作区](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)，这是一种安全且集成的环境，可释放组织中的团队合作精神和创造力，所有这些都由 Microsoft 365 企业版启用和授权。</span><span class="sxs-lookup"><span data-stu-id="c4928-112">Accomplishing all of these migrations over time gets your organization closer to the [modern workplace](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), a secure and integrated environment that unlocks teamwork and creativity in your organization, all of which is enabled and empowered by Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="c4928-113">有关迁移特定 Office 365 工作负载的用户和数据的信息：</span><span class="sxs-lookup"><span data-stu-id="c4928-113">For information about migrating users and data for specific Office 365 workloads:</span></span>

- <span data-ttu-id="c4928-114">从 Exchange Server 到 Exchange Online 的用户邮箱，请参阅 [Exchange Online 工作负载](exchangeonline-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="c4928-114">User mailboxes from Exchange Server to Exchange Online, see the [Exchange Online workload](exchangeonline-workload.md).</span></span>
- <span data-ttu-id="c4928-115">从 SharePoint Server 到 SharePoint Online 的 SharePoint 数据，请参阅 [SharePoint Online 工作负载](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="c4928-115">SharePoint data from SharePoint Server to SharePoint Online, see the [SharePoint Online workload](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="c4928-116">Microsoft Teams 的 Skype for Business，请参阅 [Microsoft Teams 工作负载](teams-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="c4928-116">Skype for Business Online to Microsoft Teams, see the [Microsoft Teams workload](teams-workload.md).</span></span>

## <a name="migration-for-microsoft-office-client-products"></a><span data-ttu-id="c4928-117">Microsoft Office 客户端产品迁移</span><span class="sxs-lookup"><span data-stu-id="c4928-117">Migration for Microsoft Office client products</span></span>

<span data-ttu-id="c4928-p103">在许多大小组织中，你可能都会使用旧版 Office 客户端产品（如 Word、Excel 和 PowerPoint）的组合。这些旧版本：</span><span class="sxs-lookup"><span data-stu-id="c4928-p103">In many organizations both large and small, you might be using a combination of older versions of the Office client products, such as Word, Excel, and PowerPoint. These older versions:</span></span>

- <span data-ttu-id="c4928-120">可以使用最新的安全更新和支持修补程序[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，但该过程有时是手动的，可能无法在整个组织内缩放。</span><span class="sxs-lookup"><span data-stu-id="c4928-120">Can be [updated](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) with the latest security updates and support fixes, but the process is sometimes manual and might not scale across your organization.</span></span>
- <span data-ttu-id="c4928-121">未能最佳利用 Microsoft 云技术并帮助你数字化转换业务。</span><span class="sxs-lookup"><span data-stu-id="c4928-121">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="c4928-122">不包含新功能。</span><span class="sxs-lookup"><span data-stu-id="c4928-122">Do not contain new features.</span></span>
 
<span data-ttu-id="c4928-123">Microsoft 365 企业版包含 Office 365 专业增强版，这是 Office 客户端产品的一个版本，可与 Microsoft 365 企业版许可证一起使用，并从 Microsoft 云安装和更新。</span><span class="sxs-lookup"><span data-stu-id="c4928-123">Microsoft 365 Enterprise includes Office 365 ProPlus, a version of the Office client products that is available with a Microsoft 365 Enterprise license and is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="c4928-124">Office 365 专业增强版包括安全更新和最新功能。</span><span class="sxs-lookup"><span data-stu-id="c4928-124">Office 365 ProPlus includes security updates and the latest features.</span></span> <span data-ttu-id="c4928-125">有关详细信息，请参阅[关于企业中的 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="c4928-125">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

### <a name="office-2007"></a><span data-ttu-id="c4928-126">Office 2007</span><span class="sxs-lookup"><span data-stu-id="c4928-126">Office 2007</span></span>

<span data-ttu-id="c4928-p105">对于 Office 2007 版本中的 Office 版本，停止提供支持时间已过。有关详细信息，请参阅 [Office 2007 停止提供支持路线图](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="c4928-p105">For versions of Office in the Office 2007 release, the end of support has already passed. See [Office 2007 End of Support Roadmap](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap) for more information.</span></span>

<span data-ttu-id="c4928-129">与其通过 Office 2010、Office 2013 或 Office 2016 升级运行 Office 2007 的计算机，不如考虑：</span><span class="sxs-lookup"><span data-stu-id="c4928-129">Rather than upgrading your computers running Office 2007 with Office 2010, Office 2013, or Office 2016, consider:</span></span>

1. <span data-ttu-id="c4928-130">为用户获取并分配 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="c4928-130">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="c4928-131">卸载其计算机中的 Office 2007。</span><span class="sxs-lookup"><span data-stu-id="c4928-131">Uninstalling Office 2007 on their computers.</span></span>
3. <span data-ttu-id="c4928-p106">单独安装 Office 365 专业增强版或在 IT 部署时安装 Office 365 专业增强版。有关详细信息，请参阅[阶段4：Office 365 专业增强版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="c4928-p106">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="c4928-134">Office 365 专业增强版会自动安装更新，并可利用 Office 365 中基于云的服务来提高安全性和生产效率。</span><span class="sxs-lookup"><span data-stu-id="c4928-134">Office 365 ProPlus installs updates automatically and can take advantage of cloud-based services in Office 365 for enhanced security and productivity.</span></span>

### <a name="office-2010"></a><span data-ttu-id="c4928-135">Office 2010</span><span class="sxs-lookup"><span data-stu-id="c4928-135">Office 2010</span></span>

<span data-ttu-id="c4928-136">对于 Office 2010 版本中的 Office 版本，将于 **2020 年 10 月 13 日**停止提供支持。</span><span class="sxs-lookup"><span data-stu-id="c4928-136">For versions of Office in the Office 2010 release, the end of support is **October 13, 2020**.</span></span> <span data-ttu-id="c4928-137">有关详细信息，请参阅 [Office 2010 的停止提供支持路线图](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="c4928-137">For more information, see [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).</span></span>

<span data-ttu-id="c4928-138">与其通过 Office 2013 或 Office 2016 升级运行 Office 2010 的计算机（两种方式均必须手动更新），不如考虑：</span><span class="sxs-lookup"><span data-stu-id="c4928-138">Rather than upgrading your computers running Office 2010 with Office 2013 or Office 2016, both of which must be manually updated, consider:</span></span> 

1. <span data-ttu-id="c4928-139">为用户获取并分配 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="c4928-139">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="c4928-140">卸载其计算机中的 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="c4928-140">Uninstalling Office 2010 on their computers.</span></span>
3. <span data-ttu-id="c4928-p108">单独安装 Office 365 专业增强版或在 IT 部署时安装 Office 365 专业增强版。有关详细信息，请参阅[阶段4：Office 365 专业增强版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="c4928-p108">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="c4928-143">Office 365 专业增强版会自动安装安全更新和新功能更新，并可利用 Microsoft 365 中基于云的服务来提高安全性和生产效率。</span><span class="sxs-lookup"><span data-stu-id="c4928-143">Office 365 ProPlus installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

### <a name="office-2013-and-office-2016"></a><span data-ttu-id="c4928-144">Office 2013 和 Office 2016</span><span class="sxs-lookup"><span data-stu-id="c4928-144">Office 2013 and Office 2016</span></span>

<span data-ttu-id="c4928-145">尚未确定针对 Office 的 Office 2013 和 Office 2016 版本的支持终止路线图。</span><span class="sxs-lookup"><span data-stu-id="c4928-145">The end of support roadmap for the Office 2013 and Office 2016 versions of Office has not yet been determined.</span></span> <span data-ttu-id="c4928-146">但是，与 Office 2010 一样，仍然必须[安装安全更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)这些更新可能没法很好地缩放，具体取决于组织的规模。</span><span class="sxs-lookup"><span data-stu-id="c4928-146">However, like Office 2010, you must still [install security updates](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), which might not scale well depending on the size of your organization.</span></span>

<span data-ttu-id="c4928-147">与其使用 Office 2013 或 Office 2016 最新安全更新保证计算机处于最新状态或者将计算机从 Office 2013 更新到 Office 2016，请考虑执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c4928-147">Rather than keep updating your computers with the latest security updates for Office 2013 or Office 2016 or update your computers from Office 2013 to Office 2016, consider:</span></span>

1. <span data-ttu-id="c4928-148">为用户获取并分配 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="c4928-148">Obtaining and assigning a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="c4928-149">卸载其计算机中的 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="c4928-149">Uninstalling Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="c4928-p110">单独安装 Office 365 专业增强版或在 IT 部署时安装 Office 365 专业增强版。有关详细信息，请参阅[阶段4：Office 365 专业增强版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="c4928-p110">Installing Office 365 ProPlus, either individually or in conjunction with an IT rollout. For more information, see [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md).</span></span>

<span data-ttu-id="c4928-152">Office 365 专业增强版会自动安装安全更新和新功能更新，并可利用 Microsoft 365 中基于云的服务来提高安全性和生产效率。</span><span class="sxs-lookup"><span data-stu-id="c4928-152">Office 365 ProPlus installs both security and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migration-for-microsoft-office-server-products"></a><span data-ttu-id="c4928-153">Microsoft Office 服务器产品迁移</span><span class="sxs-lookup"><span data-stu-id="c4928-153">Migration for Microsoft Office server products</span></span>

<span data-ttu-id="c4928-p111">在许多大小组织中，你可能都会使用旧版 Office 服务器产品（如 Exchange Server 和 SharePoint Server）的组合。这些旧版本：</span><span class="sxs-lookup"><span data-stu-id="c4928-p111">In many organizations both large and small, you might be using a combination of older versions of the Office Server products, such as Exchange Server and SharePoint Server. These older versions:</span></span>

- <span data-ttu-id="c4928-p112">应该更新最新的安全更新并支持修补程序。在某些情况下，这些更新每月发布一次。</span><span class="sxs-lookup"><span data-stu-id="c4928-p112">Should be updated with the latest security updates and support fixes. In some cases, these updates are released monthly.</span></span>
- <span data-ttu-id="c4928-158">未能最佳利用 Microsoft 云技术并帮助你数字化转换业务。</span><span class="sxs-lookup"><span data-stu-id="c4928-158">Are not optimally enabled to leverage Microsoft’s cloud technologies and help you digitally transform your business.</span></span>
- <span data-ttu-id="c4928-159">请勿包含新的生产应用程序，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="c4928-159">Do not include new productivity applications, such as Microsoft Teams.</span></span>
- <span data-ttu-id="c4928-160">请勿包含最新的安全功能，例如 Exchange 高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="c4928-160">Do not include the latest security features, such as Exchange Advanced Threat Protection.</span></span>

<span data-ttu-id="c4928-161">Microsoft 365 企业版包含 Office 365，后者包含 Office 服务基于云的版本，这些版本使用 Web 浏览器和 Outlook 客户端等与 Office 服务器软件本地版本相同的工具。</span><span class="sxs-lookup"><span data-stu-id="c4928-161">Microsoft 365 Enterprise includes Office 365, which includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="c4928-162">这些服务持续更新来保障安全性，但无需 IT 操作，从而节省维护和更新本地服务器所耗的时间。</span><span class="sxs-lookup"><span data-stu-id="c4928-162">These services are continually updated for security without involving IT, saving you the time it takes to maintain and update on-premises servers.</span></span> <span data-ttu-id="c4928-163">这些服务还包含 Office 服务器软件中当前未提供的新功能增强版。</span><span class="sxs-lookup"><span data-stu-id="c4928-163">These services also have new features enhancements that are not present in Office server software.</span></span> 

### <a name="office-server-2007"></a><span data-ttu-id="c4928-164">Office Server 2007</span><span class="sxs-lookup"><span data-stu-id="c4928-164">Office Server 2007</span></span>

<span data-ttu-id="c4928-p114">对于 Office 2007 版本中的服务器产品，停止提供支持时间已过。有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="c4928-p114">For server products in the Office 2007 release, the end of support has already passed. See these articles for the details:</span></span>

- [<span data-ttu-id="c4928-167">Exchange 2007 停止提供支持路线图</span><span class="sxs-lookup"><span data-stu-id="c4928-167">Exchange 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [<span data-ttu-id="c4928-168">SharePoint Server 2007 停止提供支持路线图</span><span class="sxs-lookup"><span data-stu-id="c4928-168">SharePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [<span data-ttu-id="c4928-169">Project Server 2007 停止提供支持路线图</span><span class="sxs-lookup"><span data-stu-id="c4928-169">Project Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [<span data-ttu-id="c4928-170">Office Communications Server 停止提供支持路线图</span><span class="sxs-lookup"><span data-stu-id="c4928-170">Office Communications Server end of support roadmap</span></span>](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [<span data-ttu-id="c4928-171">PerformancePoint Server 2007 停止提供支持路线图</span><span class="sxs-lookup"><span data-stu-id="c4928-171">PerformancePoint Server 2007 end of support roadmap</span></span>](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

<span data-ttu-id="c4928-172">与其通过 Office 2010、Office 2013 或 Office 2016 版本中的服务器产品升级 Office 2007 版本中的服务器产品，不如考虑：</span><span class="sxs-lookup"><span data-stu-id="c4928-172">Rather than upgrading your server products in the Office 2007 release with server products in the Office 2010, Office 2013, or Office 2016 releases, consider:</span></span>

1. <span data-ttu-id="c4928-p115">将 Office 2007 服务器上的数据迁移到 Office 365。为顺利完成此操作，请聘用 Microsoft 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c4928-p115">Migrating the data on your Office 2007 servers to Office 365. To help with this, hire a Microsoft partner.</span></span>
2. <span data-ttu-id="c4928-175">向用户推出新功能和工作流程。</span><span class="sxs-lookup"><span data-stu-id="c4928-175">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="c4928-176">如果不再需要运行 Office 2007 服务器产品的本地服务器，请将其停用。</span><span class="sxs-lookup"><span data-stu-id="c4928-176">When there is no longer a need for the on-premises servers running Office 2007 server products, decommissioning them.</span></span>

### <a name="office-server-2010"></a><span data-ttu-id="c4928-177">Office Server 2010</span><span class="sxs-lookup"><span data-stu-id="c4928-177">Office Server 2010</span></span>

<span data-ttu-id="c4928-178">对于 Office 2010 版本中的服务器产品，将于 **2020 年 10 月 13 日**终止对下述内容的支持：</span><span class="sxs-lookup"><span data-stu-id="c4928-178">For server products in the Office 2010 release, the end of support is **October 13, 2020** for the following:</span></span>

- [<span data-ttu-id="c4928-179">Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="c4928-179">Exchange Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support)
- [<span data-ttu-id="c4928-180">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="c4928-180">SharePoint Server 2010</span></span>](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010)

<span data-ttu-id="c4928-181">与其通过 Office 2013 或 Office 2016 版本中的服务器产品升级 Office 2010 版本中的服务器产品，不如考虑：</span><span class="sxs-lookup"><span data-stu-id="c4928-181">Rather than upgrading these server products in the Office 2010 release with server products in the Office 2013 or Office 2016 release, consider:</span></span>

1. <span data-ttu-id="c4928-182">将 Office 2010 服务器上的数据迁移到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c4928-182">Migrating the data on your Office 2010 servers to Microsoft 365.</span></span> <span data-ttu-id="c4928-183">有关此方面的帮助，请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c4928-183">To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="c4928-184">向用户推出新功能和工作流程。</span><span class="sxs-lookup"><span data-stu-id="c4928-184">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="c4928-185">如果不再需要运行 Office 2010 服务器产品的本地服务器，请将其停用。</span><span class="sxs-lookup"><span data-stu-id="c4928-185">When there is no longer a need for the on-premises servers running Office 2010 server products, decommissioning them.</span></span>

### <a name="office-server-2013"></a><span data-ttu-id="c4928-186">Office Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4928-186">Office Server 2013</span></span>

<span data-ttu-id="c4928-p117">对于 Office 2013 版本中的服务器产品，停止提供支持的时间尚未确定。与其通过 Office 2016 版本中的服务器产品升级 Office 2013 版本中的服务器产品，不如考虑：</span><span class="sxs-lookup"><span data-stu-id="c4928-p117">For server products in the Office 2013 release, the end of support has not been determined. Rather than upgrading your server products in the Office 2013 release with server products in the Office 2016 release, consider:</span></span>

1. <span data-ttu-id="c4928-p118">将 Office 2013 服务器上的数据迁移到 Office 365。为顺利完成此操作，请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或聘用 Microsoft 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c4928-p118">Migrating the data on your Office 2013 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="c4928-191">向用户推出新功能和工作流程。</span><span class="sxs-lookup"><span data-stu-id="c4928-191">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="c4928-192">如果不再需要运行 Office 2013 服务器产品的本地服务器，请将其停用。</span><span class="sxs-lookup"><span data-stu-id="c4928-192">When there is no longer a need for the on-premises servers running Office 2013 server products, decommissioning them.</span></span>

### <a name="office-server-2016"></a><span data-ttu-id="c4928-193">Office Server 2016</span><span class="sxs-lookup"><span data-stu-id="c4928-193">Office Server 2016</span></span>

<span data-ttu-id="c4928-p119">对于 Office 2016 版本中的服务器产品，停止提供支持的时间尚未确定。要利用基于云的服务和增强功能对业务进行数字化转型，请考虑：</span><span class="sxs-lookup"><span data-stu-id="c4928-p119">For server products in the Office 2016 release, the end of support has not been determined. To take advantage of the cloud-based service and enhancements to digitally transform your business, consider:</span></span>

1. <span data-ttu-id="c4928-p120">将 Office 2016 服务器上的数据迁移到 Office 365。为顺利完成此操作，请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或聘用 Microsoft 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c4928-p120">Migrating the data on your Office 2016 servers to Office 365. To help with this, see [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) or hire a Microsoft partner.</span></span>
2. <span data-ttu-id="c4928-198">向用户推出新功能和工作流程。</span><span class="sxs-lookup"><span data-stu-id="c4928-198">Rolling out the new functionality and work processes to your users.</span></span>
3. <span data-ttu-id="c4928-199">如果不再需要运行 Office 2016 服务器产品的本地服务器，请将其停用。</span><span class="sxs-lookup"><span data-stu-id="c4928-199">When there is no longer a need for the on-premises servers running Office 2016 server products, decommissioning them.</span></span>

## <a name="migration-for-microsoft-windows-7-and-81"></a><span data-ttu-id="c4928-200">Microsoft Windows 7 和 8.1 迁移</span><span class="sxs-lookup"><span data-stu-id="c4928-200">Migration for Microsoft Windows 7 and 8.1</span></span>

<span data-ttu-id="c4928-201">将于 **2020 年 1 月 14 日**结束对 Windows 7 的支持。</span><span class="sxs-lookup"><span data-stu-id="c4928-201">Windows 7 reaches end of support on **January 14, 2020**.</span></span> <span data-ttu-id="c4928-202">要迁移运行 Windows 7 或 Windows 8.1 的设备，可以执行[就地升级](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)。</span><span class="sxs-lookup"><span data-stu-id="c4928-202">To migrate your devices running Windows 7 or Windows 8.1, you can perform an [in-place upgrade](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade).</span></span> 

<span data-ttu-id="c4928-203">有关其他方法，请参阅 [Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="c4928-203">For additional methods, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="c4928-204">也可以自行[计划 Windows 10 部署](https://aka.ms/planforwin10deployment)。</span><span class="sxs-lookup"><span data-stu-id="c4928-204">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a><span data-ttu-id="c4928-205">Office 2010 客户端和服务器及 Windows 7 的选项摘要</span><span class="sxs-lookup"><span data-stu-id="c4928-205">Summary of options for Office 2010 clients and servers and Windows 7</span></span>

<span data-ttu-id="c4928-206">有关这些产品的升级、迁移和移动到云选项的直观摘要，请参阅[停止提供支持海报](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c4928-206">For a visual summary of the upgrade, migrate, and move-to-the-cloud options for these products, see the [end of support poster](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf).</span></span>

<span data-ttu-id="c4928-207">[![终止对 Office 2010 客户端和服务器及 Windows 7 的支持海报图像](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span><span class="sxs-lookup"><span data-stu-id="c4928-207">[![Image for the end of support for Office 2010 clients and servers and Windows 7 poster](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)</span></span>

<span data-ttu-id="c4928-208">此海报包含一页内容，可借助它快速了解用于避免 Office 2010 客户端和服务器产品及 Windows 7 支持终止的各种方式，突出显示了 Microsoft 365 企业版中的首选方式及产生的目标支持。</span><span class="sxs-lookup"><span data-stu-id="c4928-208">This one-page poster is a quick way to understand the various paths you can take to prevent Office 2010 client and server products and Windows 7 from reaching end of support, with preferred paths and resulting destination support in Microsoft 365 Enterprise highlighted.</span></span>

<span data-ttu-id="c4928-209">可以[下载此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)并按 letter、legal 或 tabloid (11 x 17) 格式打印。</span><span class="sxs-lookup"><span data-stu-id="c4928-209">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c4928-210">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="c4928-210">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c4928-211">了解 Microsoft 的 IT 专家如何使用以下这些资源将公司迁移到 Microsoft 365 企业版：</span><span class="sxs-lookup"><span data-stu-id="c4928-211">See how IT experts at Microsoft migrated the company to Microsoft 365 Enterprise with these resources:</span></span> 

- [<span data-ttu-id="c4928-212">部署和更新 Microsoft Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="c4928-212">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [<span data-ttu-id="c4928-213">Microsoft 将 150,000 个邮箱迁移到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c4928-213">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="c4928-214">将 SharePoint 迁移到云：了解 Microsoft 如何运行自己的迁移</span><span class="sxs-lookup"><span data-stu-id="c4928-214">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [<span data-ttu-id="c4928-215">在 Microsoft 中将 Windows 10 部署为就地升级</span><span class="sxs-lookup"><span data-stu-id="c4928-215">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- <span data-ttu-id="c4928-216">[Windows 10 部署：来自 Microsoft IT 部门的提示和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)（视频）</span><span class="sxs-lookup"><span data-stu-id="c4928-216">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>

## <a name="transition-your-entire-organization"></a><span data-ttu-id="c4928-217">转换整个组织</span><span class="sxs-lookup"><span data-stu-id="c4928-217">Transition your entire organization</span></span>

<span data-ttu-id="c4928-218">要更好地了解如何将整个组织转移到 Microsoft 365 企业版中的产品和服务，请下载[转换海报](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c4928-218">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 Enterprise, download the [transition poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf).</span></span>

<span data-ttu-id="c4928-219">[![转移到 Microsoft 365 海报图像](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="c4928-219">[![Image for the Transition to Microsoft 365 poster](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="c4928-220">此海报包含两页内容，可借助它快速盘点现有基础结构并获取有关转移到 Microsoft 365 企业版中相应产品或服务的指南。</span><span class="sxs-lookup"><span data-stu-id="c4928-220">This two-page poster is a quick way to inventory your existing infrastructure and get to the guidance for moving to the corresponding product or service in Microsoft 365 Enterprise.</span></span> <span data-ttu-id="c4928-221">它包含 Windows 和 Office 产品，还涵盖了设备管理、标识及信息和威胁防护等其他基础结构和安全元素。</span><span class="sxs-lookup"><span data-stu-id="c4928-221">It includes Windows and Office products and other infrastructure and security elements such as device management, identity, and information and threat protection.</span></span>

<span data-ttu-id="c4928-222">可以[下载此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)并按 letter、legal 或 tabloid (11 x 17) 格式打印。</span><span class="sxs-lookup"><span data-stu-id="c4928-222">You can [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="result"></a><span data-ttu-id="c4928-223">结果</span><span class="sxs-lookup"><span data-stu-id="c4928-223">Result</span></span>

<span data-ttu-id="c4928-224">你的组织已将 Microsoft Office、Office 服务器和 Windows 的早期版本迁移到 Microsoft 365 企业版。</span><span class="sxs-lookup"><span data-stu-id="c4928-224">Your organization has migrated older versions of Microsoft Office, Office servers, and Windows to Microsoft 365 Enterprise.</span></span>
