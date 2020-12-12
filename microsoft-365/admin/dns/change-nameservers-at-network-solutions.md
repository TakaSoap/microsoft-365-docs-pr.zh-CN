---
title: 更改名称服务器以使用网络解决方案设置 Microsoft
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: '如果希望 Microsoft 管理 DNS 记录，了解如何使用网络解决方案设置 Microsoft 自定义域。 '
ms.openlocfilehash: 04817ca24b13b4c138986df3875b6d397100fffd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658424"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="9e01a-103">更改名称服务器以使用网络解决方案设置 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e01a-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="9e01a-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="9e01a-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="9e01a-105">如果希望 Microsoft 管理 DNS 记录，请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="9e01a-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="9e01a-106"> (，可以在 Network [Solutions .) ](create-dns-records-at-network-solutions.md)</span><span class="sxs-lookup"><span data-stu-id="9e01a-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="9e01a-107">在 Network Solutions 处添加 TXT 记录以验证是否拥有该域</span><span class="sxs-lookup"><span data-stu-id="9e01a-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="9e01a-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="9e01a-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e01a-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="9e01a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="9e01a-112">请按下列步骤操作或[观看视频（从 0:47 开始）](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261)。</span><span class="sxs-lookup"><span data-stu-id="9e01a-112">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
1. <span data-ttu-id="9e01a-p104">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="9e01a-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9e01a-115">在选择"**登录"** 按钮之前，首先在"登录："下拉列表中选择"管理我的域名"。</span><span class="sxs-lookup"><span data-stu-id="9e01a-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="9e01a-117">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="9e01a-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="9e01a-119">选择 **"编辑 DNS"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-119">Select **Edit DNS**.</span></span>
    
    ![选择"编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="9e01a-121">选择 **"管理高级 DNS 记录"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="9e01a-122">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="9e01a-122">(You may have to scroll down.)</span></span>
    
    ![选择"管理高级 DNS 记录"](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="9e01a-124">向下滚动到 **"TXT 记录 (** 文本) 部分，然后选择"编辑 **TXT 记录"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![选择"编辑 TXT 记录"](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="9e01a-126">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="9e01a-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="9e01a-127">**主机**</span><span class="sxs-lookup"><span data-stu-id="9e01a-127">**Host**</span></span>|<span data-ttu-id="9e01a-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e01a-128">**TTL**</span></span>|<span data-ttu-id="9e01a-129">**文本**</span><span class="sxs-lookup"><span data-stu-id="9e01a-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="9e01a-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="9e01a-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="9e01a-131">3600</span><span class="sxs-lookup"><span data-stu-id="9e01a-131">3600</span></span>  <br/> |<span data-ttu-id="9e01a-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9e01a-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9e01a-133">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="9e01a-133">**Note**: This is an example.</span></span> <span data-ttu-id="9e01a-134">在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="9e01a-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="9e01a-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="9e01a-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![在新记录的框中键入或粘贴值](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="9e01a-137">选择 **"继续"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-137">Select **Continue**.</span></span>
    
    ![选择"继续"](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="9e01a-139">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-139">Select **Save Changes**.</span></span>
    
    ![选择"保存更改"](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="9e01a-141">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="9e01a-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e01a-142">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="9e01a-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="9e01a-143">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="9e01a-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e01a-144">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9e01a-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9e01a-145">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="9e01a-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9e01a-146">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="9e01a-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9e01a-147">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="9e01a-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9e01a-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="9e01a-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9e01a-151">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="9e01a-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="9e01a-152">若要使用 Microsoft 完成域设置，请更改域注册机构中域的 NS 记录，以指向 Microsoft 主名称服务器和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="9e01a-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="9e01a-153">这会将 Microsoft 设置为更新域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9e01a-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="9e01a-154">我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="9e01a-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9e01a-155">当您将域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与域关联的所有服务都受到影响。</span><span class="sxs-lookup"><span data-stu-id="9e01a-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="9e01a-156">例如，发送到域邮箱的所有电子邮件 (如 rob@ *your_domain*  .com) 将在你进行此更改后开始发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9e01a-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="9e01a-157">准备好更改 NS 记录以便 Microsoft 可以设置域了吗？</span><span class="sxs-lookup"><span data-stu-id="9e01a-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="9e01a-158">请按下列步骤操作或[观看视频（从 2:23 开始）](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261)。</span><span class="sxs-lookup"><span data-stu-id="9e01a-158">Follow the steps below or [watch the video (start at 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="9e01a-159">完成本节中的步骤后，应列出的唯一名称服务器是以下四个：ns1.bdm.microsoftonline.com、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com 和 **ns4.bdm.microsoftonline.com。**  </span><span class="sxs-lookup"><span data-stu-id="9e01a-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="9e01a-160">以下过程将演示如何从列表中删除任何其他不需要的名称服务器，以及如何添加 *正确*  的名称服务器（如果它们尚未显示在列表中）。</span><span class="sxs-lookup"><span data-stu-id="9e01a-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="9e01a-161">若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。</span><span class="sxs-lookup"><span data-stu-id="9e01a-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="9e01a-162">系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="9e01a-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9e01a-163">在选择"**登录"** 按钮之前，首先在"登录："下拉列表中选择"管理我的域名"。</span><span class="sxs-lookup"><span data-stu-id="9e01a-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="9e01a-165">选择要修改的域名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="9e01a-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![选择域的复选框](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="9e01a-167">选择 **"编辑 DNS"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-167">Select **Edit DNS**.</span></span>
    
    ![选择"编辑 DNS"](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="9e01a-169">选择 **"移动 DNS"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="9e01a-171">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：</span><span class="sxs-lookup"><span data-stu-id="9e01a-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="9e01a-172">如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="9e01a-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="9e01a-173">如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="9e01a-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="9e01a-174">如果未列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="9e01a-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="9e01a-175">在"**域**"页上的"指定域名服务器 **"部分，** 选择"**添加更多名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="9e01a-177">在" **域名**"页面中，键入或复制并粘贴下表中的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="9e01a-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9e01a-178">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="9e01a-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="9e01a-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e01a-180">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="9e01a-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="9e01a-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e01a-182">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="9e01a-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="9e01a-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e01a-184">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="9e01a-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="9e01a-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="9e01a-187">选择 **"移动 DNS"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="9e01a-189">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="9e01a-191">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="9e01a-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e01a-192">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="9e01a-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="9e01a-193">如果已列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="9e01a-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="9e01a-p113">*仅*  当具有这四个  *正确*  的名称服务器以外的现有名称服务器时，执行以下步骤。（即，  *仅*  删除名称  *不是* **ns1.bdm.microsoftonline.com** 、 **ns2.bdm.microsoftonline.com** 、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的任何当前名称服务器。）</span><span class="sxs-lookup"><span data-stu-id="9e01a-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="9e01a-196">如果列有任何其他名称服务器，选择服务器，然后按键盘上的 **Delete** 键，将其删除。</span><span class="sxs-lookup"><span data-stu-id="9e01a-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="9e01a-198">选择 **"添加更多名称服务器"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="9e01a-200">在" **域名**"页面中，键入或复制并粘贴下表中的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="9e01a-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="9e01a-201">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="9e01a-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="9e01a-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e01a-203">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="9e01a-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="9e01a-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e01a-205">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="9e01a-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="9e01a-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="9e01a-207">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="9e01a-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="9e01a-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="9e01a-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="9e01a-210">选择 **"移动 DNS"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="9e01a-212">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="9e01a-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="9e01a-214">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="9e01a-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e01a-215">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="9e01a-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
