---
title: 更改名称服务器以使用 MyDomain 设置 Office 365
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: 了解如何设置 Office 365 以在 MyDomain 处管理自定义域的 DNS 记录。
ms.openlocfilehash: 05681fb48cc4c06aa44421029739a71ef6e59871
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238460"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="93999-103">更改名称服务器以使用 MyDomain 设置 Office 365</span><span class="sxs-lookup"><span data-stu-id="93999-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="93999-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="93999-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="93999-p101">如果希望 Office 365 管理 Office 365 DNS 记录，请按照以下说明操作。（如果愿意，可[在 MyDomain 处管理所有 Office 365 DNS 记录](create-dns-records-at-mydomain.md)。）</span><span class="sxs-lookup"><span data-stu-id="93999-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="93999-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="93999-107">Add a TXT record for verification</span></span>

<span data-ttu-id="93999-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="93999-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93999-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="93999-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="93999-p104">若要开始，请使用[此链接](https://www.mydomain.com/controlpanel)转到你在 MyDomain 上的域页面。系统将会提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="93999-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="93999-114">在 "**我的收藏夹**" 部分，选择 "**域中心**"。</span><span class="sxs-lookup"><span data-stu-id="93999-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="93999-115">在 "**域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="93999-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="93999-116">在 "**概述**" 行中，选择 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="93999-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="93999-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="93999-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="93999-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span><span class="sxs-lookup"><span data-stu-id="93999-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="93999-119">**内容**</span><span class="sxs-lookup"><span data-stu-id="93999-119">**Content**</span></span> <br/> |
|<span data-ttu-id="93999-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="93999-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="93999-121">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="93999-121">**Note**: This is an example.</span></span> <span data-ttu-id="93999-122">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="93999-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="93999-123">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="93999-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="93999-124">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="93999-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="93999-125">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="93999-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="93999-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="93999-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="93999-127">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="93999-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="93999-128">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="93999-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="93999-129">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="93999-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="93999-130">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="93999-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="93999-131">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="93999-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="93999-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="93999-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="93999-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="93999-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="93999-134">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="93999-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="93999-135">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="93999-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="93999-p107">要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="93999-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="93999-139">将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。</span><span class="sxs-lookup"><span data-stu-id="93999-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="93999-140">例如，发送到您的域的所有电子邮件（如 rob@ *your_domain。*</span><span class="sxs-lookup"><span data-stu-id="93999-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="93999-141">com）在你进行此更改后，将开始进入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="93999-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="93999-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="93999-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="93999-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="93999-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="93999-144">若要开始，请使用[此链接](https://www.mydomain.com/controlpanel)转到你在 MyDomain 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="93999-144">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="93999-145">系统将会提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="93999-145">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="93999-146">在 "**我的收藏夹**" 部分，选择 "**域中心**"。</span><span class="sxs-lookup"><span data-stu-id="93999-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="93999-147">在 "**域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="93999-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="93999-148">在 "**概述**" 行中，选择 "**名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="93999-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![MyDomain-BP-委派-1-1](../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="93999-150">在" **更新名称服务器**"部分中，选择" **使用不同的名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="93999-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![MyDomain-BP-委派-1-2-1](../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="93999-152">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一。</span><span class="sxs-lookup"><span data-stu-id="93999-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="93999-153">如果已列出正确的名称服务器</span><span class="sxs-lookup"><span data-stu-id="93999-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="93999-154">如果已列出正确的名称服务器，可跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="93999-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![MyDomain-BP-委派-1-2-2](../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="93999-156">如果未列出正确的名称服务器</span><span class="sxs-lookup"><span data-stu-id="93999-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="93999-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="93999-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="93999-158">（也就是说，仅删除任何*未*命名为**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的当前名称服务器。）</span><span class="sxs-lookup"><span data-stu-id="93999-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="93999-159">在" **名称服务器:**"字段中选择每个条目，然后按键盘上的 **Delete** 键，删除现有名称服务器。</span><span class="sxs-lookup"><span data-stu-id="93999-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![MyDomain-BP-委派-1-3-1](../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="93999-161">选择 "**增加**" 两次，添加两个新的名称服务器行。</span><span class="sxs-lookup"><span data-stu-id="93999-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![MyDomain-BP-委派-1-3-2](../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="93999-163">在记录的框中，键入或复制并粘贴下表中的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="93999-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="93999-164">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="93999-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="93999-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="93999-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="93999-166">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="93999-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="93999-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="93999-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="93999-168">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="93999-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="93999-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="93999-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="93999-170">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="93999-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="93999-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="93999-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![MyDomain-BP-委派-1-4](../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="93999-173">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="93999-173">Select **Save**.</span></span>
    
    ![MyDomain-BP-委派-1-5](../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="93999-p112">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="93999-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
