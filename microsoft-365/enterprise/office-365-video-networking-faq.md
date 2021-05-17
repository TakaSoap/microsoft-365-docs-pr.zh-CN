---
title: Office 365视频网络常见问题
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: 查找有关带宽规划、加密以及服务如何利用内容交付网络& CDN 等最常见的 (问题的答案) 。
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921566"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a><span data-ttu-id="94e99-103">Office 365视频网络常见问题</span><span class="sxs-lookup"><span data-stu-id="94e99-103">Office 365 Video networking Frequently Asked Questions</span></span>

<span data-ttu-id="94e99-104">通过Office 365存储库和流式传输服务，在组织中存储和流式传输视频变得简单。</span><span class="sxs-lookup"><span data-stu-id="94e99-104">The Office 365 Video repository and streaming services make storing and streaming videos within your organization simple.</span></span> <span data-ttu-id="94e99-105">有许多有关视频的[Office 365信息](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50);此网络常见问题解答旨在回答有关带宽规划、加密以及服务如何利用内容交付网络和 CDN (最常见的) 。 [](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-105">There's a lot of great [information about Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50); this networking FAQ is designed to answer the most common questions around bandwidth planning, encryption, and how the service leverages [Content Delivery Networks](content-delivery-networks.md) (CDNs).</span></span>
  
<span data-ttu-id="94e99-106">如果你尚未完全了解上传或播放视频时会发生什么情况，请观看我们放在一起的此视频，上传到[Office 365 视频](https://www.youtube.com/watch?v=HXSZ0jYBKlM)时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="94e99-106">If you don't already have a thorough understanding of what happens when a video is uploaded or played back, have a look at this video we put together, [What happens to a video file when uploaded to Office 365 Video](https://www.youtube.com/watch?v=HXSZ0jYBKlM).</span></span>
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a><span data-ttu-id="94e99-107">视频Office 365要求是什么？</span><span class="sxs-lookup"><span data-stu-id="94e99-107">What are the Office 365 Video bandwidth requirements?</span></span>

<span data-ttu-id="94e99-108">有许多受支持的[视频格式](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817)可以上载到Office 365。</span><span class="sxs-lookup"><span data-stu-id="94e99-108">There are a numerous [supported video formats](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) that can be uploaded to Office 365.</span></span> <span data-ttu-id="94e99-109">然后，将每个视频文件编码为具有多个不同视频质量的标准格式进行播放。</span><span class="sxs-lookup"><span data-stu-id="94e99-109">Each video file is then encoded to a standard format with several different video qualities for playback.</span></span> <span data-ttu-id="94e99-110">Office 365视频使用自适应比特率流，根据可用网络带宽和视频播放器的大小选择最佳视频播放质量。</span><span class="sxs-lookup"><span data-stu-id="94e99-110">Office 365 Video uses adaptive bitrate streaming to select the best video playback quality based on the available network bandwidth and size of the video player.</span></span> <span data-ttu-id="94e99-111">为此，播放器最初请求最低播放质量。</span><span class="sxs-lookup"><span data-stu-id="94e99-111">To do this, the player initially requests the lowest playback quality.</span></span> <span data-ttu-id="94e99-112">然后，该服务开始向视频播放器发送 2 秒的视频段。</span><span class="sxs-lookup"><span data-stu-id="94e99-112">The service then begins sending 2-second video segments to the video player.</span></span> <span data-ttu-id="94e99-113">然后，玩家可以基于每个段的传送速度请求较高或更低的播放质量。</span><span class="sxs-lookup"><span data-stu-id="94e99-113">The player can then request higher or lower playback quality based on how quickly each segment is delivered.</span></span>
  
<span data-ttu-id="94e99-114">自适应比特率流在后台执行所有这些操作，同时视频播放中断或缓冲最少。</span><span class="sxs-lookup"><span data-stu-id="94e99-114">The adaptive bitrate streaming does all this in the background while the video plays with the least amount of disruption or buffering.</span></span> <span data-ttu-id="94e99-115">在视频播放期间，视频播放器允许查看器手动覆盖自动播放质量，以选择特定的视频播放质量。</span><span class="sxs-lookup"><span data-stu-id="94e99-115">During video playback, the video player allows the viewer to manually override the automatic playback quality, to select a specific video playback quality.</span></span>
  
<span data-ttu-id="94e99-116">下面是一个快速表，其中概述了每个视频播放质量的网络要求。</span><span class="sxs-lookup"><span data-stu-id="94e99-116">Here's a quick table that outlines the network requirements for each of the video playback qualities.</span></span> <span data-ttu-id="94e99-117">每个人播放视频所需的最小带宽为 802Kbps。</span><span class="sxs-lookup"><span data-stu-id="94e99-117">The minimum bandwidth per person needed to play a video is 802Kbps.</span></span>
  
| <span data-ttu-id="94e99-118">播放质量</span><span class="sxs-lookup"><span data-stu-id="94e99-118">Playback Quality</span></span> | <span data-ttu-id="94e99-119">网络速度</span><span class="sxs-lookup"><span data-stu-id="94e99-119">Network Speed</span></span> |
|:-----|:-----|
|<span data-ttu-id="94e99-120">288p</span><span class="sxs-lookup"><span data-stu-id="94e99-120">288p</span></span>  <br/> |<span data-ttu-id="94e99-121">802Kbps</span><span class="sxs-lookup"><span data-stu-id="94e99-121">802Kbps</span></span>  <br/> |
|<span data-ttu-id="94e99-122">360p</span><span class="sxs-lookup"><span data-stu-id="94e99-122">360p</span></span>  <br/> |<span data-ttu-id="94e99-123">1.2 Mbps</span><span class="sxs-lookup"><span data-stu-id="94e99-123">1.2 Mbps</span></span>  <br/> |
|<span data-ttu-id="94e99-124">576p</span><span class="sxs-lookup"><span data-stu-id="94e99-124">576p</span></span>  <br/> |<span data-ttu-id="94e99-125">2.5 Mbps</span><span class="sxs-lookup"><span data-stu-id="94e99-125">2.5 Mbps</span></span>  <br/> |
|<span data-ttu-id="94e99-126">720p</span><span class="sxs-lookup"><span data-stu-id="94e99-126">720p</span></span>  <br/> |<span data-ttu-id="94e99-127">3.8 Mbps</span><span class="sxs-lookup"><span data-stu-id="94e99-127">3.8 Mbps</span></span>  <br/> |

<span data-ttu-id="94e99-128"> ([返回顶部) ](office-365-video-networking-faq.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-128">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a><span data-ttu-id="94e99-129">内容交付网络 (CDN 如何) 视频播放？</span><span class="sxs-lookup"><span data-stu-id="94e99-129">How do Content Delivery Networks (CDNs) help video playback?</span></span>

<span data-ttu-id="94e99-130">如果同一地理位置内同一组织的多个人员正在流式传输 (视频) ，CDN 将在离该地理区域更近的位置存储这些视频的副本。</span><span class="sxs-lookup"><span data-stu-id="94e99-130">If several people from the same organization within the same geographic location are streaming the same video(s), CDNs will store a copy of these videos in a location closer to that geographic region.</span></span> <span data-ttu-id="94e99-131">存储视频或将视频缓存在最靠近的位置后，每个人都会从离他们最近的位置流式传输视频，而不是从远离的位置流式传输视频。</span><span class="sxs-lookup"><span data-stu-id="94e99-131">With the video stored, or cached at the closest location, each person streams the video from the location closest to them instead of a location further away.</span></span> <span data-ttu-id="94e99-132">Office 365视频Azure 媒体服务 Azure CDN 中缓存的内容以及缓存时间。</span><span class="sxs-lookup"><span data-stu-id="94e99-132">Office 365 Video uses Azure Media Services to manage what is cached in the Azure CDNs, and for how long.</span></span> <span data-ttu-id="94e99-133">Azure 媒体服务可使用任意Azure CDN位置在几天内缓存[](/azure/cdn/cdn-pop-locations)视频片段和清单。</span><span class="sxs-lookup"><span data-stu-id="94e99-133">Azure Media Services can use any of the [Azure CDN locations](/azure/cdn/cdn-pop-locations) to cache video fragments and manifests for a few days.</span></span> <span data-ttu-id="94e99-134">如果组织成员继续观看缓存的视频，他们将留在缓存中。</span><span class="sxs-lookup"><span data-stu-id="94e99-134">If people in your organization continue to watch the cached videos they'll stay in the cache.</span></span> <span data-ttu-id="94e99-135">如果在几天内没有人访问视频，视频最终会从缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="94e99-135">If no one accesses the video for several days, the video will eventually drop be dropped from the cache.</span></span> <span data-ttu-id="94e99-136">下次有人尝试观看视频时，它将再次缓存在距离最近的CDN位置。</span><span class="sxs-lookup"><span data-stu-id="94e99-136">The next time someone attempts to watch the video it's once again cached at the nearest CDN location.</span></span>
  
<span data-ttu-id="94e99-137">当内容缓存在附近的位置时尝试观看视频的每个人CDN视频越靠近，并且在大多数情况下，跃点数较少。</span><span class="sxs-lookup"><span data-stu-id="94e99-137">Everyone who attempts to watch the video while the content is cached at a nearby CDN benefits from the video being closer, and in most cases less hops, away.</span></span> <span data-ttu-id="94e99-138">这将提高视频播放速度;但是，它不会更改播放视频的网络要求。</span><span class="sxs-lookup"><span data-stu-id="94e99-138">This improves video playback speed; however, it doesn't change the network requirement to play the video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94e99-139">在某些情况下，例如达到容量限制，在达到三天之前可能会删除视频。</span><span class="sxs-lookup"><span data-stu-id="94e99-139">There are some circumstances, such as our capacity limit being reached, where the video may be removed before the three days has been reached.</span></span>
  
<span data-ttu-id="94e99-140"> ([返回顶部) ](office-365-video-networking-faq.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-140">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a><span data-ttu-id="94e99-141">能否在本地缓存视频以加快播放速度？</span><span class="sxs-lookup"><span data-stu-id="94e99-141">Can I cache the videos locally for faster playback?</span></span>

<span data-ttu-id="94e99-142">是的。</span><span class="sxs-lookup"><span data-stu-id="94e99-142">Yes.</span></span> <span data-ttu-id="94e99-143">Office 365不会阻止你使用本地 CDN 或缓存代理将视频或其他Office 365内容引入本地网络，以加快访问速度。</span><span class="sxs-lookup"><span data-stu-id="94e99-143">Office 365 won't prevent you from using a local CDN or a caching proxy to bring video or other Office 365 content into your local network for faster access.</span></span> <span data-ttu-id="94e99-144">有几种方法可以网络上实现本地缓存解决方案，最常见的方法是使用在本地缓存内容的代理解决方案。</span><span class="sxs-lookup"><span data-stu-id="94e99-144">There are several ways to implement a local caching solution on your network, the most common method is to use a proxy solution that caches content locally.</span></span> <span data-ttu-id="94e99-145">代理或专用 CDN 缓存视频片段和清单后，通过代理或专用 CDN 路由的文件的未来请求会从本地缓存提取，而不是从 Internet 位置提取。</span><span class="sxs-lookup"><span data-stu-id="94e99-145">Once a proxy or private CDN has cached the video fragments and manifests, future requests for those files that route through the proxy or private CDN are pulled from the local cache and not pulled from an internet location.</span></span> <span data-ttu-id="94e99-146">在规划类似这样的解决方案时，请考虑网络带宽、容量和视频播放并发。</span><span class="sxs-lookup"><span data-stu-id="94e99-146">Consider network bandwidth, capacity, and video playback concurrency during the planning of a solution like this.</span></span>
  
<span data-ttu-id="94e99-147"> ([返回顶部) ](office-365-video-networking-faq.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-147">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-videos-are-encrypted-and-secured"></a><span data-ttu-id="94e99-148">视频是如何加密和安全的？</span><span class="sxs-lookup"><span data-stu-id="94e99-148">How videos are encrypted and secured?</span></span>

<span data-ttu-id="94e99-149">Office 365视频了解保护数据安全和隐私非常重要。</span><span class="sxs-lookup"><span data-stu-id="94e99-149">Office 365 Video knows how important it is to keep your data secure and private.</span></span> <span data-ttu-id="94e99-150">[Microsoft 信任](https://products.office.com/business/office-365-trust-center-welcome) 中心介绍了我们对内容的隐私和安全性的承诺。</span><span class="sxs-lookup"><span data-stu-id="94e99-150">[Microsoft Trust Center](https://products.office.com/business/office-365-trust-center-welcome) describes our commitment to the privacy and security of your content.</span></span> <span data-ttu-id="94e99-151">通过视频播放，速度对于获得良好的体验非常重要;但是，我们不会为了速度而损害你的安全或隐私。</span><span class="sxs-lookup"><span data-stu-id="94e99-151">With video playback, speed is important for a good experience; however, we don't compromise your security or privacy in exchange for speed.</span></span> <span data-ttu-id="94e99-152">下面我们是如何适应速度、安全性和隐私的。</span><span class="sxs-lookup"><span data-stu-id="94e99-152">Here's how we accommodate speed, security and privacy.</span></span>
  
<span data-ttu-id="94e99-153">当你或你组织中的某人上载新视频时，该视频会进行转码、使用 AES-128 加密进行加密，并存储在Azure 媒体服务。</span><span class="sxs-lookup"><span data-stu-id="94e99-153">When you or someone in your organization uploads a new video, that video is transcoded, encrypted with AES-128 encryption, and stored in Azure Media Services.</span></span> <span data-ttu-id="94e99-154">这意味着视频在传输过程中和处于其余时间都进行加密。</span><span class="sxs-lookup"><span data-stu-id="94e99-154">This means the videos are encrypted both in transit and at rest.</span></span>
  
<span data-ttu-id="94e99-155">当贵组织中有人尝试观看新视频时，他们会按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="94e99-155">When someone in your organization attempts to watch a new video, they follow these steps:</span></span>
  
1. <span data-ttu-id="94e99-156">询问 SharePoint Online 是否有权观看视频。</span><span class="sxs-lookup"><span data-stu-id="94e99-156">Ask SharePoint Online if they have permission to view the video.</span></span>

2. <span data-ttu-id="94e99-157">SharePoint联机使用文件权限来确定用户能否观看视频。</span><span class="sxs-lookup"><span data-stu-id="94e99-157">SharePoint Online uses the file permissions to determine if the person can watch the video.</span></span>

3. <span data-ttu-id="94e99-158">如果允许，SharePoint Online 从 Azure 检索令牌，以向视频播放器提供令牌。</span><span class="sxs-lookup"><span data-stu-id="94e99-158">If they're allowed, SharePoint Online retrieves a token from Azure to give to the video player.</span></span>

4. <span data-ttu-id="94e99-159">然后，视频播放器使用该令牌从 Azure 请求解密密钥。</span><span class="sxs-lookup"><span data-stu-id="94e99-159">The video player then uses the token to request the decryption key from Azure.</span></span>

5. <span data-ttu-id="94e99-160">有了解密密钥，视频播放器可以流式传输视频。</span><span class="sxs-lookup"><span data-stu-id="94e99-160">With the decryption key in hand, the video player is able to stream the video.</span></span>

![O365 视频播放](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
<span data-ttu-id="94e99-162"> ([返回顶部) ](office-365-video-networking-faq.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-162">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a><span data-ttu-id="94e99-163">在视频中播放Office 365要求？</span><span class="sxs-lookup"><span data-stu-id="94e99-163">What are the requirements to playback Office 365 Video?</span></span>

<span data-ttu-id="94e99-164">Office 365视频支持的操作系统和 Web 浏览器与 SharePoint 要求中的 Office 365 [Online 要求相同](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45)。</span><span class="sxs-lookup"><span data-stu-id="94e99-164">Office 365 Video supported operating systems and web browsers are the same as the SharePoint Online requirements in [Office 365 system requirements](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45).</span></span> <span data-ttu-id="94e99-165">根据你拥有的操作系统和 Web 浏览器配置，将确定视频播放器的特定需求。</span><span class="sxs-lookup"><span data-stu-id="94e99-165">Depending on which operating system and web browser configuration you have will determine the specific needs of the video player.</span></span> <span data-ttu-id="94e99-166">以下是有关视频播放 [要求的信息](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)。</span><span class="sxs-lookup"><span data-stu-id="94e99-166">Here's more information on [video playback requirements](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).</span></span>
  
<span data-ttu-id="94e99-167"> ([返回顶部) ](office-365-video-networking-faq.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-167">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a><span data-ttu-id="94e99-168">我无法获取Office 365视频，应从何处开始？</span><span class="sxs-lookup"><span data-stu-id="94e99-168">I can't get Office 365 video to work, where should I start?</span></span>

<span data-ttu-id="94e99-169">视频Office 365疑难解答包括网络疑难解答、ISP () ，以及你的Office 365。</span><span class="sxs-lookup"><span data-stu-id="94e99-169">Troubleshooting connectivity to Office 365 Video involves troubleshooting your network, your ISP(s), and your configuration of Office 365.</span></span> <span data-ttu-id="94e99-170">首先需要服务运行状况仪表板。</span><span class="sxs-lookup"><span data-stu-id="94e99-170">The first place to start is the service health dashboard.</span></span> <span data-ttu-id="94e99-171">这将告诉你视频Office 365有问题。</span><span class="sxs-lookup"><span data-stu-id="94e99-171">This will tell you of Office 365 Video is having a problem or not.</span></span> <span data-ttu-id="94e99-172">如果一切看起来都不错，下面提供了一些其他资源来帮助你。</span><span class="sxs-lookup"><span data-stu-id="94e99-172">If everything looks great there, here's some additional resources to help you.</span></span>
  
- <span data-ttu-id="94e99-173">确保你可以连接到视频 视频 所需的[Office 365终结点](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="94e99-173">Make sure you can connect to the [network endpoints required for Office 365 Video](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

- <span data-ttu-id="94e99-174">使用我们的网络疑难解答指南[检查Office 365网络连接](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)。</span><span class="sxs-lookup"><span data-stu-id="94e99-174">Check your network connectivity using our [Office 365 network troubleshooting guide](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).</span></span>

- <span data-ttu-id="94e99-175">有关[在慢速网络上使用 Office 365，请参阅我们的最佳实践](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)。</span><span class="sxs-lookup"><span data-stu-id="94e99-175">See our [best practices for using Office 365 on a slow network](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span>

- <span data-ttu-id="94e99-176">[查找有关视频Office 365的帮助](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)。</span><span class="sxs-lookup"><span data-stu-id="94e99-176">[Find help about Office 365 Video configuration](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).</span></span>

<span data-ttu-id="94e99-177"> ([返回顶部) ](office-365-video-networking-faq.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-177">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="office-365-video-resources"></a><span data-ttu-id="94e99-178">Office 365视频资源</span><span class="sxs-lookup"><span data-stu-id="94e99-178">Office 365 Video resources</span></span>

<span data-ttu-id="94e99-179">下面是一些其他资源，可帮助你成功部署和使用Office 365视频：</span><span class="sxs-lookup"><span data-stu-id="94e99-179">Here's a few other resources to help you successfully deploy and use Office 365 Video:</span></span>
  
[<span data-ttu-id="94e99-180">查找有关视频Office 365的帮助</span><span class="sxs-lookup"><span data-stu-id="94e99-180">Find help about Office 365 Video configuration</span></span>](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[<span data-ttu-id="94e99-181">“了解 Office 365”视频</span><span class="sxs-lookup"><span data-stu-id="94e99-181">Meet Office 365 Video</span></span>](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[<span data-ttu-id="94e99-182">在视频中创建Office 365频道</span><span class="sxs-lookup"><span data-stu-id="94e99-182">Create and manage a channel in Office 365 Video</span></span>](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[<span data-ttu-id="94e99-183">管理 Office 365 视频门户</span><span class="sxs-lookup"><span data-stu-id="94e99-183">Manage your Office 365 Video portal</span></span>](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[<span data-ttu-id="94e99-184">在视频中工作Office 365格式</span><span class="sxs-lookup"><span data-stu-id="94e99-184">Video formats that work in Office 365 Video</span></span>](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
<span data-ttu-id="94e99-185"> ([返回顶部) ](office-365-video-networking-faq.md)</span><span class="sxs-lookup"><span data-stu-id="94e99-185">([Back to top](office-365-video-networking-faq.md))</span></span>
  
<span data-ttu-id="94e99-186">以下是可以用于返回的简短链接：[https://aka.ms/video365networkfaq]()</span><span class="sxs-lookup"><span data-stu-id="94e99-186">Here's a short link you can use to come back: [https://aka.ms/video365networkfaq]()</span></span>