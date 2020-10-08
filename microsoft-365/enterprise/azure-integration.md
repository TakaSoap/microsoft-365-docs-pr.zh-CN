---
title: Azure 与 Microsoft 365 的集成
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: 如果要使用本地环境进行密码同步或单一登录，请将 Microsoft 365 与 Azure AD 集成。
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384750"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure 与 Microsoft 365 的集成

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft 365 使用 Azure Active Directory (Azure AD) 管理场景背后的用户身份。 Microsoft 365 订阅包括免费的 Azure AD 订阅，以便您可以将内部部署 Active Directory 域服务集成 (AD DS) ，以同步用户帐户和密码或设置单一登录。 您还可以购买高级功能，以便更好地管理帐户。
  
Azure AD 还提供其他功能，如管理集成的应用程序，可用于扩展和自定义 Microsoft 365 订阅。
  
您可以使用 Azure AD 部署顾问在 Microsoft 365 管理中心中进行引导式设置和配置体验 (您必须登录到 Microsoft 365) ：

 - [Azure AD Connect advisor](https://aka.ms/aadconnectpwsync)
 - [AD FS 部署顾问](https://aka.ms/adfsguidance)
 - [Azure AD 安装指南](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD 版本和 Microsoft 365 身份管理

如果你已付费订阅 Microsoft 365，你也会拥有免费的 Azure AD 订阅。 您可以使用 Azure AD 创建和管理用户和组帐户。 若要激活此订阅，您必须完成一次性注册。 之后，你可以从 Microsoft 365 管理中心访问 Azure AD。 

有关注册免费 Azure AD 订阅的说明，请参阅 [使用免费的 AZURE ad 订阅](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。 请勿直接转到 azure.microsoft.com 进行注册，否则你将结束与 microsoft Azure 的试用版或付费订阅（与 Microsoft 365 的免费 Azure AD 订阅分开）。 
  
使用免费订阅，可以与本地目录同步，设置单一登录，并与服务应用程序（如 Salesforce、DropBox 等）进行同步，并将其与许多软件同步。
  
如果需要增强的 AD DS 功能、双向同步和其他管理功能，可以将免费订阅升级到付费的高级订阅。 有关详细信息，请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/pricing/details/active-directory/)。
  
有关 Microsoft 365 和 Azure AD 的详细信息，请参阅 [microsoft 365 标识模型](about-microsoft-365-identity.md)。
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>扩展 Microsoft 365 租户的功能

|**功能**|**说明**|
|:-----|:-----|
|集成应用程序  <br/> |您可以向各个应用授予对您的 Microsoft 365 数据（如邮件、日历、联系人、用户、组、文件和文件夹）的访问权限。 你还可以在全局管理员级别授权这些应用，并通过在 Azure AD 中注册应用，使其对你的整个公司可用。 Formore 信息，请参阅 [适用于 Microsoft 365 管理员的集成应用和 AZURE AD](integrated-apps-and-azure-ads.md)。  <br/> 另请参阅 [单一登录](https://go.microsoft.com/fwlink/p/?LinkId=698604)。  <br/> |
|PowerApps  <br/> | Power apps 是可连接到现有数据源（如 SharePoint 列表和其他数据应用程序）的移动设备的重点应用程序。 有关详细信息，请参阅 [Create a PowerApp for a list In SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) 和 [PowerApps 页](https://powerapps.microsoft.com/) 。  <br/> |
   
## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)
