---
title: 数据丢失防护策略提示参考
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: 了解如何向 DLP 策略中的数据丢失防护 (策略) 通知用户他们正在处理与 DLP 策略冲突的内容。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 0c42569da3fcac40d3121a59f7dc004f25dd3f74
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086755"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="a60d4-103">数据丢失防护策略提示参考</span><span class="sxs-lookup"><span data-stu-id="a60d4-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="a60d4-104">对于适用于 DLP 策略Outlook工作负荷的所有条件、例外和操作，Exchange Web Access 中的 DLP 策略提示除外：</span><span class="sxs-lookup"><span data-stu-id="a60d4-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="a60d4-105">**条件：**</span><span class="sxs-lookup"><span data-stu-id="a60d4-105">**Conditions:**</span></span>

- <span data-ttu-id="a60d4-106">发件人是</span><span class="sxs-lookup"><span data-stu-id="a60d4-106">Sender Is</span></span>
- <span data-ttu-id="a60d4-107">发件人域为</span><span class="sxs-lookup"><span data-stu-id="a60d4-107">Sender Domain Is</span></span>
- <span data-ttu-id="a60d4-108">收件人是</span><span class="sxs-lookup"><span data-stu-id="a60d4-108">Recipient is a member of</span></span>
- <span data-ttu-id="a60d4-109">标头包含单词或短语</span><span class="sxs-lookup"><span data-stu-id="a60d4-109">Header contains words or phrases</span></span>
- <span data-ttu-id="a60d4-110">标头与模式匹配</span><span class="sxs-lookup"><span data-stu-id="a60d4-110">Header matches patterns</span></span>
- <span data-ttu-id="a60d4-111">文档大小等于或大于</span><span class="sxs-lookup"><span data-stu-id="a60d4-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="a60d4-112">邮件类型为</span><span class="sxs-lookup"><span data-stu-id="a60d4-112">Message type is</span></span>
- <span data-ttu-id="a60d4-113">邮件重要性为</span><span class="sxs-lookup"><span data-stu-id="a60d4-113">Message importance is</span></span>
- <span data-ttu-id="a60d4-114">内容字符集包含单词</span><span class="sxs-lookup"><span data-stu-id="a60d4-114">Content character set contains words</span></span>
- <span data-ttu-id="a60d4-115">主题或正文包含字词或短语</span><span class="sxs-lookup"><span data-stu-id="a60d4-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="a60d4-116">主题或正文与模式匹配</span><span class="sxs-lookup"><span data-stu-id="a60d4-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="a60d4-117">内容字符集包含单词</span><span class="sxs-lookup"><span data-stu-id="a60d4-117">Content character set contains words</span></span>
- <span data-ttu-id="a60d4-118">内容接收自</span><span class="sxs-lookup"><span data-stu-id="a60d4-118">Content is received from</span></span>
- <span data-ttu-id="a60d4-119">使发件人覆盖策略提示</span><span class="sxs-lookup"><span data-stu-id="a60d4-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="a60d4-120">邮件大小等于或大于</span><span class="sxs-lookup"><span data-stu-id="a60d4-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="a60d4-121">Sender AD 属性包含字词或短语</span><span class="sxs-lookup"><span data-stu-id="a60d4-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="a60d4-122">Sender AD 属性与模式匹配</span><span class="sxs-lookup"><span data-stu-id="a60d4-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="a60d4-123">文档内容包含字词或短语</span><span class="sxs-lookup"><span data-stu-id="a60d4-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="a60d4-124">文档内容与模式匹配</span><span class="sxs-lookup"><span data-stu-id="a60d4-124">Document content matches patterns</span></span>

<span data-ttu-id="a60d4-125">**操作：**</span><span class="sxs-lookup"><span data-stu-id="a60d4-125">**Actions:**</span></span>

