---
title: Microsoft 365 管理中心中的 Azure Active Directory 角色
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 在 Microsoft 365 管理中心中管理这些 Azure 管理员角色。
ms.openlocfilehash: 72835a0f9fdf9a15fc3ffa07c0fab6ca6f0260cb
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759938"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心中的 Azure Active Directory 角色

Microsoft 365 管理中心可让你管理 30 多个 Azure AD 角色。 然而，这些角色是 Azure 门户中可用角色的子集。 如果你有一家大型企业，则 Azure 门户可能具有可满足贵组织需求的角色。 是否在查找 Azure AD 的详细角色说明？ 请参阅 [Azure Active Directory 中的管理员角色权限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。

分配有管理员角色的用户在组织所订阅的云服务中拥有相同的访问权限级别，不管该角色是通过 Office 365 管理中心、Azure 门户还是适用于 Windows PowerShell 的 Azure AD 模块分配的。

在 Microsoft 365 管理中心，你可以转到“**角色**”，然后选择任何角色以打开其详细信息窗格。 选择“**权限**”选项卡，以查看分配有该角色的管理员有权执行的操作的详细列表。 选择“**已分配**”或“**已分配管理员**”选项卡，以向角色添加用户。 有关在 Microsoft 365 管理中心分配角色的详细信息，请参阅[分配管理员角色](assign-admin-roles.md)。

## <a name="all-azure-ad-roles"></a>所有 Azure AD 角色

以下是 Microsoft 365 管理中心提供的所有管理员角色的列表。 正在查找 Microsoft 365 管理员角色的详细角色说明？ 查看[关于管理员角色](./about-admin-roles.md)。

|管理员角色     |说明  |
|---------|---------|
|应用程序管理员     |    可完全访问企业应用程序、应用程序注册和应用程序代理设置。     |
|应用程序开发人员     |    创建应用程序注册并同意代表自己访问应用。     |
|身份验证管理员     |    可要求用户重新注册非密码凭据的身份验证，例如 MFA。     |
|Azure 信息保护管理员     |   管理 Azure 信息保护策略的标签、管理保护模板和激活保护。       |
|帐务管理员     |    进行采购、管理订阅、管理服务请求和监视服务运行状况。     |
|云应用程序管理员     | 可完全访问企业应用程序和应用程序注册。 无应用程序代理。     |
|云设备管理员     |    启用、禁用和删除设备，并且可以读取 Windows 10 BitLocker 密钥。     |
|合规性管理员     |    管理法规要求和电子数据展示案例，保留位置、身份和应用的数据治理。     |
|合规性数据管理员     |    跟踪数据，确保其受到保护、深入了解问题并帮助降低风险。     |
|条件访问管理员     |   管理 Azure Active Directory 条件访问设置，但不管理 Exchange ActiveSync 条件访问策略。      |
|客户密码箱访问审批者     |      管理客户密码箱请求，可以打开或关闭客户密码箱。   |
|桌面分析管理员     |   可以访问和管理桌面管理工具和服务。      |
|Dynamics 365 管理员     |  可完全访问 Microsoft Dynamics 365 Online、管理服务请求和监视服务运行状况。       |
|Exchange 管理员     |  可完全访问 Exchange Online、创建和管理组、管理服务请求和监视服务运行状况。    |
|外部标识提供程序管理员    |     可配置标识提供程序以便在直接联盟中使用。    |
|全局管理员     |    可无限制地访问所有管理中心内的全部管理功能和大部分数据。     |
|全局读取者     |    对管理中心内的全部管理功能和大部分数据具有只读访问权限。 有关此角色的访问权限和限制的详细说明，请参阅 [Azure Active Directory 中的管理员角色权限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)。    |
|组管理员   |在管理中心创建组并管理所有组设置。|
|来宾邀请者     |    管理 Azure Active Directory B2B 来宾用户邀请。     |
|支持管理员     | 为所有非管理员和某些管理员角色重置密码并重新进行身份验证、管理服务请求和监视服务运行状况。      |
|见解管理员     | 管理 Microsoft 365 见解应用程序的所有方面，阅读 Azure Active Directory 信息，可监视服务运行状况并创建和管理服务请求。      |
|见解商业版管理员     | 阅读 Microsoft 365 见解应用程序中的报告和见解。      |
|Intune 管理员     | 可完全访问 Intune，管理用户和设备以关联策略，创建和管理组。      |
|Kaizala 管理员     |    可完全访问 Kaizala 的所有管理功能和数据，管理服务请求。     |
|许可证管理员     |     分配和删除用户的许可证以及编辑其使用位置。    |
|消息中心隐私读取者     |    在消息中心访问数据隐私消息，获取电子邮件通知。     |
|消息中心读取者     | 在消息中心中读取和共享常规消息，获取每周的电子邮件摘要，对用户、组、域和订阅具有只读访问权限。     |
|Office 应用管理员    |   为 Office 管理基于云的策略，并管理用户在 Office 应用中看到的新增内容。   |
|密码管理员    |   重置非管理员或以下用户角色的密码：目录读取者、来宾邀请者，或密码管理员。 此角色无法授予管理服务请求或监视服务运行状况的能力。   |
|Power BI 管理员    |   可完全访问 Power Bl 管理任务、管理服务请求和监视服务运行状况。   |
|Power 平台管理员     |    可完全访问 Microsoft Dynamics 365、PowerApps、数据丢失防护策略和 Microsoft Flow。     |
|特权角色管理员     |    管理角色分配和 Privileged Identity Management 的所有访问控制功能。     |
|特权身份验证管理员     |    重置密码、更新非密码凭据、强制使用注销、监视服务运行状况和管理服务请求。     |
|报表阅读人员     |   可读取来自报告仪表板、Power BI 采用内容包、登录报告和 Microsoft Graph 报告 API 的使用情况报告数据。      |
|搜索管理员     |    可完全访问 Microsoft 搜索、分配搜索管理员和搜索编辑者角色、管理编辑内容、监视服务运行状况和创建服务请求。     |
|搜索编辑者     |    只能创建、编辑和删除 Microsoft 搜索的内容，例如书签、问答和位置。     |
|安全管理员     |    控制组织的安全性、管理安全策略、审查安全分析和报告、监视威胁情况。     |
|安全操作员     |    调查和响应安全警报、在 Identity Protection 中心管理各种功能、监视服务运行状况。     |
|安全读取者     |    对安全功能、登录报告和审核日志具有只读访问权限。     |
|服务支持管理员     |    为 Azure、Microsoft 365 和 Office 365 服务创建服务请求，并监视服务运行状况。     |
|SharePoint 管理员     |    可完全访问 SharePoint Online、管理 Microsoft 365 组、管理服务请求和监视服务运行状况。     |
|Skype for Business 管理员     | 可完全访问所有 Teams 和 Skype 功能以及 Skype 用户属性，管理服务请求和监视服务运行状况。      |
|Teams 管理员     |    可完全访问 Teams 和 Skype 管理中心，管理 Microsoft 365 组和服务请求以及监视服务运行状况。     |
|Teams 通信管理员     |    分配电话号码，创建和管理语音和会议策略，以及读取呼叫分析。     |
|Teams 通信支持工程师     |    读取所有呼叫参与者的呼叫记录详细信息以排查通信问题。     |
|Teams 通信支持专员     |    仅读取特定用户的用户呼叫详细信息以排查通信问题。|
|用户管理员     |   重置用户密码、创建和管理用户及组（包括筛选器）、管理服务请求和监视服务运行状况。|

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作伙伴的委派管理

如果你正与 Microsoft 合作伙伴协作，可向其分配管理员角色。 他们又可以为你的公司（或其公司）内的用户分配管理员角色。 你可能希望他们执行此操作，例如，如果是由对方为你设置和管理联机组织的情况。
  
合作伙伴可以分配以下角色：

- 完全管理，其权限等同于全局管理员，但通过合作伙伴中心管理多重身份验证除外。

- 有限管理，其权限等同于支持管理员。

在合作伙伴将这些角色分配给用户之前，必须先将合作伙伴作为委派管理员添加到你的帐户中。 此过程由授权合作伙伴发起。 合作伙伴将向你发送一封电子邮件，询问你是否要授予其作为委派管理员的权限。有关说明，请参阅[授权或删除合作伙伴关系](../misc/add-partner.md)。
  
## <a name="related-articles"></a>相关文章

[关于 Microsoft 365 管理员角色](about-admin-roles.md)

[分配管理员角色](assign-admin-roles.md)
  
[Microsoft 365 管理中心中的活动报告](../activity-reports/activity-reports.md)