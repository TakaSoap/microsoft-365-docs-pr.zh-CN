---
title: 邮件流智能
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理员可以了解使用连接器（也称为"邮件流智能" (）与邮件传递关联的) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7d4277d1ce3baeabcb5b1795b5d57583fbc8245
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029252"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="32ee3-103">EOP 中的邮件流智能</span><span class="sxs-lookup"><span data-stu-id="32ee3-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="32ee3-104">在 Exchange Online 中具有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，通常使用连接器将电子邮件从 EOP 路由到本地电子邮件环境。</span><span class="sxs-lookup"><span data-stu-id="32ee3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="32ee3-105">您还可以使用连接器将邮件从 Microsoft 365 路由到合作伙伴组织。</span><span class="sxs-lookup"><span data-stu-id="32ee3-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="32ee3-106">当 Microsoft 365 无法通过连接器传递这些邮件时，它们在 Microsoft 365 中排队。</span><span class="sxs-lookup"><span data-stu-id="32ee3-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="32ee3-107">Microsoft 365 将继续重试每封邮件的传递 24 小时。</span><span class="sxs-lookup"><span data-stu-id="32ee3-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="32ee3-108">24 小时后，排队的邮件将过期，邮件将在未送达报告（也称为 NDR 或退回邮件）中返回到原始发件人 (也称为 NDR 或退回) 。</span><span class="sxs-lookup"><span data-stu-id="32ee3-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="32ee3-109">当邮件无法通过连接器传递时，Microsoft 365 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="32ee3-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="32ee3-110">本文介绍了最常见的错误及其解决方案。</span><span class="sxs-lookup"><span data-stu-id="32ee3-110">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="32ee3-111">统称为邮件流智能。通过连接器发送的未送达邮件的排队和通知 _错误统称为邮件流智能_。</span><span class="sxs-lookup"><span data-stu-id="32ee3-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="32ee3-112">错误代码：450 4.4.312 DNS 查询失败</span><span class="sxs-lookup"><span data-stu-id="32ee3-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="32ee3-113">通常，此错误意味着 Microsoft 365 尝试连接到连接器中指定的智能主机，但用于查找智能主机 IP 地址的 DNS 查询失败。</span><span class="sxs-lookup"><span data-stu-id="32ee3-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="32ee3-114">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="32ee3-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="32ee3-115">您的域的 DNS 托管服务与维护域 (服务器一方存在) 。</span><span class="sxs-lookup"><span data-stu-id="32ee3-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="32ee3-116">您的域最近已过期，因此无法检索 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="32ee3-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="32ee3-117">您的域的 MX 记录最近已更改，并且 DNS 服务器以前仍缓存了域的 DNS 信息。</span><span class="sxs-lookup"><span data-stu-id="32ee3-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="32ee3-118">如何修复错误代码 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="32ee3-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="32ee3-119">与 DNS 托管服务一起确定并修复域的问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="32ee3-120">如果错误来自合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="32ee3-121">错误代码：450 4.4.315 连接已退出</span><span class="sxs-lookup"><span data-stu-id="32ee3-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="32ee3-122">通常，这意味着 Microsoft 365 无法连接到目标电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="32ee3-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="32ee3-123">错误详细信息将解释此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-123">The error details will explain the problem.</span></span> <span data-ttu-id="32ee3-124">例如：</span><span class="sxs-lookup"><span data-stu-id="32ee3-124">For example:</span></span>

