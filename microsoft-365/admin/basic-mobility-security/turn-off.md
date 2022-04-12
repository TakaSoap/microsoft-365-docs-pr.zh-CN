---
title: 关闭基本移动性和安全性
f1.keywords: NOCSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 删除组或策略以关闭基本移动性和安全性。
ms.openlocfilehash: c3c82c040e688977a68e06639e87c8f733bc8c38
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780756"
---
# <a name="turn-off-basic-mobility-and-security"></a>关闭基本移动性和安全性

若要有效关闭基本移动性和安全性，请从设备管理策略中删除由安全组定义的人员组，或自行删除策略。

- 通过从创建的设备策略中删除用户安全组来删除用户组。

- 删除所有基本移动性和安全性设备策略，为每个人禁用基本移动性和安全性。

这些选项删除了组织中设备的基本移动性和安全性强制。 遗憾的是，设置后，不能简单地“取消预配”基本移动性和安全性。

> [!IMPORTANT]
> 从策略中删除用户安全组或自行删除策略时，请注意对用户设备的影响。 例如，可能会删除电子邮件配置文件和缓存的电子邮件，具体取决于设备。 有关详细信息，请参阅 [删除策略或从策略中删除用户时会发生什么情况？](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>从基本移动性和安全性设备策略中删除用户安全组

1. 在浏览器类型中： [https://protection.office.com/devicev2](https://protection.office.com/devicev2).

2. 选择设备策略，然后选择 **“编辑策略**”。

3. 在 **“部署** ”页上，选择 **“删除**”。

4. 在 **“组**”下，选择一个安全组。

5. 选择 **“删除**”，然后选择 **“保存**”。

## <a name="remove-basic-mobility-and-security-device-policies"></a>删除基本移动性和安全性设备策略

1. 在浏览器类型中： [https://protection.office.com/devicev2](https://protection.office.com/devicev2).

2. 选择设备策略，然后选择 **“删除”策略**。

3. 在“警告”对话框中，选择 **“是**”。

> [!NOTE]
> 有关在组织设备仍处于受阻状态时取消阻止设备的更多步骤，请参阅博客文章[“从Office 365 移动设备管理中删除访问控制](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)。
