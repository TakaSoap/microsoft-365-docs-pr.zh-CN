---
title: 在 Microsoft 的网络解决方案中创建 DNS 记录
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
description: 了解如何在 Microsoft 的网络解决方案中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: f990e4311ef88022d7fec2e1b7c90b3d8d035448
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939139"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="95e58-103">在 Microsoft 的网络解决方案中创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="95e58-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="95e58-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="95e58-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="95e58-105">如果网络解决方案是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="95e58-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="95e58-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="95e58-106">These are the main records to add.</span></span> <span data-ttu-id="95e58-107">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="95e58-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="95e58-108">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="95e58-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="95e58-109">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="95e58-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="95e58-110">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="95e58-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="95e58-111">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="95e58-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="95e58-112">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="95e58-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="95e58-113">在网络解决方案中添加这些记录后，您的域将设置为与 Microsoft 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="95e58-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="95e58-p102">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="95e58-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="95e58-117">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="95e58-117">Add a TXT record for verification</span></span>
<span data-ttu-id="95e58-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="95e58-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="95e58-p103">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="95e58-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="95e58-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="95e58-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="95e58-123">请按下列步骤操作或[观看视频（从 0:47 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="95e58-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="95e58-p105">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="95e58-p105">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e58-126">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="95e58-128">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="95e58-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="95e58-130">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-130">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="95e58-132">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="95e58-133">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="95e58-133">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="95e58-135">向下滚动到 "**文本（TXT 记录）** " 部分，然后选择 "**编辑 TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![选择 "编辑 TXT 记录"](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="95e58-137">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="95e58-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="95e58-138">**主机**</span><span class="sxs-lookup"><span data-stu-id="95e58-138">**Host**</span></span>|<span data-ttu-id="95e58-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="95e58-139">**TTL**</span></span>|<span data-ttu-id="95e58-140">**文本**</span><span class="sxs-lookup"><span data-stu-id="95e58-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="95e58-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="95e58-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="95e58-142">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-142">3600</span></span>  <br/> |<span data-ttu-id="95e58-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="95e58-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="95e58-144">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="95e58-144">**Note:** This is an example.</span></span> <span data-ttu-id="95e58-145">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="95e58-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="95e58-146">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="95e58-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![在新记录的框中键入或粘贴值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="95e58-148">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-148">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="95e58-150">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-150">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="95e58-152">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="95e58-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="95e58-153">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="95e58-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="95e58-154">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="95e58-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="95e58-155">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="95e58-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="95e58-156">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="95e58-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="95e58-157">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="95e58-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="95e58-158">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="95e58-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="95e58-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="95e58-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="95e58-162">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="95e58-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="95e58-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="95e58-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="95e58-164">请执行以下步骤或[观看视频（从3:51 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="95e58-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="95e58-165">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="95e58-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="95e58-166">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="95e58-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e58-167">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="95e58-169">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="95e58-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="95e58-171">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-171">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="95e58-173">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="95e58-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="95e58-174">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="95e58-176">向下滚动到 "**邮件服务器（MX 记录）** " 部分，然后选择 "**编辑 MX 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![选择 "编辑 MX 记录"](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="95e58-178">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="95e58-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="95e58-179">**优先级**</span><span class="sxs-lookup"><span data-stu-id="95e58-179">**Priority**</span></span>|<span data-ttu-id="95e58-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="95e58-180">**TTL**</span></span>|<span data-ttu-id="95e58-181">**邮件服务器**</span><span class="sxs-lookup"><span data-stu-id="95e58-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="95e58-182">10  </span><span class="sxs-lookup"><span data-stu-id="95e58-182">10</span></span>  <br/> <span data-ttu-id="95e58-183">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="95e58-183">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="95e58-184">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-184">3600</span></span>  <br/> | <span data-ttu-id="95e58-185">*\<域密钥\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="95e58-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="95e58-186">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="95e58-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="95e58-187">**注意：** 从你的 Microsoft 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="95e58-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="95e58-188">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="95e58-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![在新记录的框中键入或粘贴值](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="95e58-190">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-190">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="95e58-192">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-192">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="95e58-194">如果有任何其他 MX 记录，请通过选择每条记录的 "**删除**" 来删除所有这些记录。</span><span class="sxs-lookup"><span data-stu-id="95e58-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![选中其他 MX 记录的 "删除" 复选框](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="95e58-196">选择所有选项后，选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-196">When they are all selected, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="95e58-198">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-198">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="95e58-200">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="95e58-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="95e58-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="95e58-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="95e58-202">请执行以下步骤或[观看视频（从4:43 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="95e58-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="95e58-203">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="95e58-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="95e58-204">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="95e58-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e58-205">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="95e58-207">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="95e58-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="95e58-209">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-209">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="95e58-211">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="95e58-212">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="95e58-212">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="95e58-214">向下滚动到 "**主机别名（CNAME 记录）** " 部分，然后选择 "**编辑 CNAME 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![选择 "在主机别名下编辑 CNAME 记录"](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="95e58-216">在四个新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="95e58-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="95e58-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="95e58-217">**Alias**</span></span>|<span data-ttu-id="95e58-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="95e58-218">**TTL**</span></span>|<span data-ttu-id="95e58-219">**引用主机名**</span><span class="sxs-lookup"><span data-stu-id="95e58-219">**Refers to Host Name**</span></span>|<span data-ttu-id="95e58-220">**其他主机（选择 "**其他主机**" 选项按钮）**</span><span class="sxs-lookup"><span data-stu-id="95e58-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="95e58-221">自动发现</span><span class="sxs-lookup"><span data-stu-id="95e58-221">autodiscover</span></span>  <br/> |<span data-ttu-id="95e58-222">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-222">3600</span></span>  <br/> |<span data-ttu-id="95e58-223">（无设置）</span><span class="sxs-lookup"><span data-stu-id="95e58-223">(No setting)</span></span>  <br/> |<span data-ttu-id="95e58-224">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="95e58-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="95e58-225">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="95e58-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="95e58-226">sip</span><span class="sxs-lookup"><span data-stu-id="95e58-226">sip</span></span>  <br/> |<span data-ttu-id="95e58-227">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-227">3600</span></span>  <br/> |<span data-ttu-id="95e58-228">（无设置）</span><span class="sxs-lookup"><span data-stu-id="95e58-228">(No setting)</span></span>  <br/> |<span data-ttu-id="95e58-229">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="95e58-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="95e58-230">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="95e58-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="95e58-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="95e58-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="95e58-232">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-232">3600</span></span>  <br/> |<span data-ttu-id="95e58-233">（无设置）</span><span class="sxs-lookup"><span data-stu-id="95e58-233">(No setting)</span></span>  <br/> |<span data-ttu-id="95e58-234">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="95e58-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="95e58-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="95e58-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="95e58-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="95e58-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="95e58-237">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-237">3600</span></span>  <br/> |<span data-ttu-id="95e58-238">（无设置）</span><span class="sxs-lookup"><span data-stu-id="95e58-238">(No setting)</span></span>  <br/> |<span data-ttu-id="95e58-239">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="95e58-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="95e58-240">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="95e58-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="95e58-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="95e58-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="95e58-242">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-242">3600</span></span>  <br/> |<span data-ttu-id="95e58-243">（无设置）</span><span class="sxs-lookup"><span data-stu-id="95e58-243">(No setting)</span></span>  <br/> |<span data-ttu-id="95e58-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="95e58-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="95e58-245">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="95e58-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![为新记录键入或粘贴值](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="95e58-247">添加完所需的所有 CNAME 记录后，选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="95e58-249">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-249">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="95e58-251">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="95e58-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="95e58-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="95e58-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="95e58-253">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="95e58-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="95e58-254">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="95e58-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="95e58-255">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="95e58-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="95e58-256">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="95e58-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="95e58-257">请执行以下步骤或[观看视频（从5:35 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="95e58-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="95e58-258">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="95e58-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="95e58-259">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="95e58-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e58-260">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="95e58-262">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="95e58-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="95e58-264">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-264">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="95e58-266">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="95e58-267">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="95e58-267">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="95e58-269">向下滚动到 "**文本（TXT 记录）** " 部分，然后选择 "**编辑 TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![选择 "文本" 下的 "编辑 TXT 记录"](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="95e58-271">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="95e58-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="95e58-272">**主机**</span><span class="sxs-lookup"><span data-stu-id="95e58-272">**Host**</span></span>|<span data-ttu-id="95e58-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="95e58-273">**TTL**</span></span>|<span data-ttu-id="95e58-274">**文本**</span><span class="sxs-lookup"><span data-stu-id="95e58-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="95e58-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="95e58-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="95e58-276">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-276">3600</span></span>  <br/> |<span data-ttu-id="95e58-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="95e58-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="95e58-278">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="95e58-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![为新记录键入或粘贴值](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="95e58-280">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-280">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="95e58-282">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-282">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="95e58-284">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="95e58-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="95e58-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="95e58-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="95e58-286">请执行以下步骤或[观看视频（从6:18 开始）](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="95e58-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="95e58-287">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="95e58-287">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="95e58-288">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="95e58-288">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95e58-289">在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="95e58-291">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="95e58-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="95e58-293">选择 "**编辑 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-293">Select **Edit DNS**.</span></span>
    
    ![选择 "编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="95e58-295">选择 "**管理高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="95e58-296">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="95e58-296">(You may have to scroll down.)</span></span>
    
    ![选择 "管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="95e58-298">向下滚动到 "**服务（SRV 记录）** " 部分，然后选择 "**编辑 SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![选择 "服务" 下的 "编辑 SRV 记录"](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="95e58-300">在两个新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="95e58-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="95e58-301">（从下拉列表中选择 "**服务**" 和 "**协议**" 值。）</span><span class="sxs-lookup"><span data-stu-id="95e58-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="95e58-302">**服务**</span><span class="sxs-lookup"><span data-stu-id="95e58-302">**Service**</span></span>|<span data-ttu-id="95e58-303">**协议**</span><span class="sxs-lookup"><span data-stu-id="95e58-303">**Protocol**</span></span>|<span data-ttu-id="95e58-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="95e58-304">**TTL**</span></span>|<span data-ttu-id="95e58-305">**优先级**</span><span class="sxs-lookup"><span data-stu-id="95e58-305">**Priority**</span></span>|<span data-ttu-id="95e58-306">**权重**</span><span class="sxs-lookup"><span data-stu-id="95e58-306">**Weight**</span></span>|<span data-ttu-id="95e58-307">**端口**</span><span class="sxs-lookup"><span data-stu-id="95e58-307">**Port**</span></span>|<span data-ttu-id="95e58-308">**目标**</span><span class="sxs-lookup"><span data-stu-id="95e58-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="95e58-309">_sip</span><span class="sxs-lookup"><span data-stu-id="95e58-309">_sip</span></span>  <br/> |<span data-ttu-id="95e58-310">_tls</span><span class="sxs-lookup"><span data-stu-id="95e58-310">_tls</span></span>  <br/> |<span data-ttu-id="95e58-311">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-311">3600</span></span>  <br/> |<span data-ttu-id="95e58-312">100</span><span class="sxs-lookup"><span data-stu-id="95e58-312">100</span></span>  <br/> |<span data-ttu-id="95e58-313">1</span><span class="sxs-lookup"><span data-stu-id="95e58-313">1</span></span>  <br/> |<span data-ttu-id="95e58-314">443</span><span class="sxs-lookup"><span data-stu-id="95e58-314">443</span></span>  <br/> |<span data-ttu-id="95e58-315">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="95e58-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="95e58-316">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="95e58-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="95e58-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="95e58-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="95e58-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="95e58-318">_tcp</span></span>  <br/> |<span data-ttu-id="95e58-319">3600</span><span class="sxs-lookup"><span data-stu-id="95e58-319">3600</span></span>  <br/> |<span data-ttu-id="95e58-320">100</span><span class="sxs-lookup"><span data-stu-id="95e58-320">100</span></span>  <br/> |<span data-ttu-id="95e58-321">1</span><span class="sxs-lookup"><span data-stu-id="95e58-321">1</span></span>  <br/> |<span data-ttu-id="95e58-322">5061</span><span class="sxs-lookup"><span data-stu-id="95e58-322">5061</span></span>  <br/> |<span data-ttu-id="95e58-323">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="95e58-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="95e58-324">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="95e58-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![为新记录键入或粘贴值](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="95e58-326">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-326">Select **Continue**.</span></span>
    
    ![选择 "继续"](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="95e58-328">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="95e58-328">Select **Save Changes**.</span></span>
    
    ![选择 "保存更改"](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="95e58-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="95e58-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
