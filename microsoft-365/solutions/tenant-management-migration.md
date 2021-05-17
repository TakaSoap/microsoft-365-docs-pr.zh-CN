---
title: 步骤 4. 企业租户Microsoft 365迁移
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
description: 为Windows租户迁移 Windows 设备、Office客户端应用Office服务器Microsoft 365服务器。
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929140"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="5eb40-104">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="5eb40-104">Step 4.</span></span> <span data-ttu-id="5eb40-105">企业租户Microsoft 365迁移</span><span class="sxs-lookup"><span data-stu-id="5eb40-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="5eb40-106">大多数企业组织具有异类环境，其中包括操作系统、客户端软件和服务器软件的多个版本。</span><span class="sxs-lookup"><span data-stu-id="5eb40-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="5eb40-107">Microsoft 365企业版包括 IT 基础结构的关键组件的最安全版本。</span><span class="sxs-lookup"><span data-stu-id="5eb40-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="5eb40-108">它还包括旨在利用云技术的生产力功能。</span><span class="sxs-lookup"><span data-stu-id="5eb40-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="5eb40-109">若要最大程度地提高企业集成套件Microsoft 365业务价值，请开始规划和实施迁移这些版本的策略：</span><span class="sxs-lookup"><span data-stu-id="5eb40-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="5eb40-110">发件人</span><span class="sxs-lookup"><span data-stu-id="5eb40-110">From</span></span> | <span data-ttu-id="5eb40-111">到</span><span class="sxs-lookup"><span data-stu-id="5eb40-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="5eb40-112">Windows 7 和 Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5eb40-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="5eb40-113">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="5eb40-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="5eb40-114">Office工作人员设备上安装的客户端产品</span><span class="sxs-lookup"><span data-stu-id="5eb40-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="5eb40-115">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="5eb40-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="5eb40-116">Office本地服务器上安装的服务器产品</span><span class="sxs-lookup"><span data-stu-id="5eb40-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="5eb40-117">它们相同的基于云的服务Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5eb40-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="5eb40-118">迁移到Windows 10</span><span class="sxs-lookup"><span data-stu-id="5eb40-118">Migrating to Windows 10</span></span>

<span data-ttu-id="5eb40-119">企业Microsoft 365的每个许可证都包括一个Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="5eb40-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="5eb40-120">若要迁移运行 Windows 7 或 Windows 8.1的设备，可以执行就地升级。</span><span class="sxs-lookup"><span data-stu-id="5eb40-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="5eb40-121">*2020* 年 1 Windows 7 日停止支持。</span><span class="sxs-lookup"><span data-stu-id="5eb40-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="5eb40-122">有关在就地升级Windows 10 企业版其他安装方法，请参阅Windows 10[部署方案](/windows/deployment/windows-10-deployment-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="5eb40-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="5eb40-123">也可以自行[计划 Windows 10 部署](/windows/deployment/planning/)。</span><span class="sxs-lookup"><span data-stu-id="5eb40-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="5eb40-124">迁移到Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="5eb40-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="5eb40-125">Microsoft 365企业版包括 Microsoft 365 企业应用版，它是从 Microsoft 云安装和更新的 Office 客户端产品 (Word、PowerPoint、Excel 和 Outlook) 的一个版本。</span><span class="sxs-lookup"><span data-stu-id="5eb40-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="5eb40-126">有关详细信息，请参阅关于[Microsoft 365 企业应用版。](/deployoffice/about-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="5eb40-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="5eb40-127">不要使计算机在 Office 2019 或较旧版本中保持最新，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5eb40-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="5eb40-128">获取并分配Microsoft 365许可证。</span><span class="sxs-lookup"><span data-stu-id="5eb40-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="5eb40-129">卸载Office 2013 或 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="5eb40-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="5eb40-130">单独Microsoft 365 企业应用版 IT 部署期间安装客户端。</span><span class="sxs-lookup"><span data-stu-id="5eb40-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="5eb40-131">有关详细信息，请参阅 [Microsoft 365 应用版部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="5eb40-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="5eb40-132">Microsoft 365 企业应用版可自动安装安全更新和新功能更新，并可以利用 Microsoft 365 中的基于云的服务，从而增强安全性和工作效率。</span><span class="sxs-lookup"><span data-stu-id="5eb40-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="5eb40-133">将本地服务器和数据迁移到Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5eb40-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="5eb40-134">Microsoft 365 企业版包括基于云的 Office 服务器服务版本，这些服务使用与本地版本的 Office 服务器软件（如 Web 浏览器和 Outlook 客户端）相同的工具。</span><span class="sxs-lookup"><span data-stu-id="5eb40-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="5eb40-135">这些基于云的服务会针对安全性和新功能自动更新。</span><span class="sxs-lookup"><span data-stu-id="5eb40-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="5eb40-136">迁移后，IT 部门可以节省维护和更新本地服务器所花的时间。</span><span class="sxs-lookup"><span data-stu-id="5eb40-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="5eb40-137">使用以下资源获取有关迁移特定应用程序工作负载的用户Microsoft 365数据：</span><span class="sxs-lookup"><span data-stu-id="5eb40-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="5eb40-138">将邮箱从本地Exchange Server移动到Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5eb40-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="5eb40-139">将SharePoint数据从 SharePoint Server 迁移到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5eb40-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="5eb40-140">将 Skype for Business Online 迁移到 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5eb40-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="5eb40-141">转换整个组织</span><span class="sxs-lookup"><span data-stu-id="5eb40-141">Transition your entire organization</span></span>

