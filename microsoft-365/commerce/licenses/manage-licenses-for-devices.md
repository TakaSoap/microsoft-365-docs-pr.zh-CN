---
title: 管理设备的许可证
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: 了解如何将许可证分配给组以用于设备。
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238370"
---
# <a name="manage-licenses-for-devices"></a>管理设备的许可证

如果您有 Office 365 专业增强版教育版（设备），您可以使用 Azure AD 组将许可证分配给设备。 当设备具有许可证时，使用该设备的任何人都可以使用 Office 365。 例如，假设你的组织中的人员使用20台膝上型电脑和平板电脑。 将许可证分配给每个设备时，登录到其中一个设备的每个人都将使用 Office 365，而无需自己的许可证。

> [!IMPORTANT]
> Office 365 专业增强版教育版（设备）仅适用于教育版 A3 和 A5 批量许可客户。

若要开始，请在 Azure Active Directory 管理中心中创建一个组，然后将设备分配到该组。 若要了解有关设备许可的详细信息（包括设备要求、可以使用哪些类型的组以及如何将 Office 365 专业增强版配置为使用设备许可），请参阅[适用于 office 365 专业增强版的设备许可教育客户](https://go.microsoft.com/fwlink/p/?linkid=2094216)。

> [!IMPORTANT]
> 您必须是全局管理员才能完成本文中的任务。

## <a name="assign-licenses-to-devices"></a>将许可证分配给设备

将许可证分配给组时，会将许可证分配给组中的所有设备。 您只能将一个订阅分配给任何单个组。

1. 在 Microsoft 365 管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。
2. 在 "**许可证**" 页上，选择 " **Office 365 专业增强版教育版（设备）**"。
3. 在 " **Office 365 专业增强版教育版（设备）** " 页上，选择 "订阅"，然后选择 "**分配许可证**"。
4. 在 "**将许可证分配给组**" 窗格中，开始键入组名称，然后从结果中选择它以将其添加到列表中。
6. 选择 "**分配**"，然后选择 "**关闭**"。

## <a name="unassign-licenses-from-devices"></a>从设备中取消分配许可证

从组中取消分配许可证时，将从组内的所有设备中删除许可证。 所有应用及其关联的数据都是只读的。

1. 在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。
2. 在 "**许可证**" 页上，选择 " **Office 365 专业增强版教育版（设备）**"。
3. 在 " **Office 365 专业增强版教育版（设备）** " 页上，选择 "订阅"，选择 "**更多操作**"，然后选择 "未**分配许可证**"。
5. 在 "未**分配许可证**" 对话框中，选择 "未**分配**"。