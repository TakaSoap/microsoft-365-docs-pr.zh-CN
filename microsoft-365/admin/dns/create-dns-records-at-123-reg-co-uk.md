---
title: 在123-reg.co.uk 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 了解如何验证您的域，并在 123-reg.co.uk for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 51542e1f00153a87ca06ec540d391de6ca621bab
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307027"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="9cd79-103">在123-reg.co.uk 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="9cd79-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="9cd79-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="9cd79-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9cd79-105">如果 DNS 托管提供者是 123-reg.co.uk，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9cd79-106">在123-reg.co.uk 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="9cd79-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="9cd79-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9cd79-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9cd79-108">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="9cd79-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9cd79-109">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9cd79-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9cd79-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="9cd79-110">Add a TXT record for verification</span></span>
<span data-ttu-id="9cd79-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9cd79-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9cd79-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="9cd79-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cd79-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="9cd79-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9cd79-p104">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9cd79-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9cd79-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9cd79-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9cd79-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9cd79-120">在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cd79-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9cd79-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9cd79-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9cd79-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9cd79-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="9cd79-123">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9cd79-123">**Hostname**</span></span> <br/> |<span data-ttu-id="9cd79-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="9cd79-124">**Type**</span></span> <br/> |<span data-ttu-id="9cd79-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="9cd79-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="9cd79-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="9cd79-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="9cd79-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9cd79-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9cd79-128">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="9cd79-128">**Note:** This is an example.</span></span> <span data-ttu-id="9cd79-129">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="9cd79-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="9cd79-130">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="9cd79-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="9cd79-131">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9cd79-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="9cd79-132">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="9cd79-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9cd79-133">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="9cd79-134">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="9cd79-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9cd79-135">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cd79-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9cd79-136">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="9cd79-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9cd79-137">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="9cd79-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9cd79-138">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="9cd79-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9cd79-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9cd79-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9cd79-140">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="9cd79-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9cd79-141">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9cd79-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9cd79-142">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cd79-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9cd79-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9cd79-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9cd79-p107">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9cd79-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9cd79-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9cd79-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9cd79-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9cd79-148">在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cd79-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9cd79-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9cd79-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9cd79-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9cd79-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9cd79-151">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9cd79-151">**Hostname**</span></span>|<span data-ttu-id="9cd79-152">**类型**</span><span class="sxs-lookup"><span data-stu-id="9cd79-152">**Type**</span></span>|<span data-ttu-id="9cd79-153">**优先级**</span><span class="sxs-lookup"><span data-stu-id="9cd79-153">**Priority**</span></span>|<span data-ttu-id="9cd79-154">**目标 MX**</span><span class="sxs-lookup"><span data-stu-id="9cd79-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9cd79-155">MX</span><span class="sxs-lookup"><span data-stu-id="9cd79-155">MX</span></span>  <br/> |<span data-ttu-id="9cd79-156">1 </span><span class="sxs-lookup"><span data-stu-id="9cd79-156">1</span></span>  <br/> <span data-ttu-id="9cd79-157">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="9cd79-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="9cd79-158">*\<domain-key\>*  . mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="9cd79-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="9cd79-159">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="9cd79-160">**注意：** 从 Microsoft 帐户获取 \<domain-key\>。</span><span class="sxs-lookup"><span data-stu-id="9cd79-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="9cd79-161">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="9cd79-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![复制并粘贴表中的值](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="9cd79-163">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9cd79-163">Select **Add**.</span></span>
    
    ![选择“添加”](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="9cd79-165">如果有任何其他 MX 记录，通过选择每条记录的" **删除(回收站)**"图标将其删除。</span><span class="sxs-lookup"><span data-stu-id="9cd79-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![选择 "删除 (垃圾桶" 图标) ](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9cd79-167">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="9cd79-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9cd79-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9cd79-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9cd79-p109">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9cd79-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9cd79-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9cd79-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9cd79-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9cd79-173">在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cd79-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9cd79-174">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="9cd79-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9cd79-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9cd79-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9cd79-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9cd79-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9cd79-177">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9cd79-177">**Hostname**</span></span>|<span data-ttu-id="9cd79-178">**类型**</span><span class="sxs-lookup"><span data-stu-id="9cd79-178">**Type**</span></span>|<span data-ttu-id="9cd79-179">**目标 CNAME**</span><span class="sxs-lookup"><span data-stu-id="9cd79-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9cd79-180">自动发现</span><span class="sxs-lookup"><span data-stu-id="9cd79-180">autodiscover</span></span>  <br/> |<span data-ttu-id="9cd79-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cd79-181">CNAME</span></span>  <br/> |<span data-ttu-id="9cd79-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9cd79-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="9cd79-183">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9cd79-184">sip</span><span class="sxs-lookup"><span data-stu-id="9cd79-184">sip</span></span>  <br/> |<span data-ttu-id="9cd79-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cd79-185">CNAME</span></span>  <br/> |<span data-ttu-id="9cd79-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9cd79-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9cd79-187">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9cd79-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9cd79-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9cd79-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cd79-189">CNAME</span></span>  <br/> |<span data-ttu-id="9cd79-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9cd79-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9cd79-191">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9cd79-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9cd79-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9cd79-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cd79-193">CNAME</span></span>  <br/> |<span data-ttu-id="9cd79-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="9cd79-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="9cd79-195">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9cd79-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9cd79-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9cd79-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="9cd79-197">CNAME</span></span>  <br/> |<span data-ttu-id="9cd79-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9cd79-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="9cd79-199">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![复制并粘贴表中的值](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="9cd79-201">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9cd79-201">Select **Add**.</span></span>
    
    ![选择“添加”](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="9cd79-203">添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="9cd79-204">在 " **高级 DNS** " 部分，使用表中下一行的值创建记录，然后再次选择 " **添加** " 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="9cd79-205">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9cd79-206">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="9cd79-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9cd79-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9cd79-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cd79-208">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="9cd79-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9cd79-209">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="9cd79-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9cd79-210">如果你已有域的 SPF 记录，请勿为 Microsfot 创建新的。</span><span class="sxs-lookup"><span data-stu-id="9cd79-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="9cd79-211">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的  *单个*  SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="9cd79-212">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="9cd79-212">Need examples?</span></span> <span data-ttu-id="9cd79-213">请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf)。</span><span class="sxs-lookup"><span data-stu-id="9cd79-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="9cd79-214">若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="9cd79-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="9cd79-215">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="9cd79-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="9cd79-216">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9cd79-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9cd79-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9cd79-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9cd79-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9cd79-219">在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cd79-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9cd79-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9cd79-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9cd79-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9cd79-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9cd79-222">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9cd79-222">**Hostname**</span></span>|<span data-ttu-id="9cd79-223">**类型**</span><span class="sxs-lookup"><span data-stu-id="9cd79-223">**Type**</span></span>|<span data-ttu-id="9cd79-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="9cd79-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9cd79-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="9cd79-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="9cd79-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9cd79-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9cd79-227">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="9cd79-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-配置-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="9cd79-229">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9cd79-229">Select **Add**.</span></span>
    
    ![选择“添加”](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9cd79-231">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="9cd79-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9cd79-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9cd79-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9cd79-p112">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9cd79-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9cd79-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9cd79-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9cd79-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9cd79-237">在 " **管理 DNS** " 页面上，选择 " **高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cd79-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9cd79-238">添加两条 SRV 记录中的第一个：</span><span class="sxs-lookup"><span data-stu-id="9cd79-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="9cd79-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9cd79-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9cd79-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9cd79-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9cd79-241">主机名</span><span class="sxs-lookup"><span data-stu-id="9cd79-241">Hostname</span></span>|<span data-ttu-id="9cd79-242">类型</span><span class="sxs-lookup"><span data-stu-id="9cd79-242">Type</span></span>|<span data-ttu-id="9cd79-243">优先级</span><span class="sxs-lookup"><span data-stu-id="9cd79-243">Priority</span></span>|<span data-ttu-id="9cd79-244">TTL</span><span class="sxs-lookup"><span data-stu-id="9cd79-244">TTL</span></span>|<span data-ttu-id="9cd79-245">目标 SRV</span><span class="sxs-lookup"><span data-stu-id="9cd79-245">Destination SRV</span></span>|
    |<span data-ttu-id="9cd79-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="9cd79-246">_sip._tls</span></span>|<span data-ttu-id="9cd79-247">SRV</span><span class="sxs-lookup"><span data-stu-id="9cd79-247">SRV</span></span>|<span data-ttu-id="9cd79-248">100</span><span class="sxs-lookup"><span data-stu-id="9cd79-248">100</span></span>|<span data-ttu-id="9cd79-249">3600</span><span class="sxs-lookup"><span data-stu-id="9cd79-249">3600</span></span>|<span data-ttu-id="9cd79-250">1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="9cd79-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="9cd79-251">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="9cd79-252">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="9cd79-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="9cd79-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9cd79-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="9cd79-254">SRV</span><span class="sxs-lookup"><span data-stu-id="9cd79-254">SRV</span></span>|<span data-ttu-id="9cd79-255">100</span><span class="sxs-lookup"><span data-stu-id="9cd79-255">100</span></span>|<span data-ttu-id="9cd79-256">3600</span><span class="sxs-lookup"><span data-stu-id="9cd79-256">3600</span></span>|<span data-ttu-id="9cd79-257">1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="9cd79-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="9cd79-258">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9cd79-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="9cd79-259">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="9cd79-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![复制并粘贴表中的值](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="9cd79-261">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9cd79-261">Select **Add**.</span></span>
    
    ![选择“添加”](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="9cd79-263">添加其他 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="9cd79-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="9cd79-264">在 " **高级 DNS** " 部分，使用表中第二行的值创建记录，然后再次选择 " **添加** " 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="9cd79-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="9cd79-265">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9cd79-265">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9cd79-266">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="9cd79-266">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9cd79-267">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9cd79-267">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
