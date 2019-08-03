---
title: Microsoft 托管桌面的先决条件
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6351dd4696ed21b177dc2789b18c380fba4ebe91
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171722"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的先决条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

本主题概述了为确保 Microsoft 托管桌面成功而必须满足的基础结构要求。 

Microsoft FastTrack 可帮助您满足这些要求, 并帮助您准备参与 Microsoft 托管桌面。 有关详细信息, 请参阅[Microsoft FastTrack](https://fasttrack.microsoft.com/about)。 

区域 | 先决条件详细信息
--- | ---
许可 |Microsoft 托管桌面要求以下任一 Microsoft 365 许可证 (或等效项):<br>-Microsoft 365 E5<br>-Microsoft 365 E5 安全附加版的 microsoft 365 E3<br><br>有关可用许可证的详细信息, 请参阅[Microsoft 365 许可](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
连接 |  所有 Microsoft 托管桌面设备都需要连接到公司网络中的多个 Microsoft 服务终结点。<br><br>有关所需 Ip 和 Url 的完整列表, 请参阅[网络配置](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必须是所有用户帐户的颁发机构的来源, 或者必须使用 Azure AD Connect 的最新受支持版本从本地 Active Directory 同步用户帐户。<br><br>必须为 Microsoft 托管桌面用户启用[企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview)。<br><br>有关 Azure AD Connect 的详细信息, 请参阅[AZURE Ad connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>有关受支持的 Azure AD Connect 版本的详细信息, 请参阅[AZURE Ad connect: Version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)。
身份验证 |    如果 Azure AD 不是用户帐户的颁发机构的来源, 则必须在 Azure AD Connect 中配置以下各项之一:<br>-密码哈希同步<br>传递身份验证<br>-使用 ADFS 的联合<br><br>使用 Azure AD Connect 设置身份验证选项时, 还建议使用密码写回。 有关详细信息, 请参阅[密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>有关 Azure AD 的身份验证选项的详细信息, 请参阅[AZURE Ad Connect user 登录选项](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Office 365 |    必须为 Microsoft 托管桌面用户启用 OneDrive for Business。<br><br>尽管不需要向 Microsoft 托管桌面注册, 但强烈建议将以下服务迁移到云:<br>-电子邮件: 迁移到基于云的邮箱、Exchange online 或使用 exchange Online 混合 (本地 Exchange 2013 或更高版本) 进行配置。<br>-文件和文件夹: 迁移到 OneDrive for business 或 SharePoint Online。<br>-在线协作工具: 迁移到团队。
设备管理 | Microsoft 托管桌面设备需要使用 Microsoft Intune 进行管理。 必须将 Intune 设置为移动设备管理机构。<br><br>有关详细信息, 请参阅[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
数据备份和恢复 | Microsoft 托管桌面需要将文件同步到 OneDrive for Business 以进行保护。 未同步到 OneDrive for business 的任何文件都不能由 Microsoft 托管桌面保证, 在设备交换过程中可能会丢失, 或者支持需要设备重置的呼叫。<br><br>尽管这不是必需的, 但 Microsoft 托管桌面强烈建议从映射的网络驱动器迁移到适当的云解决方案。 

当你准备好开始使用 Microsoft 托管桌面时, 请与你的 Microsoft 帐户管理员联系。 
