---
title: 在 EasyDNS 为 Microsoft 创建 DNS 记录
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 了解如何在 EasyDNS for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656815"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="4e178-103">在 EasyDNS 为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="4e178-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="4e178-104">[如果找不到 ](../setup/domains-faq.yml) 要查找的内容，请查看域常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="4e178-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4e178-105">你需要在注册机构网站上添加以下所有 DNS 记录，将邮件路由到 Microsoft，将域用于 Teams 和 Skype for Business，等等。</span><span class="sxs-lookup"><span data-stu-id="4e178-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="4e178-106">注意：SRV 记录当前在所有 easyDNS 服务包下不可用。</span><span class="sxs-lookup"><span data-stu-id="4e178-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="4e178-107">你可能需要使用 easyDNS 升级到更高的服务级别，以添加 Skype for Business 所需的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4e178-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="4e178-108">验证是否拥有具有 TXT 记录的域</span><span class="sxs-lookup"><span data-stu-id="4e178-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="4e178-109">转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。</span><span class="sxs-lookup"><span data-stu-id="4e178-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="4e178-110">在所有 **域标题** 下，选择 **dns。**</span><span class="sxs-lookup"><span data-stu-id="4e178-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="4e178-111">在 **TXT 记录** 标题下，选择编辑按钮 (扳手图标) 。</span><span class="sxs-lookup"><span data-stu-id="4e178-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="4e178-112">在文本字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="4e178-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="4e178-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="4e178-113">**Host**</span></span>|<span data-ttu-id="4e178-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="4e178-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="4e178-115">MS=msXXXXXXXX (使用管理中心"域"页上提供的值) </span><span class="sxs-lookup"><span data-stu-id="4e178-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="4e178-116">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="4e178-117">检查以确保记录正确，然后选择"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="4e178-118">请等待几分钟，然后再继续，以便你刚刚创建的记录可以传播到 Internet 中，并且 Microsoft 会检测到该记录。</span><span class="sxs-lookup"><span data-stu-id="4e178-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="4e178-119">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="4e178-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="4e178-120">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="4e178-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="4e178-121">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="4e178-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="4e178-122">在" **设置"** 页上，选择 **"开始设置"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="4e178-123">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="4e178-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="4e178-124">添加 MX 记录以将电子邮件路由到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e178-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="4e178-125">转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。</span><span class="sxs-lookup"><span data-stu-id="4e178-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="4e178-126">在所有 **域标题** 下，选择 **dns。**</span><span class="sxs-lookup"><span data-stu-id="4e178-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="4e178-127">在 **MX 记录标题** 下，选择编辑按钮 (扳手图标) 。</span><span class="sxs-lookup"><span data-stu-id="4e178-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="4e178-128">在文本字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="4e178-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="4e178-129">**区域邮件**</span><span class="sxs-lookup"><span data-stu-id="4e178-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="4e178-130">**邮件服务器**</span><span class="sxs-lookup"><span data-stu-id="4e178-130">**MAIL SERVER**</span></span>|<span data-ttu-id="4e178-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="4e178-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4e178-132">\<domain-key\>.mail.protection.outlook.com (从管理中心 \<domain-key\> "域"页面获取) </span><span class="sxs-lookup"><span data-stu-id="4e178-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="4e178-133">0</span><span class="sxs-lookup"><span data-stu-id="4e178-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="4e178-134">如果要保存其他 MX 记录以用于备份，请将其复制到某处。</span><span class="sxs-lookup"><span data-stu-id="4e178-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="4e178-135">在继续之前，请在此处删除所有其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="4e178-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="4e178-136">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="4e178-137">检查以确保记录正确，然后选择"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="4e178-138">添加所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="4e178-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="4e178-139">转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。</span><span class="sxs-lookup"><span data-stu-id="4e178-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="4e178-140">在所有 **域标题** 下，选择 **dns。**</span><span class="sxs-lookup"><span data-stu-id="4e178-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="4e178-141">在 **CNAME/别名** 记录标题下，选择 (扳手图标) 。</span><span class="sxs-lookup"><span data-stu-id="4e178-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="4e178-142">在文本字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="4e178-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="4e178-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="4e178-143">**HOST**</span></span>|<span data-ttu-id="4e178-144">**地址 (必须以"."结尾。)**</span><span class="sxs-lookup"><span data-stu-id="4e178-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4e178-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4e178-145">autodiscover</span></span>  <br/> |<span data-ttu-id="4e178-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="4e178-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="4e178-147">sip</span><span class="sxs-lookup"><span data-stu-id="4e178-147">sip</span></span>  <br/> |<span data-ttu-id="4e178-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4e178-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="4e178-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4e178-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4e178-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4e178-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="4e178-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4e178-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4e178-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="4e178-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="4e178-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4e178-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4e178-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4e178-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="4e178-155">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="4e178-156">检查以确保记录正确，然后选择"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4e178-157">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4e178-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="4e178-158">转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。</span><span class="sxs-lookup"><span data-stu-id="4e178-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="4e178-159">在所有 **域标题** 下，选择 **dns。**</span><span class="sxs-lookup"><span data-stu-id="4e178-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="4e178-160">在 **TXT 记录** 标题下，选择编辑按钮 (扳手图标) 。</span><span class="sxs-lookup"><span data-stu-id="4e178-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="4e178-161">在文本字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="4e178-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="4e178-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="4e178-162">**Host**</span></span>|<span data-ttu-id="4e178-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="4e178-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="4e178-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4e178-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="4e178-165">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="4e178-166">检查以确保记录正确，然后选择"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4e178-167">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="4e178-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="4e178-168">注意：SRV 记录当前在 easyDNS 的 Domain Plus 服务级别下不可用。</span><span class="sxs-lookup"><span data-stu-id="4e178-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="4e178-169">您可能需要使用 easyDNS 升级到更高的服务级别，以添加 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="4e178-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="4e178-170">转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。</span><span class="sxs-lookup"><span data-stu-id="4e178-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="4e178-171">在所有 **域标题** 下，选择 **dns。**</span><span class="sxs-lookup"><span data-stu-id="4e178-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="4e178-172">在 **SRV 记录标题** 下，选择编辑按钮 (扳手图标) 。</span><span class="sxs-lookup"><span data-stu-id="4e178-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="4e178-173">在文本字段中输入以下记录：</span><span class="sxs-lookup"><span data-stu-id="4e178-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="4e178-174">**服务**</span><span class="sxs-lookup"><span data-stu-id="4e178-174">**SERVICE**</span></span>|<span data-ttu-id="4e178-175">**PROTO**</span><span class="sxs-lookup"><span data-stu-id="4e178-175">**PROTO**</span></span>|<span data-ttu-id="4e178-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="4e178-176">**HOST**</span></span>|<span data-ttu-id="4e178-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="4e178-177">**PRI**</span></span>|<span data-ttu-id="4e178-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="4e178-178">**WGT**</span></span>|<span data-ttu-id="4e178-179">**端口**</span><span class="sxs-lookup"><span data-stu-id="4e178-179">**PORT**</span></span>|<span data-ttu-id="4e178-180">**TARGET (必须以"."结尾。)**</span><span class="sxs-lookup"><span data-stu-id="4e178-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="4e178-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4e178-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4e178-182">_sip</span><span class="sxs-lookup"><span data-stu-id="4e178-182">_sip</span></span>  <br/> |<span data-ttu-id="4e178-183">TLS</span><span class="sxs-lookup"><span data-stu-id="4e178-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="4e178-184">100</span><span class="sxs-lookup"><span data-stu-id="4e178-184">100</span></span>  <br/> |<span data-ttu-id="4e178-185">1 </span><span class="sxs-lookup"><span data-stu-id="4e178-185">1</span></span>  <br/> |<span data-ttu-id="4e178-186">443</span><span class="sxs-lookup"><span data-stu-id="4e178-186">443</span></span>  <br/> |<span data-ttu-id="4e178-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4e178-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="4e178-188">1800</span><span class="sxs-lookup"><span data-stu-id="4e178-188">1800</span></span>  <br/> |
    |<span data-ttu-id="4e178-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4e178-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="4e178-190">TCP</span><span class="sxs-lookup"><span data-stu-id="4e178-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="4e178-191">100</span><span class="sxs-lookup"><span data-stu-id="4e178-191">100</span></span>  <br/> |<span data-ttu-id="4e178-192">1 </span><span class="sxs-lookup"><span data-stu-id="4e178-192">1</span></span>  <br/> |<span data-ttu-id="4e178-193">5061</span><span class="sxs-lookup"><span data-stu-id="4e178-193">5061</span></span>  <br/> |<span data-ttu-id="4e178-194">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="4e178-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="4e178-195">1800</span><span class="sxs-lookup"><span data-stu-id="4e178-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="4e178-196">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="4e178-197">检查以确保记录正确，然后选择"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e178-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

