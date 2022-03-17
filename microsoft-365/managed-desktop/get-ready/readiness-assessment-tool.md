---
title: 准备情况评估工具
description: 说明这两种工具、它们运行的检查以及结果的含义
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 8d949b13203aaeab51d2518f16650ba6df832195
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525634"
---
# <a name="readiness-assessment-tools"></a>准备情况评估工具

为了在注册时获得尽可能流畅Microsoft 托管桌面，必须提前设置设置和其他参数，以及满足某些设备和网络要求。

通过管理门户访问的Microsoft 托管桌面一个工具，用于检查与管理相关的设置。 另一个可下载的工具可检查各个设备要求和网络设置。 可以使用这些工具检查这些设置，并接收修复任何错误的详细步骤。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>设备和网络的可下载准备情况评估检查程序

有关使用可下载的准备情况评估检查程序的详细信息，请参阅 [可下载的准备情况评估检查程序](readiness-assessment-downloadable.md)。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>用于管理设置的联机准备情况评估工具

联机[工具](https://aka.ms/mmdart)会检查 Microsoft Endpoint Manager (中的设置，Microsoft Intune) 、Azure Active Directory (Azure AD) 和 Microsoft 365，以确保这些设置能够使用Microsoft 托管桌面。

Microsoft 托管桌面上次在 Azure AD 组织或租户管理租户中运行检查后， (与这些检查) 。 12 个月后，我们会以已取消标识的形式保留它。 你可以选择删除我们收集的数据。

至少具有全局读取者或 Intune 管理员角色的任何人都可以运行此工具，但条件访问策略和多重 (身份验证策略中的两项检查) [](readiness-assessment-fix.md#conditional-access-policies)额外的权限。[](readiness-assessment-fix.md#multi-factor-authentication)

> [!IMPORTANT]  
> 联机准备情况评估工具可帮助你检查首次Microsoft 托管桌面注册的准备情况。 如果你的组织已注册Microsoft 托管桌面，请勿使用此工具。

评估工具检查以下项：

## <a name="microsoft-intune-settings"></a>Microsoft Intune设置

以下是以下Microsoft Intune设置：

| 支票 | 说明 |
| ------ | ------ |
| Autopilot 部署配置文件 | 验证 Autopilot 部署配置文件的分配是否适用于所有设备。 <br><br> 不应将 **配置文件** 分配给任何Microsoft 托管桌面设备。 |
| 证书连接器 | 检查证书连接器的状态以确保它们处于活动状态。 |
| 条件访问 | 验证条件访问策略是否未分配给所有用户。 <br><br> 不应将 **条件访问** 策略分配给Microsoft 托管桌面帐户。 |
| 设备合规性策略 | 检查未将 Intune 合规性策略分配给所有用户。 <br><br> 不应将 **策略** 分配给任何Microsoft 托管桌面设备。 |
| 设备配置文件 | 确认配置文件未分配给所有用户或所有设备。 <br><br> 不应将 **配置文件** 分配给任何Microsoft 托管桌面配置文件。 |
| 设备类型限制 | 检查Windows 10设备是否允许在 Intune 中注册。 |
| 注册状态页 | 确认未启用注册状态页。 |
| Intune 注册 | 验证Windows 10组织中Azure AD设备是否自动在 Intune 中注册。 |
| 适用于企业的 Microsoft Store | 确认已适用于企业的 Microsoft Store和 Intune 同步。 |
| 多重身份验证 | 验证多重身份验证是否不适用于Microsoft 托管桌面帐户。 |
| PowerShell 脚本 | 检查Windows PowerShell **脚本的分配** 方式是否面向 Microsoft 托管桌面 设备。 |
| 地区 | 检查你的区域是否受 Microsoft 托管桌面。 |
| 安全基线 | 检查安全基线配置文件是否未面向所有用户或所有设备。 <br><br> 安全基线策略 **不应面向** 任何Microsoft 托管桌面设备。 |
| Windows应用 | 查看你想要分配给设备Microsoft 托管桌面应用。 |
| Windows Hello 企业版 | 检查Windows Hello Business 是否已启用。 |
| Windows 10更新圈 | 检查 Intune 的"Windows 10更新圈"策略是否未面向所有用户或所有设备。 <br><br> 策略不应 **面向** 任何Microsoft 托管桌面设备。 |

## <a name="azure-active-directory-settings"></a>Azure Active Directory设置

以下是以下Azure Active Directory设置：

| 支票 | 说明 |
| ----- | ----- |
| 适用于状态漫游的Enterprise临时"订阅 | 建议如何检查设置，如果设置为"false"，可能会Enterprise状态漫游正常工作。 |
| 企业状态漫游 | 建议如何检查是否Enterprise状态漫游是否已启用。 |
| 许可证 | 检查你已获取必要的 [许可证](prerequisites.md#more-about-licenses)。 |
| 多重身份验证 | 检查多重身份验证是否未应用于所有用户。 <br><br> 多重身份验证不得 **意外** 应用于Microsoft 托管桌面帐户。 |
| 安全帐户名称 | 检查用户名称是否与保留供Microsoft 托管桌面的用户名冲突。 |
| 安全管理员角色 | 确认在 Microsoft Defender for Endpoint 中为具有安全读者、安全操作员或全局读者角色的用户分配了这些角色。 |
| 安全性默认值 | 检查组织Azure AD中是否启用了安全Azure Active Directory。 |
| 自助式密码重置 | 确认已启用自助服务密码重置。 |
| 标准用户角色 | 验证用户是标准用户，并且没有本地管理员权限。 |

## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 应用版设置Enterprise

以下是用于Microsoft 365 应用版设置Enterprise设置：

| 支票 | 说明 |
| ----- | ----- |
| OneDrive for Business | 检查OneDrive for Business是否使用不受支持的设置。 |

对于每个检查，该工具将报告四个可能的结果之一：

| 结果 | 含义 |
| ----- | ----- |
| Ready | 完成注册前无需任何操作。 |
| 公告 | 按照工具中的步骤操作，实现注册和用户的最佳体验。 <br><br> *你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。 |
| 未就绪 | **如果不修复** 这些问题，注册将失败。 <br><br> 按照工具中的步骤进行解析。 |
| 错误 | 你 (Azure Active Director) AD 角色没有足够的权限运行此检查。 |

## <a name="after-enrollment"></a>注册后

完成注册后，请Microsoft 托管桌面并调整某些 Intune 和 Azure AD 设置。 有关详细信息，请参阅注册 [后调整设置](../get-started/conditional-access.md)。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
2. 运行本文 (准备情况评估) 。
3. 购买 [公司门户](../get-started/company-portal.md)。
4. 查看 [来宾帐户的先决条件](guest-accounts.md)。
5. 检查 [网络配置](network.md)。
6. [准备证书和网络配置文件](certs-wifi-lan.md)。
7. [准备用户对数据的访问权限](authentication.md)。
8. [准备应用](apps.md)。
9. [准备映射的驱动器](mapped-drives.md)。
10. [准备打印资源](printing.md)。
11. 地址 [设备名称](address-device-names.md)。
