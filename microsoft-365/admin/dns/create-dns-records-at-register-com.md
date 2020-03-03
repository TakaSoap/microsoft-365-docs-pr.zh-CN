---
title: 在 Register.com 处为 Office 365 创建 DNS 记录
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: 了解如何在 Register.com for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 0210c03a48112d9cc517ae15f879db3b40eb8c94
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42354133"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="cd9bc-103">在 Register.com 处为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cd9bc-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="cd9bc-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cd9bc-105">如果 DNS 托管提供者是 Register.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="cd9bc-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-106">These are the main records to add.</span></span> <span data-ttu-id="cd9bc-107">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="cd9bc-108">在 Register.com 添加 TXT 记录以验证您是否拥有该域</span><span class="sxs-lookup"><span data-stu-id="cd9bc-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="cd9bc-109">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="cd9bc-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="cd9bc-110">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="cd9bc-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="cd9bc-111">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="cd9bc-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="cd9bc-112">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="cd9bc-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="cd9bc-113">在 Register.com 添加这些记录后，您的域将设置为使用 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cd9bc-114">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd9bc-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cd9bc-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cd9bc-116">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cd9bc-117">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="cd9bc-118">在 Register.com 添加 TXT 记录以验证您是否拥有该域</span><span class="sxs-lookup"><span data-stu-id="cd9bc-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="cd9bc-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cd9bc-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cd9bc-p103">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd9bc-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="cd9bc-124">请执行以下步骤或[观看视频（从0:44 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cd9bc-125">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cd9bc-126">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cd9bc-127">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cd9bc-128">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cd9bc-129">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cd9bc-130">向下滚动到 "**高级技术设置**" 部分，然后选择 "**编辑 TXT 记录（SPF）**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="cd9bc-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cd9bc-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="cd9bc-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="cd9bc-132">**Host Name**</span></span> <br/> |<span data-ttu-id="cd9bc-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="cd9bc-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="cd9bc-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cd9bc-135">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-135">**Note:** This is an example.</span></span> <span data-ttu-id="cd9bc-136">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-136">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="cd9bc-137">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="cd9bc-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="cd9bc-138">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="cd9bc-139">在下一页上，再次选择 "**继续**" 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="cd9bc-140">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cd9bc-141">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cd9bc-142">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cd9bc-143">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cd9bc-144">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cd9bc-145">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cd9bc-146">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cd9bc-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cd9bc-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cd9bc-148">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cd9bc-149">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cd9bc-150">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="cd9bc-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cd9bc-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cd9bc-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cd9bc-152">请执行以下步骤或[观看视频（从3:32 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cd9bc-153">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cd9bc-154">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cd9bc-155">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cd9bc-156">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cd9bc-157">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cd9bc-158">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑邮件交换器记录**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![选择 "编辑邮件交换器记录"](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="cd9bc-160">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cd9bc-161">（从下拉列表中选择 "**优先级**" 值。）</span><span class="sxs-lookup"><span data-stu-id="cd9bc-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cd9bc-162">\*\*\*\*主机名\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-163">优先级 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-164">邮件服务器 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="cd9bc-165">高</span><span class="sxs-lookup"><span data-stu-id="cd9bc-165">High</span></span>  <br/> <span data-ttu-id="cd9bc-166">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd9bc-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="cd9bc-167">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cd9bc-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="cd9bc-168">**注意：** 从 Office 365 帐户获取 \<*域密钥*\>。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="cd9bc-169">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="cd9bc-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![复制并粘贴表中的值](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="cd9bc-171">如果已列出任何其他 MX 记录，请选择要删除的每条记录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![选择要删除的每个记录](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="cd9bc-173">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-173">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="cd9bc-175">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cd9bc-177">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="cd9bc-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="cd9bc-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cd9bc-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cd9bc-179">请执行以下步骤或[观看视频（从4:23 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cd9bc-180">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cd9bc-181">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cd9bc-182">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cd9bc-183">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cd9bc-184">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cd9bc-185">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑域别名记录**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![选择 "编辑域别名记录"](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="cd9bc-187">选择 "**添加更多域别名**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-187">Select **Add more domain aliases**.</span></span>
    
    ![选择 "添加更多域别名"](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="cd9bc-189">添加所需的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="cd9bc-190">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="cd9bc-191">第一个字段（未标记） \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-192">指向 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cd9bc-193">自动发现</span><span class="sxs-lookup"><span data-stu-id="cd9bc-193">autodiscover</span></span>  <br/> |<span data-ttu-id="cd9bc-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cd9bc-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cd9bc-195">sip</span><span class="sxs-lookup"><span data-stu-id="cd9bc-195">sip</span></span>  <br/> |<span data-ttu-id="cd9bc-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd9bc-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cd9bc-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cd9bc-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cd9bc-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd9bc-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="cd9bc-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cd9bc-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cd9bc-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cd9bc-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cd9bc-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cd9bc-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cd9bc-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cd9bc-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![从表中复制并粘贴 DNS 值](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="cd9bc-204">添加完所需的所有 CNAME 记录后，选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="cd9bc-206">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cd9bc-208">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="cd9bc-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cd9bc-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cd9bc-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd9bc-210">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cd9bc-211">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cd9bc-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd9bc-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cd9bc-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="cd9bc-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="cd9bc-214">请执行以下步骤或[观看视频（从5:12 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cd9bc-215">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cd9bc-216">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cd9bc-217">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cd9bc-218">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cd9bc-219">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cd9bc-220">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑 TXT 记录（SPF）**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![选择 "编辑 TXT 记录（SPF）"](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="cd9bc-222">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="cd9bc-223">\*\*\*\*主机名\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-224">\*\*\*\*TXT 记录\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="cd9bc-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cd9bc-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cd9bc-226">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![复制并粘贴表中的值](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="cd9bc-228">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-228">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="cd9bc-230">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cd9bc-232">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="cd9bc-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cd9bc-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cd9bc-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cd9bc-234">请执行以下步骤或[观看视频（从5:55 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cd9bc-235">若要开始，请使用[此链接](https://www.register.com/myaccount/)转到 Register.com 上您的域页面。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-235">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cd9bc-236">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-236">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cd9bc-237">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cd9bc-238">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cd9bc-239">查找包含要修改的域的名称的行;然后，在该行中，选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cd9bc-240">滚动到 "**高级技术设置**" 部分，然后选择 "**编辑 SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![选择编辑 SRV 记录](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="cd9bc-242">添加两条 SRV 记录中的第一个：</span><span class="sxs-lookup"><span data-stu-id="cd9bc-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="cd9bc-243">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="cd9bc-244">（从下拉列表中选择 "**优先级**" 值。）</span><span class="sxs-lookup"><span data-stu-id="cd9bc-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cd9bc-245">服务 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-246">Proto \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-247">\*\*\*\*名称\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-248">优先级 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-249">体重 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-250">端口 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="cd9bc-251">目标 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="cd9bc-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cd9bc-252">_sip</span><span class="sxs-lookup"><span data-stu-id="cd9bc-252">_sip</span></span>  <br/> |<span data-ttu-id="cd9bc-253">_tls</span><span class="sxs-lookup"><span data-stu-id="cd9bc-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="cd9bc-254">高</span><span class="sxs-lookup"><span data-stu-id="cd9bc-254">High</span></span>  <br/> |<span data-ttu-id="cd9bc-255">1</span><span class="sxs-lookup"><span data-stu-id="cd9bc-255">1</span></span>  <br/> |<span data-ttu-id="cd9bc-256">443</span><span class="sxs-lookup"><span data-stu-id="cd9bc-256">443</span></span>  <br/> |<span data-ttu-id="cd9bc-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd9bc-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cd9bc-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cd9bc-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="cd9bc-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="cd9bc-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="cd9bc-260">高</span><span class="sxs-lookup"><span data-stu-id="cd9bc-260">High</span></span>  <br/> |<span data-ttu-id="cd9bc-261">1</span><span class="sxs-lookup"><span data-stu-id="cd9bc-261">1</span></span>  <br/> |<span data-ttu-id="cd9bc-262">5061</span><span class="sxs-lookup"><span data-stu-id="cd9bc-262">5061</span></span>  <br/> |<span data-ttu-id="cd9bc-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd9bc-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![复制并粘贴表中的值](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="cd9bc-265">选择 "**添加更多 SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-265">Select **Add more SRV records**.</span></span>
    
    ![选择 "添加更多 SRV 记录"](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="cd9bc-267">添加第二条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="cd9bc-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="cd9bc-268">将上表中第二行的值键入或复制并粘贴到第二条记录的框中。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="cd9bc-269">在添加这两个 SRV 记录后，请选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="cd9bc-271">在下一页上，再次选择 "**继续**" 以确认并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![选择 "继续"](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="cd9bc-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cd9bc-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cd9bc-274">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cd9bc-275">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cd9bc-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
