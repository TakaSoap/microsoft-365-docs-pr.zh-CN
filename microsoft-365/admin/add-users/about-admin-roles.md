---
title: 关于 Microsoft 365 管理中心中的管理员角色
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: 管理员角色映射到业务功能，并授予在管理中心执行特定任务的权限。 例如，服务管理员可打开 Microsoft 的支持票证。
ms.openlocfilehash: d67f80ef00f6decb7172d4ea484a3c4161fcbf31
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387414"
---
# <a name="about-admin-roles"></a>关于管理员角色

你的 Microsoft 365 或 Office 365 订阅附带了一组管理员角色，可使用 Microsoft 365 管理中心将这些角色分配给组织中的用户。 每个管理员角色都映射到常用的业务功能，并授予这些用户在管理中心执行特定任务的权限。

Microsoft 365 管理中心可让你管理 Azure AD 角色和 Microsoft Intune 角色。 然而，这些角色是 Azure 门户和 Intune 管理中心中可用角色的子集。

是否在查找 Azure AD 的详细角色说明？ 请参阅 [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。

是否在查找 Microsoft Intune 的详细角色说明？ 查看 [Microsoft Intune 中的基于角色的访问控制 (RBAC)](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。

有关在 Microsoft 365 管理中心分配角色的详细信息，请参阅[分配管理员角色](assign-admin-roles.md)。

## <a name="things-to-consider"></a>要考虑的事项...

由于管理员有权访问敏感数据和文件，因此我们建议你按照以下准则操作，以使组织的数据更加安全。

| 建议                  | 这为什么重要？                 |
| :------------------- | :------------------- |
| 拥有 2 到 4 名全局管理员  | 由于全局管理员的密码只能由另一名全局管理员进行重置，因此我们建议你的组织中至少有 2 名全局管理员，以防帐户锁定。 但是全局管理员几乎可以无限制地访问组织的设置和大部分数据，因此我们还建议你不要拥有超过 4 名全局管理员，因为这是一个安全威胁。 |
| 分配*最小权限*角色    | 分配*最小权限*角色意味着只向管理员授予完成工作所需的访问权限。 例如，如果希望其他人重置员工密码，则不应分配无限制的全局管理员角色，而应分配受限的管理员角色，如密码管理员或支持管理员。这将有助于保护你的数据安全。                 |
| 要求对管理员进行多重身份验证                  |    实际上，要求对所有用户都执行 MFA 是一个好主意，但而管理员绝对有必要使用 MFA 进行登录。 MFA 要求用户输入第二种身份验证方法，以验证他们声称的身份。 管理员可以访问大量的客户和员工数据，如果你要求 MFA，即使管理员的密码遭到泄露，若没有第二种身份证明，密码也毫无用处。  <br><br>如果你已启用 MFA，则当用户下一次登录时，他们需要提供备选电子邮件地址和电话号码才能恢复帐户。  <br> [设置多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)          |

如果你在管理中心收到一条消息，告知你没有编辑设置或页面的权限，这是因为向你分配了没有该权限的角色。

## <a name="azure-ad-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心提供的 Azure AD 角色

Microsoft 365 管理中心可让你管理 30 多个 Azure AD 角色。 然而，这些角色是 Azure 门户中可用角色的子集。 如果你有一家大型企业，则 Azure 门户可能具有可满足贵组织需求的角色。

分配有管理员角色的用户在组织所订阅的云服务中拥有相同的访问权限级别，不管该角色是通过 Office 365 管理中心、Azure 门户还是适用于 Windows PowerShell 的 Azure AD 模块分配的。

::: moniker range="o365-worldwide"

在 Microsoft 365 管理中心，你可以转到“**角色**”，然后选择任何角色以打开其详细信息窗格。 选择“**权限**”选项卡，以查看分配有该角色的管理员有权执行的操作的详细列表。 选择“**已分配**”或“**已分配管理员**”选项卡，以向角色添加用户。

::: moniker-end

你可能只需要在组织中分配以下角色。 默认情况下，我们首先显示大多数组织使用的角色。 如果找不到角色，请转到列表底部并选择“**查看更多角色**”。 （有关详细信息，包括与角色关联的 cmdlet，请参阅 [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)。）

|管理员角色     |应该为谁分配此角色？  |
|---------|---------|
|Exchange 管理员     |   将 Exchange 管理员角色分配给需要查看和管理用户电子邮件邮箱、Microsoft 365 组和 Exchange Online 的用户。 <br><br> Exchange 管理员还可以：<br> - 恢复用户邮箱中的已删除项目 <br> - 设置“代理发送”和“代表发送”代理 <br>  |
|全局管理员     |   向需要全局访问 Microsoft Online Services 中的大多数管理功能和数据的用户分配全局管理员角色。 <br><br> 为太多的用户提供全局访问权限会带来安全风险，我们建议你设置 2 至 4 名全局管理员。 <br><br> 只有全局管理员才能执行以下操作：<br> - 为所有用户重置密码 <br> - 添加和管理域 <br> <br> **注意：** 已注册 Microsoft Online Services 的人员将自动成为全局管理员。 |
|全局读取者    |   向需要在可供全局管理员查看的管理中心中查看管理员功能和设置的用户分配全局读取者角色。 全局读取者管理员不能编辑任何设置。   |
|组管理员     |   向需要跨管理中心（包括 Microsoft 365 管理中心和 Azure Active Directory 门户）管理所有组设置的用户分配组管理员角色。 <br><br> 组管理员可以：<br> - 创建、编辑、删除和还原 Microsoft 365 组 <br> - 创建和更新组的创建、过期和命名策略 <br> - 创建、编辑、删除和还原 Azure Active Directory 安全组| 
|支持管理员     |   为需要执行以下操作的用户分配支持管理员角色：<br> - 重置密码 <br> - 强制用户注销 <br> - 管理服务请求 <br> - 监视服务运行状况 <br> <br> **注意**：支持管理员只能帮助非管理员用户和分配有以下角色的用户：目录读取者、来宾邀请者、支持管理员、消息中心读取者和报表阅读人员。      |
|Office 应用管理员    |   为需要执行以下操作的用户分配 Office 应用管理员角色： <br> - 使用 Office 云策略服务为 Office 创建和管理基于云的策略 <br> - 创建和管理服务请求 <br> - 管理用户在 Office 应用中看到的新增内容   <br> - 监视服务运行状况  |
|服务管理员    |   将服务管理员角色作为附加角色分配给其角色不包括以下内容，但仍需要执行以下操作的管理员或用户： <br> - 打开和管理服务请求 <br> - 查看和共享消息中心帖子   |
|SharePoint 管理员    |   为需要访问和管理 SharePoint Online 管理中心的用户分配 SharePoint 管理员角色。 <br><br>SharePoint 管理员还可以： <br> - 创建和删除网站 <br> - 管理网站集和全局 SharePoint 设置   |
|Teams 服务管理员    |   为需要访问和管理 Teams 服务管理中心的用户分配 Teams 管理员角色。 <br><br>Teams 服务管理员还可以： <br> - 管理会议 <br> - 管理会议网桥 <br> - 管理所有组织范围内的设置，包括联合身份验证、Teams 升级和 Teams 客户端设置   |
|用户管理员     |    为需要对所有用户执行以下操作的用户分配用户管理员角色： <br> - 添加用户和组 <br> - 分配许可证 <br> - 管理大多数用户属性 <br> - 创建和管理用户视图 <br> - 更新密码过期策略 <br> - 管理服务请求 <br> - 监视服务运行状况 <br><br>  用户管理员还可以对非管理员和分配有以下角色的用户执行以下操作：目录读取者、来宾邀请者、支持管理员、消息中心读取者和报表阅读人员： <br> - 管理用户名<br> - 删除和还原用户<br> - 重置密码 <br> - 强制用户注销 <br> - 更新 (FIDO) 设备密钥   |

### <a name="all-azure-ad-roles"></a>所有 Azure AD 角色

 以下是 Microsoft 365 管理中心提供的所有管理员角色的列表。

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
|全局读取者     |    对管理中心内的全部管理功能和大部分数据具有只读访问权限。 有关此角色的访问权限和限制的详细说明，请参阅 [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)。    |
|组管理员   |在管理中心创建组并管理所有组设置。|
|来宾邀请者     |    管理 Azure Active Directory B2B 来宾用户邀请。     |
|支持管理员     | 为所有非管理员和某些管理员角色重置密码并重新进行身份验证、管理服务请求和监视服务运行状况。      |
|Intune 管理员     | 可完全访问 Intune，管理用户和设备以关联策略，创建和管理组。      |
|Kaizala 管理员     |    可完全访问 Kaizala 的所有管理功能和数据，管理服务请求。     |
|许可证管理员     |     分配和删除用户的许可证以及编辑其使用位置。    |
|消息中心隐私读取者     |    在消息中心访问数据隐私消息，获取电子邮件通知。     |
|消息中心读取者     | 在消息中心中读取和共享常规消息，获取每周的电子邮件摘要，对用户、组、域和订阅具有只读访问权限。     |
|Office 应用管理员    |   为 Office 管理基于云的策略，并管理用户在 Office 应用中看到的新增内容。   |
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

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心提供的 Microsoft Intune 角色

|管理员角色     |应该为谁分配此角色？  |
|---------|---------|
|应用程序管理员     |   将应用程序管理员角色分配给管理移动应用的应用程序生命周期、配置策略管理的应用以及查看设备信息和配置文件的用户。  |
|技术支持操作员     |   将技术支持操作员角色分配给向用户和设备分配应用程序和策略的用户。 |
|Intune 角色管理员    |   将 Intune 角色管理员分配给可以向其他管理员分配 Intune 权限，并且可以管理自定义和内置 Intune 角色的用户。   |
|策略和个人资料管理员     |   将策略和个人资料管理员角色分配给用户管理合规性策略、配置文件和 Apple 注册的用户。   |
|只读操作员     |   将只读操作员角色分配给仅可查看用户、设备、注册详细信息和配置的用户。   |
|学校管理员     |   将学校管理员角色分配给用户，以获取在 Intune 教育版中管理 Windows 10 和 iOS 设备、应用和配置的完全访问权限。   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作伙伴的委派管理

如果你正与 Microsoft 合作伙伴协作，可向其分配管理员角色。 他们又可以为你的公司（或其公司）内的用户分配管理员角色。 你可能希望他们执行此操作，例如，如果是由对方为你设置和管理联机组织的情况。
  
合作伙伴可以分配以下角色：
  
- 完全管理，其权限等同于全局管理员，但通过合作伙伴中心管理多重身份验证除外。
    
- 有限管理，其权限等同于支持管理员。

在合作伙伴将这些角色分配给用户之前，必须先将合作伙伴作为委派管理员添加到你的帐户中。 此过程由授权合作伙伴发起。 合作伙伴将向你发送一封电子邮件，询问你是否要授予其作为委派管理员的权限。有关说明，请参阅[授权或删除合作伙伴关系](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)。
  
## <a name="related-articles"></a>相关文章

[分配管理员角色](assign-admin-roles.md)
  
[Microsoft 365 管理中心中的活动报告](../activity-reports/activity-reports.md)
