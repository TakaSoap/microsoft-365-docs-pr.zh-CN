---
title: Microsoft 托管桌面角色和责任
description: 本文介绍 Microsoft 为用户提供的角色Microsoft 托管桌面。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 2a9a1d4314503b900d774851b2d23587d4c37579
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034445"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 托管桌面角色和责任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

当你的组织在组织中注册Microsoft 托管桌面，Microsoft 会为你们做什么？ 贵组织应承担哪些责任？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色和责任

Microsoft 提供以下关键角色和责任：

角色或责任 | 说明
--- | ---
MDM 策略管理 | Microsoft 将按照最佳做法应用 MDM 策略，并考虑策略更改请求。 我们还将按照设备策略中的规定更改 [租户](../service-description/device-policies.md)。
用户支持 | 我们提供了一种机制，用于提升对设备的访问权限，并在必要时通过支持请求上报问题。 有关详细信息，请参阅用户 [支持](../service-description/user-support.md)。
Microsoft 托管桌面服务支持 | Microsoft 会通过运营团队为 IT 部门Microsoft 托管桌面支持。 此团队将支持针对客户的生产环境进行技术疑难解答、更改请求和事件Microsoft 托管桌面管理。 有关详细信息，请参阅管理员[对 Microsoft 托管桌面。](../working-with-managed-desktop/admin-support.md)
安全监视 | Microsoft 将监视你的Microsoft 托管桌面使用 Microsoft Defender for Endpoint 的设备。 如果安全Microsoft 托管桌面中心 (SOC) 检测到威胁，我们将通知你、隔离设备并远程纠正问题。 有关详细信息，[请参阅安全。](../service-description/security.md)
更新监视和管理 | 我们主动监视 Microsoft 托管桌面 设备，以确保为 Microsoft Windows 和 Microsoft Office 安装最新的质量和功能更新。 有关详细信息，请参阅如何处理 [更新](../service-description/updates.md)。
用户和设备分组 | Microsoft 托管桌面运营团队将在 IT 操作中创建和管理所需的设备和用户组。 不允许更改这些组的成员或配置。 更改这些组可能会导致意外的设备配置和功能丢失。 对于建立后有关这些组的任何问题或问题，IT 管理员可以与Microsoft 托管桌面联系。 有关详细信息，请参阅管理员[对 Microsoft 托管桌面。](../working-with-managed-desktop/admin-support.md)

## <a name="your-roles-and-responsibilities"></a>你的角色和责任

部署需要这组常见角色和职责，但 Microsoft 不提供。 它并不详尽，但适用于大多数组织。 你和 Microsoft 共同负责一些项目。 

角色或责任 | 说明
--- | ---
变更管理 | 当需要更改客户的生产环境时，Microsoft 将提前Microsoft 托管桌面通知。 有关详细信息，请参阅服务 [更改和通信](../service-description/servicechanges.md)。<br><br>您必须具有自己的变更管理流程，并且必须与运营团队建立Microsoft 托管桌面联系。 您还必须具有审阅和批准这些更改的资源。 有关详细信息，请参阅操作 [和监视](../service-description/operations-and-monitoring.md)。  
身份管理 | 您负责创建用户帐户、将用户分配给组以及使元数据保持最新。 
Microsoft 365 企业应用版配置和管理 | Microsoft 负责确保Office应用程序部署到用户，并且这些应用程序保持最新。 <br><br> 您负责管理Microsoft 365策略，包括Exchange Online管理职责：<br>- 电子邮件管理<br>- 邮箱和规则配置<br>- Exchange本地管理<br><br>您还负责协作工具、SharePoint服务器管理、域管理以及安全以及信息策略，这些策略在 Microsoft 365 管理中心。 
用户支持 | 通过你或指定的支持合作伙伴为用户提供从第一个联系人到解决方案的所有用户支持和技术支持。 您必须直接提供用户支持，或与合作伙伴合作，为以下领域提供支持： <br><br>- 现场基础结构：所有网络和 Internet 连接、VPN 基础结构和客户端配置、本地会议室设备、打印机、代理服务器和配置以及防火墙。<br><br>- 公司范围内的云资源：电子邮件、SharePoint、协作服务和其他与公司范围内的技术占用相关的云基础结构。<br><br>- 业务线和任何其他特定于公司的应用程序。
Apps | 对于作为应用程序一部分提供的应用，角色Microsoft 托管桌面与你提供的应用稍有不同。 <br><br>对于由 Microsoft (Microsoft 365 企业应用版提供的应用，Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、Teams 和 OneNote **) ，Microsoft** 将为部署、更新和支持提供完整服务。 **必须** 获取和分配这些应用的许可证，将用户添加到安全组，并管理生命周期结束并部署所需的任何加载项。<br><br>对于你 (的应用（如业务线应用) ，无论你是自行打包应用还是联系非 Microsoft 供应商，你都应对以下操作负责：  <br><br>- 确定目标用户组所需的应用程序<br>- 创建和管理Azure AD部署的应用程序组<br>- 打包应用以满足Microsoft Intune标准<br>- 将应用上载到Microsoft Intune<br>- 在环境中测试Microsoft 托管桌面应用<br>- 与用户一起测试应用<br>- 管理用户并将其分配给应用程序<br>- 通过应用程序更新标识和部署Microsoft Intune<br>- 在应用程序停用后卸载和删除应用程序<br>- 获取和分配许可证<br>- 为业务线应用提供用户支持<br>- 远程管理应用设置<br><br>**Microsoft** 将提供Microsoft Intune部署工具，以将应用程序交付到远程客户端。<br><br>有关详细信息，[请参阅应用。](../get-ready/apps.md)
安全监视和响应 | 你负责调查和解决不是Microsoft 托管桌面设备的事件，并确保 Microsoft 托管桌面 运营团队了解可能会影响服务的任何问题。
操作支持 | 必须提供组织中首选联系人和主题专家的列表。 如果存在与事件无关的操作事件，我们需要这些Microsoft 托管桌面。 <br><br>你还负责调查和解决不在 Microsoft 托管桌面 中的设备和服务的事件，并确保 Microsoft 托管桌面 Operations Team 始终获得通知。
网络基础结构，包括 VPN | 你负责设置、配置和管理 (包括排除和调试所有与网络相关的基础结构) 服务（包括 Internet 连接、网络控制、代理配置和远程连接基础结构）的) 。<br><br>如果在硬件或软件 (配置代理) ，则代理必须允许一组 URL。 你负责解决由于多个代理导致的任何冲突或不兼容性。 可以使用可配置设置添加特定于您的组织的网络代理。 有关详细信息，请参阅可 [配置设置](../working-with-managed-desktop/config-setting-ref.md#proxy)。<br><br>有关详细信息，请参阅代理 [配置](../get-ready/network.md)。
打印 | 您负责安装、维护和管理打印机和打印队列。 云打印是推荐的解决方案，但不是必需的。 




