---
title: Microsoft 托管桌面的可配置设置参考
description: 在 Microsoft 托管桌面中设置可配置设置的类别
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917700"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="400ff-104">可配置设置参考 - Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="400ff-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="400ff-105">本主题列出了客户可以使用 Microsoft 托管桌面配置的设置类别。</span><span class="sxs-lookup"><span data-stu-id="400ff-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="400ff-106">每个设置类别包括有关要求、最佳做法以及如何自定义设置类别的信息。</span><span class="sxs-lookup"><span data-stu-id="400ff-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="400ff-107">桌面背景图片</span><span class="sxs-lookup"><span data-stu-id="400ff-107">Desktop background picture</span></span>
<span data-ttu-id="400ff-108">你可以自定义组织中 Microsoft 托管桌面设备的桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="400ff-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="400ff-109">可以使用它应用公司品牌或营销材料。</span><span class="sxs-lookup"><span data-stu-id="400ff-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="400ff-110">要求</span><span class="sxs-lookup"><span data-stu-id="400ff-110">Requirements</span></span>

<span data-ttu-id="400ff-111">桌面背景图片必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="400ff-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="400ff-112">图片文件格式 - .jpg、jpeg 或 .png</span><span class="sxs-lookup"><span data-stu-id="400ff-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="400ff-113">文件位置 - 受信任安全 http 上的主机 (https) 位置。</span><span class="sxs-lookup"><span data-stu-id="400ff-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="400ff-114">不允许 - 不支持 http 和文件共享 (unc) 位置。</span><span class="sxs-lookup"><span data-stu-id="400ff-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="400ff-115">自定义和部署桌面背景图片</span><span class="sxs-lookup"><span data-stu-id="400ff-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="400ff-116">**添加自定义桌面背景图片**</span><span class="sxs-lookup"><span data-stu-id="400ff-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="400ff-117">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="400ff-117">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="400ff-118">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-118">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="400ff-119">在 **"设置**"工作区中，选择 **"桌面背景图片"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-119">In **Settings** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="400ff-120">输入想要使用的图片的位置。</span><span class="sxs-lookup"><span data-stu-id="400ff-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="400ff-121">选择 **"阶段** 部署"保存更改并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="400ff-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="400ff-122">浏览器起始页</span><span class="sxs-lookup"><span data-stu-id="400ff-122">Browser start pages</span></span>
<span data-ttu-id="400ff-123">当用户启动 Microsoft Edge 时，浏览器起始页在单个选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="400ff-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="400ff-124">如果希望用户轻松打开他们经常使用的一组网站，请添加每个网站的浏览器起始页。</span><span class="sxs-lookup"><span data-stu-id="400ff-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="400ff-125">要求</span><span class="sxs-lookup"><span data-stu-id="400ff-125">Requirements</span></span>

<span data-ttu-id="400ff-126">必须为浏览器起始页的 Intranet 或 Internet (FQDN) 完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="400ff-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="400ff-127">如果配置了内部站点，请让用户知道，只有在办公室或通过 VPN 连接连接到内部网络时，才允许访问这些站点。</span><span class="sxs-lookup"><span data-stu-id="400ff-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="400ff-128">自定义和部署浏览器起始页</span><span class="sxs-lookup"><span data-stu-id="400ff-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="400ff-129">**添加浏览器起始页**</span><span class="sxs-lookup"><span data-stu-id="400ff-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="400ff-130">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="400ff-130">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="400ff-131">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-131">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="400ff-132">在 **"设置**"工作区中，选择 **"浏览器起始页"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-132">In **Settings** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="400ff-133">选择 **"添加起始页"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="400ff-134">在 **"添加浏览器起始页**"上，输入要使用网站的 URL，然后选择"**添加起始页"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="400ff-135">对其他浏览器起始页重复步骤 1-5。</span><span class="sxs-lookup"><span data-stu-id="400ff-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="400ff-136">选择 **"阶段** 部署"保存更改并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="400ff-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="400ff-137">企业模式站点列表位置</span><span class="sxs-lookup"><span data-stu-id="400ff-137">Enterprise mode site list location</span></span>

