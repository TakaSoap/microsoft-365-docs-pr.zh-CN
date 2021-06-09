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
description: 管理员可以了解使用连接器（也称为邮件流智能 (与邮件传递关联的错误) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44f2272c98f0c011c05cbe728e720f4d3180c09d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844666"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="4beae-103">EOP 中的邮件流智能</span><span class="sxs-lookup"><span data-stu-id="4beae-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4beae-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4beae-104">**Applies to**</span></span>
- [<span data-ttu-id="4beae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4beae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4beae-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4beae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4beae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4beae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4beae-108">在具有 Exchange Online 或独立 Exchange Online Protection (EOP) 组织邮箱且没有 Exchange Online 邮箱的 Microsoft 365 组织中，通常使用连接器将电子邮件从 EOP 路由到本地电子邮件环境。</span><span class="sxs-lookup"><span data-stu-id="4beae-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="4beae-109">您还可以使用连接器将邮件从 Microsoft 365路由到合作伙伴组织。</span><span class="sxs-lookup"><span data-stu-id="4beae-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="4beae-110">如果Microsoft 365无法通过连接器传递这些邮件，则这些邮件会排入队列Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4beae-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="4beae-111">Microsoft 365 24 小时内继续重试每封邮件的传递。</span><span class="sxs-lookup"><span data-stu-id="4beae-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="4beae-112">24 小时后，排队的邮件将过期，并且该邮件将在未送达报告（也称为 NDR 或退回邮件 (中返回到原始发件人) 。</span><span class="sxs-lookup"><span data-stu-id="4beae-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="4beae-113">Microsoft 365连接器无法传递邮件时，将生成错误。</span><span class="sxs-lookup"><span data-stu-id="4beae-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="4beae-114">本文介绍了最常见的错误及其解决方案。</span><span class="sxs-lookup"><span data-stu-id="4beae-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="4beae-115">通过连接器发送的未送达邮件的排队和通知错误统称为"邮件 _流智能"。_</span><span class="sxs-lookup"><span data-stu-id="4beae-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="4beae-116">错误代码：450 4.4.312 DNS 查询失败</span><span class="sxs-lookup"><span data-stu-id="4beae-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="4beae-117">通常，此错误Microsoft 365尝试连接到连接器中指定的智能主机，但查找智能主机 IP 地址的 DNS 查询失败。</span><span class="sxs-lookup"><span data-stu-id="4beae-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="4beae-118">导致此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="4beae-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="4beae-119">您的域的 DNS 托管服务存在 (维护您的域服务器的权威名称服务器的一) 。</span><span class="sxs-lookup"><span data-stu-id="4beae-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="4beae-120">您的域最近已过期，因此无法检索 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="4beae-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="4beae-121">您的域的 MX 记录最近已更改，并且 DNS 服务器以前仍缓存了您的域的 DNS 信息。</span><span class="sxs-lookup"><span data-stu-id="4beae-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="4beae-122">如何修复错误代码 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="4beae-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="4beae-123">使用 DNS 托管服务识别和修复域问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="4beae-124">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) 联系你的合作伙伴来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="4beae-125">错误代码：450 4.4.315 连接时间已过</span><span class="sxs-lookup"><span data-stu-id="4beae-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="4beae-126">通常，这意味着Microsoft 365无法连接到目标电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="4beae-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="4beae-127">错误详细信息将解释此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-127">The error details will explain the problem.</span></span> <span data-ttu-id="4beae-128">例如：</span><span class="sxs-lookup"><span data-stu-id="4beae-128">For example:</span></span>

