---
title: 在 Bluehost 处为 Microsoft 创建 DNS 记录
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: 了解如何验证您的域，并在 Bluehost for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: c0ba1b876c939632bc6c43a6e0004fbbe23a7723
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646231"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="480ea-103">在 Bluehost 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="480ea-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="480ea-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="480ea-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="480ea-105">如果 Bluehost 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="480ea-106">在 Bluehost 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="480ea-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="480ea-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="480ea-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="480ea-108">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="480ea-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="480ea-109">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="480ea-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="480ea-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="480ea-110">Add a TXT record for verification</span></span>
<span data-ttu-id="480ea-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="480ea-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="480ea-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="480ea-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="480ea-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="480ea-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="480ea-116">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="480ea-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="480ea-117">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="480ea-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="480ea-118">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="480ea-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="480ea-119">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="480ea-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="480ea-120">在 " \*\* _domain_name_*_" 区域的 "_* dns 区域编辑器**" 行中，选择 "**管理 DNS 记录\*\*"。</span><span class="sxs-lookup"><span data-stu-id="480ea-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="480ea-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="480ea-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="480ea-122">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="480ea-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="480ea-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="480ea-123">**Host Record**</span></span> <br/> |<span data-ttu-id="480ea-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="480ea-124">**TTL**</span></span> <br/> |<span data-ttu-id="480ea-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="480ea-125">**Type**</span></span> <br/> |<span data-ttu-id="480ea-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="480ea-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="480ea-127">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-127">14400</span></span>  <br/> |<span data-ttu-id="480ea-128">TXT</span><span class="sxs-lookup"><span data-stu-id="480ea-128">TXT</span></span>  <br/> |<span data-ttu-id="480ea-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="480ea-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="480ea-130">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="480ea-130">**Note:** This is an example.</span></span> <span data-ttu-id="480ea-131">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="480ea-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="480ea-132">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="480ea-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="480ea-133">选择 " **添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="480ea-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="480ea-134">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="480ea-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="480ea-135">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="480ea-136">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="480ea-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="480ea-137">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="480ea-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="480ea-138">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="480ea-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="480ea-139">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="480ea-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="480ea-140">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="480ea-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="480ea-141">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="480ea-141">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="480ea-142">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="480ea-142">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="480ea-143">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="480ea-143">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="480ea-144">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="480ea-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="480ea-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="480ea-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="480ea-146">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="480ea-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="480ea-147">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="480ea-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="480ea-148">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="480ea-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="480ea-149">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="480ea-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="480ea-150">在 " \*\* _domain_name_*_" 区域的 "_* dns 区域编辑器**" 行中，选择 "**管理 DNS 记录\*\*"。</span><span class="sxs-lookup"><span data-stu-id="480ea-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="480ea-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="480ea-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="480ea-152">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="480ea-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="480ea-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="480ea-153">**Host Record**</span></span>|<span data-ttu-id="480ea-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="480ea-154">**TTL**</span></span>|<span data-ttu-id="480ea-155">**类型**</span><span class="sxs-lookup"><span data-stu-id="480ea-155">**Type**</span></span>|<span data-ttu-id="480ea-156">**指向**</span><span class="sxs-lookup"><span data-stu-id="480ea-156">**Points To**</span></span>|<span data-ttu-id="480ea-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="480ea-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="480ea-158">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-158">14400</span></span>  <br/> |<span data-ttu-id="480ea-159">MX</span><span class="sxs-lookup"><span data-stu-id="480ea-159">MX</span></span>  <br/> | <span data-ttu-id="480ea-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="480ea-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="480ea-161">**注意：** 从 Microsoft 帐户获取 \<*domain-key*\>。</span><span class="sxs-lookup"><span data-stu-id="480ea-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="480ea-162">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="480ea-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="480ea-163">0</span><span class="sxs-lookup"><span data-stu-id="480ea-163">0</span></span>  <br/> <span data-ttu-id="480ea-164">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="480ea-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![从下拉列表中选择 "类型"](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="480ea-166">选择 " **添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="480ea-166">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="480ea-168">如果 Mx 中有任何其他 MX 记录 \*\* (邮件交换器) \*\* 部分，请删除每条。</span><span class="sxs-lookup"><span data-stu-id="480ea-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="480ea-169">对于其中一个 MX 记录，请选择 " **删除"。**</span><span class="sxs-lookup"><span data-stu-id="480ea-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![选择每个其他 MX 记录的 "删除"](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="480ea-171">在确认对话框中，选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="480ea-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![选择 "确定"](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="480ea-173">使用相同的过程删除已列出的任何其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="480ea-174">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="480ea-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="480ea-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="480ea-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="480ea-176">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="480ea-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="480ea-177">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="480ea-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="480ea-178">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="480ea-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="480ea-179">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="480ea-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="480ea-180">在 " \*\* _domain_name_*_" 区域的 "_* dns 区域编辑器**" 行中，选择 "**管理 DNS 记录\*\*"。</span><span class="sxs-lookup"><span data-stu-id="480ea-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="480ea-181">在 " \*\* (主机) \*\* 记录" 部分，找到 **自动发现** 记录的行，然后选择该行的 " **删除** "。</span><span class="sxs-lookup"><span data-stu-id="480ea-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="480ea-182">在添加 Microsoft 所需的**自动发现**记录*之前*，必须删除现有的**自动发现**记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="480ea-183">Bluehost 不允许同时维护两个 **自动发现** 记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![选择“删除”](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="480ea-185">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="480ea-185">Select **OK**.</span></span>
    
    ![选择 "确定"](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="480ea-187">创建 6 条 CNAME 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="480ea-188">在 " **DNS 区域编辑器** " 页上的 " **添加 DNS 记录** " 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="480ea-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="480ea-189">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="480ea-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="480ea-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="480ea-190">**Host Record**</span></span>|<span data-ttu-id="480ea-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="480ea-191">**TTL**</span></span>|<span data-ttu-id="480ea-192">**类型**</span><span class="sxs-lookup"><span data-stu-id="480ea-192">**Type**</span></span>|<span data-ttu-id="480ea-193">**指向**</span><span class="sxs-lookup"><span data-stu-id="480ea-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="480ea-194">自动发现</span><span class="sxs-lookup"><span data-stu-id="480ea-194">autodiscover</span></span>  <br/> |<span data-ttu-id="480ea-195">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-195">14400</span></span>  <br/> |<span data-ttu-id="480ea-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="480ea-196">CNAME</span></span>  <br/> |<span data-ttu-id="480ea-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="480ea-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="480ea-198">sip</span><span class="sxs-lookup"><span data-stu-id="480ea-198">sip</span></span>  <br/> |<span data-ttu-id="480ea-199">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-199">14400</span></span>  <br/> |<span data-ttu-id="480ea-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="480ea-200">CNAME</span></span>  <br/> |<span data-ttu-id="480ea-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="480ea-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="480ea-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="480ea-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="480ea-203">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-203">14400</span></span>  <br/> |<span data-ttu-id="480ea-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="480ea-204">CNAME</span></span>  <br/> |<span data-ttu-id="480ea-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="480ea-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="480ea-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="480ea-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="480ea-207">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-207">14400</span></span>  <br/> |<span data-ttu-id="480ea-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="480ea-208">CNAME</span></span>  <br/> |<span data-ttu-id="480ea-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="480ea-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="480ea-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="480ea-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="480ea-211">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-211">14400</span></span>  <br/> |<span data-ttu-id="480ea-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="480ea-212">CNAME</span></span>  <br/> |<span data-ttu-id="480ea-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="480ea-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![创建第一个 CNAME 记录](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="480ea-215">选择 " **添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="480ea-215">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="480ea-217">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="480ea-218">仍在 " **添加 DNS 记录** " 部分，使用表中下一行的值创建记录，然后再次选择 " **添加记录** " 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="480ea-219">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="480ea-220">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="480ea-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="480ea-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="480ea-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="480ea-222">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="480ea-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="480ea-223">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="480ea-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="480ea-224">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="480ea-225">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的  *单个*  SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="480ea-226">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="480ea-226">Need examples?</span></span> <span data-ttu-id="480ea-227">请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="480ea-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="480ea-228">若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="480ea-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="480ea-229">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="480ea-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="480ea-230">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="480ea-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="480ea-231">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="480ea-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="480ea-232">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="480ea-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="480ea-233">在 " \*\* _domain_name_*_" 区域的 "_* dns 区域编辑器**" 行中，选择 "**管理 DNS 记录\*\*"。</span><span class="sxs-lookup"><span data-stu-id="480ea-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="480ea-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="480ea-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="480ea-235">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="480ea-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="480ea-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="480ea-236">**Host Record**</span></span>|<span data-ttu-id="480ea-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="480ea-237">**TTL**</span></span>|<span data-ttu-id="480ea-238">**类型**</span><span class="sxs-lookup"><span data-stu-id="480ea-238">**Type**</span></span>|<span data-ttu-id="480ea-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="480ea-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="480ea-240">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-240">14400</span></span>  <br/> |<span data-ttu-id="480ea-241">TXT</span><span class="sxs-lookup"><span data-stu-id="480ea-241">TXT</span></span>  <br/> |<span data-ttu-id="480ea-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="480ea-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="480ea-243">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="480ea-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![复制 TXT 值](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="480ea-245">选择 " **添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="480ea-245">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="480ea-247">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="480ea-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="480ea-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="480ea-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="480ea-249">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="480ea-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="480ea-250">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="480ea-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="480ea-251">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="480ea-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="480ea-252">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="480ea-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="480ea-253">在 " \*\* _domain_name_*_" 区域的 "_* dns 区域编辑器**" 行中，选择 "**管理 DNS 记录\*\*"。</span><span class="sxs-lookup"><span data-stu-id="480ea-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="480ea-254">创建两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="480ea-255">在 " **DNS 区域编辑器** " 页上的 " **添加 DNS 记录** " 区域中，在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="480ea-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="480ea-256">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="480ea-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="480ea-257">**服务**</span><span class="sxs-lookup"><span data-stu-id="480ea-257">**Service**</span></span>|<span data-ttu-id="480ea-258">**协议**</span><span class="sxs-lookup"><span data-stu-id="480ea-258">**Protocol**</span></span>|<span data-ttu-id="480ea-259">**主机**</span><span class="sxs-lookup"><span data-stu-id="480ea-259">**Host**</span></span>|<span data-ttu-id="480ea-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="480ea-260">**TTL**</span></span>|<span data-ttu-id="480ea-261">**类型**</span><span class="sxs-lookup"><span data-stu-id="480ea-261">**Type**</span></span>|<span data-ttu-id="480ea-262">**优先级**</span><span class="sxs-lookup"><span data-stu-id="480ea-262">**Priority**</span></span>|<span data-ttu-id="480ea-263">**权重**</span><span class="sxs-lookup"><span data-stu-id="480ea-263">**Weight**</span></span>|<span data-ttu-id="480ea-264">**端口**</span><span class="sxs-lookup"><span data-stu-id="480ea-264">**Port**</span></span>|<span data-ttu-id="480ea-265">**指向**</span><span class="sxs-lookup"><span data-stu-id="480ea-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="480ea-266">_sip</span><span class="sxs-lookup"><span data-stu-id="480ea-266">_sip</span></span>  <br/> |<span data-ttu-id="480ea-267">_tls</span><span class="sxs-lookup"><span data-stu-id="480ea-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="480ea-268">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-268">14400</span></span>  <br/> |<span data-ttu-id="480ea-269">SRV</span><span class="sxs-lookup"><span data-stu-id="480ea-269">SRV</span></span>  <br/> |<span data-ttu-id="480ea-270">100</span><span class="sxs-lookup"><span data-stu-id="480ea-270">100</span></span>  <br/> |<span data-ttu-id="480ea-271">1</span><span class="sxs-lookup"><span data-stu-id="480ea-271">1</span></span>  <br/> |<span data-ttu-id="480ea-272">443</span><span class="sxs-lookup"><span data-stu-id="480ea-272">443</span></span>  <br/> |<span data-ttu-id="480ea-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="480ea-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="480ea-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="480ea-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="480ea-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="480ea-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="480ea-276">14400</span><span class="sxs-lookup"><span data-stu-id="480ea-276">14400</span></span>  <br/> |<span data-ttu-id="480ea-277">SRV</span><span class="sxs-lookup"><span data-stu-id="480ea-277">SRV</span></span>  <br/> |<span data-ttu-id="480ea-278">100</span><span class="sxs-lookup"><span data-stu-id="480ea-278">100</span></span>  <br/> |<span data-ttu-id="480ea-279">1</span><span class="sxs-lookup"><span data-stu-id="480ea-279">1</span></span>  <br/> |<span data-ttu-id="480ea-280">5061</span><span class="sxs-lookup"><span data-stu-id="480ea-280">5061</span></span>  <br/> |<span data-ttu-id="480ea-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="480ea-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![复制新记录的值](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="480ea-283">选择 " **添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="480ea-283">Select **add record**.</span></span>
    
    ![选择 "添加记录"](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="480ea-285">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="480ea-286">仍在 " **添加 DNS 记录** " 部分，使用表中其他行的值创建记录，然后再次选择 " **添加记录** " 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="480ea-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="480ea-287">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="480ea-287">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="480ea-288">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="480ea-288">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="480ea-289">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="480ea-289">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

