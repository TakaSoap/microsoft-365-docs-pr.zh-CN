---
title: 设备配置
description: 了解应用于 Microsoft 托管桌面设备的默认策略。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920488"
---
# <a name="device-configuration"></a>设备配置


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

在设置新的 Microsoft 托管桌面设备时，我们确保该设备具有针对 Microsoft 托管桌面进行优化的合适配置。 该配置包括一组在载入过程中设置的默认策略。 只要可能，这些策略 (MDM) 移动设备管理。 有关详细信息，请参阅 [移动设备管理](/windows/client-management/mdm/)。 

>[!NOTE]
>为避免冲突，请勿更改这些策略。

设备将到达签名映像，然后在第一个用户登录时加入 Azure Active Directory 域。 设备将自动安装所需的策略和应用程序，无需 IT 人员的任何干预。

## <a name="default-policies"></a>默认策略

此表突出显示了在设备预配期间应用于所有 Microsoft 托管桌面设备的默认策略。 Microsoft 托管桌面操作团队未批准对由 Microsoft 托管桌面管理的对象进行的所有检测到的更改都将还原。

Policy | 说明
--- | ---
安全基线 | [MDM 的 Microsoft](/windows/device-security/windows-security-baselines) 安全基线已针对所有 Microsoft 托管桌面设备进行配置。 此基线是行业标准配置。 它公开发布，经过良好测试，并经过 Microsoft 安全专家审查，以确保 Microsoft 托管的桌面设备和应用在新式工作场所中的安全性。 <br><br>为了在不断演变的安全威胁形势中缓解威胁，Microsoft 安全基线将进行更新，并随每个 Windows 10 功能更新部署到 Microsoft 托管桌面设备。<br><br>有关详细信息，请参阅 [Windows 安全基线](/windows/security/threat-protection/windows-security-baselines)。
Microsoft 托管桌面建议的安全模板 | 对安全基线的一组建议更改，可优化用户体验。  这些更改记录在安全附录 [中](#security-addendum)。 根据需要更新策略附录。  
更新部署 | 使用适用于 Business 的 Windows 更新执行软件更新的逐步部署。 IT 管理员无法修改部署组策略的设置。 有关基于组部署的信息，请参阅如何在 Microsoft 托管 [桌面中处理更新](updates.md)。
按流量计费的连接 | 默认情况下，通过按流量计费的连接（如 LTE) ）上的更新 (关闭，尽管每个用户都可以在"设置"">更新"> **高级选项中** 单独启用此功能。 如果要允许所有用户通过按流量计费的连接启用更新，请提交更改请求[](../working-with-managed-desktop/admin-support.md)，这将针对所有设备启用此设置。
| 设备合规性 | 这些策略针对所有 Microsoft 托管桌面设备进行配置。 当设备偏离所需安全配置时，该设备被报告为不兼容。

## <a name="windows-diagnostic-data"></a>Windows 诊断数据

 设备将设置为根据已知的商业标识符向 Microsoft 提供增强的诊断数据。 作为 Microsoft 托管桌面的一部分，IT 管理员无法更改这些设置。 对于 GDPR 区域一般数据保护 () ，用户可以降低提供的诊断数据级别，但服务将会减少。 例如，Microsoft 托管桌面将无法收集在设置和策略上进行访问以最好地满足性能和安全需求所需的数据。 有关详细信息，请参阅 [在组织中配置 Windows 诊断数据。](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>安全附录

 本节概述了除了默认策略中列出的标准 Microsoft 托管桌面策略之外，还将部署 [的策略](#default-policies)。 此配置在设计时考虑金融服务和高度管控行业，在保持用户工作效率的同时优化最高安全性。

 ### <a name="additional-security-policies"></a>其他安全策略

 添加了这些策略以提高高度管控行业的安全性。 
 - **安全监视**：Microsoft 将监视使用 [Microsoft Defender for Endpoint 的设备](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。 如果检测到威胁，Microsoft 将通知客户、隔离设备并远程纠正问题。 
 - **禁用 PowerShell V2：Microsoft** 在 2017 年 8 月删除了 PowerShell V2。 在所有 Microsoft 托管桌面设备上已禁用此功能。 有关此更改详细信息，请参阅 Windows PowerShell [2.0 弃用](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。