---
title: 在 Freenom 上为 Office 365 创建 DNS 记录
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 了解如何在 Freenom for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 16348eb03a6507e15d31d5c183bd91125d0236f6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350663"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a><span data-ttu-id="58f52-103">在 Freenom 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="58f52-103">Create DNS records at Freenom for Office 365</span></span>

<span data-ttu-id="58f52-104">如果找不到您要查找的内容，[请检查域 FAQ](../setup/domains-faq.md) 。</span><span class="sxs-lookup"><span data-stu-id="58f52-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="58f52-105">Freenom 网站不支持 SRV 记录，这意味着多个 Skype for Business Online 和 Outlook Web App 功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="58f52-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="58f52-106">无论使用哪种 Office 365 计划，都有显著的服务限制，您可能想要切换到其他 DNS 承载提供程序。</span><span class="sxs-lookup"><span data-stu-id="58f52-106">No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="58f52-107">如果考虑到服务限制，您可以选择在 Freenom 管理您自己的 Office 365 DNS 记录，请按照本文中的步骤验证您的域并为电子邮件和其他服务设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="58f52-107">If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="58f52-108">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="58f52-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="58f52-p102">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="58f52-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="58f52-112">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="58f52-112">Add a TXT record for verification</span></span>
<span data-ttu-id="58f52-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="58f52-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="58f52-p103">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="58f52-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="58f52-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="58f52-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="58f52-118">若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="58f52-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="58f52-119">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="58f52-119">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="58f52-121">选择 "**服务**"，然后选择 **"我的域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="58f52-123">对于要编辑的域，选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="58f52-125">选择 "**管理 FREENOM DNS**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom 管理 Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="58f52-127">在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **TXT** "。</span><span class="sxs-lookup"><span data-stu-id="58f52-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 添加记录类型 TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="58f52-129">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="58f52-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="58f52-130">**名称**</span><span class="sxs-lookup"><span data-stu-id="58f52-130">**Name**</span></span>|<span data-ttu-id="58f52-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="58f52-131">**Type**</span></span>|<span data-ttu-id="58f52-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="58f52-132">**TTL**</span></span>|<span data-ttu-id="58f52-133">**目标**</span><span class="sxs-lookup"><span data-stu-id="58f52-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58f52-134">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="58f52-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="58f52-135">TXT</span><span class="sxs-lookup"><span data-stu-id="58f52-135">TXT</span></span>  <br/> |<span data-ttu-id="58f52-136">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-137">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="58f52-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="58f52-138">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="58f52-138">**Note:** This is an example.</span></span> <span data-ttu-id="58f52-139">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="58f52-139">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="58f52-140">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="58f52-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![用于验证的 Freenom TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="58f52-142">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 记录保存更改](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="58f52-144">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="58f52-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="58f52-145">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="58f52-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="58f52-146">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="58f52-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="58f52-147">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="58f52-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="58f52-148">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="58f52-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="58f52-149">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="58f52-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="58f52-150">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="58f52-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="58f52-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="58f52-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="58f52-154">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="58f52-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="58f52-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="58f52-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="58f52-156">若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="58f52-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="58f52-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="58f52-157">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="58f52-159">选择 "**服务**"，然后选择 **"我的域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="58f52-161">对于要编辑的域，选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="58f52-163">将您的域的名称设置为默认的 Freenom 名称服务器。</span><span class="sxs-lookup"><span data-stu-id="58f52-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="58f52-164">选择 "**管理工具**"，然后选择 "**名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom 名称服务器设置](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="58f52-166">请确保已选择 "**使用默认名称服务器**"，然后选择 "**更改名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom 更改名称服务器](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="58f52-168">选择 "**管理 FREENOM DNS**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="58f52-170">在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **MX** "。</span><span class="sxs-lookup"><span data-stu-id="58f52-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom 添加记录类型 MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="58f52-172">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="58f52-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="58f52-173">**名称**</span><span class="sxs-lookup"><span data-stu-id="58f52-173">**Name**</span></span>|<span data-ttu-id="58f52-174">**Type**</span><span class="sxs-lookup"><span data-stu-id="58f52-174">**Type**</span></span>|<span data-ttu-id="58f52-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="58f52-175">**TTL**</span></span>|<span data-ttu-id="58f52-176">**目标**</span><span class="sxs-lookup"><span data-stu-id="58f52-176">**Target**</span></span>|<span data-ttu-id="58f52-177">**优先级**</span><span class="sxs-lookup"><span data-stu-id="58f52-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58f52-178">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="58f52-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="58f52-179">MX （邮件交换器）</span><span class="sxs-lookup"><span data-stu-id="58f52-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="58f52-180">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-181">\<域密钥\>. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="58f52-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="58f52-182">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="58f52-182">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   <span data-ttu-id="58f52-183">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="58f52-183">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="58f52-184">10 </span><span class="sxs-lookup"><span data-stu-id="58f52-184">10</span></span>  <br/> <span data-ttu-id="58f52-185">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span><span class="sxs-lookup"><span data-stu-id="58f52-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX 记录](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="58f52-187">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX 记录保存更改](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="58f52-189">如果有任何其他 MX 记录，请将它们全部删除。</span><span class="sxs-lookup"><span data-stu-id="58f52-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="58f52-190">对于每个记录，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-190">For each record, select **Delete**.</span></span> <span data-ttu-id="58f52-191">当**您确实要删除此条目时？** 出现时，选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="58f52-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="58f52-192">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="58f52-192">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="58f52-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="58f52-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="58f52-194">若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="58f52-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="58f52-195">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="58f52-195">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="58f52-197">选择 "**服务**"，然后选择 **"我的域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="58f52-199">对于要编辑的域，选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="58f52-201">选择 "**管理 FREENOM DNS**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="58f52-203">在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **CNAME** "。</span><span class="sxs-lookup"><span data-stu-id="58f52-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom 添加记录类型 CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="58f52-205">创建第一个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="58f52-205">Create the first CNAME record.</span></span> <span data-ttu-id="58f52-206">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="58f52-206">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="58f52-207">**名称**</span><span class="sxs-lookup"><span data-stu-id="58f52-207">**Name**</span></span>|<span data-ttu-id="58f52-208">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="58f52-208">**Record type**</span></span>|<span data-ttu-id="58f52-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="58f52-209">**TTL**</span></span>|<span data-ttu-id="58f52-210">**目标**</span><span class="sxs-lookup"><span data-stu-id="58f52-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58f52-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="58f52-211">autodiscover</span></span>  <br/> |<span data-ttu-id="58f52-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="58f52-212">CNAME</span></span>  <br/> |<span data-ttu-id="58f52-213">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="58f52-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="58f52-215">sip</span><span class="sxs-lookup"><span data-stu-id="58f52-215">sip</span></span>  <br/> |<span data-ttu-id="58f52-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="58f52-216">CNAME</span></span>  <br/> |<span data-ttu-id="58f52-217">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="58f52-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="58f52-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="58f52-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="58f52-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="58f52-220">CNAME</span></span>  <br/> |<span data-ttu-id="58f52-221">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="58f52-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="58f52-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="58f52-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="58f52-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="58f52-224">CNAME</span></span>  <br/> |<span data-ttu-id="58f52-225">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="58f52-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="58f52-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="58f52-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="58f52-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="58f52-228">CNAME</span></span>  <br/> |<span data-ttu-id="58f52-229">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="58f52-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="58f52-232">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME 保存更改](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="58f52-234">重复前面的步骤以创建其他五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="58f52-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="58f52-235">对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。</span><span class="sxs-lookup"><span data-stu-id="58f52-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="58f52-236">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="58f52-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="58f52-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="58f52-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="58f52-238">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="58f52-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="58f52-239">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="58f52-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="58f52-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="58f52-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="58f52-241">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="58f52-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="58f52-242">若要开始，请使用[此链接](https://my.freenom.com/)转到 Freenom 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="58f52-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="58f52-243">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="58f52-243">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录名](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="58f52-245">选择 "**服务**"，然后选择 **"我的域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom 选择服务和我的域](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="58f52-247">对于要编辑的域，选择 "**管理域**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom 选择管理域](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="58f52-249">选择 "**管理 FREENOM DNS**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="58f52-251">在 "**添加记录**" 下的 "**类型**" 列中，从菜单中选择 " **TXT** "。</span><span class="sxs-lookup"><span data-stu-id="58f52-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 添加记录类型 TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="58f52-253">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="58f52-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="58f52-254">**名称**</span><span class="sxs-lookup"><span data-stu-id="58f52-254">**Name**</span></span>|<span data-ttu-id="58f52-255">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="58f52-255">**Record type**</span></span>|<span data-ttu-id="58f52-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="58f52-256">**TTL**</span></span>|<span data-ttu-id="58f52-257">**目标**</span><span class="sxs-lookup"><span data-stu-id="58f52-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="58f52-258">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="58f52-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="58f52-259">TXT</span><span class="sxs-lookup"><span data-stu-id="58f52-259">TXT</span></span>  <br/> |<span data-ttu-id="58f52-260">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="58f52-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="58f52-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="58f52-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="58f52-262">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="58f52-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![SPF 的 Freenom TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="58f52-264">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="58f52-264">Select **Save Changes**.</span></span>
    
    ![SPF 保存更改的 Freenom TXT 记录](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

