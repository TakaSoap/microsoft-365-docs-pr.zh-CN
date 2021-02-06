---
title: 在 GoDaddy 为 Microsoft 创建 DNS 记录
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 了解如何在 GoDaddy for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 2b53985dc17f3d124ec2b37dbf0047bce229385c
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126445"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="769ce-103">在 GoDaddy 为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="769ce-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="769ce-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="769ce-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="769ce-105">如果 GoDaddy 是 DNS 托管提供商，请按照本文中的步骤验证域并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="769ce-106">在 GoDaddy 添加这些记录后，域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="769ce-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="769ce-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="769ce-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="769ce-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="769ce-110">Add a TXT record for verification</span></span>
<span data-ttu-id="769ce-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="769ce-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="769ce-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="769ce-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="769ce-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="769ce-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="769ce-116">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="769ce-116">Follow the steps below.</span></span>

1. <span data-ttu-id="769ce-117">To get started， go to your domains page at GoDaddy by using [this link.](https://account.godaddy.com/products/?go_redirect=disabled)</span><span class="sxs-lookup"><span data-stu-id="769ce-117">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="769ce-118">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="769ce-118">You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="769ce-120">在 **"** 域"下，选择要编辑的域下的 DNS。</span><span class="sxs-lookup"><span data-stu-id="769ce-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="769ce-122">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-122">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="769ce-124">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="769ce-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="769ce-125">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="769ce-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="769ce-126">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="769ce-126">**Record type**</span></span> |<span data-ttu-id="769ce-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="769ce-127">**Host**</span></span>|<span data-ttu-id="769ce-128">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="769ce-128">**TXT Value**</span></span>|<span data-ttu-id="769ce-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="769ce-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="769ce-130">TXT（文本）</span><span class="sxs-lookup"><span data-stu-id="769ce-130">TXT (Text)</span></span>|@|<span data-ttu-id="769ce-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="769ce-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="769ce-132">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="769ce-132">**Note**: This is an example.</span></span> <span data-ttu-id="769ce-133">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="769ce-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="769ce-134">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="769ce-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="769ce-135">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-135">1 hour</span></span>  <br><span data-ttu-id="769ce-136"> (从下拉列表中选择一个值。) </span><span class="sxs-lookup"><span data-stu-id="769ce-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="769ce-138">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-138">Select **Save**.</span></span>

6. <span data-ttu-id="769ce-139">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="769ce-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="769ce-140">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="769ce-141">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="769ce-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="769ce-142">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="769ce-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="769ce-143">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="769ce-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="769ce-144">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="769ce-145">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="769ce-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="769ce-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="769ce-149">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="769ce-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="769ce-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="769ce-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="769ce-151">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="769ce-151">Follow the steps below.</span></span>

1. <span data-ttu-id="769ce-152">To get started， go to your domains page at GoDaddy by using [this link.](https://account.godaddy.com/products/?go_redirect=disabled)</span><span class="sxs-lookup"><span data-stu-id="769ce-152">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="769ce-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="769ce-153">You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="769ce-155">在 **"** 域"下，选择要编辑的域下的 DNS。</span><span class="sxs-lookup"><span data-stu-id="769ce-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="769ce-157">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-157">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="769ce-159">从 **(选择")** 邮件交换器"选项。</span><span class="sxs-lookup"><span data-stu-id="769ce-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="769ce-161">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="769ce-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="769ce-162"> (从下拉列表中选择 **TTL** 值。) </span><span class="sxs-lookup"><span data-stu-id="769ce-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="769ce-163">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="769ce-163">**Record type**</span></span>|<span data-ttu-id="769ce-164">**主机**</span><span class="sxs-lookup"><span data-stu-id="769ce-164">**Host**</span></span>|<span data-ttu-id="769ce-165">**指向**</span><span class="sxs-lookup"><span data-stu-id="769ce-165">**Points to**</span></span>|<span data-ttu-id="769ce-166">**优先级**</span><span class="sxs-lookup"><span data-stu-id="769ce-166">**Priority**</span></span>|<span data-ttu-id="769ce-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="769ce-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="769ce-168">MX (邮件交换器) </span><span class="sxs-lookup"><span data-stu-id="769ce-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="769ce-169">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="769ce-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="769ce-170">**注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。</span><span class="sxs-lookup"><span data-stu-id="769ce-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           <span data-ttu-id="769ce-171">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="769ce-171">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="769ce-172">10 </span><span class="sxs-lookup"><span data-stu-id="769ce-172">10</span></span>  <br/> <span data-ttu-id="769ce-173">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="769ce-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="769ce-174">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="769ce-175">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="769ce-176">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="769ce-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="769ce-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="769ce-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="769ce-178">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="769ce-178">Follow the steps below.</span></span>

1. <span data-ttu-id="769ce-179">To get started， go to your domains page at GoDaddy by using [this link.](https://account.godaddy.com/products/?go_redirect=disabled)</span><span class="sxs-lookup"><span data-stu-id="769ce-179">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="769ce-180">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="769ce-180">You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="769ce-182">在 **"** 域"下，选择要编辑的域下的 DNS。</span><span class="sxs-lookup"><span data-stu-id="769ce-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="769ce-184">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-184">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="769ce-186">从 **下拉列表 (")** 别名"。</span><span class="sxs-lookup"><span data-stu-id="769ce-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="769ce-188">创建第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="769ce-189">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="769ce-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="769ce-190"> (从下拉列表中选择 **TTL** 值。) </span><span class="sxs-lookup"><span data-stu-id="769ce-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="769ce-191">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="769ce-191">**Record type**</span></span>|<span data-ttu-id="769ce-192">**主机**</span><span class="sxs-lookup"><span data-stu-id="769ce-192">**Host**</span></span>|<span data-ttu-id="769ce-193">**指向**</span><span class="sxs-lookup"><span data-stu-id="769ce-193">**Points to**</span></span>|<span data-ttu-id="769ce-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="769ce-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="769ce-195">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="769ce-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="769ce-196">自动发现</span><span class="sxs-lookup"><span data-stu-id="769ce-196">autodiscover</span></span>  <br/> |<span data-ttu-id="769ce-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="769ce-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="769ce-198">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="769ce-199">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="769ce-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="769ce-200">sip</span><span class="sxs-lookup"><span data-stu-id="769ce-200">sip</span></span>  <br/> |<span data-ttu-id="769ce-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="769ce-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="769ce-202">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="769ce-203">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="769ce-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="769ce-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="769ce-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="769ce-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="769ce-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="769ce-206">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="769ce-207">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="769ce-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="769ce-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="769ce-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="769ce-209">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="769ce-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="769ce-210">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="769ce-211">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="769ce-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="769ce-212">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="769ce-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="769ce-213">EnterpriseEnrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="769ce-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="769ce-214">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="769ce-215">重复这些步骤以添加下一条 CNAME 记录，直到创建全部六条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="769ce-216">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="769ce-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="769ce-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="769ce-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="769ce-218">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="769ce-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="769ce-219">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="769ce-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="769ce-220">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="769ce-221">相反，将所需的 Microsoft 值添加到当前记录，以便具有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="769ce-222">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="769ce-222">Follow the steps below.</span></span>

1. <span data-ttu-id="769ce-223">To get started， go to your domains page at GoDaddy by using [this link.](https://account.godaddy.com/products/?go_redirect=disabled)</span><span class="sxs-lookup"><span data-stu-id="769ce-223">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="769ce-224">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="769ce-224">You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="769ce-226">在 **"** 域"下，选择要编辑的域下的 DNS。</span><span class="sxs-lookup"><span data-stu-id="769ce-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="769ce-228">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-228">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="769ce-230">Choose **TXT (Text)** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="769ce-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="769ce-232">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="769ce-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="769ce-233"> (从下拉列表中选择 **TTL** 值。) </span><span class="sxs-lookup"><span data-stu-id="769ce-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="769ce-234">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="769ce-234">**Record type**</span></span>|<span data-ttu-id="769ce-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="769ce-235">**Host**</span></span>|<span data-ttu-id="769ce-236">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="769ce-236">**TXT Value**</span></span>|<span data-ttu-id="769ce-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="769ce-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="769ce-238">TXT（文本）</span><span class="sxs-lookup"><span data-stu-id="769ce-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="769ce-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="769ce-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="769ce-240">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="769ce-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="769ce-241">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="769ce-243">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="769ce-244">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="769ce-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="769ce-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="769ce-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="769ce-246">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="769ce-246">Follow the steps below.</span></span>

1. <span data-ttu-id="769ce-247">To get started， go to your domains page at GoDaddy by using [this link.](https://account.godaddy.com/products/?go_redirect=disabled)</span><span class="sxs-lookup"><span data-stu-id="769ce-247">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).</span></span> <span data-ttu-id="769ce-248">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="769ce-248">You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="769ce-250">在 **"** 域"下，选择要编辑的域下的 DNS。</span><span class="sxs-lookup"><span data-stu-id="769ce-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="769ce-252">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-252">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="769ce-254">从 **(列表中选择) SRV** 服务服务选项。</span><span class="sxs-lookup"><span data-stu-id="769ce-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="769ce-256">创建第一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-256">Create the first SRV record.</span></span>

    <span data-ttu-id="769ce-257">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="769ce-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="769ce-258"> (从下拉列表中选择 **记录** 类型和 **TTL** 值。) </span><span class="sxs-lookup"><span data-stu-id="769ce-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="769ce-259">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="769ce-259">**Record type**</span></span>|<span data-ttu-id="769ce-260">**名称**</span><span class="sxs-lookup"><span data-stu-id="769ce-260">**Name**</span></span>|<span data-ttu-id="769ce-261">**目标**</span><span class="sxs-lookup"><span data-stu-id="769ce-261">**Target**</span></span>|<span data-ttu-id="769ce-262">**协议**</span><span class="sxs-lookup"><span data-stu-id="769ce-262">**Protocol**</span></span>|<span data-ttu-id="769ce-263">**服务**</span><span class="sxs-lookup"><span data-stu-id="769ce-263">**Service**</span></span>|<span data-ttu-id="769ce-264">**优先级**</span><span class="sxs-lookup"><span data-stu-id="769ce-264">**Priority**</span></span>|<span data-ttu-id="769ce-265">**权重**</span><span class="sxs-lookup"><span data-stu-id="769ce-265">**Weight**</span></span>|<span data-ttu-id="769ce-266">**端口**</span><span class="sxs-lookup"><span data-stu-id="769ce-266">**Port**</span></span>|<span data-ttu-id="769ce-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="769ce-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="769ce-268">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="769ce-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="769ce-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="769ce-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="769ce-270">_tls</span><span class="sxs-lookup"><span data-stu-id="769ce-270">_tls</span></span>  <br/> |<span data-ttu-id="769ce-271">_sip</span><span class="sxs-lookup"><span data-stu-id="769ce-271">_sip</span></span>  <br/> |<span data-ttu-id="769ce-272">100</span><span class="sxs-lookup"><span data-stu-id="769ce-272">100</span></span>  <br/> |<span data-ttu-id="769ce-273">1 </span><span class="sxs-lookup"><span data-stu-id="769ce-273">1</span></span>  <br/> |<span data-ttu-id="769ce-274">443</span><span class="sxs-lookup"><span data-stu-id="769ce-274">443</span></span>  <br/> |<span data-ttu-id="769ce-275">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="769ce-276">SRV（服务）</span><span class="sxs-lookup"><span data-stu-id="769ce-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="769ce-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="769ce-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="769ce-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="769ce-278">_tcp</span></span>  <br/> |<span data-ttu-id="769ce-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="769ce-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="769ce-280">100</span><span class="sxs-lookup"><span data-stu-id="769ce-280">100</span></span>  <br/> |<span data-ttu-id="769ce-281">1 </span><span class="sxs-lookup"><span data-stu-id="769ce-281">1</span></span>  <br/> |<span data-ttu-id="769ce-282">5061</span><span class="sxs-lookup"><span data-stu-id="769ce-282">5061</span></span>  <br/> |<span data-ttu-id="769ce-283">1 小时</span><span class="sxs-lookup"><span data-stu-id="769ce-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="769ce-285">重复 **步骤 5** 以创建另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="769ce-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="769ce-286">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="769ce-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="769ce-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="769ce-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
