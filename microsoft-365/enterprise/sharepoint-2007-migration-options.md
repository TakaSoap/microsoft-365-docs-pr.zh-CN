---
title: 要考虑的 SharePoint 2007 迁移选项
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文包含有关使用 SharePoint Server 2007 的用户的信息，帮助他们规划升级。
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924876"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a><span data-ttu-id="31ebb-103">要考虑的 SharePoint 2007 迁移选项</span><span class="sxs-lookup"><span data-stu-id="31ebb-103">SharePoint 2007 migration options to consider</span></span>

<span data-ttu-id="31ebb-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="31ebb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="31ebb-105">Microsoft SharePoint 2007 和 SharePoint Server 2007 已终止支持。</span><span class="sxs-lookup"><span data-stu-id="31ebb-105">Microsoft SharePoint 2007 and SharePoint Server 2007 have reached end of support.</span></span> <span data-ttu-id="31ebb-106">是时候升级了！</span><span class="sxs-lookup"><span data-stu-id="31ebb-106">It's time to upgrade!</span></span> <span data-ttu-id="31ebb-107">本文提供有关迁移选项的信息。</span><span class="sxs-lookup"><span data-stu-id="31ebb-107">This article provides information about your migration options.</span></span>
  
## <a name="common-upgrade-strategies-for-sharepoint"></a><span data-ttu-id="31ebb-108">SharePoint 的常见升级策略</span><span class="sxs-lookup"><span data-stu-id="31ebb-108">Common upgrade strategies for SharePoint</span></span>

<span data-ttu-id="31ebb-109">有多种方法可以升级 SharePoint Server 环境。</span><span class="sxs-lookup"><span data-stu-id="31ebb-109">There are multiple methods to upgrade a SharePoint Server environment.</span></span> <span data-ttu-id="31ebb-110">如果您有 SharePoint Server 2007 Microsoft Office，下面是升级方法的一些示例：</span><span class="sxs-lookup"><span data-stu-id="31ebb-110">If you have a Microsoft Office SharePoint Server 2007 farm, here are some examples of the upgrade methods:</span></span>
  
- <span data-ttu-id="31ebb-111">数据库附加</span><span class="sxs-lookup"><span data-stu-id="31ebb-111">Database attach</span></span>
    
- <span data-ttu-id="31ebb-112">并行升级</span><span class="sxs-lookup"><span data-stu-id="31ebb-112">Side-by-side upgrade</span></span>
    
- <span data-ttu-id="31ebb-113">就地升级</span><span class="sxs-lookup"><span data-stu-id="31ebb-113">In-place upgrade</span></span>
    
- <span data-ttu-id="31ebb-114">具有 (数据库/单独的数据库附加数据库的混合升级) </span><span class="sxs-lookup"><span data-stu-id="31ebb-114">Hybrid upgrade (in-place with detached databases / separate database attach)</span></span>
    
- <span data-ttu-id="31ebb-115">SharePoint 混合 (联机连接到本地 SharePoint) </span><span class="sxs-lookup"><span data-stu-id="31ebb-115">SharePoint hybrids (connect online to on-premises SharePoint)</span></span>
    
- <span data-ttu-id="31ebb-116">在网站集或库之间手动移动数据</span><span class="sxs-lookup"><span data-stu-id="31ebb-116">Manually move data between site collections or libraries</span></span>
    
