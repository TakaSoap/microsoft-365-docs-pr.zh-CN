---
title: 在 GoDaddy 处为 Office 365 创建 DNS 记录
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 了解如何在 GoDaddy for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349233"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="493e3-103">在 GoDaddy 处为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="493e3-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="493e3-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="493e3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="493e3-105">如果 GoDaddy 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="493e3-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="493e3-106">在 GoDaddy 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="493e3-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="493e3-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="493e3-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="493e3-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="493e3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="493e3-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="493e3-111">Add a TXT record for verification</span></span>
<span data-ttu-id="493e3-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="493e3-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="493e3-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="493e3-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="493e3-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="493e3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="493e3-117">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="493e3-117">Follow the steps below.</span></span>

1. <span data-ttu-id="493e3-118">若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="493e3-118">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="493e3-119">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="493e3-119">You'll be prompted to log in.</span></span>

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="493e3-121">在 "**域**" 下，选择要编辑的域下的 "DNS"。</span><span class="sxs-lookup"><span data-stu-id="493e3-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="493e3-123">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-123">Select **Add**.</span></span>

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="493e3-125">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="493e3-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="493e3-126">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="493e3-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="493e3-127">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="493e3-127">**Record type**</span></span> |<span data-ttu-id="493e3-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="493e3-128">**Host**</span></span>|<span data-ttu-id="493e3-129">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="493e3-129">**TXT Value**</span></span>|<span data-ttu-id="493e3-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="493e3-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="493e3-131">TXT（文本）</span><span class="sxs-lookup"><span data-stu-id="493e3-131">TXT (Text)</span></span>|@|<span data-ttu-id="493e3-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="493e3-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="493e3-133">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="493e3-133">**Note**: This is an example.</span></span> <span data-ttu-id="493e3-134">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="493e3-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="493e3-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="493e3-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="493e3-136">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-136">1 hour</span></span>  <br><span data-ttu-id="493e3-137">（从下拉列表中选择一个值。）</span><span class="sxs-lookup"><span data-stu-id="493e3-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-验证-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="493e3-139">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-139">Select **Save**.</span></span>

6. <span data-ttu-id="493e3-140">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="493e3-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="493e3-141">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="493e3-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="493e3-142">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="493e3-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="493e3-143">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="493e3-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="493e3-144">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="493e3-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="493e3-145">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="493e3-146">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="493e3-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="493e3-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="493e3-150">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="493e3-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="493e3-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="493e3-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="493e3-152">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="493e3-152">Follow the steps below.</span></span>

1. <span data-ttu-id="493e3-153">若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="493e3-153">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="493e3-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="493e3-154">You'll be prompted to log in.</span></span>

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="493e3-156">在 "**域**" 下，选择要编辑的域下的 "DNS"。</span><span class="sxs-lookup"><span data-stu-id="493e3-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="493e3-158">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-158">Select **Add**.</span></span>

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="493e3-160">从下拉列表中选择 " **MX （邮件交换器）** "。</span><span class="sxs-lookup"><span data-stu-id="493e3-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-配置-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="493e3-162">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="493e3-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="493e3-163">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="493e3-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="493e3-164">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="493e3-164">**Record type**</span></span>|<span data-ttu-id="493e3-165">**主机**</span><span class="sxs-lookup"><span data-stu-id="493e3-165">**Host**</span></span>|<span data-ttu-id="493e3-166">**指向**</span><span class="sxs-lookup"><span data-stu-id="493e3-166">**Points to**</span></span>|<span data-ttu-id="493e3-167">**优先级**</span><span class="sxs-lookup"><span data-stu-id="493e3-167">**Priority**</span></span>|<span data-ttu-id="493e3-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="493e3-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="493e3-169">MX （邮件交换器）</span><span class="sxs-lookup"><span data-stu-id="493e3-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="493e3-170">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="493e3-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="493e3-171">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="493e3-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           <span data-ttu-id="493e3-172">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="493e3-172">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="493e3-173">10 </span><span class="sxs-lookup"><span data-stu-id="493e3-173">10</span></span>  <br/> <span data-ttu-id="493e3-174">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="493e3-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="493e3-175">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="493e3-176">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="493e3-177">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="493e3-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="493e3-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="493e3-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="493e3-179">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="493e3-179">Follow the steps below.</span></span>

1. <span data-ttu-id="493e3-180">若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="493e3-180">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="493e3-181">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="493e3-181">You'll be prompted to log in.</span></span>

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="493e3-183">在 "**域**" 下，选择要编辑的域下的 "DNS"。</span><span class="sxs-lookup"><span data-stu-id="493e3-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="493e3-185">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-185">Select **Add**.</span></span>

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="493e3-187">从下拉列表中选择 " **CNAME （别名）** "。</span><span class="sxs-lookup"><span data-stu-id="493e3-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-配置-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="493e3-189">创建第一个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="493e3-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="493e3-190">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="493e3-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="493e3-191">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="493e3-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="493e3-192">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="493e3-192">**Record type**</span></span>|<span data-ttu-id="493e3-193">**主机**</span><span class="sxs-lookup"><span data-stu-id="493e3-193">**Host**</span></span>|<span data-ttu-id="493e3-194">**指向**</span><span class="sxs-lookup"><span data-stu-id="493e3-194">**Points to**</span></span>|<span data-ttu-id="493e3-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="493e3-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="493e3-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="493e3-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="493e3-197">自动发现</span><span class="sxs-lookup"><span data-stu-id="493e3-197">autodiscover</span></span>  <br/> |<span data-ttu-id="493e3-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="493e3-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="493e3-199">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="493e3-200">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="493e3-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="493e3-201">sip</span><span class="sxs-lookup"><span data-stu-id="493e3-201">sip</span></span>  <br/> |<span data-ttu-id="493e3-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="493e3-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="493e3-203">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="493e3-204">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="493e3-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="493e3-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="493e3-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="493e3-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="493e3-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="493e3-207">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="493e3-208">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="493e3-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="493e3-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="493e3-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="493e3-210">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="493e3-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="493e3-211">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="493e3-212">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="493e3-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="493e3-213">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="493e3-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="493e3-214">EnterpriseEnrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="493e3-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="493e3-215">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="493e3-216">重复这些步骤以添加下一条 CNAME 记录，直到您已创建所有六个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="493e3-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="493e3-217">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="493e3-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="493e3-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="493e3-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="493e3-219">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="493e3-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="493e3-220">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="493e3-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="493e3-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="493e3-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="493e3-222">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="493e3-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="493e3-223">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="493e3-223">Follow the steps below.</span></span>

