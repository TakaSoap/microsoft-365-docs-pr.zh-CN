---
title: 步骤 4. Microsoft 365 企业版租户迁移
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 为 Microsoft 365 租户迁移 Windows 设备、Office 客户端应用和 Office 服务器。
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929140"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="49f0e-104">第 4 步：</span><span class="sxs-lookup"><span data-stu-id="49f0e-104">Step 4.</span></span> <span data-ttu-id="49f0e-105">Microsoft 365 企业版租户迁移</span><span class="sxs-lookup"><span data-stu-id="49f0e-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="49f0e-106">大多数企业组织具有异类环境，其中包括操作系统、客户端软件和服务器软件的多个版本。</span><span class="sxs-lookup"><span data-stu-id="49f0e-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="49f0e-107">Microsoft 365 企业版包括最安全版本的 IT 基础结构的关键组件。</span><span class="sxs-lookup"><span data-stu-id="49f0e-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="49f0e-108">它还包括旨在利用云技术的生产力功能。</span><span class="sxs-lookup"><span data-stu-id="49f0e-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="49f0e-109">若要最大化 Microsoft 365 企业集成产品套件的业务价值，请开始规划和实施迁移这些版本的策略：</span><span class="sxs-lookup"><span data-stu-id="49f0e-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="49f0e-110">发件人</span><span class="sxs-lookup"><span data-stu-id="49f0e-110">From</span></span> | <span data-ttu-id="49f0e-111">To</span><span class="sxs-lookup"><span data-stu-id="49f0e-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="49f0e-112">Windows 7 和 Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="49f0e-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="49f0e-113">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="49f0e-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="49f0e-114">安装在工作者设备的 Office 客户端产品</span><span class="sxs-lookup"><span data-stu-id="49f0e-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="49f0e-115">适用于企业的 Microsoft 365 应用</span><span class="sxs-lookup"><span data-stu-id="49f0e-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="49f0e-116">本地服务器上安装的 Office 服务器产品</span><span class="sxs-lookup"><span data-stu-id="49f0e-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="49f0e-117">Microsoft 365 中等效的基于云的服务</span><span class="sxs-lookup"><span data-stu-id="49f0e-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="49f0e-118">迁移到 Windows 10</span><span class="sxs-lookup"><span data-stu-id="49f0e-118">Migrating to Windows 10</span></span>

