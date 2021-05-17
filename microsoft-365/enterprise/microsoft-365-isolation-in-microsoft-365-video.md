---
title: Office 365 视频中的租户隔离
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文介绍租户隔离如何在视频中分隔每个租户存储Office 365视频。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fc67b17aa40b3bca9ce6d73ebb7e18319e780339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918926"
---
# <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="ef20f-103">Office 365 视频中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="ef20f-103">Tenant Isolation in Office 365 Video</span></span>

> [!NOTE]
> <span data-ttu-id="ef20f-104">Office 365视频将替换为 Microsoft Stream。</span><span class="sxs-lookup"><span data-stu-id="ef20f-104">Office 365 Video will be replaced by Microsoft Stream.</span></span> <span data-ttu-id="ef20f-105">若要了解有关将智能添加到视频协作的新企业视频服务，并了解当前 Microsoft 365 视频客户的转换计划，请参阅 Office 365 Video transition [to Microsoft Stream overview](/stream/migrate-from-office-365)。</span><span class="sxs-lookup"><span data-stu-id="ef20f-105">To learn more about the new enterprise video service that adds intelligence to video collaboration and learn about the transition plans for current Microsoft 365 Video customers, see [Office 365 Video transition to Microsoft Stream overview](/stream/migrate-from-office-365).</span></span>

## <a name="introduction"></a><span data-ttu-id="ef20f-106">简介</span><span class="sxs-lookup"><span data-stu-id="ef20f-106">Introduction</span></span>

<span data-ttu-id="ef20f-107">Azure 存储用于存储多个 Office 365 服务的数据，包括Office 365和 Sway。</span><span class="sxs-lookup"><span data-stu-id="ef20f-107">Azure Storage is used to store data for multiple Office 365 services, including Office 365 Video and Sway.</span></span> <span data-ttu-id="ef20f-108">Azure 存储 Blob 存储，Blob 存储是高度可扩展的、基于 REST 的云对象存储，用于存储非结构化数据。</span><span class="sxs-lookup"><span data-stu-id="ef20f-108">Azure Storage includes Blob storage, which is a highly-scalable, REST-based, cloud object store that is used for storing unstructured data.</span></span> <span data-ttu-id="ef20f-109">Azure 存储使用简单的访问控制模型;每个 Azure 订阅都可以创建一个或多个存储帐户。</span><span class="sxs-lookup"><span data-stu-id="ef20f-109">Azure Storage uses a simple access control model; each Azure subscription can create one or more Storage Accounts.</span></span> <span data-ttu-id="ef20f-110">每个存储帐户都有一个密钥，用于控制对该帐户中存储的访问。</span><span class="sxs-lookup"><span data-stu-id="ef20f-110">Each Storage Account has a single secret key that is used to control access to all data in that Storage Account.</span></span> <span data-ttu-id="ef20f-111">这支持存储与应用程序关联的典型方案，并且这些应用程序可以完全控制其关联数据;例如，Sway 将内容存储在 Azure 存储。</span><span class="sxs-lookup"><span data-stu-id="ef20f-111">This supports the typical scenario where storage is associated with applications and those applications have full control over their associated data; for example, Sway storing content in Azure Storage.</span></span> <span data-ttu-id="ef20f-112">Sway 的所有客户内容都存储在共享的 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="ef20f-112">All customer content for Sway is stored in shared Azure storage accounts.</span></span> <span data-ttu-id="ef20f-113">每个用户的内容都位于 Azure 存储中单独的 blob 目录树中。</span><span class="sxs-lookup"><span data-stu-id="ef20f-113">Each user's content is in a separate directory tree of blobs in Azure storage.</span></span>

<span data-ttu-id="ef20f-114">管理客户环境访问权限的系统 (例如 Azure 门户、SMAPI 等 ) 隔离在由 Microsoft 运营的 Azure 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="ef20f-114">The systems managing access to customer environments (e.g., the Azure Portal, SMAPI, etc.) are isolated within an Azure application operated by Microsoft.</span></span> <span data-ttu-id="ef20f-115">这会在逻辑上将客户访问基础结构与客户应用程序和存储层分离。</span><span class="sxs-lookup"><span data-stu-id="ef20f-115">This logically separates the customer access infrastructure from the customer applications and storage layer.</span></span>

## <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="ef20f-116">Office 365 视频中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="ef20f-116">Tenant Isolation in Office 365 Video</span></span>

