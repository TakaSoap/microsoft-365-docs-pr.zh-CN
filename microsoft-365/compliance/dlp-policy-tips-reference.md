---
title: 数据丢失防护策略提示参考
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解如何向 DLP 策略中的数据丢失防护 (策略) 通知用户他们正在处理与 DLP 策略冲突的内容。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876793"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="e6d0a-103">数据丢失防护策略提示参考</span><span class="sxs-lookup"><span data-stu-id="e6d0a-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="e6d0a-104">Outlook Web Access 中的 DLP 策略提示受 DLP 策略中适用于 Exchange 工作负载的所有条件、例外和操作的支持，以下条件除外：</span><span class="sxs-lookup"><span data-stu-id="e6d0a-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="e6d0a-105">**条件：**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-105">**Conditions:**</span></span>

- <span data-ttu-id="e6d0a-106">发件人是</span><span class="sxs-lookup"><span data-stu-id="e6d0a-106">Sender Is</span></span>
- <span data-ttu-id="e6d0a-107">发件人域为</span><span class="sxs-lookup"><span data-stu-id="e6d0a-107">Sender Domain Is</span></span>
- <span data-ttu-id="e6d0a-108">收件人是</span><span class="sxs-lookup"><span data-stu-id="e6d0a-108">Recipient is a member of</span></span>
- <span data-ttu-id="e6d0a-109">标头包含单词或短语</span><span class="sxs-lookup"><span data-stu-id="e6d0a-109">Header contains words or phrases</span></span>
- <span data-ttu-id="e6d0a-110">标头与模式匹配</span><span class="sxs-lookup"><span data-stu-id="e6d0a-110">Header matches patterns</span></span>
- <span data-ttu-id="e6d0a-111">文档大小等于或大于</span><span class="sxs-lookup"><span data-stu-id="e6d0a-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="e6d0a-112">邮件类型为</span><span class="sxs-lookup"><span data-stu-id="e6d0a-112">Message type is</span></span>
- <span data-ttu-id="e6d0a-113">邮件重要性为</span><span class="sxs-lookup"><span data-stu-id="e6d0a-113">Message importance is</span></span>
- <span data-ttu-id="e6d0a-114">内容字符集包含单词</span><span class="sxs-lookup"><span data-stu-id="e6d0a-114">Content character set contains words</span></span>
- <span data-ttu-id="e6d0a-115">主题或正文包含字词或短语</span><span class="sxs-lookup"><span data-stu-id="e6d0a-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="e6d0a-116">主题或正文与模式匹配</span><span class="sxs-lookup"><span data-stu-id="e6d0a-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="e6d0a-117">内容字符集包含单词</span><span class="sxs-lookup"><span data-stu-id="e6d0a-117">Content character set contains words</span></span>
- <span data-ttu-id="e6d0a-118">内容接收自</span><span class="sxs-lookup"><span data-stu-id="e6d0a-118">Content is received from</span></span>
- <span data-ttu-id="e6d0a-119">使发件人覆盖策略提示</span><span class="sxs-lookup"><span data-stu-id="e6d0a-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="e6d0a-120">邮件大小等于或大于</span><span class="sxs-lookup"><span data-stu-id="e6d0a-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="e6d0a-121">Sender AD 属性包含字词或短语</span><span class="sxs-lookup"><span data-stu-id="e6d0a-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="e6d0a-122">Sender AD 属性与模式匹配</span><span class="sxs-lookup"><span data-stu-id="e6d0a-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="e6d0a-123">文档内容包含字词或短语</span><span class="sxs-lookup"><span data-stu-id="e6d0a-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="e6d0a-124">文档内容与模式匹配</span><span class="sxs-lookup"><span data-stu-id="e6d0a-124">Document content matches patterns</span></span>

<span data-ttu-id="e6d0a-125">**操作：**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-125">**Actions:**</span></span>

