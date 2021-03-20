---
title: 为 Microsoft 托管桌面准备证书和网络配置文件
description: certs/wifi/lan
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9f4490711c1ea051afe9d8efb081a2f7a141f8ba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909114"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a><span data-ttu-id="479ee-104">为 Microsoft 托管桌面准备证书和网络配置文件</span><span class="sxs-lookup"><span data-stu-id="479ee-104">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>  
 
<span data-ttu-id="479ee-105">对于使用 Microsoft 托管桌面的客户来说，基于证书的身份验证是一项常见要求。</span><span class="sxs-lookup"><span data-stu-id="479ee-105">Certificate-based authentication is a common requirement for customers using Microsoft Managed Desktop.</span></span> <span data-ttu-id="479ee-106">您可能需要证书来访问 Wi-Fi LAN、连接到 VPN 解决方案或访问组织内部资源。</span><span class="sxs-lookup"><span data-stu-id="479ee-106">You might require certificates to access Wi-Fi or LAN, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>   
 
<span data-ttu-id="479ee-107">由于 Microsoft 托管桌面设备已加入 Azure Active Directory (Azure AD) 并且由 Microsoft Intune 管理，因此必须使用与 Intune 集成的简单证书注册协议 (SCEP) 或公钥加密标准 (PKCS) 证书基础结构来部署此类证书。</span><span class="sxs-lookup"><span data-stu-id="479ee-107">Because Microsoft Managed Desktop devices are joined to Azure Active Directory (Azure AD) and are managed by Microsoft Intune, you must deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with Intune.</span></span>    
 
## <a name="certificate-requirements"></a><span data-ttu-id="479ee-108">证书要求</span><span class="sxs-lookup"><span data-stu-id="479ee-108">Certificate requirements</span></span> 
 
<span data-ttu-id="479ee-109">通过 SCEP 或 PKCS 基础结构部署证书需要根证书。</span><span class="sxs-lookup"><span data-stu-id="479ee-109">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="479ee-110">您组织中其他应用程序和服务可能需要将根证书部署到 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="479ee-110">Other applications and services in your organization might require root certificates to be deployed to your Microsoft Managed Desktop devices.</span></span>    
 
<span data-ttu-id="479ee-111">在将 SCEP 或 PKCS 证书部署到 Microsoft 托管桌面之前，应收集组织中需要用户证书或设备证书的每个服务的要求。</span><span class="sxs-lookup"><span data-stu-id="479ee-111">Before you deploy SCEP or PKCS certificates to Microsoft Managed Desktop, you should gather requirements for each service that requires a user or device certificate in your organization.</span></span> <span data-ttu-id="479ee-112">若要简化此活动，可以使用以下规划模板之一：</span><span class="sxs-lookup"><span data-stu-id="479ee-112">To make this activity easier, you can use one of the following planning templates:</span></span>  
 
