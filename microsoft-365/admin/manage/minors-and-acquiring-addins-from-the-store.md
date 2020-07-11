---
title: 向应用商店中的未成年人和收购外接程序
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解常规数据保护法规 (GDPR) 管理未成年人的个人数据的管理法规。
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103087"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>向应用商店中的未成年人和收购外接程序

一般数据保护法规 (GDPR) 是一种欧洲联合法规，生效时间可能为25，2018。 它向用户提供对其数据的权限并加以保护。 GDPR 的其中一个方面是，未成年人的个人数据不能发送给其家长或监护人尚未批准的当事人。 定义为次要的特定年龄取决于个人所在的区域。
  
具有关于家长同意的法令法规的地区包括美国、韩国、英国和欧盟。 对于这些区域，将通过 Azure Active Directory)  (阻止从存储中获取任何新的 Office 外接程序，并运行之前获取的外接程序，从而阻止了次要区域。 对于没有法令法规的国家/地区，将不提供下载限制。
  
根据 Azure Active Directory 中指定的数据，将用户确定为次要用户。 组织管理员负责声明法律年龄组和该用户的家长同意。
  
如果父/监护人同意使用特定的外接程序，组织管理员可以使用集中部署将该外接程序部署到所有已同意的未成年人。
  
若要符合 GDPR 的要求，您需要确保在学校/组织中部署以下 Office 内部版本之一。
 
 **对于 Word、Excel、PowerPoint 和 Project**： 

|**平台** <br/> |**内部版本号** <br/> |
|:-----|:-----|
|适用于企业版 (当前频道) 的 Microsoft 365 应用程序  <br/> |9001.2138   <br/> |
|适用于企业版的 Microsoft 365 应用 (半年企业频道)   <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Office 网页版  <br/> |无  <br/> |
   
 **对于 Outlook**： 
  
|**平台** <br/> |**内部版本号** <br/> |
|:-----|:-----|
|适用于 Windows (MSI) 的 Outlook 2016  <br/> |生成不 TBD  <br/> |
|Outlook 2016 for Windows (C2R)   <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|适用于 iOS 的 Outlook mobile  <br/> |2.75.0  <br/> |
|Outlook mobile for Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |无  <br/> |

 **Office 2013 要求**
  
Word、Excel 和 PowerPoint 2013 for Windows 将支持相同的未成年人检查（如果 Active Directory 身份验证库 (ADAL) 已启用）。 有两种合规性选项，如下所述。
  
- **启用 ADAL**。 本文介绍如何为 Office 2013 启用 ADAL：使用适用[于 office 客户端的 Microsoft 365 新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。<br/>您还需要将注册表项设置为启用 ADAL，如在[Windows 设备上为 Office 2013 启用新式验证](../security-and-compliance/enable-modern-authentication.md)中所述。<br/>此外，还需要为 Office 2013 安装以下四月份更新：
    
  - [Office 2013 安全更新说明：4月10日，2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018年4月3日，Office 2013 (KB4018333) 的更新](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **不启用 ADAL**。 如果无法在 Office 2013 中启用 ADAL，我们建议使用组策略关闭 Office 客户端的存储。 有关如何关闭 "Office 相关应用程序" 设置的信息位于[此处](https://technet.microsoft.com/library/cc178992.aspx)。

## <a name="related-articles"></a>相关文章

[在管理中心部署外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[在管理中心中管理外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
