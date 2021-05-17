---
title: 在 SharePoint Online 中延迟加载图像和 JavaScript
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
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
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: 了解如何通过使用 JavaScript 延迟加载图像和非必需 JavaScript 来减少 SharePoint Online 页面的加载时间。
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919160"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="21a5a-103">在 SharePoint Online 中延迟加载图像和 JavaScript</span><span class="sxs-lookup"><span data-stu-id="21a5a-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="21a5a-104">本文介绍如何通过使用 JavaScript 延迟加载图像，以及等到页面加载后加载非必要的 JavaScript 来减少 SharePoint Online 页面的加载时间。</span><span class="sxs-lookup"><span data-stu-id="21a5a-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="21a5a-105">图像可能会对 SharePoint Online 上的页面加载速度产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="21a5a-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="21a5a-106">默认情况下，大多数现代 Internet 浏览器在加载 HTML 页面时预取图像。</span><span class="sxs-lookup"><span data-stu-id="21a5a-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="21a5a-107">如果图像在屏幕上不可见，直到用户向下滚动，这可能会导致页面加载速度不必要地变慢。</span><span class="sxs-lookup"><span data-stu-id="21a5a-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="21a5a-108">图像可以阻止浏览器加载页面的可见部分。</span><span class="sxs-lookup"><span data-stu-id="21a5a-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="21a5a-109">若要解决此问题，可以先使用 JavaScript 跳过加载图像。</span><span class="sxs-lookup"><span data-stu-id="21a5a-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="21a5a-110">此外，加载非必要的 JavaScript 也会减慢页面下载SharePoint速度。</span><span class="sxs-lookup"><span data-stu-id="21a5a-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="21a5a-111">本主题介绍一些可用于在 SharePoint Online 中通过 JavaScript 改进页面加载SharePoint的方法。</span><span class="sxs-lookup"><span data-stu-id="21a5a-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="21a5a-112">通过使用 JavaScript 延迟 SharePoint Online 页面中的图像加载，改进页面加载时间</span><span class="sxs-lookup"><span data-stu-id="21a5a-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="21a5a-113">可以使用 JavaScript 阻止 Web 浏览器预取图像。</span><span class="sxs-lookup"><span data-stu-id="21a5a-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="21a5a-114">这将加快文档呈现的总体速度。</span><span class="sxs-lookup"><span data-stu-id="21a5a-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="21a5a-115">为此，请从 标记中删除 src 属性的值，并将其替换为数据属性中文件的路径，例如 \<img\> ：data-src。</span><span class="sxs-lookup"><span data-stu-id="21a5a-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="21a5a-116">例如：</span><span class="sxs-lookup"><span data-stu-id="21a5a-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="21a5a-117">通过使用此方法，浏览器不会立即下载图像。</span><span class="sxs-lookup"><span data-stu-id="21a5a-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="21a5a-118">如果图像已位于视口中，JavaScript 会通知浏览器从 data 属性检索 URL 并将其作为 src 属性的值插入。</span><span class="sxs-lookup"><span data-stu-id="21a5a-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="21a5a-119">图像仅在用户滚动并进入视图时加载。</span><span class="sxs-lookup"><span data-stu-id="21a5a-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="21a5a-120">若要实现所有这些功能，你需要使用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="21a5a-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="21a5a-121">在文本文件中，定义 **isElementInViewport ()** 函数以检查元素是否位于用户可见的浏览器部分。</span><span class="sxs-lookup"><span data-stu-id="21a5a-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

<span data-ttu-id="21a5a-122">接下来，在 **loadItemsInView ()** 函数中，使用 **isElementInViewport ()** 对象。</span><span class="sxs-lookup"><span data-stu-id="21a5a-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="21a5a-123">**loadItemsInView ()** 函数将加载具有 data-src 属性的值的所有图像（如果它们位于用户可见的浏览器部分）。</span><span class="sxs-lookup"><span data-stu-id="21a5a-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="21a5a-124">将以下函数添加到文本文件：</span><span class="sxs-lookup"><span data-stu-id="21a5a-124">Add the following function to the text file:</span></span>
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

