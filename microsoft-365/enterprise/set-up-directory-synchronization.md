---
title: 为 Microsoft 365 设置目录同步
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: 了解如何在 Microsoft 365 和本地 Active Directory 之间设置目录同步。
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924900"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>为 Microsoft 365 设置目录同步

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Microsoft 365 使用 Azure (Azure AD) 租户存储和管理身份验证标识以及访问基于云的资源的权限。 

如果你有本地 Active Directory 域服务 (AD DS) 域或林，可以将 AD DS 用户帐户、组和联系人与 Microsoft 365 订阅的 Azure AD 租户同步。 这是 Microsoft 365 的混合标识。 下面是其组件。

![Microsoft 365 的目录同步组件](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect 在本地服务器上运行，将 AD DS 与 Azure AD 租户同步。 除了目录同步，还可以指定以下身份验证选项：

- PHS (密码哈希) 

  Azure AD 执行身份验证本身。

- 直通身份验证 (PTA)

  Azure AD 具有 AD DS 来执行身份验证。

- 联合身份验证

  Azure AD 指向另一个标识提供程序请求身份验证的客户端计算机。

有关详细信息 [，请参阅](plan-for-directory-synchronization.md) 混合标识。
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. 查看 Azure AD Connect 的先决条件

通过 Microsoft 365 订阅，可获取免费的 Azure AD 订阅。 设置目录同步时，将在其中一台本地服务器上安装 Azure AD Connect。
  
对于 Microsoft 365，你需要：
  
- 验证本地域。 Azure AD Connect 向导将指导你完成此操作。
- 获取 Microsoft 365 租户和 AD DS 管理员帐户的用户名和密码。

对于安装 Azure AD Connect 本地服务器，需要：
  
|**服务器操作系统**|**其他软件**|
|:-----|:-----|
|Windows Server 2012 R2 及更高版本 | - 默认情况下安装 PowerShell，无需任何操作。  <br> - 通过 Windows 更新提供 Net 4.5.1 及更高版本。 确保在控制面板中安装了 Windows Server 的最新更新。 |
|Windows Server 2008 R2 Service Pack 1 (SP1) ** 或 Windows Server 2012 | - 最新版本的 PowerShell 在 Windows 管理框架 4.0 中可用。 在 Microsoft 下载中心 [中搜索它](https://go.microsoft.com/fwlink/p/?LinkId=717996)。  <br> - .Net 4.5.1 及更高版本在 [Microsoft 下载中心提供](https://go.microsoft.com/fwlink/p/?LinkId=717996)。 |
|Windows Server 2008 | - 最新支持的 PowerShell 版本在 Windows 管理框架 3.0 中提供，可在 [Microsoft 下载中心获取](https://go.microsoft.com/fwlink/p/?LinkId=717996)。  <br> - .Net 4.5.1 及更高版本在 [Microsoft 下载中心提供](https://go.microsoft.com/fwlink/p/?LinkId=717996)。 |

有关 Azure AD Connect 的硬件、软件、帐户和权限要求、SSL 证书要求和对象限制的详细信息，请参阅 Prerequisites for Azure [Active Directory](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) Connect。
  
还可以查看 Azure AD [Connect](/azure/active-directory/hybrid/reference-connect-version-history) 版本版本历史记录，以查看每个版本中包含和修复了哪些内容。

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. 安装 Azure AD Connect 并配置目录同步

在开始之前，请确保你已：

- Microsoft 365 全局管理员的用户名和密码
- AD DS 域管理员的用户名和密码
- 哪一种身份验证 (PHS、PTA、联合身份验证) 
- 是否要将 Azure [AD 无缝单一登录 (SSO) ](/azure/active-directory/hybrid/how-to-connect-sso)

请按以下步骤操作：

1. 登录到 Microsoft [365](https://admin.microsoft.com)管理中心 (左侧导航栏中选择"用户 https://admin.microsoft.com)  \> **""** 活动用户"。
2. 在"**活动用户**"页面上， (三个点) \> **目录同步"。**
  
3. 在 **Azure Active Directory** 准备页面上，选择转到下载中心，获取 **Azure AD Connect** 工具链接以开始使用。 
4. 按照 Azure [AD Connect 和 Azure AD Connect Health 安装路线图 中的步骤操作](/azure/active-directory/hybrid/how-to-connect-install-roadmap)。

## <a name="3-finish-setting-up-domains"></a>3. 完成域设置

按照管理 DNS 记录时为 [Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 创建 DNS 记录中的步骤完成域设置。

## <a name="next-step"></a>后续步骤

[向用户帐户分配许可证](assign-licenses-to-user-accounts.md)