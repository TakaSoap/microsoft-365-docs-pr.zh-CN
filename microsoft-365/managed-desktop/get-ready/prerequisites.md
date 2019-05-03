---
title: Microsoft 托管桌面的先决条件
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 19bd7c553840b0de51f7b26a8f1206a9c5d7b3af
ms.sourcegitcommit: b27650d1388ca136f85fcc662fe3ba069e9ee895
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/02/2019
ms.locfileid: "33560051"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的先决条件

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Microsoft 托管桌面的成功在客户的基础结构中以已知、记录和商定的要求开始。 本节概述了这些 infastructure 要求。 

Microsoft FastTrack 可帮助客户满足这些要求, 并帮助你准备参与 Microsoft 托管桌面。 有关详细信息, 请参阅[Microsoft FastTrack](https://fasttrack.microsoft.com/about)。 

区域 | 先决条件详细信息
--- | ---
许可 |Microsoft 托管桌面需要以下 Microsoft 365 许可 (或等效项):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 + 安全 E5<br><br>有关可用许可证的详细信息, 请参阅[Microsoft 365 许可](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
连接 |  所有 Microsoft 托管桌面设备都需要连接到公司网络中的多个 Microsoft 服务终结点。<br><br>有关所需 Ip 和 Url 的完整列表, 请参阅[网络配置](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必须是所有用户帐户的颁发机构的来源, 或者必须使用 Azure AD Connect 的最新受支持版本从本地 Active Directory 同步用户帐户。<br><br>有关 Azure AD Connect 的详细信息, 请参阅[AZURE Ad connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>有关受支持的 Azure AD Connect 版本的详细信息, 请参阅[AZURE Ad connect: Version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)。
身份验证 |    如果 Azure AD 不是用户帐户的颁发机构的来源, 则必须在 Azure AD Connect 中配置以下各项之一:<br>-密码哈希同步<br>传递身份验证<br>-使用 ADFS 的联合<br><br>使用 Azure AD Connect 设置身份验证选项时, 还需要密码写回。 有关详细信息, 请参阅[密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>有关 Azure AD 的身份验证选项的详细信息, 请参阅[AZURE Ad Connect user 登录选项](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Office 365 |    尽管不需要向 Microsoft 托管桌面注册, 但强烈建议将以下服务迁移到云:<br>-将电子邮件迁移到基于云的邮箱、Exchange online, 或使用 exchange Online 混合 (本地 Exchange 2013 或更高版本) 进行配置。<br>-文件和文件夹–迁移到 OneDrive for business/SharePoint Online。<br>-在线协作工具–迁移到团队。
设备管理 | Microsoft 托管桌面设备需要使用 Microsoft Intune 进行管理。 必须将 Intune 设置为移动设备管理机构。<br><br>有关详细信息, 请参阅[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
数据备份和恢复 | Microsoft 托管桌面需要将文件同步到 OneDrive for Business 以进行保护。 未同步到 OneDrive for business 的任何文件都不能由 Microsoft 托管桌面保证, 在设备交换期间可能会丢失, 或者支持需要设备重置的呼叫。<br><br>尽管这不是必需的, 但 Microsoft 托管桌面强烈建议从映射的网络驱动器迁移到适当的云解决方案。  

当你准备好开始使用 Microsoft 托管桌面时, 请与你的 Microsoft 帐户管理员联系。 
