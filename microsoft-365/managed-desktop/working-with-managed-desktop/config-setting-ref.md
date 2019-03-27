---
title: Microsoft 托管桌面的可配置设置参考
description: 在 Microsoft 托管桌面中设置可配置设置的类别
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 296602422cf4d590ae17335d7a0bbbc939d929ed
ms.sourcegitcommit: d38c0ce846bac19e876a03a59ed4f268c7bae389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900271"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="7e5de-104">可配置的设置参考-Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="7e5de-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="7e5de-105">本主题列出了客户可以使用 Microsoft 托管桌面配置的设置类别。</span><span class="sxs-lookup"><span data-stu-id="7e5de-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="7e5de-106">每个设置类别都包含有关要求、最佳实践以及如何自定义设置类别的信息。</span><span class="sxs-lookup"><span data-stu-id="7e5de-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="7e5de-107">桌面背景图片</span><span class="sxs-lookup"><span data-stu-id="7e5de-107">Desktop background picture</span></span>
<span data-ttu-id="7e5de-108">您可以为组织中的 Microsoft 托管桌面设备自定义桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="7e5de-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="7e5de-109">您可以使用它来应用公司品牌或营销材料。</span><span class="sxs-lookup"><span data-stu-id="7e5de-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="7e5de-110">Requirements</span><span class="sxs-lookup"><span data-stu-id="7e5de-110">Requirements</span></span>

<span data-ttu-id="7e5de-111">必须满足桌面背景图片的以下要求:</span><span class="sxs-lookup"><span data-stu-id="7e5de-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="7e5de-112">图片文件格式-.jpg、jpeg 或 .png</span><span class="sxs-lookup"><span data-stu-id="7e5de-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="7e5de-113">文件位置-主机位于受信任的安全 http (https) 位置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="7e5de-114">不允许-不支持 Http 和文件共享 (unc) 位置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="7e5de-115">自定义和部署桌面背景图片</span><span class="sxs-lookup"><span data-stu-id="7e5de-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="7e5de-116">**添加自定义桌面背景图片**</span><span class="sxs-lookup"><span data-stu-id="7e5de-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="7e5de-117">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="7e5de-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="7e5de-118">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="7e5de-119">在**可配置**的工作区中, 选择 "**桌面背景图片**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="7e5de-120">输入要使用的图片的位置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="7e5de-121">选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="7e5de-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="7e5de-122">浏览器起始页</span><span class="sxs-lookup"><span data-stu-id="7e5de-122">Browser start pages</span></span>
<span data-ttu-id="7e5de-123">当用户启动 Microsoft Edge 时, 浏览器起始页在各个选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="7e5de-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="7e5de-124">如果您想让用户轻松打开一组经常使用的网站, 请为每个网站添加一个浏览器起始页。</span><span class="sxs-lookup"><span data-stu-id="7e5de-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="7e5de-125">Requirements</span><span class="sxs-lookup"><span data-stu-id="7e5de-125">Requirements</span></span>

<span data-ttu-id="7e5de-126">您必须为您的浏览器起始页提供 intranet 或 Internet 站点的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7e5de-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="7e5de-127">如果配置了内部网站, 请让用户知道, 仅当在 office 中连接到内部网络或使用 VPN 连接进行连接时, 才允许访问这些网站。</span><span class="sxs-lookup"><span data-stu-id="7e5de-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="7e5de-128">自定义和部署浏览器起始页</span><span class="sxs-lookup"><span data-stu-id="7e5de-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="7e5de-129">**添加浏览器起始页**</span><span class="sxs-lookup"><span data-stu-id="7e5de-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="7e5de-130">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="7e5de-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="7e5de-131">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="7e5de-132">在**可配置**的工作区中, 选择 "**浏览器起始页**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="7e5de-133">选择 "**添加起始页**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="7e5de-134">在 "**添加浏览器起始页**" 中, 输入要使用的网站的 URL, 然后选择 "**添加起始页**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="7e5de-135">对其他浏览器启动页重复步骤1-5。</span><span class="sxs-lookup"><span data-stu-id="7e5de-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="7e5de-136">选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="7e5de-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="7e5de-137">企业模式网站列表位置</span><span class="sxs-lookup"><span data-stu-id="7e5de-137">Enterprise mode site list location</span></span>

