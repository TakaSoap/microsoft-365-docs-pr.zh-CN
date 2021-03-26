---
title: 在 Hostgator 为 Microsoft 创建 DNS 记录
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: 了解如何在 Hostgator for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 7f12b407254ff4146f77090da07d98db63e47305
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221879"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a><span data-ttu-id="edff1-103">在 Hostgator 为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="edff1-103">Create DNS records at Hostgator for Microsoft</span></span>

 <span data-ttu-id="edff1-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="edff1-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="edff1-105">如果 Hostgator 是 DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="edff1-106">在使用本文中的其他任何过程添加 DNS[](#point-your-domain-to-your-hosting-account)记录之前，必须执行第一个过程，即将域指向托管帐户。</span><span class="sxs-lookup"><span data-stu-id="edff1-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="edff1-107">在 Hostgator 进行所有这些更改后，域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="edff1-107">After you make all of these changes at Hostgator, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="edff1-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="edff1-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="edff1-109">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="edff1-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="edff1-110">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="edff1-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="edff1-111">将域指向托管帐户</span><span class="sxs-lookup"><span data-stu-id="edff1-111">Point your domain to your hosting account</span></span>
<span data-ttu-id="edff1-112"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="edff1-112"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="edff1-113">您必须先执行此过程，然后才能执行本文中的其他任何过程。</span><span class="sxs-lookup"><span data-stu-id="edff1-113">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="edff1-114">请按以下步骤将域与托管帐户关联。</span><span class="sxs-lookup"><span data-stu-id="edff1-114">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="edff1-115">To get started， go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/).</span><span class="sxs-lookup"><span data-stu-id="edff1-115">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/).</span></span> <span data-ttu-id="edff1-116">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="edff1-116">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="edff1-117">选择 **左侧** 的"域"。</span><span class="sxs-lookup"><span data-stu-id="edff1-117">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="edff1-118">在" **管理域** "页上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="edff1-118">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="edff1-119">在左侧的弹出菜单上，选择名称 **服务器**。</span><span class="sxs-lookup"><span data-stu-id="edff1-119">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="edff1-120">On the **Name Servers** page for your domain， in the Automatically point this domain to **my hosting account** drop-down list， choose the hosting account that is associated with your domain.</span><span class="sxs-lookup"><span data-stu-id="edff1-120">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="edff1-121">选择 **"保存名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-121">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="edff1-122">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="edff1-122">Add a TXT record for verification</span></span>
<span data-ttu-id="edff1-123"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="edff1-123"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="edff1-124">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="edff1-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="edff1-p103">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="edff1-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="edff1-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="edff1-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="edff1-p105">若要开始，请转到您在 Hostgator 上的 cPanel 页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="edff1-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="edff1-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="edff1-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="edff1-132">您的 cPanel 地址应如下所示 https://YourSiteAddress:secure-port-number ：。</span><span class="sxs-lookup"><span data-stu-id="edff1-132">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="edff1-133">从 Hostgator 收到的注册电子邮件将指定该地址，"托管"页面上也提供了 cPanel 链接。) </span><span class="sxs-lookup"><span data-stu-id="edff1-133">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edff1-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="edff1-135">若要开始使用 Microsoft，可以从 Hostgator 购买托管帐户，也可以将名称服务器重新代理[为指向 Microsoft。](change-nameservers-at-hostgator.md)</span><span class="sxs-lookup"><span data-stu-id="edff1-135">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="edff1-136">在"**控制面板"** 页上的 **"域"** 区域中，选择"**高级区域编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-136">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="edff1-137">在"**高级区域编辑器**"页上的"添加记录"区域中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="edff1-137">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="edff1-138">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="edff1-138">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="edff1-139">**名称**</span><span class="sxs-lookup"><span data-stu-id="edff1-139">**Name**</span></span> <br/> |<span data-ttu-id="edff1-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="edff1-140">**TTL**</span></span> <br/> |<span data-ttu-id="edff1-141">**类型**</span><span class="sxs-lookup"><span data-stu-id="edff1-141">**Type**</span></span> <br/> |<span data-ttu-id="edff1-142">**TXT 数据**</span><span class="sxs-lookup"><span data-stu-id="edff1-142">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="edff1-143">使用你的  *domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-143">Use your  *domain_name*.</span></span> <span data-ttu-id="edff1-144">（例如，fourthcoffee.com.)。</span><span class="sxs-lookup"><span data-stu-id="edff1-144">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-145">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-145">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-146">1</span><span class="sxs-lookup"><span data-stu-id="edff1-146">1</span></span>  <br/> |<span data-ttu-id="edff1-147">TXT</span><span class="sxs-lookup"><span data-stu-id="edff1-147">TXT</span></span>  <br/> |<span data-ttu-id="edff1-148">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="edff1-148">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="edff1-149">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="edff1-149">**Note:** This is an example.</span></span> <span data-ttu-id="edff1-150">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="edff1-150">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="edff1-151">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="edff1-151">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="edff1-152">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-152">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="edff1-153">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="edff1-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="edff1-154">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="edff1-155">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="edff1-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="edff1-156">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="edff1-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="edff1-157">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="edff1-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="edff1-158">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="edff1-158">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="edff1-159">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="edff1-159">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="edff1-160">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="edff1-160">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="edff1-161">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="edff1-161">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="edff1-162">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="edff1-162">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="edff1-163">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="edff1-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="edff1-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="edff1-164"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="edff1-165">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="edff1-165">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="edff1-166">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-166">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="edff1-167">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="edff1-167">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="edff1-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="edff1-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="edff1-169">您的 cPanel 地址应如下所示 https://YourSiteAddress:secure-port-number ：。</span><span class="sxs-lookup"><span data-stu-id="edff1-169">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="edff1-170">从 Hostgator 收到的注册电子邮件将指定该地址，"托管"页面上也提供了 cPanel 链接。) </span><span class="sxs-lookup"><span data-stu-id="edff1-170">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edff1-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="edff1-172">若要开始使用 Microsoft，可以从 Hostgator 购买托管帐户，也可以将名称服务器重新代理[为指向 Microsoft。](change-nameservers-at-hostgator.md)</span><span class="sxs-lookup"><span data-stu-id="edff1-172">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="edff1-173">在"**控制面板"** 页上的"**电子邮件**"区域中，选择 **"MX 条目"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-173">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="edff1-174">在"**电子邮件路由"** 区域中，选择"**远程邮件交换器"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-174">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="edff1-175">选择“更改”。</span><span class="sxs-lookup"><span data-stu-id="edff1-175">Select **Change**.</span></span>
  
