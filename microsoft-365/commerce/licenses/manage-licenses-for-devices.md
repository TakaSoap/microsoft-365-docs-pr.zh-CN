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
ms.openlocfilehash: 1a525117c25a2471ad696ef1447fd7e4ccb6bed0
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011181"
---
# <a name="manage-licenses-for-devices"></a>管理设备的许可证

如果你有 Microsoft 365 Apps for enterprise （设备）或 Microsoft 365 Apps 教育（设备），你可以使用 Azure AD 组将许可证分配给设备。 当设备具有许可证时，使用该设备的任何人都可以使用适用于企业的 Microsoft 365 应用（以前称为 Office 365 专业增强版）。 例如，假设你的组织中的人员使用20台膝上型电脑和平板电脑。 将许可证分配给每个设备时，登录其中一个设备的每个人都将使用 Microsoft 365 应用程序进行企业，而无需自己的许可证。

> [!IMPORTANT]
> 适用于企业的 Microsoft 365 应用程序的基于设备的许可仅作为一些商业客户和一些教育客户的附加许可证提供。 对于商业客户，许可证是*Microsoft 365 企业版（设备）应用程序*，并且只能通过企业协议/企业协议订阅使用。 对于教育版客户，许可证是*Microsoft 365 教育版（设备）应用程序*，仅通过注册教育版解决方案（EES）提供。 有关详细信息，请阅读 "教育版上的博客文章"[可用性](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)。 若要获得商业可用性，请联系你的 Microsoft 帐户代表。

若要开始，请在 Azure Active Directory 管理中心中创建一个组，然后将设备分配到该组。 若要了解有关设备许可的详细信息（包括设备要求、可以使用的组类型以及如何将 Microsoft 365 应用程序配置为使用设备许可），请参阅[适用于企业的 microsoft 365 应用程序的基于设备的许可](https://go.microsoft.com/fwlink/p/?linkid=2094216)。

> [!IMPORTANT]
> 您必须是全局管理员才能完成本文中的任务。

## <a name="assign-licenses-to-devices"></a>将许可证分配给设备

将许可证分配给组时，会将许可证分配给组中的所有设备。 您只能将一个订阅分配给任何单个组。

1. 在 Microsoft 365 管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。
2. 在 "**许可证**" 页上，选择 "**适用于教育的 Microsoft 365 应用程序（设备）** " 或 "适用**于企业的 microsoft 365 应用（设备）**"。
3. 在下一页上，选择 "订阅"，然后选择 "**分配许可证**"。
4. 在 "**将许可证分配给组**" 窗格中，开始键入组名称，然后从结果中选择它以将其添加到列表中。
5. 选择 "**分配**"，然后选择 "**关闭**"。

## <a name="unassign-licenses-from-devices"></a>从设备中取消分配许可证

从组中取消分配许可证时，将从组内的所有设备中删除许可证。 所有应用及其关联的数据都是只读的。

1. 在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。
2. 在 "**许可证**" 页上，选择 "**适用于教育的 Microsoft 365 应用程序（设备）** " 或 "适用**于企业的 microsoft 365 应用（设备）**"。
3. 在下一页上，选择 "订阅"，选择 "**更多操作**"，然后选择 "未**分配许可证**"。
4. 在 "未**分配许可证**" 对话框中，选择 "未**分配**"。