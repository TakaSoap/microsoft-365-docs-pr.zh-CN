---
title: Contoso 的 IT 基础结构和业务需求
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 本地 IT 基础设施的基本结构，以及 Microsoft 365 企业版如何满足其业务需求。
ms.openlocfilehash: bd259f367cdf3417e32671457f248029c853b6f8
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283671"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>Contoso 的 IT 基础结构和业务需求

**摘要：** 了解 Contoso 本地 IT 基础设施的基本结构，以及 Microsoft 365 企业版如何满足其业务需求。


Contoso 正在从本地集中式 IT 基础结构转换到一个合并了基于云的个人生产率工作负载和应用程序的包含云的 IT 基础结构。

## <a name="contosos-existing-it-infrastructure"></a>Contoso 的现有 IT 基础结构

Contoso 通过将应用程序数据中心置于巴黎总部，来使用最集中的本地 IT 基础结构。

图 1 显示总部办事处及应用程序数据中心、DMZ 和 Internet。

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**图 1 Contoso 的现有 IT 基础结构**
 
本地应用程序数据中心主机： 

- 使用 SQL Server 和其他 Linux 数据库的自定义业务线应用程序。
- 一组旧版 SharePoint server。
- 用于文件存储的组织级和工作组级服务器。

此外，每个区域中心办事处都支持一组具有类似应用程序集的服务器。这些服务器处于区域 IT 部门的控制之下。

这些独立的多地理数据中心的应用程序和数据上的可搜索性仍然是一个挑战。

在 Contoso 总部 DMZ 中，不同的服务器集提供不同的功能：

- 巴黎总部的工作人员对 Contoso Intranet 和 Web 代理基于 VPN 的远程访问。
- 对 Contoso 公共网站的托管，客户可以在其中订购产品、部件、配件或服务。
- 对 Contoso 合作伙伴 Extranet 的托管，用于合作伙伴的通信和协作。

## <a name="contosos-business-needs"></a>Contoso 的业务需求

Contoso 的业务需求分为五个主要类别。

工作效率：

- 简化协作

  将电子邮件和基于文件共享的协作替换为在线模型，以允许对文档进行实时更改、简化在线会议并捕获会话线程。
- 提高远程和移动工作者的工作效率

  由于许多员工在家办公或在办公点工作，将出现瓶颈的 VPN 解决方案替换为对 Contoso 数据和云资源的高性能访问。
- 提高创造力和革新能力

  利用最新的视觉学习和创意开发方法，包括墨迹书写和 3D 可视化。

安全性：

- 标识和访问管理

  强制实施多重身份验证和其他形式的身份验证并保护用户和管理员帐户凭据。

- 威胁防护

  防范外部安全威胁，包括电子邮件和基于操作系统的恶意软件。

- 信息保护

  锁定对高价值数字资产（如客户数据、设计规范和员工信息）的访问并加密。

- 安全管理

  监视安全状态并且能够实时检测和响应威胁。

远程和移动访问及业务合作伙伴：

- 提高远程和移动工作者的安全性

  制定自带设备 (BYOD) 和公司拥有的设备管理以确保安全访问、正确的应用程序行为和公司数据保护。

- 减少员工远程访问基础结构

  通过将通常访问的资源移动到云来减少维护和支持成本，并提高远程访问解决方案的性能。

- 为企业对企业 (B2B) 交易提供更好的连接并减少开销

  将不断老化且费用高昂的合作伙伴Extranet 替换为使用联合身份验证的基于云的解决方案。

合规性：

- 遵守区域法规要求

  遵守并始终遵守针对数据存储、加密、数据隐私和个人数据的行业和区域法规，如欧盟一般数据保护条例 (GDPR)。

管理：

- 减少管理客户端电脑和设备上运行的软件的 IT 开销

  在组织中自动安装 Windows 操作系统和 Microsoft Office 更新。

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a>将 Contoso 业务需求映射到 Microsoft 365 企业版

Contoso 的 IT 部门会在部署之前，确定以下映射到 Microsoft 365 企业版 E5 功能的业务需求：

||||
|:-------|:-----|:-----|
| **类别** | **业务需要** | **Microsoft 365 企业版的产品或功能** |
| 工作效率 |  |  |
|  | 简化协作 | Teams、SharePoint Online、Skype for Business Online |
|  | 提高远程和移动工作者的工作效率 | Office 365 工作负载和基于云的数据 |
|  | 提高创造力和革新能力 | Windows Ink、Cortana at Work、PowerPoint |
| 安全性 |  |  |
|  | 标识和访问管理 | 专用全局管理员帐户使用多重身份验证 (MFA) 和 Azure AD Privileged Identity Management (PIM) <BR> 用于所有用户帐户的 MFA <BR> 条件访问 <BR> Windows Hello <BR> Windows Credential Guard |
|  | 威胁防护 | 高级威胁分析 <BR> Windows Defender <BR> 高级威胁防护 <BR> Office 365 高级威胁防护 <BR> Office 365 威胁调查和响应 <BR> |
|  | 信息保护 | Azure 信息保护 <BR> Office 365 数据丢失防护 (DLP) <BR> Windows 信息保护 <BR> Microsoft Cloud App Security <BR> Office 365 云应用安全 (CAS) <BR> Microsoft Intune |
|  | 安全管理 | Azure 安全中心  <BR> Windows Defender 安全中心 |
| 远程和移动访问及业务合作伙伴 |  |  |
|  | 提高远程和移动工作者的安全性 | Microsoft Intune |
|  | 减少员工远程访问基础结构 | Office 365 工作负载和基于云的数据 |
|  | 为 B2B 交易提供更好的连接并减少开销 | 联合身份验证和基于云的资源 |
| 合规性 |  |  |
|  | 遵守区域法规要求 | Office 365 中的 GDPR 功能 |
| 管理 |  |  |
|  | 减少安装客户端更新的 IT 开销 | 部署圈 <BR> Windows 10 就地升级和 Autopilot <BR> Office 365 专业增强版 |
||||

## <a name="next-step"></a>后续步骤

[了解](contoso-networking.md) Contoso Corporation 本地网络，以及它是如何进行优化，以跨整个组织访问或延迟访问 Microsoft 365 基于云的资源。

## <a name="see-also"></a>另请参阅

[部署指南](deploy-microsoft-365-enterprise.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)
