---
title: 在 easyDNS 上为 Office 365 创建 DNS 记录
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 了解如何在 easyDNS for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251212"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="2101c-103">在 easyDNS 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2101c-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="2101c-104">如果找不到您要查找的内容，[请检查域 FAQ](../setup/domains-faq.md) 。</span><span class="sxs-lookup"><span data-stu-id="2101c-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2101c-105">您需要在注册机构的网站上添加以下所有 DNS 记录以将邮件路由到 Office 365，并将您的域用于团队和 Skype for Business 等。</span><span class="sxs-lookup"><span data-stu-id="2101c-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="2101c-106">注意：所有 easyDNS service 程序包中当前都不提供 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2101c-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="2101c-107">您可能需要使用 easyDNS 升级到较高的服务级别，以添加 Office 365 Skype for Business 所需的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2101c-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="2101c-108">验证您是否拥有包含 TXT 记录的域</span><span class="sxs-lookup"><span data-stu-id="2101c-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="2101c-109">转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="2101c-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="2101c-110">在 "**所有域**" 标题下，选择 " **dns"。**</span><span class="sxs-lookup"><span data-stu-id="2101c-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="2101c-111">在 " **TXT 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。</span><span class="sxs-lookup"><span data-stu-id="2101c-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="2101c-112">在 "文本" 字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="2101c-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="2101c-113">**主机**</span><span class="sxs-lookup"><span data-stu-id="2101c-113">**Host**</span></span>|<span data-ttu-id="2101c-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="2101c-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="2101c-115">MS = msXXXXXXXX （在管理中心域页面上使用提供给你的值）</span><span class="sxs-lookup"><span data-stu-id="2101c-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="2101c-116">选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="2101c-117">请进行检查以确保记录正确，然后选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="2101c-118">在继续之前，请等待几分钟，以便您刚刚创建的记录可以通过 Internet 传播并在 Office 365 中检测到。</span><span class="sxs-lookup"><span data-stu-id="2101c-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="2101c-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="2101c-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="2101c-120">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="2101c-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="2101c-121">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="2101c-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="2101c-122">在 "**设置**" 页上，选择 "**启动安装程序"。**</span><span class="sxs-lookup"><span data-stu-id="2101c-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="2101c-123">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="2101c-124">添加 MX 记录以将电子邮件路由到 Office 365</span><span class="sxs-lookup"><span data-stu-id="2101c-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="2101c-125">转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="2101c-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="2101c-126">在 "**所有域**" 标题下，选择 " **dns"。**</span><span class="sxs-lookup"><span data-stu-id="2101c-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="2101c-127">在 " **MX 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。</span><span class="sxs-lookup"><span data-stu-id="2101c-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="2101c-128">在 "文本" 字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="2101c-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="2101c-129">**区域邮件**</span><span class="sxs-lookup"><span data-stu-id="2101c-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="2101c-130">**邮件服务器**</span><span class="sxs-lookup"><span data-stu-id="2101c-130">**MAIL SERVER**</span></span>|<span data-ttu-id="2101c-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="2101c-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2101c-132">\<\>mail.protection.outlook.com （从管理中心域页面获取\<你的域\>密钥值）</span><span class="sxs-lookup"><span data-stu-id="2101c-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="2101c-133">0</span><span class="sxs-lookup"><span data-stu-id="2101c-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="2101c-134">如果要保存其他 MX 记录以进行备份，请将它们复制到某处。</span><span class="sxs-lookup"><span data-stu-id="2101c-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="2101c-135">在继续之前，请在此处删除所有其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="2101c-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="2101c-136">选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="2101c-137">请进行检查以确保记录正确，然后选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="2101c-138">添加所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="2101c-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="2101c-139">转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="2101c-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="2101c-140">在 "**所有域**" 标题下，选择 " **dns"。**</span><span class="sxs-lookup"><span data-stu-id="2101c-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="2101c-141">在 " **CNAME/别名记录**" 标题下，选择 "编辑" 按钮（扳手图标）。</span><span class="sxs-lookup"><span data-stu-id="2101c-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="2101c-142">在 "文本" 字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="2101c-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="2101c-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="2101c-143">**HOST**</span></span>|<span data-ttu-id="2101c-144">**Address （必须以 "." 结尾）**</span><span class="sxs-lookup"><span data-stu-id="2101c-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="2101c-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2101c-145">autodiscover</span></span>  <br/> |<span data-ttu-id="2101c-146">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="2101c-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="2101c-147">sip</span><span class="sxs-lookup"><span data-stu-id="2101c-147">sip</span></span>  <br/> |<span data-ttu-id="2101c-148">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="2101c-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="2101c-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2101c-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2101c-150">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="2101c-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="2101c-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2101c-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2101c-152">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="2101c-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="2101c-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2101c-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2101c-154">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="2101c-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="2101c-155">选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="2101c-156">请进行检查以确保记录正确，然后选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2101c-157">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2101c-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="2101c-158">转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="2101c-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="2101c-159">在 "**所有域**" 标题下，选择 " **dns"。**</span><span class="sxs-lookup"><span data-stu-id="2101c-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="2101c-160">在 " **TXT 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。</span><span class="sxs-lookup"><span data-stu-id="2101c-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="2101c-161">在 "文本" 字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="2101c-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="2101c-162">**主机**</span><span class="sxs-lookup"><span data-stu-id="2101c-162">**Host**</span></span>|<span data-ttu-id="2101c-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="2101c-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="2101c-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2101c-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="2101c-165">选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="2101c-166">请进行检查以确保记录正确，然后选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="2101c-167">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2101c-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="2101c-168">注意： easyDNS ' Domain Plus service 级别下当前不提供 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2101c-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="2101c-169">您可能需要使用 easyDNS 升级到更高的服务级别，以添加 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2101c-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="2101c-170">转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="2101c-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="2101c-171">在 "**所有域**" 标题下，选择 " **dns"。**</span><span class="sxs-lookup"><span data-stu-id="2101c-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="2101c-172">在 " **SRV 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。</span><span class="sxs-lookup"><span data-stu-id="2101c-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="2101c-173">在 "文本" 字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="2101c-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="2101c-174">**服务台**</span><span class="sxs-lookup"><span data-stu-id="2101c-174">**SERVICE**</span></span>|<span data-ttu-id="2101c-175">**协议**</span><span class="sxs-lookup"><span data-stu-id="2101c-175">**PROTO**</span></span>|<span data-ttu-id="2101c-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="2101c-176">**HOST**</span></span>|<span data-ttu-id="2101c-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="2101c-177">**PRI**</span></span>|<span data-ttu-id="2101c-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="2101c-178">**WGT**</span></span>|<span data-ttu-id="2101c-179">**端口**</span><span class="sxs-lookup"><span data-stu-id="2101c-179">**PORT**</span></span>|<span data-ttu-id="2101c-180">**目标（必须以 "." 结尾）**</span><span class="sxs-lookup"><span data-stu-id="2101c-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="2101c-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2101c-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2101c-182">_sip</span><span class="sxs-lookup"><span data-stu-id="2101c-182">_sip</span></span>  <br/> |<span data-ttu-id="2101c-183">TLS</span><span class="sxs-lookup"><span data-stu-id="2101c-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="2101c-184">100</span><span class="sxs-lookup"><span data-stu-id="2101c-184">100</span></span>  <br/> |<span data-ttu-id="2101c-185">1</span><span class="sxs-lookup"><span data-stu-id="2101c-185">1</span></span>  <br/> |<span data-ttu-id="2101c-186">443</span><span class="sxs-lookup"><span data-stu-id="2101c-186">443</span></span>  <br/> |<span data-ttu-id="2101c-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="2101c-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="2101c-188">1800</span><span class="sxs-lookup"><span data-stu-id="2101c-188">1800</span></span>  <br/> |
    |<span data-ttu-id="2101c-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2101c-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="2101c-190">TCP</span><span class="sxs-lookup"><span data-stu-id="2101c-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="2101c-191">100</span><span class="sxs-lookup"><span data-stu-id="2101c-191">100</span></span>  <br/> |<span data-ttu-id="2101c-192">1</span><span class="sxs-lookup"><span data-stu-id="2101c-192">1</span></span>  <br/> |<span data-ttu-id="2101c-193">5061</span><span class="sxs-lookup"><span data-stu-id="2101c-193">5061</span></span>  <br/> |<span data-ttu-id="2101c-194">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="2101c-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="2101c-195">1800</span><span class="sxs-lookup"><span data-stu-id="2101c-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="2101c-196">选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="2101c-197">请进行检查以确保记录正确，然后选择 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="2101c-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

