---
title: 在 Netregistry 处为 Microsoft 创建 DNS 记录
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: 了解如何验证您的域，并在 Netregistry for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: ed3e3bae232dcbb3c8e4eea3d1a3bc4dd0a88799
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939151"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="7e57a-103">在 Netregistry 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="7e57a-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="7e57a-104">如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="7e57a-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7e57a-105">如果 Netregistry 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="7e57a-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="7e57a-106">下面是要添加的主要记录：</span><span class="sxs-lookup"><span data-stu-id="7e57a-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="7e57a-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="7e57a-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="7e57a-108">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e57a-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="7e57a-109">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="7e57a-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="7e57a-110">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7e57a-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="7e57a-111">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="7e57a-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="7e57a-112">在 Netregistry 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="7e57a-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="7e57a-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7e57a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7e57a-116">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="7e57a-116">Add a TXT record for verification</span></span>
<span data-ttu-id="7e57a-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="7e57a-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="7e57a-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="7e57a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e57a-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="7e57a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7e57a-122">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="7e57a-122">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="7e57a-123">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="7e57a-123">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="7e57a-125">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="7e57a-127">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="7e57a-129">在 "**添加区域记录**" 下，从列表中选择 " **TXT 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="7e57a-131">必须在 TXT 框中的条目前后使用引号。</span><span class="sxs-lookup"><span data-stu-id="7e57a-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="7e57a-132">在 "**新建 TXT 记录**" 表单中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="7e57a-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="7e57a-133">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e57a-133">**Name**</span></span>|<span data-ttu-id="7e57a-134">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-134">**TTL (SEC)**</span></span>|<span data-ttu-id="7e57a-135">**TXT （指向 "地址" 或 "值"）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="7e57a-136">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="7e57a-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="7e57a-137">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-138">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="7e57a-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="7e57a-139">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="7e57a-139">**Note:** This is an example.</span></span> <span data-ttu-id="7e57a-140">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="7e57a-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7e57a-141">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="7e57a-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="7e57a-143">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-143">Select **Add record**.</span></span>
    
