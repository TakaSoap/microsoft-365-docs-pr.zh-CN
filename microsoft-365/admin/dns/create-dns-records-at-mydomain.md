---
title: 在 MyDomain 处为 Microsoft 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: 了解如何在 MyDomain 处验证你的域并设置电子邮件、Skype for Business Online 和其他 Microsoft 服务的 DNS 记录。
ms.openlocfilehash: 1c6edc1e3ad03b0467c70741d4097cf3a3b5e196
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400408"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="687ee-103">在 MyDomain 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="687ee-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="687ee-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="687ee-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="687ee-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="687ee-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="687ee-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="687ee-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="687ee-107">如果忽略服务限制，选择在 MyDomain 处管理自己的 Microsoft DNS 记录，请按本文中的步骤为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="687ee-108">在 MyDomain 添加这些记录后，你的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="687ee-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="687ee-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="687ee-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="687ee-110">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="687ee-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="687ee-111">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="687ee-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="687ee-112">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="687ee-112">Add a TXT record for verification</span></span>
<span data-ttu-id="687ee-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="687ee-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="687ee-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="687ee-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="687ee-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="687ee-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="687ee-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="687ee-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="687ee-117">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="687ee-117">You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="687ee-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="687ee-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="687ee-119">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="687ee-119">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="687ee-120">在“**我的收藏夹**”部分，选择则“**域中心**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="687ee-121">在“**域**”下，选择要编辑的域名。</span><span class="sxs-lookup"><span data-stu-id="687ee-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="687ee-122">在“**概述**”行，选择“**DNS**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="687ee-123">在“**修改**”下拉列表中，选择“**TXT/SPF 记录**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="687ee-124">在" **内容**"下方新记录对应的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="687ee-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="687ee-125">**内容**</span><span class="sxs-lookup"><span data-stu-id="687ee-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="687ee-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="687ee-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="687ee-127">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="687ee-127">**Note:** This is an example.</span></span> <span data-ttu-id="687ee-128">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="687ee-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="687ee-129">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="687ee-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="687ee-130">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="687ee-131">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="687ee-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="687ee-132">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="687ee-133">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="687ee-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="687ee-134">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="687ee-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="687ee-135">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="687ee-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="687ee-136">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="687ee-137">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="687ee-138">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="687ee-138">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="687ee-139">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="687ee-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="687ee-140">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="687ee-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="687ee-141">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="687ee-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="687ee-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="687ee-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="687ee-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="687ee-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="687ee-144">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="687ee-144">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="687ee-145">在“**我的收藏夹**”部分，选择则“**域中心**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="687ee-146">在“**域**”下，选择要编辑的域名。</span><span class="sxs-lookup"><span data-stu-id="687ee-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="687ee-147">在“**概述**”行，选择“**DNS**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="687ee-148">在“**修改**”下拉列表中，选择“**MX 记录**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="687ee-150">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="687ee-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="687ee-151">**Priority**</span><span class="sxs-lookup"><span data-stu-id="687ee-151">**Priority**</span></span>|<span data-ttu-id="687ee-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="687ee-152">**Host**</span></span>|<span data-ttu-id="687ee-153">**指向：**</span><span class="sxs-lookup"><span data-stu-id="687ee-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="687ee-154">0</span><span class="sxs-lookup"><span data-stu-id="687ee-154">0</span></span>  <br/> <span data-ttu-id="687ee-155">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="687ee-155">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |@  <br/> | <span data-ttu-id="687ee-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="687ee-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="687ee-157">**注意：** 从 Microsoft 帐户获取 \<*domain-key*\>。</span><span class="sxs-lookup"><span data-stu-id="687ee-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="687ee-158"> > [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="687ee-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="687ee-160">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="687ee-162">如果存在任何其他现有 MX 记录，请在“**操作**”列中选择“**删除**”以删除每条 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="687ee-164">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="687ee-166">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="687ee-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="687ee-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="687ee-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="687ee-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="687ee-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="687ee-169">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="687ee-169">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="687ee-170">在“**我的收藏夹**”部分，选择则“**域中心**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="687ee-171">在“**域**”下，选择要编辑的域名。</span><span class="sxs-lookup"><span data-stu-id="687ee-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="687ee-172">在“**概述**”行，选择“**DNS**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="687ee-173">在“**修改**”下拉列表中，选择“**CNAME 别名**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="687ee-175">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="687ee-176">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="687ee-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="687ee-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="687ee-177">**Host**</span></span>|<span data-ttu-id="687ee-178">**指向：**</span><span class="sxs-lookup"><span data-stu-id="687ee-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="687ee-179">自动发现</span><span class="sxs-lookup"><span data-stu-id="687ee-179">autodiscover</span></span>  <br/> |<span data-ttu-id="687ee-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="687ee-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="687ee-181">sip</span><span class="sxs-lookup"><span data-stu-id="687ee-181">sip</span></span>  <br/> |<span data-ttu-id="687ee-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="687ee-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="687ee-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="687ee-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="687ee-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="687ee-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="687ee-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="687ee-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="687ee-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="687ee-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="687ee-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="687ee-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="687ee-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="687ee-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="687ee-190">选择“**添加**”以添加第一条记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="687ee-192">添加第二条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="687ee-193">使用上表中第二行的值，然后选择“**添加**”以添加第二条记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="687ee-194">按同样的方法，使用表中第 3 到 6 行的值添加其余记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="687ee-195">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="687ee-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="687ee-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="687ee-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="687ee-197">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="687ee-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="687ee-198">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="687ee-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="687ee-199">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="687ee-200">可以将所需的 Microsoft 值添加到当前记录，这样就拥有包含两组值的单个 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="687ee-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="687ee-201">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="687ee-201">Need examples?</span></span> <span data-ttu-id="687ee-202">请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="687ee-202">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="687ee-203">若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="687ee-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="687ee-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="687ee-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="687ee-205">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="687ee-205">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="687ee-206">在“**我的收藏夹**”部分，选择则“**域中心**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="687ee-207">在“**域**”下，选择要编辑的域名。</span><span class="sxs-lookup"><span data-stu-id="687ee-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="687ee-208">在“**概述**”行，选择“**DNS**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="687ee-209">在“**修改**”下拉列表中，选择“**TXT/SPF 记录**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="687ee-211">在" **内容**"下方新记录对应的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="687ee-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="687ee-212">**内容**</span><span class="sxs-lookup"><span data-stu-id="687ee-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="687ee-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="687ee-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="687ee-214">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="687ee-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="687ee-216">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="687ee-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="687ee-218">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="687ee-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="687ee-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="687ee-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="687ee-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="687ee-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="687ee-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="687ee-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="687ee-222">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="687ee-222">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="687ee-223">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="687ee-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="687ee-224">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="687ee-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
