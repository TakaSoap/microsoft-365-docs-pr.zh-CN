---
title: 为 Microsoft 托管桌面准备证书和网络配置文件
description: 证书/wifi/局域网
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
ms.openlocfilehash: c7c57861986d275165484ae726140720a75da88e
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530027"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备证书和网络配置文件  
 
基于证书的身份验证是使用 Microsoft 托管桌面的客户的常见要求。 您可能需要证书访问 Wlan 或 LAN、连接到 VPN 解决方案或访问组织中的内部资源。   
 
由于 Microsoft 托管桌面设备已加入 Azure Active Directory （Azure AD）并由 Microsoft Intune 进行管理，因此您必须使用与 Intune 集成的简单证书注册协议（SCEP）或公钥加密标准（PKCS）证书基础结构部署此类证书。    
 
## <a name="certificate-requirements"></a>证书要求 
 
通过 SCEP 或 PKCS 基础结构部署证书需要根证书。 组织中的其他应用程序和服务可能要求将根证书部署到 Microsoft 托管桌面设备。    
 
在将 SCEP 或 PKCS 证书部署到 Microsoft 托管桌面之前，应收集组织中需要用户或设备证书的每个服务的要求。 若要简化此过程，可以使用以下规划模板之一：  
 
- [PKCS 证书模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 证书模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>目前，使用 EAP 类型时，仅支持将 SCEP 证书配置文件部署到 Microsoft 托管桌面的 Wi-fi 配置文件部署中。 不支持 PKCS 证书配置文件。 请参阅[在 Intune 中添加适用于 Windows 10 设备的 wlan 设置](https://docs.microsoft.com/intune/wi-fi-settings-windows)以供参考。

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-fi 连接要求

若要允许自动为企业网络所需的 Wi-fi 配置提供设备，您可能需要 Wlan 配置配置文件。 你可以将 Microsoft 托管桌面配置为将这些配置文件部署到你的设备。 如果你的网络安全要求设备是本地域的一部分，你可能还需要评估 Wlan 网络基础结构，以确保它与 Microsoft 托管桌面设备兼容（Microsoft 托管桌面设备仅在 Azure AD 中加入）。 
 
在将 Wlan 配置部署到 Microsoft 托管桌面设备之前，你需要为每个 Wlan 网络收集组织的要求。 为了简化此过程，可以使用此[WiFi 配置文件模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>有线连接要求和 802.1 x 身份验证 
 
如果使用 802.1 x 身份验证来保护从设备到局域网（LAN）的访问，则需要将所需的配置详细信息推送到 Microsoft 托管桌面设备。 Microsoft 托管桌面设备运行 Windows 10 版本1809或更高版本支持通过 WiredNetwork 配置服务提供程序（CSP）部署 802.1 x 配置。 有关详细信息，请参阅[WIREDNETWORK CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp)文档。 
 
在将有线网络配置文件部署到 Microsoft 托管桌面设备之前，请收集您的有线公司网络的要求。 为此，请执行以下步骤： 
 
 
1. 登录到已配置现有 802.1 x 配置文件且已连接到 LAN 网络的设备。  
2. 使用管理凭据打开命令提示符。 
3. 通过运行**netsh interface show interface**查找 LAN 接口名称。 
4. 通过运行**netsh LAN 导出配置文件文件夹来导出 LAN 配置文件 XML。 Interface = "interface_name"**。 
5. 如果需要在 Microsoft 托管桌面设备上测试导出的配置文件，请运行**netsh lan add profile filename = "PATH_AND_FILENAME.xml" interface = "INTERFACE_NAME"**。 
 
 
## <a name="deploy-certificate-infrastructure"></a>部署证书基础结构  
 
如果已有使用 Intune 的 SCEP 或 PKCS 基础结构，并且这符合你的要求，则也可以将其用于 Microsoft 托管桌面。 如果尚未存在 SCEP 或 PKCS 基础结构，则必须准备一个。  
 
有关详细信息，请参阅[在 Microsoft Intune 中为你的设备配置证书配置文件](https://docs.microsoft.com/intune/certificates-configure)。 
 
 
 
## <a name="deploy-a-lan-profile"></a>部署 LAN 配置文件 
 
在导出 LAN 配置文件后，可以按照以下步骤为 Microsoft 托管桌面准备策略：   
 
1. 使用以下设置在 Microsoft Intune 中为 LAN 配置文件创建自定义配置文件（请参阅[在 Intune 中使用适用于 Windows 10 设备的自定义设置](https://docs.microsoft.com/intune/custom-settings-windows-10)）。 在 "**自定义 OMA URI 设置**" 中，选择 "**添加**"，然后输入以下值： 
    - 名称：*新式工作区-Windows 10 LAN 配置文件* 
    - 说明：输入提供有关设置概述的说明以及任何其他重要详细信息。 
    - OMA URI （区分大小写）： Enter *。/Device/Vendor/MSFT/WiredNetwork/LanXML*
    - 数据类型： select **String （XML 文件）**。 
    - 自定义 XML：上传导出的 XML 文件。
2. 使用 Microsoft 托管桌面管理门户向 Microsoft 托管桌面 IT 操作提交支持请求，以查看配置配置文件并将其部署到 "新式 Workplace 设备–测试"。 Microsoft 托管桌面 IT 操作让你知道通过管理门户中的支持请求完成请求的时间。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>部署证书和 Wi-fi/VPN 配置文件 
 
 
若要部署证书和配置文件，请按照以下步骤操作：

1. 为每个根证书和中间证书创建配置文件（请参阅[创建受信任的证书配置文件](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。 这些配置文件中的每一个都必须具有包含 DD/MM/YYYY 格式的到期日期的说明。 **不会部署不具有过期日期的证书配置文件。**
2. 为每个 SCEP 或 PKCS 证书创建一个配置文件（请参阅[create a SCEP certificate profile](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile)或[create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)）每个配置文件都必须有一个说明，其中包含一个以 DD/MM/YYYY 格式显示的到期日期。 **不会部署不具有过期日期的证书配置文件。**
3. 为每个企业 WiFi 网络创建配置文件（请参阅[适用于 Windows 10 及更高版本设备的 wi-fi 设置](https://docs.microsoft.com/intune/wi-fi-settings-windows)）。
4. 为每个公司 VPN 创建配置文件（请参阅[使用 Intune 添加 VPN 连接的 windows 10 和 Windows 全息设备设置](https://docs.microsoft.com/intune/vpn-settings-windows-10)）。
5. 使用 Microsoft 托管桌面管理门户将名为 "证书部署" 或 "Wi-fi 配置文件部署" 的支持请求提交到 Microsoft 托管桌面管理门户，以查看配置配置文件并将其部署到 "新式 Workplace 设备–测试"。 Microsoft 托管桌面 IT 操作可让你知道在通过管理门户中的支持请求完成请求时。 
 
 
