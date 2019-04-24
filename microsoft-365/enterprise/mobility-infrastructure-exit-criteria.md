---
title: 移动设备管理基础结构退出条件
description: microsoft 365 企业版包括使用 Microsoft Intune 的移动设备管理。 查看要求和先决条件、使用 Azure Active Directory 资源设置 Intune、注册 iOS、macOS、Android 和 Windows 设备、部署应用、创建配置配置文件、使用合规性策略, 以及为移动启用条件访问Microsoft 365 企业版的设备管理。
keywords: microsoft 365, microsoft 365 企业版, microsoft 365 文档, 移动设备管理, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291229"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>移动设备管理基础结构退出条件

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*这适用于 Microsoft 365 企业版的 E3 和 E5 版本*

确保您的配置满足以下针对移动设备管理基础结构的要求。

- 已设置 Intune，包括通过创建 Azure AD 用户和组为设备应用组织的规则。
- 在 Intune 中有已注册设备，这样设备便能收到你创建的策略。
- 向设备添加了应用，这样用户便能访问组织的 Microsoft 365 云服务（如 Exchange Online 和 SharePoint Online）。
- 已使用你创建的 Azure AD 用户和组来配置功能和设置，并将它们应用于设备，这可能包括启用防病毒功能和限制特定应用。
- 已制定合规性策略，对设备上的防火墙或密码长度有所要求。如果设备不合规，条件访问就会阻止访问组织的数据。



## <a name="results-and-next-steps"></a>结果和后续步骤

你的设备已在 Intune 中注册并配置了适当的策略。

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| 如果你按照 Microsoft 365 企业版端到端部署的阶段执行, 下一阶段是[信息保护](infoprotect-infrastructure.md)。 |
