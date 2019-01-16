---
title: Microsoft 托管桌面的角色及职责
description: 本主题介绍的角色和职责由 Microsoft 提供的用于 Microsoft 托管桌面。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 96131f7577e0e655067c70bffdd75163ba790adf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
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
最终用户支持 | Microsoft 将提供最终用户支持的设备、 Windows 和 Office 的所有注册用户通过获取帮助应用程序的所有 Microsoft 托管桌面设备上预安装的产品套件。 
Microsoft 托管桌面服务支持 | Microsoft 将向 customer IT 提供支持通过 Microsoft 托管桌面运营团队的部门。此团队将支持技术疑难解答，更改请求和事件管理客户的 Microsoft 托管桌面环境。有关详细信息，请参阅[管理支持的 Microsoft 托管桌面](../working-with-managed-desktop/admin-support.md)。
安全监控 | Microsoft 将监控使用 Windows Defender ATP 客户 Microsoft 托管桌面设备。如果威胁检测到由 Microsoft 托管桌面安全操作中心 (SOC)，Microsoft 将通知客户，隔离该设备，并远程纠正此问题。有关详细信息，请参阅[Security](../service-description/security.md)。
监视和管理更新 | Microsoft 将主动监视客户 Microsoft 托管桌面设备，以确保 Microsoft Windows 和 Microsoft Office 的安装了最新更新质量和功能。有关详细信息，请参阅[如何处理更新](../service-description/updates.md)。
用户和设备分组 | Microsoft 托管桌面运营团队将创建和管理所需的设备和用户组的 IT 操作的一部分。不应从 Microsoft 托管桌面运营团队对不审批的情况下这些组所做更改。

## <a name="your-roles-and-responsibilities"></a>您的角色及职责

下面是常见的角色和职责未提供的 Microsoft，但成功部署所需的其他设置。它不是详尽但适用于大多数组织。有 Microsoft 和客户共享 responsibilties 下方的几个项目。 

角色或职责 | 说明
--- | ---
变更管理 | Microsoft 将通知客户，提前时需要对其 Microsoft 托管桌面环境进行更改。客户，则需要具有自己的变更管理处理而有一个与 Microsoft 托管桌面运营团队建立的联系人。客户还需要有资源审阅和审批这些更改。有关详细信息，请参阅[操作和监控](../service-description/operations-and-monitoring.md)。  
标识管理 | 客户负责创建用户帐户将用户分配到组和保持最新的元数据。 
Office 365 配置和管理 | Microsoft 负责确保 Office 应用程序部署到最终用户以这些应用程序保持最新。 <br><br> 客户负责管理 Office 365 服务和策略，包括 Exchange Online 管理责任：<br>电子邮件管理<br>邮箱和规则配置<br>Exchange 部署管理<br><br>客户也是负责协作工具、 SharePoint server 管理、 域管理、 安全和信息策略在 Office 365 管理门户中设置的。 
最终用户支持 | 客户负责提供最终用户支持： <br>在网站基础结构： 所有网络和 internet 连接、 VPN 基础结构和客户端的配置、 本地会议室内设备、 打印机、 代理服务器和配置，防火墙。<br><br>-公司范围云资源： 电子邮件、 SharePoint、 协作服务和与公司范围内技术占用其他云基础结构。<br><br>-的业务和任何其他公司特定应用程序的行。
应用 | Microsoft 将提供根据请求使用 Intune 的已批准应用程序的部署指南。<br><br>客户负责为：<br>-为其组织 （外部应用程序 Office 365） 提供应用程序的列表<br>应用程序许可证管理<br>– 具有正确的类型和数量的许可证<br>应用程序工作分配<br>– 到 Azure AD 用户组分配的应用程序<br>应用程序更新<br>– 监控、 打包和部署应用程序功能和安全更新<br>用户的应用程序测试 (UAT)<br>-提供一个合适的可部署包<br><br>有关详细信息，请参阅[应用程序](../get-ready/apps.md)
安全监控和响应 | 客户负责调查和解决非 Microsoft 托管桌面设备和确保 Microsoft 托管桌面运营团队通知的可能影响服务的任何问题的事件。
操作支持 | 客户负责提供列表的首选的客户联系人和行业专家那里获得。Microsoft 需要这些情况下没有非 Microsoft 托管桌面操作事件。 <br><br>客户也是负责调查和解决的非 Microsoft 托管桌面设备和服务以及确保 Microsoft 托管桌面运营团队始终会接到通知事件。
网络基础结构，包括 VPN | 客户负责安装、 配置和管理 （包括疑难解答和调试） 的所有网络相关的基础结构和服务，包括 internet 连接网络控件、 代理配置和远程连接基础结构。<br><br>如果代理配置 （在硬件或软件），则必须允许由代理服务器的 Url 的集合。客户负责解决任何冲突或由于多个代理服务器的不兼容。<br><br>有关详细信息，请参阅[代理配置](../get-ready/network.md)。
打印 | 客户负责安装、 维护和管理打印机和打印队列。云打印建议的解决方案，但不是必需的。 




