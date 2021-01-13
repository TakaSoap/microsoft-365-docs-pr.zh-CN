---
title: Microsoft 托管桌面角色和责任
description: 本文介绍 Microsoft 为 Microsoft 托管桌面提供的角色和职责。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841311"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 托管桌面角色和责任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

当你的组织在 Microsoft 托管桌面中注册时，Microsoft 会为你们做什么？ 组织应承担什么责任？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色和责任

Microsoft 提供以下关键角色和责任：

角色或责任 | 说明
--- | ---
MDM 策略管理 | Microsoft 将按照最佳做法应用 MDM 策略，并考虑策略更改请求。 我们还将按照设备策略中的规定对租户 [进行更改](../service-description/device-policies.md)。
用户支持 | 我们通过预安装在所有 Microsoft 托管桌面设备上提供的"获取帮助"应用，为所有注册用户提供设备、Windows 和 Microsoft 365 企业应用版产品套件的用户支持。 
Microsoft 托管桌面服务支持 | Microsoft 将通过 Microsoft 托管桌面运营团队为 IT 部门提供支持。 此团队将支持客户的 Microsoft 托管桌面环境的技术疑难解答、更改请求和事件管理。 有关详细信息，请参阅 [Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。
安全监视 | Microsoft 将监视使用 Microsoft Defender for Endpoint 的 Microsoft 托管桌面设备。 如果 Microsoft 托管桌面安全操作 (SOC) 检测到威胁，我们将通知你、隔离设备并远程纠正问题。 有关详细信息，请参阅"[安全"。](../service-description/security.md)
更新监视和管理 | 我们主动监视你的 Microsoft 托管桌面设备，以确保为 Microsoft Windows 和 microsoft Windows Microsoft Office。 有关详细信息，请参阅 [如何处理更新](../service-description/updates.md)。
用户和设备分组 | Microsoft 托管桌面运营团队将在 IT 操作中创建和管理所需的设备和用户组。 不允许这些组的任何成员身份或配置更改。 更改这些组可能会导致意外的设备配置和功能丢失。 对于建立后与这些组有关的任何问题，IT 管理员可以联系 Microsoft 托管桌面操作。 有关详细信息，请参阅 [Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。

## <a name="your-roles-and-responsibilities"></a>你的角色和责任

部署需要这组常见角色和职责，但 Microsoft 不提供。 它并不详尽，但适用于大多数组织。 有一些项你和 Microsoft 共同负责。 

角色或责任 | 说明
--- | ---
变更管理 | 当需要更改其 Microsoft 托管桌面环境时，Microsoft 将提前通知客户。 有关详细信息，请参阅服务 [更改和通信](../service-description/servicechanges.md)。<br><br>你必须拥有自己的变更管理流程，并且与 Microsoft 托管桌面运营团队建立了联系。 您还必须具有审阅和批准这些更改的资源。 有关详细信息，请参阅操作 [和监视](../service-description/operations-and-monitoring.md)。  
身份管理 | 您负责创建用户帐户、将用户分配给组以及使元数据保持最新。 
Microsoft 365 企业应用版配置和管理 | Microsoft 负责确保向用户部署 Office 应用程序，并且这些应用程序保持最新。 <br><br> 你负责管理 Microsoft 365 服务和策略，包括 Exchange Online 管理职责：<br>- 电子邮件管理<br>- 邮箱和规则配置<br>- Exchange 本地管理<br><br>您还需要负责在 Microsoft 365 管理中心中设置的协作工具、SharePoint 服务器管理、域管理以及安全和信息策略。 
用户支持 | 您必须为： <br>- 现场基础结构：所有网络和 Internet 连接、VPN 基础结构和客户端配置、本地会议室设备、打印机、代理服务器和配置以及防火墙。<br><br>- 公司范围的云资源：电子邮件、SharePoint、协作服务以及与公司范围内的技术占用相关的其他云基础结构。<br><br>- 业务线和任何其他公司特定应用程序。
应用 | 对于作为 Microsoft 托管桌面的一部分提供的应用与所提供的应用，角色和职责会稍有不同。 <br><br>对于由 Microsoft (Microsoft 365 企业应用版（包含 Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、Teams 和 OneNote) ）提供的应用 **，Microsoft** 将提供用于部署、更新和支持的完整服务。 **必须** 获取和分配这些应用的许可证，将用户添加到安全组，管理生命周期结束并部署所需的任何加载项。<br><br>对于你 (的应用（如业务线应用) ，无论你是自行打包应用还是联系非 Microsoft 供应商进行打包，你都应对以下操作负责：  <br><br>- 标识目标用户组所需的应用程序<br>- 为应用部署创建和管理 Azure AD 组<br>- 打包应用以满足 Microsoft Intune 部署标准<br>- 将应用上传到 Microsoft Intune<br>- 在 Microsoft 托管桌面环境中测试应用<br>- 与用户一起测试应用<br>- 管理用户并将其分配给应用程序<br>- 通过 Microsoft Intune 识别和部署应用程序更新<br>- 在应用程序停用后卸载和删除应用程序<br>- 采购和分配许可证<br>- 为业务线应用提供用户支持<br>- 远程管理应用设置<br><br>**Microsoft** 将提供 Microsoft Intune 部署工具，将应用程序交付到远程客户端。<br><br>有关详细信息，请参阅["应用"。](../get-ready/apps.md)
安全监视和响应 | 你负责调查和解决不是 Microsoft 托管桌面设备的设备事件，并确保 Microsoft 托管桌面运营团队了解可能会影响服务的任何问题。
操作支持 | 必须提供组织中首选联系人和主题专家的列表。 如果存在与 Microsoft 托管桌面无关的操作事件，我们需要这些联系人。 <br><br>你还负责调查和解决不在 Microsoft 托管桌面中的设备和服务的事件，并确保始终通知 Microsoft 托管桌面运营团队。
网络基础结构，包括 VPN | 你负责设置、配置和管理 (包括解决和调试所有与网络相关的基础结构) 服务（包括 Internet 连接、网络控制、代理配置和远程连接基础结构）的) 。<br><br>如果在硬件或软件 (配置代理) ，则代理必须允许一组 URL。 你负责解决由于多个代理导致的任何冲突或不兼容问题。 可以使用可配置设置添加特定于您的组织的网络代理。 有关详细信息，请参阅"[可配置设置"。](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>有关详细信息，请参阅代理 [配置](../get-ready/network.md)。
打印 | 您负责安装、维护和管理打印机和打印队列。 云打印是建议的解决方案，但不是必需的。 




