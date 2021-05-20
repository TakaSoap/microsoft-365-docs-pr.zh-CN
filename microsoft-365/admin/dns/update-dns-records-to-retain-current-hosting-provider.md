---
title: 更新 DNS 记录以便利用当前的托管提供商继续托管网站
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 了解如何将流量路由到 Microsoft 外部托管的现有公共网站（如果已设置 Microsoft 管理自定义域的 DNS 记录）。
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572133"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="09550-103">更新 DNS 记录以便利用当前的托管提供商继续托管网站</span><span class="sxs-lookup"><span data-stu-id="09550-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="09550-104">**如果在 DNS** 托管提供商中管理域的 Microsoft 记录，则无需担心本主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="09550-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="09550-105">您的网站将保留在原处，供用户继续正常访问。</span><span class="sxs-lookup"><span data-stu-id="09550-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="09550-106">**如果 Microsoft 管理 DNS 记录**，若要将流量路由到在 Microsoft 外部托管的现有公共网站，在将域添加到 Microsoft 后，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="09550-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="09550-107">更新管理中心Microsoft 365 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="09550-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="09550-108">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="09550-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

1. <span data-ttu-id="09550-109">在"**域**"页面上，选择域，然后选择 **"DNS 记录"。**</span><span class="sxs-lookup"><span data-stu-id="09550-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

1. <span data-ttu-id="09550-110">选择 **+ 添加记录** ，然后输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="09550-110">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="09550-111">对于 **类型** 输入 **：A (Address)**</span><span class="sxs-lookup"><span data-stu-id="09550-111">For **type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="09550-112">对于" **主机名或别名** "，请键入： **@**</span><span class="sxs-lookup"><span data-stu-id="09550-112">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="09550-113">对于" **IP 地址** "，请键入网站当前托管位置的静态 IP 地址（例如 172.16.140.1）。</span><span class="sxs-lookup"><span data-stu-id="09550-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="09550-p102">必须是该网站的 *静态*  IP 地址，不能是  *动态*  IP 地址。 请与您的网站的托管网站核实，确保可以获得您的公共网站的静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="09550-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
1. <span data-ttu-id="09550-116">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="09550-116">Select **Save**.</span></span> 
    
<span data-ttu-id="09550-117">此外，您可以创建 CNAME 记录以帮助客户找到您的网站。</span><span class="sxs-lookup"><span data-stu-id="09550-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="09550-118">选择 **+ 添加记录** ，然后输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="09550-118">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="09550-119">对于 **类型** 输入 **：CNAME (别名)**</span><span class="sxs-lookup"><span data-stu-id="09550-119">For **type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="09550-120">对于" **主机名或别名** "，请键入： **www**</span><span class="sxs-lookup"><span data-stu-id="09550-120">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="09550-121">对于" **指向地址** "，请键入网站的完全限定域名 (FQDN)，例如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="09550-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="09550-122">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="09550-122">Select **Save**.</span></span> 
    
<span data-ttu-id="09550-123">最后，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="09550-123">Finally, do the following:</span></span>
  
<span data-ttu-id="09550-124">[将域的 NS 记录更新](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 为指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="09550-124">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="09550-125">当 NS 记录更新为指向 Microsoft 时，域已全部设置。</span><span class="sxs-lookup"><span data-stu-id="09550-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="09550-126">电子邮件将路由到 Microsoft，并且发送到你的网站地址的流量将继续转到你的当前网站主机。</span><span class="sxs-lookup"><span data-stu-id="09550-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
