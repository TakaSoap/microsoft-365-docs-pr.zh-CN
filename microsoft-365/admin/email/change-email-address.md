---
title: 将电子邮件地址更改为使用您的自定义域
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
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '将您的初始电子邮件地址更改为友好的电子邮件地址，如 tom@fourthcoffee.com。 若要执行此操作，您需要购买域名，并将其添加到 Office 365。 '
ms.openlocfilehash: 1c3c77f9626cdf292e0fb9400070cef3df05a9d6
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115966"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="14e92-104">将电子邮件地址更改为使用您的自定义域</span><span class="sxs-lookup"><span data-stu-id="14e92-104">Change your email address to use your custom domain</span></span>

 <span data-ttu-id="14e92-105">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="14e92-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="14e92-p102">Office 365 中您的初始电子邮件地址包括 .onmicrosoft.com，例如 tom@fourthcoffee.onmicrosoft.com。 您可以将其更改为更易于记忆的地址（如 tom@fourthcoffee.com）。 您首先需要您自己的域名，例如 fourthcoffee.com。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。</span><span class="sxs-lookup"><span data-stu-id="14e92-p102">Your initial email address in Office 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com. You can change it to a friendlier address like tom@fourthcoffee.com. You'll need your own domain name, like fourthcoffee.com first. If you already have one, great! If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="14e92-111">Office 365 德国的初始电子邮件地址包括 onmicrosoft.de，如 tom@fourthcoffee.onmicrosoft.de。</span><span class="sxs-lookup"><span data-stu-id="14e92-111">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="14e92-112">您可以将其更改为更友好的地址，如 tom@fourthcoffee.de。</span><span class="sxs-lookup"><span data-stu-id="14e92-112">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="14e92-113">你将需要自己的域名，如 fourthcoffee.de。</span><span class="sxs-lookup"><span data-stu-id="14e92-113">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="14e92-114">如果您已有一个，太好了！</span><span class="sxs-lookup"><span data-stu-id="14e92-114">If you already have one, great!</span></span> <span data-ttu-id="14e92-115">如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。</span><span class="sxs-lookup"><span data-stu-id="14e92-115">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="14e92-116">由世纪互联运营的 Office 365 中的初始电子邮件地址包括 partner.onmschina.cn，如 tom@fourthcoffee.partner.onmschina.cn。</span><span class="sxs-lookup"><span data-stu-id="14e92-116">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="14e92-117">您可以将其更改为更友好的地址，如 tom@fourthcoffee.cn。</span><span class="sxs-lookup"><span data-stu-id="14e92-117">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="14e92-118">你将需要自己的域名，如 fourthcoffee.cn。</span><span class="sxs-lookup"><span data-stu-id="14e92-118">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="14e92-119">如果您已有一个，太好了！</span><span class="sxs-lookup"><span data-stu-id="14e92-119">If you already have one, great!</span></span> <span data-ttu-id="14e92-120">如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。</span><span class="sxs-lookup"><span data-stu-id="14e92-120">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="14e92-p105">当你在安装期间通过更新域的 MX 记录将域的电子邮件更改为传送到 Office 365 时，所有发送到该域的电子邮件都将开始传送到 Office 365。在更改 MX 记录前，请确保你已在 Office 365 中添加用户并为每个在你的域中有电子邮件的人创建邮箱。不想将你的域中每个人的电子邮件移到 Office 365？你可以采取步骤，[改为仅使用几个电子邮件地址来试点 Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)。</span><span class="sxs-lookup"><span data-stu-id="14e92-p105">When you change your domain's email to come to Office 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Office 365. Make sure you've added users and created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record. Don't want to move email for everyone on your domain to Office 365? You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="14e92-125">使用 Microsoft 365 管理中心将您的电子邮件地址更改为使用您的自定义域</span><span class="sxs-lookup"><span data-stu-id="14e92-125">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="14e92-126">您必须具有全局管理员帐户才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="14e92-126">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="14e92-127">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="14e92-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="14e92-128">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="14e92-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="14e92-129">转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。</span><span class="sxs-lookup"><span data-stu-id="14e92-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="14e92-130">转到 "**安装** > **域**" 页。</span><span class="sxs-lookup"><span data-stu-id="14e92-130">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="14e92-131">在 "**域**" 页上，选择 "**添加域**"。</span><span class="sxs-lookup"><span data-stu-id="14e92-131">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="14e92-132">按照相应步骤确认您拥有自己的域和更改您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="14e92-132">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="14e92-133">系统将引导您在 Office 365 中正确设置您的域。</span><span class="sxs-lookup"><span data-stu-id="14e92-133">You'll be guided to get everything set up correctly with your domain in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="14e92-134">如果未使用 Exchange 许可证，则不能使用域从 Office 365 租户发送或接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="14e92-134">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Office 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="14e92-135">相关文章</span><span class="sxs-lookup"><span data-stu-id="14e92-135">Related articles</span></span>

[<span data-ttu-id="14e92-136">使用 Office 365 购买自定义域</span><span class="sxs-lookup"><span data-stu-id="14e92-136">Buy a custom domain using Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
