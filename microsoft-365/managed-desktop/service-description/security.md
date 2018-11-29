---
title: Microsoft 托管桌面的安全性
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866024"
---
# <a name="security-in-microsoft-managed-desktop"></a><span data-ttu-id="8d7ff-103">Microsoft 托管桌面的安全性</span><span class="sxs-lookup"><span data-stu-id="8d7ff-103">Security in Microsoft Managed Desktop</span></span>

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

<span data-ttu-id="8d7ff-p101">通过使用许多 Microsoft 技术，我们可以确保 Microsoft 托管桌面设备的安全和 Microsoft 托管桌面安全运营团队可以阻止、 检测和响应高级威胁。不允许第三方安全产品、 应用程序和服务。Microsoft 将应用标准策略基准，以确保设备、 标识、 网络和企业数据安全，并受保护。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p101">By using many Microsoft technologies, we can ensure that Microsoft Managed Desktop devices are secure and that the Microsoft Managed Desktop security ops team can prevent, detect, and respond to advanced threats. Third-party security products, apps, and services are not allowed. Microsoft will apply a standard policy baseline to ensure devices, identity, network, and corporate data are secured and protected.</span></span>

<span data-ttu-id="8d7ff-107">以下各节记录了安全实施这些类别：</span><span class="sxs-lookup"><span data-stu-id="8d7ff-107">These categories of security enforcement are documented in the following sections:</span></span>

