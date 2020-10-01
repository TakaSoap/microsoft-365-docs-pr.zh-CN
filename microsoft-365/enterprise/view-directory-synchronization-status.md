---
title: 在 Microsoft 365 中查看目录同步状态
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: 在本文中，您将了解如何在 Office 365 中检查目录同步的状态。
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326945"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>在 Microsoft 365 中查看目录同步状态

如果已将本地 Active Directory 域服务集成 (AD DS) Azure Active Directory (Azure AD) 通过将本地环境与 Microsoft 365 同步，您还可以检查同步的状态。
  
## <a name="view-directory-synchronization-status"></a>查看目录同步状态

- 登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) ，并在主页上选择 " **DirSync Status** "。
- 或者，您可以转到 **用户** \> **活动用户**，并在 " **活动用户** " 页上选择 " **更多** \> **目录同步**"。 在 " **目录同步** " 窗格中，选择 " **转到 DirSync management**"。

## <a name="information-on-the-manage-directory-synchronization-page"></a>"管理目录同步" 页上的信息

下表列出了可以在页面上获取相关信息的功能。
  
如果目录同步存在问题，则还会在此页面上列出这些错误。 有关可能遇到的不同错误的详细信息，请参阅 [确定 Microsoft 365 中的目录同步错误](identify-directory-synchronization-errors.md)。
  
|Item|它有何用途？|
|:-----|:-----|
|**已验证域** | 你已验证的 Microsoft 365 租户中的域的数量。 |
|**未验证域** | 已添加但未验证的域。 |
|**目录同步已启用** |True 或 False。 指定是否已启用目录同步。 |
|**最新目录同步** | 上次运行目录同步的时间。 如果上一次同步的时间已超过三天，将显示一条警告和指向故障排除工具的链接。 |
|**启用密码同步** | True 或 False。 指定在内部部署和 Microsoft 365 租户之间是否有密码哈希同步。 |
|**上次密码同步** | 上次运行密码哈希同步的时间。 如果上一次同步的时间已超过三天，将显示一条警告和指向故障排除工具的链接。 |
|**目录同步客户端版本** | 如果已发布新版本的 Azure AD Connect，则包含下载链接。 |
|**目录同步服务帐户** | 显示 Microsoft 365 目录同步服务帐户的名称。 |
|||

## <a name="monitor-synchronization-health"></a>监控同步运行状况

在此部分中，将在每个本地 AD DS 域控制器上安装 Azure AD Connect Health 代理，以监控由 Azure AD Connect 提供的标识基础架构和同步服务。 Azure AD Connect Health 门户提供了监控信息，可以从中查看警报、性能监控、使用情况分析和其他信息。

如何使用 Azure AD Connect Health 的关键设计决策是基于使用 Azure AD Connect 的方式：

- 如果你使用的是****“托管身份验证”选项，请从[使用用于同步的 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) 开始，以理解并配置 Azure AD Connect Health。
- 如果仅使用****“联合身份验证”将帐户和组的名称与 Active Directory 联合身份验证服务 (AD FS) 同步，请从[在 AD FS 中使用 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 开始，以理解并配置 Azure AD Connect Health。

完成后，你将拥有：

- 在本地标识提供者服务器上安装的 Azure AD Connect Health 代理。
- 显示本地基础结构的当前状态，以及与 Microsoft 365 订阅的 Azure AD 租户同步活动的 Azure AD Connect Health 门户。

