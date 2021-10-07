---
title: 准备情况评估工具
description: 说明这两种工具、它们运行的检查以及结果的含义
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: c584632a625ecb8597aa0c9319063e6f9198bec3
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216930"
---
# <a name="readiness-assessment-tools"></a>准备情况评估工具

为了在注册时获得尽可能流畅Microsoft 托管桌面，必须提前设置设置和其他参数，以及满足某些设备和网络要求。 一个工具（通过管理Microsoft 托管桌面访问）检查与管理相关的设置。 另一个可下载的工具可检查各个设备要求和网络设置。 可以使用这些工具检查这些设置，并接收修复任何错误的详细步骤。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>设备和网络的可下载准备情况评估检查程序

有关使用可下载的准备情况评估检查程序的详细信息，请参阅 [可下载的准备情况评估检查程序](readiness-assessment-downloadable.md)。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>用于管理设置的联机准备情况评估工具

联机[工具](https://aka.ms/mmdart)可Microsoft Endpoint Manager (Azure AD Microsoft Endpoint Manager (、Microsoft Intune) 、Azure Active Directory (Azure AD) 和 Microsoft 365 中的设置，以确保它们Microsoft 托管桌面。 Microsoft 托管桌面在 Azure AD 组织或租户管理中心中运行检查后，将与这些检查关联的数据保留 12 (12) 。 12 个月后，我们会以已取消标识的形式保留它。 你可以选择删除我们收集的数据。

至少具有全局读取者或 Intune 管理员角色的任何人都可以运行此工具，但条件访问策略和多重 (中的两项检查需要[](readiness-assessment-fix.md#conditional-access-policies)其他权限。 [](readiness-assessment-fix.md#multifactor-authentication)

> [!IMPORTANT]  
> 联机准备情况评估工具可帮助你检查首次Microsoft 托管桌面注册的准备情况。 如果你的组织已注册Microsoft 托管桌面，请勿使用此工具。

评估工具检查以下项：

## <a name="microsoft-intune-settings"></a>Microsoft Intune设置

|支票  |说明  |
|---------|---------|
|Autopilot 部署配置文件     | 验证 Autopilot 部署配置文件的分配是否适用于所有设备 (该配置文件不应分配给任何Microsoft 托管桌面设备。)        |
|证书连接器     | 检查证书连接器的状态以确保它们处于活动状态   |
|条件访问     | 验证条件访问策略是否未分配给所有 (不应将条件访问策略分配给Microsoft 托管桌面帐户。)     |
|设备合规性策略     | 检查未将 Intune 合规性策略分配给所有用户 (不应将策略分配给任何Microsoft 托管桌面设备。)     |
|设备配置文件     | 确认配置文件未分配给所有用户，或者不应将 (配置文件的所有设备分配给任何Microsoft 托管桌面设备。)      |
|设备类型限制     | 检查Windows 10你的组织中设备是否允许在 Intune 中注册        |
|注册状态页     | 确认未启用注册状态页      |
|Intune 注册     | 验证Windows 10 Azure AD 组织中设备是否自动在 Intune 中注册         |
|适用于企业的 Microsoft Store     | 确认已适用于企业的 Microsoft Store和 Intune 同步        |
|多重身份验证 | 验证多重身份验证是否未应用于Microsoft 托管桌面帐户。
|PowerShell 脚本     | 检查Windows PowerShell *脚本的分配* 方式是否面向 Microsoft 托管桌面 设备    |
|区域     | 检查你的区域是否受 Microsoft 托管桌面        |
|安全基线     | 检查安全基线配置文件不面向所有用户，或安全基线策略 (所有设备不应面向任何Microsoft 托管桌面设备。)        |
|Windows应用     | 查看你想要分配给Microsoft 托管桌面的应用      |
|Windows Hello 企业版     | 检查Windows Hello Business 是否已启用        |
|Windows 10更新圈     | 检查 Intune 的"Windows 10 更新圈"策略不面向所有用户或 (该策略不应面向任何Microsoft 托管桌面设备。)      |


## <a name="azure-active-directory-settings"></a>Azure Active Directory设置

|支票  |说明  |
|---------|---------|
|适用于状态漫游的Enterprise临时"订阅     | 建议如何检查设置，如果 (设置为"false"，) 可能会Enterprise状态漫游正常工作  |
|企业状态漫游     | 建议如何检查Enterprise漫游是否已启用       |
|许可证     | 检查是否获取了必要的 [许可证](prerequisites.md#more-about-licenses)         |
|多重身份验证     | 检查多重身份验证是否未应用于 (多重身份验证不得意外应用于Microsoft 托管桌面帐户。) |
|安全帐户名称   | 检查用户名称是否与保留供Microsoft 托管桌面的用户名冲突        |
|安全管理员角色     | 确认在 Microsoft Defender for Endpoint 中为具有安全读者、安全操作员或全局读者角色的用户分配了这些角色         |
|安全性默认值 | 检查 Azure AD 组织是否已启用安全Azure Active Directory |
|自助式密码重置     | 确认已启用自助服务密码重置        |
|标准用户角色     | 验证用户是标准用户，并且没有本地管理员权限         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 企业应用版设置

|支票  |说明  |
|---------|---------|
|OneDrive for Business     | 检查OneDrive for Business是否使用不受支持的设置。        |


对于每个检查，该工具将报告四个可能的结果之一：


|结果  |含义  |
|---------|---------|
|Ready     | 完成注册前无需任何操作。        |
|公告    | 按照工具中的步骤操作，实现注册和用户的最佳体验。 *你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。        |
|未就绪 | *如果不修复* 这些问题，注册将失败。 按照工具中的步骤进行解析。        |
|错误 | 你 (Azure Active Director) AD 角色没有足够的权限运行此检查。 |

## <a name="after-enrollment"></a>注册后

完成注册后，请记住Microsoft 托管桌面并调整某些 Intune 和 Azure AD 设置。 有关详细信息，请参阅 [在注册后调整设置](../get-started/conditional-access.md)。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
2. 运行本文 (准备情况评估) 。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。
