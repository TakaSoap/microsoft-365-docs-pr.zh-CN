---
title: 次要加载项和从应用商店获取加载项
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 了解 GDPR 一般数据保护 () 管理未成年人个人数据的一般数据保护条例。
ms.openlocfilehash: 84a1ecc9eb5d29ae1c2e4597b8299430cc3de038
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173063"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>次要加载项和从应用商店获取加载项

GDPR 一般 (条例) 欧盟法规，于 2018 年 5 月 25 日生效。 它为用户提供了访问和保护其数据的权利。 GDPR 的一个方面是，未成年人无法将他们的个人数据发送给其家长或监护人尚未批准的各方。 定义为未成年人的特定年龄取决于个人所在的地区。
  
具有有关家长同意的法规的区域包括美国、韩国、英国和欧盟。 对于这些区域，将阻止 (通过 Azure Active Directory) 从应用商店获取任何新的 Office 外接程序并运行之前获取的外接程序。 对于没有法规的国家/地区，将没有下载限制。
  
根据用户信息中指定的数据，将用户确定为Azure Active Directory。 组织管理员负责声明法定年龄组和该用户的家长同意。
  
如果家长/监护人同意使用特定加载项的未成年人，则组织管理员可以使用集中部署将加载项部署到所有获得同意的未成年人。
  
若要使未成年人符合 GDPR，你需要确保学校/组织中部署以下Office版本之一。
 
 **对于 Word、Excel、PowerPoint 和 Project：** 

|**平台** <br/> |**内部版本号** <br/> |
|:-----|:-----|
|Microsoft 365 企业应用版 (当前频道)   <br/> |9001.2138   <br/> |
|Microsoft 365 企业应用版 (半年频道Enterprise频道)   <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Office 网页版  <br/> |不适用  <br/> |
   
 **例如Outlook：** 
  
|**平台** <br/> |**内部版本号** <br/> |
|:-----|:-----|
|Outlook 2016 MSI Windows ()   <br/> |生成无 TBD  <br/> |
|Outlook 2016 C2R Windows (C2R)   <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook iOS 移动版  <br/> |2.75.0  <br/> |
|Outlook Android 移动版  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |不适用  <br/> |

 **Office 2013 要求**
  
如果启用了 Active Directory 身份验证库 (ADAL) ，适用于 Windows 的 Word、Excel 和 PowerPoint 2013 将支持相同的次要) 检查。 有两种合规性选项，如下文说明。
  
- **启用 ADAL**。 本文介绍如何为 Office 2013 启用 ADAL：Microsoft 365[客户端使用新式Office身份验证](../../enterprise/modern-auth-for-office-2013-and-2016.md)。<br/>还需要设置注册表项以启用 ADAL，如在 Windows 设备上为[Office 2013 启用新式验证Windows说明](../security-and-compliance/enable-modern-authentication.md)。<br/>此外，还需要安装 2013 年 4 月Office更新：
    
  - [2013 年 4 Office安全更新说明：2018 年 4 月 10 日](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018 年 4 月 3 日，Office 2013 (KB4018333) ](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **不要启用 ADAL**。 如果无法在 Office 2013 中启用 ADAL，则建议使用组策略为 Office 关闭应用商店。 有关关闭应用以启用Office的信息位于[此处](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))。

## <a name="related-articles"></a>相关文章

[在管理中心部署加载项](./manage-deployment-of-add-ins.md)

[在管理中心管理加载项](./manage-addins-in-the-admin-center.md)