- <span data-ttu-id="a60d4-126">将邮件转发给发件人的经理进行审批</span><span class="sxs-lookup"><span data-stu-id="a60d4-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="a60d4-127">将邮件转发给特定审批者进行审批</span><span class="sxs-lookup"><span data-stu-id="a60d4-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="a60d4-128">将邮件重定向到特定用户</span><span class="sxs-lookup"><span data-stu-id="a60d4-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="a60d4-129">将收件人添加到"收件人"框</span><span class="sxs-lookup"><span data-stu-id="a60d4-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="a60d4-130">将收件人添加到抄送框</span><span class="sxs-lookup"><span data-stu-id="a60d4-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="a60d4-131">将收件人添加到"Bcc"框</span><span class="sxs-lookup"><span data-stu-id="a60d4-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="a60d4-132">将发件人的经理添加为收件人</span><span class="sxs-lookup"><span data-stu-id="a60d4-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="a60d4-133">添加 HTML 免责声明</span><span class="sxs-lookup"><span data-stu-id="a60d4-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="a60d4-134">预悬电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="a60d4-134">Prepend email subject</span></span>
- <span data-ttu-id="a60d4-135">删除 O365 邮件加密和权限保护</span><span class="sxs-lookup"><span data-stu-id="a60d4-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="a60d4-136">Outlook 2013 及更高版本仅支持显示某些条件和例外的策略提示</span><span class="sxs-lookup"><span data-stu-id="a60d4-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="a60d4-137">目前，Outlook 2013 及更高版本支持显示策略策略提示，这些策略不包含以下提及的条件和相应例外之外的任何条件或例外：</span><span class="sxs-lookup"><span data-stu-id="a60d4-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="a60d4-138">内容 (仅适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a60d4-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="a60d4-139">不支持敏感度标签) </span><span class="sxs-lookup"><span data-stu-id="a60d4-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="a60d4-140">共享内容</span><span class="sxs-lookup"><span data-stu-id="a60d4-140">Content is shared</span></span>

