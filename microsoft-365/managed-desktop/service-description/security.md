---
title: Microsoft 托管桌面的安全性
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866024"
---
# <a name="security-in-microsoft-managed-desktop"></a><span data-ttu-id="5c707-103">Microsoft 托管桌面的安全性</span><span class="sxs-lookup"><span data-stu-id="5c707-103">Security in Microsoft Managed Desktop</span></span>

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

<span data-ttu-id="5c707-p101">Microsoft 托管桌面应用一组标准的策略，并使用许多 Microsoft 技术，可帮助 Microsoft 托管桌面的安全设备、 存储的公司数据和详细信息。下面列出的区域的详细进一步：</span><span class="sxs-lookup"><span data-stu-id="5c707-p101">Microsoft Managed Desktop applies a standard set of policies and utilizes many Microsoft technologies to help secure Microsoft Managed Desktop devices, stored company data, and more. The areas listed below are detailed further:</span></span>  

- <span data-ttu-id="5c707-106">[数据安全性](#data-security)-由 Microsoft 托管桌面和安全地存储位置收集的数据类型</span><span class="sxs-lookup"><span data-stu-id="5c707-106">[Data security](#data-security) - types of data collected by Microsoft Managed Desktop and where it's securely stored</span></span>
- <span data-ttu-id="5c707-107">[设备安全](#device-security)– 安全和保护 Microsoft 托管桌面设备上</span><span class="sxs-lookup"><span data-stu-id="5c707-107">[Device security](#device-security) – security and protection on Microsoft Managed Desktop devices</span></span>
- <span data-ttu-id="5c707-108">[标识和访问管理](#identity-and-access-management)– 管理安全使用 Azure Active Directory 标识服务通过设备</span><span class="sxs-lookup"><span data-stu-id="5c707-108">[Identity and Access Management](#identity-and-access-management) – managing secure use of devices through Azure Active Directory identity services</span></span>
- <span data-ttu-id="5c707-109">[网络安全](#network-security)– VPN 信息和 Microsoft 托管桌面推荐的解决方案和设置</span><span class="sxs-lookup"><span data-stu-id="5c707-109">[Network security](#network-security) – VPN information and Microsoft Managed Desktop recommended solution and settings</span></span>
- <span data-ttu-id="5c707-110">[信息安全](#information-security)– 可选可用的服务，以进一步保护敏感信息</span><span class="sxs-lookup"><span data-stu-id="5c707-110">[Information security](#information-security) – optional available services to further protect sensitive information</span></span> 

## <a name="data-security"></a><span data-ttu-id="5c707-111">数据安全性</span><span class="sxs-lookup"><span data-stu-id="5c707-111">Data security</span></span>

<span data-ttu-id="5c707-112">从客户租户收集的数据 （以使 Microsoft 托管桌面 IT 服务和操作） 存储在 Microsoft 租户位于美国的 Azure SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="5c707-112">Data collected from customer tenants (which enables Microsoft Managed Desktop IT services and operations) is stored in Azure SQL databases in the Microsoft tenant hosted in the United States of America.</span></span>

<span data-ttu-id="5c707-113">有关详细信息，请参阅[Microsoft Azure security](https://docs.microsoft.com/azure/security/azure-database-security-overview)。</span><span class="sxs-lookup"><span data-stu-id="5c707-113">For more information, see [Microsoft Azure security](https://docs.microsoft.com/azure/security/azure-database-security-overview).</span></span>

<span data-ttu-id="5c707-114">下面列出了从您的租户传输的数据类型：</span><span class="sxs-lookup"><span data-stu-id="5c707-114">Listed below are the types of data transmitted from your tenant:</span></span>

- <span data-ttu-id="5c707-115">设备更新、 使用情况和可靠性数据</span><span class="sxs-lookup"><span data-stu-id="5c707-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="5c707-116">应用程序部署和可靠性数据</span><span class="sxs-lookup"><span data-stu-id="5c707-116">App deployment and reliability data</span></span>
- <span data-ttu-id="5c707-117">更新和安全策略部署数据</span><span class="sxs-lookup"><span data-stu-id="5c707-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="5c707-118">分配给设备的用户</span><span class="sxs-lookup"><span data-stu-id="5c707-118">Users assigned to devices</span></span>



## <a name="device-security"></a><span data-ttu-id="5c707-119">设备安全</span><span class="sxs-lookup"><span data-stu-id="5c707-119">Device security</span></span>

<span data-ttu-id="5c707-120">Microsoft 托管桌面可确保托管的所有设备安全和保护，并尽可能使用以下服务检测早地威胁：</span><span class="sxs-lookup"><span data-stu-id="5c707-120">Microsoft Managed Desktop ensures all managed devices are secured and protected, and detects threats as early as possible using the following services:</span></span>

<span data-ttu-id="5c707-121">服务</span><span class="sxs-lookup"><span data-stu-id="5c707-121">Service</span></span> | <span data-ttu-id="5c707-122">说明</span><span class="sxs-lookup"><span data-stu-id="5c707-122">Description</span></span>
--- | ---
<span data-ttu-id="5c707-123">防病毒</span><span class="sxs-lookup"><span data-stu-id="5c707-123">Antivirus</span></span> | <span data-ttu-id="5c707-124">安装和配置 Windows Defender AV</span><span class="sxs-lookup"><span data-stu-id="5c707-124">Windows Defender AV is installed and configured</span></span><br><span data-ttu-id="5c707-125">Windows Defender AV 定义是最新</span><span class="sxs-lookup"><span data-stu-id="5c707-125">Windows Defender AV definitions are up to date</span></span>
<span data-ttu-id="5c707-126">完整批量加密</span><span class="sxs-lookup"><span data-stu-id="5c707-126">Full Volume Encryption</span></span> |    <span data-ttu-id="5c707-127">Windows BitLocker 是 Microsoft 托管桌面设备批量加密解决方案。</span><span class="sxs-lookup"><span data-stu-id="5c707-127">Windows BitLocker is the volume encryption solution for Microsoft Managed Desktop devices.</span></span><br><br><span data-ttu-id="5c707-128">到服务 onboarded 组织后，将使用 Windows BitLocker 与内置信任平台模块 (TPM) 设备休眠模式中或关闭时，防止未授权的访问本地数据加密设备。</span><span class="sxs-lookup"><span data-stu-id="5c707-128">Once an organization is onboarded into the service, devices will be encrypted using Windows BitLocker with built-in Trust Platform Module (TPM) to prevent unauthorized access to local data when the device is in sleep mode, or off.</span></span> 
<span data-ttu-id="5c707-129">监视</span><span class="sxs-lookup"><span data-stu-id="5c707-129">Monitoring</span></span> |    <span data-ttu-id="5c707-p102">Windows Defender 高级威胁保护 (Windows Defender ATP) 用于跨所有 Microsoft 托管桌面设备的安全威胁监视。Windows Defender ATP 允许企业客户检测、 调查和响应公司网络中的高级威胁。有关详细信息，请参阅[Windows Defender 高级威胁保护。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="5c707-p102">Windows Defender Advanced Threat Protection (Windows Defender ATP) is used for security threat monitoring across all Microsoft Managed Desktop devices. Windows Defender ATP allows enterprise customers to detect, investigate, and respond to advanced threats in their corporate network. For more information, see [Windows Defender Advanced Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span></span> 
<span data-ttu-id="5c707-133">软件更新</span><span class="sxs-lookup"><span data-stu-id="5c707-133">Software updates</span></span> |  <span data-ttu-id="5c707-134">Microsoft 托管桌面设备始终安全使用最新的安全更新。</span><span class="sxs-lookup"><span data-stu-id="5c707-134">Microsoft Managed Desktop devices are always secured with the latest security updates.</span></span>
<span data-ttu-id="5c707-135">安全的设备配置</span><span class="sxs-lookup"><span data-stu-id="5c707-135">Secure Device Configuration</span></span> |   <span data-ttu-id="5c707-p103">Microsoft 托管桌面实现 Microsoft 安全基准。有关详细信息，请参阅[Windows 安全基准。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="5c707-p103">Microsoft Managed Desktop implements the Microsoft Security Baseline. For more information, see [Windows security baselines.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)</span></span>



## <a name="identity-and-access-management"></a><span data-ttu-id="5c707-138">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="5c707-138">Identity and access management</span></span>

<span data-ttu-id="5c707-p104">标识和访问管理保护公司资产和关键业务数据。Microsoft 托管桌面配置设备，以确保安全使用 Azure Active Directory (Azure AD) 托管标识。它是客户的责任维护其 Azure AD 租户中的准确信息。</span><span class="sxs-lookup"><span data-stu-id="5c707-p104">Identity and access management protects corporate assets and business-critical data. Microsoft Managed Desktop configures devices to ensure secure use with Azure Active Directory (Azure AD) managed identities. It is the customer's responsibility to maintain accurate information in their Azure AD tenant.</span></span> 

<span data-ttu-id="5c707-142">服务</span><span class="sxs-lookup"><span data-stu-id="5c707-142">Service</span></span> | <span data-ttu-id="5c707-143">说明</span><span class="sxs-lookup"><span data-stu-id="5c707-143">Description</span></span>
--- | ---
<span data-ttu-id="5c707-144">生物身份验证</span><span class="sxs-lookup"><span data-stu-id="5c707-144">Biometric Authentication</span></span> |  <span data-ttu-id="5c707-p105">Windows Hello 允许用户使用其表面或 PIN，进行更加复杂忘记或窃取密码登录。有关详细信息，请参阅[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span><span class="sxs-lookup"><span data-stu-id="5c707-p105">Windows Hello allows users to login using their face or a PIN, making passwords harder to forget or steal. For more information, see [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span></span>
<span data-ttu-id="5c707-147">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="5c707-147">Multi-factor authentication</span></span> | <span data-ttu-id="5c707-148">Azure 多因素身份验证更紧密通过提供良好，自助服务密码重置为使用移动电话，身份验证的其他级别控制对敏感函数 Microsoft 托管桌面服务的访问。</span><span class="sxs-lookup"><span data-stu-id="5c707-148">Azure multi-factor authentication more tightly controls access to sensitive functions of the Microsoft Managed Desktop service by providing an additional level of authentication using a mobile phone, as well as self-service password reset.</span></span> 
<span data-ttu-id="5c707-149">标准用户权限</span><span class="sxs-lookup"><span data-stu-id="5c707-149">Standard user permission</span></span> |  <span data-ttu-id="5c707-p106">保护系统，并使其更安全，用户将分配标准用户权限。这被分配的 Windows 自动执行某些操作的全新体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="5c707-p106">To protect the system and make it more secure, the user will be assigned Standard User Permissions. This is assigned as part of the Windows Autopilot out-of-box experience.</span></span>



## <a name="network-security"></a><span data-ttu-id="5c707-152">网络安全</span><span class="sxs-lookup"><span data-stu-id="5c707-152">Network security</span></span>

<span data-ttu-id="5c707-153">客户负责网络安全。</span><span class="sxs-lookup"><span data-stu-id="5c707-153">Customers are responsible for network security.</span></span> 

<span data-ttu-id="5c707-154">服务</span><span class="sxs-lookup"><span data-stu-id="5c707-154">Service</span></span> | <span data-ttu-id="5c707-155">说明</span><span class="sxs-lookup"><span data-stu-id="5c707-155">Description</span></span>
--- | ---
<span data-ttu-id="5c707-156">VPN</span><span class="sxs-lookup"><span data-stu-id="5c707-156">VPN</span></span> | <span data-ttu-id="5c707-157">客户拥有其 VPN 基础结构，以确保可以 intranet 外部公开有限的企业资源。</span><span class="sxs-lookup"><span data-stu-id="5c707-157">Customers own their VPN infrastructure, to ensure limited corporate resources can be exposed outside the intranet.</span></span><br><br><span data-ttu-id="5c707-p107">最低要求： Microsoft 托管桌面需要 Windows 10 兼容和支持 VPN 解决方案。如果您的组织需要 VPN 解决方案，它需要支持 Windows 10 并且已打包和可通过 Intune 部署。有关详细信息，请联系您软件发行者。</span><span class="sxs-lookup"><span data-stu-id="5c707-p107">Minimum requirement: Microsoft Managed Desktop requires a Windows 10 compatible and supported VPN solution. If your organization needs a VPN solution, it needs to support Windows 10 and be packaged and deployable through Intune. Contact your software publisher for more information.</span></span><br><br><span data-ttu-id="5c707-161">建议：</span><span class="sxs-lookup"><span data-stu-id="5c707-161">Recommendation:</span></span><br><span data-ttu-id="5c707-p108">-Microsoft 建议无法轻松地部署通过 Intune 到推送 VPN 配置文件的现代 VPN 解决方案。这样，始终可用的、 无缝、 可靠，安全地访问企业网络。有关详细信息，请参阅[[VPN 设置 Intune]](https://docs.microsoft.com/intune/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="5c707-p108">- Microsoft recommends a modern VPN solution that could be easily deployed through Intune to push VPN profiles. This provides an always-on, seamless, reliable, and secure way to access corporate network. For more information, see [[VPN settings in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).</span></span><br><span data-ttu-id="5c707-165">-粗 VPN 客户端或旧 VPN 客户端，不建议使用由 Microsoft 同时使用 Microsoft 托管桌面，因为它会影响最终用户环境。</span><span class="sxs-lookup"><span data-stu-id="5c707-165">- Thick VPN clients, or legacy VPN clients, are not recommended by Microsoft while using Microsoft Managed Desktop as it can impact the end-user environment.</span></span><br><span data-ttu-id="5c707-166">-Microsoft 建议的传出的 web 流量转直接到 Internet，而不经由 VPN 以避免任何性能问题。</span><span class="sxs-lookup"><span data-stu-id="5c707-166">- Microsoft recommends that the outgoing web traffic goes directly to Internet without going through the VPN to avoid any performance issues.</span></span><br><span data-ttu-id="5c707-167">-理想情况下，Microsoft 建议使用 Azure Active Directory 应用程序代理，而不是 VPN。</span><span class="sxs-lookup"><span data-stu-id="5c707-167">- Ideally, Microsoft recommends the use of Azure Active Directory App Proxy instead of a VPN.</span></span>


## <a name="information-security"></a><span data-ttu-id="5c707-168">信息安全</span><span class="sxs-lookup"><span data-stu-id="5c707-168">Information security</span></span>

<span data-ttu-id="5c707-169">客户可以配置这些可选的服务，以帮助保护企业高价值资产。</span><span class="sxs-lookup"><span data-stu-id="5c707-169">Customers may configure these optional services to help protect corporate high-value assets.</span></span> 

<span data-ttu-id="5c707-170">服务</span><span class="sxs-lookup"><span data-stu-id="5c707-170">Service</span></span> | <span data-ttu-id="5c707-171">说明</span><span class="sxs-lookup"><span data-stu-id="5c707-171">Description</span></span>
--- | ---
<span data-ttu-id="5c707-172">数据恢复</span><span class="sxs-lookup"><span data-stu-id="5c707-172">Data recovery</span></span>  | <span data-ttu-id="5c707-p109">到 OneDrive for Business 备份存储在设备上的密钥文件夹中的信息。Microsoft 托管桌面不负责使用 OneDrive for Business 同步的数据。</span><span class="sxs-lookup"><span data-stu-id="5c707-p109">Information stored in key folders on the device is backed up to OneDrive for Business. Microsoft Managed Desktop is not responsible for data that isn’t synchronized with OneDrive for Business.</span></span> 
<span data-ttu-id="5c707-175">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="5c707-175">Windows Information Protection</span></span> |    <span data-ttu-id="5c707-176">对于需要高级别的信息安全性的公司，我们建议[Windows 信息保护](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)和[Azure Information Protection。](https://www.microsoft.com/cloud-platform/azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="5c707-176">For companies that require high levels of information security, we recommend [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) and [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection).</span></span> 

