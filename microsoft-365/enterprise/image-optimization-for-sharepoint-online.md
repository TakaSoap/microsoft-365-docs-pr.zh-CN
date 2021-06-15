---
title: SharePoint经典发布网站的图像优化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
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
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: 了解如何使用再现和子画面来提高 SharePoint Online 经典发布网站上的图像性能。
ms.openlocfilehash: 15885f1d8803332e24e2656a48b796dab28c665f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924571"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a><span data-ttu-id="7e91f-103">SharePoint经典发布网站的图像优化</span><span class="sxs-lookup"><span data-stu-id="7e91f-103">Image optimization for SharePoint Online classic publishing sites</span></span>

<span data-ttu-id="7e91f-104">网页的加载速度取决于呈现页面所需的所有组件的组合大小，包括图像、HTML、JavaScript 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="7e91f-104">The loading speed of a webpage depends on the combined size of all the components required to render the page including images, HTML, JavaScript, and CSS.</span></span> <span data-ttu-id="7e91f-105">图像是使网站更具吸引力的一种很好的方法，但其大小可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="7e91f-105">Images are a great way to make your site more appealing, but their size can affect performance.</span></span> <span data-ttu-id="7e91f-106">通过压缩和调整大小以及使用子画面来优化图像，可以偏移非常大的图像的效果。</span><span class="sxs-lookup"><span data-stu-id="7e91f-106">By optimizing your images with compression and resizing, and using sprites, you can offset the effects of very large images.</span></span> <span data-ttu-id="7e91f-107">通过使用SharePoint形式，可以上载单个大图像，并显示图像的各个部分，以允许重复使用而不是重新加载。</span><span class="sxs-lookup"><span data-stu-id="7e91f-107">Using SharePoint image renditions, you can upload a single large image, and display sections of the image allowing it to be reused rather than reloaded.</span></span>