<span data-ttu-id="a60d4-141">请注意，所有条件都适用于在客户端应用中Outlook的电子邮件，这些条件将匹配内容，并强制对内容执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="a60d4-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="a60d4-142">但是，对于除上述条件之外使用的任何条件，都不支持向用户显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="a60d4-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="a60d4-143">Outlook 2013 及更高版本Office桌面应用支持仅显示某些敏感信息类型的策略提示</span><span class="sxs-lookup"><span data-stu-id="a60d4-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="a60d4-144">将为在桌面版 (2013 及更高版本的 Outlook 和更高版本的) 和 Office 应用（桌面版 (上的 Word、Excel、PowerPoint) ）中显示 DLP 策略提示而检测到的现成敏感信息类型列表如下：</span><span class="sxs-lookup"><span data-stu-id="a60d4-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="a60d4-145">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="a60d4-145">ABA Routing Number</span></span>
- <span data-ttu-id="a60d4-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="a60d4-147">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="a60d4-148">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="a60d4-149">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="a60d4-149">Australia Passport Number</span></span>
- <span data-ttu-id="a60d4-150">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="a60d4-150">Australia Tax File Number</span></span>
- <span data-ttu-id="a60d4-151">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="a60d4-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="a60d4-152">Azure IAAS 数据库连接字符串和 Azure SQL连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="a60d4-153">Azure IoT连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="a60d4-154">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="a60d4-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="a60d4-155">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="a60d4-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="a60d4-156">Azure SAS</span></span>  
- <span data-ttu-id="a60d4-157">Azure 服务总线 连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="a60d4-158">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="a60d4-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="a60d4-159">Azure 存储帐户密钥 (通用) </span><span class="sxs-lookup"><span data-stu-id="a60d4-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="a60d4-160">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-160">Belgium National Number</span></span>
- <span data-ttu-id="a60d4-161">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-161">Brazil CPF Number</span></span>
- <span data-ttu-id="a60d4-162">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="a60d4-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="a60d4-163">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="a60d4-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="a60d4-164">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="a60d4-165">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="a60d4-166">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="a60d4-166">Canada Health Service Number</span></span>
- <span data-ttu-id="a60d4-167">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-167">Canada Passport Number</span></span>
- <span data-ttu-id="a60d4-168">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="a60d4-169">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="a60d4-170">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="a60d4-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="a60d4-171">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="a60d4-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="a60d4-172">信用卡号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-172">Credit Card Number</span></span>
- <span data-ttu-id="a60d4-173">克罗地亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="a60d4-174">克罗地亚个人标识 (OIB) 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="a60d4-175">捷克个人标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="a60d4-176">丹麦个人识别号</span><span class="sxs-lookup"><span data-stu-id="a60d4-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="a60d4-177">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="a60d4-178">欧盟借记卡号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-178">EU Debit Card Number</span></span>
- <span data-ttu-id="a60d4-179">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="a60d4-180">欧盟国家标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-180">EU National Identification Number</span></span>  
- <span data-ttu-id="a60d4-181">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-181">EU Passport Number</span></span>  
- <span data-ttu-id="a60d4-182">欧盟社会保险号码 (SSN) 或等效 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="a60d4-183">EU Tax Identification Number (TIN) </span><span class="sxs-lookup"><span data-stu-id="a60d4-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="a60d4-184">芬兰国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-184">Finland National ID</span></span>
- <span data-ttu-id="a60d4-185">芬兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-185">Finland Passport Number</span></span>
- <span data-ttu-id="a60d4-186">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-186">France Driver's License Number</span></span>
- <span data-ttu-id="a60d4-187">法国国家/地区身份证 (CNI)</span><span class="sxs-lookup"><span data-stu-id="a60d4-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="a60d4-188">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-188">France Passport Number</span></span>
- <span data-ttu-id="a60d4-189">法国社会保险号码 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a60d4-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="a60d4-190">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-190">German Driver's License Number</span></span>
- <span data-ttu-id="a60d4-191">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-191">German Passport Number</span></span>
- <span data-ttu-id="a60d4-192">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="a60d4-193">希腊国民身份证</span><span class="sxs-lookup"><span data-stu-id="a60d4-193">Greece National ID Card</span></span>  
- <span data-ttu-id="a60d4-194">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="a60d4-195">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="a60d4-196">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="a60d4-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="a60d4-197">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="a60d4-198">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="a60d4-199">ICD-10-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="a60d4-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="a60d4-200">ICD-9-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="a60d4-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="a60d4-201">IP 地址</span><span class="sxs-lookup"><span data-stu-id="a60d4-201">IP Address</span></span>
- <span data-ttu-id="a60d4-202">爱尔兰个人公共服务 (PPS) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="a60d4-203">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="a60d4-204">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-204">Israel National ID</span></span>
- <span data-ttu-id="a60d4-205">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="a60d4-206">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="a60d4-207">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="a60d4-208">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-208">Japan Passport Number</span></span>
- <span data-ttu-id="a60d4-209">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="a60d4-210">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="a60d4-211">日式居民身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="a60d4-212">马来西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="a60d4-213">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="a60d4-214">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="a60d4-215">挪威标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-215">Norway Identity Number</span></span>  
- <span data-ttu-id="a60d4-216">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="a60d4-217">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="a60d4-217">Poland Identity Card</span></span>
- <span data-ttu-id="a60d4-218">波兰国家/地区身份证号码 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a60d4-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="a60d4-219">波兰护照</span><span class="sxs-lookup"><span data-stu-id="a60d4-219">Poland Passport</span></span>
- <span data-ttu-id="a60d4-220">葡萄牙公民卡号</span><span class="sxs-lookup"><span data-stu-id="a60d4-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="a60d4-221">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="a60d4-222">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="a60d4-223">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="a60d4-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="a60d4-224">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="a60d4-225">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="a60d4-226">SQL Server连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="a60d4-227">瑞典国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-227">Sweden National ID</span></span>
- <span data-ttu-id="a60d4-228">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-228">Sweden Passport Number</span></span>
- <span data-ttu-id="a60d4-229">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-229">SWIFT Code</span></span>
- <span data-ttu-id="a60d4-230">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-230">Taiwan National ID</span></span>
- <span data-ttu-id="a60d4-231">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="a60d4-232">台湾居民证书 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="a60d4-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="a60d4-233">泰语总体标识代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="a60d4-234">土耳其国家身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-234">Turkish National Identification number</span></span>
- <span data-ttu-id="a60d4-p103">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="a60d4-p104">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="a60d4-p105">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="a60d4-p106">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="a60d4-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="a60d4-p107">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p107">U.S. / U.K. Passport Number</span></span>
- <span data-ttu-id="a60d4-245">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="a60d4-246">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="a60d4-247">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="a60d4-248">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="a60d4-249">请注意，除了上述开箱即用敏感信息类型外，DLP 策略提示还支持自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a60d4-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="a60d4-250">终结点设备上数据丢失防护仅支持某些敏感信息类型的策略提示</span><span class="sxs-lookup"><span data-stu-id="a60d4-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="a60d4-251">将在驻留在终结点设备上的文档中检测到的现用敏感信息类型列表如下：</span><span class="sxs-lookup"><span data-stu-id="a60d4-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="a60d4-252">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="a60d4-252">ABA Routing Number</span></span> 
- <span data-ttu-id="a60d4-253">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="a60d4-254">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="a60d4-255">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="a60d4-256">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="a60d4-256">Australia Passport Number</span></span> 
- <span data-ttu-id="a60d4-257">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="a60d4-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="a60d4-258">澳大利亚商务号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-258">Australian Business Number</span></span> 
- <span data-ttu-id="a60d4-259">澳大利亚公司编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-259">Australian Company Number</span></span> 
- <span data-ttu-id="a60d4-260">奥地利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-261">奥地利身份证</span><span class="sxs-lookup"><span data-stu-id="a60d4-261">Austria Identity Card</span></span> 
- <span data-ttu-id="a60d4-262">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-262">Austria Passport Number</span></span> 
- <span data-ttu-id="a60d4-263">奥地利社会保险号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="a60d4-264">奥地利税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-265">奥地利增值税 (VAT) 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="a60d4-266">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="a60d4-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="a60d4-267">Azure IAAS 数据库连接字符串和 Azure SQL连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="a60d4-268">Azure IoT连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="a60d4-269">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="a60d4-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="a60d4-270">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="a60d4-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="a60d4-271">Azure SAS</span></span> 
- <span data-ttu-id="a60d4-272">Azure 服务总线 连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="a60d4-273">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="a60d4-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="a60d4-274">Azure 存储帐户密钥 (通用) </span><span class="sxs-lookup"><span data-stu-id="a60d4-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="a60d4-275">比利时驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-276">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-276">Belgium National Number</span></span> 
- <span data-ttu-id="a60d4-277">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="a60d4-278">比利时增值税编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="a60d4-279">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="a60d4-280">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="a60d4-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="a60d4-281">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="a60d4-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="a60d4-282">保加利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-283">保加利亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="a60d4-284">保加利亚统一编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="a60d4-285">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="a60d4-286">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-287">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="a60d4-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="a60d4-288">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-288">Canada Passport Number</span></span> 
- <span data-ttu-id="a60d4-289">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="a60d4-290">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="a60d4-291">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="a60d4-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="a60d4-292">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="a60d4-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="a60d4-293">信用卡号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-293">Credit Card Number</span></span> 
- <span data-ttu-id="a60d4-294">克罗地亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-295">克罗地亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="a60d4-296">克罗地亚国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="a60d4-297">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="a60d4-298">克罗地亚个人标识 (OIB) 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="a60d4-299">CSCAN-AZURE0060 Azure 存储帐户共享访问签名</span><span class="sxs-lookup"><span data-stu-id="a60d4-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="a60d4-300">CSCAN-GENERAL0140 常规对称密钥</span><span class="sxs-lookup"><span data-stu-id="a60d4-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="a60d4-301">塞浦路斯驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-302">塞浦路斯身份证</span><span class="sxs-lookup"><span data-stu-id="a60d4-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="a60d4-303">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="a60d4-304">塞浦路斯税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-305">捷克驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-306">捷克个人标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="a60d4-307">捷克共和国护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="a60d4-308">丹麦驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-309">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="a60d4-310">丹麦个人识别号</span><span class="sxs-lookup"><span data-stu-id="a60d4-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="a60d4-311">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="a60d4-312">爱沙尼亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-313">爱沙尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="a60d4-314">爱沙尼亚个人标识代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="a60d4-315">欧盟借记卡号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="a60d4-316">欧盟驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-317">欧盟国家标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-317">EU National Identification Number</span></span> 
- <span data-ttu-id="a60d4-318">欧盟护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-318">EU Passport Number</span></span> 
- <span data-ttu-id="a60d4-319">欧盟社会保险号码 (SSN) 或等效 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="a60d4-320">EU Tax Identification Number (TIN) </span><span class="sxs-lookup"><span data-stu-id="a60d4-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="a60d4-321">芬兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-322">芬兰欧洲健康保险号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="a60d4-323">芬兰国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-323">Finland National ID</span></span> 
- <span data-ttu-id="a60d4-324">芬兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-324">Finland Passport Number</span></span> 
- <span data-ttu-id="a60d4-325">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-325">France Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-326">法国健康保险号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="a60d4-327">法国国家/地区身份证 (CNI)</span><span class="sxs-lookup"><span data-stu-id="a60d4-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="a60d4-328">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-328">France Passport Number</span></span> 
- <span data-ttu-id="a60d4-329">法国社会保险号码 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a60d4-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="a60d4-330">numéro SPI. (法国税务标识号) </span><span class="sxs-lookup"><span data-stu-id="a60d4-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="a60d4-331">法国增值税编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="a60d4-332">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-332">German Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-333">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-333">German Passport Number</span></span> 
- <span data-ttu-id="a60d4-334">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="a60d4-335">德国税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-336">德国增值税编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="a60d4-337">希腊驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-338">希腊国民身份证</span><span class="sxs-lookup"><span data-stu-id="a60d4-338">Greece National ID Card</span></span> 
- <span data-ttu-id="a60d4-339">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-339">Greece Passport Number</span></span> 
- <span data-ttu-id="a60d4-340">希腊社会保险号码 (AMKA) </span><span class="sxs-lookup"><span data-stu-id="a60d4-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="a60d4-341">希腊语税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="a60d4-342">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="a60d4-343">匈牙利社会安全号码 (TAJ) </span><span class="sxs-lookup"><span data-stu-id="a60d4-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="a60d4-344">匈牙利语增值税编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="a60d4-345">匈牙利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-346">匈牙利护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="a60d4-347">匈牙利个人标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="a60d4-348">匈牙利税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="a60d4-349">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="a60d4-350">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="a60d4-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="a60d4-351">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="a60d4-352">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="a60d4-353">ICD-10-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="a60d4-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="a60d4-354">ICD-9-CM (国际) </span><span class="sxs-lookup"><span data-stu-id="a60d4-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="a60d4-355">IP 地址</span><span class="sxs-lookup"><span data-stu-id="a60d4-355">IP Address</span></span> 
- <span data-ttu-id="a60d4-356">爱尔兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-357">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="a60d4-358">爱尔兰个人公共服务 (PPS) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="a60d4-359">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="a60d4-360">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-360">Israel National ID</span></span> 
- <span data-ttu-id="a60d4-361">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-362">意大利财政代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="a60d4-363">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-363">Italy Passport Number</span></span> 
- <span data-ttu-id="a60d4-364">意大利增值税编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="a60d4-365">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="a60d4-366">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-367">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-367">Japan Passport Number</span></span> 
- <span data-ttu-id="a60d4-368">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="a60d4-369">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="a60d4-370">日语 My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="a60d4-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="a60d4-371">日语个人编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="a60d4-372">日式居民身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="a60d4-373">拉脱维亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-374">拉脱维亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="a60d4-375">拉脱维亚个人代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="a60d4-376">立陶宛驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-377">立陶宛护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="a60d4-378">立陶宛个人代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="a60d4-379">都明达驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-380">阿比塞明卡 (自然人身份证号) </span><span class="sxs-lookup"><span data-stu-id="a60d4-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="a60d4-381">阿比塞卡 (非自然人的身份证号) </span><span class="sxs-lookup"><span data-stu-id="a60d4-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="a60d4-382">百分卡护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="a60d4-383">马来西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="a60d4-384">马耳他驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-385">马耳他身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="a60d4-386">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-386">Malta Passport Number</span></span> 
- <span data-ttu-id="a60d4-387">马耳他税务 ID 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="a60d4-388">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="a60d4-389">荷兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-390">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="a60d4-391">荷兰税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-392">荷兰增值税编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="a60d4-393">新西兰银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="a60d4-394">新西兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="a60d4-395">新西兰的收入数字</span><span class="sxs-lookup"><span data-stu-id="a60d4-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="a60d4-396">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="a60d4-397">新西兰社会电话号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="a60d4-398">挪威标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-398">Norway Identity Number</span></span> 
- <span data-ttu-id="a60d4-399">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="a60d4-400">波兰驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-401">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="a60d4-401">Poland Identity Card</span></span> 
- <span data-ttu-id="a60d4-402">波兰国家/地区身份证号码 (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a60d4-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="a60d4-403">波兰护照</span><span class="sxs-lookup"><span data-stu-id="a60d4-403">Poland Passport</span></span> 
- <span data-ttu-id="a60d4-404">波兰税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-405">波兰语 REGON 号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-405">Polish REGON Number</span></span> 
- <span data-ttu-id="a60d4-406">葡萄牙公民卡号</span><span class="sxs-lookup"><span data-stu-id="a60d4-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="a60d4-407">葡萄牙驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-408">葡萄牙护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="a60d4-409">葡萄牙税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-410">罗马尼亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-411">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-411">Romania Passport Number</span></span> 
- <span data-ttu-id="a60d4-412">罗马尼亚个人数字代码 (CNP) </span><span class="sxs-lookup"><span data-stu-id="a60d4-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="a60d4-413">俄语护照号码 (国内) </span><span class="sxs-lookup"><span data-stu-id="a60d4-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="a60d4-414">俄语护照号码 (国际) </span><span class="sxs-lookup"><span data-stu-id="a60d4-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="a60d4-415">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="a60d4-416">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="a60d4-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="a60d4-417">斯洛伐克驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-418">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="a60d4-419">斯洛伐克个人号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="a60d4-420">斯洛文尼亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-421">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="a60d4-422">斯洛文尼亚税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-423">斯洛文尼亚唯一主公民编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="a60d4-424">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="a60d4-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="a60d4-425">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="a60d4-426">西班牙 DNI</span><span class="sxs-lookup"><span data-stu-id="a60d4-426">Spain DNI</span></span> 
- <span data-ttu-id="a60d4-427">西班牙驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-428">西班牙护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-428">Spain Passport Number</span></span> 
- <span data-ttu-id="a60d4-429">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="a60d4-430">西班牙税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-431">SQL Server连接字符串</span><span class="sxs-lookup"><span data-stu-id="a60d4-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="a60d4-432">瑞典驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-433">瑞典国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-433">Sweden National ID</span></span> 
- <span data-ttu-id="a60d4-434">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="a60d4-435">瑞典税务标识号</span><span class="sxs-lookup"><span data-stu-id="a60d4-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="a60d4-436">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-436">SWIFT Code</span></span> 
- <span data-ttu-id="a60d4-437">瑞士社会保险号 AHV</span><span class="sxs-lookup"><span data-stu-id="a60d4-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="a60d4-438">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="a60d4-438">Taiwan National ID</span></span> 
- <span data-ttu-id="a60d4-439">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="a60d4-440">台湾居民证书 (ARC/TARC) </span><span class="sxs-lookup"><span data-stu-id="a60d4-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="a60d4-441">泰语总体标识代码</span><span class="sxs-lookup"><span data-stu-id="a60d4-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="a60d4-442">土耳其国家身份证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="a60d4-p108">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-p109">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="a60d4-p110">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="a60d4-p111">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="a60d4-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="a60d4-451">英国</span><span class="sxs-lookup"><span data-stu-id="a60d4-451">U.K.</span></span> <span data-ttu-id="a60d4-452">唯一的纳税参考编号</span><span class="sxs-lookup"><span data-stu-id="a60d4-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="a60d4-p113">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-p113">U.S. / U.K. Passport Number</span></span> 
- <span data-ttu-id="a60d4-455">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="a60d4-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="a60d4-456">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="a60d4-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="a60d4-457">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="a60d4-458">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a60d4-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="a60d4-459">乌克兰护照号码 (国内) </span><span class="sxs-lookup"><span data-stu-id="a60d4-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="a60d4-460">乌克兰护照号码 (国际) </span><span class="sxs-lookup"><span data-stu-id="a60d4-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="a60d4-461">请注意，除了上述开箱即用敏感信息类型之外，还将检测到自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a60d4-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="a60d4-462">Microsoft 应用中 DLP 策略提示的支持矩阵</span><span class="sxs-lookup"><span data-stu-id="a60d4-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="a60d4-463">**应用和平台**</span><span class="sxs-lookup"><span data-stu-id="a60d4-463">**App and platform**</span></span>|<span data-ttu-id="a60d4-464">**DLP 策略提示支持**</span><span class="sxs-lookup"><span data-stu-id="a60d4-464">**DLP policy tip support**</span></span>|<span data-ttu-id="a60d4-465">**支持的敏感信息类型**</span><span class="sxs-lookup"><span data-stu-id="a60d4-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="a60d4-466">**支持的谓词和操作**</span><span class="sxs-lookup"><span data-stu-id="a60d4-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="a60d4-467">**备注**</span><span class="sxs-lookup"><span data-stu-id="a60d4-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="a60d4-468">**OutlookWeb Access**</span><span class="sxs-lookup"><span data-stu-id="a60d4-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a60d4-469">全部</span><span class="sxs-lookup"><span data-stu-id="a60d4-469">All</span></span>|<span data-ttu-id="a60d4-470">Subset</span><span class="sxs-lookup"><span data-stu-id="a60d4-470">Subset</span></span>|<span data-ttu-id="a60d4-471">请参阅 [数据丢失防护策略提示参考](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="a60d4-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="a60d4-472">**OutlookWin32 (Outlook 2013 及)**</span><span class="sxs-lookup"><span data-stu-id="a60d4-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a60d4-473">Subset</span><span class="sxs-lookup"><span data-stu-id="a60d4-473">Subset</span></span>|<span data-ttu-id="a60d4-474">Subset</span><span class="sxs-lookup"><span data-stu-id="a60d4-474">Subset</span></span>|<span data-ttu-id="a60d4-475">请参阅[Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions)及更高版本仅支持显示某些条件和例外的策略提示，并且桌面版上的[Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)及更高版本和 Office 应用支持显示仅某些敏感信息类型的策略提示，了解有关支持敏感信息类型和 DLP 条件以及支持在 Outlook Win32 上显示 DLP 策略提示的操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a60d4-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="a60d4-476">**Outlook移动 (iOS、Android) /Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="a60d4-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a60d4-477">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-477">None</span></span>|<span data-ttu-id="a60d4-478">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-478">None</span></span>|<span data-ttu-id="a60d4-479">DLP 策略提示在移动版上Outlook支持</span><span class="sxs-lookup"><span data-stu-id="a60d4-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="a60d4-480">**Sharepoint Online/One Drive for Business Web 客户端**</span><span class="sxs-lookup"><span data-stu-id="a60d4-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a60d4-481">全部</span><span class="sxs-lookup"><span data-stu-id="a60d4-481">All</span></span>|<span data-ttu-id="a60d4-482">DLP 中所有 SPO/ODB 谓词和操作</span><span class="sxs-lookup"><span data-stu-id="a60d4-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="a60d4-483">**Sharepoint Win32/ One Drive for Business Win32 客户端**</span><span class="sxs-lookup"><span data-stu-id="a60d4-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a60d4-484">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-484">None</span></span>|<span data-ttu-id="a60d4-485">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-485">None</span></span>|<span data-ttu-id="a60d4-486">Sharepoint 或桌面客户端应用程序不支持 DLP OneDrive提示</span><span class="sxs-lookup"><span data-stu-id="a60d4-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="a60d4-487">**Word、Excel、PowerPoint Web 客户端**</span><span class="sxs-lookup"><span data-stu-id="a60d4-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a60d4-488">全部</span><span class="sxs-lookup"><span data-stu-id="a60d4-488">All</span></span>|<span data-ttu-id="a60d4-489">DLP 中所有 SPO/ODB 谓词和操作</span><span class="sxs-lookup"><span data-stu-id="a60d4-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="a60d4-490">如果文档托管在 SPO 或 ODB Web 应用上并且已标记 DLP 策略，则支持 DLP 策略提示。</span><span class="sxs-lookup"><span data-stu-id="a60d4-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="a60d4-491">**Word、Excel、PowerPoint Mobile 客户端**</span><span class="sxs-lookup"><span data-stu-id="a60d4-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a60d4-492">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-492">None</span></span>|<span data-ttu-id="a60d4-493">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-493">None</span></span>|<span data-ttu-id="a60d4-494">DLP 策略提示在适用于应用程序的移动应用程序中不受Office。</span><span class="sxs-lookup"><span data-stu-id="a60d4-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="a60d4-495">**TeamsWeb/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="a60d4-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a60d4-496">全部</span><span class="sxs-lookup"><span data-stu-id="a60d4-496">All</span></span>|<span data-ttu-id="a60d4-497">DLP Teams中所有规则谓词</span><span class="sxs-lookup"><span data-stu-id="a60d4-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="a60d4-498">当邮件被标记为"此邮件已标记"时，将显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="a60d4-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="a60d4-499">我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="a60d4-499">What can I do?”</span></span> <span data-ttu-id="a60d4-500">单击链接时，用户可以查看检测到的敏感信息类型，并覆盖或报告问题（如果管理员允许）。请注意，不会为文件显示任何策略提示。</span><span class="sxs-lookup"><span data-stu-id="a60d4-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="a60d4-501">当收件人尝试访问文档时，如果不允许，他们可能会被拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="a60d4-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="a60d4-502">**Win32 终结点设备**</span><span class="sxs-lookup"><span data-stu-id="a60d4-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="a60d4-503">Subset</span><span class="sxs-lookup"><span data-stu-id="a60d4-503">Subset</span></span>|<span data-ttu-id="a60d4-504">DLP 策略中所有终结点 DLP 谓词和操作</span><span class="sxs-lookup"><span data-stu-id="a60d4-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="a60d4-505">请参阅 [Endpoint 上的数据丢失防护仅支持某些敏感信息类型的策略提示](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="a60d4-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="a60d4-506">**Mac 设备**</span><span class="sxs-lookup"><span data-stu-id="a60d4-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a60d4-507">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-507">None</span></span>|<span data-ttu-id="a60d4-508">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-508">None</span></span>|<span data-ttu-id="a60d4-509">现在，Mac 设备上未实施数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="a60d4-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="a60d4-510">**第三方云应用**</span><span class="sxs-lookup"><span data-stu-id="a60d4-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a60d4-511">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-511">None</span></span>|<span data-ttu-id="a60d4-512">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-512">None</span></span>|<span data-ttu-id="a60d4-513">第三方云应用不支持数据丢失防护策略提示</span><span class="sxs-lookup"><span data-stu-id="a60d4-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="a60d4-514">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="a60d4-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a60d4-515">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-515">None</span></span>|<span data-ttu-id="a60d4-516">无</span><span class="sxs-lookup"><span data-stu-id="a60d4-516">None</span></span>||
|<span data-ttu-id="a60d4-517">**Word、Excel、PowerPoint Win32 客户端**</span><span class="sxs-lookup"><span data-stu-id="a60d4-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="a60d4-518">Subset</span><span class="sxs-lookup"><span data-stu-id="a60d4-518">Subset</span></span>|<span data-ttu-id="a60d4-519">Subset</span><span class="sxs-lookup"><span data-stu-id="a60d4-519">Subset</span></span>|<span data-ttu-id="a60d4-520">请参阅[Outlook 2013 及](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)更高版本和桌面Office应用支持，其中仅显示某些敏感信息类型的策略提示，了解支持的敏感信息类型列表</span><span class="sxs-lookup"><span data-stu-id="a60d4-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="a60d4-521">WXP 客户端应用的策略提示适用于存储在 Sharepoint Online 或 One Drive for Business 网站中的文档，适用于 DLP 策略中条件或操作完全相同的所有 DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="a60d4-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="a60d4-522">内容包含敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a60d4-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="a60d4-523">访问 (内容在内部/外部共享) </span><span class="sxs-lookup"><span data-stu-id="a60d4-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="a60d4-524">通知用户 (策略提示/用户通知) </span><span class="sxs-lookup"><span data-stu-id="a60d4-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="a60d4-525">阻止所有人</span><span class="sxs-lookup"><span data-stu-id="a60d4-525">Block everyone</span></span></li><li><span data-ttu-id="a60d4-526">事件报告</span><span class="sxs-lookup"><span data-stu-id="a60d4-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="a60d4-527">如果存在任何其他条件或操作，该策略的 DLP 策略提示将不会显示在 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="a60d4-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="a60d4-528">有关详细信息[，请参阅 Excel、PowerPoint 和 Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)中的策略提示</span><span class="sxs-lookup"><span data-stu-id="a60d4-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
