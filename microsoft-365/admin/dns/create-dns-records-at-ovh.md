---
title: 在 OVH 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: 了解如何验证您的域，并在 OVH for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 87a2a731a253fdc0593a1aae8020e615dca63c4a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645811"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="4b4f6-103">在 OVH 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="4b4f6-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="4b4f6-104">如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4b4f6-105">如果 OVH 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4b4f6-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="4b4f6-107">在 OVH 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="4b4f6-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="4b4f6-108">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b4f6-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="4b4f6-109">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="4b4f6-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="4b4f6-110">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4b4f6-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="4b4f6-111">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="4b4f6-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="4b4f6-112">在 OVH 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="4b4f6-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4b4f6-116">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="4b4f6-116">Add a TXT record for verification</span></span>
<span data-ttu-id="4b4f6-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="4b4f6-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="4b4f6-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b4f6-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4b4f6-122">若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-122">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="4b4f6-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-123">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="4b4f6-125">在 " **域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="4b4f6-127">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-127">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="4b4f6-129">选择 " **添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-129">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="4b4f6-131">选择 " **TXT** "</span><span class="sxs-lookup"><span data-stu-id="4b4f6-131">Select **TXT**</span></span>
    
    ![OVH 选择 TXT 条目](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="4b4f6-133">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="4b4f6-134">若要分配 TTL 值，请从下拉列表中选择 " **个性化** "，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="4b4f6-135">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-135">**Record type**</span></span>|<span data-ttu-id="4b4f6-136">**子域**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-136">**Sub-domain**</span></span>|<span data-ttu-id="4b4f6-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-137">**TTL**</span></span>|<span data-ttu-id="4b4f6-138">**值**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b4f6-139">TXT</span><span class="sxs-lookup"><span data-stu-id="4b4f6-139">TXT</span></span>  <br/> |<span data-ttu-id="4b4f6-140">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="4b4f6-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="4b4f6-141">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="4b4f6-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4b4f6-142">MS = msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="4b4f6-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="4b4f6-143">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-143">**Note:** This is an example.</span></span> <span data-ttu-id="4b4f6-144">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="4b4f6-145">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="4b4f6-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="4b4f6-146">选择“**确认**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-146">Select **Confirm**.</span></span> 
    
    ![OVH 确认 TXT 以进行验证](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="4b4f6-148">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4b4f6-149">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4b4f6-150">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4b4f6-151">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4b4f6-152">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4b4f6-153">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4b4f6-154">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4b4f6-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4b4f6-158">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b4f6-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4b4f6-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="4b4f6-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="4b4f6-160">若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-160">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="4b4f6-161">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-161">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="4b4f6-163">在 " **域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="4b4f6-165">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-165">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="4b4f6-167">选择 " **添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-167">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="4b4f6-169">选择 " **MX**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-169">Select **MX**.</span></span>
    
    ![OVH MX 记录类型](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="4b4f6-171">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="4b4f6-172">若要分配 TTL 值，请从下拉列表中选择 " **个性化** "，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4b4f6-173">默认情况下，OVH 对目标使用相对表示法，这会将域名添加到目标记录的末尾。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="4b4f6-174">若要改为使用绝对表示法，请在目标记录中添加一个点，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="4b4f6-175">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-175">**Record type**</span></span>|<span data-ttu-id="4b4f6-176">**子域**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-176">**Sub-domain**</span></span>|<span data-ttu-id="4b4f6-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-177">**TTL**</span></span>|<span data-ttu-id="4b4f6-178">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-178">**Priority**</span></span>|<span data-ttu-id="4b4f6-179">**Target**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b4f6-180">MX</span><span class="sxs-lookup"><span data-stu-id="4b4f6-180">MX</span></span>  <br/> |<span data-ttu-id="4b4f6-181">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="4b4f6-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="4b4f6-182">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="4b4f6-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4b4f6-183">10  </span><span class="sxs-lookup"><span data-stu-id="4b4f6-183">10</span></span>  <br/> <span data-ttu-id="4b4f6-184">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="4b4f6-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="4b4f6-185">\<domain-key\>. mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="4b4f6-186">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="4b4f6-187">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="4b4f6-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![邮件的 OVH MX 记录](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="4b4f6-189">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-189">Select **Next**.</span></span>
    
    ![OVH MX 记录选择 "下一步"](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="4b4f6-191">选择“**确认**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-191">Select **Confirm**.</span></span>
    
    ![OVH MX 记录选择 "确认"](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="4b4f6-193">如果有任何其他 MX 记录，请在 " **DNS 区域** " 页上的列表中将它们全部删除。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="4b4f6-194">选择每个记录，然后在 " **操作** " 列中选择 "垃圾桶 **删除** " 图标。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH 删除 MX 记录](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="4b4f6-196">选择“**确认**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b4f6-197">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="4b4f6-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4b4f6-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="4b4f6-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="4b4f6-199">若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-199">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="4b4f6-200">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-200">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="4b4f6-202">在 " **域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="4b4f6-204">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-204">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="4b4f6-206">选择 " **添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-206">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="4b4f6-208">选择 " **CNAME**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-208">Select **CNAME**.</span></span>
    
    ![OVH 添加 CNAME 记录类型](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="4b4f6-210">创建第一个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="4b4f6-211">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="4b4f6-212">若要分配 TTL 值，请从下拉列表中选择 " **个性化** "，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="4b4f6-213">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-213">**Record type**</span></span>|<span data-ttu-id="4b4f6-214">**子域**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-214">**Sub-domain**</span></span>|<span data-ttu-id="4b4f6-215">**Target**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-215">**Target**</span></span>|<span data-ttu-id="4b4f6-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b4f6-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b4f6-217">CNAME</span></span>  <br/> |<span data-ttu-id="4b4f6-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4b4f6-218">autodiscover</span></span>  <br/> |<span data-ttu-id="4b4f6-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="4b4f6-220">3600秒</span><span class="sxs-lookup"><span data-stu-id="4b4f6-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="4b4f6-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b4f6-221">CNAME</span></span>  <br/> |<span data-ttu-id="4b4f6-222">sip</span><span class="sxs-lookup"><span data-stu-id="4b4f6-222">sip</span></span>  <br/> |<span data-ttu-id="4b4f6-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="4b4f6-224">3600秒</span><span class="sxs-lookup"><span data-stu-id="4b4f6-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="4b4f6-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b4f6-225">CNAME</span></span>  <br/> |<span data-ttu-id="4b4f6-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4b4f6-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4b4f6-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="4b4f6-228">3600秒</span><span class="sxs-lookup"><span data-stu-id="4b4f6-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="4b4f6-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b4f6-229">CNAME</span></span>  <br/> |<span data-ttu-id="4b4f6-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4b4f6-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4b4f6-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="4b4f6-232">3600秒</span><span class="sxs-lookup"><span data-stu-id="4b4f6-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="4b4f6-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b4f6-233">CNAME</span></span>  <br/> |<span data-ttu-id="4b4f6-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4b4f6-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4b4f6-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="4b4f6-236">3600秒</span><span class="sxs-lookup"><span data-stu-id="4b4f6-236">3600 seconds</span></span>  <br/> |
   
    ![OVH CNAME 记录](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="4b4f6-238">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-238">Select **Next**.</span></span>
    
    ![OVH 添加 CNAME 值并选择 "下一步"](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="4b4f6-240">选择“**确认**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="4b4f6-241">重复前面的步骤以创建其他五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="4b4f6-242">对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4b4f6-243">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4b4f6-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4b4f6-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="4b4f6-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b4f6-245">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4b4f6-246">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4b4f6-247">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4b4f6-248">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的  *单个*  SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="4b4f6-249">若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-249">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="4b4f6-250">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-250">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="4b4f6-252">在 " **域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="4b4f6-254">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-254">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="4b4f6-256">选择 " **添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-256">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="4b4f6-258">选择 " **TXT**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="4b4f6-259">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="4b4f6-260">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-260">**Record type**</span></span>|<span data-ttu-id="4b4f6-261">**子域**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-261">**Sub-domain**</span></span>|<span data-ttu-id="4b4f6-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-262">**TTL**</span></span>|<span data-ttu-id="4b4f6-263">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b4f6-264">TXT</span><span class="sxs-lookup"><span data-stu-id="4b4f6-264">TXT</span></span>  <br/> |<span data-ttu-id="4b4f6-265">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="4b4f6-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="4b4f6-266">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="4b4f6-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4b4f6-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4b4f6-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4b4f6-268">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH 为 SPF 添加 TXT 记录](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="4b4f6-270">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-270">Select **Next**.</span></span>
    
    ![OVH 为 SPF 添加 TXT 记录，然后选择 "下一步"](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="4b4f6-272">选择“**确认**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-272">Select **Confirm**.</span></span>
    
    ![OVH 为 SPF 和确认添加 TXT 记录](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b4f6-274">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="4b4f6-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4b4f6-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="4b4f6-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="4b4f6-276">若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-276">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/).</span></span> <span data-ttu-id="4b4f6-277">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-277">You'll be prompted to log in.</span></span>
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="4b4f6-279">在 " **域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="4b4f6-281">选择 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-281">Select **DNS zone**.</span></span>
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="4b4f6-283">选择 " **添加条目**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-283">Select **Add an entry**.</span></span>
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="4b4f6-285">选择 " **SRV**"。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-285">Select **SRV**.</span></span>
    
    ![OVH 选择 SRV 记录类型](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="4b4f6-287">创建第一个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="4b4f6-288">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="4b4f6-289">若要分配 TTL 值，请从下拉列表中选择 " **个性化** "，然后在文本框中键入值。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="4b4f6-290">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-290">**Record type**</span></span>|<span data-ttu-id="4b4f6-291">**子域**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-291">**Sub-domain**</span></span>|<span data-ttu-id="4b4f6-292">**优先级**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-292">**Priority**</span></span>|<span data-ttu-id="4b4f6-293">**权重**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-293">**Weight**</span></span>|<span data-ttu-id="4b4f6-294">**端口**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-294">**Port**</span></span>|<span data-ttu-id="4b4f6-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-295">**TTL**</span></span>|<span data-ttu-id="4b4f6-296">**Target**</span><span class="sxs-lookup"><span data-stu-id="4b4f6-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b4f6-297">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="4b4f6-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="4b4f6-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4b4f6-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="4b4f6-299">100</span><span class="sxs-lookup"><span data-stu-id="4b4f6-299">100</span></span>  <br/> |<span data-ttu-id="4b4f6-300">1</span><span class="sxs-lookup"><span data-stu-id="4b4f6-300">1</span></span>  <br/> |<span data-ttu-id="4b4f6-301">443</span><span class="sxs-lookup"><span data-stu-id="4b4f6-301">443</span></span>  <br/> |<span data-ttu-id="4b4f6-302">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="4b4f6-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4b4f6-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4b4f6-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="4b4f6-304">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="4b4f6-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="4b4f6-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4b4f6-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="4b4f6-306">100</span><span class="sxs-lookup"><span data-stu-id="4b4f6-306">100</span></span>  <br/> |<span data-ttu-id="4b4f6-307">1</span><span class="sxs-lookup"><span data-stu-id="4b4f6-307">1</span></span>  <br/> |<span data-ttu-id="4b4f6-308">5061</span><span class="sxs-lookup"><span data-stu-id="4b4f6-308">5061</span></span>  <br/> |<span data-ttu-id="4b4f6-309">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="4b4f6-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="4b4f6-310">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH SRV 记录](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="4b4f6-312">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-312">Select **Next**.</span></span>
    
    ![OVH SRV 记录选择 "下一步"](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="4b4f6-314">选择“**确认**”。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="4b4f6-315">重复前面的步骤以创建其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-315">Repeat the previous steps to create the other SRV record.</span></span> <span data-ttu-id="4b4f6-316">将上表中第二行的值键入或复制并粘贴到第二条记录的框中。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-316">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="4b4f6-p120">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4b4f6-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
