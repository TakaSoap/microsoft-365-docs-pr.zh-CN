---
title: Microsoft 托管桌面的先决条件
description: ''
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8d9c008af9531bc5b829d248665dc5b58ac6034b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277383"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的先决条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Microsoft 托管桌面的成功在客户的基础结构中以已知、记录和商定的要求开始。 本节概述了这些 infastructure 要求。 

Microsoft FastTrack 可帮助客户满足这些要求, 并帮助你准备参与 Microsoft 托管桌面。 有关详细信息, 请参阅[Microsoft FastTrack](https://fasttrack.microsoft.com/about)。 

区域 | 先决条件详细信息
--- | ---
许可 | 必须为每个 MMD 用户分配以下许可证选项之一:<br>-Microsoft 365 E5<br>-Microsoft 365 E3、企业移动性 + 安全 E5 和 Windows 10 企业版 e5<br>-Office 365 E3, 企业移动性 + 安全性 E5 和 Windows 10 企业版 e5<br><br>现有企业协议客户可能需要遵循指导以在 Azure AD 租户中启用 Windows 10 企业版订阅激活。 有关详细信息, 请参阅[部署 Windows 10 企业版许可证](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses#enabling-subscription-activation-with-an-existing-ea)。<br><br>可以通过配置基于 Azure AD 组的许可, 使用安全组来分配产品许可证。 有关详细信息, 请参阅[什么是 Azure Active Directory 中的基于组的许可](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。<br><br>有关可用许可证的详细信息, 请参阅[Microsoft 365 许可](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
连接 |  所有 microsoft 托管桌面设备都需要连接到公司网络中的多个 microsoft 服务终结点。<br><br>有关所需 ip 和 url 的完整列表, 请参阅[网络配置](../get-ready/network.md)。 
Azure Active Directory |    azure Active Directory (azure AD) 必须是所有用户帐户的颁发机构的来源, 或者必须使用 azure AD Connect 的最新受支持版本从本地 Active Directory 同步用户帐户。<br><br>有关 azure ad connect 的详细信息, 请参阅[azure ad connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>有关受支持的 Azure AD connect 版本的详细信息, 请参阅[Azure ad connect: Version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)。
身份验证 |    如果 azure ad 不是用户帐户的颁发机构的来源, 则必须在 azure ad Connect 中配置以下各项之一:<br>-密码哈希同步<br>传递身份验证<br>-使用 ADFS 的联合<br><br>使用 Azure AD Connect 设置身份验证选项时, 还需要密码写回。 有关详细信息, 请参阅[密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>有关 Azure ad 的身份验证选项的详细信息, 请参阅[azure ad Connect user 登录选项](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Office 365 |    尽管不需要向 Microsoft 托管桌面注册, 但强烈建议将以下服务迁移到云:<br>-将电子邮件迁移到基于云的邮箱、exchange online, 或使用 exchange online 混合 (本地 exchange 2013 或更高版本) 进行配置。<br>-文件和文件夹–迁移到 OneDrive for business/SharePoint Online。<br>-在线协作工具–迁移到团队。
设备管理 | microsoft 托管桌面设备需要使用 Microsoft Intune 进行管理。 必须将 Intune 设置为移动设备管理机构。<br><br>有关详细信息, 请参阅[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
数据备份和恢复 | Microsoft 托管桌面需要将文件同步到 OneDrive for business 以进行保护。 未同步到 OneDrive for business 的任何文件都不能由 Microsoft 托管桌面保证, 在设备交换期间可能会丢失, 或者支持需要设备重置的呼叫。<br><br>尽管这不是必需的, 但 Microsoft 托管桌面强烈建议从映射的网络驱动器迁移到适当的云解决方案。  

当你准备好开始使用 microsoft 托管桌面时, 请与你的 microsoft 帐户管理员联系。 
