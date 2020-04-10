---
title: 在 OVH 上为 Office 365 创建 DNS 记录
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: 了解如何在 OVH for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 3ba4e61c875f74a0a6cf76c8b7cd82ea88e0221b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211106"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="ddbb4-103">在 OVH 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="ddbb4-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="ddbb4-104">如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ddbb4-105">如果 OVH 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ddbb4-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="ddbb4-107">在 OVH 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="ddbb4-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="ddbb4-108">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ddbb4-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="ddbb4-109">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="ddbb4-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="ddbb4-110">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="ddbb4-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ddbb4-111">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="ddbb4-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="ddbb4-112">在 OVH 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ddbb4-113">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ddbb4-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ddbb4-117">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="ddbb4-117">Add a TXT record for verification</span></span>
<span data-ttu-id="ddbb4-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="ddbb4-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="ddbb4-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddbb4-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ddbb4-123">若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-123">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ddbb4-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-124">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ddbb4-126">在 "**域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ddbb4-128">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-128">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ddbb4-130">选择 "**添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-130">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ddbb4-132">选择 " **TXT** "</span><span class="sxs-lookup"><span data-stu-id="ddbb4-132">Select **TXT**</span></span>
    
    ![OVH 选择 TXT 条目](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="ddbb4-134">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="ddbb4-135">若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ddbb4-136">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-136">**Record type**</span></span>|<span data-ttu-id="ddbb4-137">**子域**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-137">**Sub-domain**</span></span>|<span data-ttu-id="ddbb4-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-138">**TTL**</span></span>|<span data-ttu-id="ddbb4-139">**值**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ddbb4-140">TXT</span><span class="sxs-lookup"><span data-stu-id="ddbb4-140">TXT</span></span>  <br/> |<span data-ttu-id="ddbb4-141">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="ddbb4-142">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ddbb4-143">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="ddbb4-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="ddbb4-144">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-144">**Note:** This is an example.</span></span> <span data-ttu-id="ddbb4-145">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="ddbb4-146">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="ddbb4-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ddbb4-147">选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-147">Select **Confirm**.</span></span> 
    
    ![OVH 确认 TXT 以进行验证](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="ddbb4-149">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ddbb4-150">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ddbb4-151">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ddbb4-152">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ddbb4-153">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ddbb4-154">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ddbb4-155">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ddbb4-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ddbb4-159">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ddbb4-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ddbb4-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="ddbb4-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="ddbb4-161">若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-161">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ddbb4-162">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-162">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ddbb4-164">在 "**域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ddbb4-166">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-166">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ddbb4-168">选择 "**添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-168">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ddbb4-170">选择 " **MX**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-170">Select **MX**.</span></span>
    
    ![OVH MX 记录类型](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="ddbb4-172">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="ddbb4-173">若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ddbb4-174">默认情况下，OVH 对目标使用相对表示法，这会将域名添加到目标记录的末尾。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="ddbb4-175">若要改为使用绝对表示法，请在目标记录中添加一个点，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="ddbb4-176">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-176">**Record type**</span></span>|<span data-ttu-id="ddbb4-177">**子域**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-177">**Sub-domain**</span></span>|<span data-ttu-id="ddbb4-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-178">**TTL**</span></span>|<span data-ttu-id="ddbb4-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-179">**Priority**</span></span>|<span data-ttu-id="ddbb4-180">**目标**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ddbb4-181">MX</span><span class="sxs-lookup"><span data-stu-id="ddbb4-181">MX</span></span>  <br/> |<span data-ttu-id="ddbb4-182">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="ddbb4-183">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ddbb4-184">10 </span><span class="sxs-lookup"><span data-stu-id="ddbb4-184">10</span></span>  <br/> <span data-ttu-id="ddbb4-185">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="ddbb4-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="ddbb4-186">\<\>mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ddbb4-187">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="ddbb4-188">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="ddbb4-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![邮件的 OVH MX 记录](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="ddbb4-190">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-190">Select **Next**.</span></span>
    
    ![OVH MX 记录选择 "下一步"](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="ddbb4-192">选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-192">Select **Confirm**.</span></span>
    
    ![OVH MX 记录选择 "确认"](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="ddbb4-194">如果有任何其他 MX 记录，请在 " **DNS 区域**" 页上的列表中将它们全部删除。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="ddbb4-195">选择每个记录，然后在 "**操作**" 列中选择 "垃圾桶**删除**" 图标。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH 删除 MX 记录](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="ddbb4-197">选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ddbb4-198">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="ddbb4-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ddbb4-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="ddbb4-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="ddbb4-200">若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-200">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ddbb4-201">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-201">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ddbb4-203">在 "**域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ddbb4-205">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-205">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ddbb4-207">选择 "**添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-207">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ddbb4-209">选择 " **CNAME**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-209">Select **CNAME**.</span></span>
    
    ![OVH 添加 CNAME 记录类型](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="ddbb4-211">创建第一个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="ddbb4-212">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="ddbb4-213">若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ddbb4-214">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-214">**Record type**</span></span>|<span data-ttu-id="ddbb4-215">**子域**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-215">**Sub-domain**</span></span>|<span data-ttu-id="ddbb4-216">**目标**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-216">**Target**</span></span>|<span data-ttu-id="ddbb4-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ddbb4-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="ddbb4-218">CNAME</span></span>  <br/> |<span data-ttu-id="ddbb4-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ddbb4-219">autodiscover</span></span>  <br/> |<span data-ttu-id="ddbb4-220">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="ddbb4-221">3600秒</span><span class="sxs-lookup"><span data-stu-id="ddbb4-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ddbb4-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="ddbb4-222">CNAME</span></span>  <br/> |<span data-ttu-id="ddbb4-223">sip</span><span class="sxs-lookup"><span data-stu-id="ddbb4-223">sip</span></span>  <br/> |<span data-ttu-id="ddbb4-224">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ddbb4-225">3600秒</span><span class="sxs-lookup"><span data-stu-id="ddbb4-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ddbb4-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="ddbb4-226">CNAME</span></span>  <br/> |<span data-ttu-id="ddbb4-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ddbb4-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ddbb4-228">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ddbb4-229">3600秒</span><span class="sxs-lookup"><span data-stu-id="ddbb4-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ddbb4-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="ddbb4-230">CNAME</span></span>  <br/> |<span data-ttu-id="ddbb4-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ddbb4-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ddbb4-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="ddbb4-233">3600秒</span><span class="sxs-lookup"><span data-stu-id="ddbb4-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="ddbb4-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="ddbb4-234">CNAME</span></span>  <br/> |<span data-ttu-id="ddbb4-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ddbb4-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ddbb4-236">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="ddbb4-237">3600秒</span><span class="sxs-lookup"><span data-stu-id="ddbb4-237">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME 记录](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="ddbb4-239">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-239">Select **Next**.</span></span>
    
    ![OVH 添加 CNAME 值并选择 "下一步"](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="ddbb4-241">选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="ddbb4-242">重复前面的步骤以创建其他五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="ddbb4-243">对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ddbb4-244">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="ddbb4-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ddbb4-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="ddbb4-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddbb4-246">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ddbb4-247">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ddbb4-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ddbb4-249">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="ddbb4-250">若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-250">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ddbb4-251">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-251">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ddbb4-253">在 "**域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ddbb4-255">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-255">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ddbb4-257">选择 "**添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-257">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ddbb4-259">选择 " **TXT**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="ddbb4-260">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="ddbb4-261">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-261">**Record type**</span></span>|<span data-ttu-id="ddbb4-262">**子域**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-262">**Sub-domain**</span></span>|<span data-ttu-id="ddbb4-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-263">**TTL**</span></span>|<span data-ttu-id="ddbb4-264">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ddbb4-265">TXT</span><span class="sxs-lookup"><span data-stu-id="ddbb4-265">TXT</span></span>  <br/> |<span data-ttu-id="ddbb4-266">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="ddbb4-267">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ddbb4-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ddbb4-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ddbb4-269">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH 为 SPF 添加 TXT 记录](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="ddbb4-271">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-271">Select **Next**.</span></span>
    
    ![OVH 为 SPF 添加 TXT 记录，然后选择 "下一步"](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="ddbb4-273">选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-273">Select **Confirm**.</span></span>
    
    ![OVH 为 SPF 和确认添加 TXT 记录](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ddbb4-275">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="ddbb4-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="ddbb4-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="ddbb4-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="ddbb4-277">若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-277">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="ddbb4-278">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-278">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="ddbb4-280">在 "**域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="ddbb4-282">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-282">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="ddbb4-284">选择 "**添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-284">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="ddbb4-286">选择 " **SRV**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-286">Select **SRV**.</span></span>
    
    ![OVH 选择 SRV 记录类型](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="ddbb4-288">创建第一个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="ddbb4-289">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="ddbb4-290">若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="ddbb4-291">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-291">**Record type**</span></span>|<span data-ttu-id="ddbb4-292">**子域**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-292">**Sub-domain**</span></span>|<span data-ttu-id="ddbb4-293">**优先级**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-293">**Priority**</span></span>|<span data-ttu-id="ddbb4-294">**权重**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-294">**Weight**</span></span>|<span data-ttu-id="ddbb4-295">**端口**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-295">**Port**</span></span>|<span data-ttu-id="ddbb4-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-296">**TTL**</span></span>|<span data-ttu-id="ddbb4-297">**目标**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ddbb4-298">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="ddbb4-299">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="ddbb4-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="ddbb4-300">100</span><span class="sxs-lookup"><span data-stu-id="ddbb4-300">100</span></span>  <br/> |<span data-ttu-id="ddbb4-301">1</span><span class="sxs-lookup"><span data-stu-id="ddbb4-301">1</span></span>  <br/> |<span data-ttu-id="ddbb4-302">443</span><span class="sxs-lookup"><span data-stu-id="ddbb4-302">443</span></span>  <br/> |<span data-ttu-id="ddbb4-303">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ddbb4-304">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="ddbb4-305">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="ddbb4-306">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="ddbb4-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ddbb4-307">100</span><span class="sxs-lookup"><span data-stu-id="ddbb4-307">100</span></span>  <br/> |<span data-ttu-id="ddbb4-308">1</span><span class="sxs-lookup"><span data-stu-id="ddbb4-308">1</span></span>  <br/> |<span data-ttu-id="ddbb4-309">5061</span><span class="sxs-lookup"><span data-stu-id="ddbb4-309">5061</span></span>  <br/> |<span data-ttu-id="ddbb4-310">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="ddbb4-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ddbb4-311">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV 记录](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="ddbb4-313">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-313">Select **Next**.</span></span>
    
    ![OVH SRV 记录选择 "下一步"](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="ddbb4-315">选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="ddbb4-316">重复前面的步骤以创建其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-316">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="ddbb4-317">将上表中第二行的值键入或复制并粘贴到第二条记录的框中。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-317">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="ddbb4-p120">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="ddbb4-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