- <span data-ttu-id="4beae-129">您的本地电子邮件服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="4beae-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="4beae-130">连接器的智能主机设置出错，Microsoft 365尝试连接到错误的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4beae-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="4beae-131">如何修复错误代码 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="4beae-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="4beae-132">了解适用于你的方案，并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="4beae-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="4beae-133">例如，如果邮件流一直运行正常，并且尚未更改连接器设置，则需要检查本地电子邮件环境以查看服务器是否关闭，或者是否对网络基础结构进行了任何更改 (例如，您更改了 Internet 服务提供商，因此您现在具有不同的 IP 地址) 。</span><span class="sxs-lookup"><span data-stu-id="4beae-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="4beae-134">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) 联系你的合作伙伴来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="4beae-135">错误代码：450 4.4.316 连接被拒绝</span><span class="sxs-lookup"><span data-stu-id="4beae-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="4beae-136">通常，此错误意味着Microsoft 365尝试连接到目标电子邮件服务器时遇到连接错误。</span><span class="sxs-lookup"><span data-stu-id="4beae-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="4beae-137">导致此错误的一个可能原因是防火墙阻止了来自 IP Microsoft 365连接。</span><span class="sxs-lookup"><span data-stu-id="4beae-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="4beae-138">或者，如果已完全将本地电子邮件系统迁移到本地电子邮件系统并关闭本地电子邮件环境，Microsoft 365错误。</span><span class="sxs-lookup"><span data-stu-id="4beae-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="4beae-139">如何修复错误代码 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="4beae-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="4beae-140">如果您的内部部署环境中有邮箱，则需要修改防火墙设置以允许从 TCP 端口 25 上的 Microsoft 365 IP 地址连接到内部部署电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="4beae-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="4beae-141">有关 IP 地址Microsoft 365，请参阅Microsoft 365 [URL 和 IP 地址范围](../../enterprise/urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="4beae-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="4beae-142">如果不应再将邮件传递到本地环境，请单击警报中的"立即修复"，Microsoft 365立即拒绝具有无效收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="4beae-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="4beae-143">这将降低超出组织对无效收件人的配额的风险，这可能会影响正常邮件传递。</span><span class="sxs-lookup"><span data-stu-id="4beae-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="4beae-144">或者，可以使用以下说明手动修复该问题：</span><span class="sxs-lookup"><span data-stu-id="4beae-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="4beae-145">在 Exchange 管理中心[ (EAC) ](/Exchange/exchange-admin-center)中，禁用或删除将电子邮件从 Microsoft 365 发送到本地电子邮件环境的连接器：</span><span class="sxs-lookup"><span data-stu-id="4beae-145">In the [Exchange admin center (EAC)](/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="4beae-146">在 EAC 中，转到"**邮件流** \> **""连接器"。**</span><span class="sxs-lookup"><span data-stu-id="4beae-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="4beae-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps：</span><span class="sxs-lookup"><span data-stu-id="4beae-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>
       - <span data-ttu-id="4beae-148">通过单击"删除 **""删除"** ![ 图标删除连接器](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="4beae-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>
       - <span data-ttu-id="4beae-149">通过单击"编辑 **编辑"** ![ 图标并 ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 清除" **打开"来禁用连接器**。</span><span class="sxs-lookup"><span data-stu-id="4beae-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="4beae-150">将与本地电子邮件环境Microsoft 365接受的域从"内部中继"更改为 **"权威"。** </span><span class="sxs-lookup"><span data-stu-id="4beae-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="4beae-151">有关说明，请参阅[管理 Exchange Online 中的接受Exchange Online。](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="4beae-151">For instructions, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="4beae-152">**注意**：通常，这些更改需要 30 分钟到 1 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="4beae-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="4beae-153">一小时后，请确认您不再收到该错误。</span><span class="sxs-lookup"><span data-stu-id="4beae-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="4beae-154">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="4beae-155">错误代码：450 4.4.317 无法连接到远程服务器</span><span class="sxs-lookup"><span data-stu-id="4beae-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="4beae-156">通常，此错误意味着Microsoft 365已连接到目标电子邮件服务器，但服务器立即响应错误，或不符合连接要求。</span><span class="sxs-lookup"><span data-stu-id="4beae-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="4beae-157">错误详细信息将解释此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-157">The error details will explain the problem.</span></span> <span data-ttu-id="4beae-158">例如：</span><span class="sxs-lookup"><span data-stu-id="4beae-158">For example:</span></span>

- <span data-ttu-id="4beae-159">目标电子邮件服务器响应了"服务不可用"错误，指示服务器无法与 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4beae-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>
- <span data-ttu-id="4beae-160">连接器配置为需要 TLS，但目标电子邮件服务器不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="4beae-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="4beae-161">如何修复错误代码 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="4beae-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="4beae-162">验证本地电子邮件服务器的 TLS 设置和证书，以及连接器上的 TLS 设置。</span><span class="sxs-lookup"><span data-stu-id="4beae-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>
- <span data-ttu-id="4beae-163">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="4beae-164">错误代码：450 4.4.318 连接突然关闭</span><span class="sxs-lookup"><span data-stu-id="4beae-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="4beae-165">通常，此错误意味着Microsoft 365本地电子邮件环境通信时遇到困难，因此连接已中断。</span><span class="sxs-lookup"><span data-stu-id="4beae-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="4beae-166">导致此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="4beae-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="4beae-167">防火墙使用 SMTP 数据包检查规则，这些规则无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="4beae-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>
- <span data-ttu-id="4beae-168">本地电子邮件服务器无法正常运行 (例如，服务挂起、崩溃或系统资源不足) 从而导致服务器出现问题并关闭与 Microsoft 365 的连接。</span><span class="sxs-lookup"><span data-stu-id="4beae-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>
- <span data-ttu-id="4beae-169">本地环境和本地环境之间存在网络Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4beae-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="4beae-170">如何修复错误代码 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="4beae-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="4beae-171">了解适用于你的方案，并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="4beae-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>
- <span data-ttu-id="4beae-172">如果问题由本地环境和本地环境之间的网络Microsoft 365，请与网络团队联系以解决问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>
- <span data-ttu-id="4beae-173">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="4beae-174">错误代码：450 4.7.320 证书验证失败</span><span class="sxs-lookup"><span data-stu-id="4beae-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="4beae-175">通常，此错误意味着Microsoft 365验证目标电子邮件服务器的证书时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="4beae-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="4beae-176">错误详细信息将解释此错误。</span><span class="sxs-lookup"><span data-stu-id="4beae-176">The error details will explain the error.</span></span> <span data-ttu-id="4beae-177">例如：</span><span class="sxs-lookup"><span data-stu-id="4beae-177">For example:</span></span>

- <span data-ttu-id="4beae-178">证书已过期</span><span class="sxs-lookup"><span data-stu-id="4beae-178">Certificate expired</span></span>
- <span data-ttu-id="4beae-179">证书主题不匹配</span><span class="sxs-lookup"><span data-stu-id="4beae-179">Certificate subject mismatch</span></span>
- <span data-ttu-id="4beae-180">证书不再有效</span><span class="sxs-lookup"><span data-stu-id="4beae-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="4beae-181">如何修复错误代码 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="4beae-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="4beae-182">修复连接器上的证书或设置，以便可以传递Microsoft 365排队的邮件。</span><span class="sxs-lookup"><span data-stu-id="4beae-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>
- <span data-ttu-id="4beae-183">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="4beae-184">其他错误代码</span><span class="sxs-lookup"><span data-stu-id="4beae-184">Other error codes</span></span>

<span data-ttu-id="4beae-185">Microsoft 365向本地或合作伙伴电子邮件服务器传递邮件时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="4beae-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="4beae-186">使用 **错误中的** "目标服务器信息"检查环境中的问题，或在出现配置错误时修改连接器。</span><span class="sxs-lookup"><span data-stu-id="4beae-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="4beae-187">如果错误来自你的合作伙伴组织 (例如，第三方云服务提供商) ，你需要联系你的合作伙伴来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="4beae-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