<span data-ttu-id="7e5de-138">如果您具有与 Microsoft Edge 存在兼容性问题的特定网站和应用程序, 则可以使用企业模式网站列表, 以使用 Internet Explorer 11 自动打开网站。</span><span class="sxs-lookup"><span data-stu-id="7e5de-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="7e5de-139">此外, 如果您知道 intranet 网站不能与 Microsoft Edge 正常运行, 则可以将所有 intranet 网站设置为自动使用 Internet Explorer 11 打开。</span><span class="sxs-lookup"><span data-stu-id="7e5de-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="7e5de-140">使用企业模式意味着您可以继续将 Microsoft Edge 用作默认浏览器, 同时确保您的应用程序继续在 Internet Explorer 11 上工作。</span><span class="sxs-lookup"><span data-stu-id="7e5de-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="7e5de-141">有关企业模式网站列表的详细信息, 请参阅[企业模式和企业模式网站列表](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。</span><span class="sxs-lookup"><span data-stu-id="7e5de-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="7e5de-142">您可以指定 https://位置, 也可以指定在其中承载企业模式网站列表的内部共享的位置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="7e5de-143">Requirements</span><span class="sxs-lookup"><span data-stu-id="7e5de-143">Requirements</span></span>

<span data-ttu-id="7e5de-144">企业模式网站列表文件必须满足以下要求:</span><span class="sxs-lookup"><span data-stu-id="7e5de-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="7e5de-145">文件格式-符合[文件要求](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="7e5de-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="7e5de-146">文件位置-主机文件位于内部 https 位置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="7e5de-147">不允许-不允许在内部文件共享 (如 *//sharename*) 上托管</span><span class="sxs-lookup"><span data-stu-id="7e5de-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="7e5de-148">最佳做法</span><span class="sxs-lookup"><span data-stu-id="7e5de-148">Best practices</span></span>

<span data-ttu-id="7e5de-149">提供了这些最佳实践, 以帮助客户确定其 IT 基础结构的现代化:</span><span class="sxs-lookup"><span data-stu-id="7e5de-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="7e5de-150">**选择有限数量的网站**– microsoft 托管桌面使用 microsoft Edge 作为首选浏览器, 以提高组织的整体安全性和用户的可用性。</span><span class="sxs-lookup"><span data-stu-id="7e5de-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="7e5de-151">此列表中的大多数网站都适用于需要较旧版本的浏览器的旧版 web 应用程序, 这些应用程序不会包含任意多个安全功能。</span><span class="sxs-lookup"><span data-stu-id="7e5de-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="7e5de-152">**请考虑使用替代**–考虑使用不同的网站或 web 应用程序, 而无需使用较早的浏览器。</span><span class="sxs-lookup"><span data-stu-id="7e5de-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="7e5de-153">或者, 考虑更新网站, 以便它可以使用较新的浏览器。</span><span class="sxs-lookup"><span data-stu-id="7e5de-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="7e5de-154">较新的浏览器使用最新技术并帮助提高安全性。</span><span class="sxs-lookup"><span data-stu-id="7e5de-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="7e5de-155">自定义和部署企业网站模式列表位置</span><span class="sxs-lookup"><span data-stu-id="7e5de-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="7e5de-156">**添加企业网站模式列表位置**</span><span class="sxs-lookup"><span data-stu-id="7e5de-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="7e5de-157">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="7e5de-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="7e5de-158">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="7e5de-159">在**可配置**的工作区中, 选择 "**企业模式站点列表位置**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="7e5de-160">为您的网站列表输入 https 位置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="7e5de-161">选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="7e5de-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="7e5de-162">受信任网站</span><span class="sxs-lookup"><span data-stu-id="7e5de-162">Trusted sites</span></span>

<span data-ttu-id="7e5de-163">受信任的网站允许您自定义不同网站的安全区域或网站可使用的位置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="7e5de-164">安全区域包括:</span><span class="sxs-lookup"><span data-stu-id="7e5de-164">Security zones include:</span></span> 
- <span data-ttu-id="7e5de-165">区域1–本地 Intranet 区域</span><span class="sxs-lookup"><span data-stu-id="7e5de-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="7e5de-166">区域2–受信任的站点区域</span><span class="sxs-lookup"><span data-stu-id="7e5de-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="7e5de-167">区域3– Internet 区域</span><span class="sxs-lookup"><span data-stu-id="7e5de-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="7e5de-168">区域4–受限制的站点区域</span><span class="sxs-lookup"><span data-stu-id="7e5de-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="7e5de-169">Requirements</span><span class="sxs-lookup"><span data-stu-id="7e5de-169">Requirements</span></span>

<span data-ttu-id="7e5de-170">为每个受信任的站点提供 intranet 或 Internet 站点的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7e5de-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="7e5de-171">自定义和部署受信任的网站</span><span class="sxs-lookup"><span data-stu-id="7e5de-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="7e5de-172">**添加受信任的网站**</span><span class="sxs-lookup"><span data-stu-id="7e5de-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="7e5de-173">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="7e5de-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="7e5de-174">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="7e5de-175">在**可配置**的工作区中, 选择 "**受信任的站点**", 然后选择 "**添加可信站点**"</span><span class="sxs-lookup"><span data-stu-id="7e5de-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="7e5de-176">在 "**添加受信任站点**" 中, 输入 URL, 选择安全区域, 然后选择 "**添加受信任的站点**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="7e5de-177">对要添加的每个受信任站点重复步骤1-4。</span><span class="sxs-lookup"><span data-stu-id="7e5de-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="7e5de-178">选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="7e5de-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="7e5de-179">**删除受信任的网站**</span><span class="sxs-lookup"><span data-stu-id="7e5de-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="7e5de-180">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="7e5de-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="7e5de-181">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="7e5de-182">在**可配置**的工作区中, 选择 "**受信任站点**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="7e5de-183">选择要删除的网站, 然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="7e5de-184">对要删除的每个受信任站点重复步骤1-4。</span><span class="sxs-lookup"><span data-stu-id="7e5de-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="7e5de-185">选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="7e5de-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="7e5de-186">代理</span><span class="sxs-lookup"><span data-stu-id="7e5de-186">Proxy</span></span>
<span data-ttu-id="7e5de-187">您可以管理您的组织的网络代理设置。</span><span class="sxs-lookup"><span data-stu-id="7e5de-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="7e5de-188">添加代理服务器和端口号, 然后添加代理站点例外。</span><span class="sxs-lookup"><span data-stu-id="7e5de-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="7e5de-189">Microsoft 托管桌面包括一组用于运行服务所需的默认代理异常。</span><span class="sxs-lookup"><span data-stu-id="7e5de-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="7e5de-190">默认的排除列表仅可由 Microsoft 托管桌面服务进行修改。</span><span class="sxs-lookup"><span data-stu-id="7e5de-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="7e5de-191">有关详细信息, 请参阅[Microsoft 托管桌面的网络配置](../get-ready/network.md)。</span><span class="sxs-lookup"><span data-stu-id="7e5de-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="7e5de-192">在 microsoft 托管桌面门户中添加的代理站点例外将添加到 microsoft managed desktop service 中包含的默认代理例外。</span><span class="sxs-lookup"><span data-stu-id="7e5de-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="7e5de-193">更新默认代理例外列表始终优先于客户部署。</span><span class="sxs-lookup"><span data-stu-id="7e5de-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="7e5de-194">这意味着, 如果为默认代理例外列表部署, 则将暂停暂存部署。</span><span class="sxs-lookup"><span data-stu-id="7e5de-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="7e5de-195">Requirements</span><span class="sxs-lookup"><span data-stu-id="7e5de-195">Requirements</span></span>

<span data-ttu-id="7e5de-196">对于代理服务器和代理站点例外, 必须满足以下要求:</span><span class="sxs-lookup"><span data-stu-id="7e5de-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="7e5de-197">必须是有效的服务器地址和端口号</span><span class="sxs-lookup"><span data-stu-id="7e5de-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="7e5de-198">url 必须是有效的 http 站点</span><span class="sxs-lookup"><span data-stu-id="7e5de-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="7e5de-199">自定义和部署代理</span><span class="sxs-lookup"><span data-stu-id="7e5de-199">Customize and deploy proxies</span></span>

<span data-ttu-id="7e5de-200">**添加单个代理站点例外**</span><span class="sxs-lookup"><span data-stu-id="7e5de-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="7e5de-201">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="7e5de-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="7e5de-202">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="7e5de-203">在**可配置**的工作区中, 选择 "**代理**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="7e5de-204">输入代理服务器的**地址**和**端口号**, 然后选择 "**添加代理例外**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="7e5de-205">输入有效的 http 站点的 URL, 然后选择 "**添加代理例外**"。</span><span class="sxs-lookup"><span data-stu-id="7e5de-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="7e5de-206">对要添加的每个受信任站点重复步骤1-5。</span><span class="sxs-lookup"><span data-stu-id="7e5de-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="7e5de-207">选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="7e5de-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7e5de-208">其他资源</span><span class="sxs-lookup"><span data-stu-id="7e5de-208">Additional resources</span></span>
- [<span data-ttu-id="7e5de-209">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="7e5de-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="7e5de-210">部署可配置的设置</span><span class="sxs-lookup"><span data-stu-id="7e5de-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
