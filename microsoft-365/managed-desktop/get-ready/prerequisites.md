---
title: Microsoft 托管桌面的系统必备
description: 在 Microsoft 托管桌面中注册之前设置的许可证、Azure 帐户、身份验证设置和 Microsoft 365 设置
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5b5fb7185bb696bb6daae0a67a209cf3f7e77655
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924560"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的系统必备

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

本主题概述了为确保成功使用 Microsoft 托管桌面而必须满足的基础结构要求。 


区域 | 先决条件详细信息
--- | ---
授权 |Microsoft 托管桌面需要 Microsoft 365 E3 许可证以及 Microsoft Defender for Endpoint (或分配给) 等效项。 Azure Active Directory Premium 2 的两个许可证必须在租户中提供，但用户不需要此许可证。 <br>有关特定服务计划的详细信息，请参阅本主题 [中有关](#more-about-licenses) 许可证的详细信息。<br>有关可用许可证详细信息，请参阅 [Microsoft 365 许可](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
连接 |  所有 Microsoft 托管桌面设备都需要从企业网络连接到多个 Microsoft 服务终结点。<br><br>有关所需 IP 和 URL 的完整列表，请参阅网络 [配置](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必须是所有用户帐户的颁发机构，或者必须使用最新支持的 Azure AD Connect 版本从本地 Active Directory 同步用户帐户。<br><br>[必须为 Microsoft](/azure/active-directory/devices/enterprise-state-roaming-overview) 托管桌面用户启用企业状态漫游。<br><br>有关详细信息，请参阅[Azure AD Connect。](/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>有关受支持的 Azure AD Connect 版本详细信息，请参阅 [Azure AD Connect：版本发布历史记录](/azure/active-directory/hybrid/reference-connect-version-history)。
身份验证 |    如果 Azure AD 不是用户帐户的主要身份验证源，则必须在 Azure AD Connect 中配置以下项之一：<br>- 密码哈希同步<br>- 传递身份验证<br>- 外部标识提供程序 (包括 Windows Server ADFS 和非 Microsoft IDP) 配置为满足 Azure AD 集成要求。 有关详细信息 [，](https://www.microsoft.com/download/details.aspx?id=56843) 请参阅指南。 <br><br>使用 Azure AD Connect 设置身份验证选项时，还推荐密码写回。 有关详细信息，请参阅密码 [写回](/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>如果实施了外部标识提供程序，则必须验证解决方案：<br>- 满足 Azure AD 集成要求<br>- 支持 Azure AD 条件访问，允许配置 Microsoft 托管桌面设备合规性策略<br>- 启用设备注册和使用作为 Microsoft 托管桌面的一部分所需的 Microsoft 365 服务或功能 <br><br>有关使用 Azure AD 的身份验证选项的详细信息，请参阅 [Azure AD Connect 用户登录选项](/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | 必须为 Microsoft 托管桌面用户启用 OneDrive for Business。<br><br>尽管不需要注册 Microsoft 托管桌面，但我们强烈建议将以下服务迁移到云：<br>- 电子邮件：迁移到基于云的邮箱、Exchange Online，或在本地使用 Exchange 2013 或更高版本配置 Exchange Online 混合。<br>- 文件和文件夹：迁移到 OneDrive for Business 或 SharePoint Online。<br>- 联机协作工具：迁移到 Teams。
设备管理 | Microsoft 托管桌面设备需要使用 Microsoft Intune 进行管理。 Intune 必须设置为移动设备管理机构。<br><br>有关详细信息，请参阅[Microsoft Intune。](https://www.microsoft.com/cloud-platform/microsoft-intune) 
数据备份和恢复 |  Microsoft 托管桌面要求将文件同步到 OneDrive for Business 以提供保护。 Microsoft 托管桌面不保证任何未同步到 OneDrive for Business 的文件，在设备交换或支持需要设备重置的呼叫期间可能会丢失。<br><br>尽管不需要，但 Microsoft 托管桌面强烈建议从映射的网络驱动器迁移到相应的云解决方案。 有关详细信息，请参阅为 [Microsoft 托管桌面准备映射驱动器](mapped-drives.md)

准备好开始使用 Microsoft 托管桌面后，请联系你的 Microsoft 客户经理。 

## <a name="more-about-licenses"></a>有关许可证的更多信息

Microsoft 托管桌面需要某些许可证选项才能正常运行。 请参阅 [Microsoft 托管桌面](../intro/technologies.md) 技术，了解如何使用这些许可证。

> [!TIP]
> 若要向特定用户分配这些许可证选项，我们建议你利用 Azure Active [](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Directory 的基于组的许可功能。

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 企业版  
- Microsoft Defender for Endpoint
- 适用于企业的 Microsoft 365 应用
- Microsoft Teams
- [SharePoint Online 计划 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online 计划 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> 你的 Microsoft 帐户管理器将帮助你查看当前许可证和服务计划，并找到最有效的途径，帮助你获取所需的任何其他许可证或服务计划，同时避免重复。