<span data-ttu-id="ef20f-117">[Office 365视频](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)是一个企业门户，可为组织提供高度安全、组织范围的目标，用于发布、共享和发现视频内容。</span><span class="sxs-lookup"><span data-stu-id="ef20f-117">[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is an enterprise portal that provides organizations with a highly secure, organization-wide destination for posting, sharing, and discovering video content.</span></span> <span data-ttu-id="ef20f-118">在Office 365视频中，每个租户的视频在所有位置保持隔离和加密，并且仅对具有组织视频访问权限的经过身份验证的用户可用。</span><span class="sxs-lookup"><span data-stu-id="ef20f-118">In Office 365 Video, each tenant's videos are kept isolated and encrypted in all locations, and are only available to authenticated users that have access and permissions to the organization's videos.</span></span> <span data-ttu-id="ef20f-119">Office 365视频使用技术组合来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="ef20f-119">Office 365 Video uses a combination of technologies to accomplish this:</span></span>

- <span data-ttu-id="ef20f-120">SharePoint联机用于存储视频文件和元数据 (视频标题、说明等) 。</span><span class="sxs-lookup"><span data-stu-id="ef20f-120">SharePoint Online is used for storing the video file and metadata (video title, description, etc.).</span></span> <span data-ttu-id="ef20f-121">它还提供了安全性和合规性层 (身份验证) 搜索功能。</span><span class="sxs-lookup"><span data-stu-id="ef20f-121">It also provides the security and compliance layer (including authentication), and search features.</span></span>
- <span data-ttu-id="ef20f-122">Azure 媒体服务 AES 加密功能和缩略图功能， (代码转换、自适应流式处理、安全) 传输服务。</span><span class="sxs-lookup"><span data-stu-id="ef20f-122">Azure Media Services provides transcoding, adaptive streaming, secure delivery (using AES encryption), and thumbnail features.</span></span>

<span data-ttu-id="ef20f-123">[Azure 媒体服务](https://azure.microsoft.com/services/media-services/)是一种平台即服务产品，用于启用云中的端到端媒体工作流。</span><span class="sxs-lookup"><span data-stu-id="ef20f-123">[Azure Media Services](https://azure.microsoft.com/services/media-services/) is a platform-as-a-service offering for enabling end-to-end media workflows in the cloud.</span></span> <span data-ttu-id="ef20f-124">该平台提供了 REST API，用于通过 PlayReady (进行上载、编码、加密) ，以及通过全球的 Azure 数据中心传递媒体。</span><span class="sxs-lookup"><span data-stu-id="ef20f-124">The platform provides a REST API for uploading, encoding, encrypting (with PlayReady), and delivery of media through Azure datacenters around the world.</span></span>

<span data-ttu-id="ef20f-125">视频的所有Office 365都通过 HTTPS 进行。</span><span class="sxs-lookup"><span data-stu-id="ef20f-125">All uploads for Office 365 Video occur via HTTPS.</span></span> <span data-ttu-id="ef20f-126">上传视频文件时，该文件存储在 SharePoint Online 中，并且文件副本通过加密通道发送到Azure 媒体服务。</span><span class="sxs-lookup"><span data-stu-id="ef20f-126">When a video file is uploaded, it is stored in SharePoint Online, and a copy of the file is sent via an encrypted channel to Azure Media Services.</span></span> <span data-ttu-id="ef20f-127">Azure 媒体服务视频代码转换为多种格式，这些格式针对查看体验 (例如移动、低带宽、高带宽等) 。</span><span class="sxs-lookup"><span data-stu-id="ef20f-127">Azure Media Services transcodes the video into multiple formats that are optimized for viewing experience (e.g., mobile, low-bandwidth, high-bandwidth, etc.).</span></span> <span data-ttu-id="ef20f-128">这些文件以及上载过程中获取的原始文件存储在 Azure Blob 存储中。</span><span class="sxs-lookup"><span data-stu-id="ef20f-128">These files, along with the original file acquired during upload, are stored in Azure Blob storage.</span></span> <span data-ttu-id="ef20f-129">根据 MPEG 通用加密打包算法 (或更早的 PlayReady 版本) ，文件使用 AES 128 进行加密以用于播放，在将文件存储在 Azure Blob 存储中之前，使用 AES 256 存储加密进行加密。</span><span class="sxs-lookup"><span data-stu-id="ef20f-129">The files are encrypted using AES 128 per the MPEG Common Encryption packaging algorithm (or an earlier PlayReady version) for playback, and encrypted using AES 256 storage encryption before being stored in Azure Blob storage.</span></span> <span data-ttu-id="ef20f-130"> (使用 Azure 媒体服务 客户端 SDK，客户可以控制所使用的加密。</span><span class="sxs-lookup"><span data-stu-id="ef20f-130">(Using the Azure Media Services Client SDK, customers can control which encryption is used.</span></span> <span data-ttu-id="ef20f-131">例如，客户可以在将 AES 256 Azure 媒体服务应用 (AES 256) 高价值媒体资产，然后再将其上载到 Azure Blob 存储。) </span><span class="sxs-lookup"><span data-stu-id="ef20f-131">For example, a customer could apply Azure Media Services storage encryption (AES 256) to a high-value media asset before uploading it Azure Blob storage.)</span></span>

<span data-ttu-id="ef20f-132">Azure 媒体服务还会为视频生成缩略图，该视频会随缩略图元数据一SharePoint加密通道传输到联机。</span><span class="sxs-lookup"><span data-stu-id="ef20f-132">Azure Media Services also generates a thumbnail for the video, which it transmits along with thumbnail metadata to SharePoint Online via an encrypted channel.</span></span>