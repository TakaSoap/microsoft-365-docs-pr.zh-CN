---
title: 在 Google Domains 为 Office 365 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 了解如何在适用于 Office 365 的 Google 域上验证您的域并为电子邮件、Lync 和其他服务设置 DNS 记录。
ms.openlocfilehash: f0a9a42127fc5b722679013b899255f77840d670
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211723"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="cbb69-103">在 Google Domains 为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cbb69-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="cbb69-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="cbb69-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cbb69-105">如果 DNS 托管提供商是 Google Domains，请按照本文中的步骤验证域并为电子邮件、Lync 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="cbb69-106">在 Google Domains 添加这些记录后，域将设置为使用 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="cbb69-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cbb69-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="cbb69-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cbb69-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cbb69-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cbb69-109">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cbb69-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cbb69-110">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cbb69-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cbb69-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="cbb69-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cbb69-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb69-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cbb69-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="cbb69-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cbb69-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="cbb69-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cbb69-p104">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cbb69-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="cbb69-120">选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="cbb69-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="cbb69-121">输入登录凭据，然后再次选择 **"登录**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="cbb69-122">在 "**我的域**" 页面上，找到要用于 Office 365 的域，然后选择它旁边的 "**管理**" 链接。</span><span class="sxs-lookup"><span data-stu-id="cbb69-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="cbb69-123">在左侧导航栏中，选择 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="cbb69-124">在 "\* \* 自定义资源记录 \* \*" 部分中新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="cbb69-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cbb69-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cbb69-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cbb69-127">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbb69-127">**Name**</span></span> <br/> |<span data-ttu-id="cbb69-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="cbb69-128">**Type**</span></span> <br/> |<span data-ttu-id="cbb69-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cbb69-129">**TTL**</span></span> <br/> |<span data-ttu-id="cbb69-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="cbb69-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="cbb69-131">TXT</span><span class="sxs-lookup"><span data-stu-id="cbb69-131">TXT</span></span>  <br/> |<span data-ttu-id="cbb69-132">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-132">1H</span></span>  <br/> |<span data-ttu-id="cbb69-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cbb69-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cbb69-134">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="cbb69-134">**Note:** This is an example.</span></span> <span data-ttu-id="cbb69-135">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="cbb69-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="cbb69-136">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="cbb69-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="cbb69-137">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="cbb69-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="cbb69-138">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="cbb69-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cbb69-139">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cbb69-140">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="cbb69-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cbb69-141">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="cbb69-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cbb69-142">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="cbb69-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cbb69-143">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="cbb69-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cbb69-144">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="cbb69-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cbb69-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cbb69-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cbb69-146">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cbb69-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cbb69-147">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cbb69-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cbb69-148">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="cbb69-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cbb69-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb69-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cbb69-p108">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cbb69-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="cbb69-153">选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="cbb69-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="cbb69-154">输入登录凭据，然后再次选择 **"登录**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="cbb69-155">在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。</span><span class="sxs-lookup"><span data-stu-id="cbb69-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cbb69-p109">如果有 G 套件电子邮件帐户，必须先删除与该帐户关联的 MX 记录。G 套件的 MX 记录将导致无法添加任何其他 MX 记录，包括 Office 365 所需的 MX 记录。请注意，删除 G 套件记录不会删除 G 套件帐户。若要删除 G 套件 MX 记录，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="cbb69-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="cbb69-160">在 "**综合记录**" 部分的 " **G 套件**" 区域中，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="cbb69-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-161">(You may have to scroll down.)</span></span>
    
    ![在 "综合记录" 部分中选择 "删除"](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="cbb69-163">选择“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbb69-163">Select **Delete**.</span></span>
    
    ![选择 "删除"](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="cbb69-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cbb69-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cbb69-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cbb69-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cbb69-168">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbb69-168">**Name**</span></span>|<span data-ttu-id="cbb69-169">**Type**</span><span class="sxs-lookup"><span data-stu-id="cbb69-169">**Type**</span></span>|<span data-ttu-id="cbb69-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cbb69-170">**TTL**</span></span>|<span data-ttu-id="cbb69-171">**Data**</span><span class="sxs-lookup"><span data-stu-id="cbb69-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="cbb69-172">MX</span><span class="sxs-lookup"><span data-stu-id="cbb69-172">MX</span></span>  <br/> |<span data-ttu-id="cbb69-173">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-173">1H</span></span>  <br/> |<span data-ttu-id="cbb69-174">0  *\<域密钥\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cbb69-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cbb69-175">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="cbb69-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cbb69-p110">**0** 是 MX 优先级值。将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  </span><span class="sxs-lookup"><span data-stu-id="cbb69-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="cbb69-178">**注意：** 从 Office 365 帐户获取 \<*域密钥*\>。</span><span class="sxs-lookup"><span data-stu-id="cbb69-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  <span data-ttu-id="cbb69-179">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="cbb69-179">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          <span data-ttu-id="cbb69-180">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="cbb69-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![在 "自定义资源记录" 部分键入或粘贴值](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="cbb69-182">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="cbb69-182">Select **Add**.</span></span>
    
    ![选择"添加"](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="cbb69-184">如果有任何其他自定义 MX 记录，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="cbb69-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="cbb69-185">在 "MX 记录" 行中选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-185">Select **Edit** in the MX record row.</span></span> 
    
    ![在 MX 记录行中选择 "编辑"](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="cbb69-187">对于每个其他自定义 MX 记录，请选择 "**数据**" 框中的条目，然后按键盘上的**Delete**键以删除该记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="cbb69-188">继续操作，直到删除所有其他 MX 记录的" **数据**"条目。</span><span class="sxs-lookup"><span data-stu-id="cbb69-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="cbb69-190">删除了每个其他 MX 记录的**数据**输入后，请选择 "**保存**" 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cbb69-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![选择 "保存"](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cbb69-192">添加 Office 365 所需的五个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="cbb69-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="cbb69-193">若要开始，请转到 [Google 域页面] （https://domains.google.com/registrar)并登录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="cbb69-194">在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。</span><span class="sxs-lookup"><span data-stu-id="cbb69-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cbb69-195">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="cbb69-196">在" **自定义资源记录**"部分中新记录的框内，键入或复制粘贴下表第一行中的值。</span><span class="sxs-lookup"><span data-stu-id="cbb69-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="cbb69-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cbb69-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cbb69-199">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbb69-199">**Name**</span></span>|<span data-ttu-id="cbb69-200">**Type**</span><span class="sxs-lookup"><span data-stu-id="cbb69-200">**Type**</span></span>|<span data-ttu-id="cbb69-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cbb69-201">**TTL**</span></span>|<span data-ttu-id="cbb69-202">**Data**</span><span class="sxs-lookup"><span data-stu-id="cbb69-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cbb69-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cbb69-203">autodiscover</span></span>  <br/> |<span data-ttu-id="cbb69-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="cbb69-204">CNAME</span></span>  <br/> |<span data-ttu-id="cbb69-205">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-205">1H</span></span>  <br/> |<span data-ttu-id="cbb69-206">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cbb69-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cbb69-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cbb69-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cbb69-208">sip</span><span class="sxs-lookup"><span data-stu-id="cbb69-208">sip</span></span>  <br/> |<span data-ttu-id="cbb69-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="cbb69-209">CNAME</span></span>  <br/> |<span data-ttu-id="cbb69-210">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-210">1H</span></span>  <br/> |<span data-ttu-id="cbb69-211">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cbb69-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cbb69-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cbb69-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cbb69-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cbb69-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cbb69-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="cbb69-214">CNAME</span></span>  <br/> |<span data-ttu-id="cbb69-215">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-215">1H</span></span>  <br/> |<span data-ttu-id="cbb69-216">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cbb69-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cbb69-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cbb69-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cbb69-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cbb69-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cbb69-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="cbb69-219">CNAME</span></span>  <br/> |<span data-ttu-id="cbb69-220">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-220">1H</span></span>  <br/> |<span data-ttu-id="cbb69-221">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="cbb69-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cbb69-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cbb69-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cbb69-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cbb69-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cbb69-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="cbb69-224">CNAME</span></span>  <br/> |<span data-ttu-id="cbb69-225">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-225">1H</span></span>  <br/> |<span data-ttu-id="cbb69-226">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="cbb69-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cbb69-227">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cbb69-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![在 "自定义资源记录" 部分键入或粘贴值](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="cbb69-229">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="cbb69-229">Select **Add**.</span></span>
    
    ![选择"添加"](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="cbb69-231">添加其他 4 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="cbb69-232">在 "**自定义资源记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**添加**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="cbb69-233">重复此过程，直到您已创建所有必需的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cbb69-234">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="cbb69-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbb69-235">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="cbb69-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cbb69-236">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="cbb69-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cbb69-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cbb69-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cbb69-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span><span class="sxs-lookup"><span data-stu-id="cbb69-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="cbb69-239">需要示例吗？</span><span class="sxs-lookup"><span data-stu-id="cbb69-239">Need examples?</span></span> <span data-ttu-id="cbb69-240">请查看 [Office 365 的外部域名系统记录](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)。</span><span class="sxs-lookup"><span data-stu-id="cbb69-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="cbb69-241">若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="cbb69-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="cbb69-p113">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cbb69-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="cbb69-245">选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="cbb69-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="cbb69-246">输入登录凭据，然后再次选择 **"登录**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="cbb69-247">在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。</span><span class="sxs-lookup"><span data-stu-id="cbb69-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cbb69-248">在 "**自定义资源记录**" 部分的 "TXT 记录" 行中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="cbb69-p114">Google Domains 会将 TXT 记录存储为可能含有多条记录的集。存在至少一条其他 TXT 记录（例如用于验证域的 TXT 记录）时，必须向该记录集添加新的 TXT 记录。如果尝试将其他 TXT 记录作为单独条目进行输入，将始终出现" **记录重复**"错误信息。</span><span class="sxs-lookup"><span data-stu-id="cbb69-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![在 TXT 记录行中选择 "编辑"](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="cbb69-253">选择 " **（+）** " 控件。</span><span class="sxs-lookup"><span data-stu-id="cbb69-253">Select the **(+)** control.</span></span> 
    
    ![选择加号控件](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="cbb69-255">在新记录的框中，键入或复制粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="cbb69-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cbb69-256">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="cbb69-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cbb69-257">**数据**</span><span class="sxs-lookup"><span data-stu-id="cbb69-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="cbb69-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cbb69-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="cbb69-259">我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="cbb69-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![在 "自定义资源记录" 部分键入或粘贴值](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="cbb69-261">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cbb69-261">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cbb69-263">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="cbb69-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cbb69-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cbb69-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cbb69-p115">要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cbb69-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="cbb69-268">选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="cbb69-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="cbb69-269">输入登录凭据，然后再次选择 **"登录**"。</span><span class="sxs-lookup"><span data-stu-id="cbb69-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="cbb69-270">在 "**域**" 页上的 "**域**" 部分，为要编辑的域选择 "**配置 DNS** "。</span><span class="sxs-lookup"><span data-stu-id="cbb69-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="cbb69-271">添加第一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="cbb69-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cbb69-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cbb69-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cbb69-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cbb69-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cbb69-275">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbb69-275">**Name**</span></span>|<span data-ttu-id="cbb69-276">**Type**</span><span class="sxs-lookup"><span data-stu-id="cbb69-276">**Type**</span></span>|<span data-ttu-id="cbb69-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cbb69-277">**TTL**</span></span>|<span data-ttu-id="cbb69-278">**数据**</span><span class="sxs-lookup"><span data-stu-id="cbb69-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cbb69-279">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="cbb69-279">_sip._tls</span></span>|<span data-ttu-id="cbb69-280">SRV</span><span class="sxs-lookup"><span data-stu-id="cbb69-280">SRV</span></span>|<span data-ttu-id="cbb69-281">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-281">1H</span></span>|<span data-ttu-id="cbb69-282">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cbb69-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="cbb69-283">**此值必须以句点（.）结尾\*\*\*\*注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="cbb69-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="cbb69-284">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="cbb69-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="cbb69-285">SRV</span><span class="sxs-lookup"><span data-stu-id="cbb69-285">SRV</span></span>|<span data-ttu-id="cbb69-286">1H</span><span class="sxs-lookup"><span data-stu-id="cbb69-286">1H</span></span>|<span data-ttu-id="cbb69-287">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cbb69-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="cbb69-288">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cbb69-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="cbb69-289">我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="cbb69-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![在 "自定义资源记录" 部分键入或粘贴值](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="cbb69-291">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="cbb69-291">Select **Add**.</span></span>
    
    ![选择"添加"](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="cbb69-293">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="cbb69-294">在 "**自定义资源记录**" 部分，使用表中第二行的值创建记录，然后再次选择 "**添加**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="cbb69-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cbb69-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cbb69-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cbb69-296">但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。</span><span class="sxs-lookup"><span data-stu-id="cbb69-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cbb69-297">如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="cbb69-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
