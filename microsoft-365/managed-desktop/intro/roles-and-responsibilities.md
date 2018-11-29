---
title: Microsoft 托管桌面的角色及职责
description: 本主题介绍的角色和职责由 Microsoft 提供的用于 Microsoft 托管桌面。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 923cde6353e4ff5122317f2c053fef244ee7e1b6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866040"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft 托管桌面的角色及职责


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

当 Microsoft 托管桌面注册您的组织时，有什么作用 Microsoft？ 您和贵组织的责任是什么？

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft 的角色和职责

以下是几个主要角色和将由 Microsoft 向您提供的责任。

角色或职责 | 说明
--- | ---
MDM 策略管理 | Microsoft 将应用 MDM 策略根据最佳做法，并考虑策略更改的请求。我们还将为您的租户[设备策略](../service-description/device-policies.md)中所述进行更改。
应用程序部署 | Microsoft 将部署到客户端的 Microsoft 托管桌面设备使用 Intune 的已批准应用程序。有关详细信息，请参阅[Apps](../get-ready/apps.md)。 
最终用户支持 | Microsoft 将提供最终用户支持的设备、 Windows 和 Office 产品套件的所有注册用户。 
Microsoft 托管桌面服务支持 | Microsoft 将向 customer IT 提供支持通过 Microsoft 托管桌面运营团队的部门。此团队将支持技术疑难解答，更改请求和事件管理客户的 Microsoft 托管桌面环境。有关详细信息，请参阅[获得支持](../service-description/support.md)。
安全监控 | Microsoft 将监控使用 Windows Defender ATP 客户 Microsoft 托管桌面设备。如果威胁检测到由 Microsoft 托管桌面安全操作中心 (SOC)，Microsoft 将通知客户，隔离该设备，并远程纠正此问题。有关详细信息，请参阅[Security](../service-description/security.md)。
监视和管理更新 | Microsoft 将主动监视客户 Microsoft 托管桌面设备，以确保最新的质量、 功能和定义更新安装 Microsoft Windows 和 Microsoft Office 的。有关详细信息，请参阅[如何处理更新](../service-description/updates.md)。
设备采购 | Microsoft 将货到最终用户或您选择的 IT 分发点的有序的 Microsoft 托管桌面设备。有关详细信息，请参阅[设备](../get-started/devices.md)。

## <a name="your-roles-and-responsibilities"></a>您的角色及职责

下面是一组额外的常见的未提供的 Microsoft，但成功部署所需的角色。它不是详尽，但对于大多数组织而言的典型。 

角色或 reponsibility | 说明
--- | ---
变更管理 | Microsoft 托管桌面将通知客户，提前时需要对其 Microsoft 托管桌面环境进行更改。客户需要有其自己的更改管理流程，而且都需要有与 Microsoft 托管桌面联系人。客户需要具有资源来查看和批准这些更改。有关详细信息，请参阅[操作和监控](../service-description/operations-and-monitoring.md)。  
标识管理 | 创建用户帐户，将用户分配到组和保持最新的元数据。 
Office 365 配置和管理 | Exchange Oonline 管理，包括：<br>电子邮件管理<br>邮箱和规则配置<br>Exchange 部署管理<br><br>协作工具、 SharePoint server 管理、 域管理、 安全和信息策略在 Office 365 管理门户 （Microsoft 托管桌面将确保 Office 应用程序部署到最终用户设备和保持最新） 中设置。 
最终用户支持 | 客户将提供对最终用户支持： <br>在网站基础结构： 所有网络和 internet 连接、 VPN 基础结构和客户端的配置、 本地会议室内设备、 打印机、 代理服务器和配置，防火墙。<br><br>-公司范围云资源： 电子邮件、 SharePoint、 协作服务和与公司范围内技术占用其他云基础结构。<br><br>---业务线应用程序： 自定义软件、 第三方软件、 企业资源规划 (ERP) 软件、 设计工具和未指定此文档中的任何内容。
用户和设备分组 | Microsoft 托管桌面运营团队将创建和管理所需的设备和用户组的 IT 操作的一部分。客户不将更改而不通过支持渠道的第一个联系 IT 操作这些分组。所有检测到更改将被还原。
应用 | 客户将提供他们想要使用组织 （超出附带 Microsoft 365 许可证的应用程序） 中的应用程序的列表。客户还提供了可部署包 （约或 MSI）<br>客户负责为：<br>应用程序许可证管理 – 具有正确的类型和数量的许可证<br>应用程序分配 – 分配到 Azure AD 用户组的应用程序<br>应用程序的更新 – 监控，打包和部署应用程序功能和安全更新<br>用户的应用程序测试 (UAT)<br><br>有关详细信息，请参阅[应用程序](../get-ready/apps.md)
安全监控和响应 | 如果在安全事件检测即 Microsoft 托管桌面操作的范围之外，我们将需要基于严重问题的首选的客户联系人的列表。<br><br>客户负责调查和解决非 Microsoft 托管桌面设备和确保 Microsoft 托管桌面运营团队通知的可能影响服务的任何问题的事件。
操作支持 | Microsoft 托管桌面操作需要首选的客户联系人和行业专家那里获得的列表。我们需要这些情况下没有非 Microsoft 托管桌面操作事件。 <br><br>客户负责调查和解决的非 Microsoft 托管桌面设备和服务以及确保 Microsoft 托管桌面运营团队始终会接到通知事件。
网络基础结构，包括 VPN | 安装、 配置和管理 （包括疑难解答和调试） 的所有网络相关的基础结构和服务，包括 internet 连接网络控件、 代理配置和远程连接基础结构。<br><br>默认情况下，Microsoft 托管桌面不指定或需要代理。但是，如果一个配置 （在硬件或软件），是必须由代理允许的 Url 的集合。客户负责解决任何冲突或由于多个代理服务器的不兼容。<br><br>有关详细信息，请参阅[代理配置](../get-ready/network.md)。
打印 | 安装、 维护和管理打印机和打印队列。云打印建议的解决方案，但不是必需的。 
移动设备 | 设备和不提供通过 Microsoft 托管桌面的附件。Microsoft 托管桌面运营团队仅支持 Microsoft 托管桌面设备、 扩展坞分开和包含的附件。




