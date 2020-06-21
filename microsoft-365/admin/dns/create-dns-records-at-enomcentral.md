---
title: 在 eNomCentral 处为 Microsoft 创建 DNS 记录
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 了解如何验证您的域，并在 eNomCentral for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780393"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="dbd9c-103">在 eNomCentral 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="dbd9c-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="dbd9c-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dbd9c-105">如果 eNomCentral 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="dbd9c-106">在 eNomCentral 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="dbd9c-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="dbd9c-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="dbd9c-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dbd9c-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="dbd9c-110">Add a TXT record for verification</span></span>
<span data-ttu-id="dbd9c-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd9c-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="dbd9c-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="dbd9c-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dbd9c-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="dbd9c-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="dbd9c-116">请按下列步骤操作或[观看视频（从 0:46 开始）](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="dbd9c-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="dbd9c-118">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-118">You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dbd9c-120">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dbd9c-122">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-验证-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="dbd9c-124">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="dbd9c-125">从下拉列表中选择 "**记录类型**" 值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="dbd9c-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-126">**Host Name**</span></span> <br/> |<span data-ttu-id="dbd9c-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-127">**Record Type**</span></span> <br/> |<span data-ttu-id="dbd9c-128">**地址**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="dbd9c-129">TXT</span><span class="sxs-lookup"><span data-stu-id="dbd9c-129">TXT</span></span>  <br/> |<span data-ttu-id="dbd9c-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dbd9c-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dbd9c-131">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-131">**Note:** This is an example.</span></span> <span data-ttu-id="dbd9c-132">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="dbd9c-133">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="dbd9c-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-验证-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="dbd9c-135">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-135">Select **save**.</span></span>
    
    ![eNom-验证-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="dbd9c-137">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dbd9c-138">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="dbd9c-139">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dbd9c-140">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="dbd9c-141">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dbd9c-142">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dbd9c-143">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dbd9c-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="dbd9c-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="dbd9c-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dbd9c-147">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="dbd9c-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="dbd9c-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd9c-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="dbd9c-149">请执行以下步骤或[观看视频（从3:40 开始）](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="dbd9c-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="dbd9c-151">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-151">You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dbd9c-153">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dbd9c-155">在 "**管理域**" 下拉列表中，选择 "**电子邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-配置-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="dbd9c-157">在 "**服务选择**" 下拉列表中，选择 "**用户" （MX）**。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-配置-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="dbd9c-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dbd9c-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-160">**Host Name**</span></span>|<span data-ttu-id="dbd9c-161">**Address**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-161">**Address**</span></span>|<span data-ttu-id="dbd9c-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="dbd9c-163">*\<domain-key\>*. mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="dbd9c-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="dbd9c-165">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           <span data-ttu-id="dbd9c-166">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="dbd9c-166">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="dbd9c-167">10  </span><span class="sxs-lookup"><span data-stu-id="dbd9c-167">10</span></span>  <br/> <span data-ttu-id="dbd9c-168">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="dbd9c-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![eNom-配置-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="dbd9c-170">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-170">Select **save**.</span></span>
    
    ![eNom-配置-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="dbd9c-172">如果存在任何其他现有 MX 记录，请选中这些记录的复选框以将其选中。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-配置-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="dbd9c-174">选择 "**删除已选中**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-174">Select **delete checked**.</span></span>
    
    ![eNom-配置-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="dbd9c-176">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="dbd9c-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="dbd9c-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd9c-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="dbd9c-178">请执行以下步骤或[观看视频（从4:24 开始）](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="dbd9c-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="dbd9c-180">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-180">You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dbd9c-182">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dbd9c-184">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="dbd9c-186">选择 "**新建行**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-186">Select **new row**.</span></span>
    
    ![eNom-配置-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="dbd9c-188">在六个新记录的框中，键入或复制并粘贴以下值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="dbd9c-189">从下拉列表中选择 "**记录类型**" 值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="dbd9c-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-190">**Host Name**</span></span>|<span data-ttu-id="dbd9c-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-191">**Record Type**</span></span>|<span data-ttu-id="dbd9c-192">**地址**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dbd9c-193">自动发现</span><span class="sxs-lookup"><span data-stu-id="dbd9c-193">autodiscover</span></span>  <br/> |<span data-ttu-id="dbd9c-194">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="dbd9c-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dbd9c-195">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="dbd9c-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dbd9c-197">sip</span><span class="sxs-lookup"><span data-stu-id="dbd9c-197">sip</span></span>  <br/> |<span data-ttu-id="dbd9c-198">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="dbd9c-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dbd9c-199">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dbd9c-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dbd9c-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dbd9c-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dbd9c-202">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="dbd9c-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dbd9c-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dbd9c-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dbd9c-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dbd9c-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dbd9c-206">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="dbd9c-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dbd9c-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="dbd9c-208">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dbd9c-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dbd9c-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dbd9c-210">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="dbd9c-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="dbd9c-211">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="dbd9c-212">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="dbd9c-213">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-213">Select **save**.</span></span>
    
    ![eNom-配置-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dbd9c-215">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="dbd9c-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dbd9c-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd9c-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbd9c-217">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dbd9c-218">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dbd9c-219">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="dbd9c-220">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="dbd9c-221">请执行以下步骤或[观看视频（从5:12 开始）](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-221">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="dbd9c-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="dbd9c-223">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-223">You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dbd9c-225">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dbd9c-227">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="dbd9c-229">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="dbd9c-230">从下拉列表中选择 "**记录类型**" 值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="dbd9c-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-231">**Host Name**</span></span>|<span data-ttu-id="dbd9c-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-232">**Record Type**</span></span>|<span data-ttu-id="dbd9c-233">**地址**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="dbd9c-234">TXT</span><span class="sxs-lookup"><span data-stu-id="dbd9c-234">TXT</span></span>  <br/> |<span data-ttu-id="dbd9c-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dbd9c-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="dbd9c-236">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-配置-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="dbd9c-238">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-238">Select **save**.</span></span>
    
    ![eNom-配置-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="dbd9c-240">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="dbd9c-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="dbd9c-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd9c-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="dbd9c-242">请执行以下步骤或[观看视频（从5:50 开始）](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-242">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="dbd9c-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="dbd9c-244">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-244">You'll be prompted to login.</span></span>
    
    ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="dbd9c-246">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="dbd9c-248">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="dbd9c-250">在 "**新行**" 的右侧，选择 "**添加 SRV 或 SPF 记录**"。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-配置-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="dbd9c-252">在两个新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dbd9c-253">**服务**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-253">**Service**</span></span>|<span data-ttu-id="dbd9c-254">**协议**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-254">**Protocol**</span></span>|<span data-ttu-id="dbd9c-255">**优先级**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-255">**Priority**</span></span>|<span data-ttu-id="dbd9c-256">**权重**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-256">**Weight**</span></span>|<span data-ttu-id="dbd9c-257">**端口**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-257">**Port**</span></span>|<span data-ttu-id="dbd9c-258">**目标（主机名）**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dbd9c-259">_sip</span><span class="sxs-lookup"><span data-stu-id="dbd9c-259">_sip</span></span>  <br/> |<span data-ttu-id="dbd9c-260">_tls</span><span class="sxs-lookup"><span data-stu-id="dbd9c-260">_tls</span></span>  <br/> |<span data-ttu-id="dbd9c-261">100</span><span class="sxs-lookup"><span data-stu-id="dbd9c-261">100</span></span>  <br/> |<span data-ttu-id="dbd9c-262">1 </span><span class="sxs-lookup"><span data-stu-id="dbd9c-262">1</span></span>  <br/> |<span data-ttu-id="dbd9c-263">443</span><span class="sxs-lookup"><span data-stu-id="dbd9c-263">443</span></span>  <br/> |<span data-ttu-id="dbd9c-264">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dbd9c-265">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="dbd9c-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="dbd9c-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="dbd9c-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="dbd9c-267">_tcp</span></span>  <br/> |<span data-ttu-id="dbd9c-268">100</span><span class="sxs-lookup"><span data-stu-id="dbd9c-268">100</span></span>  <br/> |<span data-ttu-id="dbd9c-269">1 </span><span class="sxs-lookup"><span data-stu-id="dbd9c-269">1</span></span>  <br/> |<span data-ttu-id="dbd9c-270">5061</span><span class="sxs-lookup"><span data-stu-id="dbd9c-270">5061</span></span>  <br/> |<span data-ttu-id="dbd9c-271">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dbd9c-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="dbd9c-272">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dbd9c-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-配置-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="dbd9c-274">选择 "**保存**"</span><span class="sxs-lookup"><span data-stu-id="dbd9c-274">Select **save**</span></span>
    
    ![eNom-配置-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="dbd9c-276">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-276">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="dbd9c-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="dbd9c-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="dbd9c-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dbd9c-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

