---
title: Office 365 DoD DNS 记录
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要：DoD Office 365 DNS 记录
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687801"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="2fcc3-103">Office 365 DoD DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2fcc3-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="2fcc3-104">*本文适用于 doD Office 365 doD Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="2fcc3-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="2fcc3-105">作为加入 DoD Office 365的一部分，您需要将 SMTP 和 SIP 域添加到联机服务租户。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="2fcc3-106">你将使用 Azure AD PowerShell 中的 New-MsolDomain cmdlet 完成此操作，或使用 [Azure](https://portal.azure.us) 政府门户启动添加域和证明所有权的过程。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="2fcc3-107">将域添加到租户并进行验证后，请使用以下指南为以下服务添加相应的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="2fcc3-108">您可能需要修改下表，以满足组织对入站 MX 记录 (s) 以及您已有的任何现有 Exchange 自动发现 () 的需求。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="2fcc3-109">我们强烈建议与邮件团队协调这些 DNS 记录，以避免电子邮件出现任何中断或错误传递。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="2fcc3-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2fcc3-110">Exchange Online</span></span>

| <span data-ttu-id="2fcc3-111">类型</span><span class="sxs-lookup"><span data-stu-id="2fcc3-111">Type</span></span> | <span data-ttu-id="2fcc3-112">优先级</span><span class="sxs-lookup"><span data-stu-id="2fcc3-112">Priority</span></span> | <span data-ttu-id="2fcc3-113">主机名</span><span class="sxs-lookup"><span data-stu-id="2fcc3-113">Host name</span></span> | <span data-ttu-id="2fcc3-114">指向地址或值</span><span class="sxs-lookup"><span data-stu-id="2fcc3-114">Points to address or value</span></span> | <span data-ttu-id="2fcc3-115">TTL</span><span class="sxs-lookup"><span data-stu-id="2fcc3-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="2fcc3-116">MX</span><span class="sxs-lookup"><span data-stu-id="2fcc3-116">MX</span></span> | <span data-ttu-id="2fcc3-117">0</span><span class="sxs-lookup"><span data-stu-id="2fcc3-117">0</span></span> | @ | <span data-ttu-id="2fcc3-118">*tenant*.mail.protection.office365.us (请参阅下文了解其他详细信息) </span><span class="sxs-lookup"><span data-stu-id="2fcc3-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="2fcc3-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2fcc3-119">1 Hour</span></span> |
| <span data-ttu-id="2fcc3-120">TXT</span><span class="sxs-lookup"><span data-stu-id="2fcc3-120">TXT</span></span> | - | @ | <span data-ttu-id="2fcc3-121">v=spf1 include：spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="2fcc3-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="2fcc3-122">1 小时</span><span class="sxs-lookup"><span data-stu-id="2fcc3-122">1 Hour</span></span> |
| <span data-ttu-id="2fcc3-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fcc3-123">CNAME</span></span> | - | <span data-ttu-id="2fcc3-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2fcc3-124">autodiscover</span></span> | <span data-ttu-id="2fcc3-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="2fcc3-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="2fcc3-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2fcc3-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="2fcc3-127">Exchange自动发现记录</span><span class="sxs-lookup"><span data-stu-id="2fcc3-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="2fcc3-128">如果在本地Exchange Server，我们建议在迁移到 Exchange Online 时保留现有记录，并完成迁移后更新该记录。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="2fcc3-129">Exchange OnlineMX 记录</span><span class="sxs-lookup"><span data-stu-id="2fcc3-129">Exchange Online MX Record</span></span>

<span data-ttu-id="2fcc3-130">接受域的 MX 记录值遵循上述标准格式 *：tenant*.mail.protection.office365.us，将 *租户* 替换为默认租户名称的第一部分。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="2fcc3-131">例如，如果你的租户名称 contoso.onmicrosoft.us，你将使用 contoso.mail.protection.office365.us **作为** MX 记录的值。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="2fcc3-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2fcc3-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="2fcc3-133">CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="2fcc3-133">CNAME records</span></span>

| <span data-ttu-id="2fcc3-134">类型</span><span class="sxs-lookup"><span data-stu-id="2fcc3-134">Type</span></span> | <span data-ttu-id="2fcc3-135">主机名</span><span class="sxs-lookup"><span data-stu-id="2fcc3-135">Host name</span></span> | <span data-ttu-id="2fcc3-136">指向地址或值</span><span class="sxs-lookup"><span data-stu-id="2fcc3-136">Points to address or value</span></span> | <span data-ttu-id="2fcc3-137">TTL</span><span class="sxs-lookup"><span data-stu-id="2fcc3-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="2fcc3-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fcc3-138">CNAME</span></span> | <span data-ttu-id="2fcc3-139">sip</span><span class="sxs-lookup"><span data-stu-id="2fcc3-139">sip</span></span> | <span data-ttu-id="2fcc3-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2fcc3-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="2fcc3-141">1 小时</span><span class="sxs-lookup"><span data-stu-id="2fcc3-141">1 Hour</span></span> |
| <span data-ttu-id="2fcc3-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="2fcc3-142">CNAME</span></span> | <span data-ttu-id="2fcc3-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2fcc3-143">lyncdiscover</span></span> | <span data-ttu-id="2fcc3-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2fcc3-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="2fcc3-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2fcc3-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="2fcc3-146">SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2fcc3-146">SRV records</span></span>

| <span data-ttu-id="2fcc3-147">类型</span><span class="sxs-lookup"><span data-stu-id="2fcc3-147">Type</span></span> | <span data-ttu-id="2fcc3-148">服务</span><span class="sxs-lookup"><span data-stu-id="2fcc3-148">Service</span></span> | <span data-ttu-id="2fcc3-149">协议</span><span class="sxs-lookup"><span data-stu-id="2fcc3-149">Protocol</span></span> | <span data-ttu-id="2fcc3-150">端口</span><span class="sxs-lookup"><span data-stu-id="2fcc3-150">Port</span></span> | <span data-ttu-id="2fcc3-151">粗细</span><span class="sxs-lookup"><span data-stu-id="2fcc3-151">Weight</span></span> | <span data-ttu-id="2fcc3-152">优先级</span><span class="sxs-lookup"><span data-stu-id="2fcc3-152">Priority</span></span> | <span data-ttu-id="2fcc3-153">名称</span><span class="sxs-lookup"><span data-stu-id="2fcc3-153">Name</span></span> | <span data-ttu-id="2fcc3-154">Target</span><span class="sxs-lookup"><span data-stu-id="2fcc3-154">Target</span></span> | <span data-ttu-id="2fcc3-155">TTL</span><span class="sxs-lookup"><span data-stu-id="2fcc3-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="2fcc3-156">SRV</span><span class="sxs-lookup"><span data-stu-id="2fcc3-156">SRV</span></span> | <span data-ttu-id="2fcc3-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="2fcc3-157">\_sip</span></span> | <span data-ttu-id="2fcc3-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="2fcc3-158">\_tls</span></span> | <span data-ttu-id="2fcc3-159">443</span><span class="sxs-lookup"><span data-stu-id="2fcc3-159">443</span></span> | <span data-ttu-id="2fcc3-160">1</span><span class="sxs-lookup"><span data-stu-id="2fcc3-160">1</span></span> | <span data-ttu-id="2fcc3-161">100</span><span class="sxs-lookup"><span data-stu-id="2fcc3-161">100</span></span> | @ | <span data-ttu-id="2fcc3-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2fcc3-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="2fcc3-163">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2fcc3-163">1 Hour</span></span> |
| <span data-ttu-id="2fcc3-164">SRV</span><span class="sxs-lookup"><span data-stu-id="2fcc3-164">SRV</span></span> | <span data-ttu-id="2fcc3-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2fcc3-165">\_sipfederationtls</span></span> | <span data-ttu-id="2fcc3-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="2fcc3-166">\_tcp</span></span> | <span data-ttu-id="2fcc3-167">5061</span><span class="sxs-lookup"><span data-stu-id="2fcc3-167">5061</span></span> | <span data-ttu-id="2fcc3-168">1</span><span class="sxs-lookup"><span data-stu-id="2fcc3-168">1</span></span> | <span data-ttu-id="2fcc3-169">100</span><span class="sxs-lookup"><span data-stu-id="2fcc3-169">100</span></span> | @ | <span data-ttu-id="2fcc3-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2fcc3-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="2fcc3-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2fcc3-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="2fcc3-172">其他 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2fcc3-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fcc3-173">如果 DNS 区域中已有 *msoid* CNAME 记录，则此时必须从 DNS 中删除该记录。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="2fcc3-174">msoid 记录与以前Microsoft 365 企业版应用程序 (*应用程序* Office 365 专业增强版) ，并且将阻止激活成功。</span><span class="sxs-lookup"><span data-stu-id="2fcc3-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
