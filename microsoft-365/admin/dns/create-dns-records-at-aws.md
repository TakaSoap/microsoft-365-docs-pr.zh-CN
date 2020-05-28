---
title: 在 Amazon Web Services （AWS）上为 Microsoft 创建 DNS 记录
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: 了解如何验证您的域并为电子邮件、Skype for Business Online 和 Microsoft 的 Amazon Web 服务（AWS）上的其他服务设置 DNS 记录。
ms.openlocfilehash: fcc4da3a5841e9df2f6edabd540363fe70bb73ad
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400565"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="cf435-103">在 Amazon Web Services （AWS）上为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cf435-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="cf435-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="cf435-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cf435-105">如果 AWS 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype Online for Business 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="cf435-106">在 AWS 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="cf435-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="cf435-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cf435-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cf435-108">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cf435-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cf435-109">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cf435-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cf435-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="cf435-110">Add a TXT record for verification</span></span>
<span data-ttu-id="cf435-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cf435-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cf435-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="cf435-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf435-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="cf435-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cf435-p104">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="cf435-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cf435-118">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="cf435-119">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="cf435-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cf435-120">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="cf435-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cf435-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cf435-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="cf435-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="cf435-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="cf435-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cf435-125">**名称**</span><span class="sxs-lookup"><span data-stu-id="cf435-125">**Name**</span></span> <br/> |<span data-ttu-id="cf435-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="cf435-126">**Type**</span></span> <br/> |<span data-ttu-id="cf435-127">**别名**</span><span class="sxs-lookup"><span data-stu-id="cf435-127">**Alias**</span></span> <br/> |<span data-ttu-id="cf435-128">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="cf435-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="cf435-129">**值**</span><span class="sxs-lookup"><span data-stu-id="cf435-129">**Value**</span></span> <br/> |<span data-ttu-id="cf435-130">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="cf435-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="cf435-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cf435-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cf435-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="cf435-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="cf435-133">否</span><span class="sxs-lookup"><span data-stu-id="cf435-133">No</span></span>  <br/> |<span data-ttu-id="cf435-134">300</span><span class="sxs-lookup"><span data-stu-id="cf435-134">300</span></span>  <br/> |<span data-ttu-id="cf435-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cf435-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="cf435-136">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="cf435-136">**Note:** This is an example.</span></span> <span data-ttu-id="cf435-137">在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="cf435-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="cf435-138">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="cf435-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cf435-139">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="cf435-140">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cf435-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="cf435-141">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="cf435-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cf435-142">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="cf435-143">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="cf435-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cf435-144">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cf435-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cf435-145">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="cf435-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cf435-146">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="cf435-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cf435-147">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="cf435-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cf435-148">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cf435-148">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cf435-149">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cf435-149">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cf435-150">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cf435-150">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="cf435-151">添加 MX 记录，以便你的域的电子邮件将发送到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf435-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="cf435-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cf435-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cf435-153">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="cf435-153">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="cf435-154">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="cf435-154">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cf435-155">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="cf435-156">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="cf435-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cf435-157">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="cf435-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cf435-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cf435-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="cf435-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="cf435-160">**名称**</span><span class="sxs-lookup"><span data-stu-id="cf435-160">**Name**</span></span>|<span data-ttu-id="cf435-161">**Type**</span><span class="sxs-lookup"><span data-stu-id="cf435-161">**Type**</span></span>|<span data-ttu-id="cf435-162">**别名**</span><span class="sxs-lookup"><span data-stu-id="cf435-162">**Alias**</span></span>|<span data-ttu-id="cf435-163">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="cf435-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="cf435-164">**值**</span><span class="sxs-lookup"><span data-stu-id="cf435-164">**Value**</span></span>|<span data-ttu-id="cf435-165">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="cf435-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cf435-166">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="cf435-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cf435-167">MX - 邮件交换</span><span class="sxs-lookup"><span data-stu-id="cf435-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="cf435-168">否</span><span class="sxs-lookup"><span data-stu-id="cf435-168">No</span></span>  <br/> |<span data-ttu-id="cf435-169">300</span><span class="sxs-lookup"><span data-stu-id="cf435-169">300</span></span>  <br/> |<span data-ttu-id="cf435-170">0 *\<domain-key\>* . mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cf435-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cf435-p109">0 是 MX 优先级值。 将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  </span><span class="sxs-lookup"><span data-stu-id="cf435-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="cf435-173">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="cf435-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cf435-174">**注意：**\<*domain-key*\>从 Microsoft 365 帐户获取。</span><span class="sxs-lookup"><span data-stu-id="cf435-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="cf435-175">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="cf435-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cf435-176">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-176">Simple</span></span>  <br/> |
       
    ![AWS-配置-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="cf435-178">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cf435-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="cf435-180">如果有任何其他 MX 记录，请删除它们。</span><span class="sxs-lookup"><span data-stu-id="cf435-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cf435-181">AWS 将 MX 记录存储为可能包含多个记录的集合。</span><span class="sxs-lookup"><span data-stu-id="cf435-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="cf435-182">**请勿**选择 "**删除记录集**"，因为这将删除所有 MX 记录，包括刚刚添加的记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="cf435-183">请使用下面的说明。</span><span class="sxs-lookup"><span data-stu-id="cf435-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="cf435-184">首先，选择 MX 记录集。</span><span class="sxs-lookup"><span data-stu-id="cf435-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="cf435-186">接下来，在" **编辑记录集**"区域中，通过选择" **值**"框中的条目并按键盘上的 **Delete** 键来删除每个已过时 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="cf435-188">选择 "**保存记录集**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="cf435-190">添加 Microsoft 365 所需的五个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="cf435-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="cf435-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cf435-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="cf435-192">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="cf435-192">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="cf435-193">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="cf435-193">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cf435-194">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="cf435-195">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="cf435-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cf435-196">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="cf435-197">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="cf435-198">在" **创建记录集**"区域中新记录的框内，键入或复制并粘贴下表第一行中的值。</span><span class="sxs-lookup"><span data-stu-id="cf435-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cf435-199">（从下拉列表中选择" **类型**"和" **路由策略**"值。）</span><span class="sxs-lookup"><span data-stu-id="cf435-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="cf435-200">**名称**</span><span class="sxs-lookup"><span data-stu-id="cf435-200">**Name**</span></span>|<span data-ttu-id="cf435-201">**Type**</span><span class="sxs-lookup"><span data-stu-id="cf435-201">**Type**</span></span>|<span data-ttu-id="cf435-202">**别名**</span><span class="sxs-lookup"><span data-stu-id="cf435-202">**Alias**</span></span>|<span data-ttu-id="cf435-203">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="cf435-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="cf435-204">**值**</span><span class="sxs-lookup"><span data-stu-id="cf435-204">**Value**</span></span>|<span data-ttu-id="cf435-205">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="cf435-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cf435-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cf435-206">autodiscover</span></span>  <br/> |<span data-ttu-id="cf435-207">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="cf435-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="cf435-208">否</span><span class="sxs-lookup"><span data-stu-id="cf435-208">No</span></span>  <br/> |<span data-ttu-id="cf435-209">300</span><span class="sxs-lookup"><span data-stu-id="cf435-209">300</span></span>  <br/> |<span data-ttu-id="cf435-210">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cf435-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cf435-211">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="cf435-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cf435-212">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="cf435-213">sip</span><span class="sxs-lookup"><span data-stu-id="cf435-213">sip</span></span>  <br/> |<span data-ttu-id="cf435-214">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="cf435-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="cf435-215">否</span><span class="sxs-lookup"><span data-stu-id="cf435-215">No</span></span>  <br/> |<span data-ttu-id="cf435-216">300</span><span class="sxs-lookup"><span data-stu-id="cf435-216">300</span></span>  <br/> |<span data-ttu-id="cf435-217">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cf435-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cf435-218">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="cf435-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cf435-219">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="cf435-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cf435-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cf435-221">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="cf435-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="cf435-222">否</span><span class="sxs-lookup"><span data-stu-id="cf435-222">No</span></span>  <br/> |<span data-ttu-id="cf435-223">300</span><span class="sxs-lookup"><span data-stu-id="cf435-223">300</span></span>  <br/> |<span data-ttu-id="cf435-224">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cf435-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cf435-225">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="cf435-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cf435-226">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="cf435-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cf435-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cf435-228">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="cf435-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="cf435-229">否</span><span class="sxs-lookup"><span data-stu-id="cf435-229">No</span></span>  <br/> |<span data-ttu-id="cf435-230">300</span><span class="sxs-lookup"><span data-stu-id="cf435-230">300</span></span>  <br/> |<span data-ttu-id="cf435-231">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="cf435-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cf435-232">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="cf435-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cf435-233">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="cf435-234">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="cf435-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cf435-235">CNAME - 规范名称</span><span class="sxs-lookup"><span data-stu-id="cf435-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="cf435-236">否</span><span class="sxs-lookup"><span data-stu-id="cf435-236">No</span></span>  <br/> |<span data-ttu-id="cf435-237">300</span><span class="sxs-lookup"><span data-stu-id="cf435-237">300</span></span>  <br/> |<span data-ttu-id="cf435-238">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="cf435-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cf435-239">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="cf435-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cf435-240">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-240">Simple</span></span>  <br/> |
   
    ![AWS-配置-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="cf435-242">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cf435-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="cf435-244">添加其他 4 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="cf435-245">在 "**托管区域**" 页上，选择 "**创建记录集**"，使用表中下一行的值创建记录，然后再次选择 "**创建**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="cf435-246">重复此过程，直到创建完所有五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cf435-247">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="cf435-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cf435-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cf435-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf435-249">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="cf435-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cf435-250">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="cf435-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cf435-251">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cf435-252">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="cf435-253">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="cf435-253">Need examples?</span></span> <span data-ttu-id="cf435-254">请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="cf435-254">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="cf435-255">若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="cf435-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="cf435-256">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="cf435-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="cf435-257">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="cf435-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cf435-258">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="cf435-259">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="cf435-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cf435-260">选择**TXT**记录集。</span><span class="sxs-lookup"><span data-stu-id="cf435-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="cf435-p115">在" **编辑记录集**"区域中，找到现有记录的" **值:**"框，在当前条目的末尾按 Enter 键（键盘上）创建新行；然后在该新行（现有值下方）上，键入或复制粘贴下表中的值。（可查看该表下方说明中的示例。）</span><span class="sxs-lookup"><span data-stu-id="cf435-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="cf435-264">**值:**</span><span class="sxs-lookup"><span data-stu-id="cf435-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="cf435-265">v=spf1 include:outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cf435-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cf435-p116">（系统会自动提供屏幕说明所需的引号。无需手动键入。）  </span><span class="sxs-lookup"><span data-stu-id="cf435-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="cf435-268">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="cf435-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-配置-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="cf435-270">选择 "**保存记录集**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="cf435-272">添加 Microsoft 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="cf435-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="cf435-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cf435-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cf435-274">要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="cf435-274">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="cf435-275">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="cf435-275">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="cf435-276">在 "**资源**" 页上，选择 "**托管区域**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="cf435-277">在 "**托管区域**" 页上的 "**域名**" 列中，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="cf435-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cf435-278">选择 "**创建记录集**"。</span><span class="sxs-lookup"><span data-stu-id="cf435-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="cf435-279">添加第一条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="cf435-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="cf435-280">在" **创建记录集**"区域中新记录的框内，键入或复制并粘贴下表第一行中的值。</span><span class="sxs-lookup"><span data-stu-id="cf435-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cf435-281">（从下拉列表中选择" **类型**"和" **路由策略**"值。）</span><span class="sxs-lookup"><span data-stu-id="cf435-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="cf435-282">**名称**</span><span class="sxs-lookup"><span data-stu-id="cf435-282">**Name**</span></span>|<span data-ttu-id="cf435-283">**Type**</span><span class="sxs-lookup"><span data-stu-id="cf435-283">**Type**</span></span>|<span data-ttu-id="cf435-284">**别名**</span><span class="sxs-lookup"><span data-stu-id="cf435-284">**Alias**</span></span>|<span data-ttu-id="cf435-285">**TTL（秒）**</span><span class="sxs-lookup"><span data-stu-id="cf435-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="cf435-286">**值**</span><span class="sxs-lookup"><span data-stu-id="cf435-286">**Value**</span></span>|<span data-ttu-id="cf435-287">**路由策略**</span><span class="sxs-lookup"><span data-stu-id="cf435-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cf435-288">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="cf435-288">_sip._tls</span></span>|<span data-ttu-id="cf435-289">SRV - 服务定位器</span><span class="sxs-lookup"><span data-stu-id="cf435-289">SRV - Service locator</span></span>|<span data-ttu-id="cf435-290">否</span><span class="sxs-lookup"><span data-stu-id="cf435-290">No</span></span>|<span data-ttu-id="cf435-291">300</span><span class="sxs-lookup"><span data-stu-id="cf435-291">300</span></span>|<span data-ttu-id="cf435-292">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cf435-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="cf435-293">**此值必须以句点（.）结尾**></span><span class="sxs-lookup"><span data-stu-id="cf435-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="cf435-294">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="cf435-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cf435-295">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-295">Simple</span></span>|
    |<span data-ttu-id="cf435-296">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="cf435-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="cf435-297">SRV - 服务定位器</span><span class="sxs-lookup"><span data-stu-id="cf435-297">SRV - Service locator</span></span>|<span data-ttu-id="cf435-298">否</span><span class="sxs-lookup"><span data-stu-id="cf435-298">No</span></span>|<span data-ttu-id="cf435-299">300</span><span class="sxs-lookup"><span data-stu-id="cf435-299">300</span></span>|<span data-ttu-id="cf435-300">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cf435-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="cf435-301">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cf435-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="cf435-302">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="cf435-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cf435-303">简单</span><span class="sxs-lookup"><span data-stu-id="cf435-303">Simple</span></span>|
   
    ![AWS-配置-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="cf435-305">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cf435-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="cf435-307">添加其他 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="cf435-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="cf435-308">在 "**托管区域**" 页上，选择 "**创建记录集**"，使用表中下一行的值创建记录，然后再次选择 "**创建**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="cf435-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="cf435-309">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cf435-309">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cf435-310">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cf435-310">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cf435-311">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cf435-311">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