1. <span data-ttu-id="493e3-224">若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="493e3-224">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="493e3-225">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="493e3-225">You'll be prompted to log in.</span></span>

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="493e3-227">在 "**域**" 下，选择要编辑的域下的 "DNS"。</span><span class="sxs-lookup"><span data-stu-id="493e3-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="493e3-229">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-229">Select **Add**.</span></span>

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="493e3-231">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="493e3-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-配置-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="493e3-233">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="493e3-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="493e3-234">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="493e3-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="493e3-235">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="493e3-235">**Record type**</span></span>|<span data-ttu-id="493e3-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="493e3-236">**Host**</span></span>|<span data-ttu-id="493e3-237">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="493e3-237">**TXT Value**</span></span>|<span data-ttu-id="493e3-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="493e3-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="493e3-239">TXT（文本）</span><span class="sxs-lookup"><span data-stu-id="493e3-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="493e3-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="493e3-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="493e3-241">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="493e3-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="493e3-242">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-242">1 hour</span></span>  <br/> |

    ![GoDaddy-配置-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="493e3-244">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="493e3-245">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="493e3-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="493e3-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="493e3-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="493e3-247">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="493e3-247">Follow the steps below.</span></span>

1. <span data-ttu-id="493e3-248">若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="493e3-248">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="493e3-249">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="493e3-249">You'll be prompted to log in.</span></span>

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="493e3-251">在 "**域**" 下，选择要编辑的域下的 "DNS"。</span><span class="sxs-lookup"><span data-stu-id="493e3-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="493e3-253">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-253">Select **Add**.</span></span>

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="493e3-255">从下拉列表中选择 " **SRV （服务）** "。</span><span class="sxs-lookup"><span data-stu-id="493e3-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-配置-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="493e3-257">创建第一个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="493e3-257">Create the first SRV record.</span></span>

    <span data-ttu-id="493e3-258">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="493e3-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="493e3-259">（从下拉列表中选择 "**记录类型**" 和 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="493e3-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="493e3-260">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="493e3-260">**Record type**</span></span>|<span data-ttu-id="493e3-261">**名称**</span><span class="sxs-lookup"><span data-stu-id="493e3-261">**Name**</span></span>|<span data-ttu-id="493e3-262">**目标**</span><span class="sxs-lookup"><span data-stu-id="493e3-262">**Target**</span></span>|<span data-ttu-id="493e3-263">**协议**</span><span class="sxs-lookup"><span data-stu-id="493e3-263">**Protocol**</span></span>|<span data-ttu-id="493e3-264">**服务**</span><span class="sxs-lookup"><span data-stu-id="493e3-264">**Service**</span></span>|<span data-ttu-id="493e3-265">**优先级**</span><span class="sxs-lookup"><span data-stu-id="493e3-265">**Priority**</span></span>|<span data-ttu-id="493e3-266">**权重**</span><span class="sxs-lookup"><span data-stu-id="493e3-266">**Weight**</span></span>|<span data-ttu-id="493e3-267">**端口**</span><span class="sxs-lookup"><span data-stu-id="493e3-267">**Port**</span></span>|<span data-ttu-id="493e3-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="493e3-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="493e3-269">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="493e3-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="493e3-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="493e3-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="493e3-271">_tls</span><span class="sxs-lookup"><span data-stu-id="493e3-271">_tls</span></span>  <br/> |<span data-ttu-id="493e3-272">_sip</span><span class="sxs-lookup"><span data-stu-id="493e3-272">_sip</span></span>  <br/> |<span data-ttu-id="493e3-273">100</span><span class="sxs-lookup"><span data-stu-id="493e3-273">100</span></span>  <br/> |<span data-ttu-id="493e3-274">1</span><span class="sxs-lookup"><span data-stu-id="493e3-274">1</span></span>  <br/> |<span data-ttu-id="493e3-275">443</span><span class="sxs-lookup"><span data-stu-id="493e3-275">443</span></span>  <br/> |<span data-ttu-id="493e3-276">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="493e3-277">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="493e3-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="493e3-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="493e3-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="493e3-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="493e3-279">_tcp</span></span>  <br/> |<span data-ttu-id="493e3-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="493e3-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="493e3-281">100</span><span class="sxs-lookup"><span data-stu-id="493e3-281">100</span></span>  <br/> |<span data-ttu-id="493e3-282">1</span><span class="sxs-lookup"><span data-stu-id="493e3-282">1</span></span>  <br/> |<span data-ttu-id="493e3-283">5061</span><span class="sxs-lookup"><span data-stu-id="493e3-283">5061</span></span>  <br/> |<span data-ttu-id="493e3-284">1 小时</span><span class="sxs-lookup"><span data-stu-id="493e3-284">1 hour</span></span>  <br/> |

    ![GoDaddy-配置-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="493e3-286">重复**步骤 5**以创建另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="493e3-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="493e3-287">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="493e3-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="493e3-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="493e3-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
