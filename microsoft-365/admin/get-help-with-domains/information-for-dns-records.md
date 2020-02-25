---
title: 收集创建 Office 365 DNS 记录所需的信息
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: '了解如何查找创建适用于 Office 365 的 DNS 记录所需的值/信息。 '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251141"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="b45b5-103">收集创建 Office 365 DNS 记录所需的信息</span><span class="sxs-lookup"><span data-stu-id="b45b5-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="b45b5-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="b45b5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="b45b5-105">步骤1：查找 TXT 记录值并验证</span><span class="sxs-lookup"><span data-stu-id="b45b5-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="b45b5-106">在 Microsoft 365 管理中心，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="b45b5-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="b45b5-107">如果使用的是 Office 365 德国，请转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="b45b5-107">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="b45b5-108">如果您正在使用由世纪互联运营的 Office 365，请转到此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="b45b5-108">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b45b5-109">在 "**域**" 页上，选择您的域，然后选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="b45b5-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="b45b5-110">你将返回域设置向导，查看需要添加的特定值。</span><span class="sxs-lookup"><span data-stu-id="b45b5-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="b45b5-111">在 "**验证域**" 页上，选择 "**添加 TXT 记录**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b45b5-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="b45b5-112">复制所示的**TXT 值**。</span><span class="sxs-lookup"><span data-stu-id="b45b5-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="b45b5-113">其外观如下所示： **MS = msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="b45b5-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="b45b5-114">转到 "[在任何 DNS 托管提供程序中创建 dns 记录](create-dns-records-at-any-dns-hosting-provider.md)"，然后从注册机构列表中选择您的 dns 主机，以查看分步说明。</span><span class="sxs-lookup"><span data-stu-id="b45b5-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="b45b5-115">按照在 DNS 主机上创建 TXT 记录（或 MX 记录）的步骤操作，然后返回 Office 365 中验证域。</span><span class="sxs-lookup"><span data-stu-id="b45b5-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="b45b5-116">在 Office 365 中验证域后，从 DNS 主机中删除 TXT 记录（或 MX 记录）。</span><span class="sxs-lookup"><span data-stu-id="b45b5-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="b45b5-117">步骤2：查找电子邮件和其他的 MX 记录值</span><span class="sxs-lookup"><span data-stu-id="b45b5-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="b45b5-118">在 Microsoft 365 管理中心，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="b45b5-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="b45b5-119">如果使用的是 Office 365 德国，请转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="b45b5-119">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="b45b5-120">如果您正在使用由世纪互联运营的 Office 365，请转到此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="b45b5-120">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b45b5-121">在" **域**"页面上，选择你的域。</span><span class="sxs-lookup"><span data-stu-id="b45b5-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="b45b5-122">" **所需的 DNS 设置**"下将显示要添加的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="b45b5-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="b45b5-123">更改 DNS 主机时，需要保持此信息可用，以便复制粘贴这些值。</span><span class="sxs-lookup"><span data-stu-id="b45b5-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="b45b5-124">页面上列出的 DNS 记录组取决于" **域用途**"下列出的选项。</span><span class="sxs-lookup"><span data-stu-id="b45b5-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="b45b5-125">转到 "[在任何 DNS 托管提供程序中创建 dns 记录](create-dns-records-at-any-dns-hosting-provider.md)"，然后从注册机构列表中选择您的 dns 主机，以查看有关在该 DNS 主机的网站上添加记录的分步说明。</span><span class="sxs-lookup"><span data-stu-id="b45b5-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="b45b5-126">按照在您的 DNS 主机上创建记录的步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="b45b5-126">Follow the steps for creating the records at your DNS host.</span></span>
