---
title: 关闭基本移动性和安全性
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 删除组或策略以关闭基本移动性和安全性。
ms.openlocfilehash: 7ec4ec0d47668c21824d8e01e3845d637b9b0922
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59169868"
---
# <a name="turn-off-basic-mobility-and-security"></a>关闭基本移动性和安全性

若要有效关闭基本移动性和安全性，请从设备管理策略中删除由安全组定义的用户组，或者删除策略本身。

- 通过从已创建的设备策略中删除用户安全组来删除用户组。

- 通过删除所有基本移动和安全设备策略，为所有人禁用基本移动性和安全性。

这些选项将删除组织中设备的基本移动性和安全性强制。 遗憾的是，设置基本移动性和安全性后，不能简单地"取消设置"基本移动性和安全性。

> [!IMPORTANT]
> 在从策略中删除用户安全组或删除策略本身时，请注意对用户设备的影响。 例如，可能会删除电子邮件配置文件和缓存的电子邮件，具体取决于设备。 有关详细信息，请参阅删除策略或从策略中删除用户  [时会发生什么情况？](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>从基本移动性和安全设备策略中删除用户安全组

1. 在浏览器类型中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ：。

2. 选择设备策略，然后选择编辑 **策略**。

3. 在" **部署"**   页上，选择"删除 **"。**

4. 在  **"组**"下，选择一个安全组。

5. 选择  **"删除**"，然后选择"**保存"。**

## <a name="remove-basic-mobility-and-security-device-policies"></a>删除基本移动性和安全性设备策略

1. 在浏览器类型中  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ：。

2. 选择设备策略，然后选择删除  **策略**。

3. 在"警告"对话框中，选择"**是"。**

> [!NOTE]
> 有关在组织设备仍处于阻止状态时取消阻止设备的更多步骤，请参阅博客文章从 Office 365 移动设备管理[。](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
