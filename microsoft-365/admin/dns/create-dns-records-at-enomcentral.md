---
title: 在 eNomCentral 上为 Office 365 创建 DNS 记录
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 了解如何在 eNomCentral for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: dec76e0dde2775851ff464e3b8765f82dfb57625
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350463"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a><span data-ttu-id="f16b7-103">在 eNomCentral 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="f16b7-103">Create DNS records at eNomCentral for Office 365</span></span>

 <span data-ttu-id="f16b7-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="f16b7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f16b7-105">如果 eNomCentral 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f16b7-106">在 eNomCentral 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="f16b7-106">After you add these records at eNomCentral, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f16b7-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f16b7-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f16b7-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="f16b7-111">Add a TXT record for verification</span></span>
<span data-ttu-id="f16b7-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f16b7-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f16b7-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f16b7-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="f16b7-117">请按下列步骤操作或[观看视频（从 0:46 开始）](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f16b7-p104">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f16b7-121">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="f16b7-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f16b7-123">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-验证-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="f16b7-125">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="f16b7-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f16b7-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f16b7-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="f16b7-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f16b7-127">**Host Name**</span></span> <br/> |<span data-ttu-id="f16b7-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f16b7-128">**Record Type**</span></span> <br/> |<span data-ttu-id="f16b7-129">**地址**</span><span class="sxs-lookup"><span data-stu-id="f16b7-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="f16b7-130">TXT</span><span class="sxs-lookup"><span data-stu-id="f16b7-130">TXT</span></span>  <br/> |<span data-ttu-id="f16b7-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f16b7-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f16b7-132">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="f16b7-132">**Note:** This is an example.</span></span> <span data-ttu-id="f16b7-133">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="f16b7-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="f16b7-134">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="f16b7-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-验证-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="f16b7-136">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-136">Select **save**.</span></span>
    
    ![eNom-验证-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="f16b7-138">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="f16b7-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f16b7-139">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f16b7-140">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="f16b7-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f16b7-141">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="f16b7-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f16b7-142">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="f16b7-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f16b7-143">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="f16b7-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f16b7-144">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="f16b7-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f16b7-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f16b7-148">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="f16b7-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f16b7-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f16b7-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f16b7-150">请执行以下步骤或[观看视频（从3:40 开始）](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f16b7-p107">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f16b7-154">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="f16b7-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f16b7-156">在 "**管理域**" 下拉列表中，选择 "**电子邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-配置-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="f16b7-158">在 "**服务选择**" 下拉列表中，选择 "**用户" （MX）**。</span><span class="sxs-lookup"><span data-stu-id="f16b7-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-配置-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="f16b7-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f16b7-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="f16b7-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f16b7-161">**Host Name**</span></span>|<span data-ttu-id="f16b7-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="f16b7-162">**Address**</span></span>|<span data-ttu-id="f16b7-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="f16b7-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="f16b7-164">*\<域密钥\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="f16b7-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="f16b7-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f16b7-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="f16b7-166">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="f16b7-166">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           <span data-ttu-id="f16b7-167">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f16b7-167">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="f16b7-168">10 </span><span class="sxs-lookup"><span data-stu-id="f16b7-168">10</span></span>  <br/> <span data-ttu-id="f16b7-169">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="f16b7-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-配置-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="f16b7-171">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-171">Select **save**.</span></span>
    
    ![eNom-配置-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="f16b7-173">如果存在任何其他现有 MX 记录，请选中这些记录的复选框以将其选中。</span><span class="sxs-lookup"><span data-stu-id="f16b7-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-配置-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="f16b7-175">选择 "**删除已选中**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-175">Select **delete checked**.</span></span>
    
    ![eNom-配置-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f16b7-177">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="f16b7-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f16b7-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f16b7-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f16b7-179">请执行以下步骤或[观看视频（从4:24 开始）](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f16b7-p109">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f16b7-183">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="f16b7-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f16b7-185">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="f16b7-187">选择 "**新建行**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-187">Select **new row**.</span></span>
    
    ![eNom-配置-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="f16b7-189">在六个新记录的框中，键入或复制并粘贴以下值。</span><span class="sxs-lookup"><span data-stu-id="f16b7-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="f16b7-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f16b7-190">**Host Name**</span></span>|<span data-ttu-id="f16b7-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f16b7-191">**Record Type**</span></span>|<span data-ttu-id="f16b7-192">**地址**</span><span class="sxs-lookup"><span data-stu-id="f16b7-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f16b7-193">自动发现</span><span class="sxs-lookup"><span data-stu-id="f16b7-193">autodiscover</span></span>  <br/> |<span data-ttu-id="f16b7-194">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="f16b7-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f16b7-195">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="f16b7-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="f16b7-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f16b7-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f16b7-197">sip</span><span class="sxs-lookup"><span data-stu-id="f16b7-197">sip</span></span>  <br/> |<span data-ttu-id="f16b7-198">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="f16b7-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f16b7-199">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f16b7-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f16b7-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f16b7-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f16b7-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f16b7-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f16b7-202">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="f16b7-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f16b7-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f16b7-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f16b7-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f16b7-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f16b7-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f16b7-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f16b7-206">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="f16b7-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f16b7-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="f16b7-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="f16b7-208">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="f16b7-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f16b7-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f16b7-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f16b7-210">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="f16b7-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f16b7-211">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="f16b7-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="f16b7-212">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="f16b7-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-配置-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="f16b7-214">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-214">Select **save**.</span></span>
    
    ![eNom-配置-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f16b7-216">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="f16b7-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f16b7-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f16b7-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f16b7-218">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="f16b7-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f16b7-219">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="f16b7-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f16b7-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f16b7-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f16b7-221">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-221">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="f16b7-222">请执行以下步骤或[观看视频（从5:12 开始）](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f16b7-p111">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f16b7-226">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="f16b7-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f16b7-228">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="f16b7-230">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="f16b7-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f16b7-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f16b7-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f16b7-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f16b7-232">**Host Name**</span></span>|<span data-ttu-id="f16b7-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f16b7-233">**Record Type**</span></span>|<span data-ttu-id="f16b7-234">**地址**</span><span class="sxs-lookup"><span data-stu-id="f16b7-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f16b7-235">TXT</span><span class="sxs-lookup"><span data-stu-id="f16b7-235">TXT</span></span>  <br/> |<span data-ttu-id="f16b7-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f16b7-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="f16b7-237">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="f16b7-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-配置-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="f16b7-239">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-239">Select **save**.</span></span>
    
    ![eNom-配置-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f16b7-241">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="f16b7-241">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f16b7-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f16b7-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="f16b7-243">请执行以下步骤或[观看视频（从5:50 开始）](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f16b7-p112">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f16b7-247">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="f16b7-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f16b7-249">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="f16b7-251">在 "**新行**" 的右侧，选择 "**添加 SRV 或 SPF 记录**"。</span><span class="sxs-lookup"><span data-stu-id="f16b7-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-配置-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="f16b7-253">在两个新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="f16b7-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="f16b7-254">**服务**</span><span class="sxs-lookup"><span data-stu-id="f16b7-254">**Service**</span></span>|<span data-ttu-id="f16b7-255">**协议**</span><span class="sxs-lookup"><span data-stu-id="f16b7-255">**Protocol**</span></span>|<span data-ttu-id="f16b7-256">**优先级**</span><span class="sxs-lookup"><span data-stu-id="f16b7-256">**Priority**</span></span>|<span data-ttu-id="f16b7-257">**权重**</span><span class="sxs-lookup"><span data-stu-id="f16b7-257">**Weight**</span></span>|<span data-ttu-id="f16b7-258">**端口**</span><span class="sxs-lookup"><span data-stu-id="f16b7-258">**Port**</span></span>|<span data-ttu-id="f16b7-259">**目标（主机名）**</span><span class="sxs-lookup"><span data-stu-id="f16b7-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f16b7-260">_sip</span><span class="sxs-lookup"><span data-stu-id="f16b7-260">_sip</span></span>  <br/> |<span data-ttu-id="f16b7-261">_tls</span><span class="sxs-lookup"><span data-stu-id="f16b7-261">_tls</span></span>  <br/> |<span data-ttu-id="f16b7-262">100</span><span class="sxs-lookup"><span data-stu-id="f16b7-262">100</span></span>  <br/> |<span data-ttu-id="f16b7-263">1</span><span class="sxs-lookup"><span data-stu-id="f16b7-263">1</span></span>  <br/> |<span data-ttu-id="f16b7-264">443</span><span class="sxs-lookup"><span data-stu-id="f16b7-264">443</span></span>  <br/> |<span data-ttu-id="f16b7-265">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f16b7-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f16b7-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f16b7-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f16b7-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f16b7-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f16b7-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="f16b7-268">_tcp</span></span>  <br/> |<span data-ttu-id="f16b7-269">100</span><span class="sxs-lookup"><span data-stu-id="f16b7-269">100</span></span>  <br/> |<span data-ttu-id="f16b7-270">1</span><span class="sxs-lookup"><span data-stu-id="f16b7-270">1</span></span>  <br/> |<span data-ttu-id="f16b7-271">5061</span><span class="sxs-lookup"><span data-stu-id="f16b7-271">5061</span></span>  <br/> |<span data-ttu-id="f16b7-272">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f16b7-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="f16b7-273">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="f16b7-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-配置-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="f16b7-275">选择 "**保存**"</span><span class="sxs-lookup"><span data-stu-id="f16b7-275">Select **save**</span></span>
    
    ![eNom-配置-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="f16b7-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f16b7-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

