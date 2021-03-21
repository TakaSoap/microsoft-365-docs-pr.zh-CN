---
title: 诊断 SharePoint Online 的性能问题
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: 本文介绍了如何使用开发人员工具诊断 SharePoint Online Internet Explorer常见问题。
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927608"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="369bb-103">诊断 SharePoint Online 的性能问题</span><span class="sxs-lookup"><span data-stu-id="369bb-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="369bb-104">本文介绍了如何使用开发人员工具诊断 SharePoint Online Internet Explorer常见问题。</span><span class="sxs-lookup"><span data-stu-id="369bb-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="369bb-105">有三种不同的方法可以确定 SharePoint Online 网站中的页面存在自定义项的性能问题。</span><span class="sxs-lookup"><span data-stu-id="369bb-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="369bb-106">F12 工具栏网络监视器</span><span class="sxs-lookup"><span data-stu-id="369bb-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="369bb-107">与非自定义基线的比较</span><span class="sxs-lookup"><span data-stu-id="369bb-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="369bb-108">SharePoint Online 响应头指标</span><span class="sxs-lookup"><span data-stu-id="369bb-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="369bb-109">本主题介绍如何使用其中每种方法诊断性能问题。</span><span class="sxs-lookup"><span data-stu-id="369bb-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="369bb-110">找到问题的原因后，您可以使用有关提高 SharePoint 性能的文章（可在 上找到）来寻求解决方案 https://aka.ms/tune 。</span><span class="sxs-lookup"><span data-stu-id="369bb-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="369bb-111">使用 F12 工具栏诊断 SharePoint Online 中的性能</span><span class="sxs-lookup"><span data-stu-id="369bb-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="369bb-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="369bb-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="369bb-113">本文使用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="369bb-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="369bb-114">其他浏览器上的 F12 开发人员工具版本具有类似的功能，尽管它们看起来可能略有不同。</span><span class="sxs-lookup"><span data-stu-id="369bb-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="369bb-115">有关 F12 开发人员工具的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="369bb-115">For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="369bb-116">[F12 工具的新增功能](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="369bb-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="369bb-117">[使用 F12 开发人员工具](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="369bb-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="369bb-118">若要显示开发人员工具，请按 **F12，** 然后单击"Wi-Fi图标：</span><span class="sxs-lookup"><span data-stu-id="369bb-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![F12 开发人员工具 wifi 图标的屏幕截图](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="369bb-120">在" **网络** "选项卡上，按绿色播放按钮加载页面。</span><span class="sxs-lookup"><span data-stu-id="369bb-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="369bb-121">该工具将返回浏览器请求获取页面请求的所有文件。</span><span class="sxs-lookup"><span data-stu-id="369bb-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="369bb-122">以下屏幕截图显示了一个此类列表。</span><span class="sxs-lookup"><span data-stu-id="369bb-122">The following screen shot shows one such list.</span></span>
  
