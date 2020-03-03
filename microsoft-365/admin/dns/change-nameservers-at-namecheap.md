---
title: 更改名称服务器以使用 Namecheap 设置 Office 365
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: '如果您希望 Office 365 管理您的 DNS 记录，请了解如何使用 Namecheap 设置 Office 365 自定义域。 '
ms.openlocfilehash: 3a26f2acb9bb52d05974f050b265dd3e1a0fc0cb
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351803"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a><span data-ttu-id="3fb62-103">更改名称服务器以使用 Namecheap 设置 Office 365</span><span class="sxs-lookup"><span data-stu-id="3fb62-103">Change nameservers to set up Office 365 with Namecheap</span></span>

 <span data-ttu-id="3fb62-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="3fb62-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="3fb62-105">如果希望 Office 365 管理 Office 365 DNS 记录，请按以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="3fb62-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="3fb62-106">（如果你愿意，可以[在 Namecheap 管理所有 Office 365 DNS 记录](create-dns-records-at-namecheap.md)。）</span><span class="sxs-lookup"><span data-stu-id="3fb62-106">(If you prefer, you can [manage all your Office 365 DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3fb62-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="3fb62-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="3fb62-108">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="3fb62-108">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="3fb62-109">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="3fb62-109">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="3fb62-111">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="3fb62-113">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="3fb62-115">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="3fb62-117">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="3fb62-119">在 "**类型**" 下拉中，选择 " **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3fb62-120">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="3fb62-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-验证-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="3fb62-122">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="3fb62-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3fb62-123">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="3fb62-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="3fb62-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="3fb62-124">**Type**</span></span>|<span data-ttu-id="3fb62-125">**主机**</span><span class="sxs-lookup"><span data-stu-id="3fb62-125">**Host**</span></span>|<span data-ttu-id="3fb62-126">**值**</span><span class="sxs-lookup"><span data-stu-id="3fb62-126">**Value**</span></span>|<span data-ttu-id="3fb62-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3fb62-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3fb62-128">TXT</span><span class="sxs-lookup"><span data-stu-id="3fb62-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="3fb62-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3fb62-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3fb62-130">**注意**：这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="3fb62-130">**Note**: This is an example.</span></span> <span data-ttu-id="3fb62-131">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="3fb62-131">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="3fb62-132">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="3fb62-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3fb62-133">30分钟</span><span class="sxs-lookup"><span data-stu-id="3fb62-133">30 min</span></span>  <br/> |
   
   ![Namecheap-验证-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="3fb62-135">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="3fb62-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-验证-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="3fb62-137">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="3fb62-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3fb62-138">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="3fb62-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="3fb62-139">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="3fb62-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3fb62-140">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="3fb62-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3fb62-141">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="3fb62-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3fb62-142">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="3fb62-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3fb62-143">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="3fb62-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3fb62-p104">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb62-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="3fb62-147">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="3fb62-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="3fb62-p105">要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="3fb62-p105">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3fb62-p106">将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。例如，在你进行此更改之后，发送到你的域（例如 rob@ *your_domain*  .com）的所有电子邮件都将开始传送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="3fb62-p106">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="3fb62-153">完成本部分中的步骤后，应  *仅*  列出以下四个名称服务器： >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  以下过程将演示如何从列表中删除任何其他不需要的名称服务器，以及如何添加  *正确*  的名称服务器（如果它们尚未显示在列表中）。</span><span class="sxs-lookup"><span data-stu-id="3fb62-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="3fb62-154">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="3fb62-154">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="3fb62-155">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="3fb62-155">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="3fb62-157">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="3fb62-159">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="3fb62-161">选择 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-161">Select **Domain**.</span></span>
    
    ![Namecheap-委派-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="3fb62-163">找到 "**名称服务器**" 部分，然后从 " **Namecheap 默认**" 下拉列表中选择 "**自定义**"。</span><span class="sxs-lookup"><span data-stu-id="3fb62-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-委派-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="3fb62-165">根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一。</span><span class="sxs-lookup"><span data-stu-id="3fb62-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="3fb62-166">如果未列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="3fb62-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="3fb62-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="3fb62-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="3fb62-168">选择 "**添加**名称服务器" 两次，添加两个新行。</span><span class="sxs-lookup"><span data-stu-id="3fb62-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-委派-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="3fb62-170">在 "名称服务器 **" 框中**，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="3fb62-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="3fb62-171">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="3fb62-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="3fb62-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="3fb62-173">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="3fb62-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="3fb62-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="3fb62-175">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="3fb62-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="3fb62-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="3fb62-177">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="3fb62-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="3fb62-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-委派-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="3fb62-180">选择 "**保存**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="3fb62-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-委派-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="3fb62-p108">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="3fb62-p108">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="3fb62-184">如果已列出名称服务器</span><span class="sxs-lookup"><span data-stu-id="3fb62-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="3fb62-p109">*仅*  当具有这四个  *正确*  的名称服务器以外的现有名称服务器时，执行以下步骤。（即，  *仅*  删除名称  *不是* **ns1.bdm.microsoftonline.com** 、 **ns2.bdm.microsoftonline.com** 、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的任何当前名称服务器。）</span><span class="sxs-lookup"><span data-stu-id="3fb62-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="3fb62-187">如果在**Nameserver**框中列出了任何其他名称服务器，则通过选择它并按键盘上的**delete**键来删除每个。</span><span class="sxs-lookup"><span data-stu-id="3fb62-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-委派-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="3fb62-189">选择 "**添加**名称服务器" 两次，添加两个新行。</span><span class="sxs-lookup"><span data-stu-id="3fb62-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-委派-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="3fb62-191">在 "名称服务器 **" 框中**，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="3fb62-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="3fb62-192">**名称服务器 1**</span><span class="sxs-lookup"><span data-stu-id="3fb62-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="3fb62-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="3fb62-194">**名称服务器 2**</span><span class="sxs-lookup"><span data-stu-id="3fb62-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="3fb62-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="3fb62-196">**名称服务器 3**</span><span class="sxs-lookup"><span data-stu-id="3fb62-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="3fb62-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="3fb62-198">**名称服务器 4**</span><span class="sxs-lookup"><span data-stu-id="3fb62-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="3fb62-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="3fb62-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-委派-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="3fb62-201">选择 "**保存**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="3fb62-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-委派-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="3fb62-p110">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="3fb62-p110">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
