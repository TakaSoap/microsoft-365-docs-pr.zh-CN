---
title: 邮件流智能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理员可以了解使用连接器服务与邮件传递关联的错误代码 (，也称为邮件流智能) 。
ms.openlocfilehash: b345b52f572efca2aca1fde6ba720d733e521cc4
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827709"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="53789-103">EOP 中的邮件流智能</span><span class="sxs-lookup"><span data-stu-id="53789-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="53789-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，通常可以使用连接器将电子邮件从 EOP 路由到内部部署电子邮件环境。</span><span class="sxs-lookup"><span data-stu-id="53789-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="53789-105">您还可以使用连接器将来自 Microsoft 365 的邮件路由到合作伙伴组织。</span><span class="sxs-lookup"><span data-stu-id="53789-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="53789-106">当 Microsoft 365 无法通过连接器传递这些邮件时，它们会在 Microsoft 365 中排队。</span><span class="sxs-lookup"><span data-stu-id="53789-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="53789-107">Microsoft 365 将继续 24 小时对每封邮件重试传递。</span><span class="sxs-lookup"><span data-stu-id="53789-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="53789-108">24 小时之后，排队邮件将过期，并且邮件将以未送达报告 (也称为 NDR 或退回邮件未送达邮件类型退回) 。</span><span class="sxs-lookup"><span data-stu-id="53789-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="53789-109">当邮件无法使用连接器传递时，Microsoft 365 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="53789-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="53789-110">本主题对最常见的错误及其解决方案进行了描述。</span><span class="sxs-lookup"><span data-stu-id="53789-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="53789-111">通过连接器发送的无法送达邮件的队列和通知错误集中称为 _邮件流智能_。</span><span class="sxs-lookup"><span data-stu-id="53789-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="53789-112">错误代码：450 4.4.312 DNS 查询失败</span><span class="sxs-lookup"><span data-stu-id="53789-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="53789-113">通常情况下，此错误意味着 Microsoft 365 尝试连接到连接器中指定的智能主机，但查找智能主机的 IP 地址的 DNS 查询失败。</span><span class="sxs-lookup"><span data-stu-id="53789-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="53789-114">此错误可能是由如下原因造出的：</span><span class="sxs-lookup"><span data-stu-id="53789-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="53789-115">您的域的 DNS 托管服务遇到 (方将保留域服务的权威名称) 。</span><span class="sxs-lookup"><span data-stu-id="53789-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="53789-116">你的域最近已过期，无法检索 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="53789-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="53789-117">您的域的 MX 记录最近已更改，DNS 服务器仍之前已缓存域的 DNS 信息。</span><span class="sxs-lookup"><span data-stu-id="53789-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="53789-118">如何修复错误代码 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="53789-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="53789-119">使用您的 DNS 托管服务来识别并修复您的域的问题。</span><span class="sxs-lookup"><span data-stu-id="53789-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="53789-120">如果错误来自合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="53789-121">错误代码：450 4.4.315 连接超时</span><span class="sxs-lookup"><span data-stu-id="53789-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="53789-122">通常情况下，Microsoft 365 无法连接到目标电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="53789-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="53789-123">错误详细信息将说明问题。</span><span class="sxs-lookup"><span data-stu-id="53789-123">The error details will explain the problem.</span></span> <span data-ttu-id="53789-124">例如：</span><span class="sxs-lookup"><span data-stu-id="53789-124">For example:</span></span>

