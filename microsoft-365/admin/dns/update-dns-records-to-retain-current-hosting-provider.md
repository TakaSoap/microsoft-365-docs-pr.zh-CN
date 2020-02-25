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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 了解如何将流量路由到在 Office 365 外部托管的现有公共网站（如果已将 Office 365 设置为管理自定义域的 DNS 记录）。
ms.openlocfilehash: de95818eea729cb11972faf986c9be40bb6e76da
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251208"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="31b54-103">更新 DNS 记录以便利用当前的托管提供商继续托管网站</span><span class="sxs-lookup"><span data-stu-id="31b54-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="31b54-p101">**如果由您在 DNS 托管提供商处管理您的域的 Office 365 记录** ，您不必担心本主题中的步骤。您的网站将保留在原处，供用户继续正常访问。</span><span class="sxs-lookup"><span data-stu-id="31b54-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="31b54-106">**如果由 Office 365 管理 DNS 记录** ，那么要若将流量路由至在 Office 365 外部托管的现有公共网站，请在将域添加到 Office 365 后，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="31b54-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="31b54-107">更新 Microsoft 365 管理中心中的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="31b54-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="31b54-108">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="31b54-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="31b54-109">在" **域** "页面上的域列表中，选择要用于你的网站的域，然后在管理窗格中选择" **DNS 设置** "。</span><span class="sxs-lookup"><span data-stu-id="31b54-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="31b54-110">选择" **+ 新增自定义记录** "，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="31b54-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="31b54-111">对于" **DNS 类型** "，请输入： **A (地址)**</span><span class="sxs-lookup"><span data-stu-id="31b54-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="31b54-112">对于" **主机名或别名** "，请键入： **@**</span><span class="sxs-lookup"><span data-stu-id="31b54-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="31b54-113">对于" **IP 地址** "，请键入网站当前托管位置的静态 IP 地址（例如 172.16.140.1）。</span><span class="sxs-lookup"><span data-stu-id="31b54-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="31b54-p102">必须是该网站的 *静态*  IP 地址，不能是  *动态*  IP 地址。 请与您的网站的托管网站核实，确保可以获得您的公共网站的静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="31b54-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="31b54-116">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="31b54-116">Select **Save**.</span></span> 
    
<span data-ttu-id="31b54-117">此外，您可以创建 CNAME 记录以帮助客户找到您的网站。</span><span class="sxs-lookup"><span data-stu-id="31b54-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="31b54-118">选择" **+ 新增自定义记录** "，然后输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="31b54-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="31b54-119">对于" **DNS 类型** "，请输入： **CNAME (别名)**</span><span class="sxs-lookup"><span data-stu-id="31b54-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="31b54-120">对于" **主机名或别名** "，请键入： **www**</span><span class="sxs-lookup"><span data-stu-id="31b54-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="31b54-121">对于" **指向地址** "，请键入网站的完全限定域名 (FQDN)，例如 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="31b54-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="31b54-122">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="31b54-122">Select **Save**.</span></span> 
    
<span data-ttu-id="31b54-123">最后，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="31b54-123">Finally, do the following:</span></span>
  
<span data-ttu-id="31b54-124">[将您的域的 NS 记录更新为](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx)指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="31b54-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="31b54-p103">当这些 NS 记录更新为指向 Office 365 时，您的域即已设置成功。电子邮件将路由至 Office 365，到您的网站地址的流量将继续转到您的当前网站主机。</span><span class="sxs-lookup"><span data-stu-id="31b54-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 