<span data-ttu-id="400ff-138">如果你拥有你知道与 Microsoft Edge 存在兼容性问题的特定网站和应用，可以使用企业模式站点列表，以便使用 11 Internet Explorer网站。</span><span class="sxs-lookup"><span data-stu-id="400ff-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="400ff-139">此外，如果你知道 Intranet 站点不能与 Microsoft Edge 一起正常工作，可以将所有 Intranet 站点设置为使用 Internet Explorer 11 自动打开。</span><span class="sxs-lookup"><span data-stu-id="400ff-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="400ff-140">使用企业模式意味着你可以继续使用 Microsoft Edge 作为默认浏览器，同时确保你的应用继续在 Internet Explorer 11 上工作。</span><span class="sxs-lookup"><span data-stu-id="400ff-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="400ff-141">有关企业模式站点列表详细信息，请参阅企业 [模式和企业模式站点列表](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。</span><span class="sxs-lookup"><span data-stu-id="400ff-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="400ff-142">你可以指定 https:// 托管企业模式站点列表的内部共享的位置。</span><span class="sxs-lookup"><span data-stu-id="400ff-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="400ff-143">要求</span><span class="sxs-lookup"><span data-stu-id="400ff-143">Requirements</span></span>

<span data-ttu-id="400ff-144">企业模式站点列表文件必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="400ff-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="400ff-145">文件格式 - 满足文件要求的 XML [文件](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="400ff-145">File format - XML file that meets [file requirements](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="400ff-146">文件位置 - 内部 https 位置上的主机文件。</span><span class="sxs-lookup"><span data-stu-id="400ff-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="400ff-147">不允许 - 不允许在内部文件共享上承载，如 *//sharename*</span><span class="sxs-lookup"><span data-stu-id="400ff-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="400ff-148">最佳做法</span><span class="sxs-lookup"><span data-stu-id="400ff-148">Best practices</span></span>

<span data-ttu-id="400ff-149">提供这些最佳做法是帮助客户做出关于现代化 IT 基础结构的决策：</span><span class="sxs-lookup"><span data-stu-id="400ff-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="400ff-150">**选择有限数量的站点** – Microsoft 托管桌面使用 Microsoft Edge 作为首选浏览器，以提高组织的整体安全性和用户的可用性。</span><span class="sxs-lookup"><span data-stu-id="400ff-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="400ff-151">此列表中的大多数网站适用于需要早期版本的浏览器（不包含太多安全功能）的旧 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="400ff-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="400ff-152">**考虑备用** – 考虑不需要较旧浏览器的不同站点或 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="400ff-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="400ff-153">或者，请考虑更新网站，以便它可以使用较新的浏览器。</span><span class="sxs-lookup"><span data-stu-id="400ff-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="400ff-154">较新的浏览器使用最新的技术并帮助提高安全性。</span><span class="sxs-lookup"><span data-stu-id="400ff-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="400ff-155">自定义和部署企业站点模式列表位置</span><span class="sxs-lookup"><span data-stu-id="400ff-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="400ff-156">**添加企业站点模式列表位置**</span><span class="sxs-lookup"><span data-stu-id="400ff-156">**To add an enterprise site mode list location**</span></span>

1. <span data-ttu-id="400ff-157">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="400ff-157">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="400ff-158">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-158">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="400ff-159">在 **"设置**"工作区中，**选择"企业模式站点列表位置"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-159">In **Settings** workspace, select **Enterprise mode site list location**.</span></span> 
4. <span data-ttu-id="400ff-160">输入站点列表的 https 位置。</span><span class="sxs-lookup"><span data-stu-id="400ff-160">Enter the https location for your site list.</span></span> 
5. <span data-ttu-id="400ff-161">选择 **"阶段** 部署"保存更改并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="400ff-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="400ff-162">受信任网站</span><span class="sxs-lookup"><span data-stu-id="400ff-162">Trusted sites</span></span>

<span data-ttu-id="400ff-163">受信任的站点允许您为不同的网站自定义安全区域或网站可以使用的区域。</span><span class="sxs-lookup"><span data-stu-id="400ff-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="400ff-164">安全区域包括：</span><span class="sxs-lookup"><span data-stu-id="400ff-164">Security zones include:</span></span> 
- <span data-ttu-id="400ff-165">区域 1 – 本地 Intranet 区域</span><span class="sxs-lookup"><span data-stu-id="400ff-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="400ff-166">区域 2 – 受信任的站点区域</span><span class="sxs-lookup"><span data-stu-id="400ff-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="400ff-167">区域 3 – Internet 区域</span><span class="sxs-lookup"><span data-stu-id="400ff-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="400ff-168">区域 4 – 受限制的站点区域</span><span class="sxs-lookup"><span data-stu-id="400ff-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="400ff-169">要求</span><span class="sxs-lookup"><span data-stu-id="400ff-169">Requirements</span></span>

