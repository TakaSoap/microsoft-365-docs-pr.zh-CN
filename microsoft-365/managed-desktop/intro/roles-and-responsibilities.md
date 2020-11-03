---
title: Microsoft 托管桌面角色和责任
description: 本文介绍 Microsoft 托管桌面所提供的角色和职责。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: de0bc092c35c7f48c562da8d4218f7a638abe1d5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847776"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 托管桌面角色和责任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

在 Microsoft 托管桌面中注册组织后，Microsoft 会为你做些什么？ 您的组织的责任是什么？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色和职责

Microsoft 提供以下关键角色和职责：

角色或责任 | 说明
--- | ---
MDM 策略管理 | Microsoft 将根据最佳实践应用 MDM 策略，并考虑策略更改请求。 我们还将根据 [设备策略](../service-description/device-policies.md)中的规定对你的租户进行更改。
用户支持 | 通过预安装在所有 Microsoft 托管桌面设备上的 Get 帮助应用，我们为所有注册用户提供针对设备、Windows 和 Microsoft 365 应用程序的用户支持。 
Microsoft 托管桌面服务支持 | Microsoft 将通过 Microsoft 托管桌面操作团队为你的 IT 部门提供支持。 此团队将支持客户的 Microsoft 托管桌面环境的技术故障排除、更改请求和事件管理。 有关详细信息，请参阅 [Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。
安全监视 | Microsoft 将使用 Microsoft Defender for Endpoint 监视 Microsoft 托管桌面设备。 如果 Microsoft 托管桌面安全操作中心 (SOC) 检测到威胁，我们会通知你，隔离设备，并远程修正问题。 有关详细信息，请参阅 [安全性](../service-description/security.md)。
更新监控和管理 | 我们积极监视你的 Microsoft 托管桌面设备，以确保为 Microsoft Windows 和 Microsoft Office 安装了最新的质量和功能更新。 有关详细信息，请参阅 [如何处理更新](../service-description/updates.md)。
用户和设备分组 | Microsoft 托管桌面操作团队将创建和管理所需的设备和用户组作为 IT 操作的一部分。 不允许对这些组进行成员资格或配置更改。 更改这些组可能会导致设备的意外配置和功能丢失。 有关这些组的任何问题或问题，请在建立后，IT 管理员可以联系 Microsoft 托管桌面操作。 有关详细信息，请参阅 [Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。

## <a name="your-roles-and-responsibilities"></a>您的角色和职责

部署需要这一组额外的共同角色和责任，但 Microsoft 不提供。 它并不详尽，但适用于大多数组织。 您和 Microsoft 共同负责的一些项目。 

角色或责任 | 说明
--- | ---
变更管理 | 当需要对 Microsoft 托管桌面环境进行更改时，Microsoft 将提前通知客户。 有关详细信息，请参阅 [服务更改和通信](../service-description/servicechanges.md)。<br><br>您必须拥有自己的更改管理过程，并具有与 Microsoft 托管桌面操作团队建立的联系人。 此外，您还必须具有审阅和批准这些更改的资源。 有关详细信息，请参阅 [操作和监视](../service-description/operations-and-monitoring.md)。  
身份管理 | 您负责创建用户帐户，将用户分配到组，并将元数据保持为最新。 
适用于企业配置和管理的 Microsoft 365 应用程序 | Microsoft 负责确保将 Office 应用程序部署到用户，这些应用程序将保持最新。 <br><br> 您负责管理 Microsoft 365 服务和策略，包括 Exchange Online 管理责任：<br>-电子邮件管理<br>-邮箱和规则配置<br>-Exchange 本地管理<br><br>您还应负责在 Microsoft 365 管理中心设置的协作工具、SharePoint server 管理、域管理和安全和信息策略。 
用户支持 | 您必须为以下用户提供用户支持： <br>-现场基础结构：所有网络和 internet 连接、VPN 基础结构和客户端配置、本地会议室设备、打印机、代理服务器和配置以及防火墙。<br><br>-公司范围内的云资源：电子邮件、SharePoint、协作服务和其他与公司范围的技术覆盖相关的云基础结构。<br><br>-业务线和任何其他特定于公司的应用程序。
应用 | 角色和责任因作为 Microsoft 托管桌面的一部分而提供，与你提供的应用程序的应用稍有不同。 <br><br>对于 Microsoft (提供的适用于企业的 Microsoft 365 应用程序（包含 Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、团队和 OneNote) ）， **microsoft** 将为部署、更新和支持人员提供完整服务。 **您** 必须获取并分配这些应用程序的许可证，将用户添加到安全组，并管理使用寿命的结束时间并部署所需的任何加载项。<br><br>对于您提供 (如业务线应用程序) 的应用程序，无论您是自己打包还是接洽非 Microsoft 供应商来执行此操作， **您** 都需要负责以下操作： <br><br>-识别目标用户组所需的应用程序<br>-创建和管理用于应用程序部署的 Azure AD 组<br>-打包应用程序以满足 Microsoft Intune 部署标准<br>-将应用程序上载到 Microsoft Intune<br>-在 Microsoft 托管桌面环境中测试应用程序<br>-使用您的用户测试应用程序<br>-管理用户并将其分配给应用程序<br>-通过 Microsoft Intune 识别和部署应用程序更新<br>-卸载并删除已停用的应用程序<br>-采购和分配许可证<br>-为业务线应用程序提供用户支持<br>-远程管理应用程序设置<br><br>**Microsoft** 将提供 microsoft Intune 部署工具以将应用程序传递到远程客户端。<br><br>有关详细信息，请参阅 [应用](../get-ready/apps.md)。
安全监视和响应 | 你负责调查和解决不是 Microsoft 托管桌面设备的设备的事件，并确保 Microsoft 托管桌面操作团队收到可能影响服务的任何问题。
操作支持 | 您必须提供组织中首选联系人和主题专家的列表。 如果与 Microsoft 托管桌面无关的操作事件，我们需要这样做。 <br><br>您还负责调查和解决不在 Microsoft 托管桌面中的设备和服务的事件，并确保始终通知 Microsoft 托管桌面操作团队。
包括 VPN 在内的网络基础结构 | 您负责安装、配置和管理 (，包括对所有与网络相关的基础结构和服务的故障排除和调试) ，包括 internet 连接、网络控制、代理配置和远程连接基础结构。<br><br>如果代理配置 (在硬件或软件) 中，则必须有代理允许的 Url 的集合。 您负责解决因多个代理而导致的任何冲突或不兼容问题。 您可以使用可配置的设置添加特定于您的组织的网络代理。 有关详细信息，请参阅 [可配置设置](../working-with-managed-desktop/config-setting-ref.md#proxy)。<br><br>有关详细信息，请参阅 [Proxy Configuration](../get-ready/network.md)。
打印 | 您负责安装、维护和管理打印机和打印队列。 云打印是推荐的解决方案，但不是必需的。 




