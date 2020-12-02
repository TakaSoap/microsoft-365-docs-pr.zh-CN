---
title: 准备情况评估工具
description: 说明工具运行的检查和结果的含义
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 491422126f7d159689e7995b69bef0f395491dcb
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527705"
---
# <a name="readiness-assessment-tool"></a>准备情况评估工具

若要在注册 Microsoft 托管桌面时获得最平滑的可能体验，请务必提前设置一些设置和其他参数。 您可以使用此工具检查这些设置，并获得修复不正确的详细步骤。

该工具检查 Microsoft 终结点管理器中的设置 (具体来说，Microsoft Intune) 、Azure Active Directory (Azure AD) 和 Microsoft 365，以确保它们可与 Microsoft 托管桌面配合使用。 Microsoft 托管桌面在上次运行 Azure AD 组织 (租户) 中的检查后，会保留与这些检查相关的数据。 12个月后，我们会将其保留在取消识别的表单中。  您可以选择删除我们收集的数据。

至少具有 Intune 管理员角色的任何人都可以运行此工具，但两个检查 ([条件访问策略](readiness-assessment-fix.md#conditional-access-policies) 和多 [因素身份验证](readiness-assessment-fix.md#multifactor-authentication) 都需要其他权限。
 
评估工具将检查以下项：

## <a name="microsoft-intune-settings"></a>Microsoft Intune 设置

|支票  |说明  |
|---------|---------|
|Autopilot 部署配置文件     | 验证 Autopilot 部署配置文件的分配是否不适用于所有设备 (*不应将* 配置文件分配给任何 Microsoft 托管桌面设备。 )        |
|证书连接器     | 检查证书连接器的状态以确保它们处于活动状态   |
|条件访问     | 验证是否未将条件访问策略分配给所有用户 (*不* 应将条件访问策略分配给 Microsoft 托管桌面服务帐户。 )     |
|设备合规性策略     | 检查是否未向所有用户分配 Intune 合规性策略 (*不* 应将策略分配给任何 Microsoft 托管桌面设备。 )     |
|设备配置文件     | 确认未将配置文件分配给所有用户或所有设备 (*不* 应将配置文件分配给任何 Microsoft 托管桌面设备。 )      |
|设备类型限制     | 检查是否允许组织中的 Windows 10 设备注册 Intune        |
|"注册状态" 页     | 确认未启用 "注册状态" 页      |
|Intune 注册     | 验证 Azure AD 组织中的 Windows 10 设备是否已在 Intune 中自动注册         |
|适用于企业的 Microsoft Store     | 确认 Microsoft Store for Business 已启用，并已与 Intune 同步        |
|多重身份验证 | 验证是否对 Microsoft 托管桌面服务帐户应用了多重身份验证。
|PowerShell 脚本     | 检查是否以 Microsoft 托管桌面设备的目标 *方式分配 Windows* PowerShell 脚本    |
|区域     | 检查 Microsoft 托管桌面是否支持你的区域        |
|安全基准     | 检查安全基准配置文件是否不面向所有用户或所有设备 (安全基准策略 *不* 应以任何 Microsoft 托管桌面设备为目标。 )        |
|Windows 应用     | 查看要分配给 Microsoft 托管桌面设备的应用程序      |
|Windows Hello 企业版     | 检查是否已启用 Windows Hello 企业版        |
|Windows 10 更新环     | 检查 Intune 的 "Windows 10 更新环" 策略是否不针对所有用户或所有设备 (该策略 *不* 应将任何 Microsoft 托管桌面设备作为目标。 )      |


## <a name="azure-active-directory-settings"></a>Azure Active Directory 设置

|支票  |说明  |
|---------|---------|
|企业状态漫游的 "临时" 订阅     | 建议如何检查 (如果设置为 "false" 的设置 ) 可能会阻止企业状态漫游正常工作  |
|企业状态漫游     | 建议如何检查是否已启用企业状态漫游       |
|许可证     | 检查是否已获取必需的 [许可证](prerequisites.md#more-about-licenses)         |
|多重身份验证     | 检查是否对所有用户应用了多重身份验证 (多重身份验证不能意外应用于 Microsoft 托管桌面服务帐户。 ) |
|安全帐户名称   | 检查没有与 Microsoft 托管桌面保留的用户名称相冲突的用户名是否可供自己使用        |
|安全管理员角色     | 确认已在 Microsoft Defender for Endpoint 中为具有安全读取器、安全操作员或全局读取器角色的用户分配了这些角色         |
|安全性默认值 | 检查 Azure AD 组织是否在 Azure Active Directory 中启用了安全默认设置 |
|自助服务密码重置     | 确认已启用自助密码重置        |
|标准用户角色     | 验证用户是否为标准用户且没有本地管理员权限         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>适用于企业版的 Microsoft 365 应用程序设置

|支票  |说明  |
|---------|---------|
|OneDrive for Business     | 检查 OneDrive for Business 是否使用了不受支持的设置。        |


对于每个检查，该工具将报告以下四个可能的结果之一：


|结果  |含义  |
|---------|---------|
|Ready     | 完成注册之前，不需要执行任何操作。        |
|欲    | 按照工具中的步骤执行注册和用户的最佳体验。 你 *可以* 完成注册，但必须先解决这些问题，然后再部署你的第一个设备。        |
|未就绪 | 如果不解决这些问题，*注册将失败*。 按照工具中的步骤解决这些问题。        |
|Error | 您正在使用的 Azure Active Director (AD) 角色没有足够的权限来运行此检查。 |

## <a name="after-enrollment"></a>注册后

在 Microsoft 托管桌面中完成注册后，请记住返回并调整特定 Intune 和 Azure AD 设置。 有关详细信息，请参阅 [在注册后调整设置](../get-started/conditional-access.md)。
