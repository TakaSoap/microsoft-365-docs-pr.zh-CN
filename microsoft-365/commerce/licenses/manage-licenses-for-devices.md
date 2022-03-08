---
title: 管理设备的许可证
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
description: 了解如何将许可证分配给组以用于设备。
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
- okr_SMB
search.appverid: MET150
ms.date: 08/27/2021
ms.openlocfilehash: fd452cb52a1c65a59e478fb80438ac95a57e8bf6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311783"
---
# <a name="manage-licenses-for-devices"></a>管理设备的许可证

如果你拥有Microsoft 365 企业应用版 (设备) 或 Microsoft 365 应用版 for Education () ，可以使用 Azure AD 组向设备分配许可证。 当设备具有许可证时，使用该设备的任何人都可以使用Microsoft 365 企业应用版 (之前Office 365 专业增强版) 。 例如，假设你拥有 20 台笔记本电脑和平板电脑，供组织人员使用。 向每台设备分配许可证时，登录到其中一台设备的每个人将使用Microsoft 365 企业应用版而无需自己的许可证。

> [!IMPORTANT]
> 某些商业客户Microsoft 365 企业应用版教育客户只能使用基于设备的许可作为附加许可证。 对于商业客户，许可证Microsoft 365 企业应用版 (*设备*) ，并且仅通过 企业协议/企业协议 订阅提供。 对于教育行业客户，许可证Microsoft 365 应用版 *教育 (设备*) ，并且仅通过注册教育版解决方案 (EES) 。 有关详细信息，请阅读有关教育可用性 [的博客文章](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)。 要获得商业可用性，请联系你的 Microsoft 帐户代表。

首先，在管理中心Azure Active Directory组，然后将设备分配给该组。 若要了解有关设备许可（包括设备要求、可以使用的组类型以及如何配置 Microsoft 365 企业应用版 以使用设备许可）的信息，请参阅基于设备的许可[Microsoft 365 企业应用版。](/deployoffice/device-based-licensing)

> [!IMPORTANT]
> 你必须是全局管理员才能完成本文中的任务。

## <a name="assign-licenses-to-devices"></a>向设备分配许可证

将许可证分配给组时，需要将许可证分配给组内的所有设备。 只能向任何单个组分配一个订阅。

1. In the Microsoft 365 管理中心， go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a>  >  page.
2. 在许可证 **页面上**，选择 **Microsoft 365 应用版教育 (设备**) 或 **Microsoft 365 企业应用版 (设备)**。
3. 下一页上，选择订阅，然后选择分配 **许可证**。
4. 在 **"将许可证分配给组** "窗格中，开始键入组名称，然后从结果中选择它以将其添加到列表中。
5. 选择 **"分配"**，然后选择" **关闭"**。

## <a name="unassign-licenses-from-devices"></a>从设备取消分配许可证

从组取消分配许可证时，会从组内的所有设备中删除许可证。 然后，所有应用及其关联数据都是只读的。

1. In the admin center， go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a>  >  page.
2. 在许可证 **页面上**，选择 **Microsoft 365 应用版教育 (设备**) 或 **Microsoft 365 企业应用版 (设备)**。
3. On the next page， choose a subscription， select the three dots (more actions) ， and then choose **Unassign licenses**.
4. 在" **取消分配许可证** "对话框中，选择" **取消分配"**。
