---
title: 在 DNSMadeEasy 为 Microsoft 创建 DNS 记录
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 了解如何在 DNSMadeEasy for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 719b416564447b3a6f4108b747ae921b4f6f6bb8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657944"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="2d3cc-103">在 DNSMadeEasy 为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2d3cc-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="2d3cc-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2d3cc-105">如果 DNSMadeEasy 是 DNS 托管提供商，请按照本文中的步骤验证域并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2d3cc-106">在 DNSMadeEasy 添加这些记录后，你的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="2d3cc-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2d3cc-108">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2d3cc-109">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2d3cc-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="2d3cc-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2d3cc-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2d3cc-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2d3cc-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d3cc-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2d3cc-116">对于 DNSMadeEasy 帐户，添加的域是从单独的域注册机构购买的。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="2d3cc-117">DNSMadeEasy 不提供域注册服务。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="2d3cc-118">在 DNSMadeEasy 登录并创建 DNS 记录的能力足以证明所有权。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="2d3cc-119">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="2d3cc-120">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2d3cc-121">在" **管理控制台** "页上的 **"最近** 更新的域"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="2d3cc-122">在"**托管 DNS"** 页上 **的"TXT** 记录"区域中，选择 () **+** 控件 (**添加新) 。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="2d3cc-123">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="2d3cc-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="2d3cc-125">**名称**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-125">**Name**</span></span> <br/> |<span data-ttu-id="2d3cc-126">**值**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-126">**Value**</span></span> <br/> |<span data-ttu-id="2d3cc-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="2d3cc-128">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2d3cc-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2d3cc-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2d3cc-130">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-130">**Note:** This is an example.</span></span> <span data-ttu-id="2d3cc-131">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="2d3cc-132">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="2d3cc-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="2d3cc-133">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="2d3cc-134">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="2d3cc-135">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2d3cc-136">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="2d3cc-137">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2d3cc-138">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="2d3cc-139">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="2d3cc-140">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="2d3cc-141">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2d3cc-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2d3cc-143">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2d3cc-144">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2d3cc-145">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d3cc-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2d3cc-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2d3cc-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="2d3cc-147">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-147">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="2d3cc-148">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-148">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2d3cc-149">在" **管理控制台** "页上的 **"最近** 更新的域"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="2d3cc-150">在" **管理控制台** "页上的 **"最近** 更新的域"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="2d3cc-152">在"**托管 DNS"** 页上的 **"MX** 记录"区域中，选择 (**+**) 控件 (**添加新) 。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="2d3cc-153">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="2d3cc-155">在 **"添加 MX 记录** "区域中新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="2d3cc-156">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="2d3cc-157">**名称**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-157">**Name**</span></span>|<span data-ttu-id="2d3cc-158">**服务器**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-158">**Server**</span></span>|<span data-ttu-id="2d3cc-159">**MX 级别**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-159">**MX Level**</span></span>|<span data-ttu-id="2d3cc-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2d3cc-161">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="2d3cc-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2d3cc-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2d3cc-163">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="2d3cc-164">**注意：** 从 Microsoft 帐户获取 \<*domain-key*\>。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="2d3cc-165">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="2d3cc-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="2d3cc-166">10 </span><span class="sxs-lookup"><span data-stu-id="2d3cc-166">10</span></span>  <br/> <span data-ttu-id="2d3cc-167">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="2d3cc-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="2d3cc-168">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="2d3cc-170">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="2d3cc-172">如果 **"MX** 记录"部分列出了任何其他 MX 记录，则通过选择每条记录来删除所有 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="2d3cc-174">选择所有记录后，选择"**删除所选"。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="2d3cc-176">在 **"删除 MX 记录** "对话框中，选择 **"删除** "以确认所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2d3cc-178">添加 Microsoft 所需的 5 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="2d3cc-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2d3cc-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2d3cc-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="2d3cc-180">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-180">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="2d3cc-181">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-181">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2d3cc-182">在" **管理控制台** "页上的 **"最近** 更新的域"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="2d3cc-183">在"**托管 DNS"** 页上 **的"CNAME** 记录"区域中，选择 (**+**) 控件 (**添加新) 。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="2d3cc-184">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="2d3cc-186">添加五条 CNAME 记录中的第一条。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="2d3cc-187">在 **"添加 CNAME 记录** "区域中新记录的框中，键入或复制粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="2d3cc-188">**名称**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-188">**Name**</span></span>|<span data-ttu-id="2d3cc-189">**别名**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-189">**Alias to**</span></span>|<span data-ttu-id="2d3cc-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2d3cc-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2d3cc-191">autodiscover</span></span>  <br/> |<span data-ttu-id="2d3cc-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="2d3cc-193">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="2d3cc-194">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-194">1800</span></span>  <br/> |
    |<span data-ttu-id="2d3cc-195">sip</span><span class="sxs-lookup"><span data-stu-id="2d3cc-195">sip</span></span>  <br/> |<span data-ttu-id="2d3cc-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2d3cc-197">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="2d3cc-198">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-198">1800</span></span>  <br/> |
    |<span data-ttu-id="2d3cc-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2d3cc-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2d3cc-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2d3cc-201">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="2d3cc-202">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-202">1800</span></span>  <br/> |
    |<span data-ttu-id="2d3cc-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2d3cc-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2d3cc-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="2d3cc-205">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="2d3cc-206">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-206">1800</span></span>  <br/> |
    |<span data-ttu-id="2d3cc-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2d3cc-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2d3cc-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="2d3cc-209">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="2d3cc-210">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="2d3cc-212">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="2d3cc-214">添加其他四条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="2d3cc-215">在 **"CNAME** 记录"部分，选择 **(+)** 控件 (添加新 **) ，** 使用表中下一行的值创建记录，然后再次选择"提交"以完成该记录。 </span><span class="sxs-lookup"><span data-stu-id="2d3cc-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="2d3cc-216">重复此过程，直到创建所有五条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2d3cc-217">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2d3cc-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2d3cc-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2d3cc-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d3cc-219">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2d3cc-220">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2d3cc-221">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2d3cc-222">相反，将所需的 Microsoft 值添加到当前记录，以便具有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="2d3cc-223">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="2d3cc-223">Need examples?</span></span> <span data-ttu-id="2d3cc-224">请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="2d3cc-225">若要验证 SPF 记录，可以使用以下[SPF 验证工具之一](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="2d3cc-226">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="2d3cc-227">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2d3cc-228">在" **管理控制台** "页上的 **"最近** 更新的域"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="2d3cc-229">在"**托管 DNS"** 页上 **的"TXT** 记录"区域中，选择 (**+**) 控件 (**添加新) 。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="2d3cc-230">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="2d3cc-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="2d3cc-233">**名称**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-233">**Name**</span></span>|<span data-ttu-id="2d3cc-234">**值**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-234">**Value**</span></span>|<span data-ttu-id="2d3cc-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="2d3cc-236">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="2d3cc-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="2d3cc-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2d3cc-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2d3cc-238">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="2d3cc-239">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="2d3cc-241">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2d3cc-243">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2d3cc-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2d3cc-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2d3cc-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="2d3cc-245">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-245">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="2d3cc-246">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-246">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2d3cc-247">在" **管理控制台** "页上的 **"最近** 更新的域"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="2d3cc-248">在"**托管 DNS"** 页上 **的"SRV** 记录"区域中，选择 (**+**) 控件 (**添加新) 。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="2d3cc-249"> (可能需要向下滚动) </span><span class="sxs-lookup"><span data-stu-id="2d3cc-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="2d3cc-251">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="2d3cc-252">在 **"添加 SRV 记录** "区域中新记录的框中，键入或复制粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="2d3cc-253">**名称**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-253">**Name**</span></span>|<span data-ttu-id="2d3cc-254">**优先级**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-254">**Priority**</span></span>|<span data-ttu-id="2d3cc-255">**权重**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-255">**Weight**</span></span>|<span data-ttu-id="2d3cc-256">**端口**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-256">**Port**</span></span>|<span data-ttu-id="2d3cc-257">**主机**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-257">**Host**</span></span>|<span data-ttu-id="2d3cc-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2d3cc-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="2d3cc-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="2d3cc-260">100</span><span class="sxs-lookup"><span data-stu-id="2d3cc-260">100</span></span>  <br/> |<span data-ttu-id="2d3cc-261">1 </span><span class="sxs-lookup"><span data-stu-id="2d3cc-261">1</span></span>  <br/> |<span data-ttu-id="2d3cc-262">443</span><span class="sxs-lookup"><span data-stu-id="2d3cc-262">443</span></span>  <br/> |<span data-ttu-id="2d3cc-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2d3cc-264">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="2d3cc-265">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-265">1800</span></span>  <br/> |
    |<span data-ttu-id="2d3cc-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="2d3cc-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="2d3cc-267">100</span><span class="sxs-lookup"><span data-stu-id="2d3cc-267">100</span></span>  <br/> |<span data-ttu-id="2d3cc-268">1 </span><span class="sxs-lookup"><span data-stu-id="2d3cc-268">1</span></span>  <br/> |<span data-ttu-id="2d3cc-269">5061</span><span class="sxs-lookup"><span data-stu-id="2d3cc-269">5061</span></span>  <br/> |<span data-ttu-id="2d3cc-270">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="2d3cc-271">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="2d3cc-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="2d3cc-272">1800</span><span class="sxs-lookup"><span data-stu-id="2d3cc-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="2d3cc-274">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="2d3cc-276">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="2d3cc-277">在 **"SRV** 记录"部分，选择 **(+)** 控件 (添加新 **) ，** 使用表中下一行的值创建记录，然后再次选择"提交"以完成该记录。 </span><span class="sxs-lookup"><span data-stu-id="2d3cc-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="2d3cc-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2d3cc-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="2d3cc-279">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="2d3cc-280">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="2d3cc-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

