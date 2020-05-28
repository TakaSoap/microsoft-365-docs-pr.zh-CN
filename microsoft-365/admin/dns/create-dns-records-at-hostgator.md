---
title: 在 Hostgator 处为 Microsoft 创建 DNS 记录
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 了解如何验证您的域，并在 Hostgator for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 8adfc4b6154dad0da7dd2fe037c73fcfc4f84d58
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400433"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a><span data-ttu-id="551dd-103">在 Hostgator 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="551dd-103">Create DNS records at Hostgator for Microsoft</span></span>

 <span data-ttu-id="551dd-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="551dd-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="551dd-105">如果 Hostgator 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="551dd-106">您必须先执行第一个 procedurebelow，将[您的域指向您的托管帐户](#point-your-domain-to-your-hosting-account)，然后再使用本文中的任何其他过程添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="551dd-107">在 Hostgator 中进行所有这些更改后，您的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="551dd-107">After you make all of these changes at Hostgator, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="551dd-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="551dd-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="551dd-109">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="551dd-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="551dd-110">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="551dd-111">将你的域指向你的托管帐户</span><span class="sxs-lookup"><span data-stu-id="551dd-111">Point your domain to your hosting account</span></span>
<span data-ttu-id="551dd-112"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="551dd-112"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="551dd-113">在执行本文中的任何其他过程之前，必须执行此过程。</span><span class="sxs-lookup"><span data-stu-id="551dd-113">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="551dd-114">请按以下步骤将域与托管帐户关联。</span><span class="sxs-lookup"><span data-stu-id="551dd-114">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="551dd-115">若要开始，请使用[此链接](https://portal.hostgator.com/)转到 Hostgator 上的 "域管理" 页面。</span><span class="sxs-lookup"><span data-stu-id="551dd-115">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/).</span></span> <span data-ttu-id="551dd-116">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="551dd-116">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="551dd-117">选择左侧的 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-117">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="551dd-118">在 "**管理域**" 页上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="551dd-118">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="551dd-119">在左侧的弹出菜单中，选择 "**名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-119">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="551dd-120">在您的域的 "**名称服务器**" 页上，在 "**自动将此域指向我的托管帐户**" 下拉列表中，选择与您的域关联的主机帐户。</span><span class="sxs-lookup"><span data-stu-id="551dd-120">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="551dd-121">选择 "**保存名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-121">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="551dd-122">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="551dd-122">Add a TXT record for verification</span></span>
<span data-ttu-id="551dd-123"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="551dd-123"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="551dd-124">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="551dd-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="551dd-p103">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="551dd-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="551dd-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="551dd-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="551dd-p105">若要开始，请转到您在 Hostgator 上的 cPanel 页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="551dd-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="551dd-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="551dd-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="551dd-132">您的 cPanel 地址应如下所示： https://YourSiteAddress:secure-port-number 。</span><span class="sxs-lookup"><span data-stu-id="551dd-132">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="551dd-133">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="551dd-133">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="551dd-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="551dd-135">若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-135">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="551dd-136">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-136">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="551dd-137">在 "**高级区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="551dd-137">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="551dd-138">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="551dd-138">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="551dd-139">**名称**</span><span class="sxs-lookup"><span data-stu-id="551dd-139">**Name**</span></span> <br/> |<span data-ttu-id="551dd-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="551dd-140">**TTL**</span></span> <br/> |<span data-ttu-id="551dd-141">**类型**</span><span class="sxs-lookup"><span data-stu-id="551dd-141">**Type**</span></span> <br/> |<span data-ttu-id="551dd-142">**TXT 数据**</span><span class="sxs-lookup"><span data-stu-id="551dd-142">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="551dd-143">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-143">Use your  *domain_name*.</span></span> <span data-ttu-id="551dd-144">（例如，fourthcoffee.com.)。</span><span class="sxs-lookup"><span data-stu-id="551dd-144">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-145">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="551dd-145">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-146">1 </span><span class="sxs-lookup"><span data-stu-id="551dd-146">1</span></span>  <br/> |<span data-ttu-id="551dd-147">TXT</span><span class="sxs-lookup"><span data-stu-id="551dd-147">TXT</span></span>  <br/> |<span data-ttu-id="551dd-148">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="551dd-148">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="551dd-149">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="551dd-149">**Note:** This is an example.</span></span> <span data-ttu-id="551dd-150">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="551dd-150">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="551dd-151">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="551dd-151">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="551dd-152">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-152">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="551dd-153">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="551dd-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="551dd-154">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="551dd-155">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="551dd-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="551dd-156">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="551dd-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="551dd-157">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="551dd-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="551dd-158">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="551dd-158">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="551dd-159">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="551dd-159">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="551dd-160">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="551dd-160">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="551dd-161">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="551dd-161">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="551dd-162">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-162">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="551dd-163">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="551dd-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="551dd-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="551dd-164"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="551dd-165">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="551dd-165">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="551dd-166">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-166">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="551dd-167">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="551dd-167">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="551dd-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="551dd-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="551dd-169">您的 cPanel 地址应如下所示： https://YourSiteAddress:secure-port-number 。</span><span class="sxs-lookup"><span data-stu-id="551dd-169">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="551dd-170">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="551dd-170">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="551dd-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="551dd-172">若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-172">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="551dd-173">在 "**控制面板**" 页上的 "**电子邮件**" 区域中，选择 " **MX 条目**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-173">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="551dd-174">在 "**电子邮件路由**" 区域中，选择 "**远程邮件交换器**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-174">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="551dd-175">选择 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-175">Select **Change**.</span></span>
  
5. <span data-ttu-id="551dd-176">在 "**添加新记录**" 区域中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="551dd-176">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="551dd-177">**Priority**</span><span class="sxs-lookup"><span data-stu-id="551dd-177">**Priority**</span></span>|<span data-ttu-id="551dd-178">**目标**</span><span class="sxs-lookup"><span data-stu-id="551dd-178">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="551dd-179">0</span><span class="sxs-lookup"><span data-stu-id="551dd-179">0</span></span>  <br/> <span data-ttu-id="551dd-180">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="551dd-180">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="551dd-181">*\<domain-key\>*。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="551dd-181">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="551dd-182">**注意：**\< *domain-key*  \>从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="551dd-182">**Note:** Get your \< *domain-key*  \> from your Microsoft account.</span></span>  [<span data-ttu-id="551dd-183">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="551dd-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="551dd-184">选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-184">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="551dd-185">如果 " **Mx 记录**" 一节中有任何其他 MX 记录，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="551dd-185">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="551dd-186">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="551dd-186">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="551dd-187"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="551dd-187"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="551dd-188">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="551dd-188">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="551dd-189">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-189">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="551dd-190">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="551dd-190">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="551dd-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="551dd-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="551dd-192">您的 cPanel 地址应如下所示： https://YourSiteAddress:secure-port-number 。</span><span class="sxs-lookup"><span data-stu-id="551dd-192">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="551dd-193">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="551dd-193">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="551dd-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="551dd-195">若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-195">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="551dd-196">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-196">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="551dd-197">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="551dd-197">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="551dd-198">在 "**高级区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="551dd-198">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="551dd-199">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="551dd-199">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="551dd-200">**名称**</span><span class="sxs-lookup"><span data-stu-id="551dd-200">**Name**</span></span>|<span data-ttu-id="551dd-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="551dd-201">**TTL**</span></span>|<span data-ttu-id="551dd-202">**类型**</span><span class="sxs-lookup"><span data-stu-id="551dd-202">**Type**</span></span>|<span data-ttu-id="551dd-203">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="551dd-203">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="551dd-204">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="551dd-204">autodiscover.</span></span> <span data-ttu-id="551dd-205">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-205">*domain_name*.</span></span> <span data-ttu-id="551dd-206">（例如，autodiscover.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="551dd-206">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="551dd-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-208">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-208">3600</span></span>  <br/> |<span data-ttu-id="551dd-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="551dd-209">CNAME</span></span>  <br/> |<span data-ttu-id="551dd-210">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="551dd-210">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="551dd-211">sip.</span><span class="sxs-lookup"><span data-stu-id="551dd-211">sip.</span></span> <span data-ttu-id="551dd-212">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-212">*domain_name*.</span></span> <span data-ttu-id="551dd-213">（例如，sip.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="551dd-213">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="551dd-214">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-215">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-215">3600</span></span>  <br/> |<span data-ttu-id="551dd-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="551dd-216">CNAME</span></span>  <br/> |<span data-ttu-id="551dd-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="551dd-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="551dd-218">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="551dd-218">lyncdiscover.</span></span> <span data-ttu-id="551dd-219">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-219">*domain_name*.</span></span> <span data-ttu-id="551dd-220">（例如，lyncdiscover.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="551dd-220">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-221">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="551dd-221">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-222">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-222">3600</span></span>  <br/> |<span data-ttu-id="551dd-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="551dd-223">CNAME</span></span>  <br/> |<span data-ttu-id="551dd-224">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="551dd-224">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="551dd-225">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="551dd-225">enterpriseregistration.</span></span> <span data-ttu-id="551dd-226">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-226">*domain_name*.</span></span> <span data-ttu-id="551dd-227">（例如，enterpriseregistration.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="551dd-227">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-228">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="551dd-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-229">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-229">3600</span></span>  <br/> |<span data-ttu-id="551dd-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="551dd-230">CNAME</span></span>  <br/> |<span data-ttu-id="551dd-231">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="551dd-231">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="551dd-232">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="551dd-232">enterpriseenrollment.</span></span> <span data-ttu-id="551dd-233">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-233">*domain_name*.</span></span> <span data-ttu-id="551dd-234">（例如，enterpriseregistration.fourthcoffee.com。）</span><span class="sxs-lookup"><span data-stu-id="551dd-234">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="551dd-235">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-236">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-236">3600</span></span>  <br/> |<span data-ttu-id="551dd-237">CNAME</span><span class="sxs-lookup"><span data-stu-id="551dd-237">CNAME</span></span>  <br/> |<span data-ttu-id="551dd-238">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="551dd-238">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="551dd-239">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-239">Select **Add Record**.</span></span>

5. <span data-ttu-id="551dd-240">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-240">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="551dd-241">在 "**添加记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-241">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="551dd-242">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-242">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="551dd-243">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="551dd-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="551dd-244"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="551dd-244"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="551dd-245">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="551dd-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="551dd-246">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="551dd-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="551dd-247">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="551dd-248">可以将所需的 Microsoft 值添加到当前记录，这样就拥有包含两组值的单个 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-248">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="551dd-249">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="551dd-249">Need examples?</span></span> <span data-ttu-id="551dd-250">请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="551dd-250">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="551dd-251">若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="551dd-252">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="551dd-252">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="551dd-253">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-253">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="551dd-254">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="551dd-254">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="551dd-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="551dd-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="551dd-256">您的 cPanel 地址应如下所示： https://YourSiteAddress:secure-port-number 。</span><span class="sxs-lookup"><span data-stu-id="551dd-256">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="551dd-257">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="551dd-257">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="551dd-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="551dd-259">若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-259">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="551dd-260">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-260">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="551dd-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="551dd-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="551dd-262">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="551dd-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="551dd-263">**名称**</span><span class="sxs-lookup"><span data-stu-id="551dd-263">**Name**</span></span>|<span data-ttu-id="551dd-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="551dd-264">**TTL**</span></span>|<span data-ttu-id="551dd-265">**类型**</span><span class="sxs-lookup"><span data-stu-id="551dd-265">**Type**</span></span>|<span data-ttu-id="551dd-266">**TXT 数据**</span><span class="sxs-lookup"><span data-stu-id="551dd-266">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="551dd-267">使用您的*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-267">Use your  *domain_name*.</span></span> <span data-ttu-id="551dd-268">（例如，fourthcoffee.com.)。</span><span class="sxs-lookup"><span data-stu-id="551dd-268">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-269">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="551dd-269">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-270">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-270">3600</span></span>  <br/> |<span data-ttu-id="551dd-271">TXT</span><span class="sxs-lookup"><span data-stu-id="551dd-271">TXT</span></span>  <br/> |<span data-ttu-id="551dd-272">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="551dd-272">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="551dd-273">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="551dd-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="551dd-274">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-274">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="551dd-275">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="551dd-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="551dd-276"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="551dd-276"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="551dd-277">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="551dd-277">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="551dd-278">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-278">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="551dd-279">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="551dd-279">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="551dd-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="551dd-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="551dd-281">您的 cPanel 地址应如下所示： https://YourSiteAddress:secure-port-number 。</span><span class="sxs-lookup"><span data-stu-id="551dd-281">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="551dd-282">从 Hostgator 接收的注册电子邮件将指定该地址，并且在**托管**页上也可以使用 cPanel 链接。</span><span class="sxs-lookup"><span data-stu-id="551dd-282">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="551dd-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="551dd-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="551dd-284">若要开始使用 Microsoft，你可以从 Hostgator 或委派中购买托管帐户，[以指向 Microsoft](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-284">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="551dd-285">在 "**控制面板**" 页上的 "**域**" 区域中，选择 "**高级区域编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-285">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="551dd-286">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-286">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="551dd-287">在 "**高级 DNS 区域编辑器**" 页上的 "**添加记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="551dd-287">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="551dd-288">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="551dd-288">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="551dd-289">**名称**</span><span class="sxs-lookup"><span data-stu-id="551dd-289">**Name**</span></span>|<span data-ttu-id="551dd-290">**TTL**</span><span class="sxs-lookup"><span data-stu-id="551dd-290">**TTL**</span></span>|<span data-ttu-id="551dd-291">**类型**</span><span class="sxs-lookup"><span data-stu-id="551dd-291">**Type**</span></span>|<span data-ttu-id="551dd-292">**优先级**</span><span class="sxs-lookup"><span data-stu-id="551dd-292">**Priority**</span></span>|<span data-ttu-id="551dd-293">**权重**</span><span class="sxs-lookup"><span data-stu-id="551dd-293">**Weight**</span></span>|<span data-ttu-id="551dd-294">**端口**</span><span class="sxs-lookup"><span data-stu-id="551dd-294">**Port**</span></span>|<span data-ttu-id="551dd-295">**目标**</span><span class="sxs-lookup"><span data-stu-id="551dd-295">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="551dd-296">_sip _tls。</span><span class="sxs-lookup"><span data-stu-id="551dd-296">_sip._tls.</span></span> <span data-ttu-id="551dd-297">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-297">*domain_name*.</span></span> <span data-ttu-id="551dd-298">（例如 _sip，_tls fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="551dd-298">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-299">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="551dd-299">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-300">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-300">3600</span></span>  <br/> |<span data-ttu-id="551dd-301">SRV</span><span class="sxs-lookup"><span data-stu-id="551dd-301">SRV</span></span>  <br/> |<span data-ttu-id="551dd-302">100</span><span class="sxs-lookup"><span data-stu-id="551dd-302">100</span></span>  <br/> |<span data-ttu-id="551dd-303">1 </span><span class="sxs-lookup"><span data-stu-id="551dd-303">1</span></span>  <br/> |<span data-ttu-id="551dd-304">443</span><span class="sxs-lookup"><span data-stu-id="551dd-304">443</span></span>  <br/> |<span data-ttu-id="551dd-305">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="551dd-305">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="551dd-306">_sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="551dd-306">_sipfederationtls._tcp.</span></span> <span data-ttu-id="551dd-307">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="551dd-307">*domain_name*.</span></span> <span data-ttu-id="551dd-308">（例如 _sipfederationtls，_tcp fourthcoffee）</span><span class="sxs-lookup"><span data-stu-id="551dd-308">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="551dd-309">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="551dd-309">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="551dd-310">3600</span><span class="sxs-lookup"><span data-stu-id="551dd-310">3600</span></span>  <br/> |<span data-ttu-id="551dd-311">SRV</span><span class="sxs-lookup"><span data-stu-id="551dd-311">SRV</span></span>  <br/> |<span data-ttu-id="551dd-312">100</span><span class="sxs-lookup"><span data-stu-id="551dd-312">100</span></span>  <br/> |<span data-ttu-id="551dd-313">1 </span><span class="sxs-lookup"><span data-stu-id="551dd-313">1</span></span>  <br/> |<span data-ttu-id="551dd-314">5061</span><span class="sxs-lookup"><span data-stu-id="551dd-314">5061</span></span>  <br/> |<span data-ttu-id="551dd-315">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="551dd-315">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="551dd-316">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="551dd-316">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="551dd-317">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-317">Add the other SRV record.</span></span>
    
    <span data-ttu-id="551dd-318">在 "**添加记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="551dd-318">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="551dd-319">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="551dd-319">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="551dd-320">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="551dd-320">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="551dd-321">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="551dd-321">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
