---
title: 更改名称服务器以使用 Google Domains 设置 Office 365
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: 了解如何设置 Office 365 以管理 Google 域的自定义域的 DNS 记录。
ms.openlocfilehash: 771d38b9a3d08bef75c3ad1958f981539edb6c04
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238480"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a><span data-ttu-id="812e5-103">更改名称服务器以使用 Google Domains 设置 Office 365</span><span class="sxs-lookup"><span data-stu-id="812e5-103">Change nameservers to set up Office 365 with Google Domains</span></span>

 <span data-ttu-id="812e5-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="812e5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="812e5-p101">如果希望 Office 365 管理 Office 365 DNS 记录，请按照以下说明操作。（如果愿意，可[在 Google Domains 处管理所有 Office 365 DNS 记录](create-dns-records-at-google-domains.md)。）</span><span class="sxs-lookup"><span data-stu-id="812e5-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="812e5-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="812e5-107">Add a TXT record for verification</span></span>

<span data-ttu-id="812e5-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="812e5-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="812e5-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="812e5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="812e5-112">若要开始，请通过[此链接](https://domains.google.com/registrar)转到 Google 域中的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="812e5-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="812e5-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="812e5-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="812e5-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="812e5-114">To do so:</span></span>
    
1. <span data-ttu-id="812e5-115">选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="812e5-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="812e5-116">输入登录凭据，然后再次选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="812e5-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="812e5-117">在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。</span><span class="sxs-lookup"><span data-stu-id="812e5-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="812e5-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="812e5-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="812e5-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="812e5-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="812e5-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="812e5-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="812e5-121">**名称**</span><span class="sxs-lookup"><span data-stu-id="812e5-121">**Name**</span></span> <br/> |<span data-ttu-id="812e5-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="812e5-122">**Type**</span></span> <br/> |<span data-ttu-id="812e5-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="812e5-123">**TTL**</span></span> <br/> |<span data-ttu-id="812e5-124">**数据**</span><span class="sxs-lookup"><span data-stu-id="812e5-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="812e5-125">TXT</span><span class="sxs-lookup"><span data-stu-id="812e5-125">TXT</span></span>  <br/> |<span data-ttu-id="812e5-126">1H</span><span class="sxs-lookup"><span data-stu-id="812e5-126">1H</span></span>  <br/> |<span data-ttu-id="812e5-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="812e5-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="812e5-128">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="812e5-128">**Note:** This is an example.</span></span> <span data-ttu-id="812e5-129">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="812e5-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="812e5-130">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="812e5-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="812e5-131">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="812e5-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="812e5-132">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="812e5-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="812e5-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="812e5-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="812e5-134">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="812e5-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="812e5-135">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="812e5-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="812e5-136">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="812e5-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="812e5-137">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="812e5-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="812e5-138">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="812e5-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="812e5-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="812e5-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="812e5-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="812e5-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="812e5-141">如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="812e5-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="812e5-142">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="812e5-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="812e5-p107">要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="812e5-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="812e5-146">将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。</span><span class="sxs-lookup"><span data-stu-id="812e5-146">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="812e5-147">例如，发送到您的域的所有电子邮件（如 rob@ *your_domain。*</span><span class="sxs-lookup"><span data-stu-id="812e5-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="812e5-148">com）在你进行此更改后，将开始进入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="812e5-148">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="812e5-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="812e5-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="812e5-150">> 完成本节中的步骤后，应列出的唯一名称服务器为以下四个：</span><span class="sxs-lookup"><span data-stu-id="812e5-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="812e5-p110">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="812e5-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="812e5-154">选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="812e5-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="812e5-155">输入登录凭据，然后再次选择 **"登录**"。</span><span class="sxs-lookup"><span data-stu-id="812e5-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="812e5-156">在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。</span><span class="sxs-lookup"><span data-stu-id="812e5-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="812e5-157">在" **域**"页面的" **名称服务器**"部分中，选择" **使用自定义名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="812e5-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="812e5-159">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：</span><span class="sxs-lookup"><span data-stu-id="812e5-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="812e5-160">如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="812e5-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="812e5-161">如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="812e5-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="812e5-162">如果未列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="812e5-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="812e5-163">添加第一个名称服务器。</span><span class="sxs-lookup"><span data-stu-id="812e5-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="812e5-164">在" **名称服务器**"部分的" **名称服务器**"框内，键入或复制粘贴下表中的第一个值。</span><span class="sxs-lookup"><span data-stu-id="812e5-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="812e5-165">**第一个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-165">**First name server**</span></span> <br/> |<span data-ttu-id="812e5-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="812e5-167">**第二个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-167">**Second name server**</span></span> <br/> |<span data-ttu-id="812e5-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="812e5-169">**第三个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-169">**Third name server**</span></span> <br/> |<span data-ttu-id="812e5-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="812e5-171">**第四个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="812e5-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-域-BP-委派-1-2](../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="812e5-174">选择 " **+" （添加）** 控件以创建一个空行。</span><span class="sxs-lookup"><span data-stu-id="812e5-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="812e5-176">添加其他三个名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="812e5-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="812e5-177">在 "**使用自定义名称服务器**" 部分，使用表中下一行的值创建记录，然后选择 " **+" （添加）** 控件以添加另一行。</span><span class="sxs-lookup"><span data-stu-id="812e5-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="812e5-178">重复该过程，直到创建完全部 4 条名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="812e5-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="812e5-179">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="812e5-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="812e5-p111">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="812e5-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="812e5-183">如果已列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="812e5-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="812e5-184">如果列出了任何其他名称服务器，请选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="812e5-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="812e5-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="812e5-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="812e5-186">（也就是说，仅删除任何*未*命名为**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的当前名称服务器。）</span><span class="sxs-lookup"><span data-stu-id="812e5-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="812e5-188">选择每个服务器，然后按键盘上的 **Delete** 键，可将其删除。</span><span class="sxs-lookup"><span data-stu-id="812e5-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="812e5-190">仍在" **名称服务器**"部分的" **名称服务器**"行中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="812e5-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="812e5-191">**第一个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-191">**First name server**</span></span> <br/> |<span data-ttu-id="812e5-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="812e5-193">**第二个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-193">**Second name server**</span></span> <br/> |<span data-ttu-id="812e5-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="812e5-195">**第三个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-195">**Third name server**</span></span> <br/> |<span data-ttu-id="812e5-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="812e5-197">**第四个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="812e5-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="812e5-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="812e5-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-域-BP-委派-1-7](../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="812e5-200">选择 " **+" （添加）** 控件以创建一个空行。</span><span class="sxs-lookup"><span data-stu-id="812e5-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="812e5-202">添加其他两个名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="812e5-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="812e5-203">在 "**使用自定义名称服务器**" 部分，使用表中下一行的值创建记录，然后选择 " **+" （添加）** 控件以添加另一行。</span><span class="sxs-lookup"><span data-stu-id="812e5-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="812e5-204">重复该过程，直到创建完全部 4 条名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="812e5-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="812e5-205">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="812e5-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="812e5-p113">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="812e5-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
