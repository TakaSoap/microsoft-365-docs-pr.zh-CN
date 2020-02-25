---
title: 在 1&1 IONOS 处创建适用于 Office 365 的 DNS 记录
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 了解如何验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 1&1 IONOS for Office 365 的 DNS 记录。
ms.openlocfilehash: 88a46fa51ac3e259d617d6d6e1a3dbb189c1ee6d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238539"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="eac94-103">在 1&1 IONOS 处创建适用于 Office 365 的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="eac94-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="eac94-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="eac94-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="eac94-105">请注意，1&1 IONOS 不允许域同时具有 MX 记录和顶级自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="eac94-106">这就限制了为 Office 365 配置 Exchange Online 的方式。</span><span class="sxs-lookup"><span data-stu-id="eac94-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="eac94-107">有一种解决方法，但我们建议您在创建子域的过程 1&1 **IONOS 时使用它。**</span><span class="sxs-lookup"><span data-stu-id="eac94-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="eac94-108">>[如果您选择在 1](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)&1 IONOS 管理您自己的 OFFICE 365 DNS 记录，请按照本文中的步骤进行操作，以验证您的域并为电子邮件、Skype For business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="eac94-109">在 1&1 IONOS 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="eac94-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="eac94-110">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="eac94-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac94-111">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="eac94-111">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="eac94-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="eac94-112">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="eac94-113">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="eac94-113">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="eac94-114">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="eac94-114">Add a TXT record for verification</span></span>

