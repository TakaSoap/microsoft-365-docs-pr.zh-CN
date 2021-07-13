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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 收集创建 DNS 记录所需的值/信息，以将域连接到 Microsoft 365 订阅。
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393879"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="7f68c-103">收集创建 DNS 记录所需的信息</span><span class="sxs-lookup"><span data-stu-id="7f68c-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="7f68c-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="7f68c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="7f68c-105">步骤 1：查找 TXT 记录值并验证</span><span class="sxs-lookup"><span data-stu-id="7f68c-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7f68c-106">In the Microsoft 365 管理中心， go to the **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span><span class="sxs-lookup"><span data-stu-id="7f68c-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7f68c-107">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7f68c-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7f68c-108">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7f68c-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7f68c-109">在"**域**"页面上，选择你的域，然后选择"**开始设置"。**</span><span class="sxs-lookup"><span data-stu-id="7f68c-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="7f68c-110">你将返回域设置向导，查看需要添加的特定值。</span><span class="sxs-lookup"><span data-stu-id="7f68c-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="7f68c-111">在"**域验证"** 页上，**选择"将 TXT** 记录添加到域的 DNS 记录"，然后选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f68c-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="7f68c-112">复制显示的 **TXT** 值。</span><span class="sxs-lookup"><span data-stu-id="7f68c-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="7f68c-113">它如下所示 **：MS=msXXXXXXXX**。</span><span class="sxs-lookup"><span data-stu-id="7f68c-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="7f68c-114">转到 ["添加 DNS 记录"以连接域](create-dns-records-at-any-dns-hosting-provider.md)，然后按照步骤在 DNS 主机的网站上添加记录。</span><span class="sxs-lookup"><span data-stu-id="7f68c-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="7f68c-115">按照在 DNS 主机上 (TXT 记录或 MX 记录) 的步骤操作，然后重新在Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7f68c-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="7f68c-116">在 DNS 主机 (域) 后，从 DNS 主机中删除 TXT 记录或 MX Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7f68c-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="7f68c-117">步骤 2：查找电子邮件等的 MX 记录值</span><span class="sxs-lookup"><span data-stu-id="7f68c-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7f68c-118">In the Microsoft 365 管理中心， go to the **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span><span class="sxs-lookup"><span data-stu-id="7f68c-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="7f68c-119">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7f68c-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7f68c-120">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7f68c-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7f68c-121">在" **域**"页面上，选择你的域。</span><span class="sxs-lookup"><span data-stu-id="7f68c-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="7f68c-122">选择 **"管理 DNS"，** 选择 **"更多选项**  >  **""添加你自己的 DNS"，** 然后选择"继续"以查看要添加的 DNS 记录。 </span><span class="sxs-lookup"><span data-stu-id="7f68c-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="7f68c-123">更改 DNS 主机时，需要保持此信息可用，以便复制粘贴这些值。</span><span class="sxs-lookup"><span data-stu-id="7f68c-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="7f68c-124">页面上列出的 DNS 记录组取决于" **域用途**"下列出的选项。</span><span class="sxs-lookup"><span data-stu-id="7f68c-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="7f68c-125">转到 ["添加 DNS 记录"以连接域](create-dns-records-at-any-dns-hosting-provider.md)，然后按照步骤在 DNS 主机的网站上添加记录。</span><span class="sxs-lookup"><span data-stu-id="7f68c-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="7f68c-126">按照在您的 DNS 主机上创建记录的步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="7f68c-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="7f68c-127">相关内容</span><span class="sxs-lookup"><span data-stu-id="7f68c-127">Related content</span></span>

<span data-ttu-id="7f68c-128">[域常见问题解答](../setup/domains-faq.yml)（文章）</span><span class="sxs-lookup"><span data-stu-id="7f68c-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="7f68c-129">[查找并修复添加域或 DNS 记录之后出现的问题](find-and-fix-issues.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="7f68c-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="7f68c-130">[管理域](index.yml)（链接页）</span><span class="sxs-lookup"><span data-stu-id="7f68c-130">[Manage domains](index.yml) (link page)</span></span>