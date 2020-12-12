---
title: 更改名称服务器以使用 Google Domains 设置 Microsoft
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: 了解如何设置 Microsoft 以在 Google Domains 上管理自定义域的 DNS 记录。
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658436"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="44033-103">更改名称服务器以使用 Google Domains 设置 Microsoft</span><span class="sxs-lookup"><span data-stu-id="44033-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="44033-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="44033-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="44033-105">如果希望 Microsoft 管理 DNS 记录，请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="44033-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="44033-106"> (，可以在 [Google Domains](create-dns-records-at-google-domains.md).) </span><span class="sxs-lookup"><span data-stu-id="44033-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="44033-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="44033-107">Add a TXT record for verification</span></span>

<span data-ttu-id="44033-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="44033-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="44033-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="44033-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="44033-112">To get started， go to your domains page at Google Domains via [this link.](https://domains.google.com/registrar)</span><span class="sxs-lookup"><span data-stu-id="44033-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="44033-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="44033-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="44033-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="44033-114">To do so:</span></span>
    
1. <span data-ttu-id="44033-115">选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="44033-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="44033-116">输入你的登录凭据，然后再次选择 **"登录"。**</span><span class="sxs-lookup"><span data-stu-id="44033-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="44033-117">在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。</span><span class="sxs-lookup"><span data-stu-id="44033-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="44033-118">在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="44033-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="44033-119">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="44033-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="44033-120">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="44033-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44033-121">**名称**</span><span class="sxs-lookup"><span data-stu-id="44033-121">**Name**</span></span> <br/> |<span data-ttu-id="44033-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="44033-122">**Type**</span></span> <br/> |<span data-ttu-id="44033-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="44033-123">**TTL**</span></span> <br/> |<span data-ttu-id="44033-124">**数据**</span><span class="sxs-lookup"><span data-stu-id="44033-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="44033-125">TXT</span><span class="sxs-lookup"><span data-stu-id="44033-125">TXT</span></span>  <br/> |<span data-ttu-id="44033-126">1H</span><span class="sxs-lookup"><span data-stu-id="44033-126">1H</span></span>  <br/> |<span data-ttu-id="44033-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="44033-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="44033-128">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="44033-128">**Note:** This is an example.</span></span> <span data-ttu-id="44033-129">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="44033-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="44033-130">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="44033-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="44033-131">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="44033-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="44033-132">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="44033-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="44033-133">现在，你已在你的域注册机构网站添加了记录，你将返回到 Microsoft 并请求搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="44033-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="44033-134">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="44033-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="44033-135">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="44033-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="44033-136">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="44033-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="44033-137">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="44033-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="44033-138">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="44033-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="44033-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="44033-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="44033-140">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="44033-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="44033-141">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="44033-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="44033-142">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="44033-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="44033-143">若要使用 Microsoft 完成域设置，请更改域注册机构中域的 NS 记录，以指向 Microsoft 主名称服务器和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="44033-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="44033-144">这会将 Microsoft 设置为更新域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="44033-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="44033-145">我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="44033-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="44033-146">当您将域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与域关联的所有服务都受到影响。</span><span class="sxs-lookup"><span data-stu-id="44033-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="44033-147">例如，发送到域的所有电子邮件 (如 *rob@your_domain。*</span><span class="sxs-lookup"><span data-stu-id="44033-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="44033-148">com) 将在你进行此更改后开始进入 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="44033-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="44033-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="44033-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="44033-150">>完成本节中的步骤后，应列出的唯一名称服务器是以下四个：</span><span class="sxs-lookup"><span data-stu-id="44033-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="44033-p110">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="44033-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="44033-154">选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="44033-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="44033-155">输入登录凭据，然后再次选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="44033-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="44033-156">在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。</span><span class="sxs-lookup"><span data-stu-id="44033-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="44033-157">在" **域**"页面的" **名称服务器**"部分中，选择" **使用自定义名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="44033-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="44033-159">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：</span><span class="sxs-lookup"><span data-stu-id="44033-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="44033-160">如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="44033-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="44033-161">如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="44033-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="44033-162">如果未列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="44033-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="44033-163">添加第一个名称服务器。</span><span class="sxs-lookup"><span data-stu-id="44033-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="44033-164">在" **名称服务器**"部分的" **名称服务器**"框内，键入或复制粘贴下表中的第一个值。</span><span class="sxs-lookup"><span data-stu-id="44033-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="44033-165">**第一个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-165">**First name server**</span></span> <br/> |<span data-ttu-id="44033-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="44033-167">**第二个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-167">**Second name server**</span></span> <br/> |<span data-ttu-id="44033-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="44033-169">**第三个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-169">**Third name server**</span></span> <br/> |<span data-ttu-id="44033-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="44033-171">**第四个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="44033-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="44033-174">选择 **+ (添加)** 控件以创建空行。</span><span class="sxs-lookup"><span data-stu-id="44033-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="44033-176">添加其他三个名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="44033-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="44033-177">在"使用 **自定义** 名称服务器"部分，使用表中下一行的值创建记录，然后选择 + (**添加) 添加** 另一行。</span><span class="sxs-lookup"><span data-stu-id="44033-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="44033-178">重复该过程，直到创建完全部 4 条名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="44033-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="44033-179">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="44033-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="44033-181">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="44033-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="44033-182">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="44033-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="44033-183">如果已列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="44033-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="44033-184">如果列出了任何其他名称服务器，请选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="44033-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="44033-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="44033-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="44033-186"> (，即仅删除任何未命名为 **ns1.bdm.microsoftonline.com、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com**.)  </span><span class="sxs-lookup"><span data-stu-id="44033-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="44033-188">选择每个服务器，然后按键盘上的 **Delete** 键，可将其删除。</span><span class="sxs-lookup"><span data-stu-id="44033-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="44033-190">仍在" **名称服务器**"部分的" **名称服务器**"行中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="44033-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="44033-191">**第一个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-191">**First name server**</span></span> <br/> |<span data-ttu-id="44033-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="44033-193">**第二个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-193">**Second name server**</span></span> <br/> |<span data-ttu-id="44033-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="44033-195">**第三个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-195">**Third name server**</span></span> <br/> |<span data-ttu-id="44033-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="44033-197">**第四个名称服务器**</span><span class="sxs-lookup"><span data-stu-id="44033-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="44033-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="44033-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="44033-200">选择 **+ (添加)** 控件以创建空行。</span><span class="sxs-lookup"><span data-stu-id="44033-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="44033-202">添加其他两个名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="44033-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="44033-203">在"使用 **自定义** 名称服务器"部分，使用表中下一行的值创建记录，然后选择 + (添加) **控件** 以添加另一行。</span><span class="sxs-lookup"><span data-stu-id="44033-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="44033-204">重复该过程，直到创建完全部 4 条名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="44033-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="44033-205">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="44033-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="44033-207">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="44033-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="44033-208">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="44033-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
