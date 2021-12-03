---
title: Microsoft 托管桌面的系统必备
description: 许可证、Azure 帐户、身份验证设置Microsoft 365注册之前要设置的身份验证Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: b8bba3832572b6834c46806eca048b568cc3d761
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284393"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的系统必备

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure). DO NOT DELETE.-->
<!--from Prerequisites -->

本主题概述了为确保成功处理项目而必须满足的基础结构Microsoft 托管桌面。


领域 | 先决条件详细信息
--- | ---
授权 |Microsoft 托管桌面需要Microsoft 365 E3 Microsoft Defender for Endpoint (或分配给) 等效的许可证。<br>有关特定服务计划的详细信息，请参阅本主题 [中有关](#more-about-licenses) 许可证的详细信息。<br>有关可用许可证详细信息，请参阅Microsoft 365[许可](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)。
连接性 | 所有Microsoft 托管桌面设备都需要从企业网络连接到多个 Microsoft 服务终结点。<br><br>有关所需 IP 和 URL 的完整列表，请参阅网络 [配置](../get-ready/network.md)。 
Azure Active Directory | Azure Active Directory (Azure AD) 必须是所有用户帐户的颁发机构，或者用户帐户必须使用最新支持的 Azure AD 连接 版本从本地 Active Directory 进行Azure AD 连接。<br><br>有关详细信息，[请参阅Azure AD 连接。](/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>有关受支持的版本Azure AD 连接，请参阅[Azure AD 连接：版本发布历史记录](/azure/active-directory/hybrid/reference-connect-version-history)。
身份验证 | 如果Azure AD不是用户帐户的主身份验证源，则必须在"管理"中配置以下Azure AD 连接：<br>- 密码哈希同步<br>- 传递身份验证<br>- 外部标识提供程序 (包括 Windows Server ADFS 和非 Microsoft IDP) 配置为满足Azure AD要求。 有关详细信息 [，](https://www.microsoft.com/download/details.aspx?id=56843) 请参阅指南。 <br><br>在使用密码设置身份验证Azure AD 连接，还推荐密码写回。 有关详细信息，请参阅密码 [写回](/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>如果实施了外部标识提供程序，则必须验证解决方案：<br>- 满足Azure AD集成要求<br>- Azure AD条件访问，从而Microsoft 托管桌面配置设备合规性策略<br>- 启用设备注册和使用Microsoft 365服务或功能所需的服务或功能的一Microsoft 托管桌面 <br><br>有关使用身份验证选项Azure AD，请参阅Azure AD 连接[用户登录选项](/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | OneDrive for Business用户必须Microsoft 托管桌面用户。<br><br>尽管无需注册Microsoft 托管桌面，但我们强烈建议将以下服务迁移到云：<br>- 电子邮件：迁移到基于云的邮箱、Exchange联机，或在本地使用 Exchange Online Hybrid Exchange 2013 或更高版本进行配置。<br>- 文件和文件夹：迁移到 OneDrive for Business 或 SharePoint Online。<br>- 联机协作工具：迁移到Teams。
设备管理 | Microsoft 托管桌面设备需要使用 Microsoft Intune。 Intune 必须设置为移动设备管理机构。<br><br>有关详细信息，[请参阅Microsoft Intune。](https://www.microsoft.com/cloud-platform/microsoft-intune)
数据备份和恢复 | Microsoft 托管桌面需要将文件同步到OneDrive for Business进行保护。 任何未同步到OneDrive for Business文件都不能保证Microsoft 托管桌面在设备交换或支持需要设备重置的呼叫期间可能丢失。<br><br>尽管不需要，Microsoft 托管桌面强烈建议从映射的网络驱动器迁移到相应的云解决方案。 有关详细信息，请参阅为用户准备[映射Microsoft 托管桌面](mapped-drives.md)

当你准备好开始使用 Microsoft 托管桌面，请联系你的 Microsoft 客户经理。 

## <a name="more-about-licenses"></a>有关许可证的更多信息

Microsoft 托管桌面需要某些许可证选项才能运行。 请参阅[Microsoft 托管桌面](../intro/technologies.md)技术，了解如何使用这些许可证。

> [!TIP]
> 若要向特定用户分配这些许可证选项，我们建议您利用基于组的许可功能Azure Active Directory。 [](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

- Azure Active Directory Premium P1
- Microsoft Intune
- Windows 10 企业版  
- Microsoft Defender for Endpoint
- Microsoft 365 企业应用版
- Microsoft Teams
- [SharePoint Online 计划 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online 计划 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans)

> [!TIP]
> 你的 Microsoft 帐户管理器将帮助你查看当前许可证和服务计划，并找到最有效的途径，帮助你获取所需的任何其他许可证或服务计划，同时避免重复。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 请查看本文 (的先决条件) 。
2. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。