- <span data-ttu-id="32ee3-125">您的本地电子邮件服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="32ee3-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="32ee3-126">连接器的智能主机设置出错，因此 Microsoft 365 尝试连接到错误的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="32ee3-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="32ee3-127">如何修复错误代码 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="32ee3-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="32ee3-128">了解适用于你的方案，并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="32ee3-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="32ee3-129">例如，如果邮件流一直运行正常，并且您尚未更改连接器设置，则需要检查您的本地电子邮件环境以查看服务器是否关闭，或者是否对网络基础结构进行了任何更改 (例如，您更改了 Internet 服务提供商，因此您现在具有不同的 IP 地址) 。</span><span class="sxs-lookup"><span data-stu-id="32ee3-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="32ee3-130">如果错误来自合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="32ee3-131">错误代码：450 4.4.316 连接被拒绝</span><span class="sxs-lookup"><span data-stu-id="32ee3-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="32ee3-132">通常，此错误意味着 Microsoft 365 在尝试连接到目标电子邮件服务器时遇到连接错误。</span><span class="sxs-lookup"><span data-stu-id="32ee3-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="32ee3-133">导致此错误的一个可能原因是防火墙阻止了来自 Microsoft 365 IP 地址的连接。</span><span class="sxs-lookup"><span data-stu-id="32ee3-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="32ee3-134">或者，如果你已完全将本地电子邮件系统迁移到 Microsoft 365 并关闭本地电子邮件环境，则此错误可能是设计使的。</span><span class="sxs-lookup"><span data-stu-id="32ee3-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="32ee3-135">如何修复错误代码 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="32ee3-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="32ee3-136">如果您的内部部署环境中有邮箱，则需要修改防火墙设置，以允许从 TCP 端口 25 上的 Microsoft 365 IP 地址连接到本地电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="32ee3-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="32ee3-137">有关 Microsoft 365 IP 地址的列表，请参阅 [Microsoft 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="32ee3-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="32ee3-138">如果不应向本地环境传递其他邮件，请单击警报中的"立即修复"，以便 Microsoft 365 可以立即拒绝收件人无效的邮件。</span><span class="sxs-lookup"><span data-stu-id="32ee3-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="32ee3-139">这将降低超出组织对无效收件人的配额的风险，这可能会影响正常邮件传递。</span><span class="sxs-lookup"><span data-stu-id="32ee3-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="32ee3-140">或者，可以使用以下说明手动修复该问题：</span><span class="sxs-lookup"><span data-stu-id="32ee3-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="32ee3-141">在 [Exchange 管理中心 (EAC) ， ](https://docs.microsoft.com/Exchange/exchange-admin-center)禁用或删除将电子邮件从 Microsoft 365 发送到本地电子邮件环境的连接器：</span><span class="sxs-lookup"><span data-stu-id="32ee3-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="32ee3-142">在 EAC 中，转到 **"邮件流** \> **连接器"。**</span><span class="sxs-lookup"><span data-stu-id="32ee3-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="32ee3-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps：</span><span class="sxs-lookup"><span data-stu-id="32ee3-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="32ee3-144">通过单击"删除删除 **"图标删除** ![ 连接器](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="32ee3-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="32ee3-145">通过单击"编辑编辑 **"图标** ![ 并 ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 清除" **打开"来禁用连接器**。</span><span class="sxs-lookup"><span data-stu-id="32ee3-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="32ee3-146">将 Microsoft 365 中与本地电子邮件环境关联的接受域从内部中继更改为 **权威**。 </span><span class="sxs-lookup"><span data-stu-id="32ee3-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="32ee3-147">有关说明，请参阅["管理 Exchange Online 中的接受域"。](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="32ee3-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="32ee3-148">**注意**：通常，这些更改需要 30 分钟到 1 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="32ee3-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="32ee3-149">一小时后，请确认您不再收到错误。</span><span class="sxs-lookup"><span data-stu-id="32ee3-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="32ee3-150">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="32ee3-151">错误代码：450 4.4.317 无法连接到远程服务器</span><span class="sxs-lookup"><span data-stu-id="32ee3-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="32ee3-152">通常，此错误意味着 Microsoft 365 连接到目标电子邮件服务器，但服务器立即响应错误，或不符合连接要求。</span><span class="sxs-lookup"><span data-stu-id="32ee3-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="32ee3-153">错误详细信息将解释此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-153">The error details will explain the problem.</span></span> <span data-ttu-id="32ee3-154">例如：</span><span class="sxs-lookup"><span data-stu-id="32ee3-154">For example:</span></span>

- <span data-ttu-id="32ee3-155">目标电子邮件服务器响应了"服务不可用"错误，指示服务器无法与 Microsoft 365 保持通信。</span><span class="sxs-lookup"><span data-stu-id="32ee3-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="32ee3-156">连接器配置为需要 TLS，但目标电子邮件服务器不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="32ee3-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="32ee3-157">如何修复错误代码 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="32ee3-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="32ee3-158">验证本地电子邮件服务器的 TLS 设置和证书，以及连接器上的 TLS 设置。</span><span class="sxs-lookup"><span data-stu-id="32ee3-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="32ee3-159">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="32ee3-160">错误代码：450 4.4.318 连接突然关闭</span><span class="sxs-lookup"><span data-stu-id="32ee3-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="32ee3-161">通常，此错误意味着 Microsoft 365 难以与本地电子邮件环境通信，因此连接已中断。</span><span class="sxs-lookup"><span data-stu-id="32ee3-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="32ee3-162">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="32ee3-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="32ee3-163">防火墙使用 SMTP 数据包检查规则，这些规则无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="32ee3-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="32ee3-164">您的本地电子邮件服务器无法正常运行 (例如服务挂起、崩溃或系统资源不足) ，从而导致服务器将退出并关闭与 Microsoft 365 的连接。</span><span class="sxs-lookup"><span data-stu-id="32ee3-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="32ee3-165">本地环境和 Microsoft 365 之间存在网络问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="32ee3-166">如何修复错误代码 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="32ee3-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="32ee3-167">了解适用于你的方案，并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="32ee3-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="32ee3-168">如果问题由本地环境和 Microsoft 365 之间的网络问题导致，请与网络团队联系以解决问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="32ee3-169">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="32ee3-170">错误代码：450 4.7.320 证书验证失败</span><span class="sxs-lookup"><span data-stu-id="32ee3-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="32ee3-171">通常，此错误意味着 Microsoft 365 在尝试验证目标电子邮件服务器的证书时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="32ee3-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="32ee3-172">错误详细信息将解释此错误。</span><span class="sxs-lookup"><span data-stu-id="32ee3-172">The error details will explain the error.</span></span> <span data-ttu-id="32ee3-173">例如：</span><span class="sxs-lookup"><span data-stu-id="32ee3-173">For example:</span></span>

- <span data-ttu-id="32ee3-174">证书已过期</span><span class="sxs-lookup"><span data-stu-id="32ee3-174">Certificate expired</span></span>

- <span data-ttu-id="32ee3-175">证书主题不匹配</span><span class="sxs-lookup"><span data-stu-id="32ee3-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="32ee3-176">证书不再有效</span><span class="sxs-lookup"><span data-stu-id="32ee3-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="32ee3-177">如何修复错误代码 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="32ee3-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="32ee3-178">修复连接器上的证书或设置，以便可以传递 Microsoft 365 中的排队邮件。</span><span class="sxs-lookup"><span data-stu-id="32ee3-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="32ee3-179">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="32ee3-180">其他错误代码</span><span class="sxs-lookup"><span data-stu-id="32ee3-180">Other error codes</span></span>

<span data-ttu-id="32ee3-181">Microsoft 365 难以将邮件发送到本地或合作伙伴电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="32ee3-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="32ee3-182">使用 **错误中的** 目标服务器信息检查环境中的问题，或者修改连接器（如果存在配置错误）。</span><span class="sxs-lookup"><span data-stu-id="32ee3-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="32ee3-183">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="32ee3-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