<span data-ttu-id="eac94-p103">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="eac94-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac94-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="eac94-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="eac94-119">请按下列步骤操作或[观看视频（从 0:42 开始）](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="eac94-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="eac94-120">若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="eac94-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="eac94-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="eac94-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="eac94-122">选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="eac94-123">在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="eac94-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="eac94-124">在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="eac94-125">在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="eac94-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eac94-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eac94-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="eac94-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="eac94-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="eac94-128">**Type**</span></span> <br/> |<span data-ttu-id="eac94-129">**前缀**</span><span class="sxs-lookup"><span data-stu-id="eac94-129">**Prefix**</span></span> <br/> |<span data-ttu-id="eac94-130">**名称值**</span><span class="sxs-lookup"><span data-stu-id="eac94-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="eac94-131">TXT</span><span class="sxs-lookup"><span data-stu-id="eac94-131">TXT</span></span>  <br/> |<span data-ttu-id="eac94-132">（将此字段留空）</span><span class="sxs-lookup"><span data-stu-id="eac94-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="eac94-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="eac94-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="eac94-134">注意：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="eac94-134">NOTE: This is an example.</span></span> <span data-ttu-id="eac94-135">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="eac94-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="eac94-136">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="eac94-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="eac94-137">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eac94-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="eac94-138">再次选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="eac94-139">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="eac94-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="eac94-140">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="eac94-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="eac94-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="eac94-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="eac94-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="eac94-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="eac94-143">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="eac94-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="eac94-144">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="eac94-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="eac94-145">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="eac94-146">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eac94-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="eac94-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="eac94-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="eac94-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="eac94-149">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="eac94-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="eac94-150">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="eac94-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="eac94-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="eac94-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="eac94-152">请执行以下步骤或[观看视频（从3:22 开始）](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="eac94-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac94-153">如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="eac94-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="eac94-154">若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="eac94-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="eac94-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="eac94-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="eac94-156">选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="eac94-157">在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="eac94-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="eac94-158">在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="eac94-159">在 " **MX 记录**" 部分的 "\* \* 邮件交换器（MX 记录） \* \*" 区域中，选择 "**其他邮件服务器**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="eac94-160">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eac94-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="eac94-161">![1&amp;1-BP-配置-2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-161">![1&amp;1-BP-Configure-2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="eac94-162">如果已列出任何 MX 记录，请选择该记录，然后按键盘上的**delete**键，将其删除。</span><span class="sxs-lookup"><span data-stu-id="eac94-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="eac94-163">（如果没有已列出的 MX 记录，请继续执行下一步。）</span><span class="sxs-lookup"><span data-stu-id="eac94-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="eac94-164">![1&amp;1-BP-配置-2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-164">![1&amp;1-BP-Configure-2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="eac94-165">在 " **MX 1** " 记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="eac94-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="eac94-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="eac94-166">**MX 1**</span></span>|<span data-ttu-id="eac94-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="eac94-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="eac94-168">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eac94-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="eac94-169">注意：从 Office \<365 帐户中\>获取你的域密钥。</span><span class="sxs-lookup"><span data-stu-id="eac94-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> <span data-ttu-id="eac94-170">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="eac94-170">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="eac94-171">10 </span><span class="sxs-lookup"><span data-stu-id="eac94-171">10</span></span>  <br/> <span data-ttu-id="eac94-172">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="eac94-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1和 1-配置2和3](../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="eac94-174">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eac94-174">Select **Save**.</span></span><br/><span data-ttu-id="eac94-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eac94-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="eac94-176">![1&amp;1-BP-配置-2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-176">![1&amp;1-BP-Configure-2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="eac94-177">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="eac94-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="eac94-178">![在 "编辑 DNS 设置" 对话框中选择 "是"](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-178">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="eac94-179">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="eac94-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="eac94-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="eac94-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="eac94-181">1&1 IONOS 需要解决方法，以便您可以将 MX 记录与 Office 365 电子邮件服务所需的 CNAME 记录结合使用。</span><span class="sxs-lookup"><span data-stu-id="eac94-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="eac94-182">此替代方法要求您在 1&1 IONOS 创建一组子域，并将其分配给 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eac94-183">在开始此过程之前，请确保至少有两个可用的子域。</span><span class="sxs-lookup"><span data-stu-id="eac94-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="eac94-184">仅当您已经有在 1&1 IONOS 创建子域的经验时，才建议使用此解决方案。</span><span class="sxs-lookup"><span data-stu-id="eac94-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="eac94-185">基本 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="eac94-185">Basic CNAME records</span></span>

<span data-ttu-id="eac94-186">请执行以下步骤或[观看视频（从3:57 开始）](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="eac94-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac94-187">如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="eac94-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="eac94-188">若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="eac94-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="eac94-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="eac94-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="eac94-190">选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="eac94-191">在 "**域中心**" 页上，找到要更新的域，然后选择 "**管理子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="eac94-192">![1&amp;1-BP-配置-3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-192">![1&amp;1-BP-Configure-3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="eac94-193">现在，您将创建两个子域并为每个子域设置一个**别名**值。</span><span class="sxs-lookup"><span data-stu-id="eac94-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="eac94-194">（这是必需的，因为 1&1 IONOS 仅支持一个顶级 CNAME 记录，但 Office 365 需要多个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="eac94-195">首先，创建自动发现子域。</span><span class="sxs-lookup"><span data-stu-id="eac94-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="eac94-196">在 "**子域概述**" 部分，选择 "**创建子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-配置-3-1](../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="eac94-198">在 "为新子域**创建子域**" 框中，键入或复制并仅粘贴下表中的 "**创建子域**" 值。</span><span class="sxs-lookup"><span data-stu-id="eac94-198">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="eac94-199">（将在后续步骤中添加**别名**值。）</span><span class="sxs-lookup"><span data-stu-id="eac94-199">(You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="eac94-200">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="eac94-200">**Create Subdomain**</span></span>|<span data-ttu-id="eac94-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eac94-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="eac94-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eac94-202">autodiscover</span></span>  <br/> |<span data-ttu-id="eac94-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eac94-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-配置-3-2](../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="eac94-205">选择 "**创建子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="eac94-206">![1&amp;1-BP-配置-3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-206">![1&amp;1-BP-Configure-3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="eac94-207">在 "**子域概述**" 部分，找到刚创建的 "**自动发现**" 子域，然后为该子域选择 **"面板" （v）** 控件。</span><span class="sxs-lookup"><span data-stu-id="eac94-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="eac94-208">![1&amp;1-BP-配置-3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-208">![1&amp;1-BP-Configure-3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="eac94-209">在 "**子域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="eac94-210">![1&amp;1-BP-配置-3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-210">![1&amp;1-BP-Configure-3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="eac94-211">在 " **A/AAAA 记录（IP 地址）** " 部分的 " **IP 地址（A 记录）** " 区域中，选择 " **CNAME**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="eac94-212">![1&amp;1-BP-配置-3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-212">![1&amp;1-BP-Configure-3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="eac94-213">在 "**别名：** " 框中，键入或复制并仅粘贴下表中的**别名**值。</span><span class="sxs-lookup"><span data-stu-id="eac94-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="eac94-214">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="eac94-214">**Create Subdomain**</span></span>|<span data-ttu-id="eac94-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eac94-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="eac94-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eac94-216">autodiscover</span></span>  <br/> |<span data-ttu-id="eac94-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eac94-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-配置-3-7](../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="eac94-219">选中 "**我知道的已知**免责声明" 对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="eac94-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="eac94-220">![1&amp;1-BP-配置-3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-220">![1&amp;1-BP-Configure-3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="eac94-221">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eac94-221">Select **Save**.</span></span><br/><span data-ttu-id="eac94-222">![1&amp;1-BP-配置-3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-222">![1&amp;1-BP-Configure-3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="eac94-223">其他 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="eac94-223">Additional CNAME records</span></span>

<span data-ttu-id="eac94-224">以下过程中创建的其他 CNAME 记录将启用 Skype for Business Online 服务。</span><span class="sxs-lookup"><span data-stu-id="eac94-224">The additional CNAME records created in the following procedure enable Skype for Business Online services.</span></span> <span data-ttu-id="eac94-225">您将使用用于创建两个已创建的 CNAME 记录的相同步骤。</span><span class="sxs-lookup"><span data-stu-id="eac94-225">You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="eac94-226">创建第三个子域（Lyncdiscover.）。</span><span class="sxs-lookup"><span data-stu-id="eac94-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="eac94-227">在 "**子域概述**" 部分，选择 "**创建子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="eac94-228">在 "为新子域**创建子域**" 框中，键入或复制并仅粘贴下表中的 "**创建子域**" 值。</span><span class="sxs-lookup"><span data-stu-id="eac94-228">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="eac94-229">（将在后续步骤中添加**别名**值。）</span><span class="sxs-lookup"><span data-stu-id="eac94-229">(You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="eac94-230">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="eac94-230">**Create Subdomain**</span></span>|<span data-ttu-id="eac94-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eac94-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="eac94-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eac94-232">lyncdiscover</span></span>   |<span data-ttu-id="eac94-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eac94-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="eac94-234">选择 "**创建子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="eac94-235">在 "**域中心**" 页上，选择 "**管理子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="eac94-236">在 "**子域概述**" 部分，找到您刚创建的**lyncdiscover.** 子域，然后为该子域选择 **"面板" （v）** 控件。</span><span class="sxs-lookup"><span data-stu-id="eac94-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="eac94-237">在 "**子域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="eac94-238">在 " **A/AAAA 记录（IP 地址）** " 部分的 "\* \* IP 地址（A Record） \* \*" 区域中，选择 " **CNAME**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="eac94-239">在 "**别名：** " 框中，键入或复制并仅粘贴下表中的**别名**值。</span><span class="sxs-lookup"><span data-stu-id="eac94-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="eac94-240">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="eac94-240">**Create Subdomain**</span></span>|<span data-ttu-id="eac94-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eac94-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="eac94-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eac94-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="eac94-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eac94-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="eac94-244">选中 "**我知道**免责声明" 复选框，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="eac94-245">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="eac94-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="eac94-246">创建第四个子域（SIP）：</span><span class="sxs-lookup"><span data-stu-id="eac94-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="eac94-247">在 "**子域概述**" 部分，选择 "**创建子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="eac94-248">在 "为新子域**创建子域**" 框中，键入或复制并仅粘贴下表中的 "**创建子域**" 值。</span><span class="sxs-lookup"><span data-stu-id="eac94-248">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="eac94-249">（将在后续步骤中添加**别名**值。）</span><span class="sxs-lookup"><span data-stu-id="eac94-249">(You'll add the **Alias** value in a later step.)</span></span> <br/>
    
    |<span data-ttu-id="eac94-250">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="eac94-250">**Create Subdomain**</span></span>|<span data-ttu-id="eac94-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eac94-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="eac94-252">sip</span><span class="sxs-lookup"><span data-stu-id="eac94-252">sip</span></span>  <br/> |<span data-ttu-id="eac94-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eac94-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="eac94-254">选择 "**创建子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="eac94-255">在 "**域中心**" 页上，选择 "**管理子域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="eac94-256">在 "**子域概述**" 部分，找到您刚创建的**sip**子域，然后选择该子域的 **"面板" （v）** 控制。</span><span class="sxs-lookup"><span data-stu-id="eac94-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="eac94-257">在 "**子域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="eac94-258">在 " **A/AAAA 记录（IP 地址）** " 部分的 "\* \* IP 地址（A Record） \* \*" 区域中，选择 " **CNAME**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="eac94-259">在 "**别名：** " 框中，键入或复制并仅粘贴下表中的**别名**值。</span><span class="sxs-lookup"><span data-stu-id="eac94-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="eac94-260">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="eac94-260">**Create Subdomain**</span></span>|<span data-ttu-id="eac94-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eac94-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="eac94-262">sip</span><span class="sxs-lookup"><span data-stu-id="eac94-262">sip</span></span>  <br/> |<span data-ttu-id="eac94-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eac94-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="eac94-264">选中 "**我知道**免责声明" 复选框，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="eac94-265">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="eac94-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="eac94-266">MDM 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="eac94-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eac94-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eac94-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="eac94-268">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="eac94-268">**Create Subdomain**</span></span>|<span data-ttu-id="eac94-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="eac94-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eac94-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eac94-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="eac94-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="eac94-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="eac94-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eac94-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="eac94-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="eac94-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eac94-274">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="eac94-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eac94-275">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="eac94-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="eac94-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="eac94-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="eac94-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="eac94-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="eac94-278">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="eac94-279">Need examples?</span><span class="sxs-lookup"><span data-stu-id="eac94-279">Need examples?</span></span> <span data-ttu-id="eac94-280">查看[Office 365 的这些外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="eac94-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="eac94-281">若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="eac94-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="eac94-282">请执行以下步骤或[观看视频（从5:09 开始）](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="eac94-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac94-283">如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="eac94-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="eac94-284">若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="eac94-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="eac94-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="eac94-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="eac94-286">选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="eac94-287">在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （**v**）控制。</span><span class="sxs-lookup"><span data-stu-id="eac94-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="eac94-288">在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="eac94-289">在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="eac94-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="eac94-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="eac94-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eac94-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="eac94-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="eac94-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="eac94-293">**类型**</span><span class="sxs-lookup"><span data-stu-id="eac94-293">**Type**</span></span>|<span data-ttu-id="eac94-294">**前缀**</span><span class="sxs-lookup"><span data-stu-id="eac94-294">**Prefix**</span></span>|<span data-ttu-id="eac94-295">**名称值**</span><span class="sxs-lookup"><span data-stu-id="eac94-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eac94-296">TXT</span><span class="sxs-lookup"><span data-stu-id="eac94-296">TXT</span></span>  <br/> |<span data-ttu-id="eac94-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="eac94-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eac94-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="eac94-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="eac94-299">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="eac94-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT 记录](../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="eac94-301">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eac94-301">Select **Save**.</span></span><br/><span data-ttu-id="eac94-302">![添加记录](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-302">![Add record](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="eac94-303">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eac94-303">Select **Save**.</span></span><br/><span data-ttu-id="eac94-304">![保存记录](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-304">![Save record](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="eac94-305">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="eac94-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="eac94-306">![在 "编辑 DNS 设置" 对话框中选择 "是"](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-306">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="eac94-307">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="eac94-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="eac94-308">请执行以下步骤或[观看视频（从5:51 开始）](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="eac94-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eac94-309">如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="eac94-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="eac94-310">若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。</span><span class="sxs-lookup"><span data-stu-id="eac94-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="eac94-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="eac94-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="eac94-312">选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="eac94-313">在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。</span><span class="sxs-lookup"><span data-stu-id="eac94-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="eac94-314">在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="eac94-315">在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="eac94-316">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="eac94-317">在 "**添加记录**" 区域中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="eac94-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="eac94-318">（从下拉列表中选择 "**类型**" 和 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="eac94-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="eac94-319">**类型**</span><span class="sxs-lookup"><span data-stu-id="eac94-319">**Type**</span></span>|<span data-ttu-id="eac94-320">**服务**</span><span class="sxs-lookup"><span data-stu-id="eac94-320">**Service**</span></span>|<span data-ttu-id="eac94-321">**协议**</span><span class="sxs-lookup"><span data-stu-id="eac94-321">**Protocol**</span></span>|<span data-ttu-id="eac94-322">**名称**</span><span class="sxs-lookup"><span data-stu-id="eac94-322">**Name**</span></span>|<span data-ttu-id="eac94-323">**主机**</span><span class="sxs-lookup"><span data-stu-id="eac94-323">**Host**</span></span>|<span data-ttu-id="eac94-324">**优先级**</span><span class="sxs-lookup"><span data-stu-id="eac94-324">**Priority**</span></span>|<span data-ttu-id="eac94-325">**权重**</span><span class="sxs-lookup"><span data-stu-id="eac94-325">**Weight**</span></span>|<span data-ttu-id="eac94-326">**端口**</span><span class="sxs-lookup"><span data-stu-id="eac94-326">**Port**</span></span>|<span data-ttu-id="eac94-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eac94-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eac94-328">SRV</span><span class="sxs-lookup"><span data-stu-id="eac94-328">SRV</span></span>  <br/> |<span data-ttu-id="eac94-329">sip</span><span class="sxs-lookup"><span data-stu-id="eac94-329">sip</span></span>  <br/> |<span data-ttu-id="eac94-330">tls</span><span class="sxs-lookup"><span data-stu-id="eac94-330">tls</span></span>  <br/> |<span data-ttu-id="eac94-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="eac94-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eac94-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eac94-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="eac94-333">100</span><span class="sxs-lookup"><span data-stu-id="eac94-333">100</span></span>  <br/> |<span data-ttu-id="eac94-334">1</span><span class="sxs-lookup"><span data-stu-id="eac94-334">1</span></span>  <br/> |<span data-ttu-id="eac94-335">443</span><span class="sxs-lookup"><span data-stu-id="eac94-335">443</span></span>  <br/> |<span data-ttu-id="eac94-336">3600（1个 h）</span><span class="sxs-lookup"><span data-stu-id="eac94-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="eac94-337">SRV</span><span class="sxs-lookup"><span data-stu-id="eac94-337">SRV</span></span>  <br/> |<span data-ttu-id="eac94-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="eac94-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="eac94-339">tcp</span><span class="sxs-lookup"><span data-stu-id="eac94-339">tcp</span></span>  <br/> |<span data-ttu-id="eac94-340">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="eac94-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eac94-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="eac94-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="eac94-342">100</span><span class="sxs-lookup"><span data-stu-id="eac94-342">100</span></span>  <br/> |<span data-ttu-id="eac94-343">1</span><span class="sxs-lookup"><span data-stu-id="eac94-343">1</span></span>  <br/> |<span data-ttu-id="eac94-344">5061</span><span class="sxs-lookup"><span data-stu-id="eac94-344">5061</span></span>  <br/> |<span data-ttu-id="eac94-345">3600（1个 h）</span><span class="sxs-lookup"><span data-stu-id="eac94-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-配置-5-1](../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="eac94-347">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eac94-347">Select **Save**.</span></span> <br/><span data-ttu-id="eac94-348">![1&amp;1-BP-配置-5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-348">![1&amp;1-BP-Configure-5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="eac94-349">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eac94-349">Select **Save**.</span></span> <br/><span data-ttu-id="eac94-350">![1&amp;1-BP-配置-5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-350">![1&amp;1-BP-Configure-5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="eac94-351">在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="eac94-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="eac94-352">![在 "编辑 DNS 设置" 对话框中选择 "是"](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="eac94-352">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="eac94-353">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="eac94-354">在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="eac94-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="eac94-355">在 "**添加记录**" 区域中，使用表中其他行的值创建记录，然后再次选择 "**添加**"、"**保存**" 和 **"是"** 以完成记录。</span><span class="sxs-lookup"><span data-stu-id="eac94-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="eac94-356">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="eac94-356">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="eac94-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="eac94-357">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="eac94-358">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="eac94-358">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