- [<span data-ttu-id="479ee-113">PKCS 证书模板</span><span class="sxs-lookup"><span data-stu-id="479ee-113">PKCS certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [<span data-ttu-id="479ee-114">SCEP 证书模板</span><span class="sxs-lookup"><span data-stu-id="479ee-114">SCEP certificate template</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a><span data-ttu-id="479ee-115">Wi-Fi连接要求</span><span class="sxs-lookup"><span data-stu-id="479ee-115">Wi-Fi connectivity requirements</span></span>

<span data-ttu-id="479ee-116">若要允许自动为设备提供企业网络Wi-Fi配置，你可能需要一个Wi-Fi配置文件。</span><span class="sxs-lookup"><span data-stu-id="479ee-116">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you might need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="479ee-117">你可以配置 Microsoft 托管桌面以将这些配置文件部署到你的设备。</span><span class="sxs-lookup"><span data-stu-id="479ee-117">You can configure Microsoft Managed Desktop to deploy these profiles to your devices.</span></span> <span data-ttu-id="479ee-118">如果网络安全要求设备成为本地域的一部分，可能还需要评估 Wi-Fi 网络基础结构，以确保其与 Microsoft 托管桌面设备兼容 (Microsoft 托管桌面设备仅加入 Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="479ee-118">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with Microsoft Managed Desktop devices (Microsoft Managed Desktop devices are Azure AD-joined only).</span></span> 
 
<span data-ttu-id="479ee-119">在将Wi-Fi部署到 Microsoft 托管桌面设备之前，需要收集组织针对每个桌面Wi-Fi的要求。</span><span class="sxs-lookup"><span data-stu-id="479ee-119">Before you deploy a Wi-Fi configuration to Microsoft Managed Desktop devices, you will be required to gather your organization’s requirements for each Wi-Fi network.</span></span> <span data-ttu-id="479ee-120">若要简化此活动，可以使用此 [WiFi 配置文件模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="479ee-120">To make this activity easier, you can use this [WiFi profile template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).</span></span>
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a><span data-ttu-id="479ee-121">有线连接要求和 802.1x 身份验证</span><span class="sxs-lookup"><span data-stu-id="479ee-121">Wired connectivity requirements and 802.1x authentication</span></span> 
 
<span data-ttu-id="479ee-122">如果使用 802.1x 身份验证保护从设备到局域网 (LAN) 的访问，则需要将所需的配置详细信息推送到 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="479ee-122">If you use 802.1x authentication to secure access from devices to your local area network (LAN), you will need to push the required configuration details to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="479ee-123">运行 Windows 10 版本 1809 或更高版本的 Microsoft 托管桌面设备支持通过 WiredNetwork 配置服务提供程序 (CSP) 部署 802.1x 配置。</span><span class="sxs-lookup"><span data-stu-id="479ee-123">Microsoft Managed Desktop devices running Windows 10, version 1809 or later support deploying an 802.1x configuration through the WiredNetwork configuration service provider (CSP).</span></span> <span data-ttu-id="479ee-124">有关详细信息，请参阅 [WiredNetwork 云解决方案提供商](/windows/client-management/mdm/wirednetwork-csp) 文档。</span><span class="sxs-lookup"><span data-stu-id="479ee-124">For more information, see [WiredNetwork CSP](/windows/client-management/mdm/wirednetwork-csp) documentation.</span></span> 
 
<span data-ttu-id="479ee-125">在将有线网络配置文件部署到 Microsoft 托管桌面设备之前，请收集组织对有线企业网络的要求。</span><span class="sxs-lookup"><span data-stu-id="479ee-125">Before you deploy a wired network configuration profile to Microsoft Managed Desktop devices, gather your organization’s requirements for your wired corporate network.</span></span> <span data-ttu-id="479ee-126">为此，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="479ee-126">To do so, follow these steps:</span></span> 
 
 
1. <span data-ttu-id="479ee-127">登录到配置了现有 802.1x 配置文件并连接到 LAN 网络的设备。</span><span class="sxs-lookup"><span data-stu-id="479ee-127">Sign on to a device that has your existing 802.1x profile configured and is connected to the LAN network.</span></span>  
2. <span data-ttu-id="479ee-128">使用管理凭据打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="479ee-128">Open a command prompt with administrative credentials.</span></span> 
3. <span data-ttu-id="479ee-129">通过运行 netsh 接口显示接口 查找 LAN **接口名称**。</span><span class="sxs-lookup"><span data-stu-id="479ee-129">Find the LAN interface name by running **netsh interface show interface**.</span></span> 
4. <span data-ttu-id="479ee-130">通过运行 netsh lan export profile folder=导出 LAN **配置文件 XML。 Interface="interface_name"**.</span><span class="sxs-lookup"><span data-stu-id="479ee-130">Export the LAN profile XML by running **netsh lan export profile folder=.  Interface=”interface_name”**.</span></span> 
5. <span data-ttu-id="479ee-131">如果需要在 Microsoft 托管桌面设备上测试导出的配置文件，请运行 **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**。</span><span class="sxs-lookup"><span data-stu-id="479ee-131">If you need to test your exported profile on Microsoft Managed Desktop device, run **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"**.</span></span> 
 
 
## <a name="deploy-certificate-infrastructure"></a><span data-ttu-id="479ee-132">部署证书基础结构</span><span class="sxs-lookup"><span data-stu-id="479ee-132">Deploy certificate infrastructure</span></span>  
 
<span data-ttu-id="479ee-133">如果你已经拥有 Intune 的现有 SCEP 或 PKCS 基础结构，并且此方法满足你的要求，则还可以将此方法用于 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="479ee-133">If you already have an existing SCEP or PKCS infrastructure with Intune and this approach meets your requirements, you can also use it for Microsoft Managed Desktop.</span></span> <span data-ttu-id="479ee-134">如果尚未存在 SCEP 或 PKCS 基础结构，您必须准备一个。</span><span class="sxs-lookup"><span data-stu-id="479ee-134">If no SCEP or PKCS infrastructure already exists, you'll have to prepare one.</span></span>  
 
<span data-ttu-id="479ee-135">有关详细信息，请参阅在 [Microsoft Intune](/intune/certificates-configure)中为设备配置证书配置文件。</span><span class="sxs-lookup"><span data-stu-id="479ee-135">For more information, see [Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure).</span></span> 
 
 
 
## <a name="deploy-a-lan-profile"></a><span data-ttu-id="479ee-136">部署 LAN 配置文件</span><span class="sxs-lookup"><span data-stu-id="479ee-136">Deploy a LAN profile</span></span> 
 
<span data-ttu-id="479ee-137">导出 LAN 配置文件后，可以按照以下步骤为 Microsoft 托管桌面准备策略：</span><span class="sxs-lookup"><span data-stu-id="479ee-137">Once your LAN profile has been exported, you can prepare the policy for Microsoft Managed Desktop by following these steps:</span></span>   
 
1. <span data-ttu-id="479ee-138">使用以下设置在 Microsoft Intune 中为 LAN 配置文件创建自定义配置文件 (请参阅在 Intune 中为 [Windows 10](/intune/custom-settings-windows-10) 设备) 。</span><span class="sxs-lookup"><span data-stu-id="479ee-138">Create a custom profile in Microsoft Intune for the LAN profile using the following settings (see [Use custom settings for Windows 10 devices in Intune](/intune/custom-settings-windows-10)).</span></span> <span data-ttu-id="479ee-139">在 **"自定义 OMA-URI 设置**"中，选择 **"添加**"，然后输入以下值：</span><span class="sxs-lookup"><span data-stu-id="479ee-139">In **Custom OMA-URI Settings**, select **Add**, and then enter the following values:</span></span> 
    - <span data-ttu-id="479ee-140">名称： *新式 Workplace-Windows 10 LAN 配置文件*</span><span class="sxs-lookup"><span data-stu-id="479ee-140">Name: *Modern Workplace-Windows 10 LAN Profile*</span></span> 
    - <span data-ttu-id="479ee-141">说明：输入概述设置以及任何其他重要详细信息的说明。</span><span class="sxs-lookup"><span data-stu-id="479ee-141">Description: Enter a description that gives an overview of the setting, and any other important details.</span></span> 
    - <span data-ttu-id="479ee-142">OMA-URI (区分大小写) ：输入 *./Device/Vendor/MSFT/WiredNetwork/LanXML*</span><span class="sxs-lookup"><span data-stu-id="479ee-142">OMA-URI (case sensitive): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*</span></span>
    - <span data-ttu-id="479ee-143">数据类型：选择 **"字符串 (XML 文件) "。**</span><span class="sxs-lookup"><span data-stu-id="479ee-143">Data type: select **String (XML file)**.</span></span> 
    - <span data-ttu-id="479ee-144">自定义 XML：上载导出的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="479ee-144">Custom XML: Upload the exported XML file.</span></span>
2. <span data-ttu-id="479ee-145">使用 Microsoft 托管桌面管理门户向 Microsoft 托管桌面 IT 运营提交支持请求，查看配置文件，并部署到"现代工作区设备 – 测试"。</span><span class="sxs-lookup"><span data-stu-id="479ee-145">Submit a Support request to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="479ee-146">Microsoft 托管桌面 IT 操作将告知你何时通过管理门户中的支持请求完成请求。</span><span class="sxs-lookup"><span data-stu-id="479ee-146">Microsoft Managed Desktop IT Operations will let you know when the request is completed via the Support request in the Admin portal.</span></span>
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a><span data-ttu-id="479ee-147">部署证书和 WLAN/VPN 配置文件</span><span class="sxs-lookup"><span data-stu-id="479ee-147">Deploy certificates and Wi-Fi/VPN profile</span></span> 
 
 
<span data-ttu-id="479ee-148">若要部署证书和配置文件，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="479ee-148">To deploy certificates and profiles, follow these steps:</span></span>

1. <span data-ttu-id="479ee-149">为每个根证书和中间证书创建 (请参阅 [创建受信任的证书配置文件](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。</span><span class="sxs-lookup"><span data-stu-id="479ee-149">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles).</span></span> <span data-ttu-id="479ee-150">其中每个配置文件必须具有包含 DD/MM/YYYYY 格式到期日期的说明。</span><span class="sxs-lookup"><span data-stu-id="479ee-150">Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="479ee-151">**不会部署没有过期日期的证书配置文件。**</span><span class="sxs-lookup"><span data-stu-id="479ee-151">**Certificate profiles without an expiration date will not be deployed.**</span></span>
2. <span data-ttu-id="479ee-152">为每个 SCEP 或 PKCS 证书创建配置文件 (请参阅创建 [SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 证书配置文件或创建 [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) 证书配置文件) 其中每个配置文件必须具有包含 DD/MM/YYYYY 格式的到期日期的说明。</span><span class="sxs-lookup"><span data-stu-id="479ee-152">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) or [Create a PKCS certificate profile](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="479ee-153">**不会部署没有过期日期的证书配置文件。**</span><span class="sxs-lookup"><span data-stu-id="479ee-153">**Certificate profiles without an expiration date will not be deployed.**</span></span>
3. <span data-ttu-id="479ee-154">为每个企业 WiFi 网络创建 (请参阅 [Windows 10](/intune/wi-fi-settings-windows) 及更高版本设备的 WLAN) 。</span><span class="sxs-lookup"><span data-stu-id="479ee-154">Create a profile for each corporate WiFi network (see [Wi-Fi settings for Windows 10 and later devices](/intune/wi-fi-settings-windows)).</span></span>
4. <span data-ttu-id="479ee-155">为每个企业 VPN 帐户创建配置文件 (Windows [10](/intune/vpn-settings-windows-10) 和 Windows 全息设备设置，以使用 Intune) 。</span><span class="sxs-lookup"><span data-stu-id="479ee-155">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/intune/vpn-settings-windows-10)).</span></span>
5. <span data-ttu-id="479ee-156">使用 Microsoft 托管桌面管理门户将标题为"证书部署"或"WI-Fi 配置文件部署"的支持请求提交到 Microsoft 托管桌面 IT 操作，以查看配置文件并部署到"新式工作区设备 – 测试"。</span><span class="sxs-lookup"><span data-stu-id="479ee-156">Submit a Support request titled “Certificate Deployment” or “Wi-Fi Profile Deployment” to Microsoft Managed Desktop IT Operations using the Microsoft Managed Desktop Admin portal to review and deploy the configuration profile to “Modern Workplace Devices – Test”.</span></span> <span data-ttu-id="479ee-157">Microsoft 托管桌面 IT 操作会通过管理门户中的支持请求告知你请求完成时间。</span><span class="sxs-lookup"><span data-stu-id="479ee-157">Microsoft Managed Desktop IT Operations will let you know when the request has been completed via the Support request in the Admin portal.</span></span> 
 
