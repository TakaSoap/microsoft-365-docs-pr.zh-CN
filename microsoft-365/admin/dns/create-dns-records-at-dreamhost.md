---
title: 在 Dreamhost 上为 Office 365 创建 DNS 记录
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: 了解如何在 Dreamhost for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 1997af6e14dcb6a118dfcc3558037ed56d07ea87
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211783"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="c3dff-103">在 Dreamhost 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c3dff-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="c3dff-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="c3dff-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c3dff-105">如果 DreamHost 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Lync 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="c3dff-106">在 DreamHost 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="c3dff-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="c3dff-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c3dff-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3dff-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c3dff-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c3dff-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="c3dff-111">Add a TXT record for verification</span></span>
<span data-ttu-id="c3dff-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c3dff-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c3dff-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="c3dff-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3dff-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="c3dff-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c3dff-117">若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="c3dff-117">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="c3dff-118">系统将提示您登录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-118">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-配置-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="c3dff-120">在**仪表板**页面上，选择 "**域**"，然后**管理域**。</span><span class="sxs-lookup"><span data-stu-id="c3dff-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-配置-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="c3dff-122">在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。</span><span class="sxs-lookup"><span data-stu-id="c3dff-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-配置-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="c3dff-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c3dff-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c3dff-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="c3dff-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c3dff-127">**名称**</span><span class="sxs-lookup"><span data-stu-id="c3dff-127">**Name**</span></span>|<span data-ttu-id="c3dff-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="c3dff-128">**Type**</span></span>|<span data-ttu-id="c3dff-129">**值**</span><span class="sxs-lookup"><span data-stu-id="c3dff-129">**Value**</span></span>|<span data-ttu-id="c3dff-130">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c3dff-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c3dff-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c3dff-132">TXT</span><span class="sxs-lookup"><span data-stu-id="c3dff-132">TXT</span></span>  <br/> |<span data-ttu-id="c3dff-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c3dff-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c3dff-134">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="c3dff-134">**Note:** This is an example.</span></span> <span data-ttu-id="c3dff-135">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="c3dff-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="c3dff-136">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="c3dff-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c3dff-137">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-验证-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="c3dff-139">立即选择 "**添加记录"！**</span><span class="sxs-lookup"><span data-stu-id="c3dff-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-验证-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="c3dff-141">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="c3dff-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c3dff-142">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c3dff-143">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="c3dff-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c3dff-144">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="c3dff-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c3dff-145">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="c3dff-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c3dff-146">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="c3dff-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c3dff-147">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="c3dff-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="c3dff-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c3dff-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="c3dff-151">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="c3dff-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="c3dff-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c3dff-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="c3dff-153">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c3dff-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c3dff-154">若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="c3dff-154">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="c3dff-155">系统将提示您登录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-155">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-配置-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="c3dff-157">在**仪表板**页面上，依次选择 "**邮件**" 和 "**自定义 MX**"。</span><span class="sxs-lookup"><span data-stu-id="c3dff-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-配置-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="c3dff-159">在 "**管理邮件传递**" 部分的 "**操作**" 列中，为要编辑的域选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c3dff-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-配置-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="c3dff-161">在 "**自定义 MX 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的以下值。</span><span class="sxs-lookup"><span data-stu-id="c3dff-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="c3dff-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="c3dff-163">（如果存在任何其他现有 MX 记录，则将这些记录标记为 "删除"。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="c3dff-164">**MX 记录（必需）**</span><span class="sxs-lookup"><span data-stu-id="c3dff-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="c3dff-165">0  *\<域密钥\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c3dff-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="c3dff-166">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="c3dff-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="c3dff-p108">0 是 MX 优先级值。 将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  </span><span class="sxs-lookup"><span data-stu-id="c3dff-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="c3dff-169">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="c3dff-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="c3dff-170">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="c3dff-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-配置-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="c3dff-172">选择 "**立即将此域改为使用自定义 MX 记录！** "</span><span class="sxs-lookup"><span data-stu-id="c3dff-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-配置-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="c3dff-174">如果存在任何其他现有 MX 记录，请通过选择相应的条目，然后按键盘上的**delete**键来删除每个记录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-配置-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="c3dff-176">如果已删除任何记录，请选择 "**立即更新自定义 MX 记录！** "</span><span class="sxs-lookup"><span data-stu-id="c3dff-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-配置-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="c3dff-178">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="c3dff-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="c3dff-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c3dff-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="c3dff-180">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c3dff-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c3dff-181">若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="c3dff-181">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="c3dff-182">系统将提示您登录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-182">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-配置-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="c3dff-184">在**仪表板**页面上，选择 "**域**"，然后**管理域**。</span><span class="sxs-lookup"><span data-stu-id="c3dff-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-配置-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="c3dff-186">在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。</span><span class="sxs-lookup"><span data-stu-id="c3dff-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-配置-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="c3dff-188">在 "**添加自定义 DNS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="c3dff-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="c3dff-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="c3dff-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c3dff-191">**名称**</span><span class="sxs-lookup"><span data-stu-id="c3dff-191">**Name**</span></span>|<span data-ttu-id="c3dff-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="c3dff-192">**Type**</span></span>|<span data-ttu-id="c3dff-193">**值**</span><span class="sxs-lookup"><span data-stu-id="c3dff-193">**Value**</span></span>|<span data-ttu-id="c3dff-194">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c3dff-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c3dff-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c3dff-195">autodiscover</span></span>  <br/> |<span data-ttu-id="c3dff-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3dff-196">CNAME</span></span>  <br/> |<span data-ttu-id="c3dff-197">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c3dff-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="c3dff-198">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c3dff-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c3dff-199">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="c3dff-200">sip</span><span class="sxs-lookup"><span data-stu-id="c3dff-200">sip</span></span>  <br/> |<span data-ttu-id="c3dff-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3dff-201">CNAME</span></span>  <br/> |<span data-ttu-id="c3dff-202">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c3dff-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c3dff-203">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c3dff-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c3dff-204">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="c3dff-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c3dff-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c3dff-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3dff-206">CNAME</span></span>  <br/> |<span data-ttu-id="c3dff-207">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c3dff-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c3dff-208">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c3dff-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c3dff-209">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="c3dff-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c3dff-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c3dff-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3dff-211">CNAME</span></span>  <br/> |<span data-ttu-id="c3dff-212">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="c3dff-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="c3dff-213">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c3dff-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c3dff-214">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="c3dff-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c3dff-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c3dff-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3dff-216">CNAME</span></span>  <br/> |<span data-ttu-id="c3dff-217">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c3dff-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="c3dff-218">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c3dff-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c3dff-219">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-配置-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="c3dff-221">立即选择 "**添加记录"！**</span><span class="sxs-lookup"><span data-stu-id="c3dff-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-配置-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="c3dff-223">使用前面的两个步骤和表中的其他五行中的值，添加其他五个 CNAME 记录中的每个。</span><span class="sxs-lookup"><span data-stu-id="c3dff-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c3dff-224">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c3dff-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c3dff-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c3dff-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3dff-226">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="c3dff-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c3dff-227">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="c3dff-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c3dff-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="c3dff-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="c3dff-229">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="c3dff-230">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c3dff-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c3dff-231">若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="c3dff-231">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="c3dff-232">系统将提示您登录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-232">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-配置-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="c3dff-234">在**仪表板**页面上，选择 "**域**"，然后**管理域**。</span><span class="sxs-lookup"><span data-stu-id="c3dff-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-配置-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="c3dff-236">在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。</span><span class="sxs-lookup"><span data-stu-id="c3dff-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-配置-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="c3dff-238">在 "**添加自定义 DNS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="c3dff-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="c3dff-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="c3dff-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c3dff-241">**名称**</span><span class="sxs-lookup"><span data-stu-id="c3dff-241">**Name**</span></span>|<span data-ttu-id="c3dff-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="c3dff-242">**Type**</span></span>|<span data-ttu-id="c3dff-243">**值**</span><span class="sxs-lookup"><span data-stu-id="c3dff-243">**Value**</span></span>|<span data-ttu-id="c3dff-244">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c3dff-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c3dff-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c3dff-246">TXT</span><span class="sxs-lookup"><span data-stu-id="c3dff-246">TXT</span></span>  <br/> |<span data-ttu-id="c3dff-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c3dff-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c3dff-248">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="c3dff-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="c3dff-249">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-配置-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="c3dff-251">立即选择 "**添加记录"！**</span><span class="sxs-lookup"><span data-stu-id="c3dff-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-配置-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="c3dff-253">使用前面的两个步骤和表中第二行的值，添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="c3dff-254">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="c3dff-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="c3dff-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c3dff-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="c3dff-256">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c3dff-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c3dff-257">若要开始，请使用[此链接](https://panel.dreamhost.com/)转到 DreamHost 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="c3dff-257">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/).</span></span> <span data-ttu-id="c3dff-258">系统将提示您登录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-258">You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-配置-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="c3dff-260">在**仪表板**页面上，选择 "**域**"，然后**管理域**。</span><span class="sxs-lookup"><span data-stu-id="c3dff-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-配置-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="c3dff-262">在 "**管理域**" 页上的 "**域**" 部分，为要编辑的域选择 " **DNS** "。</span><span class="sxs-lookup"><span data-stu-id="c3dff-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-配置-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="c3dff-264">在 "**添加自定义 DNS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="c3dff-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="c3dff-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="c3dff-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c3dff-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c3dff-267">**名称**</span><span class="sxs-lookup"><span data-stu-id="c3dff-267">**Name**</span></span>|<span data-ttu-id="c3dff-268">**Type**</span><span class="sxs-lookup"><span data-stu-id="c3dff-268">**Type**</span></span>|<span data-ttu-id="c3dff-269">**值**</span><span class="sxs-lookup"><span data-stu-id="c3dff-269">**Value**</span></span>|<span data-ttu-id="c3dff-270">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c3dff-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c3dff-271">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="c3dff-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="c3dff-272">SRV</span><span class="sxs-lookup"><span data-stu-id="c3dff-272">SRV</span></span>  <br/> |<span data-ttu-id="c3dff-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="c3dff-273">100 1 443</span></span>  <br/> <span data-ttu-id="c3dff-274">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c3dff-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c3dff-275">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c3dff-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c3dff-276">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="c3dff-277">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="c3dff-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="c3dff-278">SRV</span><span class="sxs-lookup"><span data-stu-id="c3dff-278">SRV</span></span>  <br/> |<span data-ttu-id="c3dff-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="c3dff-279">100 1 5061</span></span>  <br/> <span data-ttu-id="c3dff-280">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c3dff-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="c3dff-281">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="c3dff-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c3dff-282">（此字段是可选的。）</span><span class="sxs-lookup"><span data-stu-id="c3dff-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-配置-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="c3dff-284">选择 "**立即添加记录"！**。</span><span class="sxs-lookup"><span data-stu-id="c3dff-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-配置-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="c3dff-286">使用前面的两个步骤和表中第二行的值，添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="c3dff-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="c3dff-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c3dff-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
