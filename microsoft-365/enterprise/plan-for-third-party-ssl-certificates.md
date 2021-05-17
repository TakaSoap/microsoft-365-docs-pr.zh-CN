---
title: 规划 Microsoft 365 的第三方 SSL 证书
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 摘要：介绍了本地和混合Exchange SSO、使用 AD FS 的 SSO、Exchange Online 服务和 Exchange 所需的 SSL 证书。
ms.openlocfilehash: f2505a40e87ab36c96c0ed24514420b56d1479d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927484"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a><span data-ttu-id="c364c-103">规划 Microsoft 365 的第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="c364c-103">Plan for third-party SSL certificates for Microsoft 365</span></span>

<span data-ttu-id="c364c-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="c364c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c364c-105">若要加密客户端和 Microsoft 365 环境之间的通信，必须在基础结构服务器上安装第三 (SSL) 证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-105">To encrypt communications between your clients and the Microsoft 365 environment, third-party Secure Socket Layer (SSL) certificates must be installed on your infrastructure servers.</span></span>

<span data-ttu-id="c364c-106">本文是 Network [planning and performance tuning for Microsoft 365 的一部分](./network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="c364c-106">This article is part of [Network planning and performance tuning for Microsoft 365](./network-planning-and-performance.md).</span></span>
   
<span data-ttu-id="c364c-107">以下组件需要证书Microsoft 365证书：</span><span class="sxs-lookup"><span data-stu-id="c364c-107">Certificates are required for the following Microsoft 365 components:</span></span>
  
- <span data-ttu-id="c364c-108">本地 Exchange</span><span class="sxs-lookup"><span data-stu-id="c364c-108">Exchange on-premises</span></span>
    
- <span data-ttu-id="c364c-109">Active Directory 联合身份验证 (联合身份验证)  (AD FS) 联合服务器和 AD FS 联合服务器代理 (单一登录) </span><span class="sxs-lookup"><span data-stu-id="c364c-109">Single sign-on (SSO) (for both the Active Directory Federation Services (AD FS) federation servers and AD FS federation server proxies)</span></span>
    
- <span data-ttu-id="c364c-110">Exchange Online服务，如自动发现、Outlook Anywhere 和 Exchange Web 服务</span><span class="sxs-lookup"><span data-stu-id="c364c-110">Exchange Online services, such as Autodiscover, Outlook Anywhere, and Exchange Web Services</span></span>
    
- <span data-ttu-id="c364c-111">Exchange混合服务器</span><span class="sxs-lookup"><span data-stu-id="c364c-111">Exchange hybrid server</span></span>
    
## <a name="certificates-for-exchange-on-premises"></a><span data-ttu-id="c364c-112">本地Exchange证书</span><span class="sxs-lookup"><span data-stu-id="c364c-112">Certificates for Exchange On-Premises</span></span>

<span data-ttu-id="c364c-113">有关如何使用数字证书确保内部部署组织与 Exchange之间的通信安全的Exchange Online，请参阅 TechNet 文章[了解证书要求](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141))。</span><span class="sxs-lookup"><span data-stu-id="c364c-113">For an overview about how to use digital certificates to make the communication between the on-premises Exchange organization and Exchange Online secure, see the TechNet article [Understanding Certificate Requirements](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141)).</span></span>
  
## <a name="certificates-for-single-sign-on"></a><span data-ttu-id="c364c-114">单一登录的证书</span><span class="sxs-lookup"><span data-stu-id="c364c-114">Certificates for Single Sign-On</span></span>

<span data-ttu-id="c364c-115">若要为用户提供包含强大安全性的简化单一登录体验，在联合服务器或联合服务器代理上需要下表中所示的证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-115">To provide your users with a simplified single sign-on experience that includes robust security, the certificates shown in the following table are required on either the federation servers or the federation server proxies.</span></span> <span data-ttu-id="c364c-116">下表重点介绍 Active Directory 联合身份验证服务 (AD FS) ，我们还提供有关使用第三方标识 [提供程序的详细信息](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="c364c-116">The table below focuses on Active Directory Federation Services (AD FS), we also have more information on [using third-party identity providers](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).</span></span>
  
