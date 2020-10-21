---
title: 更改名称服务器以使用 MyDomain 设置 Microsoft
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: 了解如何将 Microsoft 设置为在 MyDomain 处管理自定义域的 DNS 记录。
ms.openlocfilehash: 44d36f872ddbeeba1948ee8a7a4db029895fcb8c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646411"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="dcc67-103">更改名称服务器以使用 MyDomain 设置 Microsoft</span><span class="sxs-lookup"><span data-stu-id="dcc67-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="dcc67-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dcc67-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="dcc67-105">如果希望 Microsoft 为你管理 DNS 记录，请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="dcc67-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="dcc67-106"> (如果你愿意，可以 [在 MyDomain 处管理所有 MICROSOFT DNS 记录](create-dns-records-at-mydomain.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="dcc67-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dcc67-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="dcc67-107">Add a TXT record for verification</span></span>

<span data-ttu-id="dcc67-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="dcc67-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dcc67-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="dcc67-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="dcc67-p104">若要开始，请使用[此链接](https://www.mydomain.com/controlpanel)转到你在 MyDomain 上的域页面。系统将会提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="dcc67-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dcc67-114">在“**我的收藏夹**”部分，选择则“**域中心**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="dcc67-115">在“**域**”下，选择要编辑的域名。</span><span class="sxs-lookup"><span data-stu-id="dcc67-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="dcc67-116">在“**概述**”行，选择“**DNS**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="dcc67-117">在“**修改**”下拉列表中，选择“**TXT/SPF 记录**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="dcc67-118">在" **内容**"下方新记录对应的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dcc67-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="dcc67-119">**内容**</span><span class="sxs-lookup"><span data-stu-id="dcc67-119">**Content**</span></span> <br/> |
|<span data-ttu-id="dcc67-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dcc67-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dcc67-121">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="dcc67-121">**Note**: This is an example.</span></span> <span data-ttu-id="dcc67-122">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="dcc67-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="dcc67-123">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="dcc67-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="dcc67-124">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="dcc67-125">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="dcc67-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dcc67-126">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="dcc67-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="dcc67-127">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="dcc67-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dcc67-128">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="dcc67-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="dcc67-129">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="dcc67-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="dcc67-130">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="dcc67-131">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dcc67-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="dcc67-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="dcc67-133">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="dcc67-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="dcc67-134">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dcc67-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="dcc67-135">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="dcc67-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="dcc67-136">若要使用 Microsoft 完成域的设置，请在域注册机构更改您的域的 NS 记录以指向 Microsoft 主名称服务器和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="dcc67-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="dcc67-137">这将设置 Microsoft 为您更新域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="dcc67-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="dcc67-138">我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="dcc67-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="dcc67-139">当您将您的域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与您的域相关联的所有服务都将受到影响。</span><span class="sxs-lookup"><span data-stu-id="dcc67-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="dcc67-140">例如，发送到您的域的所有电子邮件 (如 rob@ *your_domain。*</span><span class="sxs-lookup"><span data-stu-id="dcc67-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="dcc67-141">在进行此更改后，com) 将会启动到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="dcc67-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dcc67-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="dcc67-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="dcc67-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="dcc67-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="dcc67-p110">若要开始，请使用[此链接](https://www.mydomain.com/controlpanel)转到你在 MyDomain 上的域页面。系统将会提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="dcc67-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dcc67-146">在“**我的收藏夹**”部分，选择则“**域中心**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="dcc67-147">在“**域**”下，选择要编辑的域名。</span><span class="sxs-lookup"><span data-stu-id="dcc67-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="dcc67-148">在 " **概述** " 行中，选择 " **名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="dcc67-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-委派-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="dcc67-150">在" **更新名称服务器**"部分中，选择" **使用不同的名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="dcc67-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-委派-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="dcc67-152">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一。</span><span class="sxs-lookup"><span data-stu-id="dcc67-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="dcc67-153">如果已列出正确的名称服务器</span><span class="sxs-lookup"><span data-stu-id="dcc67-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="dcc67-154">如果已列出正确的名称服务器，可跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="dcc67-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-委派-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="dcc67-156">如果未列出正确的名称服务器</span><span class="sxs-lookup"><span data-stu-id="dcc67-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="dcc67-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="dcc67-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="dcc67-158"> (也就是说，仅删除任何  *未*  命名的 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的当前名称服务器。 ) </span><span class="sxs-lookup"><span data-stu-id="dcc67-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="dcc67-159">在" **名称服务器:**"字段中选择每个条目，然后按键盘上的 **Delete** 键，删除现有名称服务器。</span><span class="sxs-lookup"><span data-stu-id="dcc67-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-委派-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="dcc67-161">选择 " **增加** " 两次，添加两个新的名称服务器行。</span><span class="sxs-lookup"><span data-stu-id="dcc67-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-委派-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="dcc67-163">在记录的框中，键入或复制并粘贴下表中的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="dcc67-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="dcc67-164">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="dcc67-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="dcc67-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dcc67-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dcc67-166">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="dcc67-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="dcc67-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dcc67-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dcc67-168">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="dcc67-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="dcc67-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dcc67-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="dcc67-170">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="dcc67-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="dcc67-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="dcc67-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-委派-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="dcc67-173">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="dcc67-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-委派-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="dcc67-175">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="dcc67-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="dcc67-176">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="dcc67-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