- <span data-ttu-id="e6d0a-126">将邮件转发给发件人的经理进行审批</span><span class="sxs-lookup"><span data-stu-id="e6d0a-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="e6d0a-127">将邮件转发给特定审批者进行审批</span><span class="sxs-lookup"><span data-stu-id="e6d0a-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="e6d0a-128">将邮件重定向到特定用户</span><span class="sxs-lookup"><span data-stu-id="e6d0a-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="e6d0a-129">将收件人添加到"收件人"框</span><span class="sxs-lookup"><span data-stu-id="e6d0a-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="e6d0a-130">将收件人添加到抄送框</span><span class="sxs-lookup"><span data-stu-id="e6d0a-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="e6d0a-131">将收件人添加到"Bcc"框</span><span class="sxs-lookup"><span data-stu-id="e6d0a-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="e6d0a-132">将发件人的经理添加为收件人</span><span class="sxs-lookup"><span data-stu-id="e6d0a-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="e6d0a-133">添加 HTML 免责声明</span><span class="sxs-lookup"><span data-stu-id="e6d0a-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="e6d0a-134">预悬电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="e6d0a-134">Prepend email subject</span></span>
- <span data-ttu-id="e6d0a-135">删除 O365 邮件加密和权限保护</span><span class="sxs-lookup"><span data-stu-id="e6d0a-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="e6d0a-136">删除</span><span class="sxs-lookup"><span data-stu-id="e6d0a-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="e6d0a-137">Outlook 2013 及更高版本仅支持显示某些条件和例外的策略提示</span><span class="sxs-lookup"><span data-stu-id="e6d0a-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="e6d0a-138">目前，Outlook 2013 及更高版本支持显示除以下提及的条件和相应例外外不包含任何条件或例外的策略的策略提示：</span><span class="sxs-lookup"><span data-stu-id="e6d0a-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="e6d0a-139">内容 (仅适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="e6d0a-140">不支持敏感度标签) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="e6d0a-141">共享内容</span><span class="sxs-lookup"><span data-stu-id="e6d0a-141">Content is shared</span></span>

