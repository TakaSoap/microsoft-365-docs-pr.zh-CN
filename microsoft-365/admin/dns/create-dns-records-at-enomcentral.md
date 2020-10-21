---
title: 在 eNomCentral 处为 Microsoft 创建 DNS 记录
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 了解如何验证您的域，并在 eNomCentral for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: c60c33f4be94e2f7719fdfc583500c6d1164991d
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646159"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="bed5e-103">在 eNomCentral 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="bed5e-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="bed5e-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="bed5e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="bed5e-105">如果 eNomCentral 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="bed5e-106">在 eNomCentral 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="bed5e-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="bed5e-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="bed5e-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="bed5e-110">Add a TXT record for verification</span></span>
<span data-ttu-id="bed5e-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bed5e-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="bed5e-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="bed5e-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="bed5e-116">请按下列步骤操作或[观看视频（从 0:46 开始）](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="bed5e-p104">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="bed5e-120">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="bed5e-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="bed5e-122">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-验证-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. <span data-ttu-id="bed5e-124">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="bed5e-125">从下拉列表中选择 " **记录类型** " 值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-125">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="bed5e-126">主机名</span><span class="sxs-lookup"><span data-stu-id="bed5e-126">Host Name</span></span>|<span data-ttu-id="bed5e-127">Record Type</span><span class="sxs-lookup"><span data-stu-id="bed5e-127">Record Type</span></span>|<span data-ttu-id="bed5e-128">地址</span><span class="sxs-lookup"><span data-stu-id="bed5e-128">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="bed5e-129">TXT</span><span class="sxs-lookup"><span data-stu-id="bed5e-129">TXT</span></span>|<span data-ttu-id="bed5e-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bed5e-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bed5e-131">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="bed5e-131">**Note:** This is an example.</span></span> <span data-ttu-id="bed5e-132">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="bed5e-133">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="bed5e-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-验证-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. <span data-ttu-id="bed5e-135">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-135">Select **save**.</span></span>

   ![eNom-验证-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. <span data-ttu-id="bed5e-137">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="bed5e-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="bed5e-138">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="bed5e-139">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="bed5e-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="bed5e-140">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bed5e-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="bed5e-141">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="bed5e-141">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="bed5e-142">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="bed5e-142">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="bed5e-143">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="bed5e-143">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="bed5e-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="bed5e-147">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="bed5e-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="bed5e-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="bed5e-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="bed5e-149">请执行以下步骤或 [观看视频 (从 3:40) 开始 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="bed5e-p107">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="bed5e-153">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="bed5e-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="bed5e-155">在 " **管理域** " 下拉列表中，选择 " **电子邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>

   ![eNom-配置-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. <span data-ttu-id="bed5e-157">在 " **服务选择** " 下拉列表中，选择 " \*\*用户 (" MX) \*\*。</span><span class="sxs-lookup"><span data-stu-id="bed5e-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>

   ![eNom-配置-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. <span data-ttu-id="bed5e-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bed5e-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="bed5e-160">主机名</span><span class="sxs-lookup"><span data-stu-id="bed5e-160">Host Name</span></span>|<span data-ttu-id="bed5e-161">地址</span><span class="sxs-lookup"><span data-stu-id="bed5e-161">Address</span></span>|<span data-ttu-id="bed5e-162">Pref</span><span class="sxs-lookup"><span data-stu-id="bed5e-162">Pref</span></span>|
   |---|---|---|
   |@| <span data-ttu-id="bed5e-163">*\<domain-key\>*  . mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="bed5e-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="bed5e-164">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="bed5e-165">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="bed5e-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> <span data-ttu-id="bed5e-166">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="bed5e-166">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>|<span data-ttu-id="bed5e-167">10  </span><span class="sxs-lookup"><span data-stu-id="bed5e-167">10</span></span>  <br/> <span data-ttu-id="bed5e-168">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="bed5e-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span>|

   ![eNom-配置-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. <span data-ttu-id="bed5e-170">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-170">Select **save**.</span></span>

   ![eNom-配置-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. <span data-ttu-id="bed5e-172">如果存在任何其他现有 MX 记录，请选中这些记录的复选框以将其选中。</span><span class="sxs-lookup"><span data-stu-id="bed5e-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>

   ![eNom-配置-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. <span data-ttu-id="bed5e-174">选择 " **删除已选中**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-174">Select **delete checked**.</span></span>

   ![eNom-配置-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="bed5e-176">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="bed5e-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="bed5e-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="bed5e-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="bed5e-178">请执行以下步骤或 [观看视频 (从 4:24) 开始 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="bed5e-p109">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="bed5e-182">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="bed5e-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="bed5e-184">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="bed5e-186">选择 " **新建行**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-186">Select **new row**.</span></span>

   ![eNom-配置-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. <span data-ttu-id="bed5e-188">在六个新记录的框中，键入或复制并粘贴以下值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>

   <span data-ttu-id="bed5e-189">从下拉列表中选择 " **记录类型** " 值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-189">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="bed5e-190">主机名</span><span class="sxs-lookup"><span data-stu-id="bed5e-190">Host Name</span></span>|<span data-ttu-id="bed5e-191">Record Type</span><span class="sxs-lookup"><span data-stu-id="bed5e-191">Record Type</span></span>|<span data-ttu-id="bed5e-192">地址</span><span class="sxs-lookup"><span data-stu-id="bed5e-192">Address</span></span>|
   |---|---|---|
   |<span data-ttu-id="bed5e-193">自动发现</span><span class="sxs-lookup"><span data-stu-id="bed5e-193">autodiscover</span></span>|<span data-ttu-id="bed5e-194">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="bed5e-194">CNAME (Alias)</span></span>|<span data-ttu-id="bed5e-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bed5e-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="bed5e-196">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-196">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="bed5e-197">sip</span><span class="sxs-lookup"><span data-stu-id="bed5e-197">sip</span></span>|<span data-ttu-id="bed5e-198">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="bed5e-198">CNAME (Alias)</span></span>|<span data-ttu-id="bed5e-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bed5e-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bed5e-200">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-200">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="bed5e-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bed5e-201">lyncdiscover</span></span>|<span data-ttu-id="bed5e-202">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="bed5e-202">CNAME (Alias)</span></span>|<span data-ttu-id="bed5e-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bed5e-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bed5e-204">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-204">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="bed5e-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bed5e-205">enterpriseregistration</span></span>|<span data-ttu-id="bed5e-206">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="bed5e-206">CNAME (Alias)</span></span>|<span data-ttu-id="bed5e-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="bed5e-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="bed5e-208">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-208">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="bed5e-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bed5e-209">enterpriseenrollment</span></span>|<span data-ttu-id="bed5e-210">CNAME（别名）</span><span class="sxs-lookup"><span data-stu-id="bed5e-210">CNAME (Alias)</span></span>|<span data-ttu-id="bed5e-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="bed5e-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="bed5e-212">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-212">**This value MUST end with a period (.)**</span></span>|

   ![eNom-配置-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. <span data-ttu-id="bed5e-214">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-214">Select **save**.</span></span>

   ![eNom-配置-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bed5e-216">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="bed5e-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bed5e-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="bed5e-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bed5e-218">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="bed5e-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bed5e-219">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="bed5e-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bed5e-220">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="bed5e-221">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的  *单个*  SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="bed5e-222">请执行以下步骤或 [观看视频 (从 5:12) 开始 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-222">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="bed5e-p111">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="bed5e-226">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="bed5e-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="bed5e-228">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="bed5e-230">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="bed5e-231">从下拉列表中选择 " **记录类型** " 值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-231">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="bed5e-232">主机名</span><span class="sxs-lookup"><span data-stu-id="bed5e-232">Host Name</span></span>|<span data-ttu-id="bed5e-233">Record Type</span><span class="sxs-lookup"><span data-stu-id="bed5e-233">Record Type</span></span>|<span data-ttu-id="bed5e-234">地址</span><span class="sxs-lookup"><span data-stu-id="bed5e-234">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="bed5e-235">TXT</span><span class="sxs-lookup"><span data-stu-id="bed5e-235">TXT</span></span>|<span data-ttu-id="bed5e-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bed5e-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="bed5e-237">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="bed5e-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>|

   ![eNom-配置-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. <span data-ttu-id="bed5e-239">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-239">Select **save**.</span></span>

   ![eNom-配置-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="bed5e-241">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="bed5e-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="bed5e-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="bed5e-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="bed5e-243">请执行以下步骤或 [观看视频 (从 5:50) 开始 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-243">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="bed5e-p112">若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-配置-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="bed5e-247">在 **"我的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="bed5e-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-配置-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="bed5e-249">在" **管理域**"下拉列表中，选择" **主机记录**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-配置-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="bed5e-251">在 " **新行**" 的右侧，选择 " **添加 SRV 或 SPF 记录**"。</span><span class="sxs-lookup"><span data-stu-id="bed5e-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>

   ![eNom-配置-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. <span data-ttu-id="bed5e-253">在两个新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="bed5e-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="bed5e-254">服务</span><span class="sxs-lookup"><span data-stu-id="bed5e-254">Service</span></span>|<span data-ttu-id="bed5e-255">协议</span><span class="sxs-lookup"><span data-stu-id="bed5e-255">Protocol</span></span>|<span data-ttu-id="bed5e-256">Priority</span><span class="sxs-lookup"><span data-stu-id="bed5e-256">Priority</span></span>|<span data-ttu-id="bed5e-257">粗细</span><span class="sxs-lookup"><span data-stu-id="bed5e-257">Weight</span></span>|<span data-ttu-id="bed5e-258">端口</span><span class="sxs-lookup"><span data-stu-id="bed5e-258">Port</span></span>|<span data-ttu-id="bed5e-259">目标 (主机名) </span><span class="sxs-lookup"><span data-stu-id="bed5e-259">Target (Hostname)</span></span>|
   |---|---|---|---|---|---|
   |<span data-ttu-id="bed5e-260">_sip</span><span class="sxs-lookup"><span data-stu-id="bed5e-260">_sip</span></span>|<span data-ttu-id="bed5e-261">_tls</span><span class="sxs-lookup"><span data-stu-id="bed5e-261">_tls</span></span>|<span data-ttu-id="bed5e-262">100</span><span class="sxs-lookup"><span data-stu-id="bed5e-262">100</span></span>|<span data-ttu-id="bed5e-263">1</span><span class="sxs-lookup"><span data-stu-id="bed5e-263">1</span></span>|<span data-ttu-id="bed5e-264">443</span><span class="sxs-lookup"><span data-stu-id="bed5e-264">443</span></span>|<span data-ttu-id="bed5e-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bed5e-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bed5e-266">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-266">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="bed5e-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bed5e-267">_sipfederationtls</span></span>|<span data-ttu-id="bed5e-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="bed5e-268">_tcp</span></span>|<span data-ttu-id="bed5e-269">100</span><span class="sxs-lookup"><span data-stu-id="bed5e-269">100</span></span>|<span data-ttu-id="bed5e-270">1</span><span class="sxs-lookup"><span data-stu-id="bed5e-270">1</span></span>|<span data-ttu-id="bed5e-271">5061</span><span class="sxs-lookup"><span data-stu-id="bed5e-271">5061</span></span>|<span data-ttu-id="bed5e-272">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="bed5e-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="bed5e-273">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="bed5e-273">**This value MUST end with a period (.)**</span></span>|

   ![eNom-配置-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. <span data-ttu-id="bed5e-275">选择 "**保存**"</span><span class="sxs-lookup"><span data-stu-id="bed5e-275">Select **save**</span></span>

   ![eNom-配置-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> <span data-ttu-id="bed5e-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="bed5e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
