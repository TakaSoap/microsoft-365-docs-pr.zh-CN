---
title: 在 Google Domains 为 Microsoft 创建 DNS 记录
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 了解如何在 Google Domains 验证你的域并为 Microsoft 设置电子邮件、Lync 和其他服务的 DNS 记录。
ms.openlocfilehash: 48e23c180533bab2a73e06dd4a45a9c4016680ae
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221951"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="060cf-103">在 Google Domains 为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="060cf-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="060cf-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="060cf-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="060cf-105">如果 DNS 托管提供商是 Google Domains，请按照本文中的步骤验证域并为电子邮件、Lync 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="060cf-106">在 Google Domains 添加这些记录后，你的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="060cf-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="060cf-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="060cf-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="060cf-108">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="060cf-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="060cf-109">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Microsoft 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="060cf-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="060cf-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="060cf-110">Add a TXT record for verification</span></span>
<span data-ttu-id="060cf-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="060cf-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="060cf-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="060cf-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="060cf-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="060cf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="060cf-p104">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="060cf-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="060cf-119">选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="060cf-120">输入登录凭据，然后再次选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="060cf-121">在“**我的域**”页面上，找到要与 Microsoft 一起使用的域，然后选择其旁边的“**管理**”链接。</span><span class="sxs-lookup"><span data-stu-id="060cf-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="060cf-122">在左侧导航窗格中，选择“**DNS**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="060cf-123">在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="060cf-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="060cf-124">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="060cf-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="060cf-125">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="060cf-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="060cf-126">**名称**</span><span class="sxs-lookup"><span data-stu-id="060cf-126">**Name**</span></span> <br/> |<span data-ttu-id="060cf-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="060cf-127">**Type**</span></span> <br/> |<span data-ttu-id="060cf-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="060cf-128">**TTL**</span></span> <br/> |<span data-ttu-id="060cf-129">**数据**</span><span class="sxs-lookup"><span data-stu-id="060cf-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="060cf-130">TXT</span><span class="sxs-lookup"><span data-stu-id="060cf-130">TXT</span></span>  <br/> |<span data-ttu-id="060cf-131">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-131">1H</span></span>  <br/> |<span data-ttu-id="060cf-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="060cf-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="060cf-133">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="060cf-133">**Note:** This is an example.</span></span> <span data-ttu-id="060cf-134">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="060cf-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="060cf-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="060cf-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="060cf-136">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="060cf-137">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="060cf-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="060cf-138">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="060cf-139">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="060cf-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="060cf-140">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="060cf-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="060cf-141">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="060cf-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="060cf-142">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="060cf-143">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="060cf-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="060cf-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="060cf-145">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="060cf-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="060cf-146">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="060cf-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="060cf-147">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="060cf-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="060cf-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="060cf-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="060cf-p108">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="060cf-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="060cf-152">选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="060cf-153">输入登录凭据，然后再次选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="060cf-154">在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="060cf-155">如果有 G Suite 电子邮件帐户，必须先删除与该帐户关联的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="060cf-156">G Suite 的 MX 记录将导致无法添加任何其他 MX 记录，包括 Microsoft 所需的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="060cf-157">请注意，删除 G 套件记录不会删除 G 套件帐户。</span><span class="sxs-lookup"><span data-stu-id="060cf-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="060cf-158">若要删除 G 套件 MX 记录，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="060cf-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="060cf-159">首先，在“**综合记录**”部分的“**G Suite**”区域中，选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="060cf-160">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="060cf-160">(You may have to scroll down.)</span></span>
    
    ![在“综合记录”部分中选择“删除”](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="060cf-162">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-162">Select **Delete**.</span></span>
    
    ![选择“删除”](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="060cf-164">在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="060cf-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="060cf-165">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="060cf-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="060cf-166">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="060cf-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="060cf-167">**名称**</span><span class="sxs-lookup"><span data-stu-id="060cf-167">**Name**</span></span>|<span data-ttu-id="060cf-168">**类型**</span><span class="sxs-lookup"><span data-stu-id="060cf-168">**Type**</span></span>|<span data-ttu-id="060cf-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="060cf-169">**TTL**</span></span>|<span data-ttu-id="060cf-170">**数据**</span><span class="sxs-lookup"><span data-stu-id="060cf-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="060cf-171">MX</span><span class="sxs-lookup"><span data-stu-id="060cf-171">MX</span></span>  <br/> |<span data-ttu-id="060cf-172">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-172">1H</span></span>  <br/> |<span data-ttu-id="060cf-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="060cf-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="060cf-174">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="060cf-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="060cf-p110">**0** 是 MX 优先级值。将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  </span><span class="sxs-lookup"><span data-stu-id="060cf-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="060cf-177">**注意：** 从 Microsoft 帐户获取 \<*domain-key*\>。</span><span class="sxs-lookup"><span data-stu-id="060cf-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="060cf-178">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="060cf-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="060cf-179">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="060cf-179">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![在“自定义资源记录”部分键入或粘贴值](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="060cf-181">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-181">Select **Add**.</span></span>
    
    ![选择“添加”](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="060cf-183">如果有任何其他自定义 MX 记录，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="060cf-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="060cf-184">选择相应 MX 记录行中的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-184">Select **Edit** in the MX record row.</span></span> 
    
    ![选择相应 MX 记录行中的“编辑”](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="060cf-186">针对每条其他自定义 MX 记录，选择“**数据**”框中的条目，然后按键盘上的 **Delete** 键删除该记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="060cf-187">继续操作，直到删除所有其他 MX 记录的“**数据**”条目。</span><span class="sxs-lookup"><span data-stu-id="060cf-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="060cf-189">删除所有其他 MX 记录的“**数据**”条目后，选择“**保存**”以保存更改。</span><span class="sxs-lookup"><span data-stu-id="060cf-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![选择“保存”](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="060cf-191">添加 Microsoft 所需的 5 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="060cf-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="060cf-192">若要开始，请转到 [Google Domains 页面] (https://domains.google.com/registrar) 并登录。</span><span class="sxs-lookup"><span data-stu-id="060cf-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="060cf-193">在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="060cf-194">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="060cf-195">在“**自定义资源记录**”部分中新记录的框内，键入或复制粘贴下表第一行中的值。</span><span class="sxs-lookup"><span data-stu-id="060cf-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="060cf-196">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="060cf-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="060cf-197">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="060cf-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="060cf-198">**名称**</span><span class="sxs-lookup"><span data-stu-id="060cf-198">**Name**</span></span>|<span data-ttu-id="060cf-199">**类型**</span><span class="sxs-lookup"><span data-stu-id="060cf-199">**Type**</span></span>|<span data-ttu-id="060cf-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="060cf-200">**TTL**</span></span>|<span data-ttu-id="060cf-201">**数据**</span><span class="sxs-lookup"><span data-stu-id="060cf-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="060cf-202">自动发现</span><span class="sxs-lookup"><span data-stu-id="060cf-202">autodiscover</span></span>  <br/> |<span data-ttu-id="060cf-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="060cf-203">CNAME</span></span>  <br/> |<span data-ttu-id="060cf-204">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-204">1H</span></span>  <br/> |<span data-ttu-id="060cf-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="060cf-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="060cf-206">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="060cf-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="060cf-207">sip</span><span class="sxs-lookup"><span data-stu-id="060cf-207">sip</span></span>  <br/> |<span data-ttu-id="060cf-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="060cf-208">CNAME</span></span>  <br/> |<span data-ttu-id="060cf-209">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-209">1H</span></span>  <br/> |<span data-ttu-id="060cf-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="060cf-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="060cf-211">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="060cf-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="060cf-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="060cf-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="060cf-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="060cf-213">CNAME</span></span>  <br/> |<span data-ttu-id="060cf-214">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-214">1H</span></span>  <br/> |<span data-ttu-id="060cf-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="060cf-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="060cf-216">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="060cf-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="060cf-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="060cf-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="060cf-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="060cf-218">CNAME</span></span>  <br/> |<span data-ttu-id="060cf-219">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-219">1H</span></span>  <br/> |<span data-ttu-id="060cf-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="060cf-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="060cf-221">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="060cf-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="060cf-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="060cf-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="060cf-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="060cf-223">CNAME</span></span>  <br/> |<span data-ttu-id="060cf-224">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-224">1H</span></span>  <br/> |<span data-ttu-id="060cf-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="060cf-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="060cf-226">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="060cf-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![在“自定义资源记录”部分键入或粘贴值](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="060cf-228">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-228">Select **Add**.</span></span>
    
    ![选择“添加”](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="060cf-230">添加其他 4 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="060cf-231">在“**自定义资源记录**”部分，使用表中下一行的值创建记录，然后再次选择“**添加**”完成该记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="060cf-232">重复该过程，直到创建完所需的所有 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="060cf-233">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="060cf-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="060cf-234">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="060cf-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="060cf-235">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="060cf-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="060cf-236">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="060cf-237">可以将所需的 Microsoft 值添加到当前记录，这样就拥有包含两组值的单个 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="060cf-238">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="060cf-238">Need examples?</span></span> <span data-ttu-id="060cf-239">请查看 [Microsoft 的外部域名系统记录](../../enterprise/external-domain-name-system-records.md)。</span><span class="sxs-lookup"><span data-stu-id="060cf-239">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="060cf-240">若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="060cf-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="060cf-p113">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="060cf-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="060cf-244">选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="060cf-245">输入登录凭据，然后再次选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="060cf-246">在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="060cf-247">在“**自定义资源记录**”部分的 TXT 记录行上，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="060cf-p114">Google Domains 会将 TXT 记录存储为可能含有多条记录的集。存在至少一条其他 TXT 记录（例如用于验证域的 TXT 记录）时，必须向该记录集添加新的 TXT 记录。如果尝试将其他 TXT 记录作为单独条目进行输入，将始终出现“**记录重复**”错误信息。</span><span class="sxs-lookup"><span data-stu-id="060cf-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![选择相应 TXT 记录行中的“编辑”](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="060cf-252">选择 **(+)** 控件。</span><span class="sxs-lookup"><span data-stu-id="060cf-252">Select the **(+)** control.</span></span> 
    
    ![选择加号控件](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="060cf-254">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="060cf-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="060cf-255">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="060cf-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="060cf-256">**数据**</span><span class="sxs-lookup"><span data-stu-id="060cf-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="060cf-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="060cf-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="060cf-258">我们建议复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="060cf-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![在“自定义资源记录”部分键入或粘贴值](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="060cf-260">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-260">Select **Save**.</span></span>
    
    ![选择“保存”](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="060cf-262">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="060cf-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="060cf-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="060cf-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="060cf-p115">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="060cf-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="060cf-267">选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="060cf-268">输入登录凭据，然后再次选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="060cf-269">在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="060cf-270">添加第一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="060cf-271">在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="060cf-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="060cf-272">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="060cf-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="060cf-273">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="060cf-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="060cf-274">**名称**</span><span class="sxs-lookup"><span data-stu-id="060cf-274">**Name**</span></span>|<span data-ttu-id="060cf-275">**类型**</span><span class="sxs-lookup"><span data-stu-id="060cf-275">**Type**</span></span>|<span data-ttu-id="060cf-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="060cf-276">**TTL**</span></span>|<span data-ttu-id="060cf-277">**数据**</span><span class="sxs-lookup"><span data-stu-id="060cf-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="060cf-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="060cf-278">_sip._tls</span></span>|<span data-ttu-id="060cf-279">SRV</span><span class="sxs-lookup"><span data-stu-id="060cf-279">SRV</span></span>|<span data-ttu-id="060cf-280">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-280">1H</span></span>|<span data-ttu-id="060cf-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="060cf-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="060cf-282">**此值必须以句点 (.) 结尾。** **注意：** 我们建议复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="060cf-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="060cf-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="060cf-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="060cf-284">SRV</span><span class="sxs-lookup"><span data-stu-id="060cf-284">SRV</span></span>|<span data-ttu-id="060cf-285">1H</span><span class="sxs-lookup"><span data-stu-id="060cf-285">1H</span></span>|<span data-ttu-id="060cf-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="060cf-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="060cf-287">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="060cf-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="060cf-288">我们建议复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="060cf-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![在“自定义资源记录”部分键入或粘贴值](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="060cf-290">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="060cf-290">Select **Add**.</span></span>
    
    ![选择“添加”](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="060cf-292">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="060cf-293">在“**自定义资源记录**”部分，使用表中第二行的值创建记录，然后再次选择“**添加**”完成该记录。</span><span class="sxs-lookup"><span data-stu-id="060cf-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="060cf-294">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="060cf-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="060cf-295">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="060cf-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="060cf-296">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="060cf-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