<span data-ttu-id="e6d0a-142">请注意，所有条件都适用于在 Outlook 客户端应用中创作的电子邮件，这些条件将匹配内容，并强制对内容执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="e6d0a-143">但是，对于除上述条件之外使用的任何条件，尚不支持向用户显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="e6d0a-144">Outlook 2013 及更高版本仅支持显示某些敏感信息类型的策略提示</span><span class="sxs-lookup"><span data-stu-id="e6d0a-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="e6d0a-145">将为在桌面版 (2013 及更高版本的 Outlook 中显示 DLP 策略提示而检测到的现成敏感信息) 如下：</span><span class="sxs-lookup"><span data-stu-id="e6d0a-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="e6d0a-146">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-146">ABA Routing Number</span></span>
- <span data-ttu-id="e6d0a-147">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="e6d0a-148">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="e6d0a-149">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="e6d0a-150">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-150">Australia Passport Number</span></span>
- <span data-ttu-id="e6d0a-151">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-151">Australia Tax File Number</span></span>
- <span data-ttu-id="e6d0a-152">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="e6d0a-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="e6d0a-153">Azure IAAS 数据库连接字符串和 Azure SQL连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="e6d0a-154">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="e6d0a-155">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="e6d0a-156">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="e6d0a-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="e6d0a-157">Azure SAS</span></span>  
- <span data-ttu-id="e6d0a-158">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="e6d0a-159">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="e6d0a-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="e6d0a-160">Azure 存储帐户密钥 (通用) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="e6d0a-161">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-161">Belgium National Number</span></span>
- <span data-ttu-id="e6d0a-162">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-162">Brazil CPF Number</span></span>
- <span data-ttu-id="e6d0a-163">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="e6d0a-164">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="e6d0a-165">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="e6d0a-166">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="e6d0a-167">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-167">Canada Health Service Number</span></span>
- <span data-ttu-id="e6d0a-168">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-168">Canada Passport Number</span></span>
- <span data-ttu-id="e6d0a-169">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="e6d0a-170">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="e6d0a-171">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="e6d0a-172">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="e6d0a-173">信用卡号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-173">Credit Card Number</span></span>
- <span data-ttu-id="e6d0a-174">克罗地亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="e6d0a-175">克罗地亚个人标识 (OIB) 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="e6d0a-176">捷克个人标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="e6d0a-177">丹麦个人识别号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="e6d0a-178">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="e6d0a-179">欧盟借记卡号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-179">EU Debit Card Number</span></span>
- <span data-ttu-id="e6d0a-180">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="e6d0a-181">欧盟国家标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-181">EU National Identification Number</span></span>  
- <span data-ttu-id="e6d0a-182">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-182">EU Passport Number</span></span>  
- <span data-ttu-id="e6d0a-183">欧盟社会保险号码 (SSN) 或等效 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="e6d0a-184">EU Tax Identification Number (TIN) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="e6d0a-185">芬兰国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-185">Finland National ID</span></span>
- <span data-ttu-id="e6d0a-186">芬兰护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-186">Finland Passport Number</span></span>
- <span data-ttu-id="e6d0a-187">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-187">France Driver's License Number</span></span>
- <span data-ttu-id="e6d0a-188">法国国家/地区身份证 (CNI)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="e6d0a-189">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-189">France Passport Number</span></span>
- <span data-ttu-id="e6d0a-190">法国社会保险号码 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="e6d0a-191">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-191">German Driver's License Number</span></span>
- <span data-ttu-id="e6d0a-192">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-192">German Passport Number</span></span>
- <span data-ttu-id="e6d0a-193">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="e6d0a-194">希腊国民身份证</span><span class="sxs-lookup"><span data-stu-id="e6d0a-194">Greece National ID Card</span></span>  
- <span data-ttu-id="e6d0a-195">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="e6d0a-196">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="e6d0a-197">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="e6d0a-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="e6d0a-198">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="e6d0a-199">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="e6d0a-200">ICD-10-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="e6d0a-201">ICD-9-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="e6d0a-202">IP 地址</span><span class="sxs-lookup"><span data-stu-id="e6d0a-202">IP Address</span></span>
- <span data-ttu-id="e6d0a-203">爱尔兰个人公共服务 (PPS) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="e6d0a-204">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="e6d0a-205">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-205">Israel National ID</span></span>
- <span data-ttu-id="e6d0a-206">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="e6d0a-207">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="e6d0a-208">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="e6d0a-209">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-209">Japan Passport Number</span></span>
- <span data-ttu-id="e6d0a-210">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="e6d0a-211">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="e6d0a-212">日式居民身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="e6d0a-213">马来西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="e6d0a-214">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="e6d0a-215">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="e6d0a-216">挪威标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-216">Norway Identity Number</span></span>  
- <span data-ttu-id="e6d0a-217">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="e6d0a-218">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="e6d0a-218">Poland Identity Card</span></span>
- <span data-ttu-id="e6d0a-219">波兰国家/地区身份证号码 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="e6d0a-220">波兰护照</span><span class="sxs-lookup"><span data-stu-id="e6d0a-220">Poland Passport</span></span>
- <span data-ttu-id="e6d0a-221">葡萄牙公民卡号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="e6d0a-222">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="e6d0a-223">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="e6d0a-224">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="e6d0a-225">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="e6d0a-226">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="e6d0a-227">SQL Server连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="e6d0a-228">瑞典国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-228">Sweden National ID</span></span>
- <span data-ttu-id="e6d0a-229">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-229">Sweden Passport Number</span></span>
- <span data-ttu-id="e6d0a-230">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-230">SWIFT Code</span></span>
- <span data-ttu-id="e6d0a-231">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-231">Taiwan National ID</span></span>
- <span data-ttu-id="e6d0a-232">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="e6d0a-233">台湾居民证书 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="e6d0a-234">泰语总体标识代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="e6d0a-235">土耳其国家身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-235">Turkish National Identification number</span></span>
- <span data-ttu-id="e6d0a-p103">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="e6d0a-p104">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="e6d0a-p105">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="e6d0a-p106">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="e6d0a-244">美国/英国</span><span class="sxs-lookup"><span data-stu-id="e6d0a-244">U.S. / U.K.</span></span> <span data-ttu-id="e6d0a-245">Passport Number</span><span class="sxs-lookup"><span data-stu-id="e6d0a-245">Passport Number</span></span>
- <span data-ttu-id="e6d0a-246">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="e6d0a-247">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="e6d0a-248">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="e6d0a-249">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="e6d0a-250">请注意，除了上述开箱即用敏感信息类型外，DLP 策略提示还支持自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="e6d0a-251">终结点上的数据丢失防护仅支持某些敏感信息类型的策略提示</span><span class="sxs-lookup"><span data-stu-id="e6d0a-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="e6d0a-252">将在驻留在终结点设备上的文档中检测到的现用敏感信息类型列表如下：</span><span class="sxs-lookup"><span data-stu-id="e6d0a-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="e6d0a-253">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-253">ABA Routing Number</span></span> 
- <span data-ttu-id="e6d0a-254">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="e6d0a-255">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="e6d0a-256">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="e6d0a-257">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-257">Australia Passport Number</span></span> 
- <span data-ttu-id="e6d0a-258">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="e6d0a-259">澳大利亚商务号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-259">Australian Business Number</span></span> 
- <span data-ttu-id="e6d0a-260">澳大利亚公司编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-260">Australian Company Number</span></span> 
- <span data-ttu-id="e6d0a-261">奥地利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-262">奥地利身份证</span><span class="sxs-lookup"><span data-stu-id="e6d0a-262">Austria Identity Card</span></span> 
- <span data-ttu-id="e6d0a-263">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-263">Austria Passport Number</span></span> 
- <span data-ttu-id="e6d0a-264">奥地利社会保险号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="e6d0a-265">奥地利税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-266">奥地利增值税 (VAT) 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="e6d0a-267">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="e6d0a-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="e6d0a-268">Azure IAAS 数据库连接字符串和 Azure SQL连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="e6d0a-269">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="e6d0a-270">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="e6d0a-271">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="e6d0a-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="e6d0a-272">Azure SAS</span></span> 
- <span data-ttu-id="e6d0a-273">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="e6d0a-274">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="e6d0a-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="e6d0a-275">Azure 存储帐户密钥 (通用) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="e6d0a-276">比利时驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-277">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-277">Belgium National Number</span></span> 
- <span data-ttu-id="e6d0a-278">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="e6d0a-279">比利时增值税编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="e6d0a-280">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="e6d0a-281">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="e6d0a-282">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="e6d0a-283">保加利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-284">保加利亚护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="e6d0a-285">保加利亚统一编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="e6d0a-286">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="e6d0a-287">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-288">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="e6d0a-289">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-289">Canada Passport Number</span></span> 
- <span data-ttu-id="e6d0a-290">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="e6d0a-291">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="e6d0a-292">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="e6d0a-293">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="e6d0a-294">信用卡号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-294">Credit Card Number</span></span> 
- <span data-ttu-id="e6d0a-295">克罗地亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-296">克罗地亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="e6d0a-297">克罗地亚国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="e6d0a-298">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="e6d0a-299">克罗地亚个人标识 (OIB) 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="e6d0a-300">CSCAN-AZURE0060 Azure 存储帐户共享访问签名</span><span class="sxs-lookup"><span data-stu-id="e6d0a-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="e6d0a-301">CSCAN-GENERAL0140 常规对称密钥</span><span class="sxs-lookup"><span data-stu-id="e6d0a-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="e6d0a-302">塞浦路斯驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-303">塞浦路斯身份证</span><span class="sxs-lookup"><span data-stu-id="e6d0a-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="e6d0a-304">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="e6d0a-305">塞浦路斯税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-306">捷克驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-307">捷克个人标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="e6d0a-308">捷克共和国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="e6d0a-309">丹麦驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-310">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="e6d0a-311">丹麦个人识别号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="e6d0a-312">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="e6d0a-313">爱沙尼亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-314">爱沙尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="e6d0a-315">爱沙尼亚个人标识代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="e6d0a-316">欧盟借记卡号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="e6d0a-317">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-318">欧盟国家标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-318">EU National Identification Number</span></span> 
- <span data-ttu-id="e6d0a-319">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-319">EU Passport Number</span></span> 
- <span data-ttu-id="e6d0a-320">欧盟社会保险号码 (SSN) 或等效 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="e6d0a-321">EU Tax Identification Number (TIN) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="e6d0a-322">芬兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-323">芬兰欧洲健康保险号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="e6d0a-324">芬兰国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-324">Finland National ID</span></span> 
- <span data-ttu-id="e6d0a-325">芬兰护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-325">Finland Passport Number</span></span> 
- <span data-ttu-id="e6d0a-326">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-326">France Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-327">法国健康保险号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="e6d0a-328">法国国家/地区身份证 (CNI)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="e6d0a-329">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-329">France Passport Number</span></span> 
- <span data-ttu-id="e6d0a-330">法国社会保险号码 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="e6d0a-331">numéro SPI. (法国税务标识号) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="e6d0a-332">法国增值税编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="e6d0a-333">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-333">German Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-334">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-334">German Passport Number</span></span> 
- <span data-ttu-id="e6d0a-335">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="e6d0a-336">德国税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-337">德国增值税编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="e6d0a-338">希腊驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-339">希腊国民身份证</span><span class="sxs-lookup"><span data-stu-id="e6d0a-339">Greece National ID Card</span></span> 
- <span data-ttu-id="e6d0a-340">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-340">Greece Passport Number</span></span> 
- <span data-ttu-id="e6d0a-341">希腊社会保险号码 (AMKA) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="e6d0a-342">希腊语税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="e6d0a-343">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="e6d0a-344">匈牙利社会安全号码 (TAJ) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="e6d0a-345">匈牙利语增值税编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="e6d0a-346">匈牙利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-347">匈牙利护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="e6d0a-348">匈牙利个人标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="e6d0a-349">匈牙利税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="e6d0a-350">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="e6d0a-351">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="e6d0a-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="e6d0a-352">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="e6d0a-353">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="e6d0a-354">ICD-10-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="e6d0a-355">ICD-9-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="e6d0a-356">IP 地址</span><span class="sxs-lookup"><span data-stu-id="e6d0a-356">IP Address</span></span> 
- <span data-ttu-id="e6d0a-357">爱尔兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-358">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="e6d0a-359">爱尔兰个人公共服务 (PPS) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="e6d0a-360">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="e6d0a-361">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-361">Israel National ID</span></span> 
- <span data-ttu-id="e6d0a-362">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-363">意大利财政代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="e6d0a-364">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-364">Italy Passport Number</span></span> 
- <span data-ttu-id="e6d0a-365">意大利增值税编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="e6d0a-366">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="e6d0a-367">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-368">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-368">Japan Passport Number</span></span> 
- <span data-ttu-id="e6d0a-369">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="e6d0a-370">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="e6d0a-371">日语 My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="e6d0a-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="e6d0a-372">日语个人编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="e6d0a-373">日式居民身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="e6d0a-374">拉脱维亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-375">拉脱维亚护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="e6d0a-376">拉脱维亚个人代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="e6d0a-377">立陶宛驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-378">立陶宛护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="e6d0a-379">立陶宛个人代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="e6d0a-380">都明达驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-381">阿比塞明卡 (自然人身份证号) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="e6d0a-382">阿比塞卡 (非自然人的身份证号) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="e6d0a-383">百分卡护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="e6d0a-384">马来西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="e6d0a-385">马耳他驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-386">马耳他身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="e6d0a-387">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-387">Malta Passport Number</span></span> 
- <span data-ttu-id="e6d0a-388">马耳他税务 ID 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="e6d0a-389">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="e6d0a-390">荷兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-391">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="e6d0a-392">荷兰税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-393">荷兰增值税编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="e6d0a-394">新西兰银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="e6d0a-395">新西兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="e6d0a-396">新西兰的收入数字</span><span class="sxs-lookup"><span data-stu-id="e6d0a-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="e6d0a-397">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="e6d0a-398">新西兰社会电话号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="e6d0a-399">挪威标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-399">Norway Identity Number</span></span> 
- <span data-ttu-id="e6d0a-400">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="e6d0a-401">波兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-402">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="e6d0a-402">Poland Identity Card</span></span> 
- <span data-ttu-id="e6d0a-403">波兰国家/地区身份证号码 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="e6d0a-404">波兰护照</span><span class="sxs-lookup"><span data-stu-id="e6d0a-404">Poland Passport</span></span> 
- <span data-ttu-id="e6d0a-405">波兰税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-406">波兰语 REGON 号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-406">Polish REGON Number</span></span> 
- <span data-ttu-id="e6d0a-407">葡萄牙公民卡号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="e6d0a-408">葡萄牙驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-409">葡萄牙护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="e6d0a-410">葡萄牙税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-411">罗马尼亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-412">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-412">Romania Passport Number</span></span> 
- <span data-ttu-id="e6d0a-413">罗马尼亚个人数字代码 (CNP) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="e6d0a-414">俄语护照号码 (国内) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="e6d0a-415">俄语护照号码 (国际) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="e6d0a-416">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="e6d0a-417">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="e6d0a-418">斯洛伐克驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-419">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="e6d0a-420">斯洛伐克个人号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="e6d0a-421">斯洛文尼亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-422">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="e6d0a-423">斯洛文尼亚税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-424">斯洛文尼亚唯一主公民编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="e6d0a-425">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="e6d0a-426">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="e6d0a-427">西班牙 DNI</span><span class="sxs-lookup"><span data-stu-id="e6d0a-427">Spain DNI</span></span> 
- <span data-ttu-id="e6d0a-428">西班牙驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-429">西班牙护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-429">Spain Passport Number</span></span> 
- <span data-ttu-id="e6d0a-430">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="e6d0a-431">西班牙税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-432">SQL Server连接字符串</span><span class="sxs-lookup"><span data-stu-id="e6d0a-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="e6d0a-433">瑞典驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-434">瑞典国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-434">Sweden National ID</span></span> 
- <span data-ttu-id="e6d0a-435">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="e6d0a-436">瑞典税务标识号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="e6d0a-437">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-437">SWIFT Code</span></span> 
- <span data-ttu-id="e6d0a-438">瑞士社会保险号 AHV</span><span class="sxs-lookup"><span data-stu-id="e6d0a-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="e6d0a-439">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="e6d0a-439">Taiwan National ID</span></span> 
- <span data-ttu-id="e6d0a-440">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="e6d0a-441">台湾居民证书 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="e6d0a-442">泰语总体标识代码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="e6d0a-443">土耳其国家身份证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="e6d0a-p108">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-p109">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="e6d0a-p110">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="e6d0a-p111">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="e6d0a-452">英国</span><span class="sxs-lookup"><span data-stu-id="e6d0a-452">U.K.</span></span> <span data-ttu-id="e6d0a-453">唯一的纳税参考编号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="e6d0a-454">美国/英国</span><span class="sxs-lookup"><span data-stu-id="e6d0a-454">U.S. / U.K.</span></span> <span data-ttu-id="e6d0a-455">Passport Number</span><span class="sxs-lookup"><span data-stu-id="e6d0a-455">Passport Number</span></span> 
- <span data-ttu-id="e6d0a-456">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="e6d0a-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="e6d0a-457">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="e6d0a-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="e6d0a-458">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="e6d0a-459">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="e6d0a-460">乌克兰护照号码 (国内) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="e6d0a-461">乌克兰护照号码 (国际) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="e6d0a-462">请注意，除了上述开箱即用敏感信息类型之外，还将检测到自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="e6d0a-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="e6d0a-463">Microsoft 应用中 DLP 策略提示的支持矩阵</span><span class="sxs-lookup"><span data-stu-id="e6d0a-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="e6d0a-464">**应用和平台**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-464">**App and platform**</span></span>|<span data-ttu-id="e6d0a-465">**DLP 策略提示支持**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-465">**DLP policy tip support**</span></span>|<span data-ttu-id="e6d0a-466">**支持的敏感信息类型**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="e6d0a-467">**支持的谓词和操作**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="e6d0a-468">**备注**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="e6d0a-469">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="e6d0a-470">全部</span><span class="sxs-lookup"><span data-stu-id="e6d0a-470">All</span></span>|<span data-ttu-id="e6d0a-471">Subset</span><span class="sxs-lookup"><span data-stu-id="e6d0a-471">Subset</span></span>|<span data-ttu-id="e6d0a-472">请参阅 [数据丢失防护策略提示参考](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="e6d0a-473">**Outlook Win32 (Outlook 2013 及)**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="e6d0a-474">Subset</span><span class="sxs-lookup"><span data-stu-id="e6d0a-474">Subset</span></span>|<span data-ttu-id="e6d0a-475">Subset</span><span class="sxs-lookup"><span data-stu-id="e6d0a-475">Subset</span></span>|<span data-ttu-id="e6d0a-476">请参阅 [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) 及更高版本仅支持显示某些条件和例外的策略提示 [，Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) 及更高版本仅支持显示某些敏感信息类型的策略提示，了解有关支持敏感信息类型和 DLP 条件以及支持在 Outlook Win32 上显示 DLP 策略提示的操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="e6d0a-477">**Outlook Mobile (iOS、Android) /Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="e6d0a-478">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-478">None</span></span>|<span data-ttu-id="e6d0a-479">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-479">None</span></span>|<span data-ttu-id="e6d0a-480">Outlook 移动版不支持 DLP 策略提示</span><span class="sxs-lookup"><span data-stu-id="e6d0a-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="e6d0a-481">**Sharepoint Online/One Drive for Business Web 客户端**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="e6d0a-482">全部</span><span class="sxs-lookup"><span data-stu-id="e6d0a-482">All</span></span>|<span data-ttu-id="e6d0a-483">DLP 中所有 SPO/ODB 谓词和操作</span><span class="sxs-lookup"><span data-stu-id="e6d0a-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="e6d0a-484">**Sharepoint Win32/ One Drive for Business Win32 客户端**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="e6d0a-485">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-485">None</span></span>|<span data-ttu-id="e6d0a-486">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-486">None</span></span>|<span data-ttu-id="e6d0a-487">Sharepoint 或 OneDrive 桌面客户端应用不支持 DLP 策略提示</span><span class="sxs-lookup"><span data-stu-id="e6d0a-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="e6d0a-488">**Word、Excel、Powerpoint Web 客户端**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="e6d0a-489">全部</span><span class="sxs-lookup"><span data-stu-id="e6d0a-489">All</span></span>|<span data-ttu-id="e6d0a-490">DLP 中所有 SPO/ODB 谓词和操作</span><span class="sxs-lookup"><span data-stu-id="e6d0a-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="e6d0a-491">如果文档托管在 SPO 或 ODB Web 应用上并且已标记 DLP 策略，则支持 DLP 策略提示。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="e6d0a-492">**Word、Excel、Powerpoint Mobile 客户端**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="e6d0a-493">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-493">None</span></span>|<span data-ttu-id="e6d0a-494">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-494">None</span></span>|<span data-ttu-id="e6d0a-495">Dlp 策略提示在 Office 移动应用程序中不受支持。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="e6d0a-496">**Teams Web/Teams 桌面版/Teams 移动版/Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="e6d0a-497">全部</span><span class="sxs-lookup"><span data-stu-id="e6d0a-497">All</span></span>|<span data-ttu-id="e6d0a-498">DLP 策略中所有 Teams 谓词</span><span class="sxs-lookup"><span data-stu-id="e6d0a-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="e6d0a-499">当邮件被标记为"此邮件已标记"时，将显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="e6d0a-500">我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="e6d0a-500">What can I do?”</span></span> <span data-ttu-id="e6d0a-501">单击链接时，用户可以查看检测到的敏感信息类型，并覆盖或报告问题（如果管理员允许）。请注意，不会为文件显示任何策略提示。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="e6d0a-502">当收件人尝试访问文档时，如果不允许，他们可能会被拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="e6d0a-503">**Win32 终结点设备**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="e6d0a-504">Subset</span><span class="sxs-lookup"><span data-stu-id="e6d0a-504">Subset</span></span>|<span data-ttu-id="e6d0a-505">DLP 策略中所有终结点 DLP 谓词和操作</span><span class="sxs-lookup"><span data-stu-id="e6d0a-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="e6d0a-506">请参阅 [Endpoint 上的数据丢失防护仅支持某些敏感信息类型的策略提示](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="e6d0a-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="e6d0a-507">**Mac 设备**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="e6d0a-508">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-508">None</span></span>|<span data-ttu-id="e6d0a-509">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-509">None</span></span>|<span data-ttu-id="e6d0a-510">现在，Mac 设备上无法实施数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="e6d0a-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="e6d0a-511">**第三方云应用**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="e6d0a-512">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-512">None</span></span>|<span data-ttu-id="e6d0a-513">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-513">None</span></span>|<span data-ttu-id="e6d0a-514">数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="e6d0a-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="e6d0a-515">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="e6d0a-516">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-516">None</span></span>|<span data-ttu-id="e6d0a-517">无</span><span class="sxs-lookup"><span data-stu-id="e6d0a-517">None</span></span>||
|<span data-ttu-id="e6d0a-518">**Word、Excel、Powerpoint Win32 客户端**</span><span class="sxs-lookup"><span data-stu-id="e6d0a-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="e6d0a-519">Subset</span><span class="sxs-lookup"><span data-stu-id="e6d0a-519">Subset</span></span>|<span data-ttu-id="e6d0a-520">Subset</span><span class="sxs-lookup"><span data-stu-id="e6d0a-520">Subset</span></span>|<span data-ttu-id="e6d0a-521">WXP 客户端应用的策略提示适用于存储在 Sharepoint Online 或 One Drive for Business 网站中的文档，适用于 DLP 策略中条件或操作完全相同的所有 DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="e6d0a-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="e6d0a-522">内容包含敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="e6d0a-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="e6d0a-523">访问 (内容在内部/外部共享) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="e6d0a-524">通知用户 (策略提示/用户通知) </span><span class="sxs-lookup"><span data-stu-id="e6d0a-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="e6d0a-525">阻止所有人</span><span class="sxs-lookup"><span data-stu-id="e6d0a-525">Block everyone</span></span></li><li><span data-ttu-id="e6d0a-526">事件报告</span><span class="sxs-lookup"><span data-stu-id="e6d0a-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="e6d0a-527">如果存在任何其他条件或操作，该策略的 DLP 策略提示将不会显示在 Word、Excel 或 PowerPoint 的桌面应用程序中。</span><span class="sxs-lookup"><span data-stu-id="e6d0a-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||