- <span data-ttu-id="53789-125">您的本地电子邮件服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="53789-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="53789-126">连接器的智能主机设置中存在错误，导致 Microsoft 365 将尝试连接到错误的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="53789-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="53789-127">如何修复错误代码 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="53789-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="53789-128">找出适用于你的方案，并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="53789-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="53789-129">例如，如果邮件流已正常工作，且连接器设置未更改，则需要检查本地电子邮件环境以确定服务器是否关闭，或者你是否已更改了网络基础结构 (（例如，您已更改了 Internet 服务提供商）以使你现在拥有不同的 IP 地址) 。</span><span class="sxs-lookup"><span data-stu-id="53789-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="53789-130">如果错误来自合作伙伴组织 (例如，第三方云服务提供商) ，请与合作伙伴联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="53789-131">错误代码：450 4.4.316 连接拒绝</span><span class="sxs-lookup"><span data-stu-id="53789-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="53789-132">通常情况下，此错误意味着 Microsoft 365 在尝试连接到目标电子邮件服务器时遇到了连接错误。</span><span class="sxs-lookup"><span data-stu-id="53789-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="53789-133">错误的原因是你的防火墙阻止了来自 Microsoft 365 IP 地址的连接。</span><span class="sxs-lookup"><span data-stu-id="53789-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="53789-134">如果您已将本地电子邮件系统完全迁移到 Microsoft 365 并关闭本地电子邮件环境，则此错误可能是设计使而值。</span><span class="sxs-lookup"><span data-stu-id="53789-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="53789-135">如何修复错误代码 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="53789-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="53789-136">如果您在本地环境中有邮箱，则需要修改防火墙设置以允许从 TCP 端口 25 上的 Microsoft 365 IP 地址连接到本地电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="53789-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="53789-137">有关 Microsoft 365 IP 地址的列表，请参阅 [Microsoft 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="53789-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="53789-138">如果没有其他邮件应传递到你的本地环境，则在 **警报中单击"修复** "，以便 Microsoft 365 可以立即拒绝具有无效收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="53789-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="53789-139">这将降低无效收件人超过组织配额的风险，进而可能会影响正常邮件传递。</span><span class="sxs-lookup"><span data-stu-id="53789-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="53789-140">或者，你可以按照以下说明手动修复此问题：</span><span class="sxs-lookup"><span data-stu-id="53789-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="53789-141">在 [EXCHANGE 管理中心 (EAC) ， ](https://docs.microsoft.com/Exchange/exchange-admin-center)禁用或删除将电子邮件从 Microsoft 365 传递到本地电子邮件环境的连接器：</span><span class="sxs-lookup"><span data-stu-id="53789-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="53789-142">在 EAC 中，**转到"** \> **邮件流连接器"。**</span><span class="sxs-lookup"><span data-stu-id="53789-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="53789-143">选择"发件人" **值** **Office 365** 且 **您的组织的** 电子邮件服务器的"收件人"值 **的连接器，** 并执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="53789-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="53789-144">通过单击"删除删除" **图标删除** ![ 连接器](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="53789-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="53789-145">通过单击"编辑"图标 **并** ![ 取消 ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 其打开来 **禁用连接器**。</span><span class="sxs-lookup"><span data-stu-id="53789-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="53789-146">将 Microsoft 365 中与本地电子邮件环境相关联的接受域从 **"内部中继"更改为**"**权威"。**</span><span class="sxs-lookup"><span data-stu-id="53789-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="53789-147">有关说明，请参阅["在 Exchange Online 中管理接受域"。](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="53789-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="53789-148">**注意**：这些更改通常需要 30 分钟到 1 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="53789-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="53789-149">1 小时后，验证您是否不再收到该错误。</span><span class="sxs-lookup"><span data-stu-id="53789-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="53789-150">如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="53789-151">错误代码：450 4.4.317 无法连接到远程服务器</span><span class="sxs-lookup"><span data-stu-id="53789-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="53789-152">通常情况下，此错误意味着 Microsoft 365 连接到目标电子邮件服务器，但服务器返回了即时错误，或者不满足连接要求。</span><span class="sxs-lookup"><span data-stu-id="53789-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="53789-153">错误详细信息将说明问题。</span><span class="sxs-lookup"><span data-stu-id="53789-153">The error details will explain the problem.</span></span> <span data-ttu-id="53789-154">例如：</span><span class="sxs-lookup"><span data-stu-id="53789-154">For example:</span></span>

- <span data-ttu-id="53789-155">目标电子邮件服务器响应"服务不可用"错误，表示该服务器无法保持与 Microsoft 365 的通信。</span><span class="sxs-lookup"><span data-stu-id="53789-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="53789-156">连接器配置为需要 TLS，但目标电子邮件服务器不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="53789-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="53789-157">如何修复错误代码 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="53789-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="53789-158">验证您的本地电子邮件服务器上的 TLS 设置和证书，以及连接器上的 TLS 设置。</span><span class="sxs-lookup"><span data-stu-id="53789-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="53789-159">如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="53789-160">错误代码：450 4.4.318 连接已意外关闭</span><span class="sxs-lookup"><span data-stu-id="53789-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="53789-161">通常情况下，此错误意味着 Microsoft 365 在与本地电子邮件环境进行联操作时遇到难以，因此连接断开。</span><span class="sxs-lookup"><span data-stu-id="53789-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="53789-162">此错误可能是由如下原因造出的：</span><span class="sxs-lookup"><span data-stu-id="53789-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="53789-163">你的防火墙使用 SMTP 数据包检查规则，这些规则无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="53789-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="53789-164">你的本地电子邮件服务器运行不正常 (例如服务停靠、崩溃或低系统资源) ，这将使服务器超时并关闭与 Microsoft 365 的连接。</span><span class="sxs-lookup"><span data-stu-id="53789-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="53789-165">本地环境和 Microsoft 365 之间存在网络问题。</span><span class="sxs-lookup"><span data-stu-id="53789-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="53789-166">如何修复错误代码 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="53789-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="53789-167">找出适用于你的方案，并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="53789-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="53789-168">如果此问题是由本地环境和 Microsoft 365 之间的网络问题导致的，请与网络团队联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="53789-169">如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="53789-170">错误代码：450 4.7.320 证书验证失败</span><span class="sxs-lookup"><span data-stu-id="53789-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="53789-171">通常情况下，此错误意味着 Microsoft 365 在尝试验证目标电子邮件服务器的证书时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="53789-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="53789-172">错误详细信息将说明错误。</span><span class="sxs-lookup"><span data-stu-id="53789-172">The error details will explain the error.</span></span> <span data-ttu-id="53789-173">例如：</span><span class="sxs-lookup"><span data-stu-id="53789-173">For example:</span></span>

- <span data-ttu-id="53789-174">证书过期</span><span class="sxs-lookup"><span data-stu-id="53789-174">Certificate expired</span></span>

- <span data-ttu-id="53789-175">证书使用者不匹配</span><span class="sxs-lookup"><span data-stu-id="53789-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="53789-176">证书不再有效</span><span class="sxs-lookup"><span data-stu-id="53789-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="53789-177">如何修复错误代码 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="53789-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="53789-178">修复连接器上的证书或设置，以便可以传递 Microsoft 365 中的排队邮件。</span><span class="sxs-lookup"><span data-stu-id="53789-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="53789-179">如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="53789-180">其他错误代码</span><span class="sxs-lookup"><span data-stu-id="53789-180">Other error codes</span></span>

<span data-ttu-id="53789-181">Microsoft 365 在将邮件送达本地或合作伙伴电子邮件服务器时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="53789-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="53789-182">使用 **错误中的** 目标服务器信息检查环境中的问题，或者在配置错误下修改连接器。</span><span class="sxs-lookup"><span data-stu-id="53789-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="53789-183">如果错误来自您的合作伙伴 (例如，第三方云服务提供商) ，您需要与合作伙伴联系以解决该问题。</span><span class="sxs-lookup"><span data-stu-id="53789-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
