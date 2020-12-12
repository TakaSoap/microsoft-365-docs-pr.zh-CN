---
title: 更改名称服务器以使用 Namecheap 设置 Microsoft
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: '如果希望 Microsoft 管理 DNS 记录，了解如何使用 Namecheap 设置 Microsoft 自定义域。 '
ms.openlocfilehash: 0dec28c99bd49d3ba558e11afac8142c7df96591
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657980"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="53fe6-103">更改名称服务器以使用 Namecheap 设置 Microsoft</span><span class="sxs-lookup"><span data-stu-id="53fe6-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="53fe6-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="53fe6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="53fe6-105">如果希望 Microsoft 管理 DNS 记录，请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="53fe6-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="53fe6-106"> (，可以在 [Namecheap](create-dns-records-at-namecheap.md).) </span><span class="sxs-lookup"><span data-stu-id="53fe6-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="53fe6-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="53fe6-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="53fe6-108">To get started， go to your domains page at Namecheap by using [this link.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)</span><span class="sxs-lookup"><span data-stu-id="53fe6-108">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="53fe6-109">系统将提示你登录并继续。</span><span class="sxs-lookup"><span data-stu-id="53fe6-109">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="53fe6-111">在" **登录** "页上 **的"帐户**"下 **，** 从下拉列表中选择"域列表"。</span><span class="sxs-lookup"><span data-stu-id="53fe6-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="53fe6-113">在 **"域列表**"页上，找到要编辑的域的名称，然后选择"管理 **"。**</span><span class="sxs-lookup"><span data-stu-id="53fe6-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="53fe6-115">选择 **"高级 DNS"。**</span><span class="sxs-lookup"><span data-stu-id="53fe6-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="53fe6-117">在 **"主机记录**"部分，选择 **"添加新记录"。**</span><span class="sxs-lookup"><span data-stu-id="53fe6-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="53fe6-119">在"**类型**"下拉列表中，选择 **"TXT 记录"。**</span><span class="sxs-lookup"><span data-stu-id="53fe6-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="53fe6-120">选择 **"** 添加新记录"时，将自动显示"类型 **"下拉列表**。</span><span class="sxs-lookup"><span data-stu-id="53fe6-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="53fe6-122">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="53fe6-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="53fe6-123"> (从下拉列表中选择 **TTL** 值。) </span><span class="sxs-lookup"><span data-stu-id="53fe6-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="53fe6-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="53fe6-124">**Type**</span></span>|<span data-ttu-id="53fe6-125">**主机**</span><span class="sxs-lookup"><span data-stu-id="53fe6-125">**Host**</span></span>|<span data-ttu-id="53fe6-126">**值**</span><span class="sxs-lookup"><span data-stu-id="53fe6-126">**Value**</span></span>|<span data-ttu-id="53fe6-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="53fe6-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="53fe6-128">TXT</span><span class="sxs-lookup"><span data-stu-id="53fe6-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="53fe6-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="53fe6-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="53fe6-130">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="53fe6-130">**Note**: This is an example.</span></span> <span data-ttu-id="53fe6-131">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="53fe6-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="53fe6-132">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="53fe6-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="53fe6-133">30 分钟</span><span class="sxs-lookup"><span data-stu-id="53fe6-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="53fe6-135">Select the **Save Changes** (check mark) control.</span><span class="sxs-lookup"><span data-stu-id="53fe6-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="53fe6-137">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="53fe6-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="53fe6-138">现在，你已在你的域注册机构网站添加了记录，你将返回到 Microsoft 并请求搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="53fe6-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="53fe6-139">当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="53fe6-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="53fe6-140">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="53fe6-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="53fe6-141">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="53fe6-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="53fe6-142">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="53fe6-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="53fe6-143">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="53fe6-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="53fe6-p104">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="53fe6-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="53fe6-147">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="53fe6-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="53fe6-148">若要使用 Microsoft 完成域设置，请更改域注册机构中域的 NS 记录，以指向 Microsoft 主名称服务器和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="53fe6-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="53fe6-149">这会将 Microsoft 设置为更新域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="53fe6-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="53fe6-150">我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="53fe6-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="53fe6-151">当您将域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与域关联的所有服务都受到影响。</span><span class="sxs-lookup"><span data-stu-id="53fe6-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="53fe6-152">例如，发送到域邮箱的所有电子邮件 (如 rob@ *your_domain*  .com) 将在你进行此更改后开始发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="53fe6-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="53fe6-153">完成本部分中的步骤后，应  *仅*  列出以下四个名称服务器： >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  以下过程将演示如何从列表中删除任何其他不需要的名称服务器，以及如何添加  *正确*  的名称服务器（如果它们尚未显示在列表中）。</span><span class="sxs-lookup"><span data-stu-id="53fe6-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="53fe6-154">To get started， go to your domains page at Namecheap by using [this link.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)</span><span class="sxs-lookup"><span data-stu-id="53fe6-154">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="53fe6-155">系统将提示你登录并继续。</span><span class="sxs-lookup"><span data-stu-id="53fe6-155">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="53fe6-157">在" **登录** "页上 **的"帐户**"下 **，** 从下拉列表中选择"域列表"。</span><span class="sxs-lookup"><span data-stu-id="53fe6-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="53fe6-159">在 **"域列表**"页上，找到要编辑的域的名称，然后选择"管理 **"。**</span><span class="sxs-lookup"><span data-stu-id="53fe6-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="53fe6-161">选择 **"域"。**</span><span class="sxs-lookup"><span data-stu-id="53fe6-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="53fe6-163">找到 **"NAMESERVERS"** 部分 **，然后从\*\*\*\*"Namecheap** 默认"下拉列表中选择"自定义"。</span><span class="sxs-lookup"><span data-stu-id="53fe6-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="53fe6-165">根据页面上是否已列出现在显示的名称服务器，继续执行以下两个过程之一。</span><span class="sxs-lookup"><span data-stu-id="53fe6-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="53fe6-166">如果未列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="53fe6-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="53fe6-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="53fe6-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="53fe6-168">选择 **"添加 NAMESERVER"** 两次以添加两个新行。</span><span class="sxs-lookup"><span data-stu-id="53fe6-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="53fe6-170">在 **名称器框中** ，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="53fe6-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="53fe6-171">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="53fe6-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="53fe6-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="53fe6-173">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="53fe6-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="53fe6-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="53fe6-175">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="53fe6-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="53fe6-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="53fe6-177">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="53fe6-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="53fe6-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="53fe6-180">Select the **Save** (check mark) control.</span><span class="sxs-lookup"><span data-stu-id="53fe6-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="53fe6-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="53fe6-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="53fe6-183">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="53fe6-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="53fe6-184">如果已列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="53fe6-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="53fe6-p109">*仅*  当具有这四个  *正确*  的名称服务器以外的现有名称服务器时，执行以下步骤。（即，  *仅*  删除名称  *不是* **ns1.bdm.microsoftonline.com** 、 **ns2.bdm.microsoftonline.com** 、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的任何当前名称服务器。）</span><span class="sxs-lookup"><span data-stu-id="53fe6-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="53fe6-187">如果名称服务器框中列出了任何其他名称服务器，请通过选择每个名称服务器，然后按键盘上的 **Delete** 键将其删除。</span><span class="sxs-lookup"><span data-stu-id="53fe6-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="53fe6-189">选择 **"添加 NAMESERVER"** 两次以添加两个新行。</span><span class="sxs-lookup"><span data-stu-id="53fe6-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="53fe6-191">在 **名称器框中** ，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="53fe6-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="53fe6-192">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="53fe6-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="53fe6-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="53fe6-194">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="53fe6-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="53fe6-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="53fe6-196">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="53fe6-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="53fe6-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="53fe6-198">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="53fe6-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="53fe6-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="53fe6-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="53fe6-201">Select the **Save** (check mark) control.</span><span class="sxs-lookup"><span data-stu-id="53fe6-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="53fe6-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="53fe6-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="53fe6-204">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="53fe6-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