5. <span data-ttu-id="edff1-176">在 **"添加新记录** "区域中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="edff1-176">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="edff1-177">**Priority**</span><span class="sxs-lookup"><span data-stu-id="edff1-177">**Priority**</span></span>|<span data-ttu-id="edff1-178">**目标**</span><span class="sxs-lookup"><span data-stu-id="edff1-178">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="edff1-179">0</span><span class="sxs-lookup"><span data-stu-id="edff1-179">0</span></span>  <br/> <span data-ttu-id="edff1-180">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="edff1-180">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="edff1-181">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="edff1-181">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="edff1-182">**注意：** 从 Microsoft 帐户获取 \< *domain-key*  \>。</span><span class="sxs-lookup"><span data-stu-id="edff1-182">**Note:** Get your \< *domain-key*  \> from your Microsoft account.</span></span>  [<span data-ttu-id="edff1-183">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="edff1-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="edff1-184">选择 **"添加新记录"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-184">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="edff1-185">如果"MX 记录"部分有任何其他 **MX** 记录，请删除其中每个记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-185">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="edff1-186">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="edff1-186">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="edff1-187"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="edff1-187"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="edff1-188">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="edff1-188">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="edff1-189">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-189">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="edff1-190">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="edff1-190">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="edff1-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="edff1-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="edff1-192">您的 cPanel 地址应如下所示 https://YourSiteAddress:secure-port-number ：。</span><span class="sxs-lookup"><span data-stu-id="edff1-192">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="edff1-193">从 Hostgator 收到的注册电子邮件将指定该地址，"托管"页面上也提供了 cPanel 链接。) </span><span class="sxs-lookup"><span data-stu-id="edff1-193">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edff1-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="edff1-195">若要开始使用 Microsoft，可以从 Hostgator 购买托管帐户，也可以将名称服务器重新代理[为指向 Microsoft。](change-nameservers-at-hostgator.md)</span><span class="sxs-lookup"><span data-stu-id="edff1-195">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="edff1-196">在"**控制面板"** 页上的 **"域"** 区域中，选择"**高级区域编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-196">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="edff1-197">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="edff1-197">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="edff1-198">在"**高级区域** 编辑器"页上的"添加记录"区域中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="edff1-198">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="edff1-199">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="edff1-199">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="edff1-200">**名称**</span><span class="sxs-lookup"><span data-stu-id="edff1-200">**Name**</span></span>|<span data-ttu-id="edff1-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="edff1-201">**TTL**</span></span>|<span data-ttu-id="edff1-202">**类型**</span><span class="sxs-lookup"><span data-stu-id="edff1-202">**Type**</span></span>|<span data-ttu-id="edff1-203">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="edff1-203">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="edff1-204">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="edff1-204">autodiscover.</span></span> <span data-ttu-id="edff1-205">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-205">*domain_name*.</span></span> <span data-ttu-id="edff1-206"> (，例如，autodiscover.fourthcoffee.com.) </span><span class="sxs-lookup"><span data-stu-id="edff1-206">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-207">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-208">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-208">3600</span></span>  <br/> |<span data-ttu-id="edff1-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="edff1-209">CNAME</span></span>  <br/> |<span data-ttu-id="edff1-210">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="edff1-210">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="edff1-211">sip.</span><span class="sxs-lookup"><span data-stu-id="edff1-211">sip.</span></span> <span data-ttu-id="edff1-212">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-212">*domain_name*.</span></span> <span data-ttu-id="edff1-213"> (，例如 sip.fourthcoffee.com.) </span><span class="sxs-lookup"><span data-stu-id="edff1-213">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-214">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-214">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-215">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-215">3600</span></span>  <br/> |<span data-ttu-id="edff1-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="edff1-216">CNAME</span></span>  <br/> |<span data-ttu-id="edff1-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="edff1-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="edff1-218">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="edff1-218">lyncdiscover.</span></span> <span data-ttu-id="edff1-219">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-219">*domain_name*.</span></span> <span data-ttu-id="edff1-220"> (，例如 lyncdiscover.fourthcoffee.com.) </span><span class="sxs-lookup"><span data-stu-id="edff1-220">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-221">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-221">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-222">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-222">3600</span></span>  <br/> |<span data-ttu-id="edff1-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="edff1-223">CNAME</span></span>  <br/> |<span data-ttu-id="edff1-224">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="edff1-224">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="edff1-225">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="edff1-225">enterpriseregistration.</span></span> <span data-ttu-id="edff1-226">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-226">*domain_name*.</span></span> <span data-ttu-id="edff1-227"> (，例如 enterpriseregistration.fourthcoffee.com.) </span><span class="sxs-lookup"><span data-stu-id="edff1-227">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-228">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-229">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-229">3600</span></span>  <br/> |<span data-ttu-id="edff1-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="edff1-230">CNAME</span></span>  <br/> |<span data-ttu-id="edff1-231">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="edff1-231">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="edff1-232">enterpriseenrollment。</span><span class="sxs-lookup"><span data-stu-id="edff1-232">enterpriseenrollment.</span></span> <span data-ttu-id="edff1-233">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-233">*domain_name*.</span></span> <span data-ttu-id="edff1-234"> (，例如 enterpriseregistration.fourthcoffee.com.) </span><span class="sxs-lookup"><span data-stu-id="edff1-234">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-235">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-235">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-236">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-236">3600</span></span>  <br/> |<span data-ttu-id="edff1-237">CNAME</span><span class="sxs-lookup"><span data-stu-id="edff1-237">CNAME</span></span>  <br/> |<span data-ttu-id="edff1-238">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="edff1-238">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="edff1-239">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-239">Select **Add Record**.</span></span>

5. <span data-ttu-id="edff1-240">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-240">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="edff1-241">在" **添加记录** "部分，使用表中下一行的值创建记录，然后再次选择" **添加记录** "以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-241">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="edff1-242">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-242">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="edff1-243">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="edff1-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="edff1-244"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="edff1-244"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="edff1-245">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="edff1-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="edff1-246">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="edff1-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="edff1-247">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="edff1-248">可以将所需的 Microsoft 值添加到当前记录，这样就拥有包含两组值的单个 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-248">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="edff1-249">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="edff1-249">Need examples?</span></span> <span data-ttu-id="edff1-250">请查看 [Microsoft 的外部域名系统记录](../../enterprise/external-domain-name-system-records.md)。</span><span class="sxs-lookup"><span data-stu-id="edff1-250">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="edff1-251">若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="edff1-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="edff1-252">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="edff1-252">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="edff1-253">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-253">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="edff1-254">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="edff1-254">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="edff1-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="edff1-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="edff1-256">您的 cPanel 地址应如下所示 https://YourSiteAddress:secure-port-number ：。</span><span class="sxs-lookup"><span data-stu-id="edff1-256">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="edff1-257">从 Hostgator 收到的注册电子邮件将指定该地址，"托管"页面上也提供了 cPanel 链接。) </span><span class="sxs-lookup"><span data-stu-id="edff1-257">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edff1-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="edff1-259">若要开始使用 Microsoft，可以从 Hostgator 购买托管帐户，也可以将名称服务器重新代理[为指向 Microsoft。](change-nameservers-at-hostgator.md)</span><span class="sxs-lookup"><span data-stu-id="edff1-259">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="edff1-260">在"**控制面板"** 页上的 **"域"** 区域中，选择"**高级区域编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-260">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="edff1-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="edff1-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="edff1-262">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="edff1-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="edff1-263">**名称**</span><span class="sxs-lookup"><span data-stu-id="edff1-263">**Name**</span></span>|<span data-ttu-id="edff1-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="edff1-264">**TTL**</span></span>|<span data-ttu-id="edff1-265">**类型**</span><span class="sxs-lookup"><span data-stu-id="edff1-265">**Type**</span></span>|<span data-ttu-id="edff1-266">**TXT 数据**</span><span class="sxs-lookup"><span data-stu-id="edff1-266">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="edff1-267">使用你的  *domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-267">Use your  *domain_name*.</span></span> <span data-ttu-id="edff1-268">（例如，fourthcoffee.com.)。</span><span class="sxs-lookup"><span data-stu-id="edff1-268">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-269">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-269">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-270">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-270">3600</span></span>  <br/> |<span data-ttu-id="edff1-271">TXT</span><span class="sxs-lookup"><span data-stu-id="edff1-271">TXT</span></span>  <br/> |<span data-ttu-id="edff1-272">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="edff1-272">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="edff1-273">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="edff1-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="edff1-274">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-274">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="edff1-275">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="edff1-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="edff1-276"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="edff1-276"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="edff1-277">执行此过程之前，必须首先执行本文第一部分[将域指向托管帐户](#point-your-domain-to-your-hosting-account)中的过程。</span><span class="sxs-lookup"><span data-stu-id="edff1-277">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="edff1-278">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-278">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="edff1-279">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="edff1-279">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="edff1-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="edff1-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="edff1-281">您的 cPanel 地址应如下所示 https://YourSiteAddress:secure-port-number ：。</span><span class="sxs-lookup"><span data-stu-id="edff1-281">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="edff1-282">从 Hostgator 收到的注册电子邮件将指定该地址，"托管"页面上也提供了 cPanel 链接。) </span><span class="sxs-lookup"><span data-stu-id="edff1-282">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="edff1-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="edff1-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="edff1-284">若要开始使用 Microsoft，可以从 Hostgator 购买托管帐户，也可以将名称服务器重新代理[为指向 Microsoft。](change-nameservers-at-hostgator.md)</span><span class="sxs-lookup"><span data-stu-id="edff1-284">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="edff1-285">在"**控制面板"** 页上的 **"域"** 区域中，选择"**高级区域编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-285">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="edff1-286">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-286">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="edff1-287">在"**高级 DNS** 区域编辑器"页上的"添加记录"区域中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="edff1-287">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="edff1-288">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="edff1-288">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="edff1-289">**名称**</span><span class="sxs-lookup"><span data-stu-id="edff1-289">**Name**</span></span>|<span data-ttu-id="edff1-290">**TTL**</span><span class="sxs-lookup"><span data-stu-id="edff1-290">**TTL**</span></span>|<span data-ttu-id="edff1-291">**类型**</span><span class="sxs-lookup"><span data-stu-id="edff1-291">**Type**</span></span>|<span data-ttu-id="edff1-292">**优先级**</span><span class="sxs-lookup"><span data-stu-id="edff1-292">**Priority**</span></span>|<span data-ttu-id="edff1-293">**权重**</span><span class="sxs-lookup"><span data-stu-id="edff1-293">**Weight**</span></span>|<span data-ttu-id="edff1-294">**端口**</span><span class="sxs-lookup"><span data-stu-id="edff1-294">**Port**</span></span>|<span data-ttu-id="edff1-295">**目标**</span><span class="sxs-lookup"><span data-stu-id="edff1-295">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="edff1-296">_sip._tls。</span><span class="sxs-lookup"><span data-stu-id="edff1-296">_sip._tls.</span></span> <span data-ttu-id="edff1-297">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-297">*domain_name*.</span></span> <span data-ttu-id="edff1-298"> (，例如，_sip._tls.fourthcoffee.com.) </span><span class="sxs-lookup"><span data-stu-id="edff1-298">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-299">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-299">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-300">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-300">3600</span></span>  <br/> |<span data-ttu-id="edff1-301">SRV</span><span class="sxs-lookup"><span data-stu-id="edff1-301">SRV</span></span>  <br/> |<span data-ttu-id="edff1-302">100</span><span class="sxs-lookup"><span data-stu-id="edff1-302">100</span></span>  <br/> |<span data-ttu-id="edff1-303">1</span><span class="sxs-lookup"><span data-stu-id="edff1-303">1</span></span>  <br/> |<span data-ttu-id="edff1-304">443</span><span class="sxs-lookup"><span data-stu-id="edff1-304">443</span></span>  <br/> |<span data-ttu-id="edff1-305">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="edff1-305">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="edff1-306">_sipfederationtls._tcp。</span><span class="sxs-lookup"><span data-stu-id="edff1-306">_sipfederationtls._tcp.</span></span> <span data-ttu-id="edff1-307">*domain_name*。</span><span class="sxs-lookup"><span data-stu-id="edff1-307">*domain_name*.</span></span> <span data-ttu-id="edff1-308"> (，例如，_sipfederationtls._tcp.fourthcoffee.com.) </span><span class="sxs-lookup"><span data-stu-id="edff1-308">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="edff1-309">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="edff1-309">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="edff1-310">3600</span><span class="sxs-lookup"><span data-stu-id="edff1-310">3600</span></span>  <br/> |<span data-ttu-id="edff1-311">SRV</span><span class="sxs-lookup"><span data-stu-id="edff1-311">SRV</span></span>  <br/> |<span data-ttu-id="edff1-312">100</span><span class="sxs-lookup"><span data-stu-id="edff1-312">100</span></span>  <br/> |<span data-ttu-id="edff1-313">1</span><span class="sxs-lookup"><span data-stu-id="edff1-313">1</span></span>  <br/> |<span data-ttu-id="edff1-314">5061</span><span class="sxs-lookup"><span data-stu-id="edff1-314">5061</span></span>  <br/> |<span data-ttu-id="edff1-315">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="edff1-315">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="edff1-316">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="edff1-316">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="edff1-317">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-317">Add the other SRV record.</span></span>
    
    <span data-ttu-id="edff1-318">在" **添加记录** "部分，使用表中下一行的值创建记录，然后再次选择" **添加记录** "以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="edff1-318">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="edff1-319">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="edff1-319">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="edff1-320">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="edff1-320">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="edff1-321">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="edff1-321">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>