<span data-ttu-id="5eb40-142">若要更好地了解如何将整个组织移动到 Microsoft 365 企业版中的产品和服务，请下载此转换海报：</span><span class="sxs-lookup"><span data-stu-id="5eb40-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="5eb40-143">[![显示"转换到Microsoft 365海报的图像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="5eb40-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="5eb40-144">通过这份两页的海报可以快速清点现有基础结构。</span><span class="sxs-lookup"><span data-stu-id="5eb40-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="5eb40-145">使用它获取有关移动到适用于企业的 Microsoft 365 的指南。</span><span class="sxs-lookup"><span data-stu-id="5eb40-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="5eb40-146">它显示了Windows和Office以及其他基础结构和安全元素，如设备管理、标识和威胁防护以及信息保护和合规性。</span><span class="sxs-lookup"><span data-stu-id="5eb40-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="5eb40-147">步骤 4 的结果</span><span class="sxs-lookup"><span data-stu-id="5eb40-147">Results of Step 4</span></span>

<span data-ttu-id="5eb40-148">对于迁移租户Microsoft 365，已确定：</span><span class="sxs-lookup"><span data-stu-id="5eb40-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="5eb40-149">哪些设备在 Windows 7 或 Windows 8.1 以及计划将其更新为 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="5eb40-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="5eb40-150">哪些设备在运行 Office 客户端应用以及计划将它们更新为Microsoft 365企业应用。</span><span class="sxs-lookup"><span data-stu-id="5eb40-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="5eb40-151">哪些本地Office服务器服务应迁移到其Microsoft 365迁移服务及其数据的计划。</span><span class="sxs-lookup"><span data-stu-id="5eb40-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="5eb40-152">下面是一个租户示例，该租户已完成本地服务器的迁移。</span><span class="sxs-lookup"><span data-stu-id="5eb40-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![已完成本地服务器的迁移的租户示例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="5eb40-154">在此图中，组织具有：</span><span class="sxs-lookup"><span data-stu-id="5eb40-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="5eb40-155">将其本地邮箱Exchange Server到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5eb40-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="5eb40-156">将其本地服务器SharePoint服务器网站和数据迁移到SharePoint Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5eb40-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="5eb40-157">正在进行的迁移维护</span><span class="sxs-lookup"><span data-stu-id="5eb40-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="5eb40-158">您可能需要持续：</span><span class="sxs-lookup"><span data-stu-id="5eb40-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="5eb40-159">根据您的邮箱迁移Exchange，继续滚动到向Exchange Online迁移。</span><span class="sxs-lookup"><span data-stu-id="5eb40-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="5eb40-160">根据本地部署和网站SharePoint的状态，继续向组织SharePoint Microsoft 365迁移。</span><span class="sxs-lookup"><span data-stu-id="5eb40-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="5eb40-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5eb40-161">Next step</span></span>

<span data-ttu-id="5eb40-162">[![步骤 5.部署设备和应用管理](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="5eb40-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="5eb40-163">继续执行 [设备和应用管理，](tenant-management-device-management.md) 以部署设备和应用管理。</span><span class="sxs-lookup"><span data-stu-id="5eb40-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>