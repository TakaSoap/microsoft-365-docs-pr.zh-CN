---
title: 收集创建 DNS 记录所需的信息
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
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 收集创建 DNS 记录所需的值/信息，以将域连接到 Microsoft 365 订阅。
ms.openlocfilehash: e65d53269f5fb8625b12c4eb22f78516818045be
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635722"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="2a25b-103">收集创建 DNS 记录所需的信息</span><span class="sxs-lookup"><span data-stu-id="2a25b-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="2a25b-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="2a25b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="2a25b-105">步骤 1：查找 TXT 记录值并验证</span><span class="sxs-lookup"><span data-stu-id="2a25b-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="2a25b-106">在"Microsoft 365管理中心"中，转到"**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域"</a>页面。</span><span class="sxs-lookup"><span data-stu-id="2a25b-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="2a25b-107">在管理中心，转到"设置 **域** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="2a25b-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2a25b-108">在管理中心，转到"设置 **域** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="2a25b-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="2a25b-109">在"**域**"页面上，选择你的域，然后选择"**开始设置"。**</span><span class="sxs-lookup"><span data-stu-id="2a25b-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="2a25b-110">你将返回域设置向导，查看需要添加的特定值。</span><span class="sxs-lookup"><span data-stu-id="2a25b-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="2a25b-111">在"**验证域"** 页上，选择"**改为添加 TXT 记录"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2a25b-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="2a25b-112">复制显示的 **TXT** 值。</span><span class="sxs-lookup"><span data-stu-id="2a25b-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="2a25b-113">它如下所示 **：MS=msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="2a25b-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="2a25b-114">转到" [在任何 DNS](create-dns-records-at-any-dns-hosting-provider.md)托管提供商处创建 DNS 记录"，然后从注册机构列表中选择 DNS 主机以查看分步说明。</span><span class="sxs-lookup"><span data-stu-id="2a25b-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="2a25b-115">按照在 DNS 主机上 (TXT 记录或 MX 记录) 的步骤操作，然后重新在Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2a25b-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="2a25b-116">在 DNS 主机 (域) 后，从 DNS 主机中删除 TXT 记录或 MX Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2a25b-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="2a25b-117">步骤 2：查找电子邮件等的 MX 记录值</span><span class="sxs-lookup"><span data-stu-id="2a25b-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="2a25b-118">在"Microsoft 365管理中心"中，转到"**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域"</a>页面。</span><span class="sxs-lookup"><span data-stu-id="2a25b-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="2a25b-119">在管理中心，转到"设置 **域** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="2a25b-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="2a25b-120">在管理中心，转到"设置 **域** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="2a25b-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="2a25b-121">在" **域**"页面上，选择你的域。</span><span class="sxs-lookup"><span data-stu-id="2a25b-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="2a25b-122">" **所需的 DNS 设置**"下将显示要添加的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="2a25b-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="2a25b-123">更改 DNS 主机时，需要保持此信息可用，以便复制粘贴这些值。</span><span class="sxs-lookup"><span data-stu-id="2a25b-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="2a25b-124">页面上列出的 DNS 记录组取决于" **域用途**"下列出的选项。</span><span class="sxs-lookup"><span data-stu-id="2a25b-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="2a25b-125">转到"在任何 DNS 托管提供商处创建 [DNS](create-dns-records-at-any-dns-hosting-provider.md)记录"，然后从注册机构列表中选择 DNS 主机，以查看有关在 DNS 主机网站上添加记录的分步说明。</span><span class="sxs-lookup"><span data-stu-id="2a25b-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="2a25b-126">按照在您的 DNS 主机上创建记录的步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="2a25b-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="2a25b-127">相关内容</span><span class="sxs-lookup"><span data-stu-id="2a25b-127">Related content</span></span>

<span data-ttu-id="2a25b-128">[域常见问题 (](../setup/domains-faq.yml) 文章) </span><span class="sxs-lookup"><span data-stu-id="2a25b-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="2a25b-129">[查找并修复在添加域](find-and-fix-issues.md) 或 DNS 记录后 (文章) </span><span class="sxs-lookup"><span data-stu-id="2a25b-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="2a25b-130">[管理域](index.yml)（链接页）</span><span class="sxs-lookup"><span data-stu-id="2a25b-130">[Manage domains](index.yml) (link page)</span></span>