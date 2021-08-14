---
title: 管理设备的许可证
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: 了解如何将许可证分配给组以用于设备。
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: 5866fd7ae42a8e127250a2f02c7378381b736da54027ab80bab1228fbef23e33
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53820907"
---
# <a name="manage-licenses-for-devices"></a>管理设备的许可证

如果你有适用于教育Microsoft 365 企业应用版 () Microsoft 365 应用版的设备 () ，可以使用 Azure AD 组向设备分配许可证。 当设备具有许可证时，使用该设备的任何人都可以使用Microsoft 365 企业应用版 (之前Office 365 专业增强版) 。 例如，假设你拥有 20 台笔记本电脑和平板电脑，供组织人员使用。 向每台设备分配许可证时，登录到其中一台设备的每个人将使用Microsoft 365 企业应用版而无需自己的许可证。

> [!IMPORTANT]
> 某些商业客户Microsoft 365 企业应用版教育版客户的基于设备的许可仅作为附加许可证提供。 对于商业客户，许可证Microsoft 365 企业应用版 (*设备*) 并且仅通过 企业协议/企业协议 订阅提供。 对于教育行业客户，许可证Microsoft 365 应用版 *教育* 版 (设备) 并且仅通过注册教育版解决方案 (EES) 。 有关详细信息，请阅读有关教育可用性 [的博客文章](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)。 要获得商业可用性，请联系你的 Microsoft 帐户代表。

首先，在管理中心Azure Active Directory组，然后将设备分配给该组。 若要了解有关设备许可（包括设备要求、可以使用的组类型以及如何配置 Microsoft 365 企业应用版 以使用设备许可）的信息，请参阅基于设备的许可[Microsoft 365 企业应用版。](/deployoffice/device-based-licensing)

> [!IMPORTANT]
> 你必须是全局管理员才能完成本文中的任务。

## <a name="assign-licenses-to-devices"></a>向设备分配许可证

将许可证分配给组时，需要将许可证分配给组内的所有设备。 只能向任何单个组分配一个订阅。

1. In the Microsoft 365 管理中心， go to the **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.
2. 在许可证 **页面上**，选择 **Microsoft 365 应用版 for Education (device)** 或 Microsoft 365 企业应用版 (device **)**。
3. On the next page， choose a subscription， then choose **Assign licenses**.
4. 在 **"将许可证分配给组** "窗格中，开始键入组名称，然后从结果中选择它以将其添加到列表中。
5. 选择 **"分配"，** 然后选择"**关闭"。**

## <a name="unassign-licenses-from-devices"></a>取消分配设备中的许可证

从组取消分配许可证时，会从组内的所有设备中删除许可证。 然后，所有应用及其关联数据都是只读的。

1. 在管理中心，转到"帐单  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">""许可证"</a>页面。
2. 在许可证 **页面上**，选择 **Microsoft 365 应用版 for Education (device)** 或 Microsoft 365 企业应用版 (device **)**。
3. On the next page， choose a subscription， select the three dots (more actions) ， and then choose **Unassign licenses**.
4. 在"**取消分配许可证**"对话框中，选择"**取消分配"。**
