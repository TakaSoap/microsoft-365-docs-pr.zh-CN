---
title: 收集创建 DNS 记录所需的信息
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: '了解如何查找为 Microsoft 365 创建 DNS 记录所需的值/信息。 '
ms.openlocfilehash: fddd1180f2dd80ffeec2aeec49ed821055dd5f15
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399904"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="3935e-103">收集创建 DNS 记录所需的信息</span><span class="sxs-lookup"><span data-stu-id="3935e-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="3935e-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="3935e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="3935e-105">步骤1：查找 TXT 记录值并验证</span><span class="sxs-lookup"><span data-stu-id="3935e-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3935e-106">在 Microsoft 365 管理中心，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="3935e-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3935e-107">在管理中心中，转到 "**安装** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="3935e-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3935e-108">在管理中心中，转到 "**安装** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="3935e-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="3935e-109">在 "**域**" 页上，选择您的域，然后选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="3935e-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="3935e-110">你将返回域设置向导，查看需要添加的特定值。</span><span class="sxs-lookup"><span data-stu-id="3935e-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="3935e-111">在 "**验证域**" 页上，选择 "**添加 TXT 记录**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3935e-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="3935e-112">复制所示的**TXT 值**。</span><span class="sxs-lookup"><span data-stu-id="3935e-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="3935e-113">其外观如下所示： **MS = msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="3935e-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="3935e-114">转到 "[在任何 DNS 托管提供程序中创建 dns 记录](create-dns-records-at-any-dns-hosting-provider.md)"，然后从注册机构列表中选择您的 dns 主机，以查看分步说明。</span><span class="sxs-lookup"><span data-stu-id="3935e-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="3935e-115">按照在 DNS 主机上创建 TXT 记录（或 MX 记录）的步骤操作，然后验证 Microsoft 365 中的域是否返回。</span><span class="sxs-lookup"><span data-stu-id="3935e-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="3935e-116">在 Microsoft 365 中验证域后，从 DNS 主机中删除 TXT 记录（或 MX 记录）。</span><span class="sxs-lookup"><span data-stu-id="3935e-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="3935e-117">步骤2：查找电子邮件和其他的 MX 记录值</span><span class="sxs-lookup"><span data-stu-id="3935e-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3935e-118">在 Microsoft 365 管理中心，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="3935e-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="3935e-119">在管理中心中，转到 "**安装** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="3935e-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3935e-120">在管理中心中，转到 "**安装** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="3935e-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="3935e-121">在" **域**"页面上，选择你的域。</span><span class="sxs-lookup"><span data-stu-id="3935e-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="3935e-122">" **所需的 DNS 设置**"下将显示要添加的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="3935e-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="3935e-123">更改 DNS 主机时，需要保持此信息可用，以便复制粘贴这些值。</span><span class="sxs-lookup"><span data-stu-id="3935e-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="3935e-124">页面上列出的 DNS 记录组取决于" **域用途**"下列出的选项。</span><span class="sxs-lookup"><span data-stu-id="3935e-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="3935e-125">转到 "[在任何 DNS 托管提供程序中创建 dns 记录](create-dns-records-at-any-dns-hosting-provider.md)"，然后从注册机构列表中选择您的 dns 主机，以查看有关在该 DNS 主机的网站上添加记录的分步说明。</span><span class="sxs-lookup"><span data-stu-id="3935e-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="3935e-126">按照在您的 DNS 主机上创建记录的步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="3935e-126">Follow the steps for creating the records at your DNS host.</span></span>
