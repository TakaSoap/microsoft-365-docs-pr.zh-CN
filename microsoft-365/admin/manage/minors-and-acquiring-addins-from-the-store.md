---
title: 未成年人和从应用商店获取加载项
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
description: 了解《一般数据保护条例》 (控制未成年人个人数据的 GDPR) 法规。
ms.openlocfilehash: 15b35798ba03132b35285dc16ce57b139e4d7222
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782360"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>未成年人和从应用商店获取加载项

《一般数据保护条例》 (GDPR) 是欧盟的一项法规，自 2018 年 5 月 25 日起生效。 它为用户提供数据的权限和保护权限。 GDPR 的一个方面是，未成年人无法将其个人数据发送给其父母或监护人未批准的当事人。 定义为次要的特定年龄取决于个人所在的区域。

对父母同意有法定规定的地区包括美国、韩国、英国和欧洲联盟。 对于这些区域，将阻止未成年人通过Azure Active Directory)  (从应用商店获取任何新的Office加载项，以及运行之前获取的加载项。 对于没有法定法规的国家/地区，不会有下载限制。

根据Azure Active Directory中指定的数据，用户确定为次要用户。 组织管理员负责声明该用户的法定年龄组和家长同意。

如果父/监护人使用特定加载项同意未成年人，则组织管理员可以使用集中式部署将该外接程序部署到所有同意的未成年人。

若要符合未成年人的 GDPR 要求，需要确保学校/组织中部署了以下Office版本之一。

 **对于 Word、Excel、PowerPoint 和Project**：

|平台|内部版本号|
|---|---|
|Microsoft 365 企业应用版 (当前频道) |9001.2138|
|Microsoft 365 企业应用版 (半年Enterprise频道) |8431.2159|
|Office 2016 for Windows|16.0.4672.1000|
|Office 2013 for Windows|15.0.5023.1000|
|Office 2016 for Mac|16.11.18020200|
|Office 网页版|不适用|

 **对于Outlook**：

|平台|内部版本号|
|---|---|
|WINDOWS (MSI) 的Outlook 2016|生成无 TBD|
|Windows (C2R) 的Outlook 2016|16.0.9323.1000|
|Office 2016 for Mac|16.0.9318.1000|
|Outlook适用于 iOS 的移动设备|2.75.0|
|适用于 Android 的Outlook移动设备|2.2.145|
|Outlook.com|不适用|

 **Office 2013 要求**

Word、Excel 和 PowerPoint 2013 for Windows 将支持相同的未成年人检查是否启用了 Active Directory 身份验证库 (ADAL) 。 符合性有两个选项，如下所述。

- **启用 ADAL**。 本文介绍如何为 Office 2013 启用 ADAL：[将Microsoft 365新式身份验证与Office客户端配合使用](../../enterprise/modern-auth-for-office-2013-and-2016.md)。<br/>还需要设置注册表项以启用 ADAL，如[在Windows设备上为 Office 2013 启用新式身份验证中](../security-and-compliance/enable-modern-authentication.md)所述。<br/>此外，还需要为 2013 Office安装以下 4 月更新：

  - [2013 Office安全更新说明：2018 年 4 月 10 日](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)

  - [2018 年 4 月 3 日，Office 2013 (KB4018333 的更新) ](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)

- **请勿启用 ADAL**。 如果无法在 2013 Office启用 ADAL，则建议使用组策略为Office客户端关闭应用商店。 此[处提供有关](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))如何关闭应用以Office设置的信息。

## <a name="related-articles"></a>相关文章

[在管理中心部署加载项](./manage-deployment-of-add-ins.md)

[在管理中心管理加载项](./manage-addins-in-the-admin-center.md)
