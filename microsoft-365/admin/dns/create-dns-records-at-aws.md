---
title: 在 Amazon Web Services (AWS) 上为 Office 365 创建 DNS 记录
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: 了解如何验证您的域并为 Office 365 的 Amazon Web 服务（AWS）上的电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 307ef7fd81093360c8546dadc28ea7974995518f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238560"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="83b77-103">在 Amazon Web Services (AWS) 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="83b77-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="83b77-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="83b77-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="83b77-105">如果 AWS 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype Online for Business 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="83b77-106">在 AWS 添加这些记录后，你的域将设置为使用 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="83b77-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="83b77-107">要了解有关与 Office 365 配合使用的网站的 Web 宿主和 DNS 的信息，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="83b77-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="83b77-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="83b77-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="83b77-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="83b77-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="83b77-110">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="83b77-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="83b77-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="83b77-111">Add a TXT record for verification</span></span>
<span data-ttu-id="83b77-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="83b77-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="83b77-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="83b77-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="83b77-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="83b77-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="83b77-p104">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="83b77-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="83b77-119">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="83b77-120">在 "\* \* 托管区域 \* \*" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="83b77-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="83b77-121">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="83b77-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="83b77-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="83b77-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="83b77-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="83b77-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="83b77-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="83b77-126">**名称**</span><span class="sxs-lookup"><span data-stu-id="83b77-126">**Name**</span></span> <br/> |<span data-ttu-id="83b77-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="83b77-127">**Type**</span></span> <br/> |<span data-ttu-id="83b77-128">**别名**</span><span class="sxs-lookup"><span data-stu-id="83b77-128">**Alias**</span></span> <br/> |<span data-ttu-id="83b77-129">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="83b77-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="83b77-130">**值**</span><span class="sxs-lookup"><span data-stu-id="83b77-130">**Value**</span></span> <br/> |<span data-ttu-id="83b77-131">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="83b77-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="83b77-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="83b77-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="83b77-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="83b77-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="83b77-134">否</span><span class="sxs-lookup"><span data-stu-id="83b77-134">No</span></span>  <br/> |<span data-ttu-id="83b77-135">300</span><span class="sxs-lookup"><span data-stu-id="83b77-135">300</span></span>  <br/> |<span data-ttu-id="83b77-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="83b77-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="83b77-137">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="83b77-137">**Note:** This is an example.</span></span> <span data-ttu-id="83b77-138">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="83b77-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="83b77-139">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="83b77-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="83b77-140">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="83b77-141">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83b77-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="83b77-142">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="83b77-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="83b77-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="83b77-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="83b77-144">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="83b77-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="83b77-145">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="83b77-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="83b77-146">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="83b77-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="83b77-147">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="83b77-148">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="83b77-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="83b77-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="83b77-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="83b77-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="83b77-151">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="83b77-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="83b77-152">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="83b77-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="83b77-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="83b77-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="83b77-154">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="83b77-154">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="83b77-155">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="83b77-155">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="83b77-156">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="83b77-157">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="83b77-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="83b77-158">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="83b77-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="83b77-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="83b77-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="83b77-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="83b77-161">**名称**</span><span class="sxs-lookup"><span data-stu-id="83b77-161">**Name**</span></span>|<span data-ttu-id="83b77-162">**Type**</span><span class="sxs-lookup"><span data-stu-id="83b77-162">**Type**</span></span>|<span data-ttu-id="83b77-163">**别名**</span><span class="sxs-lookup"><span data-stu-id="83b77-163">**Alias**</span></span>|<span data-ttu-id="83b77-164">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="83b77-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="83b77-165">**值**</span><span class="sxs-lookup"><span data-stu-id="83b77-165">**Value**</span></span>|<span data-ttu-id="83b77-166">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="83b77-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="83b77-167">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="83b77-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="83b77-168">MX - 邮件交换</span><span class="sxs-lookup"><span data-stu-id="83b77-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="83b77-169">否</span><span class="sxs-lookup"><span data-stu-id="83b77-169">No</span></span>  <br/> |<span data-ttu-id="83b77-170">300</span><span class="sxs-lookup"><span data-stu-id="83b77-170">300</span></span>  <br/> |<span data-ttu-id="83b77-171">0  *\<域密钥\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="83b77-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="83b77-p109">0 是 MX 优先级值。 将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  </span><span class="sxs-lookup"><span data-stu-id="83b77-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="83b77-174">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="83b77-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="83b77-175">**注意：** 从 Office \<365 帐户中获取你的*域密钥*\> 。</span><span class="sxs-lookup"><span data-stu-id="83b77-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="83b77-176">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="83b77-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="83b77-177">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-177">Simple</span></span>  <br/> |
       
    ![AWS-配置-2-1](../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="83b77-179">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83b77-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="83b77-181">如果有任何其他 MX 记录，请删除它们。</span><span class="sxs-lookup"><span data-stu-id="83b77-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="83b77-182">AWS 将 MX 记录存储为可能包含多个记录的集合。</span><span class="sxs-lookup"><span data-stu-id="83b77-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="83b77-183">**请勿**选择 "**删除记录集**"，因为这将删除所有 MX 记录，包括刚刚添加的记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="83b77-184">请使用下面的说明。</span><span class="sxs-lookup"><span data-stu-id="83b77-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="83b77-185">首先，选择 MX 记录集。</span><span class="sxs-lookup"><span data-stu-id="83b77-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="83b77-187">接下来，在" **编辑记录集**"区域中，通过选择" **值**"框中的条目并按键盘上的 **Delete** 键来删除每个已过时 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="83b77-189">选择 "**保存记录集**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="83b77-191">添加 Office 365 所需的五个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="83b77-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="83b77-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="83b77-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="83b77-193">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="83b77-193">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="83b77-194">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="83b77-194">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="83b77-195">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="83b77-196">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="83b77-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="83b77-197">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="83b77-198">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="83b77-199">在" **创建记录集**"区域中新记录的框内，键入或复制并粘贴下表第一行中的值。</span><span class="sxs-lookup"><span data-stu-id="83b77-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="83b77-200">（从下拉列表中选择" **类型**"和" **路由策略**"值。）</span><span class="sxs-lookup"><span data-stu-id="83b77-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="83b77-201">**名称**</span><span class="sxs-lookup"><span data-stu-id="83b77-201">**Name**</span></span>|<span data-ttu-id="83b77-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="83b77-202">**Type**</span></span>|<span data-ttu-id="83b77-203">**别名**</span><span class="sxs-lookup"><span data-stu-id="83b77-203">**Alias**</span></span>|<span data-ttu-id="83b77-204">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="83b77-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="83b77-205">**值**</span><span class="sxs-lookup"><span data-stu-id="83b77-205">**Value**</span></span>|<span data-ttu-id="83b77-206">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="83b77-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="83b77-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="83b77-207">autodiscover</span></span>  <br/> |<span data-ttu-id="83b77-208">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="83b77-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="83b77-209">否</span><span class="sxs-lookup"><span data-stu-id="83b77-209">No</span></span>  <br/> |<span data-ttu-id="83b77-210">300</span><span class="sxs-lookup"><span data-stu-id="83b77-210">300</span></span>  <br/> |<span data-ttu-id="83b77-211">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="83b77-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="83b77-212">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="83b77-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="83b77-213">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="83b77-214">sip</span><span class="sxs-lookup"><span data-stu-id="83b77-214">sip</span></span>  <br/> |<span data-ttu-id="83b77-215">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="83b77-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="83b77-216">否</span><span class="sxs-lookup"><span data-stu-id="83b77-216">No</span></span>  <br/> |<span data-ttu-id="83b77-217">300</span><span class="sxs-lookup"><span data-stu-id="83b77-217">300</span></span>  <br/> |<span data-ttu-id="83b77-218">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="83b77-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="83b77-219">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="83b77-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="83b77-220">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="83b77-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="83b77-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="83b77-222">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="83b77-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="83b77-223">否</span><span class="sxs-lookup"><span data-stu-id="83b77-223">No</span></span>  <br/> |<span data-ttu-id="83b77-224">300</span><span class="sxs-lookup"><span data-stu-id="83b77-224">300</span></span>  <br/> |<span data-ttu-id="83b77-225">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="83b77-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="83b77-226">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="83b77-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="83b77-227">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="83b77-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="83b77-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="83b77-229">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="83b77-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="83b77-230">否</span><span class="sxs-lookup"><span data-stu-id="83b77-230">No</span></span>  <br/> |<span data-ttu-id="83b77-231">300</span><span class="sxs-lookup"><span data-stu-id="83b77-231">300</span></span>  <br/> |<span data-ttu-id="83b77-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="83b77-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="83b77-233">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="83b77-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="83b77-234">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="83b77-235">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="83b77-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="83b77-236">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="83b77-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="83b77-237">否</span><span class="sxs-lookup"><span data-stu-id="83b77-237">No</span></span>  <br/> |<span data-ttu-id="83b77-238">300</span><span class="sxs-lookup"><span data-stu-id="83b77-238">300</span></span>  <br/> |<span data-ttu-id="83b77-239">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="83b77-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="83b77-240">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="83b77-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="83b77-241">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-241">Simple</span></span>  <br/> |
   
    ![AWS-配置-3-1](../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="83b77-243">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83b77-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="83b77-245">添加其他 4 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="83b77-246">在 "**托管区域**" 页上，选择 "**创建记录集**"，使用表中下一行的值创建记录，然后再次选择 "**创建**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="83b77-247">重复此过程，直到创建完所有五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="83b77-248">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="83b77-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="83b77-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="83b77-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="83b77-250">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="83b77-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="83b77-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="83b77-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="83b77-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="83b77-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="83b77-253">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="83b77-254">Need examples?</span><span class="sxs-lookup"><span data-stu-id="83b77-254">Need examples?</span></span> <span data-ttu-id="83b77-255">查看[Office 365 的这些外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="83b77-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="83b77-256">若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="83b77-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="83b77-257">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="83b77-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="83b77-258">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="83b77-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="83b77-259">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="83b77-260">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="83b77-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="83b77-261">选择**TXT**记录集。</span><span class="sxs-lookup"><span data-stu-id="83b77-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="83b77-p115">在" **编辑记录集**"区域中，找到现有记录的" **值:**"框，在当前条目的末尾按 Enter 键（键盘上）创建新行；然后在该新行（现有值下方）上，键入或复制粘贴下表中的值。（可查看该表下方说明中的示例。）</span><span class="sxs-lookup"><span data-stu-id="83b77-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="83b77-265">**值:**</span><span class="sxs-lookup"><span data-stu-id="83b77-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="83b77-266">v=spf1 include:outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="83b77-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="83b77-p116">（系统会自动提供屏幕说明所需的引号。无需手动键入。）  </span><span class="sxs-lookup"><span data-stu-id="83b77-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="83b77-269">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="83b77-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-配置-4-2](../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="83b77-271">选择 "**保存记录集**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="83b77-273">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="83b77-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="83b77-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="83b77-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="83b77-275">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="83b77-275">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="83b77-276">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="83b77-276">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="83b77-277">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="83b77-278">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="83b77-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="83b77-279">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="83b77-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="83b77-280">添加第一条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="83b77-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="83b77-281">在" **创建记录集**"区域中新记录的框内，键入或复制并粘贴下表第一行中的值。</span><span class="sxs-lookup"><span data-stu-id="83b77-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="83b77-282">（从下拉列表中选择" **类型**"和" **路由策略**"值。）</span><span class="sxs-lookup"><span data-stu-id="83b77-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="83b77-283">**名称**</span><span class="sxs-lookup"><span data-stu-id="83b77-283">**Name**</span></span>|<span data-ttu-id="83b77-284">**Type**</span><span class="sxs-lookup"><span data-stu-id="83b77-284">**Type**</span></span>|<span data-ttu-id="83b77-285">**别名**</span><span class="sxs-lookup"><span data-stu-id="83b77-285">**Alias**</span></span>|<span data-ttu-id="83b77-286">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="83b77-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="83b77-287">**值**</span><span class="sxs-lookup"><span data-stu-id="83b77-287">**Value**</span></span>|<span data-ttu-id="83b77-288">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="83b77-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="83b77-289">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="83b77-289">_sip._tls</span></span>|<span data-ttu-id="83b77-290">SRV - 服务定位器</span><span class="sxs-lookup"><span data-stu-id="83b77-290">SRV - Service locator</span></span>|<span data-ttu-id="83b77-291">否</span><span class="sxs-lookup"><span data-stu-id="83b77-291">No</span></span>|<span data-ttu-id="83b77-292">300</span><span class="sxs-lookup"><span data-stu-id="83b77-292">300</span></span>|<span data-ttu-id="83b77-293">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="83b77-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="83b77-294">**此值必须以句点（.）结尾**></span><span class="sxs-lookup"><span data-stu-id="83b77-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="83b77-295">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="83b77-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="83b77-296">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-296">Simple</span></span>|
    |<span data-ttu-id="83b77-297">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="83b77-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="83b77-298">SRV - 服务定位器</span><span class="sxs-lookup"><span data-stu-id="83b77-298">SRV - Service locator</span></span>|<span data-ttu-id="83b77-299">否</span><span class="sxs-lookup"><span data-stu-id="83b77-299">No</span></span>|<span data-ttu-id="83b77-300">300</span><span class="sxs-lookup"><span data-stu-id="83b77-300">300</span></span>|<span data-ttu-id="83b77-301">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="83b77-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="83b77-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="83b77-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="83b77-303">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="83b77-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="83b77-304">简单</span><span class="sxs-lookup"><span data-stu-id="83b77-304">Simple</span></span>|
   
    ![AWS-配置-5-1](../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="83b77-306">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83b77-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="83b77-308">添加其他 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="83b77-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="83b77-309">在 "**托管区域**" 页上，选择 "**创建记录集**"，使用表中下一行的值创建记录，然后再次选择 "**创建**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="83b77-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="83b77-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="83b77-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="83b77-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="83b77-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="83b77-312">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="83b77-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
