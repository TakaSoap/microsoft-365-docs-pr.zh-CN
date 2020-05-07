---
title: 在 Register.com 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: 了解如何验证您的域，并在 Register.com for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 125baf224cc9f3f21746a2f802b17f2572b65316
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048899"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="a56ed-103">在 Register.com 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a56ed-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="a56ed-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="a56ed-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a56ed-105">如果 DNS 托管提供者是 Register.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a56ed-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-106">These are the main records to add.</span></span> <span data-ttu-id="a56ed-107">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="a56ed-108">在 Register.com 添加 TXT 记录以验证您是否拥有该域</span><span class="sxs-lookup"><span data-stu-id="a56ed-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="a56ed-109">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="a56ed-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="a56ed-110">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a56ed-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="a56ed-111">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a56ed-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="a56ed-112">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a56ed-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="a56ed-113">在 Register.com 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="a56ed-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="a56ed-114">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a56ed-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a56ed-115">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="a56ed-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a56ed-116">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="a56ed-117">在 Register.com 添加 TXT 记录以验证您是否拥有该域</span><span class="sxs-lookup"><span data-stu-id="a56ed-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="a56ed-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a56ed-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a56ed-p103">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="a56ed-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a56ed-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="a56ed-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a56ed-123">请执行以下步骤或[观看视频（从0:44 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-123">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a56ed-124">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="a56ed-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="a56ed-125">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a56ed-126">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a56ed-127">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a56ed-128">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a56ed-129">向下滚动到 "**高级技术设置**" 部分，然后选择 "**编辑 TXT 记录（SPF）**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="a56ed-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a56ed-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="a56ed-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a56ed-131">**Host Name**</span></span> <br/> |<span data-ttu-id="a56ed-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="a56ed-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="a56ed-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a56ed-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a56ed-134">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="a56ed-134">**Note:** This is an example.</span></span> <span data-ttu-id="a56ed-135">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="a56ed-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="a56ed-136">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a56ed-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="a56ed-137">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="a56ed-138">在下一页上，再次选择 "**继续**" 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="a56ed-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="a56ed-139">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="a56ed-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a56ed-140">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a56ed-141">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="a56ed-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a56ed-142">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a56ed-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a56ed-143">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="a56ed-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a56ed-144">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="a56ed-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a56ed-145">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="a56ed-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a56ed-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a56ed-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a56ed-147">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="a56ed-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a56ed-148">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a56ed-149">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="a56ed-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a56ed-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a56ed-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a56ed-151">请执行以下步骤或[观看视频（从3:32 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-151">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a56ed-152">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="a56ed-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="a56ed-153">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a56ed-154">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a56ed-155">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a56ed-156">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a56ed-157">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑邮件交换器记录**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![选择 "编辑邮件交换器记录"](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="a56ed-159">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a56ed-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a56ed-160">（从下拉列表中选择 "**优先级**" 值。）</span><span class="sxs-lookup"><span data-stu-id="a56ed-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a56ed-161">\*\*\*\*主机名\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a56ed-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="a56ed-162">优先级 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="a56ed-163">邮件服务器 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a56ed-164">高</span><span class="sxs-lookup"><span data-stu-id="a56ed-164">High</span></span>  <br/> <span data-ttu-id="a56ed-165">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a56ed-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="a56ed-166">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a56ed-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="a56ed-167">**注意：** 从 Microsoft 帐户获取\<*域密钥*\>。</span><span class="sxs-lookup"><span data-stu-id="a56ed-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="a56ed-168">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a56ed-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![复制并粘贴表中的值](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="a56ed-170">如果已列出任何其他 MX 记录，请选择要删除的每条记录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![选择要删除的每个记录](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="a56ed-172">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-172">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="a56ed-174">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a56ed-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a56ed-176">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a56ed-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a56ed-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a56ed-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a56ed-178">请执行以下步骤或[观看视频（从4:23 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-178">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a56ed-179">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="a56ed-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="a56ed-180">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a56ed-181">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a56ed-182">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a56ed-183">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a56ed-184">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑域别名记录**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![选择 "编辑域别名记录"](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="a56ed-186">选择 "**添加更多域别名**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-186">Select **Add more domain aliases**.</span></span>
    
    ![选择 "添加更多域别名"](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="a56ed-188">添加所需的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="a56ed-189">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="a56ed-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="a56ed-190">第一个字段（未标记） \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="a56ed-191">指向 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a56ed-192">自动发现</span><span class="sxs-lookup"><span data-stu-id="a56ed-192">autodiscover</span></span>  <br/> |<span data-ttu-id="a56ed-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a56ed-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a56ed-194">sip</span><span class="sxs-lookup"><span data-stu-id="a56ed-194">sip</span></span>  <br/> |<span data-ttu-id="a56ed-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a56ed-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a56ed-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a56ed-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a56ed-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a56ed-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="a56ed-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a56ed-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a56ed-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a56ed-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a56ed-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a56ed-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a56ed-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a56ed-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![从表中复制并粘贴 DNS 值](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="a56ed-203">添加完所需的所有 CNAME 记录后，选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="a56ed-205">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a56ed-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a56ed-207">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a56ed-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a56ed-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a56ed-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a56ed-209">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="a56ed-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a56ed-210">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="a56ed-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a56ed-211">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a56ed-212">可以将所需的 Microsoft 值添加到当前记录，这样就拥有包含两组值的单个 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="a56ed-213">请执行以下步骤或[观看视频（从5:12 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-213">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a56ed-214">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="a56ed-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="a56ed-215">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a56ed-216">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a56ed-217">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a56ed-218">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a56ed-219">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑 TXT 记录（SPF）**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![选择 "编辑 TXT 记录（SPF）"](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="a56ed-221">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a56ed-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a56ed-222">\*\*\*\*主机名\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a56ed-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="a56ed-223">\*\*\*\*TXT 记录\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a56ed-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="a56ed-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a56ed-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a56ed-225">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="a56ed-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![复制并粘贴表中的值](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="a56ed-227">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-227">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="a56ed-229">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a56ed-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a56ed-231">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a56ed-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a56ed-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a56ed-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a56ed-233">请执行以下步骤或[观看视频（从5:55 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-233">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a56ed-234">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="a56ed-234">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="a56ed-235">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a56ed-235">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="a56ed-236">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="a56ed-237">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="a56ed-238">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="a56ed-239">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑 SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![选择编辑 SRV 记录](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="a56ed-241">添加两条 SRV 记录中的第一个：</span><span class="sxs-lookup"><span data-stu-id="a56ed-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="a56ed-242">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="a56ed-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="a56ed-243">（从下拉列表中选择 "**优先级**" 值。）</span><span class="sxs-lookup"><span data-stu-id="a56ed-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a56ed-244">服务 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="a56ed-245">Proto \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="a56ed-246">\*\*\*\*名称\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a56ed-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="a56ed-247">优先级 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="a56ed-248">体重 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="a56ed-249">端口 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="a56ed-250">目标 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="a56ed-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a56ed-251">_sip</span><span class="sxs-lookup"><span data-stu-id="a56ed-251">_sip</span></span>  <br/> |<span data-ttu-id="a56ed-252">_tls</span><span class="sxs-lookup"><span data-stu-id="a56ed-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="a56ed-253">高</span><span class="sxs-lookup"><span data-stu-id="a56ed-253">High</span></span>  <br/> |<span data-ttu-id="a56ed-254">1</span><span class="sxs-lookup"><span data-stu-id="a56ed-254">1</span></span>  <br/> |<span data-ttu-id="a56ed-255">443</span><span class="sxs-lookup"><span data-stu-id="a56ed-255">443</span></span>  <br/> |<span data-ttu-id="a56ed-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a56ed-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="a56ed-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a56ed-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a56ed-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="a56ed-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="a56ed-259">高</span><span class="sxs-lookup"><span data-stu-id="a56ed-259">High</span></span>  <br/> |<span data-ttu-id="a56ed-260">1</span><span class="sxs-lookup"><span data-stu-id="a56ed-260">1</span></span>  <br/> |<span data-ttu-id="a56ed-261">5061</span><span class="sxs-lookup"><span data-stu-id="a56ed-261">5061</span></span>  <br/> |<span data-ttu-id="a56ed-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a56ed-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![复制并粘贴表中的值](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="a56ed-264">选择 "**添加更多 SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-264">Select **Add more SRV records**.</span></span>
    
    ![选择 "添加更多 SRV 记录"](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="a56ed-266">添加第二条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="a56ed-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="a56ed-267">将上表中第二行的值键入或复制并粘贴到第二条记录的框中。</span><span class="sxs-lookup"><span data-stu-id="a56ed-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="a56ed-268">在添加这两个 SRV 记录后，请选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a56ed-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="a56ed-270">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a56ed-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="a56ed-272">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a56ed-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a56ed-273">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="a56ed-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a56ed-274">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a56ed-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