- <span data-ttu-id="31ebb-117">FastTrack 向导升级到 Microsoft 365 ([SharePoint Online 部署顾问](https://aka.ms/spoguidance)) </span><span class="sxs-lookup"><span data-stu-id="31ebb-117">FastTrack Wizard upgrade to Microsoft 365 ([SharePoint Online deployment advisor](https://aka.ms/spoguidance))</span></span>
    
- <span data-ttu-id="31ebb-118">迁移到 Microsoft 365 中的 SharePoint Online (SPO) API</span><span class="sxs-lookup"><span data-stu-id="31ebb-118">Migration API to SharePoint Online (SPO) in Microsoft 365</span></span>
    
<span data-ttu-id="31ebb-119">哪些方法最适合你？</span><span class="sxs-lookup"><span data-stu-id="31ebb-119">What works best for you?</span></span>
  
<span data-ttu-id="31ebb-120">您了解服务器场执行和用于哪些操作是升级时的强大功能。</span><span class="sxs-lookup"><span data-stu-id="31ebb-120">Your knowledge of what your farm does and is used for is a tactical strength when it comes to upgrade.</span></span> <span data-ttu-id="31ebb-121">用户使用 SharePoint 场的方式将帮助您从选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="31ebb-121">The way people use the SharePoint Farm will help you choose from your options.</span></span>
  
> [!TIP]
> <span data-ttu-id="31ebb-122">Microsoft Office SharePoint Server 2007 还有逐步升级，此处未介绍。</span><span class="sxs-lookup"><span data-stu-id="31ebb-122">Microsoft Office SharePoint Server 2007 also has a gradual upgrade not covered here.</span></span> <span data-ttu-id="31ebb-123">若要查看特定于步骤的升级文章的列表，请参阅 [SharePoint Server 2007 停止提供支持路线图](sharepoint-2007-end-of-support.md)。</span><span class="sxs-lookup"><span data-stu-id="31ebb-123">To see a list of step-specific upgrade articles see the [SharePoint Server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md).</span></span> 
  
<span data-ttu-id="31ebb-124">请记住检查 [要升级到](https://support.microsoft.com/lifecycle/search) 的任何版本的 SharePoint 的产品生命周期和系统要求。</span><span class="sxs-lookup"><span data-stu-id="31ebb-124">Remember to check the [Product Lifecycle](https://support.microsoft.com/lifecycle/search) and System Requirements for whatever version of SharePoint you're upgrading to.</span></span> <span data-ttu-id="31ebb-125">因此，您将知道何时需要下一次升级 (例如，如果您暂停 SharePoint Server 2010 等旧版产品以规划更多升级，请确保您知道其支持日期) 的结束日期，并确保您具有支持您的计划的硬件。</span><span class="sxs-lookup"><span data-stu-id="31ebb-125">This is so you'll be aware when the next upgrade will be necessary (for example, if you pause at a legacy product like SharePoint Server 2010 to plan for more upgrades, be sure you know its end of support date), and to be certain you have hardware that supports your plan.</span></span> 
  
<span data-ttu-id="31ebb-126">如果计划将部分或全部 SharePoint 网站转换到云中的 Microsoft 365，此时需要为 [指向 Microsoft 365 和 Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library)服务说明的链接添加书签。</span><span class="sxs-lookup"><span data-stu-id="31ebb-126">If you're planning to transition some, or all, of your SharePoint sites to Microsoft 365 in the Cloud, this is a time to bookmark a link to the [Microsoft 365 and Office 365 service descriptions](/office365/servicedescriptions/office-365-service-descriptions-technet-library).</span></span> <span data-ttu-id="31ebb-127">您需要使用服务说明了解 SharePoint Online 功能，以及这些功能与本地 SharePoint Server 可能会如何不同。</span><span class="sxs-lookup"><span data-stu-id="31ebb-127">You'll need the Service Descriptions to learn about SharePoint Online features and how they might differ from on-premises SharePoint Server.</span></span> <span data-ttu-id="31ebb-128">升级 SharePoint Server 2007 Microsoft Office功能。</span><span class="sxs-lookup"><span data-stu-id="31ebb-128">Upgrade functional Microsoft Office SharePoint Server 2007 farms.</span></span> <span data-ttu-id="31ebb-129">如果安装中的网站已损坏，请先修复这些网站，之后进行升级。</span><span class="sxs-lookup"><span data-stu-id="31ebb-129">If your installation has sites that are broken, fix them prior to upgrade.</span></span>
  
## <a name="a-note-about-managing-risk"></a><span data-ttu-id="31ebb-130">关于管理风险的注释</span><span class="sxs-lookup"><span data-stu-id="31ebb-130">A note about managing risk</span></span>

<span data-ttu-id="31ebb-131">"并行"等方法在升级逻辑方案中非常重要。</span><span class="sxs-lookup"><span data-stu-id="31ebb-131">Methods like 'side-by-side' are important in the scheme of upgrade logic.</span></span> <span data-ttu-id="31ebb-132">并行升级时，可以维护 Microsoft Office SharePoint Server 2007 场，但从它构建下一个版本 (SharePoint Server 2010) 新硬件。</span><span class="sxs-lookup"><span data-stu-id="31ebb-132">When you upgrade side-by-side, you maintain your Microsoft Office SharePoint Server 2007 farm, but build a farm the next version up from it (SharePoint Server 2010) on new hardware.</span></span> <span data-ttu-id="31ebb-133">这有三方面的帮助：</span><span class="sxs-lookup"><span data-stu-id="31ebb-133">This helps in three ways:</span></span>
  
1. <span data-ttu-id="31ebb-134">可以使用数据库附加对 SharePoint Server 2007 Microsoft Office进行备份，以单独升级这些数据库。</span><span class="sxs-lookup"><span data-stu-id="31ebb-134">You have a place to take backups of your Microsoft Office SharePoint Server 2007 databases to upgrade them separately, by using database attach.</span></span>
    
2. <span data-ttu-id="31ebb-135">如果您确定 Microsoft Office SharePoint Server 2007 服务器场上仅使用了少量关键文档库和其他信息，您可以选择手动将数据从 Microsoft Office SharePoint Server 2007 移动到 SharePoint Server 2010，或仅将特定网站和 Web 移动到下一版本 (这样可简化) 工作。</span><span class="sxs-lookup"><span data-stu-id="31ebb-135">If you figure out that only a small number of critical document libraries and other information are in use on your Microsoft Office SharePoint Server 2007 farm, you can choose to manually move data from Microsoft Office SharePoint Server 2007 to SharePoint Server 2010, or take only specific sites and webs to the next version (which can make your job easier).</span></span>
    
3. <span data-ttu-id="31ebb-136">直接对 SharePoint Server 2007 Microsoft Office执行较少操作，升级时服务器场包含的数据就更安全。</span><span class="sxs-lookup"><span data-stu-id="31ebb-136">The less you do to the Microsoft Office SharePoint Server 2007 server farm, directly, the safer the data that farm contains as you upgrade.</span></span>
    
<span data-ttu-id="31ebb-137">In-Place升级等方法将直接作用于 Microsoft Office SharePoint Server 2007 场，从而减少放弃路径和从环境开始轻松选择的选项。</span><span class="sxs-lookup"><span data-stu-id="31ebb-137">Methods like In-Place upgrade will act directly on your Microsoft Office SharePoint Server 2007 farm, giving you fewer easy options to abandon a path and begin again with your pristine environment.</span></span> <span data-ttu-id="31ebb-138">尽可能在一些安全措施中 (如采用和测试原始环境备份) 。</span><span class="sxs-lookup"><span data-stu-id="31ebb-138">As much as possible, build in some safety measures (like taking and testing backups of the original environment).</span></span> <span data-ttu-id="31ebb-139">例如，如果您的 Microsoft Office SharePoint Server 2007 服务器场是虚拟的，并且出于备份和还原目的被复制，那么在升级的服务窗口之前备份和还原最新的数据库。</span><span class="sxs-lookup"><span data-stu-id="31ebb-139">For example, if your Microsoft Office SharePoint Server 2007 farm is virtual, and is duplicated for the purposes of backup and restore, then back-up and restore the most current databases prior to your service window for the upgrade.</span></span> <span data-ttu-id="31ebb-140">如果您知道您可以选择还原数据库备份，则不仅为您提供了故障安全，还使您大为信心。</span><span class="sxs-lookup"><span data-stu-id="31ebb-140">Knowing that you have the option to restore database backups will not only give you a failsafe, it can give you peace of mind.</span></span>
  
> [!TIP]
> <span data-ttu-id="31ebb-141">适用于[Microsoft Office SharePoint Server 2007、SharePoint Server 2010、SharePoint](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)) [Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)和[SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade)的升级最佳做法文档已存在。 [](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14))</span><span class="sxs-lookup"><span data-stu-id="31ebb-141">Best practices documents for upgrade exist for [Microsoft Office SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)), [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)), [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013), and [SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade).</span></span> <span data-ttu-id="31ebb-142">还可以搜索具有升级或 [Microsoft](https://partnercenter.microsoft.com/pcv/search) 365 迁移经验的 Microsoft 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="31ebb-142">You can also search for [Microsoft Partners](https://partnercenter.microsoft.com/pcv/search) who have experience with upgrades or Microsoft 365 migrations.</span></span> 
  
## <a name="make-your-plan"></a><span data-ttu-id="31ebb-143">制定计划</span><span class="sxs-lookup"><span data-stu-id="31ebb-143">Make your plan</span></span>

<span data-ttu-id="31ebb-144">如果需要升级，则需要一个计划，在这种情况下，一个大小并不适合所有内容。</span><span class="sxs-lookup"><span data-stu-id="31ebb-144">If you need to upgrade, you need a plan, and one-size doesn't fit all in these cases.</span></span> <span data-ttu-id="31ebb-145">你的计划可能非常简单，例如"使用 SharePoint Online 创建 Microsoft 365 订阅，注册域，然后重定向用户以将文件保存到该域"。</span><span class="sxs-lookup"><span data-stu-id="31ebb-145">Your plan may be as simple as 'Create a Microsoft 365 subscription with SharePoint Online, register a domain, and redirect people to save their files there'.</span></span> <span data-ttu-id="31ebb-146">它可能不是。</span><span class="sxs-lookup"><span data-stu-id="31ebb-146">And it may not be.</span></span> <span data-ttu-id="31ebb-147">该决定由你决定，由你和用户真正需要决定。</span><span class="sxs-lookup"><span data-stu-id="31ebb-147">That decision is yours, and it's down to what you and your users really need.</span></span>
  
> [!NOTE]
> <span data-ttu-id="31ebb-148">在生命周期已终止的软件上运行存在风险。</span><span class="sxs-lookup"><span data-stu-id="31ebb-148">It's risky to run on software whose lifecycle has ended.</span></span> <span data-ttu-id="31ebb-149">如果发现问题，将不再修补不再提供支持的产品。</span><span class="sxs-lookup"><span data-stu-id="31ebb-149">Products that are out of support are no longer patched when issues are found.</span></span> <span data-ttu-id="31ebb-150">这也意味着，如果出现新的安全威胁，将不会出现安全修补程序或修补程序，因为生命周期结束产品不再受支持。</span><span class="sxs-lookup"><span data-stu-id="31ebb-150">This also means that if new security threats arise, there will be no security patches or fixes because the end-of-lifecycle products are no longer supported.</span></span> <span data-ttu-id="31ebb-151">请避免这种情况！</span><span class="sxs-lookup"><span data-stu-id="31ebb-151">Please avoid that situation!</span></span> 
  
### <a name="first-know-your-farm"></a><span data-ttu-id="31ebb-152">首先，了解服务器场</span><span class="sxs-lookup"><span data-stu-id="31ebb-152">First, know your farm</span></span>

<span data-ttu-id="31ebb-153">在升级时，您的决策应基于您的服务器场对您的组织所完成的工作。</span><span class="sxs-lookup"><span data-stu-id="31ebb-153">When upgrading, your decision-making should be based on what your farm does for your organization.</span></span> <span data-ttu-id="31ebb-154">它满足哪些需求？</span><span class="sxs-lookup"><span data-stu-id="31ebb-154">What need does it satisfy?</span></span> <span data-ttu-id="31ebb-155">它的角色是什么？</span><span class="sxs-lookup"><span data-stu-id="31ebb-155">What's its role?</span></span> <span data-ttu-id="31ebb-156">公司中的每个服务器场可能具有不同的角色。</span><span class="sxs-lookup"><span data-stu-id="31ebb-156">Each farm in your company may have a different role.</span></span> <span data-ttu-id="31ebb-157">一些 SharePoint 场可能是  *关键服务器场*  ，一些可能是文件存档（其中用于安全保存）。</span><span class="sxs-lookup"><span data-stu-id="31ebb-157">Some of your SharePoint farms may be  *critical*  , some may be file archives -- there for safe-keeping.</span></span> <span data-ttu-id="31ebb-158">或者，如果服务器场一次填充许多角色，则您可能需要了解网站集、Web 甚至文档库所执行哪些操作、任何自定义项及其重要级别。</span><span class="sxs-lookup"><span data-stu-id="31ebb-158">Or, if your farm fills many roles at once, then you may need to know what site collections, webs, or even document libraries do, any customizations, and how important they are.</span></span> <span data-ttu-id="31ebb-159">在此级别分析数据似乎需要做大量工作，但在升级或迁移域之前，可以省去控制域的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="31ebb-159">Analyzing your data at this level may seem like a lot of work, but it saves time and effort to master your domain before you upgrade, or migrate, it.</span></span> <span data-ttu-id="31ebb-160">在了解所有移动部件和最重要的位后，你还将了解你已增长并可以留下哪些内容。</span><span class="sxs-lookup"><span data-stu-id="31ebb-160">Once you know all the moving parts, and the most important bits, you'll also know what you've outgrown and can leave behind.</span></span> <span data-ttu-id="31ebb-161">这些知识仅对今后会大有益处。</span><span class="sxs-lookup"><span data-stu-id="31ebb-161">That knowledge will only benefit you going forward.</span></span> 
  
<span data-ttu-id="31ebb-162">那么，用户对 SharePoint Server 场说哪些内容最重要？</span><span class="sxs-lookup"><span data-stu-id="31ebb-162">So, what are users saying is most important about your SharePoint Server farm?</span></span>
  
- <span data-ttu-id="31ebb-163">内置的 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="31ebb-163">Built-in SharePoint features</span></span>
    
- <span data-ttu-id="31ebb-164">大型数据集 (，如文件存档) </span><span class="sxs-lookup"><span data-stu-id="31ebb-164">The large data corpus (such as an archive of files)</span></span>
    
- <span data-ttu-id="31ebb-165">供应情况</span><span class="sxs-lookup"><span data-stu-id="31ebb-165">Availability</span></span>
    
- <span data-ttu-id="31ebb-166">服务器场中的关键应用、Web 部件或文档 (任务关键型服务器场) </span><span class="sxs-lookup"><span data-stu-id="31ebb-166">Critical apps, web parts, or docs in the farm (Mission critical farm)</span></span>
    
- <span data-ttu-id="31ebb-167">符合合规性标准</span><span class="sxs-lookup"><span data-stu-id="31ebb-167">The Compliance standards met</span></span>
    
- <span data-ttu-id="31ebb-168">自定义项</span><span class="sxs-lookup"><span data-stu-id="31ebb-168">Customizations</span></span>
    
<span data-ttu-id="31ebb-169">如果您从 SharePoint 场运行业务必需的内容，假设它充当有关客户端服务要求的重要数据的大型目录，您可能会在"关键应用程序"旁边加一个刻度，但也可以放在"可用性"旁边，也就是说，如果一段时间你无法使用 SharePoint，你的业务会受到影响。</span><span class="sxs-lookup"><span data-stu-id="31ebb-169">If you run something essential to your business from your SharePoint farm, say it acts like a large catalog of critical data about client service requirements, you may put a tick beside 'Critical apps', but also 'Availability' -- that is, your business would be impacted if you couldn't use SharePoint for a while.</span></span> <span data-ttu-id="31ebb-170">同样，您可能要检查"自定义"，因为服务器场提供的关键服务基于自定义代码、网站定义或协同工作的很多自定义项。</span><span class="sxs-lookup"><span data-stu-id="31ebb-170">Likewise, you might check 'Customizations' because the critical services your farm offers are based on custom code, site definitions, or a number of customizations that work together.</span></span>
  
<span data-ttu-id="31ebb-171">如果 SharePoint 满足这些需求，除了使用软件内置内容外无需执行任何操作，并且通常更新它并执行正常的管理和维护，您可能已选择"内置 SharePoint"，这也是您选择使用较旧版本的 SharePoint 的原因。</span><span class="sxs-lookup"><span data-stu-id="31ebb-171">If SharePoint met those needs without your having to do anything outside of using what's built-in to the software, and you generally update it and carry out normal administration and maintenance, you may have chosen 'Built-in SharePoint' -- this may also be your reason for sitting on an older version of SharePoint.</span></span> <span data-ttu-id="31ebb-172">换句话说，它 Microsoft Office已在 SharePoint Server 2007 停止提供支持时执行所需的操作，并且到目前为止，你无需进行升级。</span><span class="sxs-lookup"><span data-stu-id="31ebb-172">In other words, it already does what you need it to and you haven't needed to upgrade until now, at Microsoft Office SharePoint Server 2007 end of support.</span></span>
  
<span data-ttu-id="31ebb-173">当您为这些项创建项目符号列表时，您将为升级创建条件。</span><span class="sxs-lookup"><span data-stu-id="31ebb-173">When you bullet-list these things, you create criteria for your upgrade.</span></span> <span data-ttu-id="31ebb-174">换句话说，任何升级都必须符合此条考虑。</span><span class="sxs-lookup"><span data-stu-id="31ebb-174">In other words, any upgrade would have to meet this bar to be considered.</span></span> <span data-ttu-id="31ebb-175">这为你提供了一种排除当前不适合你需求的方法的方法的方法。</span><span class="sxs-lookup"><span data-stu-id="31ebb-175">This gives you a way to rule out methods that don't currently fit your needs.</span></span>
  
### <a name="a-simple-sample-plan"></a><span data-ttu-id="31ebb-176">简单示例计划</span><span class="sxs-lookup"><span data-stu-id="31ebb-176">A simple sample plan</span></span>

<span data-ttu-id="31ebb-177">在 SharePoint 升级将采取的路径上，可能需要与领导层和其他管理员达成更广泛的一致。</span><span class="sxs-lookup"><span data-stu-id="31ebb-177">There may need to be wider consensus with leadership and other admins on the path your SharePoint Upgrade will take.</span></span> <span data-ttu-id="31ebb-178">SharePoint Server 管理员通常与Microsoft SQL Server合作，与网络和安全团队等合作。</span><span class="sxs-lookup"><span data-stu-id="31ebb-178">SharePoint Server Administrators often cooperate with Microsoft SQL Server admins, work with Networking and Security teams, and more.</span></span> <span data-ttu-id="31ebb-179">如果有很多利益干系人，你可能需要就升级和迁移计划达成一致或进行调整。</span><span class="sxs-lookup"><span data-stu-id="31ebb-179">Where there are a lot of stakeholders, you may need to build agreement for, or adjust, your upgrade and migration plan.</span></span> <span data-ttu-id="31ebb-180">例如，如果迁移数据以便部分公司使用 Microsoft 365 中的 SharePoint Online，可能需要在网络内部进行性能调整或测试。</span><span class="sxs-lookup"><span data-stu-id="31ebb-180">For example, if you migrate data so that part of your company uses SharePoint Online in Microsoft 365, there will likely need to be performance tuning or testing inside your network.</span></span> <span data-ttu-id="31ebb-181">应提前通知受影响的团队。</span><span class="sxs-lookup"><span data-stu-id="31ebb-181">Affected teams should be informed ahead of time.</span></span>
  
<span data-ttu-id="31ebb-182">在我的简单示例中，我显示了 SharePoint 管理员的建议，然后列出了所有利益干系人都同意的计划。</span><span class="sxs-lookup"><span data-stu-id="31ebb-182">In my simple sample, I show a SharePoint administrator's proposal and then list out the plan that all the stakeholders agreed upon.</span></span> <span data-ttu-id="31ebb-183">为清楚起见，请记录你的协议和决策。</span><span class="sxs-lookup"><span data-stu-id="31ebb-183">For clarity, document your agreements and decisions.</span></span>
  
<span data-ttu-id="31ebb-184">该计划在深入分析服务器场之后开始，并尝试确定服务器场的角色、要点和其他重要信息，这些信息将导致缩小一些升级选项范围。</span><span class="sxs-lookup"><span data-stu-id="31ebb-184">The plan starts after an in-depth analysis of a farm, and tries to identify the role of the farm, pain points, and other important information that will lead to narrowing down some upgrade options.</span></span> <span data-ttu-id="31ebb-185">之后，升级建议由 SharePoint 管理员提出，利益干系人就行动计划达成一致。</span><span class="sxs-lookup"><span data-stu-id="31ebb-185">Afterward, an upgrade proposal is made by SharePoint administrator, and stakeholders agree on an action plan.</span></span>
  
<span data-ttu-id="31ebb-186">我的"最重要的"项目符号列表：</span><span class="sxs-lookup"><span data-stu-id="31ebb-186">My 'most important' bullet list:</span></span>
  
- <span data-ttu-id="31ebb-187">可用性、SharePoint 内置功能以及合规性标准。</span><span class="sxs-lookup"><span data-stu-id="31ebb-187">Availability, features built-in to SharePoint, and Compliance standards.</span></span>
    
- <span data-ttu-id="31ebb-188">大部分数据位于三个网站集上，开发人员团队使用的一个会议工作区尤其重要，并且在全球多个时区中大量使用。</span><span class="sxs-lookup"><span data-stu-id="31ebb-188">Most of the data is on three site collections, with one Meeting Workspace used by a Dev team particularly important and in heavy use in multiple time-zones worldwide.</span></span>
    
- <span data-ttu-id="31ebb-189">还有一些广泛使用的其他网站。</span><span class="sxs-lookup"><span data-stu-id="31ebb-189">There are seventeen other sites that are widely used.</span></span>
    
- <span data-ttu-id="31ebb-190">根网站集 ("会议工作区"和"文档") 两个文档库 (文档数超过 8000 个) 。</span><span class="sxs-lookup"><span data-stu-id="31ebb-190">Two document libraries (Meeting Workspace and Documents on the root site collection) are largest (over 8000 docs each).</span></span> <span data-ttu-id="31ebb-191">我们具有大量包含电子表格附件的存档文档和列表。</span><span class="sxs-lookup"><span data-stu-id="31ebb-191">We have a large number of archived docs and list with spreadsheet attachments.</span></span>
    
- <span data-ttu-id="31ebb-192">有十四个包含敏感数据的库列表必须保持合规性。</span><span class="sxs-lookup"><span data-stu-id="31ebb-192">There are fourteen lists of libraries that have sensitive data that MUST stay in Compliance.</span></span>
    
- <span data-ttu-id="31ebb-193">我们必须能够随时随地进行保留和电子数据发现。</span><span class="sxs-lookup"><span data-stu-id="31ebb-193">We MUST have the ability to do holds and e-discovery wherever we go.</span></span>
    
- <span data-ttu-id="31ebb-194">由于 InfoSec 规则，其中某些数据必须位于本地。</span><span class="sxs-lookup"><span data-stu-id="31ebb-194">Some of this data MUST stay on-premises, due to InfoSec rules.</span></span>
    
 <span data-ttu-id="31ebb-195">**我的升级和迁移选项：**</span><span class="sxs-lookup"><span data-stu-id="31ebb-195">**My upgrade and migration choices:**</span></span>
  
| <span data-ttu-id="31ebb-196">是</span><span class="sxs-lookup"><span data-stu-id="31ebb-196">Yes</span></span> | <span data-ttu-id="31ebb-197">否</span><span class="sxs-lookup"><span data-stu-id="31ebb-197">No</span></span> |
|:-----|:-----|
|<span data-ttu-id="31ebb-198">升级数据库附加数据库</span><span class="sxs-lookup"><span data-stu-id="31ebb-198">Upgrade databases with database attach</span></span>  <br/> |<span data-ttu-id="31ebb-199">就地升级</span><span class="sxs-lookup"><span data-stu-id="31ebb-199">In-place upgrade</span></span>  <br/> |
|<span data-ttu-id="31ebb-200">使用服务器场并行升级</span><span class="sxs-lookup"><span data-stu-id="31ebb-200">Upgrade with farms side-by-side</span></span>  <br/> |<span data-ttu-id="31ebb-201">混合升级</span><span class="sxs-lookup"><span data-stu-id="31ebb-201">Hybrid Upgrade</span></span>  <br/> |
|<span data-ttu-id="31ebb-202">Microsoft 365 中的 SPO 迁移 API (个人网站数据) </span><span class="sxs-lookup"><span data-stu-id="31ebb-202">Migration API to SPO in Microsoft 365 (for personal site data)</span></span>  <br/> |<span data-ttu-id="31ebb-203">目前尚不 (SharePoint 混合) </span><span class="sxs-lookup"><span data-stu-id="31ebb-203">SharePoint Hybrid (not needed yet)</span></span>  <br/> |
|<span data-ttu-id="31ebb-204">一些针对关键数据的手动数据迁移到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="31ebb-204">Some manual data migrations to SharePoint Online for critical data</span></span>  <br/> |<span data-ttu-id="31ebb-205">FastTrack 向导升级到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="31ebb-205">FastTrack wizard upgrade to Microsoft 365</span></span>  <br/> |
   
 <span data-ttu-id="31ebb-206">**我的建议计划：**</span><span class="sxs-lookup"><span data-stu-id="31ebb-206">**My proposed plan:**</span></span>
  
<span data-ttu-id="31ebb-207">在本地升级，并行升级 SharePoint 版本，一些虚拟化版本，以便可以先升级数据库。</span><span class="sxs-lookup"><span data-stu-id="31ebb-207">Upgrade on-premises, with versions of SharePoint side-by-side, some virtualized, so that we can upgrade the databases first.</span></span> <span data-ttu-id="31ebb-208">从 SharePoint 2007 转到 SharePoint 2010。</span><span class="sxs-lookup"><span data-stu-id="31ebb-208">Go from SharePoint 2007 to SharePoint 2010.</span></span> <span data-ttu-id="31ebb-209">管理员和开发人员测试生成的服务器场。</span><span class="sxs-lookup"><span data-stu-id="31ebb-209">Admins and Devs test the resulting farm.</span></span> <span data-ttu-id="31ebb-210">用户测试生成的服务器场。</span><span class="sxs-lookup"><span data-stu-id="31ebb-210">Users test the resulting farm.</span></span> <span data-ttu-id="31ebb-211">修复在此期间出现的任何停止显示问题。</span><span class="sxs-lookup"><span data-stu-id="31ebb-211">Fix any show-stopping issues during this time.</span></span> <span data-ttu-id="31ebb-212">同样，将 SharePoint 2010 数据库并行升级到 SharePoint 2013。</span><span class="sxs-lookup"><span data-stu-id="31ebb-212">Again, side-by-side, upgrade SharePoint 2010 databases to SharePoint 2013.</span></span> <span data-ttu-id="31ebb-213">测试。</span><span class="sxs-lookup"><span data-stu-id="31ebb-213">Test.</span></span> <span data-ttu-id="31ebb-214">用户测试/试点。</span><span class="sxs-lookup"><span data-stu-id="31ebb-214">User test/pilot.</span></span> <span data-ttu-id="31ebb-215">修复在此期间出现的任何停止显示问题。</span><span class="sxs-lookup"><span data-stu-id="31ebb-215">Fix any show-stopping issues during this time.</span></span>
  
- <span data-ttu-id="31ebb-216">考虑搜索联合混合与 SPO 是否满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="31ebb-216">Consider if a Search Federated Hybrid with SPO meets your needs.</span></span>
    
- <span data-ttu-id="31ebb-217">如果你想要从此处升级到 SharePoint Online，请考虑 [使用 FastTrack](https://fasttrack.microsoft.com) 协助。</span><span class="sxs-lookup"><span data-stu-id="31ebb-217">Consider [FastTrack assistance](https://fasttrack.microsoft.com) if you would like to upgrade to SharePoint Online from here.</span></span> 
    
- <span data-ttu-id="31ebb-218">确定是否可以将任何网站集卸载到 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="31ebb-218">Determine if any site collections can be offloaded to a Microsoft 365 Subscription.</span></span> <span data-ttu-id="31ebb-219"> (Microsoft 365 符合许多 [合规性标准](/compliance/regulatory/offering-home)。</span><span class="sxs-lookup"><span data-stu-id="31ebb-219">(Microsoft 365 meets many [Compliance standards](/compliance/regulatory/offering-home).</span></span> <span data-ttu-id="31ebb-220">Microsoft 365 具有 [电子数据](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) 展示 [，可以通过合规](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) 中心进行保留) </span><span class="sxs-lookup"><span data-stu-id="31ebb-220">Microsoft 365 has [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) and can do [Holds](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) through the Compliance Centre.)</span></span> 
    
<span data-ttu-id="31ebb-221">否则，继续并行升级到 SharePoint Server 2016。</span><span class="sxs-lookup"><span data-stu-id="31ebb-221">Otherwise, continue with a side-by-side upgrade to SharePoint Server 2016.</span></span>
  
> [!NOTE]
> <span data-ttu-id="31ebb-222">在规划升级的管理员提供的建议与实际过程之间是升级所依赖的其他利益干系人的对话。</span><span class="sxs-lookup"><span data-stu-id="31ebb-222">In between recommendations made by the administrators planning the upgrade and the actual process are the conversations that happen with other stakeholders on which the upgrade relies.</span></span> <span data-ttu-id="31ebb-223">例如，有时会强制管理员更改其计划。</span><span class="sxs-lookup"><span data-stu-id="31ebb-223">For example, sometimes economics force administrators to change their plans.</span></span> <span data-ttu-id="31ebb-224">无论最终决定是什么，您都应记录下一个达成一致计划的内容。</span><span class="sxs-lookup"><span data-stu-id="31ebb-224">Whatever the final decision is, you should document what the agreed-upon plan is, going forward.</span></span> <span data-ttu-id="31ebb-225">它可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="31ebb-225">It might look something like this:</span></span> 
  
 <span data-ttu-id="31ebb-226">**我的行动计划：**</span><span class="sxs-lookup"><span data-stu-id="31ebb-226">**My action plan:**</span></span>
  
<span data-ttu-id="31ebb-227">在本地，我们使用虚拟环境来构建默认 SharePoint Server 2010 和 2013。</span><span class="sxs-lookup"><span data-stu-id="31ebb-227">On-premises, we use a virtual environment to build default SharePoint Server 2010, and 2013.</span></span> <span data-ttu-id="31ebb-228">SharePoint Server 2016 将基于满足 2016 年系统要求的新硬件构建。</span><span class="sxs-lookup"><span data-stu-id="31ebb-228">SharePoint Server 2016 will be built on new hardware that meets system requirements for 2016.</span></span> <span data-ttu-id="31ebb-229">我们会将数据库附加到从 SharePoint 2007 到 SharePoint Server 2016 之间的所有版本升级数据库。</span><span class="sxs-lookup"><span data-stu-id="31ebb-229">We will do database attaches to upgrade databases from SharePoint 2007 through all versions between it and SharePoint Server 2016.</span></span> <span data-ttu-id="31ebb-230">目前，如果本机功能还没有满足我们的需求，将在 SharePoint Server 2016 环境中重新创建和测试核心自定义项。</span><span class="sxs-lookup"><span data-stu-id="31ebb-230">Core customizations are being recreated for and tested in the SharePoint Server 2016 environment at this time, if native features don't already meet our needs.</span></span> <span data-ttu-id="31ebb-231">如果成功，我们将有一个本地服务器场，该服务器场位于具有升级数据库的新硬件上，并且自定义项更少。</span><span class="sxs-lookup"><span data-stu-id="31ebb-231">If we are successful, we will have an on-premises farm on new hardware with upgraded databases, and fewer customizations.</span></span> <span data-ttu-id="31ebb-232">我们将升级后的内容数据库附加到 SharePoint Server 2013 中的新网站集、测试、用户测试/试点，然后执行 DNS 剪切到新的 SharePoint Server 2016 环境以实时使用。</span><span class="sxs-lookup"><span data-stu-id="31ebb-232">We'll attach the upgraded content databases to new site collections in SharePoint Server 2013, test, user test/pilot, and then do a DNS cut-over to the new SharePoint Server 2016 environment for live use.</span></span>
  
- <span data-ttu-id="31ebb-233">目前，我们不考虑 SharePoint Server 2016 和 SharePoint Online 之间的联合混合。</span><span class="sxs-lookup"><span data-stu-id="31ebb-233">We will not consider Federated Hybrid between SharePoint Server 2016 and SharePoint Online right now.</span></span>
    
- <span data-ttu-id="31ebb-234">估计有 35% 的网站可以转换为具有虚域的新 SPO 网站，或者最终变为 OneDrive for Business 存储。</span><span class="sxs-lookup"><span data-stu-id="31ebb-234">An estimated 35% of our sites can be turned into new SPO sites with vanity domains, or, ultimately, become OneDrive for Business storage.</span></span> <span data-ttu-id="31ebb-235">寻找转换站点或将新站点路由到 SPO 的其他机会。</span><span class="sxs-lookup"><span data-stu-id="31ebb-235">Looking for other opportunities to convert sites, or route new sites to SPO.</span></span>
    
- <span data-ttu-id="31ebb-236">迁移的这一部分包括手动迁移、拖放到 OneDrive for Business 个人网站，还有一部分通过迁移 API 进行。</span><span class="sxs-lookup"><span data-stu-id="31ebb-236">Some of this part of the migration will be manual, by drag-and-drop to OneDrive for Business personal sites, and some by migration API.</span></span>
    
<span data-ttu-id="31ebb-237">应按照计划执行更详细的步骤或指向特定升级方向的一些链接。</span><span class="sxs-lookup"><span data-stu-id="31ebb-237">More detailed steps, or a number of links to specific upgrade directions should follow a plan.</span></span> <span data-ttu-id="31ebb-238">MOSS 2007 计算机不应停用，为了进行比较，应维护虚拟环境;但是，当用户重定向到 SharePoint Server 2016 时，升级将完成。</span><span class="sxs-lookup"><span data-stu-id="31ebb-238">The MOSS 2007 computer should not be decommissioned, and virtual environments should be maintained for the sake of comparison; however, the upgrade will be complete when users are redirected to SharePoint Server 2016.</span></span>
  
<span data-ttu-id="31ebb-239">选择方法的一个主要因素通常是升级的总成本和时间成本 (您将在 SharePoint 迁移路线图文章) 中查看有关此内容) 。</span><span class="sxs-lookup"><span data-stu-id="31ebb-239">Often major factors in choosing a method are the total cost of the upgrade and the cost in time (you'll see more on this in the SharePoint Migration Roadmap article).</span></span> <span data-ttu-id="31ebb-240">但是，提前规划将大大有助于你设置预期、做出明智的选择以及确定成功的外观。</span><span class="sxs-lookup"><span data-stu-id="31ebb-240">However, planning ahead will benefit you greatly in setting expectations, choosing wisely, and framing what success will look like.</span></span>
  
## <a name="related-links"></a><span data-ttu-id="31ebb-241">相关链接</span><span class="sxs-lookup"><span data-stu-id="31ebb-241">Related links</span></span>

[<span data-ttu-id="31ebb-242">帮助您从 Office 2007 服务器和客户端升级的资源</span><span class="sxs-lookup"><span data-stu-id="31ebb-242">Resources to help you upgrade from Office 2007 servers and clients</span></span>](upgrade-from-office-2007-servers-and-products.md)
  
[<span data-ttu-id="31ebb-243">Microsoft 生命周期策略和生命周期搜索</span><span class="sxs-lookup"><span data-stu-id="31ebb-243">Microsoft Lifecycle Policy and Lifecycle search</span></span>](https://support.microsoft.com/lifecycle)
  
[<span data-ttu-id="31ebb-244">搜索可帮助升级或迁移的 Microsoft 合作伙伴</span><span class="sxs-lookup"><span data-stu-id="31ebb-244">Search for Microsoft Partners who can help with upgrade or migration</span></span>](https://partnercenter.microsoft.com/pcv/search)
