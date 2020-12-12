---
title: 在 1 到 1 IONOS&MICROSOFT 的 DNS 记录
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 了解如何验证域，并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录（在 1 到 1 IONOS&IONOS）。
ms.openlocfilehash: 8e2deab05b5ef8d8f22993d2bfdd032999ed9c39
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657992"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="1ea1b-103">在 1 到 1 IONOS&MICROSOFT 的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="1ea1b-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="1ea1b-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="1ea1b-105">请注意，1&IONOS 不允许域同时具有 MX 记录和顶级自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="1ea1b-106">这将限制为 Microsoft 配置 Exchange Online 的方式。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="1ea1b-107">有一个解决方法，但我们建议仅在你已拥有在 IONOS 1 和 IONOS 1 时创建子&的经验。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="1ea1b-108">> 如果你选择在[](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)1&IONOS 处管理自己的 Microsoft DNS 记录，请按照本文中的步骤验证域并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="1ea1b-109">在 1 到 IONOS 的 1&添加这些记录后，域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="1ea1b-110">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1ea1b-111">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1ea1b-112">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1ea1b-113">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="1ea1b-113">Add a TXT record for verification</span></span>

<span data-ttu-id="1ea1b-p103">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ea1b-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="1ea1b-118">请按下列步骤操作或[观看视频（从 0:42 开始）](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="1ea1b-119">To get started， go to your domains page at 1&1 IONOS by using [this link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1ea1b-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1ea1b-121">选择 **"管理域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1ea1b-122">在 **"域** 中心"页上，找到要更新的域，然后选择该域 ( **v**) 控制面板。 </span><span class="sxs-lookup"><span data-stu-id="1ea1b-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1ea1b-123">在"**域设置"** 区域中，选择 **"编辑 DNS 设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1ea1b-124">在 **"TXT 和 SRV 记录**"部分，选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="1ea1b-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1ea1b-126">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="1ea1b-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1ea1b-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-127">**Type**</span></span> <br/> |<span data-ttu-id="1ea1b-128">**前缀**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-128">**Prefix**</span></span> <br/> |<span data-ttu-id="1ea1b-129">**名称值**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="1ea1b-130">TXT</span><span class="sxs-lookup"><span data-stu-id="1ea1b-130">TXT</span></span>  <br/> |<span data-ttu-id="1ea1b-131"> (将此字段留空) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="1ea1b-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1ea1b-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1ea1b-133">注意：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-133">NOTE: This is an example.</span></span> <span data-ttu-id="1ea1b-134">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1ea1b-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="1ea1b-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="1ea1b-136">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="1ea1b-137">再次 **选择"保存** "。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="1ea1b-138">在 **"编辑 DNS 设置**"对话框中，选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="1ea1b-139">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1ea1b-140">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="1ea1b-141">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1ea1b-142">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1ea1b-143">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="1ea1b-144">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="1ea1b-145">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ea1b-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1ea1b-147">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1ea1b-148">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1ea1b-149">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1ea1b-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1ea1b-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1ea1b-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1ea1b-151">按照下面的步骤操作或 [观看视频， (3：22 开始 ](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)) 。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ea1b-152">如果你已注册1und1.de， [请在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1ea1b-153">To get started， go to your domains page at 1&1 IONOS by using [this link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1ea1b-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1ea1b-155">选择 **"管理域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1ea1b-156">在 **"域** 中心"页上，找到要更新的域，然后选择该域 ( **v**) 控制面板。 </span><span class="sxs-lookup"><span data-stu-id="1ea1b-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1ea1b-157">在"**域设置"** 区域中，选择 **"编辑 DNS 设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1ea1b-158">In the **MX Records** section， in the **Mail Exchanger (MX Record)** area， select Other mail **server.**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="1ea1b-159">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="1ea1b-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="1ea1b-160">![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="1ea1b-161">如果已列出任何 MX 记录，请通过选择每条记录，然后按键盘上的 **Delete** 键将其删除。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="1ea1b-162"> (如果尚未列出 MX 记录，请继续执行下一) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="1ea1b-163">![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="1ea1b-164">在 **MX 1** 记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="1ea1b-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-165">**MX 1**</span></span>|<span data-ttu-id="1ea1b-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="1ea1b-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="1ea1b-168">注意：从 \<domain-key\> Microsoft 帐户获取你的帐户。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> <span data-ttu-id="1ea1b-169">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-169">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="1ea1b-170">10 </span><span class="sxs-lookup"><span data-stu-id="1ea1b-170">10</span></span>  <br/> <span data-ttu-id="1ea1b-171">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1 和 1 - 配置 2 和 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="1ea1b-173">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-173">Select **Save**.</span></span><br/><span data-ttu-id="1ea1b-174">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="1ea1b-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="1ea1b-175">![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="1ea1b-176">在 **"编辑 DNS 设置**"对话框中，选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="1ea1b-177">![在"编辑 DNS 设置"对话框中选择"是"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1ea1b-178">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="1ea1b-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1ea1b-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1ea1b-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1ea1b-180">1&IONOS 需要解决方法，以便你可以将 MX 记录与 Microsoft 电子邮件服务所需的 CNAME 记录一同使用。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="1ea1b-181">此解决方法要求您在 1 到 IONOS 的 1 和 IONOS&一组子域，并将其分配给 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1ea1b-182">在开始此过程之前，请确保至少有两个可用的子域。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="1ea1b-183">只有在您在 IONOS 1 和 IONOS 中具有创建子&时，才建议采用此解决方案。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="1ea1b-184">基本 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="1ea1b-184">Basic CNAME records</span></span>

<span data-ttu-id="1ea1b-185">按照以下步骤操作，或观看视频 ([3：57 开始 ](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)) 。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ea1b-186">如果你已注册1und1.de， [请在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1ea1b-187">To get started， go to your domains page at 1&1 IONOS by using [this link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1ea1b-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1ea1b-189">选择 **"管理域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1ea1b-190">在 **"域中心**"页上，找到要更新的域，然后选择"管理 **子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="1ea1b-191">![1 &amp; 1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="1ea1b-192">现在，您将创建两个子域并为每个子域设置 **一个别名** 值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="1ea1b-193"> (这是必需的，因为 IONOS&1 个 IONOS 仅支持一个顶级 CNAME 记录，但 Microsoft 需要多个 CNAME 记录。) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="1ea1b-194">首先，创建自动发现子域。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="1ea1b-195">在 **"子域概述**"部分，选择 **"创建子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1 &amp; 1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="1ea1b-197">在新建 **子域的**"创建子域"框中，键入或复制并粘贴下表中的"创建子域"值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-197">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="1ea1b-198"> (您将在稍后的步骤中添加 **Alias** 值。) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-198">(You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="1ea1b-199">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-199">**Create Subdomain**</span></span>|<span data-ttu-id="1ea1b-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1ea1b-201">自动发现</span><span class="sxs-lookup"><span data-stu-id="1ea1b-201">autodiscover</span></span>  <br/> |<span data-ttu-id="1ea1b-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; 1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="1ea1b-204">选择 **"创建子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="1ea1b-205">![1 &amp; 1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="1ea1b-206">在 **"子** 域概述"部分，找到您刚刚创建的自动发现子域，然后选择该子域的" (**v**) "控件。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1ea1b-207">![1 &amp; 1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="1ea1b-208">在"**子域设置**"区域中，选择 **"编辑 DNS 设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="1ea1b-209">![1 &amp; 1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="1ea1b-210">在 **"A/AAAA** (IP 地址) 部分，在 **"A Record ("** 区域 **) "CNAME"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="1ea1b-211">![1 &amp; 1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="1ea1b-212">在 **"别名：** "框中，键入或复制并粘贴下表中的 **Alias** 值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="1ea1b-213">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-213">**Create Subdomain**</span></span>|<span data-ttu-id="1ea1b-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1ea1b-215">自动发现</span><span class="sxs-lookup"><span data-stu-id="1ea1b-215">autodiscover</span></span>  <br/> |<span data-ttu-id="1ea1b-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; 1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="1ea1b-218">选中"我感知" **免责声明的** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="1ea1b-219">![1 &amp; 1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="1ea1b-220">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-220">Select **Save**.</span></span><br/><span data-ttu-id="1ea1b-221">![1 &amp; 1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="1ea1b-222">其他 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="1ea1b-222">Additional CNAME records</span></span>

<span data-ttu-id="1ea1b-223">以下过程中创建的其他 CNAME 记录将启用 Skype for Business Online 服务。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-223">The additional CNAME records created in the following procedure enable Skype for Business Online services.</span></span> <span data-ttu-id="1ea1b-224">您将采用与用于创建已创建的两个 CNAME 记录相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-224">You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="1ea1b-225">创建第三个子域 (Lyncdiscover) 。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="1ea1b-226">在 **"子域概述**"部分，选择 **"创建子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="1ea1b-227">在新建 **子域的**"创建子域"框中，键入或复制并粘贴下表中的"创建子域"值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-227">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="1ea1b-228"> (您将在稍后的步骤中添加 **Alias** 值。) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-228">(You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="1ea1b-229">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-229">**Create Subdomain**</span></span>|<span data-ttu-id="1ea1b-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1ea1b-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1ea1b-231">lyncdiscover</span></span>   |<span data-ttu-id="1ea1b-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="1ea1b-233">选择 **"创建子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="1ea1b-234">在"**域中心"** 页上，选择 **"管理子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="1ea1b-235">在 **"子** 域概述"部分，查找您刚刚创建的 **lyncdiscover** 子域，然后选择该子域的" (**v**) 控件。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1ea1b-236">在"**子域设置**"区域中，选择 **"编辑 DNS 设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="1ea1b-237">在 **"A/AAAA** (IP 地址) 部分，在 **"A Record ("** 区域 **) "CNAME"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="1ea1b-238">在 **"别名：** "框中，键入或复制并粘贴下表中的 **Alias** 值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="1ea1b-239">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-239">**Create Subdomain**</span></span>|<span data-ttu-id="1ea1b-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1ea1b-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1ea1b-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1ea1b-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="1ea1b-243">选中"我感知的免责声明"**复选框，然后选择**"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="1ea1b-244">在 **"编辑 DNS 设置**"对话框中，选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="1ea1b-245">创建 SIP 服务的第四 (子) ：</span><span class="sxs-lookup"><span data-stu-id="1ea1b-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="1ea1b-246">在 **"子域概述**"部分，选择 **"创建子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="1ea1b-247">在新建 **子域的**"创建子域"框中，键入或复制并粘贴下表中的"创建子域"值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-247">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table.</span></span> <span data-ttu-id="1ea1b-248"> (您将在稍后的步骤中添加 **Alias** 值。) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-248">(You'll add the **Alias** value in a later step.)</span></span> <br/>
    
    |<span data-ttu-id="1ea1b-249">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-249">**Create Subdomain**</span></span>|<span data-ttu-id="1ea1b-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1ea1b-251">sip</span><span class="sxs-lookup"><span data-stu-id="1ea1b-251">sip</span></span>  <br/> |<span data-ttu-id="1ea1b-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="1ea1b-253">选择 **"创建子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="1ea1b-254">在"**域中心"** 页上，选择 **"管理子域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="1ea1b-255">在 **"子** 域概述"部分，查找您刚刚创建的 **sip** 子域，然后选择该子 (**v**) 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="1ea1b-256">在"**子域设置**"区域中，选择 **"编辑 DNS 设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="1ea1b-257">在 **"A/AAAA** (IP 地址) 部分，在 **"A Record ("** 区域 **) "CNAME"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="1ea1b-258">在 **"别名：** "框中，键入或复制并粘贴下表中的 **Alias** 值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="1ea1b-259">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-259">**Create Subdomain**</span></span>|<span data-ttu-id="1ea1b-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1ea1b-261">sip</span><span class="sxs-lookup"><span data-stu-id="1ea1b-261">sip</span></span>  <br/> |<span data-ttu-id="1ea1b-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="1ea1b-263">选中"我感知的免责声明"**复选框，然后选择**"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="1ea1b-264">在 **"编辑 DNS 设置**"对话框中，选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="1ea1b-265">MDM 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="1ea1b-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ea1b-266">创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="1ea1b-267">**创建子域**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-267">**Create Subdomain**</span></span>|<span data-ttu-id="1ea1b-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ea1b-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1ea1b-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1ea1b-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1ea1b-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="1ea1b-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1ea1b-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1ea1b-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1ea1b-273">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="1ea1b-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ea1b-274">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1ea1b-275">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1ea1b-276">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1ea1b-277">相反，将所需的 Microsoft 值添加到当前记录，以便具有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="1ea1b-278">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="1ea1b-278">Need examples?</span></span> <span data-ttu-id="1ea1b-279">请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="1ea1b-280">若要验证 SPF 记录，可以使用以下[SPF 验证工具之一](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
<span data-ttu-id="1ea1b-281">按照下面的步骤操作或 [观看视频， (5：09 ](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)开始) 。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ea1b-282">如果你已注册1und1.de， [请在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1ea1b-283">To get started， go to your domains page at 1&1 IONOS by using [this link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1ea1b-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1ea1b-285">选择 **"管理域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1ea1b-286">在 **"域** 中心"页上，找到要更新的域，然后选择" (**v** ) 域的"面板"控件。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1ea1b-287">在"**域设置"** 区域中，选择 **"编辑 DNS 设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1ea1b-288">在 **"TXT 和 SRV 记录**"部分，选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="1ea1b-289">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="1ea1b-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="1ea1b-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="1ea1b-291">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="1ea1b-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="1ea1b-292">**类型**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-292">**Type**</span></span>|<span data-ttu-id="1ea1b-293">**前缀**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-293">**Prefix**</span></span>|<span data-ttu-id="1ea1b-294">**名称值**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1ea1b-295">TXT</span><span class="sxs-lookup"><span data-stu-id="1ea1b-295">TXT</span></span>  <br/> |<span data-ttu-id="1ea1b-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1ea1b-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1ea1b-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1ea1b-298">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT 记录](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="1ea1b-300">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-300">Select **Save**.</span></span><br/><span data-ttu-id="1ea1b-301">![添加记录](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="1ea1b-302">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-302">Select **Save**.</span></span><br/><span data-ttu-id="1ea1b-303">![保存记录](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="1ea1b-304">在 **"编辑 DNS 设置**"对话框中，选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="1ea1b-305">![在"编辑 DNS 设置"对话框中选择"是"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1ea1b-306">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="1ea1b-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="1ea1b-307">按照下面的步骤操作或 [观看视频， (5：51 开始 ](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)) 。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ea1b-308">如果你已注册1und1.de， [请在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="1ea1b-309">To get started， go to your domains page at 1&1 IONOS by using [this link.](https://my.1and1.com/)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="1ea1b-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="1ea1b-311">选择 **"管理域"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="1ea1b-312">在 **"域** 中心"页上，找到要更新的域，然后选择该域 ( **v**) 控制面板。 </span><span class="sxs-lookup"><span data-stu-id="1ea1b-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="1ea1b-313">在"**域设置"** 区域中，选择 **"编辑 DNS 设置"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="1ea1b-314">在 **"TXT 和 SRV 记录**"部分，选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="1ea1b-315">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="1ea1b-316">在 **"添加记录** "区域中新记录的框中，键入或复制粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="1ea1b-317"> (从下拉列表中选择 **类型和** **TTL** 值。) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1ea1b-318">**类型**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-318">**Type**</span></span>|<span data-ttu-id="1ea1b-319">**服务**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-319">**Service**</span></span>|<span data-ttu-id="1ea1b-320">**协议**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-320">**Protocol**</span></span>|<span data-ttu-id="1ea1b-321">**名称**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-321">**Name**</span></span>|<span data-ttu-id="1ea1b-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-322">**Host**</span></span>|<span data-ttu-id="1ea1b-323">**优先级**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-323">**Priority**</span></span>|<span data-ttu-id="1ea1b-324">**权重**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-324">**Weight**</span></span>|<span data-ttu-id="1ea1b-325">**端口**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-325">**Port**</span></span>|<span data-ttu-id="1ea1b-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1ea1b-327">SRV</span><span class="sxs-lookup"><span data-stu-id="1ea1b-327">SRV</span></span>  <br/> |<span data-ttu-id="1ea1b-328">sip</span><span class="sxs-lookup"><span data-stu-id="1ea1b-328">sip</span></span>  <br/> |<span data-ttu-id="1ea1b-329">tls</span><span class="sxs-lookup"><span data-stu-id="1ea1b-329">tls</span></span>  <br/> |<span data-ttu-id="1ea1b-330">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1ea1b-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1ea1b-332">100</span><span class="sxs-lookup"><span data-stu-id="1ea1b-332">100</span></span>  <br/> |<span data-ttu-id="1ea1b-333">1 </span><span class="sxs-lookup"><span data-stu-id="1ea1b-333">1</span></span>  <br/> |<span data-ttu-id="1ea1b-334">443</span><span class="sxs-lookup"><span data-stu-id="1ea1b-334">443</span></span>  <br/> |<span data-ttu-id="1ea1b-335">3600 (1 h) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="1ea1b-336">SRV</span><span class="sxs-lookup"><span data-stu-id="1ea1b-336">SRV</span></span>  <br/> |<span data-ttu-id="1ea1b-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1ea1b-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="1ea1b-338">tcp</span><span class="sxs-lookup"><span data-stu-id="1ea1b-338">tcp</span></span>  <br/> |<span data-ttu-id="1ea1b-339">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1ea1b-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1ea1b-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="1ea1b-341">100</span><span class="sxs-lookup"><span data-stu-id="1ea1b-341">100</span></span>  <br/> |<span data-ttu-id="1ea1b-342">1 </span><span class="sxs-lookup"><span data-stu-id="1ea1b-342">1</span></span>  <br/> |<span data-ttu-id="1ea1b-343">5061</span><span class="sxs-lookup"><span data-stu-id="1ea1b-343">5061</span></span>  <br/> |<span data-ttu-id="1ea1b-344">3600 (1 h) </span><span class="sxs-lookup"><span data-stu-id="1ea1b-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="1ea1b-346">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-346">Select **Save**.</span></span> <br/><span data-ttu-id="1ea1b-347">![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="1ea1b-348">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-348">Select **Save**.</span></span> <br/><span data-ttu-id="1ea1b-349">![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="1ea1b-350">在 **"编辑 DNS 设置**"对话框中，选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="1ea1b-351">![在"编辑 DNS 设置"对话框中选择"是"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="1ea1b-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="1ea1b-352">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="1ea1b-353">在 **"TXT 和 SRV 记录**"部分，选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="1ea1b-354">在 **"添加记录**"区域中，使用表中另一行的值创建记录，然后再次选择"添加"、"保存"和"是"以完成记录。 </span><span class="sxs-lookup"><span data-stu-id="1ea1b-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="1ea1b-355">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-355">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1ea1b-356">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-356">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1ea1b-357">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea1b-357">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
