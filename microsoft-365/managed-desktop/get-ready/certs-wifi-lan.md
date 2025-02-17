---
title: 为 Microsoft 托管桌面准备证书和网络配置文件
description: 证书要求和 WLAN 连接
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: ccdd9f390c794590eed6cbe11d169430f92bdf55
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520531"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备证书和网络配置文件  

对于使用证书的用户来说，基于证书的身份验证是Microsoft 托管桌面。 您可能需要证书以：

- 访问 Wi-Fi 或 LAN
- 连接 VPN 解决方案
- 访问组织内部资源

由于Microsoft 托管桌面设备已加入Azure Active Directory (Azure AD) 由 Microsoft Intune 管理，因此你必须使用：

- 简单证书注册协议 (SCEP) ，或
- 公钥加密标准 (PKCS) 与 Intune 集成的证书基础结构。

## <a name="certificate-requirements"></a>证书要求

通过 SCEP 或 PKCS 基础结构部署证书需要根证书。 您组织中其他应用程序和服务可能需要将根证书部署到Microsoft 托管桌面设备。

在将 SCEP 或 PKCS 证书部署到 Microsoft 托管桌面，您应收集组织中需要用户或设备证书的每个服务的要求。 若要简化此活动，可以使用以下规划模板之一：  

- [PKCS 证书模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx)
- [SCEP 证书模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi连接要求

若要允许自动为设备提供企业网络Wi-Fi配置，您可能需要一个Wi-Fi配置文件。

你可以配置Microsoft 托管桌面以将这些配置文件部署到设备。 如果网络安全要求设备成为本地域的一部分，你可能需要评估 Wi-Fi 网络基础结构以确保其与 Microsoft 托管桌面 设备兼容。 Microsoft 托管桌面设备Azure AD加入。

在将Wi-Fi配置部署到 Microsoft 托管桌面 设备之前，需要收集组织针对每个 Wi-Fi 网络的要求。 若要简化此活动，可以使用此 [WiFi 配置文件模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。

## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>有线连接要求和 802.1x 身份验证

如果使用 802.1x 身份验证保护从设备到局域网 (LAN) 的访问，则需要将所需的配置详细信息推送到 Microsoft 托管桌面 设备。

Microsoft 托管桌面运行 Windows 10 版本 1809 或更高版本的设备支持通过 WiredNetwork 配置服务提供商和 CSP) 部署 802.1x (配置。 有关详细信息，请参阅 [WiredNetwork 云解决方案提供商](/windows/client-management/mdm/wirednetwork-csp) 文档。

在将有线网络配置文件部署到Microsoft 托管桌面之前，请收集组织对有线企业网络的要求。

**要收集有线企业网络要求，请运行：**

1. 登录到配置了现有 802.1x 配置文件并连接到 LAN 网络的设备。  
2. 使用管理凭据打开命令提示符。
3. 通过运行 查找 LAN 接口名称 `netsh interface show interface`。
4. 通过运行 导出 LAN 配置文件 `netsh lan export profile folder=.  Interface=”interface_name”`XML。
5. 如果需要在设备上测试导出的配置文件Microsoft 托管桌面，请运行 `netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"`。

## <a name="deploy-certificate-infrastructure"></a>部署证书基础结构  

如果你已经拥有 Intune 的现有 SCEP 或 PKCS 基础结构，并且此方法满足你的要求，则还可以使用它Microsoft 托管桌面。

如果尚未存在 SCEP 或 PKCS 基础结构，您必须准备一个。 有关详细信息，请参阅[在 Microsoft Intune 中为设备配置证书配置文件](/intune/certificates-configure)。

## <a name="deploy-a-lan-profile"></a>部署 LAN 配置文件

导出 LAN 配置文件后，可以准备策略以用于Microsoft 托管桌面。

**若要为策略准备Microsoft 托管桌面：**

1. 使用以下设置在 MICROSOFT INTUNE 中为 LAN 配置文件创建自定义配置文件 (请参阅在 [Intune](/intune/custom-settings-windows-10) Windows 10 设备使用自定义) 。 在 **"自定义 OMA-URI 设置**，选择 **"添加**"，然后输入以下值：
    - 名称：新式 Workplace-Windows 10 LAN 配置文件
    - 说明：输入设置的简要说明以及其他重要详细信息。
    - OMA-URI (区分大小写) ：Enter `./Device/Vendor/MSFT/WiredNetwork/LanXML`
    - 数据类型：选择 **"字符串 (XML 文件) "**。
    - 自定义 XML：Upload导出的 XML 文件。
2. 将自定义配置文件分配给 **"现代工作区设备 - 测试"** 组。
3. 使用"测试"部署组的设备执行你认为必要的任何测试。 如果成功，然后将自定义配置文件分配给以下组：
    - 现代工作区设备 - 第一
    - 现代工作区设备 - 快速
    - 现代工作区设备 - 广泛

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>部署证书和 WLAN/VPN 配置文件

**部署证书和配置文件：**

1. 为每个根证书和中间证书创建配置文件 (请参阅 [创建受信任的证书配置文件](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。 其中每个配置文件必须具有包含 DD/MM/YYYYY 格式的到期日期的说明。 **证书配置文件必须具有到期日期。**
2. 为每个 SCEP 或 PKCS 证书创建 ([请参阅创建 SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 证书配置文件或创建 [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) 证书配置文件) 。 其中每个配置文件必须具有包含 DD/MM/YYYYY 格式的到期日期的说明。 **证书配置文件必须具有到期日期。**
3. 为每个企业 WiFi 网络管理员创建[ (请参阅适用于](/intune/wi-fi-settings-windows) Windows 10 及更高版本的 WLAN) 。
4. 为每个企业 VPN 服务器创建配置文件 (请参阅Windows 10和Windows全息设备设置，以使用 [Intune](/intune/vpn-settings-windows-10)) 添加 VPN 连接。
5. 将配置文件分配给 **现代工作区设备 - 测试** 组。
6. 使用"测试"部署组的设备执行你认为必要的任何测试。 如果成功，然后将自定义配置文件分配给以下组：
    - 现代工作区设备 - 第一
    - 现代工作区设备 - 快速
    - 现代工作区设备 - 广泛

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
1. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. 准备证书和网络配置文件 (本文) 。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。
