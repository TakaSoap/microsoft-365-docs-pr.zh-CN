---
title: 添加 DNS 记录以连接你的域
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: 验证域和更新注册机构的帐户中的 DNS 记录，将任何 DNS 托管提供商的域连接到 Microsoft 365。
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 62b6793dd97e146b703c82e0ba23f4d7414025b6
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623973"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="7748c-103">添加 DNS 记录以连接你的域</span><span class="sxs-lookup"><span data-stu-id="7748c-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="7748c-104">如果是从第三方托管提供商处购买的域，则可以通过更新注册机构帐户中的 DNS 记录将其连接到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7748c-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="7748c-105">执行完以下步骤后，你的域将在向你出售域的主机中保持注册，但 Microsoft 365 可将其用于你的电子邮件地址（如 user@yourdomain.com）和其他服务。</span><span class="sxs-lookup"><span data-stu-id="7748c-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="7748c-106">如果你不添加域，组织中的人员将在电子邮件地址中使用 onmicrosoft.com 域，直至你添加为止。</span><span class="sxs-lookup"><span data-stu-id="7748c-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="7748c-107">请务必在添加用户前先添加域，以免需要进行两次设置。</span><span class="sxs-lookup"><span data-stu-id="7748c-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="7748c-108">如果在下文中找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="7748c-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="7748c-109">步骤 1：添加 TXT 或 MX 记录以验证你是否拥有相应的域</span><span class="sxs-lookup"><span data-stu-id="7748c-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="7748c-110">建议：使用 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="7748c-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="7748c-111">首先，你需要证明自己拥有要添加到 Microsoft 365 的域。</span><span class="sxs-lookup"><span data-stu-id="7748c-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="7748c-112">登录到 [Microsoft 365 管理中心](https://admin.microsoft.com/)，然后选择“**全部显示**” > “**设置**” > “**域**”。</span><span class="sxs-lookup"><span data-stu-id="7748c-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="7748c-113">在新的浏览器标签页或窗口中，登录 DNS 托管提供商网站，然后找到管理 DNS 设置（如“区域文件设置”、“管理域”、“域管理器”和“DNS 管理器”）的位置。</span><span class="sxs-lookup"><span data-stu-id="7748c-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="7748c-114">转到提供商的“DNS 管理器”页面，然后将管理中心中指示的 TXT 记录添加到域中。</span><span class="sxs-lookup"><span data-stu-id="7748c-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="7748c-115">添加此记录不会影响现有电子邮件或其他服务，并且可在域连接到 Microsoft 365 后，安全地将其删除。</span><span class="sxs-lookup"><span data-stu-id="7748c-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="7748c-116">示例：</span><span class="sxs-lookup"><span data-stu-id="7748c-116">Example:</span></span>
- <span data-ttu-id="7748c-117">TXT 名称：`@`</span><span class="sxs-lookup"><span data-stu-id="7748c-117">TXT Name: `@`</span></span>
- <span data-ttu-id="7748c-118">TXT 值：MS=ms########（管理中心的唯一 ID）</span><span class="sxs-lookup"><span data-stu-id="7748c-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="7748c-119">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="7748c-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="7748c-120">保存记录，返回管理中心，然后选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="7748c-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="7748c-121">对记录更改进行注册通常需要 15 分钟左右，但有时可能需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="7748c-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="7748c-122">请稍等片刻并多尝试几次，以便获得所做的更改。</span><span class="sxs-lookup"><span data-stu-id="7748c-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="7748c-123">当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="7748c-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="7748c-124">使用 MX 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="7748c-124">Verify with an MX record</span></span>

