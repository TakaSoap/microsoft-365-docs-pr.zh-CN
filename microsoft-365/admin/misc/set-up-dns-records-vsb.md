---
title: 将你的域连接到 Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何使用 Microsoft 365 验证域和创建 DNS 记录。
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658165"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="8b09d-103">将你的域连接到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b09d-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="8b09d-104">如果你不添加域，组织中的人员将在电子邮件地址中使用 onmicrosoft.com 域，直至你添加为止。</span><span class="sxs-lookup"><span data-stu-id="8b09d-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="8b09d-105">请务必在添加用户前先添加域，以免需要进行两次设置。</span><span class="sxs-lookup"><span data-stu-id="8b09d-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="8b09d-106">如果在下文中找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="8b09d-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8b09d-107">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="8b09d-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="8b09d-108">你将从管理中心域设置向导中获取有关 MX 记录的信息。</span><span class="sxs-lookup"><span data-stu-id="8b09d-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="8b09d-109">在托管提供商的网站上，添加一条新的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="8b09d-110">请确保将字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="8b09d-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="8b09d-111">记录类型：`MX`</span><span class="sxs-lookup"><span data-stu-id="8b09d-111">Record Type: `MX`</span></span>
- <span data-ttu-id="8b09d-112">优先级：设置为可用的最高值，通常为 `0`。</span><span class="sxs-lookup"><span data-stu-id="8b09d-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="8b09d-113">主机名：`@`</span><span class="sxs-lookup"><span data-stu-id="8b09d-113">Host Name: `@`</span></span>
- <span data-ttu-id="8b09d-114">指向地址：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="8b09d-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8b09d-115">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="8b09d-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="8b09d-116">保存记录，然后删除任何其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="8b09d-117">添加 CNAME 记录以将用户连接到其邮箱</span><span class="sxs-lookup"><span data-stu-id="8b09d-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="8b09d-118">你将从管理中心域设置向导中获取有关 CNAME 记录的信息。</span><span class="sxs-lookup"><span data-stu-id="8b09d-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="8b09d-119">在托管提供商的网站上，添加以下 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="8b09d-120">请确保将每个服务的字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="8b09d-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="8b09d-121">记录类型：`CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="8b09d-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="8b09d-122">主机：将从管理中心复制的值粘贴在此处。</span><span class="sxs-lookup"><span data-stu-id="8b09d-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="8b09d-123">指向地址：从管理中心复制值并将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="8b09d-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="8b09d-124">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="8b09d-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="8b09d-125">添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="8b09d-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="8b09d-126">**准备工作：** 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="8b09d-127">相反，可以在托管提供商网站上将所需的 Microsoft 365 值添加到当前记录，这样就拥有同时包含两组值的 *单个* SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="8b09d-128">在托管提供商的网站上，编辑现有 SPF 记录或创建 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="8b09d-129">请确保将字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="8b09d-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="8b09d-130">记录类型：`TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="8b09d-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="8b09d-131">主机：`@`</span><span class="sxs-lookup"><span data-stu-id="8b09d-131">Host: `@`</span></span>
- <span data-ttu-id="8b09d-132">TXT 值：`v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="8b09d-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="8b09d-133">TTL：`3600‎`（或提供商的默认值）</span><span class="sxs-lookup"><span data-stu-id="8b09d-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="8b09d-134">保存记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-134">Save the record.</span></span>

<span data-ttu-id="8b09d-135">使用以下任一 [SPF 验证工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)验证 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="8b09d-135">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="8b09d-136">SPF 旨在帮助防骗，但有些骗术是 SPF 所无法防范的。</span><span class="sxs-lookup"><span data-stu-id="8b09d-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="8b09d-137">为了防范这些骗术，在设置 SPF 后，还应为 Microsoft 365 设置 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="8b09d-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="8b09d-138">若要开始进行设置，请参阅[使用 DKIM 验证从 Microsoft 365 中的域发送的出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)和[使用 DMARC 验证 Microsoft 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8b09d-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="8b09d-139">最后，请返回管理中心域设置向导以完成设置。</span><span class="sxs-lookup"><span data-stu-id="8b09d-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>
