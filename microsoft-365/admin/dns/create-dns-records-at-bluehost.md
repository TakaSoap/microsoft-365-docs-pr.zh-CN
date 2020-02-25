---
title: 在 Bluehost 上为 Office 365 创建 DNS 记录
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: 了解如何在 Bluehost for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 9a5cad6778cb66958539a324befee43ddb2dd8b9
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238655"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="f3aaf-103">在 Bluehost 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="f3aaf-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="f3aaf-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f3aaf-105">如果 Bluehost 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f3aaf-106">在 Bluehost 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f3aaf-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3aaf-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f3aaf-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f3aaf-110">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f3aaf-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="f3aaf-111">Add a TXT record for verification</span></span>
<span data-ttu-id="f3aaf-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f3aaf-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f3aaf-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3aaf-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f3aaf-117">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f3aaf-118">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f3aaf-119">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f3aaf-120">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="f3aaf-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f3aaf-121">在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f3aaf-122">在 "\* \* DNS 区域编辑器 \* \*" 页上的 "**添加 DNS 记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f3aaf-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f3aaf-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f3aaf-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-124">**Host Record**</span></span> <br/> |<span data-ttu-id="f3aaf-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-125">**TTL**</span></span> <br/> |<span data-ttu-id="f3aaf-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-126">**Type**</span></span> <br/> |<span data-ttu-id="f3aaf-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="f3aaf-128">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-128">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-129">TXT</span><span class="sxs-lookup"><span data-stu-id="f3aaf-129">TXT</span></span>  <br/> |<span data-ttu-id="f3aaf-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f3aaf-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f3aaf-131">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-131">**Note:** This is an example.</span></span> <span data-ttu-id="f3aaf-132">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="f3aaf-133">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="f3aaf-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="f3aaf-134">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="f3aaf-135">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f3aaf-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f3aaf-137">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f3aaf-138">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f3aaf-139">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f3aaf-140">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f3aaf-141">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f3aaf-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f3aaf-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f3aaf-144">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f3aaf-145">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="f3aaf-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f3aaf-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f3aaf-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f3aaf-147">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f3aaf-148">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f3aaf-149">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f3aaf-150">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="f3aaf-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f3aaf-151">在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f3aaf-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f3aaf-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f3aaf-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f3aaf-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-154">**Host Record**</span></span>|<span data-ttu-id="f3aaf-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-155">**TTL**</span></span>|<span data-ttu-id="f3aaf-156">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-156">**Type**</span></span>|<span data-ttu-id="f3aaf-157">**指向**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-157">**Points To**</span></span>|<span data-ttu-id="f3aaf-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f3aaf-159">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-159">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-160">MX</span><span class="sxs-lookup"><span data-stu-id="f3aaf-160">MX</span></span>  <br/> | <span data-ttu-id="f3aaf-161">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f3aaf-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="f3aaf-162">**注意：** 从 Office \<365 帐户中获取你的*域密钥*\> 。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <span data-ttu-id="f3aaf-163">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f3aaf-163">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="f3aaf-164">0</span><span class="sxs-lookup"><span data-stu-id="f3aaf-164">0</span></span>  <br/> <span data-ttu-id="f3aaf-165">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3aaf-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![从下拉列表中选择 "类型"](../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="f3aaf-167">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-167">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="f3aaf-169">如果**mx （邮件交换器）** 部分中有任何其他 MX 记录，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="f3aaf-170">对于其中一个 MX 记录，请选择 "**删除"。**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![选择每个其他 MX 记录的 "删除"](../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="f3aaf-172">在确认对话框中，选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![选择 "确定"](../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="f3aaf-174">使用相同的过程删除已列出的任何其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f3aaf-175">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="f3aaf-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f3aaf-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f3aaf-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f3aaf-177">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f3aaf-178">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f3aaf-179">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f3aaf-180">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="f3aaf-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f3aaf-181">在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f3aaf-182">在 " **A （主机）** 记录" 部分中，找到**自动发现**记录所在的行，然后为该行选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f3aaf-183">在添加 Office 365 所需的**自动发现**记录*之前*，您必须删除现有的**自动发现**记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365.</span></span> <span data-ttu-id="f3aaf-184">Bluehost 不允许同时维护两个**自动发现**记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![选择 "删除"](../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="f3aaf-186">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-186">Select **OK**.</span></span>
    
    ![选择 "确定"](../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="f3aaf-188">创建 6 条 CNAME 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="f3aaf-189">在 " **DNS 区域编辑器**" 页上的 "**添加 DNS 记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f3aaf-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f3aaf-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f3aaf-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-191">**Host Record**</span></span>|<span data-ttu-id="f3aaf-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-192">**TTL**</span></span>|<span data-ttu-id="f3aaf-193">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-193">**Type**</span></span>|<span data-ttu-id="f3aaf-194">**指向**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f3aaf-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f3aaf-195">autodiscover</span></span>  <br/> |<span data-ttu-id="f3aaf-196">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-196">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="f3aaf-197">CNAME</span></span>  <br/> |<span data-ttu-id="f3aaf-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f3aaf-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f3aaf-199">sip</span><span class="sxs-lookup"><span data-stu-id="f3aaf-199">sip</span></span>  <br/> |<span data-ttu-id="f3aaf-200">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-200">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="f3aaf-201">CNAME</span></span>  <br/> |<span data-ttu-id="f3aaf-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f3aaf-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f3aaf-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f3aaf-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f3aaf-204">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-204">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="f3aaf-205">CNAME</span></span>  <br/> |<span data-ttu-id="f3aaf-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f3aaf-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f3aaf-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f3aaf-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f3aaf-208">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-208">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="f3aaf-209">CNAME</span></span>  <br/> |<span data-ttu-id="f3aaf-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f3aaf-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f3aaf-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f3aaf-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f3aaf-212">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-212">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="f3aaf-213">CNAME</span></span>  <br/> |<span data-ttu-id="f3aaf-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f3aaf-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![创建第一个 CNAME 记录](../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="f3aaf-216">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-216">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="f3aaf-218">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="f3aaf-219">仍在 "**添加 DNS 记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="f3aaf-220">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f3aaf-221">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="f3aaf-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f3aaf-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f3aaf-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3aaf-223">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f3aaf-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f3aaf-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f3aaf-226">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="f3aaf-227">Need examples?</span><span class="sxs-lookup"><span data-stu-id="f3aaf-227">Need examples?</span></span> <span data-ttu-id="f3aaf-228">查看[Office 365 的这些外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-228">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="f3aaf-229">若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="f3aaf-230">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f3aaf-231">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f3aaf-232">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f3aaf-233">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="f3aaf-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f3aaf-234">在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f3aaf-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f3aaf-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f3aaf-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="f3aaf-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-237">**Host Record**</span></span>|<span data-ttu-id="f3aaf-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-238">**TTL**</span></span>|<span data-ttu-id="f3aaf-239">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-239">**Type**</span></span>|<span data-ttu-id="f3aaf-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f3aaf-241">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-241">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-242">TXT</span><span class="sxs-lookup"><span data-stu-id="f3aaf-242">TXT</span></span>  <br/> |<span data-ttu-id="f3aaf-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f3aaf-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="f3aaf-244">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![复制 TXT 值](../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="f3aaf-246">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-246">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f3aaf-248">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="f3aaf-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f3aaf-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f3aaf-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f3aaf-250">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="f3aaf-251">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="f3aaf-252">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="f3aaf-253">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="f3aaf-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="f3aaf-254">在 " ***domain_name*** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="f3aaf-255">创建两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="f3aaf-256">在 " **DNS 区域编辑器**" 页上的 "**添加 DNS 记录**" 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="f3aaf-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f3aaf-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f3aaf-258">**服务**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-258">**Service**</span></span>|<span data-ttu-id="f3aaf-259">**协议**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-259">**Protocol**</span></span>|<span data-ttu-id="f3aaf-260">**主机**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-260">**Host**</span></span>|<span data-ttu-id="f3aaf-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-261">**TTL**</span></span>|<span data-ttu-id="f3aaf-262">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-262">**Type**</span></span>|<span data-ttu-id="f3aaf-263">**优先级**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-263">**Priority**</span></span>|<span data-ttu-id="f3aaf-264">**权重**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-264">**Weight**</span></span>|<span data-ttu-id="f3aaf-265">**端口**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-265">**Port**</span></span>|<span data-ttu-id="f3aaf-266">**指向**</span><span class="sxs-lookup"><span data-stu-id="f3aaf-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f3aaf-267">_sip</span><span class="sxs-lookup"><span data-stu-id="f3aaf-267">_sip</span></span>  <br/> |<span data-ttu-id="f3aaf-268">_tls</span><span class="sxs-lookup"><span data-stu-id="f3aaf-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="f3aaf-269">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-269">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-270">SRV</span><span class="sxs-lookup"><span data-stu-id="f3aaf-270">SRV</span></span>  <br/> |<span data-ttu-id="f3aaf-271">100</span><span class="sxs-lookup"><span data-stu-id="f3aaf-271">100</span></span>  <br/> |<span data-ttu-id="f3aaf-272">1</span><span class="sxs-lookup"><span data-stu-id="f3aaf-272">1</span></span>  <br/> |<span data-ttu-id="f3aaf-273">443</span><span class="sxs-lookup"><span data-stu-id="f3aaf-273">443</span></span>  <br/> |<span data-ttu-id="f3aaf-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f3aaf-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f3aaf-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f3aaf-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f3aaf-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="f3aaf-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="f3aaf-277">14400</span><span class="sxs-lookup"><span data-stu-id="f3aaf-277">14400</span></span>  <br/> |<span data-ttu-id="f3aaf-278">SRV</span><span class="sxs-lookup"><span data-stu-id="f3aaf-278">SRV</span></span>  <br/> |<span data-ttu-id="f3aaf-279">100</span><span class="sxs-lookup"><span data-stu-id="f3aaf-279">100</span></span>  <br/> |<span data-ttu-id="f3aaf-280">1</span><span class="sxs-lookup"><span data-stu-id="f3aaf-280">1</span></span>  <br/> |<span data-ttu-id="f3aaf-281">5061</span><span class="sxs-lookup"><span data-stu-id="f3aaf-281">5061</span></span>  <br/> |<span data-ttu-id="f3aaf-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f3aaf-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![复制新记录的值](../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="f3aaf-284">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-284">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="f3aaf-286">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="f3aaf-287">仍在 "**添加 DNS 记录**" 部分，使用表中其他行的值创建记录，然后再次选择 "**添加记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="f3aaf-288">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f3aaf-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f3aaf-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f3aaf-290">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f3aaf-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