<span data-ttu-id="49f0e-119">每个 Microsoft 365 企业版许可证都包括一个 Windows 10 企业版许可证。</span><span class="sxs-lookup"><span data-stu-id="49f0e-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="49f0e-120">若要迁移运行 Windows 7 或 Windows 8.1 的设备，你可以执行就地升级。</span><span class="sxs-lookup"><span data-stu-id="49f0e-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="49f0e-121">对 Windows 7 的支持已于 *2020 年 1 月 14 日结束*。</span><span class="sxs-lookup"><span data-stu-id="49f0e-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="49f0e-122">有关在就地升级之外安装 Windows 10 企业版的其他方法，请参阅 [Windows 10 部署方案](/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="49f0e-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="49f0e-123">也可以自行[计划 Windows 10 部署](/windows/deployment/planning/)。</span><span class="sxs-lookup"><span data-stu-id="49f0e-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="49f0e-124">迁移到 Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="49f0e-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="49f0e-125">Microsoft 365 企业版包括 Microsoft 365 企业应用版，它是从 Microsoft 云安装和更新的 Office 客户端产品 (Word、PowerPoint、Excel 和 Outlook) 的一个版本。</span><span class="sxs-lookup"><span data-stu-id="49f0e-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="49f0e-126">有关详细信息，请参阅关于 [Microsoft 365 企业应用版](/deployoffice/about-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="49f0e-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="49f0e-127">与其使计算机为 Office 2019 或较旧版本保持最新，不如执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="49f0e-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="49f0e-128">获取并分配用户的 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="49f0e-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="49f0e-129">卸载其计算机上的 Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="49f0e-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="49f0e-130">单独安装或 IT 推出期间安装 Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="49f0e-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="49f0e-131">有关详细信息，请参阅 [Microsoft 365 应用版部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="49f0e-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="49f0e-132">Microsoft 365 企业应用版会自动安装安全更新和新功能更新，并可以利用 Microsoft 365 中基于云的服务来增强安全性和工作效率。</span><span class="sxs-lookup"><span data-stu-id="49f0e-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="49f0e-133">将本地服务器和数据迁移到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49f0e-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="49f0e-134">Microsoft 365 企业版包括基于云的 Office 服务器服务版本，这些版本使用与 Office 服务器软件本地版本相同的一些工具，如 Web 浏览器和 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="49f0e-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="49f0e-135">这些基于云的服务会针对安全性和新功能自动更新。</span><span class="sxs-lookup"><span data-stu-id="49f0e-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="49f0e-136">迁移后，IT 部门可以节省维护和更新本地服务器所花的时间。</span><span class="sxs-lookup"><span data-stu-id="49f0e-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="49f0e-137">有关迁移特定 Microsoft 365 工作负载的用户和数据的信息，请使用以下资源：</span><span class="sxs-lookup"><span data-stu-id="49f0e-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="49f0e-138">将邮箱从内部部署Exchange Server Exchange Online</span><span class="sxs-lookup"><span data-stu-id="49f0e-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="49f0e-139">将 SharePoint 数据从 SharePoint Server 迁移到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="49f0e-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="49f0e-140">将 Skype for Business Online 迁移到 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49f0e-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="49f0e-141">转换整个组织</span><span class="sxs-lookup"><span data-stu-id="49f0e-141">Transition your entire organization</span></span>

<span data-ttu-id="49f0e-142">若要更好地了解如何将整个组织移动到 Microsoft 365 企业版中的产品和服务，请下载此转换海报：</span><span class="sxs-lookup"><span data-stu-id="49f0e-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="49f0e-143">[![显示"转换到 Microsoft 365"海报的图像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="49f0e-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="49f0e-144">通过这份两页的海报可以快速清点现有基础结构。</span><span class="sxs-lookup"><span data-stu-id="49f0e-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="49f0e-145">使用它获取有关迁移到 Microsoft 365 企业版中的产品或服务的指导。</span><span class="sxs-lookup"><span data-stu-id="49f0e-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="49f0e-146">它显示了 Windows 和 Office 产品以及其他基础结构和安全元素，如设备管理、标识和威胁防护以及信息保护和合规性。</span><span class="sxs-lookup"><span data-stu-id="49f0e-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="49f0e-147">步骤 4 的结果</span><span class="sxs-lookup"><span data-stu-id="49f0e-147">Results of Step 4</span></span>

<span data-ttu-id="49f0e-148">对于 Microsoft 365 租户的迁移，已确定：</span><span class="sxs-lookup"><span data-stu-id="49f0e-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="49f0e-149">哪些设备正在运行 Windows 7 或 Windows 8.1 以及计划将它们更新到 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="49f0e-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="49f0e-150">哪些设备正在运行 Office 客户端应用以及计划将它们更新到 Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="49f0e-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="49f0e-151">哪些本地 Office 服务器服务应迁移到其 Microsoft 365 等效服务和迁移服务及其数据的计划。</span><span class="sxs-lookup"><span data-stu-id="49f0e-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="49f0e-152">下面是一个租户示例，该租户已完成本地服务器的迁移。</span><span class="sxs-lookup"><span data-stu-id="49f0e-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![已完成本地服务器的迁移的租户示例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="49f0e-154">在此图中，组织具有：</span><span class="sxs-lookup"><span data-stu-id="49f0e-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="49f0e-155">将其本地邮箱Exchange Server迁移到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="49f0e-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="49f0e-156">将其本地 SharePoint Server 网站和数据迁移到 Microsoft 365 中的 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="49f0e-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="49f0e-157">正在进行的迁移维护</span><span class="sxs-lookup"><span data-stu-id="49f0e-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="49f0e-158">您可能需要持续：</span><span class="sxs-lookup"><span data-stu-id="49f0e-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="49f0e-159">根据 Exchange 邮箱迁移的状态，继续向组织推出到 Exchange Online 的转换。</span><span class="sxs-lookup"><span data-stu-id="49f0e-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="49f0e-160">根据本地 SharePoint 网站迁移的状态，继续将迁移到 Microsoft 365 中的 SharePoint 迁移到组织。</span><span class="sxs-lookup"><span data-stu-id="49f0e-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="49f0e-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="49f0e-161">Next step</span></span>

<span data-ttu-id="49f0e-162">[![步骤 5.部署设备和应用管理](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="49f0e-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="49f0e-163">继续执行 [设备和应用管理，](tenant-management-device-management.md) 以部署设备和应用管理。</span><span class="sxs-lookup"><span data-stu-id="49f0e-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>