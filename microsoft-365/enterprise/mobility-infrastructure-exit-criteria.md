---
title: 移动设备管理基础结构退出条件
description: Microsoft 365 企业版包括使用 Microsoft Intune 的移动设备管理。 查看要求和先决条件、使用 Azure Active Directory 资源设置 Intune、注册 iOS、macOS、Android 和 Windows 设备、部署应用、创建配置配置文件、使用合规性策略，以及为移动启用条件访问Microsoft 365 企业版的设备管理。
keywords: Microsoft 365，Microsoft 365 企业版，Microsoft 365 文档，移动设备管理，Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: daf7bcf6525f30b7b52065e4f6bf2ff335f4ea4b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600879"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>移动设备管理基础结构退出条件

![阶段 5：移动设备管理](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*这适用于 Microsoft 365 企业版的 E3 和 E5 版本*

确保您的配置满足以下针对移动设备管理基础结构的要求。

- 安装 Intune，包括创建 Azure Active Directory （Azure AD）用户和组，以应用组织的设备规则。
- 在 Intune 中有已注册设备，这样设备便能收到你创建的策略。
- 向设备添加了应用，这样用户便能访问组织的 Microsoft 365 云服务（如 Exchange Online 和 SharePoint Online）。
- 已使用你创建的 Azure AD 用户和组来配置功能和设置，并将它们应用于设备，这可能包括启用防病毒功能和限制特定应用。
- 合规性策略已准备好，需要在设备上使用防火墙或密码长度。 如果设备不合规，则条件访问会阻止对组织数据的访问。

## <a name="results-and-next-steps"></a>结果和后续步骤

你的设备已在 Intune 中注册并配置了适当的策略。

|||
|:-------|:-----|
|![第 6 阶段：信息保护](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| 如果你按照 Microsoft 365 企业版端到端部署的阶段执行，下一阶段是[信息保护](infoprotect-infrastructure.md)。 |
