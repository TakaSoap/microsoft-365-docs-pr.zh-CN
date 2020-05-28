---
title: 更新 DNS 记录以便利用当前的托管提供商继续托管网站
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 如果你已将 Microsoft 设置为管理自定义域的 DNS 记录，则了解如何将流量路由到 Microsoft 外部的现有公共网站。
ms.openlocfilehash: c33dd9253da2e8833ec6ae4693be34739b31ea63
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400216"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="edbf1-103">更新 DNS 记录以便利用当前的托管提供商继续托管网站</span><span class="sxs-lookup"><span data-stu-id="edbf1-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="edbf1-104">**如果您在 DNS 托管提供程序中管理您的域的 Microsoft 记录**，则无需担心本主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="edbf1-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="edbf1-105">您的网站将保留在原处，供用户继续正常访问。</span><span class="sxs-lookup"><span data-stu-id="edbf1-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="edbf1-106">**如果 microsoft 管理您的 DNS 记录**，若要将流量路由到 microsoft 外部的现有公共网站，在将您的域添加到 microsoft 之后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="edbf1-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="edbf1-107">更新 Microsoft 365 管理中心中的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="edbf1-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="edbf1-108">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="edbf1-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="edbf1-109">在" **域** "页面上的域列表中，选择要用于你的网站的域，然后在管理窗格中选择" **DNS 设置** "。</span><span class="sxs-lookup"><span data-stu-id="edbf1-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="edbf1-110">选择" **+ 新增自定义记录** "，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="edbf1-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="edbf1-111">对于" **DNS 类型** "，请输入： **A (地址)**</span><span class="sxs-lookup"><span data-stu-id="edbf1-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="edbf1-112">对于" **主机名或别名** "，请键入： **@**</span><span class="sxs-lookup"><span data-stu-id="edbf1-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="edbf1-113">对于" **IP 地址** "，请键入网站当前托管位置的静态 IP 地址（例如 172.16.140.1）。</span><span class="sxs-lookup"><span data-stu-id="edbf1-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="edbf1-p102">必须是该网站的 *静态*  IP 地址，不能是  *动态*  IP 地址。 请与您的网站的托管网站核实，确保可以获得您的公共网站的静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="edbf1-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="edbf1-116">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="edbf1-116">Select **Save**.</span></span> 
    
<span data-ttu-id="edbf1-117">此外，您可以创建 CNAME 记录以帮助客户找到您的网站。</span><span class="sxs-lookup"><span data-stu-id="edbf1-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="edbf1-118">选择" **+ 新增自定义记录** "，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="edbf1-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="edbf1-119">对于" **DNS 类型** "，请输入： **CNAME (别名)**</span><span class="sxs-lookup"><span data-stu-id="edbf1-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="edbf1-120">对于" **主机名或别名** "，请键入： **www**</span><span class="sxs-lookup"><span data-stu-id="edbf1-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="edbf1-121">对于" **指向地址** "，请键入网站的完全限定域名 (FQDN)，例如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="edbf1-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="edbf1-122">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="edbf1-122">Select **Save**.</span></span> 
    
<span data-ttu-id="edbf1-123">最后，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="edbf1-123">Finally, do the following:</span></span>
  
<span data-ttu-id="edbf1-124">将[您的域的 NS 记录更新](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)为指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="edbf1-124">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="edbf1-125">当已将 NS 记录更新为指向 Microsoft 时，您的域将全部设置。</span><span class="sxs-lookup"><span data-stu-id="edbf1-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="edbf1-126">电子邮件将路由到 Microsoft，并且指向你的网站地址的流量将继续转到你的当前网站主机。</span><span class="sxs-lookup"><span data-stu-id="edbf1-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