| <span data-ttu-id="c364c-117">证书类型</span><span class="sxs-lookup"><span data-stu-id="c364c-117">Certificate Type</span></span> | <span data-ttu-id="c364c-118">说明</span><span class="sxs-lookup"><span data-stu-id="c364c-118">Description</span></span> | <span data-ttu-id="c364c-119">部署之前需要知道哪些内容</span><span class="sxs-lookup"><span data-stu-id="c364c-119">What you need to know before you deploy</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="c364c-120">**SSL 证书 (也称为服务器身份验证证书)**</span><span class="sxs-lookup"><span data-stu-id="c364c-120">**SSL certificate (also called a server authentication certificate)**</span></span> <br/> |<span data-ttu-id="c364c-121">这是一个标准 SSL 证书，用于保护联合服务器、客户端和联合服务器代理服务器之间的通信安全。</span><span class="sxs-lookup"><span data-stu-id="c364c-121">This is a standard SSL certificate that is used to make communications between federation servers, clients, and federation server proxy computers secure.</span></span>  <br/> |<span data-ttu-id="c364c-122">AD FS 需要 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-122">AD FS requires an SSL certificate.</span></span> <span data-ttu-id="c364c-123">默认情况下，AD FS 使用为 IIS 服务中的默认网站Internet Information Services (SSL) 。</span><span class="sxs-lookup"><span data-stu-id="c364c-123">By default, AD FS uses the SSL certificate that is configured for the default website in Internet Information Services (IIS).</span></span>  <br/> <span data-ttu-id="c364c-124">此 SSL 证书的主题名称用于确定您部署的每个 AD FS (FS) 联合身份验证服务名称。</span><span class="sxs-lookup"><span data-stu-id="c364c-124">The subject name of this SSL certificate is used to determine the Federation Service (FS) name for each instance of AD FS that you deploy.</span></span> <span data-ttu-id="c364c-125">请考虑为 CA 颁发的 (颁发机构) 一个主题名称，该证书最代表要注册的公司或Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c364c-125">Consider choosing a subject name for any new certification authority (CA)-issued certificates that best represents the name of your company or organization to Microsoft 365.</span></span> <span data-ttu-id="c364c-126">此名称必须可 Internet 路由。</span><span class="sxs-lookup"><span data-stu-id="c364c-126">This name must be Internet-routable.</span></span>  <br/><span data-ttu-id="c364c-127">**警告：** AD FS 要求此 SSL 证书在主题名称 (短) 无点。</span><span class="sxs-lookup"><span data-stu-id="c364c-127">**Caution:** AD FS requires that this SSL certificate have no dotless (short-name) subject name.</span></span>          <br/> <span data-ttu-id="c364c-128">**建议：** 由于 AD FS 的客户端必须信任此证书，因此建议使用由公共 (第三方) CA 或附属于公共受信任根的 CA 颁发的 SSL 证书;例如，VeriSign 或 Thawte。</span><span class="sxs-lookup"><span data-stu-id="c364c-128">**Recommendation:** Because this certificate must be trusted by clients of AD FS, we recommend that you use an SSL certificate issued by a public (third-party) CA or by a CA that is subordinate to a publicly trusted root; for example, VeriSign or Thawte.</span></span>  <br/> |
|<span data-ttu-id="c364c-129">**令牌签名证书**</span><span class="sxs-lookup"><span data-stu-id="c364c-129">**Token-signing certificate**</span></span> <br/> |<span data-ttu-id="c364c-130">这是一个标准的 X.509 证书，用于对联合服务器颁发的所有令牌进行安全签名，Microsoft 365验证。</span><span class="sxs-lookup"><span data-stu-id="c364c-130">This is a standard X.509 certificate that's used for securely signing all tokens that the federation server issues and that Microsoft 365 accepts and validates.</span></span>  <br/> |<span data-ttu-id="c364c-131">令牌签名证书必须包含一个私钥，该私钥与 FS 中的受信任根进行链连接。</span><span class="sxs-lookup"><span data-stu-id="c364c-131">The token-signing certificate must contain a private key that chains to a trusted root in the FS.</span></span> <span data-ttu-id="c364c-132">默认情况下，AD FS 创建自签名证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-132">By default, AD FS creates a self-signed certificate.</span></span> <span data-ttu-id="c364c-133">但是，根据组织的需要，您可以使用 AD FS 管理单元，将此证书更改为 CA 颁发的证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-133">However, depending on the needs of your organization, you can change this certificate to a CA-issued certificate by using the AD FS management snap-in.</span></span>  <br/><span data-ttu-id="c364c-134">**警告：** 令牌签名证书对 FS 的稳定性至关重要。</span><span class="sxs-lookup"><span data-stu-id="c364c-134">**Caution:** The token-signing certificate is critical to the stability of the FS.</span></span> <span data-ttu-id="c364c-135">如果证书发生更改，则必须Microsoft 365更改通知用户。</span><span class="sxs-lookup"><span data-stu-id="c364c-135">If the certificate is changed, Microsoft 365 must be notified of the change.</span></span> <span data-ttu-id="c364c-136">如果未提供通知，则用户无法登录其Microsoft 365服务产品。</span><span class="sxs-lookup"><span data-stu-id="c364c-136">If notification is not provided, users can't sign in to their Microsoft 365 service offerings.</span></span><br/><span data-ttu-id="c364c-137">**建议：** 建议使用 AD FS 生成的自签名令牌签名证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-137">**Recommendation:** We recommend that you use the self-signed token-signing certificate that is generated by AD FS.</span></span> <span data-ttu-id="c364c-138">通过执行此操作，它默认为您管理此证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-138">By doing so, it manages this certificate for you by default.</span></span> <span data-ttu-id="c364c-139">例如，当此证书即将过期时，AD FS 将生成一个新的自签名证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-139">For example, when this certificate is about to expire, AD FS will generate a new self-signed certificate.</span></span>  <br/> |
   
