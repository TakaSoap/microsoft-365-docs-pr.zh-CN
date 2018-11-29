---
title: Microsoft 托管桌面的系统必备
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: a7e82c0f4301b00e3d9e923dca10d1630744b8c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865911"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的系统必备

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

与 Microsoft 托管桌面成功开头的客户的基础结构的已知、 记录，和商定的要求。本节概述了这些先决条件。 

Microsoft FastTrack 是可用于帮助客户满足这些要求，并帮助您准备参与现代工作区中作为服务。有关详细信息，请参阅[Microsoft FastTrack](https://fasttrack.microsoft.com/about)。 

区域 | 必备的详细信息
--- | ---
许可 | Microsoft 365 E5 许可证或等同许可证是必需的。<br><br>此许可证包括 Office 365 E5、 Windows 10 企业 E5 和企业移动 + 安全 (EMS) E5。有关详细信息，请参阅[Microsoft 365 授权](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
连接 |  所有 Microsoft 托管桌面设备都需要连接到大量 Microsoft 服务终结点从组织网络内部，包括：<br>Windows 更新<br>-Microsoft Store for Business<br>-Azure Active Directory<br>Windows 错误报告<br>-联机崩溃分析<br>的连接用户体验和遥测<br>-用于 Windows 10 OneDrive 应用程序<br><br>可以在[代理配置](../get-ready/network.md)中找到的 Url 和的完整列表所需的 IP 的。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必须是为所有用户帐户，认证源或必须从本地 Active Directory 使用 Azure AD 连接，版本 1.1.654.0 同步用户帐户或更高版本。有关详细信息，请参阅[Azure AD 连接](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
身份验证 |    如果 Azure AD 不是用户帐户的认证源，则必须配置这些在 Azure AD 连接之一：<br>-密码哈希同步 （推荐）<br>-传递身份验证<br>联合身份验证与 ADFS<br><br>当设置 Azure AD 连接密码写回身份验证选项也是必需的。有关详细信息，请参阅[密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。<br><br>Azure AD 身份验证选项的详细信息，请参阅[Azure AD 连接用户登录选项](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Office 365 |    强烈建议到云迁移以下服务：<br>-电子邮件-将迁移到基于云的邮箱，Exchange online 或 Exchange Online 混合部署与 Exchange 2013 或更高版本，在本地配置。<br>-文件和文件夹 — 将迁移到 SharePoint Online/Office 365。<br>-Skype for Business – 迁移到 Skype 业务联机。<br>设备管理-Microsoft Intune A cloud only MDM 解决方案 （非混合） 是必需的它允许 IT 管理员可以管理 Microsoft 托管桌面设备世界任何地方使用可从 web 控制台。Microsoft Intune 是必需的 MDM 解决方案。<br><br>有关详细信息，请参阅[Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
数据的备份和恢复 | Microsoft 托管桌面需要要用于保护同步到 OneDrive for Business 的文件。任何未同步到 OneDrive for Business 的文件不能保证由 Microsoft 托管桌面和设备交换或需要重新启动设备的支持呼叫过程中可能会丢失。Microsoft 托管桌面不支持映射的网络驱动器。  

[了解如何满足 Microsoft 托管桌面注册的必备组件。](../get-ready/index.md)

已准备好开始使用 Microsoft 托管桌面时，请联系 Microsoft 帐户管理器。 