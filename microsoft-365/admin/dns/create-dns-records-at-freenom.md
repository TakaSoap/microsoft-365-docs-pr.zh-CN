---
title: 在 Freenom for Microsoft 创建 DNS 记录
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: 了解如何在 Freenom for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: b958a69d1dad9a0b56cf954d12cd42e40d6d4fea
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657871"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="e5710-103">在 Freenom for Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e5710-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="e5710-104">[如果找不到 ](../setup/domains-faq.yml) 要查找的内容，请查看域常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="e5710-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e5710-105">Freenom 网站不支持 SRV 记录，这意味着多个 Skype for Business Online 和 Outlook Web App功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="e5710-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="e5710-106">无论你使用哪个 Microsoft 计划，都存在重大服务限制，并且你可能想要切换到其他 DNS 托管提供商。</span><span class="sxs-lookup"><span data-stu-id="e5710-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="e5710-107">If if the service limitations， you choose to manage your own Microsoft DNS records at Freenom， follow the steps in this article to verify your domain and set up DNS records for email and other services.</span><span class="sxs-lookup"><span data-stu-id="e5710-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="e5710-p102">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e5710-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e5710-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="e5710-111">Add a TXT record for verification</span></span>
<span data-ttu-id="e5710-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="e5710-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="e5710-p103">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="e5710-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5710-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="e5710-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e5710-117">To get started， go to your domains page in Freenom by using [this link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="e5710-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="e5710-118">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e5710-118">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="e5710-120">选择 **"** 服务"，然后选择"**我的域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="e5710-122">对于要编辑的域，选择"**管理域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    !["自由"选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="e5710-124">选择 **"管理 Freenom DNS"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="e5710-126">在 **"添加记录"** 下的 **"类型"** 列中，从菜单中选择 **TXT。**</span><span class="sxs-lookup"><span data-stu-id="e5710-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 添加记录类型 TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="e5710-128">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="e5710-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e5710-129">**名称**</span><span class="sxs-lookup"><span data-stu-id="e5710-129">**Name**</span></span>|<span data-ttu-id="e5710-130">**类型**</span><span class="sxs-lookup"><span data-stu-id="e5710-130">**Type**</span></span>|<span data-ttu-id="e5710-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5710-131">**TTL**</span></span>|<span data-ttu-id="e5710-132">**Target**</span><span class="sxs-lookup"><span data-stu-id="e5710-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5710-133">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="e5710-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="e5710-134">TXT</span><span class="sxs-lookup"><span data-stu-id="e5710-134">TXT</span></span>  <br/> |<span data-ttu-id="e5710-135">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-136">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="e5710-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="e5710-137">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="e5710-137">**Note:** This is an example.</span></span> <span data-ttu-id="e5710-138">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="e5710-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e5710-139">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="e5710-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![用于验证的 Freenom TXT 值](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="e5710-141">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT 记录 保存更改](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="e5710-143">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="e5710-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e5710-144">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="e5710-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e5710-145">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="e5710-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e5710-146">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="e5710-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e5710-147">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="e5710-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e5710-148">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="e5710-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e5710-149">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="e5710-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e5710-p107">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="e5710-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e5710-153">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5710-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e5710-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="e5710-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="e5710-155">To get started， go to your domains page in Freenom by using [this link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="e5710-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="e5710-156">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e5710-156">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="e5710-158">选择 **"** 服务"，然后选择"**我的域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="e5710-160">对于要编辑的域，选择"**管理域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    !["自由"选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="e5710-162">将域的名称设置为默认 Freenom 名称服务器。</span><span class="sxs-lookup"><span data-stu-id="e5710-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="e5710-163">选择 **"管理工具**"，然后选择 **"名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers 设置](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="e5710-165">确保 **选择了"使用默认名称服务器**"，然后选择"**更改名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="e5710-167">选择 **"管理 Freenom DNS"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-167">Select **Manage Freenom DNS**.</span></span>
    
    !["Freenom"选择"管理 Freenom DNS"](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="e5710-169">在 **"添加记录**"下的 **"类型"** 列中，从菜单中选择 **MX。**</span><span class="sxs-lookup"><span data-stu-id="e5710-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="e5710-171">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="e5710-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="e5710-172">**名称**</span><span class="sxs-lookup"><span data-stu-id="e5710-172">**Name**</span></span>|<span data-ttu-id="e5710-173">**类型**</span><span class="sxs-lookup"><span data-stu-id="e5710-173">**Type**</span></span>|<span data-ttu-id="e5710-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5710-174">**TTL**</span></span>|<span data-ttu-id="e5710-175">**Target**</span><span class="sxs-lookup"><span data-stu-id="e5710-175">**Target**</span></span>|<span data-ttu-id="e5710-176">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e5710-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5710-177">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="e5710-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="e5710-178">MX (邮件交换器) </span><span class="sxs-lookup"><span data-stu-id="e5710-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="e5710-179">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-180">\<domain-key\>.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e5710-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e5710-181">**注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。</span><span class="sxs-lookup"><span data-stu-id="e5710-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   <span data-ttu-id="e5710-182">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="e5710-182">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="e5710-183">10 </span><span class="sxs-lookup"><span data-stu-id="e5710-183">10</span></span>  <br/> <span data-ttu-id="e5710-184">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e5710-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Freenom MX 记录](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="e5710-186">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="e5710-188">如果存在任何其他 MX 记录，请全部删除它们。</span><span class="sxs-lookup"><span data-stu-id="e5710-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="e5710-189">对于每个记录，选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-189">For each record, select **Delete**.</span></span> <span data-ttu-id="e5710-190">When the message **Do you really want to remove this entry？** appears， select **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5710-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e5710-191">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="e5710-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e5710-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="e5710-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="e5710-193">To get started， go to your domains page in Freenom by using [this link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="e5710-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="e5710-194">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e5710-194">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="e5710-196">选择 **"** 服务"，然后选择"**我的域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="e5710-198">对于要编辑的域，选择"**管理域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    !["自由"选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="e5710-200">选择 **"管理 Freenom DNS"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-200">Select **Manage Freenom DNS**.</span></span>
    
    !["Freenom"选择"管理 Freenom DNS"](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="e5710-202">在 **"添加记录**"下的 **"类型"** 列中，从菜单中选择 **CNAME。**</span><span class="sxs-lookup"><span data-stu-id="e5710-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="e5710-204">创建第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e5710-204">Create the first CNAME record.</span></span> <span data-ttu-id="e5710-205">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="e5710-205">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="e5710-206">**名称**</span><span class="sxs-lookup"><span data-stu-id="e5710-206">**Name**</span></span>|<span data-ttu-id="e5710-207">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="e5710-207">**Record type**</span></span>|<span data-ttu-id="e5710-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5710-208">**TTL**</span></span>|<span data-ttu-id="e5710-209">**Target**</span><span class="sxs-lookup"><span data-stu-id="e5710-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5710-210">自动发现</span><span class="sxs-lookup"><span data-stu-id="e5710-210">autodiscover</span></span>  <br/> |<span data-ttu-id="e5710-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="e5710-211">CNAME</span></span>  <br/> |<span data-ttu-id="e5710-212">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e5710-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e5710-214">sip</span><span class="sxs-lookup"><span data-stu-id="e5710-214">sip</span></span>  <br/> |<span data-ttu-id="e5710-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="e5710-215">CNAME</span></span>  <br/> |<span data-ttu-id="e5710-216">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5710-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e5710-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e5710-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e5710-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="e5710-219">CNAME</span></span>  <br/> |<span data-ttu-id="e5710-220">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e5710-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e5710-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e5710-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e5710-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="e5710-223">CNAME</span></span>  <br/> |<span data-ttu-id="e5710-224">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e5710-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="e5710-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e5710-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e5710-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="e5710-227">CNAME</span></span>  <br/> |<span data-ttu-id="e5710-228">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5710-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME 值](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="e5710-231">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="e5710-233">重复上述步骤以创建其他五条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e5710-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="e5710-234">对于每个记录，键入或复制上表中下一行的值并将其粘贴到该记录的框中。</span><span class="sxs-lookup"><span data-stu-id="e5710-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e5710-235">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="e5710-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e5710-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="e5710-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5710-237">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="e5710-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e5710-238">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="e5710-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e5710-239">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="e5710-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e5710-240">相反，将所需的 Microsoft 值添加到当前记录，以便具有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="e5710-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="e5710-241">To get started， go to your domains page in Freenom by using [this link.](https://my.freenom.com/)</span><span class="sxs-lookup"><span data-stu-id="e5710-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="e5710-242">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="e5710-242">You'll be prompted to log in.</span></span>
    
    ![Freenom 登录](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="e5710-244">选择 **"** 服务"，然后选择"**我的域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="e5710-246">对于要编辑的域，选择"**管理域"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    !["自由"选择"管理域"](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="e5710-248">选择 **"管理 Freenom DNS"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-248">Select **Manage Freenom DNS**.</span></span>
    
    !["Freenom"选择"管理 Freenom DNS"](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="e5710-250">在 **"添加记录"** 下的 **"类型"** 列中，从菜单中选择 **TXT。**</span><span class="sxs-lookup"><span data-stu-id="e5710-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom 添加记录类型 TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="e5710-252">In the boxes for the new record, type or copy and paste the following values.</span><span class="sxs-lookup"><span data-stu-id="e5710-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="e5710-253">**名称**</span><span class="sxs-lookup"><span data-stu-id="e5710-253">**Name**</span></span>|<span data-ttu-id="e5710-254">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="e5710-254">**Record type**</span></span>|<span data-ttu-id="e5710-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e5710-255">**TTL**</span></span>|<span data-ttu-id="e5710-256">**Target**</span><span class="sxs-lookup"><span data-stu-id="e5710-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e5710-257">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="e5710-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="e5710-258">TXT</span><span class="sxs-lookup"><span data-stu-id="e5710-258">TXT</span></span>  <br/> |<span data-ttu-id="e5710-259">3600 (秒) </span><span class="sxs-lookup"><span data-stu-id="e5710-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="e5710-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e5710-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="e5710-261">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="e5710-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![SPF 的 Freenom TXT 值](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="e5710-263">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="e5710-263">Select **Save Changes**.</span></span>
    
    ![SPF 保存更改的 Freenom TXT 记录](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