<span data-ttu-id="c364c-140">联合服务器代理需要下表中描述的证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-140">Federation server proxies require the certificate that is described in the following table.</span></span>
  
| <span data-ttu-id="c364c-141">证书类型</span><span class="sxs-lookup"><span data-stu-id="c364c-141">Certificate Type</span></span> | <span data-ttu-id="c364c-142">说明</span><span class="sxs-lookup"><span data-stu-id="c364c-142">Description</span></span> | <span data-ttu-id="c364c-143">部署之前需要知道哪些内容</span><span class="sxs-lookup"><span data-stu-id="c364c-143">What you need to know before you deploy</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="c364c-144">SSL 证书</span><span class="sxs-lookup"><span data-stu-id="c364c-144">SSL certificate</span></span>  <br/> |<span data-ttu-id="c364c-145">这是一个标准 SSL 证书，用于保护联合服务器、联合服务器代理和 Internet 客户端计算机之间的通信。</span><span class="sxs-lookup"><span data-stu-id="c364c-145">This is a standard SSL certificate that is used for securing communications between a federation server, a federation server proxy, and Internet client computers.</span></span>  <br/> |<span data-ttu-id="c364c-146">必须先将此 SSL 证书绑定到 IIS 中的默认网站，然后才能成功运行 AD FS 联合服务器代理配置向导。</span><span class="sxs-lookup"><span data-stu-id="c364c-146">This SSL certificate must be bound to the default website in IIS before you can successfully run the AD FS Federation Server Proxy Configuration wizard.</span></span>  <br/> <span data-ttu-id="c364c-147">此证书的主题名称必须与在企业网络中联合服务器上配置的 SSL 证书相同。</span><span class="sxs-lookup"><span data-stu-id="c364c-147">This certificate must have the same subject name as the SSL certificate that was configured on the federation server in the corporate network.</span></span>  <br/> <span data-ttu-id="c364c-148">**建议：** 建议您使用此联合服务器代理连接到的联盟服务器上配置的相同服务器身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-148">**Recommendation:** We recommend that you use the same server authentication certificate that is configured on the federation server that this federation server proxy connects to.</span></span>  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a><span data-ttu-id="c364c-149">用于自动发现、Outlook和 Active Directory 同步的证书</span><span class="sxs-lookup"><span data-stu-id="c364c-149">Certificates for Autodiscover, Outlook Anywhere, and Active Directory Synchronization</span></span>

<span data-ttu-id="c364c-150">面向外部的 Exchange 2013、Exchange 2010、Exchange 2007 和 Exchange 2003 客户端访问服务器 (CAS) 需要第三方 SSL 证书，用于自动发现、Outlook Anywhere 和 Active Directory 同步服务的安全连接。</span><span class="sxs-lookup"><span data-stu-id="c364c-150">Your external-facing Exchange 2013, Exchange 2010, Exchange 2007, and Exchange 2003 Client Access servers (CASs) require a third-party SSL certificate for secure connections for Autodiscover, Outlook Anywhere, and Active Directory synchronization services.</span></span> <span data-ttu-id="c364c-151">您可能已经在本地环境中安装了此证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-151">You may already have this certificate installed in your on-premises environment.</span></span>
  
## <a name="certificate-for-an-exchange-hybrid-server"></a><span data-ttu-id="c364c-152">混合服务器的Exchange证书</span><span class="sxs-lookup"><span data-stu-id="c364c-152">Certificate for an Exchange Hybrid Server</span></span>

<span data-ttu-id="c364c-153">面向外部的Exchange混合服务器需要第三方 SSL 证书，以确保与 Exchange Online 服务的安全连接。</span><span class="sxs-lookup"><span data-stu-id="c364c-153">Your external-facing Exchange hybrid server or servers require a third-party SSL certificate for secure connectivity with the Exchange Online service.</span></span> <span data-ttu-id="c364c-154">您需要从第三方 SSL 提供程序获取此证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-154">You need to get this certificate from your third-party SSL provider.</span></span>
  
## <a name="microsoft-365-certificate-chains"></a><span data-ttu-id="c364c-155">Microsoft 365证书链</span><span class="sxs-lookup"><span data-stu-id="c364c-155">Microsoft 365 Certificate Chains</span></span>

<span data-ttu-id="c364c-156">本文介绍了在基础结构上可能需要安装的证书。</span><span class="sxs-lookup"><span data-stu-id="c364c-156">This article describes the certificates you may need to install on your infrastructure.</span></span> <span data-ttu-id="c364c-157">有关安装在 Microsoft 365 服务器中的证书Microsoft 365[证书链。](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)</span><span class="sxs-lookup"><span data-stu-id="c364c-157">For more information on the certificates installed on our Microsoft 365 servers, see [Microsoft 365 Certificate Chains](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c364c-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c364c-158">See also</span></span>

[<span data-ttu-id="c364c-159">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="c364c-159">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)