<span data-ttu-id="400ff-170">提供每个受信任站点 (Intranet) Internet 站点的完全限定域名和 FQDN。</span><span class="sxs-lookup"><span data-stu-id="400ff-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="400ff-171">自定义和部署受信任网站</span><span class="sxs-lookup"><span data-stu-id="400ff-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="400ff-172">**添加受信任网站**</span><span class="sxs-lookup"><span data-stu-id="400ff-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="400ff-173">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="400ff-173">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="400ff-174">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-174">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="400ff-175">在 **"设置**"工作区中，选择"**受信任的站点**"，然后选择"**添加受信任网站"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-175">In **Settings** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="400ff-176">在 **"添加受信任网站"** 上，输入 URL，选择安全区域，然后选择"**添加受信任网站"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="400ff-177">对要添加的每个受信任网站重复步骤 1-4。</span><span class="sxs-lookup"><span data-stu-id="400ff-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="400ff-178">选择 **"阶段** 部署"保存更改并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="400ff-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="400ff-179">**删除受信任网站**</span><span class="sxs-lookup"><span data-stu-id="400ff-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="400ff-180">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="400ff-180">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="400ff-181">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-181">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="400ff-182">在 **"设置**"工作区中，选择 **"受信任的站点"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-182">In **Settings** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="400ff-183">选择要删除的网站，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="400ff-184">对要删除的每个受信任网站重复步骤 1-4。</span><span class="sxs-lookup"><span data-stu-id="400ff-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="400ff-185">选择 **"阶段** 部署"保存更改并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="400ff-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="400ff-186">代理</span><span class="sxs-lookup"><span data-stu-id="400ff-186">Proxy</span></span>
<span data-ttu-id="400ff-187">你可以管理组织的网络代理设置。</span><span class="sxs-lookup"><span data-stu-id="400ff-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="400ff-188">添加代理服务器和端口号，然后添加代理站点例外。</span><span class="sxs-lookup"><span data-stu-id="400ff-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="400ff-189">Microsoft 托管桌面包括服务运行所需的一组默认代理例外。</span><span class="sxs-lookup"><span data-stu-id="400ff-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="400ff-190">默认排除列表只能由 Microsoft 托管桌面服务修改。</span><span class="sxs-lookup"><span data-stu-id="400ff-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="400ff-191">有关详细信息，请参阅 [Microsoft 托管桌面的网络配置](../get-ready/network.md)。</span><span class="sxs-lookup"><span data-stu-id="400ff-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="400ff-192">添加到 Microsoft 托管桌面门户中的代理网站异常将添加到 Microsoft 托管桌面服务中包含的默认代理例外。</span><span class="sxs-lookup"><span data-stu-id="400ff-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="400ff-193">更新默认代理例外列表始终比客户部署优先。</span><span class="sxs-lookup"><span data-stu-id="400ff-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="400ff-194">这意味着，如果存在默认代理例外列表的部署，则暂存在部署将暂停。</span><span class="sxs-lookup"><span data-stu-id="400ff-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="400ff-195">要求</span><span class="sxs-lookup"><span data-stu-id="400ff-195">Requirements</span></span>

<span data-ttu-id="400ff-196">对于代理服务器和代理站点例外，必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="400ff-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="400ff-197">必须是有效的服务器地址和端口号</span><span class="sxs-lookup"><span data-stu-id="400ff-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="400ff-198">URL 必须是有效的 http 站点</span><span class="sxs-lookup"><span data-stu-id="400ff-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="400ff-199">自定义和部署代理</span><span class="sxs-lookup"><span data-stu-id="400ff-199">Customize and deploy proxies</span></span>

<span data-ttu-id="400ff-200">**添加单个代理站点异常**</span><span class="sxs-lookup"><span data-stu-id="400ff-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="400ff-201">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="400ff-201">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="400ff-202">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-202">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="400ff-203">在 **"设置"** 工作区中，选择"代理 **"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-203">In **Settings** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="400ff-204">输入 **代理服务器的地址** 和 **端口** 号，然后选择添加 **代理例外**。</span><span class="sxs-lookup"><span data-stu-id="400ff-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="400ff-205">输入有效 http 站点的 URL，然后选择"**添加代理异常"。**</span><span class="sxs-lookup"><span data-stu-id="400ff-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="400ff-206">对要添加的每个受信任网站重复步骤 1-5。</span><span class="sxs-lookup"><span data-stu-id="400ff-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="400ff-207">选择 **"阶段** 部署"保存更改并将其部署到测试组。</span><span class="sxs-lookup"><span data-stu-id="400ff-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="400ff-208">其他资源</span><span class="sxs-lookup"><span data-stu-id="400ff-208">Additional resources</span></span>
- [<span data-ttu-id="400ff-209">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="400ff-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="400ff-210">部署可配置设置</span><span class="sxs-lookup"><span data-stu-id="400ff-210">Deploy configurable settings</span></span>](config-setting-deploy.md)