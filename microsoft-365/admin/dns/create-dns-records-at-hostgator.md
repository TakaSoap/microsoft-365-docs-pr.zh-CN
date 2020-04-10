---
title: 在 Hostgator 上为 Office 365 创建 DNS 记录
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 了解如何在 Hostgator for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: a5a41e5c1eba9d99d1927192472da7746277dd38
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211711"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a><span data-ttu-id="de8a3-103">在 Hostgator 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="de8a3-103">Create DNS records at Hostgator for Office 365</span></span>

 <span data-ttu-id="de8a3-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="de8a3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="de8a3-105">如果 Hostgator 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="de8a3-106">您必须先执行第一个 procedurebelow，将[您的域指向您的托管帐户](#point-your-domain-to-your-hosting-account)，然后再使用本文中的任何其他过程添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="de8a3-107">在 Hostgator 中进行所有这些更改后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="de8a3-107">After you make all of these changes at Hostgator, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="de8a3-108">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="de8a3-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="de8a3-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="de8a3-110">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="de8a3-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="de8a3-111">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="de8a3-112">将你的域指向你的托管帐户</span><span class="sxs-lookup"><span data-stu-id="de8a3-112">Point your domain to your hosting account</span></span>
<span data-ttu-id="de8a3-113"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="de8a3-113"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de8a3-114">在执行本文中的任何其他过程之前，必须执行此过程。</span><span class="sxs-lookup"><span data-stu-id="de8a3-114">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="de8a3-115">请按以下步骤将域与托管帐户关联。</span><span class="sxs-lookup"><span data-stu-id="de8a3-115">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="de8a3-116">若要开始，请使用[此链接](https://portal.hostgator.com/)转到 Hostgator 上的 "域管理" 页面。</span><span class="sxs-lookup"><span data-stu-id="de8a3-116">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/).</span></span> <span data-ttu-id="de8a3-117">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="de8a3-117">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="de8a3-118">选择左侧的 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-118">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="de8a3-119">在 "**管理域**" 页上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="de8a3-119">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="de8a3-120">在左侧的弹出菜单中，选择 "**名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-120">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="de8a3-121">在您的域的 "**名称服务器**" 页上，在 "**自动将此域指向我的托管帐户**" 下拉列表中，选择与您的域关联的主机帐户。</span><span class="sxs-lookup"><span data-stu-id="de8a3-121">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="de8a3-122">选择 "**保存名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-122">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="de8a3-123">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="de8a3-123">Add a TXT record for verification</span></span>
<span data-ttu-id="de8a3-124"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="de8a3-124"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de8a3-125">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="de8a3-125">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="de8a3-p103">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de8a3-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="de8a3-p105">若要开始，请转到您在 Hostgator 上的 cPanel 页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="de8a3-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="de8a3-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="de8a3-133">您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="de8a3-133">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="de8a3-134">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="de8a3-134">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="de8a3-p107">要将一个 cPanel 与您的域关联，需要一个由 Hostgator 托管的帐户。 若要开始使用 Office 365，您可以从 Hostgator 购买托管帐户，或[委派名称服务器指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p107">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="de8a3-137">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-137">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="de8a3-138">在 "**高级区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="de8a3-138">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de8a3-139">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de8a3-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="de8a3-140">**Name**</span></span> <br/> |<span data-ttu-id="de8a3-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de8a3-141">**TTL**</span></span> <br/> |<span data-ttu-id="de8a3-142">**类型**</span><span class="sxs-lookup"><span data-stu-id="de8a3-142">**Type**</span></span> <br/> |<span data-ttu-id="de8a3-143">**TXT 数据**</span><span class="sxs-lookup"><span data-stu-id="de8a3-143">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="de8a3-144">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-144">Use your  *domain_name*.</span></span> <span data-ttu-id="de8a3-145">（例如，fourthcoffee.com.)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-145">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-146">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="de8a3-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-147">1</span><span class="sxs-lookup"><span data-stu-id="de8a3-147">1</span></span>  <br/> |<span data-ttu-id="de8a3-148">TXT</span><span class="sxs-lookup"><span data-stu-id="de8a3-148">TXT</span></span>  <br/> |<span data-ttu-id="de8a3-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="de8a3-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="de8a3-150">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="de8a3-150">**Note:** This is an example.</span></span> <span data-ttu-id="de8a3-151">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="de8a3-151">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="de8a3-152">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="de8a3-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="de8a3-153">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="de8a3-154">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="de8a3-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="de8a3-155">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="de8a3-156">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="de8a3-156">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="de8a3-157">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="de8a3-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="de8a3-158">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="de8a3-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="de8a3-159">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="de8a3-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="de8a3-160">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="de8a3-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="de8a3-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="de8a3-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="de8a3-162">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="de8a3-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="de8a3-163">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="de8a3-164">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="de8a3-164">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="de8a3-165"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="de8a3-165"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de8a3-166">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="de8a3-166">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="de8a3-167">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="de8a3-167">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="de8a3-168">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="de8a3-168">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="de8a3-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="de8a3-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="de8a3-170">您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="de8a3-170">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="de8a3-171">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="de8a3-171">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="de8a3-p113">要将一个 cPanel 与您的域关联，需要一个由 Hostgator 托管的帐户。 若要开始使用 Office 365，您可以从 Hostgator 购买托管帐户，或[委派名称服务器指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p113">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="de8a3-174">在 "**控制面板**" 页上的 "**电子邮件**" 区域中，选择 " **MX 条目**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-174">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="de8a3-175">在 "**电子邮件路由**" 区域中，选择 "**远程邮件交换器**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-175">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="de8a3-176">选择 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-176">Select **Change**.</span></span>
  
5. <span data-ttu-id="de8a3-177">在 "**添加新记录**" 区域中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="de8a3-177">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="de8a3-178">**Priority**</span><span class="sxs-lookup"><span data-stu-id="de8a3-178">**Priority**</span></span>|<span data-ttu-id="de8a3-179">**目标**</span><span class="sxs-lookup"><span data-stu-id="de8a3-179">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="de8a3-180">0</span><span class="sxs-lookup"><span data-stu-id="de8a3-180">0</span></span>  <br/> <span data-ttu-id="de8a3-181">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="de8a3-181">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="de8a3-182">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de8a3-182">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="de8a3-183">**注意：** 从 Office \< 365 帐户中获取你的*域密钥*\> 。  </span><span class="sxs-lookup"><span data-stu-id="de8a3-183">**Note:** Get your \< *domain-key*  \> from your Office 365 account.</span></span>  [<span data-ttu-id="de8a3-184">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="de8a3-184">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="de8a3-185">选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-185">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="de8a3-186">如果 " **Mx 记录**" 一节中有任何其他 MX 记录，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="de8a3-186">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="de8a3-187">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="de8a3-187">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="de8a3-188"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="de8a3-188"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de8a3-189">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="de8a3-189">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="de8a3-190">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="de8a3-190">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="de8a3-191">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="de8a3-191">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="de8a3-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="de8a3-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="de8a3-193">您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="de8a3-193">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="de8a3-194">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="de8a3-194">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="de8a3-p117">要将一个 cPanel 与您的域关联，需要一个由 Hostgator 托管的帐户。 若要开始使用 Office 365，您可以从 Hostgator 购买托管帐户，或[委派名称服务器指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p117">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="de8a3-197">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-197">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="de8a3-198">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="de8a3-198">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="de8a3-199">在 "**高级区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="de8a3-199">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="de8a3-200">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-200">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="de8a3-201">**名称**</span><span class="sxs-lookup"><span data-stu-id="de8a3-201">**Name**</span></span>|<span data-ttu-id="de8a3-202">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de8a3-202">**TTL**</span></span>|<span data-ttu-id="de8a3-203">**类型**</span><span class="sxs-lookup"><span data-stu-id="de8a3-203">**Type**</span></span>|<span data-ttu-id="de8a3-204">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="de8a3-204">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de8a3-205">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="de8a3-205">autodiscover.</span></span> <span data-ttu-id="de8a3-206">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-206">*domain_name*.</span></span> <span data-ttu-id="de8a3-207">（例如，autodiscover.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-207">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="de8a3-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-209">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-209">3600</span></span>  <br/> |<span data-ttu-id="de8a3-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="de8a3-210">CNAME</span></span>  <br/> |<span data-ttu-id="de8a3-211">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de8a3-211">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="de8a3-212">sip.</span><span class="sxs-lookup"><span data-stu-id="de8a3-212">sip.</span></span> <span data-ttu-id="de8a3-213">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-213">*domain_name*.</span></span> <span data-ttu-id="de8a3-214">（例如，sip.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-214">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-215">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="de8a3-215">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-216">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-216">3600</span></span>  <br/> |<span data-ttu-id="de8a3-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="de8a3-217">CNAME</span></span>  <br/> |<span data-ttu-id="de8a3-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de8a3-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de8a3-219">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="de8a3-219">lyncdiscover.</span></span> <span data-ttu-id="de8a3-220">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-220">*domain_name*.</span></span> <span data-ttu-id="de8a3-221">（例如，lyncdiscover.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-221">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="de8a3-222">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-223">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-223">3600</span></span>  <br/> |<span data-ttu-id="de8a3-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="de8a3-224">CNAME</span></span>  <br/> |<span data-ttu-id="de8a3-225">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de8a3-225">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de8a3-226">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="de8a3-226">enterpriseregistration.</span></span> <span data-ttu-id="de8a3-227">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-227">*domain_name*.</span></span> <span data-ttu-id="de8a3-228">（例如，enterpriseregistration.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-228">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-229">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="de8a3-229">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-230">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-230">3600</span></span>  <br/> |<span data-ttu-id="de8a3-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="de8a3-231">CNAME</span></span>  <br/> |<span data-ttu-id="de8a3-232">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="de8a3-232">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="de8a3-233">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="de8a3-233">enterpriseenrollment.</span></span> <span data-ttu-id="de8a3-234">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-234">*domain_name*.</span></span> <span data-ttu-id="de8a3-235">（例如，enterpriseregistration.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-235">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="de8a3-236">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-237">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-237">3600</span></span>  <br/> |<span data-ttu-id="de8a3-238">CNAME</span><span class="sxs-lookup"><span data-stu-id="de8a3-238">CNAME</span></span>  <br/> |<span data-ttu-id="de8a3-239">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="de8a3-239">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="de8a3-240">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-240">Select **Add Record**.</span></span>

5. <span data-ttu-id="de8a3-241">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-241">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="de8a3-242">在 "**添加记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-242">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="de8a3-243">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-243">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="de8a3-244">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="de8a3-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="de8a3-245"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="de8a3-245"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de8a3-246">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="de8a3-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="de8a3-247">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="de8a3-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="de8a3-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="de8a3-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="de8a3-249">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="de8a3-249">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="de8a3-250">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="de8a3-250">Need examples?</span></span> <span data-ttu-id="de8a3-251">请查看 [Office 365 的外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-251">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="de8a3-252">若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-252">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="de8a3-253">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="de8a3-253">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="de8a3-254">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="de8a3-254">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="de8a3-255">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="de8a3-255">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="de8a3-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="de8a3-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="de8a3-257">您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="de8a3-257">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="de8a3-258">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="de8a3-258">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="de8a3-p126">要将一个 cPanel 与您的域关联，需要一个由 Hostgator 托管的帐户。 若要开始使用 Office 365，您可以从 Hostgator 购买托管帐户，或[委派名称服务器指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p126">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="de8a3-261">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-261">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="de8a3-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="de8a3-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de8a3-263">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="de8a3-264">**名称**</span><span class="sxs-lookup"><span data-stu-id="de8a3-264">**Name**</span></span>|<span data-ttu-id="de8a3-265">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de8a3-265">**TTL**</span></span>|<span data-ttu-id="de8a3-266">**类型**</span><span class="sxs-lookup"><span data-stu-id="de8a3-266">**Type**</span></span>|<span data-ttu-id="de8a3-267">**TXT 数据**</span><span class="sxs-lookup"><span data-stu-id="de8a3-267">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de8a3-268">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-268">Use your  *domain_name*.</span></span> <span data-ttu-id="de8a3-269">（例如，fourthcoffee.com.)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-269">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-270">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="de8a3-270">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-271">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-271">3600</span></span>  <br/> |<span data-ttu-id="de8a3-272">TXT</span><span class="sxs-lookup"><span data-stu-id="de8a3-272">TXT</span></span>  <br/> |<span data-ttu-id="de8a3-273">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="de8a3-273">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="de8a3-274">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="de8a3-274">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="de8a3-275">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-275">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="de8a3-276">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="de8a3-276">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="de8a3-277"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="de8a3-277"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de8a3-278">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="de8a3-278">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="de8a3-279">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="de8a3-279">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="de8a3-280">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="de8a3-280">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="de8a3-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="de8a3-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="de8a3-282">您的 cPanel 地址应如下所示https://YourSiteAddress:secure-port-number：。</span><span class="sxs-lookup"><span data-stu-id="de8a3-282">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="de8a3-283">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="de8a3-283">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="de8a3-p130">要将一个 cPanel 与您的域关联，需要一个由 Hostgator 托管的帐户。 若要开始使用 Office 365，您可以从 Hostgator 购买托管帐户，或[委派名称服务器指向 Office 365](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-p130">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="de8a3-286">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-286">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="de8a3-287">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-287">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="de8a3-288">在 "**高级 DNS 区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="de8a3-288">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="de8a3-289">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="de8a3-289">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="de8a3-290">**名称**</span><span class="sxs-lookup"><span data-stu-id="de8a3-290">**Name**</span></span>|<span data-ttu-id="de8a3-291">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de8a3-291">**TTL**</span></span>|<span data-ttu-id="de8a3-292">**类型**</span><span class="sxs-lookup"><span data-stu-id="de8a3-292">**Type**</span></span>|<span data-ttu-id="de8a3-293">**优先级**</span><span class="sxs-lookup"><span data-stu-id="de8a3-293">**Priority**</span></span>|<span data-ttu-id="de8a3-294">**权重**</span><span class="sxs-lookup"><span data-stu-id="de8a3-294">**Weight**</span></span>|<span data-ttu-id="de8a3-295">**端口**</span><span class="sxs-lookup"><span data-stu-id="de8a3-295">**Port**</span></span>|<span data-ttu-id="de8a3-296">**目标**</span><span class="sxs-lookup"><span data-stu-id="de8a3-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de8a3-297">_sip _tls。</span><span class="sxs-lookup"><span data-stu-id="de8a3-297">_sip._tls.</span></span> <span data-ttu-id="de8a3-298">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-298">*domain_name*.</span></span> <span data-ttu-id="de8a3-299">（例如 _sip，_tls fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="de8a3-299">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-300">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="de8a3-300">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-301">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-301">3600</span></span>  <br/> |<span data-ttu-id="de8a3-302">SRV</span><span class="sxs-lookup"><span data-stu-id="de8a3-302">SRV</span></span>  <br/> |<span data-ttu-id="de8a3-303">100</span><span class="sxs-lookup"><span data-stu-id="de8a3-303">100</span></span>  <br/> |<span data-ttu-id="de8a3-304">1</span><span class="sxs-lookup"><span data-stu-id="de8a3-304">1</span></span>  <br/> |<span data-ttu-id="de8a3-305">443</span><span class="sxs-lookup"><span data-stu-id="de8a3-305">443</span></span>  <br/> |<span data-ttu-id="de8a3-306">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de8a3-306">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de8a3-307">_sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="de8a3-307">_sipfederationtls._tcp.</span></span> <span data-ttu-id="de8a3-308">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="de8a3-308">*domain_name*.</span></span> <span data-ttu-id="de8a3-309">（例如 _sipfederationtls，_tcp fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="de8a3-309">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="de8a3-310">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="de8a3-310">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="de8a3-311">3600</span><span class="sxs-lookup"><span data-stu-id="de8a3-311">3600</span></span>  <br/> |<span data-ttu-id="de8a3-312">SRV</span><span class="sxs-lookup"><span data-stu-id="de8a3-312">SRV</span></span>  <br/> |<span data-ttu-id="de8a3-313">100</span><span class="sxs-lookup"><span data-stu-id="de8a3-313">100</span></span>  <br/> |<span data-ttu-id="de8a3-314">1</span><span class="sxs-lookup"><span data-stu-id="de8a3-314">1</span></span>  <br/> |<span data-ttu-id="de8a3-315">5061</span><span class="sxs-lookup"><span data-stu-id="de8a3-315">5061</span></span>  <br/> |<span data-ttu-id="de8a3-316">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de8a3-316">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="de8a3-317">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="de8a3-317">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="de8a3-318">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-318">Add the other SRV record.</span></span>
    
    <span data-ttu-id="de8a3-319">在 "**添加记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="de8a3-319">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="de8a3-320">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="de8a3-320">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="de8a3-321">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="de8a3-321">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="de8a3-322">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="de8a3-322">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
