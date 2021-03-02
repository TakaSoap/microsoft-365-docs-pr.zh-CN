---
title: MSOID 的 Office 365 CNAME 记录有何用途？
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 深入了解 Office 365 中的"MSOID"CNAME 记录，该记录将你引导至针对身份验证过程的最佳服务器，以便你获得更快的响应。
monikerRange: o365-21vianet
ms.openlocfilehash: aea04391768993c40978d94b50817244cd77405c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655480"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="65dbd-103">MSOID 的 Office 365 CNAME 记录有什么用途？</span><span class="sxs-lookup"><span data-stu-id="65dbd-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="65dbd-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="65dbd-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="65dbd-105">以下仅适用于由世纪互联运营的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="65dbd-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="65dbd-p101">你可能很想知道为什么需要在 Office 365 中添加"MSOID"CNAME 记录。 这是必须为所有自定义域添加的记录（无论你使用何种订阅）。 为什么需要它？ 这有一点技术上的原因，但本质上，这使你可定向到最好的服务器以进行某些身份验证过程，因此你可获得更快的响应。</span><span class="sxs-lookup"><span data-stu-id="65dbd-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="65dbd-p102">技术详细信息：当你运行与 Office 365 配合使用的客户端应用程序时，例如 Skype for Business Online、Outlook、Windows PowerShell 或 Microsoft Azure Active Directory 同步工具，你的凭据必须经过身份验证。Office 365 使用 CNAME 记录指向你所在位置的正确身份验证终结点，从而确保快速身份验证响应时间。</span><span class="sxs-lookup"><span data-stu-id="65dbd-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="65dbd-p103">如果你的域缺少此 CNAME 记录，这些应用程序将使用美国的默认身份验证终结点，这意味着身份验证可能较慢。如果未正确配置此 CNAME 记录，例如，如果在" **指向地址**"中输入有误，这些应用程序将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="65dbd-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="65dbd-114">**如果由 Office 365 管理域的 DNS 记录，** Office 365 为您设置此 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="65dbd-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="65dbd-115">**如果你正在 DNS 主机处管理你的域的 DNS 记录，** 则可以通过 [按照适合你的 DNS 主机的说明](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)自己创建此记录。</span><span class="sxs-lookup"><span data-stu-id="65dbd-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>
  
<span data-ttu-id="65dbd-116">如果你正在规划 Office 365 部署，并且希望了解有关可能需要添加或更新的所有 DNS 记录，请阅读 [参考：Office 365 应用程序的外部域名系统记录](https://go.microsoft.com/fwlink/?LinkId=579013)。</span><span class="sxs-lookup"><span data-stu-id="65dbd-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).</span></span>
  