![返回页面请求的文件列表的屏幕截图。](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="369bb-124">还可以在右侧查看文件的下载时间，如本屏幕截图中所示。</span><span class="sxs-lookup"><span data-stu-id="369bb-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![显示从 SharePoint 加载请求页面所需时间的图表](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="369bb-126">这可直观地表示文件加载所用时间。</span><span class="sxs-lookup"><span data-stu-id="369bb-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="369bb-127">绿色线条表示页面何时可供浏览器呈现。</span><span class="sxs-lookup"><span data-stu-id="369bb-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="369bb-128">这可以快速查看可能导致网站页面加载缓慢的不同文件。</span><span class="sxs-lookup"><span data-stu-id="369bb-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="369bb-129">为 SharePoint Online 设置非自定义基线</span><span class="sxs-lookup"><span data-stu-id="369bb-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="369bb-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="369bb-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="369bb-131">确定网站性能较弱点的最佳方法就是，在 SharePoint Online 中设置全新的网站集。</span><span class="sxs-lookup"><span data-stu-id="369bb-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="369bb-132">这样，就可以将网站的所有方面与页面上没有自定义的内容进行比较。</span><span class="sxs-lookup"><span data-stu-id="369bb-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="369bb-133">OneDrive for Business 主页是不可能具有任何自定义的单独网站集的一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="369bb-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="369bb-134">查看 SharePoint 响应头信息</span><span class="sxs-lookup"><span data-stu-id="369bb-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="369bb-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="369bb-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="369bb-136">在 SharePoint Online 中，可以访问在每个文件的响应标头中发送回浏览器的信息。</span><span class="sxs-lookup"><span data-stu-id="369bb-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="369bb-137">用于诊断性能问题的最有用值是 **SPRequestDuration，** 它显示服务器处理请求所花时间。</span><span class="sxs-lookup"><span data-stu-id="369bb-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="369bb-138">这可以帮助确定请求是否非常重且需要大量资源。</span><span class="sxs-lookup"><span data-stu-id="369bb-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="369bb-139">这是对服务器为页面提供服务所完成工作的最佳见解。</span><span class="sxs-lookup"><span data-stu-id="369bb-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="369bb-140">查看 SharePoint 响应头信息</span><span class="sxs-lookup"><span data-stu-id="369bb-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="369bb-141">确保已安装 F12 工具。</span><span class="sxs-lookup"><span data-stu-id="369bb-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="369bb-142">有关下载和安装这些工具详细信息，请参阅 [F12 工具中的新增功能](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="369bb-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="369bb-143">在 F12 工具中的"网络 **"选项卡上** ，按绿色播放按钮加载页面。</span><span class="sxs-lookup"><span data-stu-id="369bb-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="369bb-144">单击该工具返回的 .aspx 文件之一， **然后单击详细信息**。</span><span class="sxs-lookup"><span data-stu-id="369bb-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![显示响应头的详细信息](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="369bb-146">单击 **"响应标头"。**</span><span class="sxs-lookup"><span data-stu-id="369bb-146">Click **Response headers**.</span></span>

    ![显示响应头的 URL 的图表](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="369bb-148">SharePoint Online 中导致性能问题的原因是什么？</span><span class="sxs-lookup"><span data-stu-id="369bb-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="369bb-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="369bb-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="369bb-150">[SharePoint Online](navigation-options-for-sharepoint-online.md)的导航选项一文演示了使用 SPRequestDuration 值确定复杂的结构导航导致页面需要很长时间在服务器上处理的示例。</span><span class="sxs-lookup"><span data-stu-id="369bb-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="369bb-151">通过为没有自定义的 (网站集) ，可以确定加载任何给定文件是否需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="369bb-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="369bb-152">[SharePoint Online 的导航选项](navigation-options-for-sharepoint-online.md)中使用的示例是主 .aspx 文件。</span><span class="sxs-lookup"><span data-stu-id="369bb-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="369bb-153">该文件包含大多数为页面 ASP.NET 运行的代码。</span><span class="sxs-lookup"><span data-stu-id="369bb-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="369bb-154">根据您使用的网站模板，如果自定义主页，这可以是 start.aspx、home.aspx、default.aspx 或其他名称。</span><span class="sxs-lookup"><span data-stu-id="369bb-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="369bb-155">如果此数字远高于基线网站，则说明您的页面中出现导致性能问题的复杂情况。</span><span class="sxs-lookup"><span data-stu-id="369bb-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="369bb-156">在确定了特定于网站的问题后，确定导致性能不佳的原因的推荐方法就是消除所有可能的原因，如页面自定义，然后将它们一个一个地添加回网站。</span><span class="sxs-lookup"><span data-stu-id="369bb-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="369bb-157">删除页面运行良好的足够自定义项后，可以一个一个地添加返回特定自定义项。</span><span class="sxs-lookup"><span data-stu-id="369bb-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="369bb-158">例如，如果你有非常复杂的导航，请尝试将导航更改为不显示子网站，然后检查开发人员工具，看看这是否有所不同。</span><span class="sxs-lookup"><span data-stu-id="369bb-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="369bb-159">或者，如果你有大量内容汇总，请尝试从页面中删除它们，看看这是否改进了操作。</span><span class="sxs-lookup"><span data-stu-id="369bb-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="369bb-160">如果您消除所有可能的原因，并一次添加一个，您可以轻松地确定哪些功能是最大的问题，然后努力找到解决方案。</span><span class="sxs-lookup"><span data-stu-id="369bb-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>