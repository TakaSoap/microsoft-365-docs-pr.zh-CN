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
ms.openlocfilehash: 6aed84a4eaf95674358aa54986cfbb76edec2ef3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629307"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="df88c-103">在 Netregistry 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="df88c-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="df88c-104">如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="df88c-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="df88c-105">如果 Netregistry 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="df88c-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="df88c-106">下面是要添加的主要记录：</span><span class="sxs-lookup"><span data-stu-id="df88c-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="df88c-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="df88c-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="df88c-108">添加 MX 记录，以便你的域的电子邮件将发送给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="df88c-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="df88c-109">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="df88c-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="df88c-110">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="df88c-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="df88c-111">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="df88c-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="df88c-112">在 Netregistry 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="df88c-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="df88c-113">若要了解 Microsoft 相关网站的托管和 DNS，请参阅[将公共网站与 microsoft 结合使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="df88c-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="df88c-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="df88c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="df88c-117">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="df88c-117">Add a TXT record for verification</span></span>
<span data-ttu-id="df88c-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="df88c-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="df88c-119">在将你的域用于 Microsoft 之前，我们必须确保你拥有此域。</span><span class="sxs-lookup"><span data-stu-id="df88c-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="df88c-120">你能够在域注册机构登录到你的帐户，并创建向 Microsoft 证明你拥有该域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="df88c-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df88c-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="df88c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="df88c-123">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="df88c-123">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df88c-124">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df88c-124">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="df88c-126">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="df88c-128">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="df88c-130">在 "**添加区域记录**" 下，从列表中选择 " **TXT 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="df88c-132">必须在 TXT 框中的条目前后使用引号。</span><span class="sxs-lookup"><span data-stu-id="df88c-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="df88c-133">在 "**新建 TXT 记录**" 表单中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="df88c-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="df88c-134">**名称**</span><span class="sxs-lookup"><span data-stu-id="df88c-134">**Name**</span></span>|<span data-ttu-id="df88c-135">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="df88c-135">**TTL (SEC)**</span></span>|<span data-ttu-id="df88c-136">**TXT （指向 "地址" 或 "值"）**</span><span class="sxs-lookup"><span data-stu-id="df88c-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="df88c-137">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="df88c-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="df88c-138">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="df88c-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="df88c-140">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="df88c-140">**Note:** This is an example.</span></span> <span data-ttu-id="df88c-141">从表中使用您的特定**目标或指向 "地址**" 值。</span><span class="sxs-lookup"><span data-stu-id="df88c-141">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="df88c-142">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="df88c-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="df88c-144">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-144">Select **Add record**.</span></span>
    
<span data-ttu-id="df88c-145">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求该记录。</span><span class="sxs-lookup"><span data-stu-id="df88c-145">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="df88c-146">当 Microsoft 找到正确的 TXT 记录时，您的域将会得到验证。</span><span class="sxs-lookup"><span data-stu-id="df88c-146">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="df88c-147">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="df88c-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="df88c-148">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="df88c-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="df88c-149">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="df88c-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="df88c-150">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="df88c-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="df88c-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="df88c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="df88c-154">添加 MX 记录，以便你的域的电子邮件将发送给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="df88c-154">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="df88c-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="df88c-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="df88c-156">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="df88c-156">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df88c-157">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df88c-157">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="df88c-159">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="df88c-161">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="df88c-163">在 "**当前区域记录**" 下，选择列表中每条 MX 记录旁边的 "**删除**"，删除默认的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="df88c-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="df88c-165">在 "**添加区域记录**" 下，从列表中选择 " **MX 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="df88c-167">在 "**新建 MX 记录**" 表单中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="df88c-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="df88c-168">**名称**</span><span class="sxs-lookup"><span data-stu-id="df88c-168">**Name**</span></span>|<span data-ttu-id="df88c-169">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="df88c-169">**TTL (SEC)**</span></span>|<span data-ttu-id="df88c-170">**Exchange （指向 "地址" 或 "值"）**</span><span class="sxs-lookup"><span data-stu-id="df88c-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="df88c-171">**主机是否处于完全限定状态？**</span><span class="sxs-lookup"><span data-stu-id="df88c-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="df88c-172">**首选项（优先级）**</span><span class="sxs-lookup"><span data-stu-id="df88c-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df88c-173">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="df88c-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="df88c-174">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="df88c-175">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df88c-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="df88c-176">**注意：** 从你的 Microsoft 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="df88c-176">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="df88c-177">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="df88c-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="df88c-178">（选中 "" 复选框）</span><span class="sxs-lookup"><span data-stu-id="df88c-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="df88c-179">10 </span><span class="sxs-lookup"><span data-stu-id="df88c-179">10</span></span>  <br/> <span data-ttu-id="df88c-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="df88c-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="df88c-182">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="df88c-184">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="df88c-184">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="df88c-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="df88c-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="df88c-186">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="df88c-186">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df88c-187">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df88c-187">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="df88c-189">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="df88c-191">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="df88c-193">在 "**添加区域记录**" 下，从列表中选择 " **CNAME 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="df88c-195">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="df88c-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="df88c-196">**名称**</span><span class="sxs-lookup"><span data-stu-id="df88c-196">**Name**</span></span>|<span data-ttu-id="df88c-197">**Type**</span><span class="sxs-lookup"><span data-stu-id="df88c-197">**Type**</span></span>|<span data-ttu-id="df88c-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df88c-198">**TTL**</span></span>|<span data-ttu-id="df88c-199">**主机（指向或地址值）**</span><span class="sxs-lookup"><span data-stu-id="df88c-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df88c-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="df88c-200">autodiscover</span></span>  <br/> |<span data-ttu-id="df88c-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="df88c-201">CNAME</span></span>  <br/> |<span data-ttu-id="df88c-202">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df88c-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="df88c-204">sip</span><span class="sxs-lookup"><span data-stu-id="df88c-204">sip</span></span>  <br/> |<span data-ttu-id="df88c-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="df88c-205">CNAME</span></span>  <br/> |<span data-ttu-id="df88c-206">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df88c-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df88c-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="df88c-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="df88c-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="df88c-209">CNAME</span></span>  <br/> |<span data-ttu-id="df88c-210">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df88c-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df88c-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="df88c-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="df88c-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="df88c-213">CNAME</span></span>  <br/> |<span data-ttu-id="df88c-214">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="df88c-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="df88c-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="df88c-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="df88c-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="df88c-217">CNAME</span></span>  <br/> |<span data-ttu-id="df88c-218">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="df88c-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="df88c-221">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="df88c-223">重复前面的步骤以创建其他五个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="df88c-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="df88c-224">对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。</span><span class="sxs-lookup"><span data-stu-id="df88c-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="df88c-225">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="df88c-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="df88c-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="df88c-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df88c-227">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="df88c-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="df88c-228">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="df88c-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="df88c-229">如果你已有域的 SPF 记录，请不要为 Microsoft 创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="df88c-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="df88c-230">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="df88c-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="df88c-231">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="df88c-231">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df88c-232">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df88c-232">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="df88c-234">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="df88c-236">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="df88c-238">在 "**添加区域记录**" 下，从列表中选择 " **TXT 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="df88c-240">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="df88c-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="df88c-241">必须在 TXT 框中的条目前后使用引号。</span><span class="sxs-lookup"><span data-stu-id="df88c-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="df88c-242">**名称**</span><span class="sxs-lookup"><span data-stu-id="df88c-242">**Name**</span></span>|<span data-ttu-id="df88c-243">**Type**</span><span class="sxs-lookup"><span data-stu-id="df88c-243">**Type**</span></span>|<span data-ttu-id="df88c-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df88c-244">**TTL**</span></span>|<span data-ttu-id="df88c-245">**TXT 数据（目标）**</span><span class="sxs-lookup"><span data-stu-id="df88c-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df88c-246">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="df88c-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="df88c-247">TXT</span><span class="sxs-lookup"><span data-stu-id="df88c-247">TXT</span></span>  <br/> |<span data-ttu-id="df88c-248">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-249">"v = spf1 包括 include spf.protection.outlook.com-all"</span><span class="sxs-lookup"><span data-stu-id="df88c-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="df88c-250">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="df88c-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="df88c-252">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="df88c-254">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="df88c-254">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="df88c-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="df88c-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="df88c-256">若要开始，请使用[此链接](https://theconsole.netregistry.com.au/)转到 Netregistry 中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="df88c-256">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/).</span></span> <span data-ttu-id="df88c-257">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="df88c-257">You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="df88c-259">在要管理的域旁边，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="df88c-261">选择 "**区域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="df88c-263">在 "**添加区域记录**" 下，从列表中选择 " **SRV 记录**"，然后选择 "**创建新记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="df88c-265">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="df88c-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df88c-266">"名称" 字段是服务（例如，_sip）和协议（例如，_tls）的组合。</span><span class="sxs-lookup"><span data-stu-id="df88c-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="df88c-267">**类型**</span><span class="sxs-lookup"><span data-stu-id="df88c-267">**Type**</span></span>|<span data-ttu-id="df88c-268">**名称**</span><span class="sxs-lookup"><span data-stu-id="df88c-268">**Name**</span></span>|<span data-ttu-id="df88c-269">**TTL （秒）**</span><span class="sxs-lookup"><span data-stu-id="df88c-269">**TTL (SEC)**</span></span>|<span data-ttu-id="df88c-270">**优先级**</span><span class="sxs-lookup"><span data-stu-id="df88c-270">**Priority**</span></span>|<span data-ttu-id="df88c-271">**权重**</span><span class="sxs-lookup"><span data-stu-id="df88c-271">**Weight**</span></span>|<span data-ttu-id="df88c-272">**端口**</span><span class="sxs-lookup"><span data-stu-id="df88c-272">**Port**</span></span>|<span data-ttu-id="df88c-273">**目标**</span><span class="sxs-lookup"><span data-stu-id="df88c-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df88c-274">SRV （服务）</span><span class="sxs-lookup"><span data-stu-id="df88c-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="df88c-275">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="df88c-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="df88c-276">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-277">100</span><span class="sxs-lookup"><span data-stu-id="df88c-277">100</span></span>  <br/> |<span data-ttu-id="df88c-278">1</span><span class="sxs-lookup"><span data-stu-id="df88c-278">1</span></span>  <br/> |<span data-ttu-id="df88c-279">443</span><span class="sxs-lookup"><span data-stu-id="df88c-279">443</span></span>  <br/> |<span data-ttu-id="df88c-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df88c-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df88c-281">SRV （服务）</span><span class="sxs-lookup"><span data-stu-id="df88c-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="df88c-282">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="df88c-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="df88c-283">3600（秒）</span><span class="sxs-lookup"><span data-stu-id="df88c-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="df88c-284">100</span><span class="sxs-lookup"><span data-stu-id="df88c-284">100</span></span>  <br/> |<span data-ttu-id="df88c-285">1</span><span class="sxs-lookup"><span data-stu-id="df88c-285">1</span></span>  <br/> |<span data-ttu-id="df88c-286">5061</span><span class="sxs-lookup"><span data-stu-id="df88c-286">5061</span></span>  <br/> |<span data-ttu-id="df88c-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df88c-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="df88c-289">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="df88c-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="df88c-291">重复前面的步骤以创建其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="df88c-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="df88c-292">将上表中第二行的值键入或复制并粘贴到第二条记录的框中。</span><span class="sxs-lookup"><span data-stu-id="df88c-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="df88c-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="df88c-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