- <span data-ttu-id="8d7ff-108">[数据安全性](#data-security)-我们如何确保您的数据存储，并且符合要求的 Azure 安全定位</span><span class="sxs-lookup"><span data-stu-id="8d7ff-108">[Data security](#data-security) - how we ensure your data is stored and meets requirements for Azure security positioning</span></span>
- <span data-ttu-id="8d7ff-109">[设备安全](#device-security)– 我们如何确保 Microsoft 托管桌面设备的安全</span><span class="sxs-lookup"><span data-stu-id="8d7ff-109">[Device security](#device-security) – how we ensure Microsoft Managed Desktop devices are secure</span></span>
- <span data-ttu-id="8d7ff-110">[标识安全性](#identity-security)– 我们如何确保现代工作区中的用户不泄漏</span><span class="sxs-lookup"><span data-stu-id="8d7ff-110">[Identity security](#identity-security) – how we ensure users in the modern workplace are not compromised</span></span>
- <span data-ttu-id="8d7ff-111">[网络安全](#network-security)– 我们如何确保安全访问公司资源</span><span class="sxs-lookup"><span data-stu-id="8d7ff-111">[Network security](#network-security) – how we ensure a secure access to corporate resources</span></span>
- <span data-ttu-id="8d7ff-112">[信息安全](#information-security)– 我们如何确保企业数据是安全</span><span class="sxs-lookup"><span data-stu-id="8d7ff-112">[Information security](#information-security) – how we ensure corporate data is secure</span></span>
- <span data-ttu-id="8d7ff-113">[特权的帐户访问](#privileged-account-access)-我们限制的访问</span><span class="sxs-lookup"><span data-stu-id="8d7ff-113">[Privileged account access](#privileged-account-access) - how we restrict access</span></span>

## <a name="data-security"></a><span data-ttu-id="8d7ff-114">数据安全性</span><span class="sxs-lookup"><span data-stu-id="8d7ff-114">Data security</span></span>

<span data-ttu-id="8d7ff-p102">从您的租户传输数据存储在 Microsoft 租户位于美国的 Azure SQL 数据库中。您的数据存储，并且符合要求的 Azure 安全定位。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p102">Data transmitted from your tenant is stored in Azure SQL databases in the Microsoft tenant hosted in the USA. Your data is stored and meets requirements for Azure security positioning.</span></span> 

<span data-ttu-id="8d7ff-117">有关详细信息，请参阅[Microsoft Azure security](https://www.microsoft.com/TrustCenter/Security/azure-security)。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-117">For more information, see [Microsoft Azure security](https://www.microsoft.com/TrustCenter/Security/azure-security).</span></span>

<span data-ttu-id="8d7ff-118">此列表概括了 Microsoft 和您的租户之间传输数据的类型。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-118">This list summarizes the types of data transmitted between Microsoft and your tenant.</span></span> 

- <span data-ttu-id="8d7ff-119">从 Microsoft 向您的租户</span><span class="sxs-lookup"><span data-stu-id="8d7ff-119">From Microsoft to your tenant</span></span>
    - <span data-ttu-id="8d7ff-120">组名称</span><span class="sxs-lookup"><span data-stu-id="8d7ff-120">Group names</span></span>
    - <span data-ttu-id="8d7ff-121">配置安全策略</span><span class="sxs-lookup"><span data-stu-id="8d7ff-121">Security policy configuration</span></span>
    - <span data-ttu-id="8d7ff-122">设备订单</span><span class="sxs-lookup"><span data-stu-id="8d7ff-122">Device orders</span></span>
    - <span data-ttu-id="8d7ff-123">用户帐户 （msadmin、 mstest，Microsoft 托管 Desktop_soc_ro、 Microsoft 托管 Desktop_wdgsoc）</span><span class="sxs-lookup"><span data-stu-id="8d7ff-123">User accounts (msadmin, mstest, Microsoft Managed Desktop_soc_ro, Microsoft Managed Desktop_wdgsoc)</span></span>
    - <span data-ttu-id="8d7ff-124">E5 许可证分配给上面的 4 个用户</span><span class="sxs-lookup"><span data-stu-id="8d7ff-124">E5 License assignment to the above 4 users</span></span>
    - <span data-ttu-id="8d7ff-125">Windows 更新更新响铃的策略</span><span class="sxs-lookup"><span data-stu-id="8d7ff-125">Windows update policies for update rings</span></span>
    - <span data-ttu-id="8d7ff-126">将来，进一步功能将开发允许发布的其他类型的配置内容包括应用程序、 策略和设置。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-126">In the future, further capabilities will be developed to allow for posting of other types of configuration content including apps, policies, and settings.</span></span>
- <span data-ttu-id="8d7ff-127">从 Microsoft 到租户</span><span class="sxs-lookup"><span data-stu-id="8d7ff-127">From your tenant to Microsoft</span></span>
    - <span data-ttu-id="8d7ff-128">设备更新、 使用情况和可靠性数据</span><span class="sxs-lookup"><span data-stu-id="8d7ff-128">Device update, usage and reliability data</span></span>
    - <span data-ttu-id="8d7ff-129">应用程序部署和可靠性数据</span><span class="sxs-lookup"><span data-stu-id="8d7ff-129">App deployment and reliability data</span></span>
    - <span data-ttu-id="8d7ff-130">更新和安全策略部署数据</span><span class="sxs-lookup"><span data-stu-id="8d7ff-130">Update and security policy deployment data</span></span>
    - <span data-ttu-id="8d7ff-131">分配给设备的用户</span><span class="sxs-lookup"><span data-stu-id="8d7ff-131">Users assigned to devices</span></span>



## <a name="device-security"></a><span data-ttu-id="8d7ff-132">设备安全</span><span class="sxs-lookup"><span data-stu-id="8d7ff-132">Device security</span></span>

<span data-ttu-id="8d7ff-p103">若要防止安全违规，务必确保所有 Microsoft 托管桌面设备都都不健康和安全。同样，务必确保我们可以检测不正常的设备并尽可能早地减少风险。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p103">To prevent security breaches, it’s important to ensure all Microsoft Managed Desktop devices are healthy and secured. It’s equally important to ensure we can detect unhealthy devices and mitigate the risk as early as possible.</span></span>

<span data-ttu-id="8d7ff-135">下表列出了提供以确保 Microsoft 托管桌面设备受信任和受保护的正常运行的服务。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-135">The following table lists the services provided to ensure Microsoft Managed Desktop devices are trusted, healthy and secured.</span></span>

<span data-ttu-id="8d7ff-136">服务</span><span class="sxs-lookup"><span data-stu-id="8d7ff-136">Service</span></span> | <span data-ttu-id="8d7ff-137">说明</span><span class="sxs-lookup"><span data-stu-id="8d7ff-137">Description</span></span>
--- | ---
<span data-ttu-id="8d7ff-138">防病毒</span><span class="sxs-lookup"><span data-stu-id="8d7ff-138">Antivirus</span></span> | <span data-ttu-id="8d7ff-139">我们将确保：</span><span class="sxs-lookup"><span data-stu-id="8d7ff-139">We will ensure that:</span></span><br><span data-ttu-id="8d7ff-140">安装和配置 Windows Defender AV</span><span class="sxs-lookup"><span data-stu-id="8d7ff-140">- Windows Defender AV is installed and configured</span></span><br><span data-ttu-id="8d7ff-141">Windows Defender AV 定义是最新</span><span class="sxs-lookup"><span data-stu-id="8d7ff-141">- Windows Defender AV definitions are up to date</span></span>
<span data-ttu-id="8d7ff-142">完整批量加密</span><span class="sxs-lookup"><span data-stu-id="8d7ff-142">Full Volume Encryption</span></span> |    <span data-ttu-id="8d7ff-143">Windows BitLocker 是 Microsoft 托管桌面设备数据加密解决方案。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-143">Windows BitLocker is the data encryption solution for Microsoft Managed Desktop devices.</span></span><br><br><span data-ttu-id="8d7ff-144">到服务 onboarded 组织后，将使用 Windows BitLocker 与内置信任平台模块 (TPM) 设备休眠模式中或关闭时，防止未授权的访问本地数据加密设备。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-144">Once an organization is onboarded into the service, devices will be encrypted using Windows BitLocker with built-in Trust Platform Module (TPM) to prevent unauthorized access to local data when the device is in sleep mode, or off.</span></span> 
<span data-ttu-id="8d7ff-145">监视</span><span class="sxs-lookup"><span data-stu-id="8d7ff-145">Monitoring</span></span> |    <span data-ttu-id="8d7ff-p104">Windows Defender 高级威胁保护 (Windows Defender ATP) 是监控解决方案的所有 Microsoft 托管桌面设备安全威胁。Windows Defender ATP 允许企业客户检测、 调查和响应公司网络中的高级威胁。有关详细信息，请参阅[Windows Defender 高级威胁保护。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p104">Windows Defender Advanced Threat Protection (Windows Defender ATP) is the security threat monitoring solution for all Microsoft Managed Desktop devices. Windows Defender ATP allows enterprise customers to detect, investigate and respond to advanced threats in their corporate network. For more information, see [Windows Defender Advanced Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)</span></span> 
<span data-ttu-id="8d7ff-149">软件更新</span><span class="sxs-lookup"><span data-stu-id="8d7ff-149">Software updates</span></span> |  <span data-ttu-id="8d7ff-150">Microsoft 将确保 Microsoft 托管桌面设备始终安全与 Windows 和 Office，使用 Windows Update for Business 的最新的安全更新。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-150">Microsoft will ensure that Microsoft Managed Desktop devices are always secured with the latest security update, for Windows and Office, using Windows Update for Business.</span></span>
<span data-ttu-id="8d7ff-151">“恢复”</span><span class="sxs-lookup"><span data-stu-id="8d7ff-151">Recovery</span></span> |  <span data-ttu-id="8d7ff-p105">企业数据存储在 OneDrive for business，并可以轻松地还原为 Microsoft 托管桌面设备。有关详细信息，请参阅[OneDrive for Business。](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p105">Corporate data is stored on OneDrive for business and can be easily restored for Microsoft Managed Desktop devices. For more information, see [OneDrive for Business.](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US)</span></span> 



## <a name="identity-security"></a><span data-ttu-id="8d7ff-154">标识安全性</span><span class="sxs-lookup"><span data-stu-id="8d7ff-154">Identity security</span></span>

<span data-ttu-id="8d7ff-p106">标识和访问管理保护公司资产和关键业务数据。Azure Active Directory (Azure AD) 提供在云中的标识服务并启用基于云的身份验证，以确保只有受信任的个人可以从 Microsoft 托管桌面设备访问企业资源。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p106">Identity and access management protects corporate assets and business-critical data. Azure Active Directory (Azure AD) provides identity services in the cloud and enable cloud-based authentication that ensures only trusted individuals can access corporate resources from Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8d7ff-157">服务</span><span class="sxs-lookup"><span data-stu-id="8d7ff-157">Service</span></span> | <span data-ttu-id="8d7ff-158">说明</span><span class="sxs-lookup"><span data-stu-id="8d7ff-158">Description</span></span>
--- | ---
<span data-ttu-id="8d7ff-159">企业级身份验证提供程序</span><span class="sxs-lookup"><span data-stu-id="8d7ff-159">Enterprise grade authentication provider</span></span> |  <span data-ttu-id="8d7ff-p107">使用 Microsoft azure AD 高级版本为您提供了承载在全球分布数据中心中的高可用性服务。服务处理来自多个 200 万个活动用户每一天的十亿的身份验证，并为您提供了为 99.9 %sla。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p107">Azure AD Premium editions used by Microsoft give you a high-availability service hosted in globally-distributed datacenters. The service handles billions of authentications each day from more than 200 million active users and gives you a 99.9% SLA.</span></span>
<span data-ttu-id="8d7ff-162">生物身份验证</span><span class="sxs-lookup"><span data-stu-id="8d7ff-162">Biometric Authentication</span></span> |  <span data-ttu-id="8d7ff-p108">Windows Hello 允许用户使用其表面或 PIN，进行更加复杂忘记或窃取密码登录。这可能需要其他配置的工作。有关详细信息，请参阅[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p108">Windows Hello allows users to login using their face or a PIN, making passwords harder to forget or steal. This might require additional work to configure. For more information, see [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)</span></span>
<span data-ttu-id="8d7ff-166">多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="8d7ff-166">Multi factor authentication</span></span> | <span data-ttu-id="8d7ff-167">Azure 多因素身份验证防止未授权的访问内部部署和云应用程序提供了其他级别的身份验证使用移动电话，以及为自助服务密码重置。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-167">Azure multi-factor authentication prevents unauthorized access to on-premises and cloud applications by providing an additional level of authentication using a mobile phone, as well as self-service password reset.</span></span> 
<span data-ttu-id="8d7ff-168">标准用户权限</span><span class="sxs-lookup"><span data-stu-id="8d7ff-168">Standard user permission</span></span> |  <span data-ttu-id="8d7ff-p109">保护系统，并使其更安全，用户将分配标准用户权限。这被分配的 Windows 自动执行某些操作的全新体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p109">To protect the system and make it more secure, the user will be assigned Standard User Permissions. This is assigned as part of the Windows Autopilot out-of-box experience.</span></span>



## <a name="network-security"></a><span data-ttu-id="8d7ff-171">网络安全</span><span class="sxs-lookup"><span data-stu-id="8d7ff-171">Network security</span></span>

<span data-ttu-id="8d7ff-172">客户负责网络安全。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-172">Customers are responsible for network security.</span></span> 

<span data-ttu-id="8d7ff-173">服务</span><span class="sxs-lookup"><span data-stu-id="8d7ff-173">Service</span></span> | <span data-ttu-id="8d7ff-174">说明</span><span class="sxs-lookup"><span data-stu-id="8d7ff-174">Description</span></span>
--- | ---
<span data-ttu-id="8d7ff-175">VPN</span><span class="sxs-lookup"><span data-stu-id="8d7ff-175">VPN</span></span> | <span data-ttu-id="8d7ff-176">客户拥有其 VPN 基础结构，以确保可以 intranet 外部公开有限的企业资源。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-176">Customers own their VPN infrastructure, to ensure limited corporate resources can be exposed outside the intranet.</span></span><br><br><span data-ttu-id="8d7ff-p110">最低要求： Microsoft 托管桌面需要 Windows 10 兼容和支持 VPN 解决方案。如果您的组织需要 VPN 解决方案，它需要支持 Windows 10 并且已打包和可通过 Intune 部署。有关详细信息，请联系您软件发行者。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p110">Minimum requirement: Microsoft Managed Desktop requires a Windows 10 compatible and supported VPN solution. If your organization needs a VPN solution, it needs to support Windows 10 and be packaged and deployable through Intune. Contact your software publisher for more information.</span></span><br><br><span data-ttu-id="8d7ff-180">建议：</span><span class="sxs-lookup"><span data-stu-id="8d7ff-180">Recommendation:</span></span><br><span data-ttu-id="8d7ff-p111">-Microsoft 建议无法轻松地部署通过 Intune 到推送 VPN 配置文件的现代 VPN 解决方案。这样，始终可用的、 无缝、 可靠，安全地访问企业网络。有关详细信息，请参阅 VPN 中 Intune 的设置。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p111">- Microsoft recommends a Modern VPN solution that could be easily deployed through Intune to push VPN profiles. This provides an always-on, seamless, reliable, and secure way to access corporate network. For more information, see VPN settings in Intune.</span></span><br><span data-ttu-id="8d7ff-184">-粗 VPN 客户端或旧 VPN 客户端，不建议使用由 Microsoft 同时使用 Microsoft 托管桌面，因为它会影响最终用户环境。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-184">- Thick VPN clients, or legacy VPN clients, are not recommended by Microsoft while using Microsoft Managed Desktop as it can impact the end-user environment.</span></span><br><span data-ttu-id="8d7ff-185">-Microsoft 建议的传出的 web 流量转直接到 Internet，而不经由 VPN 以避免任何性能问题。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-185">- Microsoft recommends that the outgoing web traffic goes directly to Internet without going through the VPN to avoid any performance issues.</span></span><br><span data-ttu-id="8d7ff-186">-理想情况下，Microsoft 建议使用 Azure Active Directory 应用程序代理，而不是 VPN。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-186">- Ideally, Microsoft recommends the use of Azure Active Directory App Proxy instead of a VPN.</span></span>


## <a name="information-security"></a><span data-ttu-id="8d7ff-187">信息安全</span><span class="sxs-lookup"><span data-stu-id="8d7ff-187">Information security</span></span>

<span data-ttu-id="8d7ff-188">客户可以配置这些可选的服务，以帮助保护企业高价值资产。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-188">Customers may configure these optional services to help protect corporate high-value assets.</span></span> 

<span data-ttu-id="8d7ff-189">服务</span><span class="sxs-lookup"><span data-stu-id="8d7ff-189">Service</span></span> | <span data-ttu-id="8d7ff-190">说明</span><span class="sxs-lookup"><span data-stu-id="8d7ff-190">Description</span></span>
--- | ---
<span data-ttu-id="8d7ff-191">条件访问</span><span class="sxs-lookup"><span data-stu-id="8d7ff-191">Conditional access</span></span> |    <span data-ttu-id="8d7ff-192">仅在兼容设备时，允许访问企业资源和服务。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-192">Allow access to corporate resources and services only when the device is compliant.</span></span>
<span data-ttu-id="8d7ff-193">数据恢复</span><span class="sxs-lookup"><span data-stu-id="8d7ff-193">Data recovery</span></span>  | <span data-ttu-id="8d7ff-p112">信息存储在设备上的密钥文件夹中备份到 OneDrive for Bbusiness。Microsoft 托管桌面不负责使用 OneDrive for Business 同步的数据。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p112">Information stored in key folders on the device is backed up to OneDrive for Bbusiness. Microsoft Managed Desktop is not responsible for data that isn’t synchronized with OneDrive for Business.</span></span> 
<span data-ttu-id="8d7ff-196">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="8d7ff-196">Windows Information Protection</span></span> |    <span data-ttu-id="8d7ff-197">对于需要高级别的信息安全性的公司，我们建议[Windows 信息保护](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)和[Azure Information Protection。](https://www.microsoft.com/cloud-platform/azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-197">For companies that require high levels of information security, we recommend [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) and [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection).</span></span> 


## <a name="privileged-account-access"></a><span data-ttu-id="8d7ff-198">特权的帐户访问</span><span class="sxs-lookup"><span data-stu-id="8d7ff-198">Privileged account access</span></span>

<span data-ttu-id="8d7ff-199">现在，我们限制访问的客户 MSAdmin 凭据和应用程序通过这些机制：</span><span class="sxs-lookup"><span data-stu-id="8d7ff-199">Today, we restrict access to the customer MSAdmin credentials and the application through these mechanisms:</span></span>

- <span data-ttu-id="8d7ff-200">**运算符**– Microsoft 完整-时间-员工位于美国已成功完成定期背景和安全检查。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-200">**Operators** – Microsoft full-time-employees located in the US who have successfully completed a periodic background and security check.</span></span>
- <span data-ttu-id="8d7ff-p113">**运算符标识**– 受到保护根据 Microsoft 设置的标准。有关详细信息，请参阅[管理用户标识和 microsoft 的安全访问](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p113">**Operator identity** – Protected according to the standards set by Microsoft. For more information, see [Managing user identities and secure access at Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft).</span></span> 
- <span data-ttu-id="8d7ff-p114">在运算符环境和客户的租户内执行**日志记录**。日志数据和个人信息保留在各自的环境中不遍历环境。</span><span class="sxs-lookup"><span data-stu-id="8d7ff-p114">**Logging** is performed within the operator environment and within the customer’s tenant. Log data and personal information are retained within the respective environments and do not traverse environments.</span></span> 

