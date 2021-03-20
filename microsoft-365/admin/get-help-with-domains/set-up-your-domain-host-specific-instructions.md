---
title: 设置域（主机特定的操作说明）
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: 了解如何管理自己的 DNS 记录或让 Microsoft 管理 DNS 记录。
ms.openlocfilehash: f3c3710320c62d20c6a16818cd138c9b686d2781
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915562"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="dcf72-103">设置域（主机特定的操作说明）</span><span class="sxs-lookup"><span data-stu-id="dcf72-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="dcf72-104">若要开始将自定义域 (contoso.com) Microsoft 365，需要验证域并配置域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="dcf72-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="dcf72-105">您可以使用域主机中的管理工具添加和管理 DNS 记录，或让 Microsoft 控制您的域记录，我们将进行设置。</span><span class="sxs-lookup"><span data-stu-id="dcf72-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="dcf72-106">选择下面的域主机，以执行确切步骤。</span><span class="sxs-lookup"><span data-stu-id="dcf72-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="dcf72-107">如果你不确定主机是谁，请参阅查找 [域注册机构](find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="dcf72-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="dcf72-108">让 Microsoft 365 管理 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="dcf72-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="dcf72-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="dcf72-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="dcf72-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="dcf72-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="dcf72-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="dcf72-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="dcf72-112">Google Domains</span><span class="sxs-lookup"><span data-stu-id="dcf72-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="dcf72-113">Hostgator   </span><span class="sxs-lookup"><span data-stu-id="dcf72-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="dcf72-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="dcf72-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="dcf72-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="dcf72-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="dcf72-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="dcf72-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="dcf72-117">或者，了解如何[更改名称服务器以使用任意域注册机构设置 Microsoft 365。](change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="dcf72-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="dcf72-118">管理你自己的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="dcf72-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="dcf72-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="dcf72-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="dcf72-120">Hover</span><span class="sxs-lookup"><span data-stu-id="dcf72-120">Hover</span></span>](./create-dns-records-at-any-dns-hosting-provider.md) |
| [<span data-ttu-id="dcf72-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="dcf72-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="dcf72-122">由 Google (eNom) </span><span class="sxs-lookup"><span data-stu-id="dcf72-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="dcf72-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="dcf72-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="dcf72-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="dcf72-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="dcf72-125">Azure DNS 区域</span><span class="sxs-lookup"><span data-stu-id="dcf72-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="dcf72-126">name.com</span><span class="sxs-lookup"><span data-stu-id="dcf72-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="dcf72-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="dcf72-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="dcf72-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="dcf72-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="dcf72-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="dcf72-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="dcf72-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="dcf72-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="dcf72-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="dcf72-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="dcf72-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="dcf72-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="dcf72-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="dcf72-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="dcf72-134">网络解决方案</span><span class="sxs-lookup"><span data-stu-id="dcf72-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="dcf72-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="dcf72-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="dcf72-136">OVH</span><span class="sxs-lookup"><span data-stu-id="dcf72-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="dcf72-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="dcf72-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="dcf72-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="dcf72-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="dcf72-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="dcf72-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="dcf72-140">注册 Microsoft 365 的 365</span><span class="sxs-lookup"><span data-stu-id="dcf72-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="dcf72-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="dcf72-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="dcf72-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="dcf72-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="dcf72-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="dcf72-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="dcf72-144"> 基于 Windows 的 DNS</span><span class="sxs-lookup"><span data-stu-id="dcf72-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="dcf72-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="dcf72-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="dcf72-146">Wix</span><span class="sxs-lookup"><span data-stu-id="dcf72-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="dcf72-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="dcf72-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="dcf72-148">Yahoo！  小型企业</span><span class="sxs-lookup"><span data-stu-id="dcf72-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="dcf72-149">我需要一般说明，因为我的域主机不在此列表上。 </span><span class="sxs-lookup"><span data-stu-id="dcf72-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