<span data-ttu-id="21a5a-125">最后，从 **window.onscroll** () 调用 **loadItemsInView** () ，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="21a5a-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="21a5a-126">这可确保视口中任何图像在用户需要时加载，而不是之前加载。</span><span class="sxs-lookup"><span data-stu-id="21a5a-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="21a5a-127">将以下内容添加到文本文件：</span><span class="sxs-lookup"><span data-stu-id="21a5a-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="21a5a-128">For SharePoint Online， you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span><span class="sxs-lookup"><span data-stu-id="21a5a-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="21a5a-129">这是因为窗口事件被重写，以确保功能区仍附加到页面顶部。</span><span class="sxs-lookup"><span data-stu-id="21a5a-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="21a5a-130">将文本文件另存为扩展名为 .js JavaScript 文件，delayLoadImages.js。</span><span class="sxs-lookup"><span data-stu-id="21a5a-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="21a5a-131">编写完文件delayLoadImages.js，您可以将文件内容添加到 SharePoint Online 中的母版页。</span><span class="sxs-lookup"><span data-stu-id="21a5a-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="21a5a-132">为此，在母版页中添加指向页眉的脚本链接。</span><span class="sxs-lookup"><span data-stu-id="21a5a-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="21a5a-133">在母版页中发布后，JavaScript 将应用于 SharePoint Online 网站中使用该母版页布局的所有页面。</span><span class="sxs-lookup"><span data-stu-id="21a5a-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="21a5a-134">或者，如果你希望仅在网站的一个页面上使用它，请使用脚本编辑器Web 部件 JavaScript 嵌入页面。</span><span class="sxs-lookup"><span data-stu-id="21a5a-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="21a5a-135">有关详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="21a5a-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="21a5a-136">如何：向 SharePoint 2013 中的网站应用母版页</span><span class="sxs-lookup"><span data-stu-id="21a5a-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [<span data-ttu-id="21a5a-137">如何：在 SharePoint 2013 中创建页面布局</span><span class="sxs-lookup"><span data-stu-id="21a5a-137">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="21a5a-138">示例：从 delayLoadImages.js Online 中的母版页引用 JavaScript SharePoint文件</span><span class="sxs-lookup"><span data-stu-id="21a5a-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="21a5a-139">为此，还需要在母版页中引用 jQuery。</span><span class="sxs-lookup"><span data-stu-id="21a5a-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="21a5a-140">在下面的示例中，在初始页面加载中，可以看到仅加载了一个图像，但页面上还有多个图像。</span><span class="sxs-lookup"><span data-stu-id="21a5a-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![显示在页面上加载一个图像的屏幕截图](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="21a5a-142">以下屏幕截图显示了滚动到视图后下载的其余图像。</span><span class="sxs-lookup"><span data-stu-id="21a5a-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![显示在页面上加载多个图像的屏幕截图](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="21a5a-144">使用 JavaScript 延迟图像加载是提高性能的有效技术;但是，如果技术应用于公共网站，则搜索引擎将无法按对常规格式的图像进行爬网的方式来爬网图像。</span><span class="sxs-lookup"><span data-stu-id="21a5a-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="21a5a-145">这可能会影响搜索引擎的排名，因为图像本身的元数据在页面加载之前并不存在。</span><span class="sxs-lookup"><span data-stu-id="21a5a-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="21a5a-146">搜索引擎爬网程序仅读取 HTML，因此不会将图像视为页面上的内容。</span><span class="sxs-lookup"><span data-stu-id="21a5a-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="21a5a-147">图像是用于在搜索结果中对页面进行排名的因素之一。</span><span class="sxs-lookup"><span data-stu-id="21a5a-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="21a5a-148">解决此问题的方法之一是为图像使用介绍性文本。</span><span class="sxs-lookup"><span data-stu-id="21a5a-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="21a5a-149">GitHub示例：注入 JavaScript 以提高性能</span><span class="sxs-lookup"><span data-stu-id="21a5a-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="21a5a-150">不要错过有关[JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759)注入的文章和代码示例，GitHub。</span><span class="sxs-lookup"><span data-stu-id="21a5a-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21a5a-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21a5a-151">See also</span></span>

[<span data-ttu-id="21a5a-152">Office 2013 和 Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="21a5a-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="21a5a-153">如何：向 SharePoint 2013 中的网站应用母版页</span><span class="sxs-lookup"><span data-stu-id="21a5a-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[<span data-ttu-id="21a5a-154">如何：在 SharePoint 2013 中创建页面布局</span><span class="sxs-lookup"><span data-stu-id="21a5a-154">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)