<span data-ttu-id="7e57a-144">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="7e57a-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7e57a-145">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="7e57a-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7e57a-146">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7e57a-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="7e57a-147">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="7e57a-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7e57a-148">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="7e57a-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7e57a-149">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="7e57a-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7e57a-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7e57a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7e57a-153">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e57a-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7e57a-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="7e57a-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="7e57a-155">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="7e57a-155">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="7e57a-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="7e57a-156">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="7e57a-158">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="7e57a-160">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="7e57a-162">在 "**当前区域记录**" 下，选择列表中每条 MX 记录旁边的 "**删除**"，删除默认的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="7e57a-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="7e57a-164">在 "**添加区域记录**" 下，从列表中选择 " **MX 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="7e57a-166">在 "**新建 MX 记录**" 表单中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="7e57a-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="7e57a-167">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e57a-167">**Name**</span></span>|<span data-ttu-id="7e57a-168">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-168">**TTL (SEC)**</span></span>|<span data-ttu-id="7e57a-169">**Exchange （指向 "地址" 或 "值"）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="7e57a-170">**主机是否处于完全限定状态？**</span><span class="sxs-lookup"><span data-stu-id="7e57a-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="7e57a-171">**首选项（优先级）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e57a-172">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="7e57a-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="7e57a-173">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="7e57a-174">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7e57a-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="7e57a-175">**注意：** 从你的 Microsoft 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="7e57a-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="7e57a-176">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="7e57a-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="7e57a-177">（选中 "" 复选框）</span><span class="sxs-lookup"><span data-stu-id="7e57a-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="7e57a-178">10  </span><span class="sxs-lookup"><span data-stu-id="7e57a-178">10</span></span>  <br/> <span data-ttu-id="7e57a-179">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="7e57a-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="7e57a-181">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7e57a-183">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="7e57a-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="7e57a-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="7e57a-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="7e57a-185">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="7e57a-185">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="7e57a-186">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="7e57a-186">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="7e57a-188">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="7e57a-190">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="7e57a-192">在 "**添加区域记录**" 下，从列表中选择 " **CNAME 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="7e57a-194">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="7e57a-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="7e57a-195">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e57a-195">**Name**</span></span>|<span data-ttu-id="7e57a-196">**Type**</span><span class="sxs-lookup"><span data-stu-id="7e57a-196">**Type**</span></span>|<span data-ttu-id="7e57a-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7e57a-197">**TTL**</span></span>|<span data-ttu-id="7e57a-198">**主机（指向或地址值）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e57a-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7e57a-199">autodiscover</span></span>  <br/> |<span data-ttu-id="7e57a-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e57a-200">CNAME</span></span>  <br/> |<span data-ttu-id="7e57a-201">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7e57a-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="7e57a-203">sip</span><span class="sxs-lookup"><span data-stu-id="7e57a-203">sip</span></span>  <br/> |<span data-ttu-id="7e57a-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e57a-204">CNAME</span></span>  <br/> |<span data-ttu-id="7e57a-205">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e57a-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7e57a-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7e57a-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7e57a-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e57a-208">CNAME</span></span>  <br/> |<span data-ttu-id="7e57a-209">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e57a-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7e57a-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7e57a-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7e57a-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e57a-212">CNAME</span></span>  <br/> |<span data-ttu-id="7e57a-213">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="7e57a-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="7e57a-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7e57a-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7e57a-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="7e57a-216">CNAME</span></span>  <br/> |<span data-ttu-id="7e57a-217">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7e57a-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="7e57a-220">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="7e57a-222">重复前面的步骤以创建其他五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="7e57a-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="7e57a-223">对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。</span><span class="sxs-lookup"><span data-stu-id="7e57a-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7e57a-224">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7e57a-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7e57a-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="7e57a-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e57a-226">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="7e57a-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7e57a-227">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="7e57a-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7e57a-228">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="7e57a-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7e57a-229">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="7e57a-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="7e57a-230">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="7e57a-230">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="7e57a-231">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="7e57a-231">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="7e57a-233">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="7e57a-235">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="7e57a-237">在 "**添加区域记录**" 下，从列表中选择 " **TXT 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="7e57a-239">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="7e57a-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7e57a-240">必须在 TXT 框中的条目前后使用引号。</span><span class="sxs-lookup"><span data-stu-id="7e57a-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="7e57a-241">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e57a-241">**Name**</span></span>|<span data-ttu-id="7e57a-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="7e57a-242">**Type**</span></span>|<span data-ttu-id="7e57a-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7e57a-243">**TTL**</span></span>|<span data-ttu-id="7e57a-244">**TXT 数据（目标）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e57a-245">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="7e57a-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="7e57a-246">TXT</span><span class="sxs-lookup"><span data-stu-id="7e57a-246">TXT</span></span>  <br/> |<span data-ttu-id="7e57a-247">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-248">"v = spf1 包括 include spf.protection.outlook.com-all"</span><span class="sxs-lookup"><span data-stu-id="7e57a-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="7e57a-249">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="7e57a-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="7e57a-251">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7e57a-253">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="7e57a-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7e57a-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="7e57a-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="7e57a-255">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="7e57a-255">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="7e57a-256">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="7e57a-256">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="7e57a-258">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="7e57a-260">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="7e57a-262">在 "**添加区域记录**" 下，从列表中选择 " **SRV 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="7e57a-264">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="7e57a-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7e57a-265">"名称" 字段是服务（例如，_sip）和协议（例如，_tls）的组合。</span><span class="sxs-lookup"><span data-stu-id="7e57a-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="7e57a-266">**类型**</span><span class="sxs-lookup"><span data-stu-id="7e57a-266">**Type**</span></span>|<span data-ttu-id="7e57a-267">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e57a-267">**Name**</span></span>|<span data-ttu-id="7e57a-268">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="7e57a-268">**TTL (SEC)**</span></span>|<span data-ttu-id="7e57a-269">**优先级**</span><span class="sxs-lookup"><span data-stu-id="7e57a-269">**Priority**</span></span>|<span data-ttu-id="7e57a-270">**权重**</span><span class="sxs-lookup"><span data-stu-id="7e57a-270">**Weight**</span></span>|<span data-ttu-id="7e57a-271">**端口**</span><span class="sxs-lookup"><span data-stu-id="7e57a-271">**Port**</span></span>|<span data-ttu-id="7e57a-272">**目标**</span><span class="sxs-lookup"><span data-stu-id="7e57a-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7e57a-273">SRV （服务）</span><span class="sxs-lookup"><span data-stu-id="7e57a-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="7e57a-274">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="7e57a-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="7e57a-275">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-276">100</span><span class="sxs-lookup"><span data-stu-id="7e57a-276">100</span></span>  <br/> |<span data-ttu-id="7e57a-277">1</span><span class="sxs-lookup"><span data-stu-id="7e57a-277">1</span></span>  <br/> |<span data-ttu-id="7e57a-278">443</span><span class="sxs-lookup"><span data-stu-id="7e57a-278">443</span></span>  <br/> |<span data-ttu-id="7e57a-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e57a-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="7e57a-280">SRV （服务）</span><span class="sxs-lookup"><span data-stu-id="7e57a-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="7e57a-281">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="7e57a-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7e57a-282">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="7e57a-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="7e57a-283">100</span><span class="sxs-lookup"><span data-stu-id="7e57a-283">100</span></span>  <br/> |<span data-ttu-id="7e57a-284">1</span><span class="sxs-lookup"><span data-stu-id="7e57a-284">1</span></span>  <br/> |<span data-ttu-id="7e57a-285">5061</span><span class="sxs-lookup"><span data-stu-id="7e57a-285">5061</span></span>  <br/> |<span data-ttu-id="7e57a-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="7e57a-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="7e57a-288">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="7e57a-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="7e57a-290">重复前面的步骤以创建其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="7e57a-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="7e57a-291">将上表中第二行的值键入或复制并粘贴到第二条记录的框中。</span><span class="sxs-lookup"><span data-stu-id="7e57a-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7e57a-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="7e57a-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

