---
title: 更改名称服务器以使用 Bluehost 设置 Microsoft
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: '了解如何在 Bluehost 中将 Microsoft 设置为管理 DNS 记录。 '
ms.openlocfilehash: c15ba11e0df57deaef61309f5bc6d1b2a60645b8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646459"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="fe2c2-103">更改名称服务器以使用 Bluehost 设置 Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe2c2-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="fe2c2-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fe2c2-105">如果希望 Microsoft 为你管理 DNS 记录，请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="fe2c2-106"> (如果你愿意，可以 [在 Bluehost 管理所有 DNS 记录](create-dns-records-at-bluehost.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="fe2c2-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fe2c2-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="fe2c2-107">Add a TXT record for verification</span></span>

<span data-ttu-id="fe2c2-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe2c2-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="fe2c2-112">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="fe2c2-113">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fe2c2-114">在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="fe2c2-115">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="fe2c2-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="fe2c2-116">在 " **domain_name** " 区域的 " **DNS 区域编辑器** " 行中，选择 " **管理 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="fe2c2-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="fe2c2-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fe2c2-118">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="fe2c2-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe2c2-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-119">**Host Record**</span></span> <br/> |<span data-ttu-id="fe2c2-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-120">**TTL**</span></span> <br/> |<span data-ttu-id="fe2c2-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-121">**Type**</span></span> <br/> |<span data-ttu-id="fe2c2-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="fe2c2-123">14400</span><span class="sxs-lookup"><span data-stu-id="fe2c2-123">14400</span></span>  <br/> |<span data-ttu-id="fe2c2-124">TXT</span><span class="sxs-lookup"><span data-stu-id="fe2c2-124">TXT</span></span>  <br/> |<span data-ttu-id="fe2c2-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fe2c2-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="fe2c2-126">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-126">**Note:** This is an example.</span></span> <span data-ttu-id="fe2c2-127">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="fe2c2-128">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="fe2c2-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="fe2c2-129">选择 " **添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="fe2c2-130">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fe2c2-131">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="fe2c2-132">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fe2c2-133">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="fe2c2-134">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="fe2c2-135">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="fe2c2-136">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe2c2-137">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="fe2c2-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="fe2c2-138">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="fe2c2-139">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="fe2c2-140">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="fe2c2-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="fe2c2-141">若要使用 Microsoft 完成域的设置，请在域注册机构更改您的域的 NS 记录以指向主名称服务器和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="fe2c2-142">这将设置 Microsoft 为您更新域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="fe2c2-143">我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fe2c2-144">当您将您的域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与您的域相关联的所有服务都将受到影响。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="fe2c2-145">例如，在进行此更改后，发送到您的域的所有电子邮件 (如 rob@ *your_domain*  .com) 将启动到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="fe2c2-146">下面的过程将向您介绍如何从列表中删除任何其他不需要的名称服务器，以及如何添加正确的名称服务器（如果尚未列出）。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="fe2c2-147">> 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="fe2c2-148">要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="fe2c2-149">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fe2c2-150">在 " **域** " 页上的 " **domain_name** " 区域中，选中您的域的复选框，然后选择 " **名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="fe2c2-152">在 " **domain_name** " 区域中，选择 " **使用自定义名称服务器**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="fe2c2-154">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：</span><span class="sxs-lookup"><span data-stu-id="fe2c2-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="fe2c2-155">如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="fe2c2-156">如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="fe2c2-157">如果未列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="fe2c2-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="fe2c2-158">在" **使用自定义名称服务器**"部分中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="fe2c2-159">**第一个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-159">**First empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fe2c2-161">**第二个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-委派-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="fe2c2-164">选择 " **添加行**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="fe2c2-166">在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="fe2c2-167">**第三个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fe2c2-169">**第四个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
  
4. <span data-ttu-id="fe2c2-171">若要添加第四个 Nameserver 记录，请再次选择 " **添加行** "，并使用上表中最后一行的值创建记录。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="fe2c2-172">选择 " **保存 nameserver 设置**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="fe2c2-174">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="fe2c2-175">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="fe2c2-176">如果已列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="fe2c2-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="fe2c2-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="fe2c2-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="fe2c2-178"> (也就是说，仅删除任何  *未*  命名的 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的当前名称服务器。 ) </span><span class="sxs-lookup"><span data-stu-id="fe2c2-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="fe2c2-179">如果列有任何其他名称服务器，删除每个服务器，具体方法是将其选中，然后按键盘上的 **Delete** 键。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="fe2c2-181">在" **使用自定义名称服务器**"部分中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="fe2c2-182">**第一个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-182">**First empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fe2c2-184">**第二个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-委派-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="fe2c2-187">选择 " **添加行**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="fe2c2-189">在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="fe2c2-190">**第三个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="fe2c2-192">**第四个空行**</span><span class="sxs-lookup"><span data-stu-id="fe2c2-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="fe2c2-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe2c2-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-委派-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="fe2c2-195">若要添加第四个 Nameserver 记录，请再次选择 " **添加行** "，并使用上表中最后一行的值创建记录。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="fe2c2-196">选择 " **保存 nameserver 设置**"。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="fe2c2-198">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="fe2c2-199">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="fe2c2-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