>[!NOTE]
><span data-ttu-id="7e91f-108">本主题适用于 SharePoint Online 经典发布网站，而不是新式门户网站。</span><span class="sxs-lookup"><span data-stu-id="7e91f-108">This topic applies to SharePoint Online classic publishing sites, not modern portal sites.</span></span> <span data-ttu-id="7e91f-109">有关 SharePoint Online 新式门户网站中的图像优化的信息，请参阅优化[SharePoint Online 新式门户页面中的图像](modern-image-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="7e91f-109">For information about image optimization in SharePoint Online modern portal sites, see [Optimize images in SharePoint Online modern portal pages](modern-image-optimization.md).</span></span>
  
## <a name="using-sprites-to-speed-up-image-loading"></a><span data-ttu-id="7e91f-110">使用子画面加快图像加载速度</span><span class="sxs-lookup"><span data-stu-id="7e91f-110">Using sprites to speed up image loading</span></span>

![spcommon 的屏幕截图](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)

<span data-ttu-id="7e91f-112">图像子画面包含许多较小的图像。</span><span class="sxs-lookup"><span data-stu-id="7e91f-112">An image sprite contains many smaller images.</span></span> <span data-ttu-id="7e91f-113">使用 CSS 可以选择复合图像的一部分，以在具有绝对定位的页面的特定部分上显示。</span><span class="sxs-lookup"><span data-stu-id="7e91f-113">Using CSS you select a part of the composite image to display on a particular part of the page with absolute positioning.</span></span> <span data-ttu-id="7e91f-114">基本上，你可以将单个图像围绕页面移动，而不是加载多个图像，并通过一个小窗口（其中向最终用户显示子画面图像必需的部分）使该图像的一小部分可见。</span><span class="sxs-lookup"><span data-stu-id="7e91f-114">Basically, you move a single image around the page instead of loading multiple images, and make a small part of that image visible through a small window where the required part of the sprite image is shown to the end user.</span></span> <span data-ttu-id="7e91f-115">SharePointOnline 使用子画面在子画面和子画面文件中spcommon.png图标。</span><span class="sxs-lookup"><span data-stu-id="7e91f-115">SharePoint Online uses sprites to display its various icons in the sprite spcommon.png file.</span></span>

<span data-ttu-id="7e91f-116">此处涵盖的内容：</span><span class="sxs-lookup"><span data-stu-id="7e91f-116">What's covered here:</span></span>
- <span data-ttu-id="7e91f-117">图像压缩</span><span class="sxs-lookup"><span data-stu-id="7e91f-117">Image compression</span></span>
- <span data-ttu-id="7e91f-118">图像优化</span><span class="sxs-lookup"><span data-stu-id="7e91f-118">Image optimization</span></span>
- <span data-ttu-id="7e91f-119">SharePoint图像再现</span><span class="sxs-lookup"><span data-stu-id="7e91f-119">SharePoint image renditions</span></span>
   
<span data-ttu-id="7e91f-120">这可提高性能，因为只下载一个映像而不是多个映像，然后缓存并重复使用该映像。</span><span class="sxs-lookup"><span data-stu-id="7e91f-120">This can increase performance because you download only one image instead of several and then cache and reuse that image.</span></span> <span data-ttu-id="7e91f-121">即使图像不保持缓存状态，通过具有单个图像而不是多个图像，此方法也会减少对服务器的 HTTP 请求总数，这将减少页面加载时间。</span><span class="sxs-lookup"><span data-stu-id="7e91f-121">Even if the image does not remain cached, by having a single image instead of multiple images, this method reduces the total number of HTTP requests to the server which will reduce page loading times.</span></span> <span data-ttu-id="7e91f-122">这确实是一种图像绑定形式。</span><span class="sxs-lookup"><span data-stu-id="7e91f-122">This is really a form of image bundling.</span></span> <span data-ttu-id="7e91f-123">如果图像未频繁更改（例如图标）（如上述示例所示SharePoint非常有用。</span><span class="sxs-lookup"><span data-stu-id="7e91f-123">This is a very useful technique if the images are not changing very often, for example, icons, as shown in the SharePoint example provided above.</span></span> <span data-ttu-id="7e91f-124">您可以使用 Web [Essentials（](https://vswebessentials.com/)一个基于社区的第三方开放源代码项目）轻松地在 Microsoft Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="7e91f-124">You can how to use [Web Essentials](https://vswebessentials.com/), a third-party, open-source, community-based project to achieve this easily in Microsoft Visual Studio.</span></span> <span data-ttu-id="7e91f-125">有关详细信息，请参阅[Minification and bundling in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md)。</span><span class="sxs-lookup"><span data-stu-id="7e91f-125">For more information, see [Minification and bundling in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md).</span></span>
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a><span data-ttu-id="7e91f-126">使用图像压缩和优化来加快页面加载速度</span><span class="sxs-lookup"><span data-stu-id="7e91f-126">Using image compression and optimization to speed up page loading</span></span>

<span data-ttu-id="7e91f-127">图像压缩和优化与减少网站上使用的图像的文件大小有关。</span><span class="sxs-lookup"><span data-stu-id="7e91f-127">Image compression and optimization is about reducing the file size of the images you use on your site.</span></span> <span data-ttu-id="7e91f-128">通常，减小图像大小的最佳技术是，将图像大小调整为网站中将查看图像的最大尺寸。</span><span class="sxs-lookup"><span data-stu-id="7e91f-128">Often, the best technique to reduce the size of an image is to resize the image to the maximum dimensions that it will be viewed on the site.</span></span> <span data-ttu-id="7e91f-129">将图像放大到将能查看到的大小没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="7e91f-129">There is no sense in having an image larger than it will ever be viewed.</span></span> <span data-ttu-id="7e91f-130">使用图像编辑器确保图像的尺寸正确无误是减小页面大小的一种快速而简便的方法。</span><span class="sxs-lookup"><span data-stu-id="7e91f-130">Making sure images are of the correct dimensions using an image editor is a quick and easy way to reduce the size of your page.</span></span>
  
<span data-ttu-id="7e91f-131">图像大小合适后，下一步是优化这些图像的压缩。</span><span class="sxs-lookup"><span data-stu-id="7e91f-131">Once images are the right size, the next step is to optimize the compression of these images.</span></span> <span data-ttu-id="7e91f-132">有各种工具可用于压缩和优化，包括照片库和第三方工具。</span><span class="sxs-lookup"><span data-stu-id="7e91f-132">There are various tools available to use for compression and optimization, including Photo Gallery and third-party tools.</span></span> <span data-ttu-id="7e91f-133">压缩的关键是尽可能减小文件大小，而不会为最终用户丢失任何可辨别的质量。</span><span class="sxs-lookup"><span data-stu-id="7e91f-133">The key to compression is to reduce the file size as much as possible without losing any discernible quality for end users.</span></span> <span data-ttu-id="7e91f-134">请确保在高清晰度显示器上测试压缩文件，以确保它们看起来仍然良好。</span><span class="sxs-lookup"><span data-stu-id="7e91f-134">Make sure you test your compressed files on a high-definition display to ensure they will still look good.</span></span>
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a><span data-ttu-id="7e91f-135">使用图像SharePoint加快页面下载速度</span><span class="sxs-lookup"><span data-stu-id="7e91f-135">Speed up page downloads by using SharePoint image renditions</span></span>

<span data-ttu-id="7e91f-136">图像再现是 SharePoint Online 中的一项功能，允许你根据预定义的图像尺寸提供不同版本的图像。</span><span class="sxs-lookup"><span data-stu-id="7e91f-136">Image renditions are a feature in SharePoint Online that allows you to serve up different versions of images based on pre-defined image dimensions.</span></span> <span data-ttu-id="7e91f-137">当存在用户生成的图像内容或网站中的 CSS 修复图像尺寸（如宽度和高度）时，这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="7e91f-137">This is especially important when there is user-generated image content or the image dimensions such as width and height are fixed by the CSS on the site.</span></span> <span data-ttu-id="7e91f-138">即使图像由 CSS 修复，仍然会加载全分辨率图像。</span><span class="sxs-lookup"><span data-stu-id="7e91f-138">Even if an image is fixed by CSS, the full resolution image is still loaded.</span></span> <span data-ttu-id="7e91f-139">在这种情况下，可以使用图像再现来减小文件大小。</span><span class="sxs-lookup"><span data-stu-id="7e91f-139">In this case the file size can be reduced by using image renditions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e91f-140">当启用发布功能时，SharePoint才可用。</span><span class="sxs-lookup"><span data-stu-id="7e91f-140">Renditions are only available for SharePoint when publishing is enabled.</span></span> <span data-ttu-id="7e91f-141">可以在"管理网站 \> 设置"下 \> 设置"管理网站功能SharePoint \> 服务器发布"。</span><span class="sxs-lookup"><span data-stu-id="7e91f-141">You can enable publishing under Settings \> Site Settings \> Manage site features \> SharePoint Server Publishing.</span></span> <span data-ttu-id="7e91f-142">此选项不会以其他方式显示。</span><span class="sxs-lookup"><span data-stu-id="7e91f-142">The option will not appear otherwise.</span></span>
  
<span data-ttu-id="7e91f-143">图像重设大小的工作原理是采用你定义最小的尺寸（宽度或高度）然后调整图像大小，以便根据锁定的纵横比自动调整其他尺寸的大小。</span><span class="sxs-lookup"><span data-stu-id="7e91f-143">The image rendition resizing works by taking the smallest dimension you define, either width or height, and then resizing the image so that the other dimension is automatically resized based on the locked aspect ratio.</span></span> <span data-ttu-id="7e91f-144">默认情况下，它将按其余尺寸从中心裁剪图像。</span><span class="sxs-lookup"><span data-stu-id="7e91f-144">By default, it will crop the image from the center by the remaining dimensions.</span></span> <span data-ttu-id="7e91f-145">例如，如果定义 100px 宽、高 50px 的再现，并且原始图像宽 1000px、高 800px，则大小将调整为 800px，以便 800px 尺寸现在为 50px，并且 1000px 尺寸 (现在为 62.5px) 从图像中心裁剪。</span><span class="sxs-lookup"><span data-stu-id="7e91f-145">For example, if you define a rendition of 100px wide and 50px high and your original image is 1000px wide and 800px high, it will be resized so that the 800px dimension is now 50px and the 1000px dimension (now 62.5px) is cropped from the center of the image.</span></span>
  
<span data-ttu-id="7e91f-146">这些步骤相对简单，但对于图像使用再现，在添加图像之前，SharePoint位于网站中。</span><span class="sxs-lookup"><span data-stu-id="7e91f-146">The steps are relatively simple but for images to use the renditions, the renditions need to be on the SharePoint site before you add the images.</span></span> <span data-ttu-id="7e91f-147">此外，还需要启用 SharePoint Server Publishing Infrastructure (Site Collection Level) 和 SharePoint Server Publishing (Site Level) 功能。</span><span class="sxs-lookup"><span data-stu-id="7e91f-147">In addition, you also need to have the SharePoint Server Publishing Infrastructure (Site Collection Level) and SharePoint Server Publishing (Site Level) features turned on.</span></span>
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a><span data-ttu-id="7e91f-148">添加图像再现以加快页面加载速度</span><span class="sxs-lookup"><span data-stu-id="7e91f-148">Add an image rendition to speed up page loading</span></span>
  
1. <span data-ttu-id="7e91f-149">确认执行此过程的用户帐户至少具有对网站集首要网站的"设计"权限，并且该网站正在发布到网页。</span><span class="sxs-lookup"><span data-stu-id="7e91f-149">Verify that the user account that is performing this procedure has, at minimum, Design permissions to the top-level site of the site collection, and that the site is being published to a webpage.</span></span>

2. <span data-ttu-id="7e91f-150">在 Web 浏览器中，转到发布网站集的顶级网站。</span><span class="sxs-lookup"><span data-stu-id="7e91f-150">In a web browser, go to the top-level site of the publishing site collection.</span></span>

3. <span data-ttu-id="7e91f-151">选择"设置"图标。</span><span class="sxs-lookup"><span data-stu-id="7e91f-151">Choose the **Settings** icon.</span></span>

4. <span data-ttu-id="7e91f-152">在 **"设置"** 页上的"外观"部分，你将看到内置图像再现。</span><span class="sxs-lookup"><span data-stu-id="7e91f-152">On the **Site Settings** page, in the **Look and Feel** section, you will see the built-in image renditions.</span></span>

    <span data-ttu-id="7e91f-153">可以使用开箱即用格式副本，或选择"图像 **再现** "新建一个。</span><span class="sxs-lookup"><span data-stu-id="7e91f-153">You can use the out of the box renditions or choose **Image Renditions** to create a new one.</span></span>

    ![图像再现的屏幕截图](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. <span data-ttu-id="7e91f-155">在“图像呈现形式”页上，选择“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="7e91f-155">On the **Image Renditions** page, choose **Add new item**.</span></span>

    ![添加新项目的屏幕截图](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. <span data-ttu-id="7e91f-157">在"新建图像呈现形式"页上的"名称"框中，为呈现形式输入名称。</span><span class="sxs-lookup"><span data-stu-id="7e91f-157">On the **New Image Rendition** page, in the **Name** box, enter a name for the rendition.</span></span>

7. <span data-ttu-id="7e91f-158">在"宽度"和"高度"文本框中，输入呈现形式的宽度和高度（以像素为单位），然后选择"保存"。</span><span class="sxs-lookup"><span data-stu-id="7e91f-158">In the **Width** and **Height** text boxes, enter the width and height, in pixels, of the rendition, and then choose **Save**.</span></span>

    ![图像再现名称的屏幕截图](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a><span data-ttu-id="7e91f-160">使用图像再现的自定义裁剪</span><span class="sxs-lookup"><span data-stu-id="7e91f-160">Custom cropping with image renditions</span></span>

<span data-ttu-id="7e91f-161">默认情况下，图像呈现形式在图像中心生成。</span><span class="sxs-lookup"><span data-stu-id="7e91f-161">By default, an image rendition is generated from the center of the image.</span></span> <span data-ttu-id="7e91f-162">您可以调整单个图像的图像呈现形式，具体方法是裁剪要使用的图像部分。</span><span class="sxs-lookup"><span data-stu-id="7e91f-162">You can adjust the image rendition for individual images by cropping the portion of the image that you want to use.</span></span> <span data-ttu-id="7e91f-163">可以基于每个再现单独裁剪图像。</span><span class="sxs-lookup"><span data-stu-id="7e91f-163">You can crop the images on an individual basis, per rendition.</span></span> <span data-ttu-id="7e91f-164">裁剪图像通过使用 blob 缓存为每个SharePoint创建图像版本来加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="7e91f-164">Cropping the images speeds up page loading by using SharePoint's blob cache to create a version of the image for each rendition.</span></span> <span data-ttu-id="7e91f-165">这样一来，服务器负载将减少，因为图像仅调整一次大小，然后就可以为最终用户多次提供服务。</span><span class="sxs-lookup"><span data-stu-id="7e91f-165">This way the server load is reduced because the image is only resized once and is then ready to serve to end users multiple times.</span></span> <span data-ttu-id="7e91f-166">若要详细了解如何裁剪图像再现形式，请参阅裁剪[图像再现。](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels)</span><span class="sxs-lookup"><span data-stu-id="7e91f-166">For more information on how to crop an image rendition, see [Crop an image rendition](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels).</span></span>
