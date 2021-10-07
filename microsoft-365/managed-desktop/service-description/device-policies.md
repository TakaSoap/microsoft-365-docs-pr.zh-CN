---
title: 设备配置
description: 了解应用于设备Microsoft 托管桌面策略。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ec545a54988c2634c651ec07084c005467afd565
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210145"
---
# <a name="device-configuration"></a>设备配置


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

在设置Microsoft 托管桌面设备时，我们确保设备配置正确，Microsoft 托管桌面。 该配置包括一组在载入过程中设置的默认策略。 只要有可能，这些策略 (MDM) 移动设备管理。 有关详细信息，请参阅 [移动设备管理](/windows/client-management/mdm/)。 

>[!NOTE]
>为避免冲突，请勿更改这些策略。

设备将到达签名图像，然后在第一Azure Active Directory登录时加入域。 设备将自动安装所需的策略和应用程序，无需 IT 人员的任何干预。

## <a name="default-policies"></a>默认策略

此表突出显示了在设备预配期间应用于Microsoft 托管桌面设备的默认策略。 Operations Team 未批准Microsoft 托管桌面对由 Microsoft 托管桌面 管理的对象的所有更改都将还原。

Policy | 说明
--- | ---
安全基线 | [MDM 的 Microsoft](/windows/device-security/windows-security-baselines)安全基线针对所有设备Microsoft 托管桌面配置。 此基线是行业标准配置。 它公开发布，经过良好测试，并经过 Microsoft 安全专家审查，Microsoft 托管桌面现代工作场所中的设备和应用安全。 <br><br>为了在不断演变的安全威胁形势中缓解威胁，Microsoft 安全基线将进行更新，并部署到Microsoft 托管桌面设备，并Windows 10更新。<br><br>有关详细信息，请参阅Windows[基线](/windows/security/threat-protection/windows-security-baselines)。
Microsoft 托管桌面建议的安全模板 | 对安全基线的一组建议更改，可优化用户体验。  这些更改记录在安全附录 [中](#security-addendum)。 根据需要更新策略附录。  
更新部署 | 使用 Windows Update for Business 执行软件更新的逐步部署。 IT 管理员无法修改部署组策略的设置。 有关基于组部署的信息，请参阅如何在 Microsoft 托管桌面[中处理更新](updates.md)。
按流量计费的连接 | 默认情况下，按流量计费的连接（如 LTE (）上的更新) 关闭，尽管每个用户都可以在"设置 > 更新">高级选项中独立启用 **此功能**。 如果要允许所有用户通过按流量计费的连接启用更新，请提交更改请求[](../working-with-managed-desktop/admin-support.md)，这将针对所有设备启用此设置。
| 设备合规性 | 这些策略针对所有设备Microsoft 托管桌面配置。 当设备偏离所需安全配置时，该设备被报告为不兼容。

## <a name="windows-diagnostic-data"></a>Windows 诊断数据

 设备将设置为根据已知的商业标识符向 Microsoft 提供增强的诊断数据。 作为管理Microsoft 托管桌面，IT 管理员无法更改这些设置。 对于 GDPR (一般数据保护条例) ，用户可以降低提供的诊断数据级别，但服务将会减少。 例如，Microsoft 托管桌面无法收集在设置和策略上进行访问以最好地满足性能和安全需求所需的数据。 有关详细信息，请参阅在[Windows配置诊断数据。](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>安全附录

 本节概述了除了默认策略 中列出的标准策略之外Microsoft 托管桌面部署[的策略](#default-policies)。 此配置在设计时考虑金融服务和高度管控行业，在保持用户工作效率的同时优化最高安全性。

 ### <a name="additional-security-policies"></a>其他安全策略

 添加了这些策略以提高高度管控行业的安全性。 
 - **安全监视**：Microsoft 将监视使用 [Microsoft Defender for Endpoint 的设备](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。 如果检测到威胁，Microsoft 将通知客户、隔离设备并远程纠正问题。 
 - **禁用 PowerShell V2：Microsoft** 在 2017 年 8 月删除了 PowerShell V2。 此功能已在所有设备上Microsoft 托管桌面禁用。 有关此更改详细信息，请参阅 Windows PowerShell [2.0 弃用](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。