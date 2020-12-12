---
title: 更改名称服务器以使用 Hostgator 设置 Microsoft
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: 了解如何设置 Microsoft 以在 Hostgator 上管理自定义域的 DNS 记录。
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658016"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="593f4-103">更改名称服务器以使用 Hostgator 设置 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="593f4-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="593f4-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="593f4-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="593f4-105">如果希望 Microsoft 管理 DNS 记录，请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="593f4-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="593f4-106"> (，可以在[Hostgator .) ](create-dns-records-at-hostgator.md)</span><span class="sxs-lookup"><span data-stu-id="593f4-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="593f4-107">将域指向托管帐户。</span><span class="sxs-lookup"><span data-stu-id="593f4-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="593f4-108">必须先执行此过程，才能执行以下 **添加 TXT 记录进行验证** 部分中的过程。</span><span class="sxs-lookup"><span data-stu-id="593f4-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="593f4-109">请按以下步骤将域与托管帐户关联。</span><span class="sxs-lookup"><span data-stu-id="593f4-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="593f4-p102">若要开始，请使用[此链接](https://portal.hostgator.com/domain/manage)转到 Hostgator 上的客户门户页面。系统将提示登录。</span><span class="sxs-lookup"><span data-stu-id="593f4-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="593f4-113">选择 **"域"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="593f4-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="593f4-115">在 **"管理域** "页上的 **"我的域** "区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="593f4-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="593f4-117">在"**域概述"** 页上的 **"名称** 服务器"区域中，选择"**更改"。**</span><span class="sxs-lookup"><span data-stu-id="593f4-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="593f4-119">在 **域** 的"名称服务器"页上的"选择托管帐户"下拉列表中，选择与域关联的托管帐户。</span><span class="sxs-lookup"><span data-stu-id="593f4-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="593f4-121">选择 **"保存名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="593f4-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="593f4-123">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="593f4-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="593f4-124">执行此过程之前，必须先执行本文第一节中的过程，将域 [指向您的托管帐户](#point-your-domain-to-your-hosting-account)。</span><span class="sxs-lookup"><span data-stu-id="593f4-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="593f4-p103">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="593f4-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="593f4-p104">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="593f4-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="593f4-p105">若要开始，请转到您在 Hostgator 上的 cPanel 页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="593f4-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="593f4-p106">（Hostgator 上的每个托管帐户都分配有一个唯一的 cPanel 地址。 您的 cPanel 地址应如下所示：https://YourSiteAddress:secure-port-number。 由您从 Hostgator 收到的注册电子邮件地址指定该地址。）</span><span class="sxs-lookup"><span data-stu-id="593f4-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="593f4-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="593f4-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="593f4-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="593f4-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="593f4-136">在 **"控制面板"** 页上的"域 **"区域中**，选择 **"高级 DNS 区域编辑器"。**</span><span class="sxs-lookup"><span data-stu-id="593f4-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="593f4-137">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="593f4-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="593f4-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="593f4-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="593f4-139">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="593f4-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="593f4-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="593f4-140">**Name**</span></span> <br/> |<span data-ttu-id="593f4-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="593f4-141">**TTL**</span></span> <br/> |<span data-ttu-id="593f4-142">**类型**</span><span class="sxs-lookup"><span data-stu-id="593f4-142">**Type**</span></span> <br/> |<span data-ttu-id="593f4-143">**TXT 数据**</span><span class="sxs-lookup"><span data-stu-id="593f4-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="593f4-144">使用你的  *domain_name*  。</span><span class="sxs-lookup"><span data-stu-id="593f4-144">Use your  *domain_name*  .</span></span> <span data-ttu-id="593f4-145">（例如，fourthcoffee.com.)。</span><span class="sxs-lookup"><span data-stu-id="593f4-145">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="593f4-146">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="593f4-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="593f4-147">1 </span><span class="sxs-lookup"><span data-stu-id="593f4-147">1</span></span>  <br/> |<span data-ttu-id="593f4-148">TXT</span><span class="sxs-lookup"><span data-stu-id="593f4-148">TXT</span></span>  <br/> |<span data-ttu-id="593f4-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="593f4-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="593f4-150">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="593f4-150">**Note:** This is an example.</span></span> <span data-ttu-id="593f4-151">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="593f4-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="593f4-152">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="593f4-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="593f4-153">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="593f4-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="593f4-154">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="593f4-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="593f4-155">现在，你已在你的域注册机构网站添加了记录，你将返回到 Microsoft 并请求搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="593f4-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="593f4-156">当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="593f4-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="593f4-157">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="593f4-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="593f4-158">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="593f4-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="593f4-159">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="593f4-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="593f4-160">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="593f4-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="593f4-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="593f4-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="593f4-162">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="593f4-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="593f4-163">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="593f4-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="593f4-164">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="593f4-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="593f4-165">若要使用 Microsoft 完成域设置，请更改域注册机构中域的 NS 记录，以指向 Microsoft 主名称服务器和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="593f4-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="593f4-166">这会将 Microsoft 设置为更新域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="593f4-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="593f4-167">我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="593f4-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="593f4-168">当您将域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与域关联的所有服务都受到影响。</span><span class="sxs-lookup"><span data-stu-id="593f4-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="593f4-169">例如，发送到域邮箱的所有电子邮件 (如 rob@ *your_domain*  .com) 将在你进行此更改后开始发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="593f4-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="593f4-170">以下过程将向您展示如何从列表中删除任何其他不需要的名称服务器，以及如何在名称服务器尚未列出时添加正确的名称服务器。</span><span class="sxs-lookup"><span data-stu-id="593f4-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="593f4-171">完成本节中的步骤后，应列出的唯一名称服务器是以下四个：ns1.bdm.microsoftonline.com、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com 和 **ns4.bdm.microsoftonline.com。**  </span><span class="sxs-lookup"><span data-stu-id="593f4-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="593f4-p114">若要开始，请使用[此链接](https://portal.hostgator.com/domain/manage)转到 Hostgator 上的客户门户页面。系统将提示登录。</span><span class="sxs-lookup"><span data-stu-id="593f4-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="593f4-175">选择 **"域"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="593f4-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="593f4-177">在 **"管理域** "页上的 **"我的域** "区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="593f4-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="593f4-179">在"**域概述"** 页上的 **"名称** 服务器"区域中，选择"**更改"。**</span><span class="sxs-lookup"><span data-stu-id="593f4-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="593f4-181">在 **域** 的"名称服务器"页上的"选择托管帐户"下拉列表中，选择与域关联的托管帐户。</span><span class="sxs-lookup"><span data-stu-id="593f4-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="593f4-183">选择 **"手动设置我的名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="593f4-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="593f4-185">**警告**：仅当您具有除四个正确的名称服务器外的现有名称服务器时，才执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="593f4-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="593f4-186"> (，即仅删除任何未命名为 **ns1.bdm.microsoftonline.com、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com**.)  </span><span class="sxs-lookup"><span data-stu-id="593f4-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="593f4-187">在域的" **名称服务器**"页面的名称服务器列表中，删除列表中的每个名称服务器，具体方法是将其选中，然后按键盘上的 **Delete** 键。</span><span class="sxs-lookup"><span data-stu-id="593f4-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="593f4-189">在名称服务器列表中，键入或复制并粘贴下表中的前两个值。</span><span class="sxs-lookup"><span data-stu-id="593f4-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="593f4-190">**名称服务器 1：**</span><span class="sxs-lookup"><span data-stu-id="593f4-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="593f4-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="593f4-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="593f4-192">**名称服务器 2：**</span><span class="sxs-lookup"><span data-stu-id="593f4-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="593f4-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="593f4-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="593f4-194">**名称服务器 3：**</span><span class="sxs-lookup"><span data-stu-id="593f4-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="593f4-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="593f4-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="593f4-196">**名称服务器 4：**</span><span class="sxs-lookup"><span data-stu-id="593f4-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="593f4-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="593f4-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="593f4-199">添加其他名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="593f4-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="593f4-200">选择 **(+) ，** 然后键入或复制表中下一行的值并将其粘贴到记录的框中。</span><span class="sxs-lookup"><span data-stu-id="593f4-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="593f4-201">重复该过程，直到创建完全部 4 条名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="593f4-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="593f4-203">选择 **"保存名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="593f4-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="593f4-205">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="593f4-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="593f4-206">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="593f4-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
