---
title: 在 DNSMadeEasy 上为 Office 365 创建 DNS 记录
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: 了解如何在 DNSMadeEasy for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240721"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="c0a69-103">在 DNSMadeEasy 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c0a69-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="c0a69-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="c0a69-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c0a69-105">如果 DNSMadeEasy 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c0a69-106">在 DNSMadeEasy 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="c0a69-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="c0a69-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="c0a69-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0a69-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c0a69-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c0a69-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c0a69-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c0a69-110">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c0a69-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c0a69-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="c0a69-111">Add a TXT record for verification</span></span>
<span data-ttu-id="c0a69-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a69-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c0a69-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="c0a69-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0a69-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="c0a69-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c0a69-117">对于 DNSMadeEasy 帐户，添加的域是从单独的域注册机构购买的。</span><span class="sxs-lookup"><span data-stu-id="c0a69-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="c0a69-118">DNSMadeEasy 不提供域注册服务。</span><span class="sxs-lookup"><span data-stu-id="c0a69-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="c0a69-119">您在 DNSMadeEasy 登录并创建 DNS 记录的能力是足够的所有权证明。</span><span class="sxs-lookup"><span data-stu-id="c0a69-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="c0a69-120">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="c0a69-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="c0a69-121">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c0a69-122">在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="c0a69-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c0a69-123">在 "**托管 DNS** " 页面上的 " **TXT 记录**" 区域中， **+** 选择 "（"）控件（**添加新**控件）。</span><span class="sxs-lookup"><span data-stu-id="c0a69-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="c0a69-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c0a69-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="c0a69-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c0a69-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="c0a69-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="c0a69-126">**Name**</span></span> <br/> |<span data-ttu-id="c0a69-127">**值**</span><span class="sxs-lookup"><span data-stu-id="c0a69-127">**Value**</span></span> <br/> |<span data-ttu-id="c0a69-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c0a69-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="c0a69-129">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="c0a69-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c0a69-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c0a69-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c0a69-131">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="c0a69-131">**Note:** This is an example.</span></span> <span data-ttu-id="c0a69-132">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="c0a69-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="c0a69-133">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="c0a69-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c0a69-134">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="c0a69-135">选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="c0a69-136">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="c0a69-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c0a69-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="c0a69-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c0a69-138">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="c0a69-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c0a69-139">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="c0a69-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c0a69-140">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="c0a69-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c0a69-141">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c0a69-142">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c0a69-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c0a69-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c0a69-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c0a69-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c0a69-145">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c0a69-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="c0a69-146">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="c0a69-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="c0a69-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a69-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c0a69-148">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="c0a69-148">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="c0a69-149">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-149">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c0a69-150">在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="c0a69-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="c0a69-151">在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="c0a69-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-配置-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="c0a69-153">在 "**托管 DNS** " 页面上的 " **MX 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。</span><span class="sxs-lookup"><span data-stu-id="c0a69-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c0a69-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c0a69-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-配置-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="c0a69-156">在 "**添加 MX 记录**" 区域中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="c0a69-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c0a69-157">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c0a69-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="c0a69-158">**名称**</span><span class="sxs-lookup"><span data-stu-id="c0a69-158">**Name**</span></span>|<span data-ttu-id="c0a69-159">**服务器**</span><span class="sxs-lookup"><span data-stu-id="c0a69-159">**Server**</span></span>|<span data-ttu-id="c0a69-160">**MX 级别**</span><span class="sxs-lookup"><span data-stu-id="c0a69-160">**MX Level**</span></span>|<span data-ttu-id="c0a69-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c0a69-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c0a69-162">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="c0a69-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="c0a69-163">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c0a69-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c0a69-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c0a69-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="c0a69-165">**注意：** 从 Office \<365 帐户中获取你的*域密钥*\> 。</span><span class="sxs-lookup"><span data-stu-id="c0a69-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <span data-ttu-id="c0a69-166">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="c0a69-166">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="c0a69-167">10 </span><span class="sxs-lookup"><span data-stu-id="c0a69-167">10</span></span>  <br/> <span data-ttu-id="c0a69-168">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="c0a69-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="c0a69-169">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-配置-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="c0a69-171">选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-配置-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="c0a69-173">如果 " **Mx 记录**" 一节中列出了任何其他 MX 记录，请通过选择每条记录将其删除。</span><span class="sxs-lookup"><span data-stu-id="c0a69-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-配置-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="c0a69-175">选择所有记录后，选择 "**删除所选**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-配置-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="c0a69-177">在 "**删除 MX 记录**" 对话框中，选择 "**删除**" 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="c0a69-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-配置-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="c0a69-179">添加 Office 365 所需的五个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="c0a69-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="c0a69-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a69-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c0a69-181">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="c0a69-181">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="c0a69-182">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-182">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c0a69-183">在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="c0a69-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c0a69-184">在 "**托管 DNS** " 页面上的 " **CNAME 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。</span><span class="sxs-lookup"><span data-stu-id="c0a69-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c0a69-185">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c0a69-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-配置-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="c0a69-187">添加五个 CNAME 记录中的第一个。</span><span class="sxs-lookup"><span data-stu-id="c0a69-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="c0a69-188">在 "**添加 CNAME 记录**" 区域中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="c0a69-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="c0a69-189">**名称**</span><span class="sxs-lookup"><span data-stu-id="c0a69-189">**Name**</span></span>|<span data-ttu-id="c0a69-190">**别名**</span><span class="sxs-lookup"><span data-stu-id="c0a69-190">**Alias to**</span></span>|<span data-ttu-id="c0a69-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c0a69-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="c0a69-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c0a69-192">autodiscover</span></span>  <br/> |<span data-ttu-id="c0a69-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c0a69-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="c0a69-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c0a69-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c0a69-195">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-195">1800</span></span>  <br/> |
    |<span data-ttu-id="c0a69-196">sip</span><span class="sxs-lookup"><span data-stu-id="c0a69-196">sip</span></span>  <br/> |<span data-ttu-id="c0a69-197">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c0a69-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c0a69-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c0a69-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c0a69-199">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-199">1800</span></span>  <br/> |
    |<span data-ttu-id="c0a69-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c0a69-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c0a69-201">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c0a69-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c0a69-202">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c0a69-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c0a69-203">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-203">1800</span></span>  <br/> |
    |<span data-ttu-id="c0a69-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c0a69-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c0a69-205">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="c0a69-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="c0a69-206">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c0a69-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c0a69-207">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-207">1800</span></span>  <br/> |
    |<span data-ttu-id="c0a69-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c0a69-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c0a69-209">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c0a69-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="c0a69-210">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="c0a69-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c0a69-211">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-配置-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="c0a69-213">选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-配置-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="c0a69-215">添加其他四条 CNAME 记录中的每一个。</span><span class="sxs-lookup"><span data-stu-id="c0a69-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="c0a69-216">在 " **CNAME 记录**" 部分中，选择 " **（** **添加新**控件）"，使用表中下一行的值创建记录，然后再次选择 "**提交**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="c0a69-217">重复此过程，直到创建完所有五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c0a69-218">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c0a69-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c0a69-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a69-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0a69-220">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="c0a69-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c0a69-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="c0a69-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c0a69-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0a69-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="c0a69-223">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="c0a69-224">Need examples?</span><span class="sxs-lookup"><span data-stu-id="c0a69-224">Need examples?</span></span> <span data-ttu-id="c0a69-225">查看[Office 365 的这些外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="c0a69-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="c0a69-226">若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="c0a69-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="c0a69-227">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="c0a69-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="c0a69-228">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c0a69-229">在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="c0a69-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c0a69-230">在 "**托管 DNS** " 页面上的 " **TXT 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。</span><span class="sxs-lookup"><span data-stu-id="c0a69-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c0a69-231">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c0a69-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-配置-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="c0a69-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c0a69-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="c0a69-234">**名称**</span><span class="sxs-lookup"><span data-stu-id="c0a69-234">**Name**</span></span>|<span data-ttu-id="c0a69-235">**值**</span><span class="sxs-lookup"><span data-stu-id="c0a69-235">**Value**</span></span>|<span data-ttu-id="c0a69-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c0a69-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="c0a69-237">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="c0a69-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c0a69-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c0a69-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c0a69-239">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="c0a69-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="c0a69-240">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-配置-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="c0a69-242">选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-配置-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="c0a69-244">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="c0a69-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="c0a69-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c0a69-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c0a69-246">要开始，请使用[此链接](https://cp.dnsmadeeasy.com/)转到您在 DNSMadeEasy 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="c0a69-246">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="c0a69-247">系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-247">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="c0a69-248">在 "**管理控制台**" 页上的 "**最近更新的域**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="c0a69-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="c0a69-249">在 "**托管 DNS** " 页面上的 " **SRV 记录**" 区域中，选择 " **（+）** " 控件（**添加新**控件）。</span><span class="sxs-lookup"><span data-stu-id="c0a69-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="c0a69-250">（您可能需要向下滚动）</span><span class="sxs-lookup"><span data-stu-id="c0a69-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-配置-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="c0a69-252">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="c0a69-253">在 "**添加 SRV 记录**" 区域中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="c0a69-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="c0a69-254">**名称**</span><span class="sxs-lookup"><span data-stu-id="c0a69-254">**Name**</span></span>|<span data-ttu-id="c0a69-255">**优先级**</span><span class="sxs-lookup"><span data-stu-id="c0a69-255">**Priority**</span></span>|<span data-ttu-id="c0a69-256">**权重**</span><span class="sxs-lookup"><span data-stu-id="c0a69-256">**Weight**</span></span>|<span data-ttu-id="c0a69-257">**端口**</span><span class="sxs-lookup"><span data-stu-id="c0a69-257">**Port**</span></span>|<span data-ttu-id="c0a69-258">**主机**</span><span class="sxs-lookup"><span data-stu-id="c0a69-258">**Host**</span></span>|<span data-ttu-id="c0a69-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c0a69-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c0a69-260">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="c0a69-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="c0a69-261">100</span><span class="sxs-lookup"><span data-stu-id="c0a69-261">100</span></span>  <br/> |<span data-ttu-id="c0a69-262">1</span><span class="sxs-lookup"><span data-stu-id="c0a69-262">1</span></span>  <br/> |<span data-ttu-id="c0a69-263">443</span><span class="sxs-lookup"><span data-stu-id="c0a69-263">443</span></span>  <br/> |<span data-ttu-id="c0a69-264">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c0a69-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c0a69-265">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c0a69-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c0a69-266">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-266">1800</span></span>  <br/> |
    |<span data-ttu-id="c0a69-267">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="c0a69-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="c0a69-268">100</span><span class="sxs-lookup"><span data-stu-id="c0a69-268">100</span></span>  <br/> |<span data-ttu-id="c0a69-269">1</span><span class="sxs-lookup"><span data-stu-id="c0a69-269">1</span></span>  <br/> |<span data-ttu-id="c0a69-270">5061</span><span class="sxs-lookup"><span data-stu-id="c0a69-270">5061</span></span>  <br/> |<span data-ttu-id="c0a69-271">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c0a69-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="c0a69-272">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="c0a69-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c0a69-273">1800</span><span class="sxs-lookup"><span data-stu-id="c0a69-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-配置-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="c0a69-275">选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="c0a69-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-配置-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="c0a69-277">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="c0a69-278">在 " **SRV 记录**" 部分中，选择 " **（** **添加新**控件）"，使用表中下一行的值创建记录，然后再次选择 "**提交**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="c0a69-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c0a69-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c0a69-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c0a69-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c0a69-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c0a69-281">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c0a69-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

