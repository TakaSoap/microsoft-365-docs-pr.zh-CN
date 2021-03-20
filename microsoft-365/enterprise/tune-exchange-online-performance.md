---
title: 优化 Exchange Online 性能
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: 本文包含一些常规提示和指向其他资源的链接，可告诉你如何提高 Exchange Online 的性能。
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909438"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="bc808-103">优化 Exchange Online 性能</span><span class="sxs-lookup"><span data-stu-id="bc808-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="bc808-104">本文包含一些常规提示和指向其他资源的链接，可告诉你如何提高 Exchange Online 的性能，尤其是在迁移前。</span><span class="sxs-lookup"><span data-stu-id="bc808-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="bc808-105">本文是 Office [365 项目的网络规划和性能调整的一](./network-planning-and-performance.md) 部分。</span><span class="sxs-lookup"><span data-stu-id="bc808-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="bc808-106">提高 Exchange Online 性能需要考虑的问题</span><span class="sxs-lookup"><span data-stu-id="bc808-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="bc808-107">若要提高迁移速度并降低组织的 Exchange Online 带宽限制，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="bc808-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="bc808-108">**减小邮箱大小。**</span><span class="sxs-lookup"><span data-stu-id="bc808-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="bc808-109">较小的邮箱大小可提高迁移速度。</span><span class="sxs-lookup"><span data-stu-id="bc808-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="bc808-110">**将邮箱移动功能与 Exchange 混合部署一同使用。**</span><span class="sxs-lookup"><span data-stu-id="bc808-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="bc808-111">使用 Exchange 混合部署，脱机 (采用 的形式。迁移到 Exchange Online) OST 文件，则无需重新下载。</span><span class="sxs-lookup"><span data-stu-id="bc808-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="bc808-112">这大大减少了下载带宽要求。</span><span class="sxs-lookup"><span data-stu-id="bc808-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="bc808-113">**计划邮箱移动在 Internet 流量较低和本地 Exchange 使用较低期间发生。**</span><span class="sxs-lookup"><span data-stu-id="bc808-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="bc808-114">当计划移动时，迁移请求将提交到邮箱复制代理，并且可能不会立即发生。</span><span class="sxs-lookup"><span data-stu-id="bc808-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="bc808-115">**使用 Outlook 网页的精简弹出窗口。**</span><span class="sxs-lookup"><span data-stu-id="bc808-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="bc808-116">精简弹出窗口通过在服务器上呈现某些组件，在 Microsoft Edge 或 Internet Explorer提供较小、占用较少内存的电子邮件版本。</span><span class="sxs-lookup"><span data-stu-id="bc808-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="bc808-117">有关详细信息，请参阅使用斜弹出式 [弹出窗口减少阅读邮件时所使用的内存](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。</span><span class="sxs-lookup"><span data-stu-id="bc808-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="bc808-118">一般建议</span><span class="sxs-lookup"><span data-stu-id="bc808-118">General advice</span></span>

- <span data-ttu-id="bc808-119">请确保 DNS 查找 outlook.office.com 在位置的逻辑输入位置进入 MS-datacenter。</span><span class="sxs-lookup"><span data-stu-id="bc808-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="bc808-120">研究邮箱缓存，然后选择相应的 (选项。</span><span class="sxs-lookup"><span data-stu-id="bc808-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="bc808-121">缓存期、共享邮箱缓存等) 。</span><span class="sxs-lookup"><span data-stu-id="bc808-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="bc808-122">在通过 Internet 之前， (Outlook 数据) 通过 VPN 连接传递到中央办公室服务器。</span><span class="sxs-lookup"><span data-stu-id="bc808-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="bc808-123">请确保邮箱数据符合文件夹和项目数量限制。</span><span class="sxs-lookup"><span data-stu-id="bc808-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="bc808-124">有关 Exchange 迁移性能详细信息，请参阅 [Office 365 迁移性能和最佳做法](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。</span><span class="sxs-lookup"><span data-stu-id="bc808-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
