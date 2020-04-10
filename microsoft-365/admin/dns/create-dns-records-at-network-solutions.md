---
title: 在 Network Solutions 处为 Office 365 创建 DNS 记录
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: 了解如何在 Office 365 的网络解决方案中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 6bbe954f763e0cb06e9bf32b991e60da34393c57
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211118"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="a8e3f-103">在 Network Solutions 处为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a8e3f-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="a8e3f-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a8e3f-105">如果网络解决方案是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a8e3f-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-106">These are the main records to add.</span></span> <span data-ttu-id="a8e3f-107">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="a8e3f-108">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="a8e3f-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="a8e3f-109">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="a8e3f-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="a8e3f-110">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a8e3f-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="a8e3f-111">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a8e3f-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="a8e3f-112">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a8e3f-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="a8e3f-113">在网络解决方案中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a8e3f-114">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a8e3f-p102">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a8e3f-118">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="a8e3f-118">Add a TXT record for verification</span></span>
<span data-ttu-id="a8e3f-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e3f-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a8e3f-p103">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8e3f-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a8e3f-124">请按下列步骤操作或[观看视频（从 0:47 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a8e3f-p105">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-p105">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8e3f-127">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a8e3f-129">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a8e3f-131">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-131">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a8e3f-133">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a8e3f-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-134">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a8e3f-136">向下滚动到 "**文本（TXT 记录）** " 部分，然后选择 "**编辑 TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![选择 "编辑 TXT 记录"](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="a8e3f-138">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="a8e3f-139">**主机**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-139">**Host**</span></span>|<span data-ttu-id="a8e3f-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-140">**TTL**</span></span>|<span data-ttu-id="a8e3f-141">**文本**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="a8e3f-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="a8e3f-143">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-143">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a8e3f-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a8e3f-145">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-145">**Note:** This is an example.</span></span> <span data-ttu-id="a8e3f-146">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="a8e3f-147">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a8e3f-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![在新记录的框中键入或粘贴值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="a8e3f-149">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-149">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="a8e3f-151">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-151">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="a8e3f-153">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a8e3f-154">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a8e3f-155">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="a8e3f-156">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a8e3f-157">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a8e3f-158">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a8e3f-159">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a8e3f-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a8e3f-163">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="a8e3f-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a8e3f-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e3f-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a8e3f-165">请执行以下步骤或[观看视频（从3:51 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a8e3f-166">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a8e3f-167">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8e3f-168">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a8e3f-170">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a8e3f-172">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-172">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a8e3f-174">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a8e3f-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-175">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a8e3f-177">向下滚动到 "**邮件服务器（MX 记录）** " 部分，然后选择 "**编辑 MX 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![选择 "编辑 MX 记录"](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="a8e3f-179">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a8e3f-180">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-180">**Priority**</span></span>|<span data-ttu-id="a8e3f-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-181">**TTL**</span></span>|<span data-ttu-id="a8e3f-182">**邮件服务器**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a8e3f-183">10 </span><span class="sxs-lookup"><span data-stu-id="a8e3f-183">10</span></span>  <br/> <span data-ttu-id="a8e3f-184">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="a8e3f-185">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-185">3600</span></span>  <br/> | <span data-ttu-id="a8e3f-186">*\<域密钥\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a8e3f-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a8e3f-188">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="a8e3f-189">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a8e3f-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![在新记录的框中键入或粘贴值](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="a8e3f-191">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-191">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="a8e3f-193">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-193">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="a8e3f-195">如果有任何其他 MX 记录，请通过选择每条记录的 "**删除**" 来删除所有这些记录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![选中其他 MX 记录的 "删除" 复选框](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="a8e3f-197">选择所有选项后，选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-197">When they are all selected, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="a8e3f-199">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-199">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a8e3f-201">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a8e3f-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a8e3f-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e3f-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a8e3f-203">请执行以下步骤或[观看视频（从4:43 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a8e3f-204">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a8e3f-205">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8e3f-206">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a8e3f-208">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a8e3f-210">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-210">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a8e3f-212">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a8e3f-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-213">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a8e3f-215">向下滚动到 "**主机别名（CNAME 记录）** " 部分，然后选择 "**编辑 CNAME 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![选择 "在主机别名下编辑 CNAME 记录"](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="a8e3f-217">在四个新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a8e3f-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-218">**Alias**</span></span>|<span data-ttu-id="a8e3f-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-219">**TTL**</span></span>|<span data-ttu-id="a8e3f-220">**引用主机名**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-220">**Refers to Host Name**</span></span>|<span data-ttu-id="a8e3f-221">**其他主机（选择 "**其他主机**" 选项按钮）**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a8e3f-222">自动发现</span><span class="sxs-lookup"><span data-stu-id="a8e3f-222">autodiscover</span></span>  <br/> |<span data-ttu-id="a8e3f-223">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-223">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-224">（无设置）</span><span class="sxs-lookup"><span data-stu-id="a8e3f-224">(No setting)</span></span>  <br/> |<span data-ttu-id="a8e3f-225">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a8e3f-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a8e3f-227">sip</span><span class="sxs-lookup"><span data-stu-id="a8e3f-227">sip</span></span>  <br/> |<span data-ttu-id="a8e3f-228">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-228">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-229">（无设置）</span><span class="sxs-lookup"><span data-stu-id="a8e3f-229">(No setting)</span></span>  <br/> |<span data-ttu-id="a8e3f-230">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a8e3f-231">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a8e3f-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a8e3f-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a8e3f-233">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-233">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-234">（无设置）</span><span class="sxs-lookup"><span data-stu-id="a8e3f-234">(No setting)</span></span>  <br/> |<span data-ttu-id="a8e3f-235">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a8e3f-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a8e3f-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a8e3f-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a8e3f-238">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-238">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-239">（无设置）</span><span class="sxs-lookup"><span data-stu-id="a8e3f-239">(No setting)</span></span>  <br/> |<span data-ttu-id="a8e3f-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a8e3f-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="a8e3f-241">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a8e3f-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a8e3f-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a8e3f-243">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-243">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-244">（无设置）</span><span class="sxs-lookup"><span data-stu-id="a8e3f-244">(No setting)</span></span>  <br/> |<span data-ttu-id="a8e3f-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a8e3f-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="a8e3f-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![为新记录键入或粘贴值](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="a8e3f-248">添加完所需的所有 CNAME 记录后，选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="a8e3f-250">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-250">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a8e3f-252">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a8e3f-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a8e3f-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e3f-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8e3f-254">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a8e3f-255">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a8e3f-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8e3f-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a8e3f-257">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="a8e3f-258">请执行以下步骤或[观看视频（从5:35 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a8e3f-259">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a8e3f-260">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8e3f-261">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a8e3f-263">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a8e3f-265">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-265">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a8e3f-267">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a8e3f-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-268">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a8e3f-270">向下滚动到 "**文本（TXT 记录）** " 部分，然后选择 "**编辑 TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![选择 "文本" 下的 "编辑 TXT 记录"](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="a8e3f-272">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="a8e3f-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="a8e3f-273">**主机**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-273">**Host**</span></span>|<span data-ttu-id="a8e3f-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-274">**TTL**</span></span>|<span data-ttu-id="a8e3f-275">**文本**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="a8e3f-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="a8e3f-277">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-277">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a8e3f-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a8e3f-279">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![为新记录键入或粘贴值](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="a8e3f-281">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-281">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="a8e3f-283">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-283">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a8e3f-285">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a8e3f-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a8e3f-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a8e3f-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="a8e3f-287">请执行以下步骤或[观看视频（从6:18 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a8e3f-288">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-288">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a8e3f-289">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-289">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8e3f-290">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a8e3f-292">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a8e3f-294">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-294">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a8e3f-296">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a8e3f-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="a8e3f-297">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a8e3f-299">向下滚动到 "**服务（SRV 记录）** " 部分，然后选择 "**编辑 SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![选择 "服务" 下的 "编辑 SRV 记录"](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="a8e3f-301">在两个新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a8e3f-302">（从下拉列表中选择 "**服务**" 和 "**协议**" 值。）</span><span class="sxs-lookup"><span data-stu-id="a8e3f-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="a8e3f-303">**服务**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-303">**Service**</span></span>|<span data-ttu-id="a8e3f-304">**协议**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-304">**Protocol**</span></span>|<span data-ttu-id="a8e3f-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-305">**TTL**</span></span>|<span data-ttu-id="a8e3f-306">**优先级**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-306">**Priority**</span></span>|<span data-ttu-id="a8e3f-307">**权重**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-307">**Weight**</span></span>|<span data-ttu-id="a8e3f-308">**端口**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-308">**Port**</span></span>|<span data-ttu-id="a8e3f-309">**目标**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a8e3f-310">_sip</span><span class="sxs-lookup"><span data-stu-id="a8e3f-310">_sip</span></span>  <br/> |<span data-ttu-id="a8e3f-311">_tls</span><span class="sxs-lookup"><span data-stu-id="a8e3f-311">_tls</span></span>  <br/> |<span data-ttu-id="a8e3f-312">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-312">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-313">100</span><span class="sxs-lookup"><span data-stu-id="a8e3f-313">100</span></span>  <br/> |<span data-ttu-id="a8e3f-314">1</span><span class="sxs-lookup"><span data-stu-id="a8e3f-314">1</span></span>  <br/> |<span data-ttu-id="a8e3f-315">443</span><span class="sxs-lookup"><span data-stu-id="a8e3f-315">443</span></span>  <br/> |<span data-ttu-id="a8e3f-316">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a8e3f-317">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="a8e3f-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a8e3f-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a8e3f-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="a8e3f-319">_tcp</span></span>  <br/> |<span data-ttu-id="a8e3f-320">3600</span><span class="sxs-lookup"><span data-stu-id="a8e3f-320">3600</span></span>  <br/> |<span data-ttu-id="a8e3f-321">100</span><span class="sxs-lookup"><span data-stu-id="a8e3f-321">100</span></span>  <br/> |<span data-ttu-id="a8e3f-322">1</span><span class="sxs-lookup"><span data-stu-id="a8e3f-322">1</span></span>  <br/> |<span data-ttu-id="a8e3f-323">5061</span><span class="sxs-lookup"><span data-stu-id="a8e3f-323">5061</span></span>  <br/> |<span data-ttu-id="a8e3f-324">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="a8e3f-325">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="a8e3f-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![为新记录键入或粘贴值](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="a8e3f-327">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-327">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="a8e3f-329">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-329">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="a8e3f-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e3f-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
