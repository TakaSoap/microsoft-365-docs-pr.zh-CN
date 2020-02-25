---
title: 在 123-reg.co.uk 处为 Office 365 创建 DNS 记录
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: 了解如何在 123-reg.co.uk for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: acbc0f1c8a7eb7dcbe5f274d0f2c8b2c403e7de0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238546"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="9dc63-103">在 123-reg.co.uk 处为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="9dc63-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="9dc63-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="9dc63-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9dc63-105">如果 DNS 托管提供者是 123-reg.co.uk，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9dc63-106">在 123-reg.co.uk 处添加这些记录后，域将设置为使用 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="9dc63-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="9dc63-107">要了解有关与 Office 365 配合使用的网站的 Web 宿主和 DNS 的信息，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="9dc63-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9dc63-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9dc63-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9dc63-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9dc63-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9dc63-110">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc63-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9dc63-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="9dc63-111">Add a TXT record for verification</span></span>
<span data-ttu-id="9dc63-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9dc63-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9dc63-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="9dc63-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9dc63-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="9dc63-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9dc63-p104">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9dc63-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9dc63-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9dc63-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9dc63-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9dc63-121">在 "**管理 DNS** " 页面上，选择 "**高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9dc63-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9dc63-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9dc63-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9dc63-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9dc63-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="9dc63-124">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9dc63-124">**Hostname**</span></span> <br/> |<span data-ttu-id="9dc63-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="9dc63-125">**Type**</span></span> <br/> |<span data-ttu-id="9dc63-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="9dc63-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="9dc63-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="9dc63-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="9dc63-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9dc63-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9dc63-129">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="9dc63-129">**Note:** This is an example.</span></span> <span data-ttu-id="9dc63-130">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="9dc63-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="9dc63-131">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="9dc63-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="9dc63-132">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9dc63-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="9dc63-133">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="9dc63-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9dc63-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="9dc63-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9dc63-135">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="9dc63-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9dc63-136">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="9dc63-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9dc63-137">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="9dc63-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9dc63-138">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="9dc63-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9dc63-139">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="9dc63-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9dc63-140">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9dc63-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9dc63-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9dc63-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9dc63-142">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc63-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9dc63-143">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="9dc63-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9dc63-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9dc63-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9dc63-145">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="9dc63-145">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="9dc63-146">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-146">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9dc63-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9dc63-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9dc63-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9dc63-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9dc63-149">在 "**管理 DNS** " 页面上，选择 "**高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9dc63-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9dc63-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9dc63-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9dc63-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9dc63-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9dc63-152">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9dc63-152">**Hostname**</span></span>|<span data-ttu-id="9dc63-153">**类型**</span><span class="sxs-lookup"><span data-stu-id="9dc63-153">**Type**</span></span>|<span data-ttu-id="9dc63-154">**优先级**</span><span class="sxs-lookup"><span data-stu-id="9dc63-154">**Priority**</span></span>|<span data-ttu-id="9dc63-155">**目标 MX**</span><span class="sxs-lookup"><span data-stu-id="9dc63-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9dc63-156">MX</span><span class="sxs-lookup"><span data-stu-id="9dc63-156">MX</span></span>  <br/> |<span data-ttu-id="9dc63-157">1</span><span class="sxs-lookup"><span data-stu-id="9dc63-157">1</span></span>  <br/> <span data-ttu-id="9dc63-158">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="9dc63-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="9dc63-159">*\<域密钥\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="9dc63-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="9dc63-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="9dc63-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="9dc63-161">**注意：** 从 Office \<365 帐户中\>获取你的域密钥。</span><span class="sxs-lookup"><span data-stu-id="9dc63-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="9dc63-162">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="9dc63-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![复制并粘贴表中的值](../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="9dc63-164">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9dc63-164">Select **Add**.</span></span>
    
    ![选择"添加"](../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="9dc63-166">如果有任何其他 MX 记录，通过选择每条记录的" **删除(回收站)**"图标将其删除。</span><span class="sxs-lookup"><span data-stu-id="9dc63-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![选择 "删除" （"垃圾桶" 图标）](../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9dc63-168">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="9dc63-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9dc63-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9dc63-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9dc63-170">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="9dc63-170">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="9dc63-171">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-171">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9dc63-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9dc63-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9dc63-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9dc63-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9dc63-174">在 "**管理 DNS** " 页面上，选择 "**高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9dc63-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9dc63-175">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="9dc63-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9dc63-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9dc63-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9dc63-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9dc63-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9dc63-178">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9dc63-178">**Hostname**</span></span>|<span data-ttu-id="9dc63-179">**类型**</span><span class="sxs-lookup"><span data-stu-id="9dc63-179">**Type**</span></span>|<span data-ttu-id="9dc63-180">**目标 CNAME**</span><span class="sxs-lookup"><span data-stu-id="9dc63-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9dc63-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9dc63-181">autodiscover</span></span>  <br/> |<span data-ttu-id="9dc63-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="9dc63-182">CNAME</span></span>  <br/> |<span data-ttu-id="9dc63-183">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="9dc63-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="9dc63-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="9dc63-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9dc63-185">sip</span><span class="sxs-lookup"><span data-stu-id="9dc63-185">sip</span></span>  <br/> |<span data-ttu-id="9dc63-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="9dc63-186">CNAME</span></span>  <br/> |<span data-ttu-id="9dc63-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="9dc63-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9dc63-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="9dc63-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9dc63-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9dc63-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9dc63-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="9dc63-190">CNAME</span></span>  <br/> |<span data-ttu-id="9dc63-191">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="9dc63-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9dc63-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="9dc63-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9dc63-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9dc63-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9dc63-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="9dc63-194">CNAME</span></span>  <br/> |<span data-ttu-id="9dc63-195">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="9dc63-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="9dc63-196">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9dc63-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="9dc63-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9dc63-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9dc63-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="9dc63-198">CNAME</span></span>  <br/> |<span data-ttu-id="9dc63-199">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="9dc63-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="9dc63-200">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="9dc63-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![复制并粘贴表中的值](../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="9dc63-202">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9dc63-202">Select **Add**.</span></span>
    
    ![选择"添加"](../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="9dc63-204">添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="9dc63-205">在 "**高级 DNS** " 部分，使用表中下一行的值创建记录，然后再次选择 "**添加**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="9dc63-206">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9dc63-207">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="9dc63-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9dc63-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9dc63-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dc63-209">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="9dc63-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9dc63-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="9dc63-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9dc63-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="9dc63-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9dc63-212">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="9dc63-213">Need examples?</span><span class="sxs-lookup"><span data-stu-id="9dc63-213">Need examples?</span></span> <span data-ttu-id="9dc63-214">查看[Office 365 的这些外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="9dc63-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="9dc63-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9dc63-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="9dc63-216">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="9dc63-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="9dc63-217">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9dc63-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9dc63-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9dc63-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9dc63-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9dc63-220">在 "**管理 DNS** " 页面上，选择 "**高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9dc63-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9dc63-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9dc63-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9dc63-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9dc63-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9dc63-223">**主机名**</span><span class="sxs-lookup"><span data-stu-id="9dc63-223">**Hostname**</span></span>|<span data-ttu-id="9dc63-224">**类型**</span><span class="sxs-lookup"><span data-stu-id="9dc63-224">**Type**</span></span>|<span data-ttu-id="9dc63-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="9dc63-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9dc63-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="9dc63-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="9dc63-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9dc63-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9dc63-228">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="9dc63-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-配置-4-1](../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="9dc63-230">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9dc63-230">Select **Add**.</span></span>
    
    ![选择"添加"](../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9dc63-232">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="9dc63-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9dc63-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9dc63-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9dc63-234">要开始，请使用[此链接](https://www.123-reg.co.uk/secure/cpanel/domain/overview)转到您在 123-reg.co.uk 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="9dc63-234">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="9dc63-235">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-235">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9dc63-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="9dc63-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="9dc63-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9dc63-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="9dc63-238">在 "**管理 DNS** " 页面上，选择 "**高级 DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9dc63-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="9dc63-239">添加两条 SRV 记录中的第一个：</span><span class="sxs-lookup"><span data-stu-id="9dc63-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="9dc63-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9dc63-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9dc63-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9dc63-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9dc63-242">主机名</span><span class="sxs-lookup"><span data-stu-id="9dc63-242">Hostname</span></span>|<span data-ttu-id="9dc63-243">类型</span><span class="sxs-lookup"><span data-stu-id="9dc63-243">Type</span></span>|<span data-ttu-id="9dc63-244">优先级</span><span class="sxs-lookup"><span data-stu-id="9dc63-244">Priority</span></span>|<span data-ttu-id="9dc63-245">TTL</span><span class="sxs-lookup"><span data-stu-id="9dc63-245">TTL</span></span>|<span data-ttu-id="9dc63-246">目标 SRV</span><span class="sxs-lookup"><span data-stu-id="9dc63-246">Destination SRV</span></span>|
    |<span data-ttu-id="9dc63-247">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="9dc63-247">_sip._tls</span></span>|<span data-ttu-id="9dc63-248">SRV</span><span class="sxs-lookup"><span data-stu-id="9dc63-248">SRV</span></span>|<span data-ttu-id="9dc63-249">100</span><span class="sxs-lookup"><span data-stu-id="9dc63-249">100</span></span>|<span data-ttu-id="9dc63-250">3600</span><span class="sxs-lookup"><span data-stu-id="9dc63-250">3600</span></span>|<span data-ttu-id="9dc63-251">1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="9dc63-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="9dc63-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="9dc63-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="9dc63-253">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="9dc63-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="9dc63-254">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="9dc63-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="9dc63-255">SRV</span><span class="sxs-lookup"><span data-stu-id="9dc63-255">SRV</span></span>|<span data-ttu-id="9dc63-256">100</span><span class="sxs-lookup"><span data-stu-id="9dc63-256">100</span></span>|<span data-ttu-id="9dc63-257">3600</span><span class="sxs-lookup"><span data-stu-id="9dc63-257">3600</span></span>|<span data-ttu-id="9dc63-258">1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="9dc63-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="9dc63-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="9dc63-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="9dc63-260">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="9dc63-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![复制并粘贴表中的值](../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="9dc63-262">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="9dc63-262">Select **Add**.</span></span>
    
    ![选择"添加"](../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="9dc63-264">添加其他 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="9dc63-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="9dc63-265">在 "**高级 DNS** " 部分，使用表中第二行的值创建记录，然后再次选择 "**添加**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="9dc63-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="9dc63-266">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9dc63-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9dc63-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9dc63-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9dc63-268">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc63-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
