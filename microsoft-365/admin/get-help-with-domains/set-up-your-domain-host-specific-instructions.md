---
title: 设置域（主机特定的操作说明）
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: 了解如何管理您自己的 DNS 记录或让 Office 365 管理您的 DNS 记录。
ms.custom: okr_smb
ms.openlocfilehash: 2313aa6c629c76a852e38b4da9093576a3b75d6e
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251140"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="cf92b-103">设置域（主机特定的操作说明）</span><span class="sxs-lookup"><span data-stu-id="cf92b-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="cf92b-104">若要开始在 Office 365 中使用自定义域（contoso.com），您需要验证您的域并配置域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cf92b-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="cf92b-105">您可以使用域主机上的管理工具来添加和管理 DNS 记录，或者为您的域记录提供 Office 365 控制，我们将为您进行设置。</span><span class="sxs-lookup"><span data-stu-id="cf92b-105">You can add and manage DNS records using the administrative tools at your domain host, or give Office 365 control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="cf92b-106">按照下面的具体步骤选择您的域主机。</span><span class="sxs-lookup"><span data-stu-id="cf92b-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="cf92b-107">如果你不确定你的主机是谁，请参阅[查找你的域注册机构](find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="cf92b-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="cf92b-108">允许 Office 365 管理 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cf92b-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="cf92b-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="cf92b-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="cf92b-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="cf92b-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="cf92b-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="cf92b-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="cf92b-112">Google 域</span><span class="sxs-lookup"><span data-stu-id="cf92b-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="cf92b-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="cf92b-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="cf92b-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="cf92b-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="cf92b-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="cf92b-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="cf92b-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="cf92b-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="cf92b-117">或者，了解如何[更改名称服务器以使用任何域注册机构设置 Office 365](change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="cf92b-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="cf92b-118">管理自己的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cf92b-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="cf92b-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="cf92b-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="cf92b-120">悬停</span><span class="sxs-lookup"><span data-stu-id="cf92b-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="cf92b-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="cf92b-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="cf92b-122">由 Google 管理（eNom）</span><span class="sxs-lookup"><span data-stu-id="cf92b-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="cf92b-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="cf92b-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="cf92b-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="cf92b-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="cf92b-125">Azure DNS 区域</span><span class="sxs-lookup"><span data-stu-id="cf92b-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="cf92b-126">name.com</span><span class="sxs-lookup"><span data-stu-id="cf92b-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="cf92b-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="cf92b-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="cf92b-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="cf92b-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="cf92b-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="cf92b-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="cf92b-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="cf92b-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="cf92b-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="cf92b-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="cf92b-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="cf92b-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="cf92b-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="cf92b-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="cf92b-134">网络解决方案</span><span class="sxs-lookup"><span data-stu-id="cf92b-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="cf92b-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="cf92b-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="cf92b-136">OVH</span><span class="sxs-lookup"><span data-stu-id="cf92b-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="cf92b-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="cf92b-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="cf92b-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="cf92b-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="cf92b-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="cf92b-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="cf92b-140">适用于 Office 365 的 Register365</span><span class="sxs-lookup"><span data-stu-id="cf92b-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="cf92b-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="cf92b-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="cf92b-142">web.com</span><span class="sxs-lookup"><span data-stu-id="cf92b-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="cf92b-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="cf92b-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="cf92b-144">基于 Windows 的 DNS</span><span class="sxs-lookup"><span data-stu-id="cf92b-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="cf92b-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="cf92b-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="cf92b-146">Wix</span><span class="sxs-lookup"><span data-stu-id="cf92b-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="cf92b-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="cf92b-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="cf92b-148">Yahoo！  小型企业版</span><span class="sxs-lookup"><span data-stu-id="cf92b-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="cf92b-149">我需要常规说明，因为我的域主机不在此列表中。</span><span class="sxs-lookup"><span data-stu-id="cf92b-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   