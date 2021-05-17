---
title: SharePoint Online 中的缩小和捆绑
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: 了解如何将缩小和捆绑技术与 Web Essentials 一同使用，以减少 HTTP 请求和在 SharePoint Online 中加载页面所花的时间。
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687625"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="46566-103">SharePoint Online 中的缩小和捆绑</span><span class="sxs-lookup"><span data-stu-id="46566-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="46566-104">本文介绍如何将缩小和捆绑技术与 Web Essentials 一同使用，以减少 HTTP 请求数并减少在 SharePoint Online 中加载页面所花的时间。</span><span class="sxs-lookup"><span data-stu-id="46566-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="46566-105">当您自定义网站时，您最终可以将大量额外文件添加到服务器以支持自定义。</span><span class="sxs-lookup"><span data-stu-id="46566-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="46566-106">添加额外的 JavaScript、CSS 和图像会增加对服务器的 HTTP 请求数，进而增加显示网页的时间。</span><span class="sxs-lookup"><span data-stu-id="46566-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="46566-107">如果你有多个相同类型的文件，可以捆绑这些文件，以更快地下载这些文件。</span><span class="sxs-lookup"><span data-stu-id="46566-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="46566-108">对于 JavaScript 和 CSS 文件，您还可以使用一种称为缩小的方法，通过删除不需要的空格和其他字符来减小文件的总大小。</span><span class="sxs-lookup"><span data-stu-id="46566-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="46566-109">使用 Web Essentials 缩小和捆绑 JavaScript 和 CSS 文件</span><span class="sxs-lookup"><span data-stu-id="46566-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="46566-110">可以使用第三方软件（如 Web Essentials）捆绑 CSS 和 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="46566-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="46566-111">Web Essentials 是一个基于社区的第三方开放源代码项目。</span><span class="sxs-lookup"><span data-stu-id="46566-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="46566-112">该软件是 Visual Studio 2012 和 Visual Studio 2013的扩展，不受 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="46566-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="46566-113">若要下载 Web Essentials，请访问 位于 的网站 [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) 。</span><span class="sxs-lookup"><span data-stu-id="46566-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="46566-114">Web Essentials 提供两种形式的捆绑：</span><span class="sxs-lookup"><span data-stu-id="46566-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="46566-115">.bundle：用于 CSS 和 JavaScript 文件</span><span class="sxs-lookup"><span data-stu-id="46566-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="46566-116">.sprite：适用于 (仅在 Visual Studio 2013) </span><span class="sxs-lookup"><span data-stu-id="46566-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="46566-117">如果您的现有功能具有自定义母版页中引用的一些品牌元素，您可以使用 Web Essentials，例如：</span><span class="sxs-lookup"><span data-stu-id="46566-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![自定义母版页中的品牌元素的屏幕截图](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="46566-119">**在 Web Essentials 中创建 TE000127218 和 CSS 捆绑包**</span><span class="sxs-lookup"><span data-stu-id="46566-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="46566-120">在Visual Studio"解决方案资源管理器"中，选择要包括在捆绑包中的文件。</span><span class="sxs-lookup"><span data-stu-id="46566-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="46566-121">右键单击所选文件，然后从上下文菜单中选择 **"Web Essentials** \> **创建 JavaScript** 捆绑文件"。</span><span class="sxs-lookup"><span data-stu-id="46566-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="46566-122">例如：</span><span class="sxs-lookup"><span data-stu-id="46566-122">For example:</span></span> 
    
    ![显示 Web Essentials 菜单选项的屏幕截图](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="46566-124">查看绑定 JavaScript 和 CSS 文件的结果</span><span class="sxs-lookup"><span data-stu-id="46566-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="46566-125">创建 JavaScript 和 CSS 捆绑包时，Web Essentials 会创建一个 XML 文件，该文件称为食谱文件，用于标识 JavaScript 和 CSS 文件以及其他一些配置信息：</span><span class="sxs-lookup"><span data-stu-id="46566-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![JavaScript 和 CSS 脚本文件的屏幕截图](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="46566-127">此外，如果在捆绑方法中将缩小标志设置为 true，则文件会减小大小并捆绑在一起。</span><span class="sxs-lookup"><span data-stu-id="46566-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="46566-128">这意味着已创建可在母版页中引用的 JavaScript 文件的新缩小版本。</span><span class="sxs-lookup"><span data-stu-id="46566-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![最小化标志设置为 true 的屏幕截图](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="46566-130">从网站加载页面时，可以使用 Web 浏览器（如 Internet Explorer 11）中的开发人员工具查看发送到服务器的请求数以及加载每个文件所需要时间。</span><span class="sxs-lookup"><span data-stu-id="46566-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="46566-131">下图是在缩小之前加载 JavaScript 和 CSS 文件的结果。</span><span class="sxs-lookup"><span data-stu-id="46566-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![显示正在下载的 80 项的屏幕截图](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="46566-133">将 CSS 和 JavaScript 文件捆绑在一起后，丢弃至 74 的请求数，每个文件仅比原始文件稍长一些，以单独下载：</span><span class="sxs-lookup"><span data-stu-id="46566-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![显示正在下载的 74 项的屏幕截图](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="46566-135">捆绑后，JavaScript 捆绑文件将显著从 815KB 减少为 365KB：</span><span class="sxs-lookup"><span data-stu-id="46566-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![显示下载大小减小的屏幕截图](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="46566-137">通过创建图像子画面绑定图像</span><span class="sxs-lookup"><span data-stu-id="46566-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="46566-138">与将 JavaScript 和 CSS 文件捆绑在一起的方式类似，可以将许多小图标和其他常见图像组合到一个较大的子画面工作表中，然后使用 CSS 显示各个图像。</span><span class="sxs-lookup"><span data-stu-id="46566-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="46566-139">用户的 Web 浏览器会下载子画面工作表一次，然后将它缓存在本地计算机上，而不是下载每个单独的图像。</span><span class="sxs-lookup"><span data-stu-id="46566-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="46566-140">这将减少下载次数和到 Web 服务器的往返次数，从而提高页面加载性能。</span><span class="sxs-lookup"><span data-stu-id="46566-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="46566-141">**在 Web Essentials 中创建图像子画面**</span><span class="sxs-lookup"><span data-stu-id="46566-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="46566-142">在Visual Studio"解决方案资源管理器"中，选择要包括在捆绑包中的文件。</span><span class="sxs-lookup"><span data-stu-id="46566-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="46566-143">右键单击所选文件，然后从上下文菜单中选择 **"Web Essentials** \> **创建** 图像子画面"。</span><span class="sxs-lookup"><span data-stu-id="46566-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="46566-144">例如：</span><span class="sxs-lookup"><span data-stu-id="46566-144">For example:</span></span> 
    
    ![显示如何创建图像子画面的屏幕截图](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="46566-146">选择保存子画面文件的位置。</span><span class="sxs-lookup"><span data-stu-id="46566-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="46566-147">.sprite 文件是描述子画面中的设置和文件的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="46566-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="46566-148">下图显示了子画面 PNG 文件及其相应的 .sprite XML 文件的示例。</span><span class="sxs-lookup"><span data-stu-id="46566-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![子画面文件的屏幕截图](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![子画面 XML 文件的屏幕截图](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

