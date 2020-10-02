---
title: Microsoft 托管桌面的系统必备
description: 在 Microsoft 托管桌面中注册前要设置的许可证、Azure 帐户、身份验证设置和 Microsoft 365 设置
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d5aaba3d1f8606ab69b360d5916a5c9a8a653a14
ms.sourcegitcommit: e87015bf29ad15688137c785d93f2c79ca3208f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48343279"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的系统必备

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

本主题概述了为确保 Microsoft 托管桌面成功而必须满足的基础结构要求。 


区域 | 先决条件详细信息
--- | ---
许可 |Microsoft 托管桌面需要 microsoft 365 E3 许可证和 Microsoft Defender for Endpoint 和 Azure Active Directory Premium 2 (或等效) 。<br>有关特定服务计划的详细信息，请参阅本主题中 [有关许可证的详细](#more-about-licenses) 信息。<br>有关可用许可证的详细信息，请参阅 [Microsoft 365 许可](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。
连接 |  所有 Microsoft 托管桌面设备都需要连接到公司网络中的多个 Microsoft 服务终结点。<br><br>有关所需 Ip 和 Url 的完整列表，请参阅 [网络配置](../get-ready/network.md)。 
Azure Active Directory |    Azure Active Directory (Azure AD) 必须是所有用户帐户的颁发机构的来源，或者必须使用 Azure AD Connect 的最新受支持版本从本地 Active Directory 同步用户帐户。<br><br>必须为 Microsoft 托管桌面用户启用[企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview)。<br><br>有关详细信息，请参阅 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)。<br><br>有关受支持的 Azure AD Connect 版本的详细信息，请参阅 [AZURE Ad connect： Version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)。
身份验证 |    如果 Azure AD 不是用户帐户的主身份验证源，则必须在 Azure AD Connect 中配置以下各项之一：<br>-密码哈希同步<br>传递身份验证<br>-外部标识提供程序 (，其中包括 Windows Server ADFS 和非 Microsoft Idp) 配置为符合 Azure AD 集成要求。 有关详细信息，请参阅 [指南](https://www.microsoft.com/download/details.aspx?id=56843) 。 <br><br>使用 Azure AD Connect 设置身份验证选项时，还建议使用密码写回。 有关详细信息，请参阅 [密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 <br><br>如果实施了外部标识提供程序，则必须验证解决方案：<br>-满足 Azure AD 集成要求<br>-支持 Azure AD 条件访问，这是为了能够配置 MMD 设备合规性策略<br>-为 microsoft 托管桌面的一部分启用设备注册和使用所需的 Microsoft 365 服务或功能 <br><br>有关 Azure AD 的身份验证选项的详细信息，请参阅 [AZURE Ad Connect user 登录选项](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)。
Microsoft 365 | 必须为 Microsoft 托管桌面用户启用 OneDrive for Business。<br><br>尽管不需要向 Microsoft 托管桌面注册，但强烈建议将以下服务迁移到云：<br>-电子邮件：迁移到基于云的邮箱、Exchange online 或使用 exchange Online 混合（本地 Exchange 2013 或更高版本）进行配置。<br>-文件和文件夹：迁移到 OneDrive for business 或 SharePoint Online。<br>-在线协作工具：迁移到团队。
设备管理 | Microsoft 托管桌面设备需要使用 Microsoft Intune 进行管理。 必须将 Intune 设置为移动设备管理机构。<br><br>有关详细信息，请参阅 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)。 
数据备份和恢复 |  Microsoft 托管桌面需要将文件同步到 OneDrive for Business 以进行保护。 未同步到 OneDrive for business 的任何文件都不能由 Microsoft 托管桌面保证，在设备交换过程中可能会丢失，或者支持需要设备重置的呼叫。<br><br>尽管这不是必需的，但 Microsoft 托管桌面强烈建议从映射的网络驱动器迁移到适当的云解决方案。 有关详细信息，请参阅 [准备 Microsoft 托管桌面的映射驱动器](mapped-drives.md)

当你准备好开始使用 Microsoft 托管桌面时，请与你的 Microsoft 帐户管理员联系。 

## <a name="more-about-licenses"></a>有关许可证的详细信息

Microsoft 托管桌面需要特定的许可证选项才能正常运行。 有关如何使用这些许可证的信息，请参阅 [Microsoft 托管桌面技术](../intro/technologies.md) 。

> [!TIP]
> 若要将这些许可证选项分配给特定用户，建议您利用 Azure Active Directory 的 [基于组的许可功能](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) 。

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 企业版  
- Microsoft Defender for Endpoint
- Microsoft 365 企业应用版
- Microsoft Teams
- [SharePoint Online 计划 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online 计划 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> 你的 Microsoft 帐户管理员将帮助你查看你当前的许可证和服务计划，并查找最有效的路径，以获取你可能需要的任何其他许可证或服务计划，同时避免重复。
