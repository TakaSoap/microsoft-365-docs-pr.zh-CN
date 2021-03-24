---
title: 管理 DNS 记录时为 Office 365 创建 DNS 记录
f1.keywords:
- CSH
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
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: '了解如何在管理 DNS 记录时为由世纪网运营的 Office 365 创建 DNS 记录。 '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914350"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="76651-103">管理 DNS 记录时为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="76651-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="76651-104">有关如何为由世纪互联运营的 Office 365 创建 DNS 记录的详细说明，包括邮件路由所需的 MX 记录，请参阅 [在任何 DNS 托管提供者处为 Office 365 创建 DNS 记录](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="76651-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="76651-105">更多选项以及应了解的一些事项：</span><span class="sxs-lookup"><span data-stu-id="76651-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="76651-106">如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="76651-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="76651-107">有关 DNS 记录功能的说明，请参阅 [DNS 基础知识](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="76651-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="76651-108">一些 DNS 托管提供商不允许您创建所有必需的记录类型，这会导致 [托管提供商不支持 SRV、CNAME、TXT 或重定向时出现](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。</span><span class="sxs-lookup"><span data-stu-id="76651-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="76651-109">如果你的提供商不支持 SRV、TXT 或 CNAME 记录，我们建议你 [将你的域](../get-help-with-domains/buy-a-domain-name.md) 转移到支持所有必需的记录类型的 [提供商](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。</span><span class="sxs-lookup"><span data-stu-id="76651-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="76651-110">若要查看哪些 DNS 记录是必需的，并查找要用于每条记录的值，包括用于电子邮件的 MX 记录，请参阅 [收集创建 Office 365 DNS 记录时](../get-help-with-domains/information-for-dns-records.md)。</span><span class="sxs-lookup"><span data-stu-id="76651-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="76651-111">有关 DNS 记录功能的说明，请参阅 [DNS 基础知识](../get-help-with-domains/dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="76651-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