<span data-ttu-id="7748c-125">如果注册机构不支持添加 TXT 记录，可通过添加 MX 记录进行验证。</span><span class="sxs-lookup"><span data-stu-id="7748c-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="7748c-126">登录到 [Microsoft 365 管理中心](https://admin.microsoft.com/)，然后选择“**全部显示**” > “**设置**” > “**域**”。</span><span class="sxs-lookup"><span data-stu-id="7748c-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="7748c-127">在新的浏览器标签页或窗口中，登录 DNS 托管提供商网站，然后找到管理 DNS 设置（如“区域文件设置”、“管理域”、“域管理器”和“DNS 管理器”）的位置。</span><span class="sxs-lookup"><span data-stu-id="7748c-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="7748c-128">转到提供商的“DNS 管理器”页面，然后将管理中心中指示的 MX 记录添加到域中。</span><span class="sxs-lookup"><span data-stu-id="7748c-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="7748c-129">此 MX 记录的 **优先级** 必须是域的所有现有 MX 记录中最高的。</span><span class="sxs-lookup"><span data-stu-id="7748c-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="7748c-130">否则，它可能会干扰发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7748c-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="7748c-131">域验证完成后，应立即删除此记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="7748c-132">请确保将字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="7748c-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="7748c-133">记录类型：`MX`</span><span class="sxs-lookup"><span data-stu-id="7748c-133">Record Type: `MX`</span></span>
- <span data-ttu-id="7748c-134">优先级：设置为可用的最高值，通常为 `0`。</span><span class="sxs-lookup"><span data-stu-id="7748c-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="7748c-135">主机名：`@`</span><span class="sxs-lookup"><span data-stu-id="7748c-135">Host Name: `@`</span></span>
- <span data-ttu-id="7748c-136">指向地址：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="7748c-137">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="7748c-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="7748c-138">当 Microsof 找到正确的 MX 记录时，表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="7748c-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="7748c-139">步骤 2：添加 DNS 记录以连接 Microsoft 服务</span><span class="sxs-lookup"><span data-stu-id="7748c-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="7748c-140">在新的浏览器标签页或窗口中，登录 DNS 托管提供商网站，然后找到管理 DNS 设置（如“区域文件设置”、“管理域”、“域管理器”和“DNS 管理器”）的位置。</span><span class="sxs-lookup"><span data-stu-id="7748c-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="7748c-141">根据要启用的服务，你将添加多个不同类型的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="7748c-142">添加针对电子邮件（Outlook、Exchange Online）的 MX 记录</span><span class="sxs-lookup"><span data-stu-id="7748c-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="7748c-143">**准备工作：** 如果用户已经拥有使用你的域的电子邮件地址（如 user@yourdomain.com），请先在管理中心中创建其帐户，然后再设置 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="7748c-144">这样一来，他们便能够继续接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7748c-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="7748c-145">更新你的域的 MX 记录时，使用你的域的任何人的所有新电子邮件现在都将发往 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7748c-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="7748c-146">你已拥有的任何电子邮件将保留在你当前的电子邮件主机中，除非你决定[将电子邮件和联系人迁移到 Microsoft 365。](../setup/migrate-email-and-contacts-admin.md)</span><span class="sxs-lookup"><span data-stu-id="7748c-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="7748c-147">你将从管理中心域设置向导中获取有关 MX 记录的信息。</span><span class="sxs-lookup"><span data-stu-id="7748c-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="7748c-148">在托管提供商的网站上，添加一条新的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="7748c-149">请确保将字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="7748c-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="7748c-150">记录类型：`MX`</span><span class="sxs-lookup"><span data-stu-id="7748c-150">Record Type: `MX`</span></span>
- <span data-ttu-id="7748c-151">优先级：设置为可用的最高值，通常为 `0`。</span><span class="sxs-lookup"><span data-stu-id="7748c-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="7748c-152">主机名：`@`</span><span class="sxs-lookup"><span data-stu-id="7748c-152">Host Name: `@`</span></span>
- <span data-ttu-id="7748c-153">指向地址：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="7748c-154">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="7748c-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="7748c-155">保存记录，然后删除任何其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="7748c-156">添加 CNAME 记录以连接其他服务（Teams、Exchange Online、AAD 和 MDM）</span><span class="sxs-lookup"><span data-stu-id="7748c-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="7748c-157">你将从管理中心域设置向导中获取有关 CNAME 记录的信息。</span><span class="sxs-lookup"><span data-stu-id="7748c-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="7748c-158">在托管提供商的网站上，为要连接的每个服务添加 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="7748c-159">请确保将每个服务的字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="7748c-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="7748c-160">记录类型：`CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="7748c-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="7748c-161">主机：将从管理中心复制的值粘贴在此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="7748c-162">指向地址：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="7748c-163">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="7748c-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="7748c-164">添加或编辑 SPF TXT 记录，以防出现垃圾邮件（Outlook、Exchange Online）</span><span class="sxs-lookup"><span data-stu-id="7748c-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="7748c-165">**准备工作：** 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="7748c-166">相反，可以在托管提供商网站上将所需的 Microsoft 365 值添加到当前记录，这样就拥有同时包含两组值的 *单个* SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="7748c-167">在托管提供商的网站上，编辑现有 SPF 记录或创建 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="7748c-168">请确保将字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="7748c-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="7748c-169">记录类型：`TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="7748c-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="7748c-170">主机：`@`</span><span class="sxs-lookup"><span data-stu-id="7748c-170">Host: `@`</span></span>
- <span data-ttu-id="7748c-171">TXT 值：`v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="7748c-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="7748c-172">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="7748c-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="7748c-173">保存记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-173">Save the record.</span></span>

<span data-ttu-id="7748c-174">使用以下任一 [SPF 验证工具](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)验证 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-174">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="7748c-175">SPF 旨在帮助防骗，但有些骗术是 SPF 所无法防范的。</span><span class="sxs-lookup"><span data-stu-id="7748c-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="7748c-176">为了防范这些骗术，在设置 SPF 后，还应为 Microsoft 365 设置 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="7748c-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="7748c-177">若要开始进行设置，请参阅[使用 DKIM 验证从 Microsoft 365 中的域发送的出站电子邮件](../../security/office-365-security/use-dkim-to-validate-outbound-email.md)和[使用 DMARC 验证 Microsoft 365 中的电子邮件](../../security/office-365-security/use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="7748c-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="7748c-178">为通信服务（Teams、Skype for Business）添加 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="7748c-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="7748c-179">在托管提供商的网站上，为要连接的每个服务添加 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="7748c-180">请确保将每个服务的字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="7748c-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="7748c-181">记录类型：`SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="7748c-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="7748c-182">名称：`@`</span><span class="sxs-lookup"><span data-stu-id="7748c-182">Name: `@`</span></span>
- <span data-ttu-id="7748c-183">目标：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="7748c-184">协议：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="7748c-185">服务：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="7748c-186">优先级：`100`</span><span class="sxs-lookup"><span data-stu-id="7748c-186">Priority: `100`</span></span>
- <span data-ttu-id="7748c-187">权重：`1`</span><span class="sxs-lookup"><span data-stu-id="7748c-187">Weight: `1`</span></span>
- <span data-ttu-id="7748c-188">端口：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7748c-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="7748c-189">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="7748c-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="7748c-190">保存记录。</span><span class="sxs-lookup"><span data-stu-id="7748c-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="7748c-191">SRV 记录字段限制和解决方法</span><span class="sxs-lookup"><span data-stu-id="7748c-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="7748c-192">某些托管提供商会对 SRV 记录中的字段值施加限制。</span><span class="sxs-lookup"><span data-stu-id="7748c-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="7748c-193">下面是应对这些限制的一些常见解决方法。</span><span class="sxs-lookup"><span data-stu-id="7748c-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="7748c-194">名称</span><span class="sxs-lookup"><span data-stu-id="7748c-194">Name</span></span>
<span data-ttu-id="7748c-195">如果托管提供商不允许将此字段设置为 **@**，请将其留空。</span><span class="sxs-lookup"><span data-stu-id="7748c-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="7748c-196">*仅* 当托管提供商为“服务”和“协议”值提供了单独的字段时，才能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="7748c-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="7748c-197">否则，请查看下面的“服务和协议”说明。</span><span class="sxs-lookup"><span data-stu-id="7748c-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="7748c-198">服务和协议</span><span class="sxs-lookup"><span data-stu-id="7748c-198">Service and Protocol</span></span>
<span data-ttu-id="7748c-199">如果托管提供商没有为 SRV 记录提供这些字段，则必须在记录的“**名称**”字段中指定“**服务**”和“**协议**”值。</span><span class="sxs-lookup"><span data-stu-id="7748c-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="7748c-200">（注意：根据你所选择的托管提供商，“**名称**”字段可能会有其他称呼，如：“**主机**”、“**主机名**”或“**子域**”。）若要添加这些值，可创建一个字符串，并用圆点分隔这些值。</span><span class="sxs-lookup"><span data-stu-id="7748c-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="7748c-201">例如：`_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="7748c-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="7748c-202">优先级、权重和端口</span><span class="sxs-lookup"><span data-stu-id="7748c-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="7748c-203">如果托管提供商没有为 SRV 记录提供这些字段，则必须在记录的“**目标**”字段中指定它们的值。</span><span class="sxs-lookup"><span data-stu-id="7748c-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="7748c-204">（注意：根据你所选择的托管提供商，“**目标**”字段可能会有其他称呼，如：“**内容**”、“**IP 地址**”或“**目标主机**”。）</span><span class="sxs-lookup"><span data-stu-id="7748c-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="7748c-205">若要添加这些值，请创建一个字符串，并用空格分隔这些值且 *有时以圆点结尾*（如果你不确定，请与你的提供商进行核实）。</span><span class="sxs-lookup"><span data-stu-id="7748c-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="7748c-206">这些值必须按以下顺序排列：优先级、权重、端口、目标。</span><span class="sxs-lookup"><span data-stu-id="7748c-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="7748c-207">示例 1：`100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="7748c-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="7748c-208">示例 2：`100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="7748c-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>

## <a name="related-content"></a><span data-ttu-id="7748c-209">相关内容</span><span class="sxs-lookup"><span data-stu-id="7748c-209">Related content</span></span>

<span data-ttu-id="7748c-210">[更改名称服务器以使用任意域注册机构设置 Microsoft 365](change-nameservers-at-any-domain-registrar.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="7748c-210">[Change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="7748c-211">[查找并修复添加域或 DNS 记录之后出现的问题](find-and-fix-issues.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="7748c-211">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="7748c-212">[管理域](index.yml)（链接页）</span><span class="sxs-lookup"><span data-stu-id="7748c-212">[Manage domains](index.yml) (link page)</span></span>