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
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: 例如服务管理员等管理员角色映射到业务功能，并授予在管理中心执行特定任务的权限。
ms.openlocfilehash: cc0f40dffee4523de3a28cfe15b803b9596b8117
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520375"
---
# <a name="about-admin-roles"></a>关于管理员角色

Microsoft 365 或 Office 365 订阅附带了一组管理员角色，可使用 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a> 将这些角色分配给组织中的用户。每个管理员角色都映射到常用的业务功能，并授予组织中的用户在管理中心执行特定任务的权限。

通过 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>，可以管理 Azure AD 角色和 Microsoft Intune 角色。 然而，这些角色是 Azure 门户和 Intune 管理中心中可用角色的子集。

## <a name="watch-what-is-an-admin"></a>观看：什么是管理员？

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

1. 登录 Microsoft 365 后，选择应用启动器。 如果看到“管理”按钮，则表示你就是管理员。
1. 选择“**管理**”以转至 Microsoft 365 管理中心。
1. 在左侧导航窗格中，选择“**用户**” > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">“**活动用户**”</a>。
1. 选择要设置为管理员的人员。用户的详细信息显示在右侧对话框中。

## <a name="before-you-begin"></a>准备工作

正在查找可以在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a> 中管理的详细 Azure AD 角色说明的完整列表？ 请参阅“Azure Active Directory 中的管理员角色权限”。 [Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)。

正在查找你可以在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a> 中管理的详细 Intune 角色说明的完整列表？  查看 [Microsoft Intune 中的基于角色的访问控制 (RBAC)](/mem/intune/fundamentals/role-based-access-control)。

有关在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a> 中分配角色的详细信息，请参阅 [分配管理员角色](assign-admin-roles.md)。

## <a name="security-guidelines-for-assigning-roles"></a>分配角色的安全准则

由于管理员有权访问敏感数据和文件，因此我们建议你按照以下准则操作，以使组织的数据更加安全。

| 建议                  | 这为什么重要？                 |
| :------------------- | :------------------- |
| 拥有 2 到 4 名全局管理员  | 由于全局管理员的密码只能由另一名全局管理员进行重置，因此我们建议你的组织中至少有 2 名全局管理员，以防帐户锁定。 但是全局管理员几乎可以无限制地访问组织的设置和大部分数据，因此我们还建议你不要拥有超过 4 名全局管理员，因为这是一个安全威胁。 |
| 分配 *最小权限* 角色    | 分配 *最小权限* 角色意味着只向管理员授予完成工作所需的访问权限。 例如，如果希望其他人重置员工密码，则不应分配无限制的全局管理员角色，而应分配受限的管理员角色，如密码管理员或支持管理员。这将有助于保护你的数据安全。                 |
| 要求对管理员进行多重身份验证                  |    实际上，要求对所有用户都执行 MFA 是一个好主意，但而管理员绝对有必要使用 MFA 进行登录。 MFA 要求用户输入第二种身份验证方法，以验证他们声称的身份。 管理员可以访问大量的客户和员工数据，如果你要求 MFA，即使管理员的密码遭到泄露，若没有第二种身份证明，密码也毫无用处。  <br><br>如果你已启用 MFA，则当用户下一次登录时，他们需要提供备选电子邮件地址和电话号码才能恢复帐户。  <br> [设置多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)          |

如果你在管理中心收到一条消息，告知你没有编辑设置或页面的权限，这是因为向你分配了没有该权限的角色。

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>常用的 Microsoft 365 管理中心角色

在 Microsoft 365 管理中心，可以转到“<a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**角色分配**</a>”，然后选择任何角色以打开其详细信息窗格。 选择“**权限**”选项卡，以查看分配有该角色的管理员有权执行的操作的详细列表。 选择“**已分配**”或“**已分配管理员**”选项卡，以向角色添加用户。

你可能只需要在组织中分配以下角色。 默认情况下，我们首先显示大多数组织使用的角色。 如果找不到角色，请转到列表底部并选择“**按类别全部显示**”。 （有关详细信息，包括与角色关联的 cmdlet，请参阅 [Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)。）

|管理员角色     |应该为谁分配此角色？  |
|---------|---------|
|帐务管理员     |   向购买用户分配帐单管理员角色，管理订阅和服务请求，并监视服务运行状况。 <br><br> 帐单管理员可以：<br> - 管理帐单的各个方面 <br> - 在 Azure 门户创建和管理支持票证 <br>  |
|Exchange 管理员     |   将 Exchange 管理员角色分配给需要查看和管理用户电子邮件邮箱、Microsoft 365 组和 Exchange Online 的用户。 <br><br> Exchange 管理员还可以：<br> - 恢复用户邮箱中的已删除项目 <br> - 设置“代理发送”和“代表发送”代理 <br>  |
|全局管理员     |   向需要全局访问 Microsoft Online Services 中的大多数管理功能和数据的用户分配全局管理员角色。 <br><br> 为太多的用户提供全局访问权限会带来安全风险，我们建议你设置 2 至 4 名全局管理员。 <br><br> 只有全局管理员才能执行以下操作：<br> - 为所有用户重置密码 <br> - 添加和管理域 <br> - 取消阻止另一个全局管理员 <br> <br> **注意：** 已注册 Microsoft Online Services 的人员将自动成为全局管理员。 |
|全局读取者    |   向需要在可供全局管理员查看的管理中心中查看管理员功能和设置的用户分配全局读取者角色。全局读取者管理员无法编辑任何设置。   |
|组管理员     |   向需要跨管理中心（包括 Microsoft 365 管理中心和 Azure Active Directory 门户）管理所有组设置的用户分配组管理员角色。 <br><br> 组管理员可以：<br> - 创建、编辑、删除和还原 Microsoft 365 组 <br> - 创建和更新组的创建、过期和命名策略 <br> - 创建、编辑、删除和还原 Azure Active Directory 安全组| 
|支持管理员     |   为需要执行以下操作的用户分配支持管理员角色：<br> - 重置密码 <br> - 强制用户注销 <br> - 管理服务请求 <br> - 监视服务运行状况 <br> <br> **注意**：支持管理员只能帮助非管理员用户和分配有以下角色的用户：目录读取者、来宾邀请者、支持管理员、消息中心读取者和报表阅读人员。      |
|许可证管理员    |   为需要分配管理许可证的用户分配许可证管理员角色，删除用户的许可证并编辑其使用位置。 <br/><br/> 帐单管理员可以： <br> - 重新处理基于组的许可证分配 <br> - 将产品许可证分配给组，以便进行基于组的许可  |
|Office 应用管理员    |   为需要执行以下操作的用户分配 Office 应用管理员角色： <br> - 使用 Office 云策略服务为 Office 创建和管理基于云的策略 <br> - 创建和管理服务请求 <br> - 管理用户在 Office 应用中看到的新增内容   <br> - 监视服务运行状况  |
|密码管理员  |   将密码管理员角色分配给需要为非管理员和密码管理员重置密码的用户。   |
|消息中心读取者 |   为需要执行以下操作的用户分配消息中心读取者角色： <br> - 监视消息中心通知 <br> - 获取消息中心发布和更新的每周电子邮件摘要 <br> - 共享消息中心帖子 <br> - 对 Azure AD 服务（如用户和组）具有只读访问权限|
|Power 平台管理员 |   为需要执行以下操作的用户分配 Power Platform 管理员角色： <br> - 管理Power Apps、Power Automate 和数据丢失防护的所有管理功能 <br> - 创建和管理服务请求 <br> - 监视服务运行状况  |
|报表读取者 |   为需要执行以下操作的用户分配支持管理员角色： <br> - 在 Microsoft 365 管理中心查看使用数据和活动报告 <br> - 访问 Power BI 采用内容包 <br> - 访问 Azure AD 的登录报告和活动 <br> - 查看由 Microsoft Graph 报告 API 返回的数据|
|服务支持管理员   |   将服务支持管理员角色作为附加角色分配给管理员或用户，他们除了要负责管理员的常规工作外，还需要做以下工作： <br> - 打开和管理服务请求 <br> - 查看和共享消息中心帖子 <br> - 监视服务运行状况   |
|SharePoint 管理员    |   为需要访问和管理 SharePoint Online 管理中心的用户分配 SharePoint 管理员角色。 <br><br>SharePoint 管理员还可以： <br> - 创建和删除网站 <br> - 管理网站集和全局 SharePoint 设置   |
|Teams 管理员    |   将 Teams 管理员角色分配给需要访问和管理 Teams 管理中心的用户。 <br><br>Teams 管理员还可以： <br> - 管理会议 <br> - 管理会议网桥 <br> - 管理所有组织范围内的设置，包括联合身份验证、Teams 升级和 Teams 客户端设置   |
|用户管理员     |    为需要对所有用户执行以下操作的用户分配用户管理员角色： <br> - 添加用户和组 <br> - 分配许可证 <br> - 管理大多数用户属性 <br> - 创建和管理用户视图 <br> - 更新密码过期策略 <br> - 管理服务请求 <br> - 监视服务运行状况 <br><br>  用户管理员还可以对非管理员和分配有以下角色的用户执行以下操作：目录读取者、来宾邀请者、支持管理员、消息中心读取者和报表阅读人员： <br> - 管理用户名<br> - 删除和还原用户<br> - 重置密码 <br> - 强制用户注销 <br> - 更新 (FIDO) 设备密钥   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作伙伴的委派管理

如果你正与 Microsoft 合作伙伴协作，可向其分配管理员角色。 他们又可以为你的公司（或其公司）内的用户分配管理员角色。 你可能希望他们执行此操作，例如，如果是由对方为你设置和管理联机组织的情况。
  
合作伙伴可以分配以下角色：
  
- **管理员代理**，其权限等同于全局管理员，但通过合作伙伴中心管理多重身份验证除外。

- **支持人员代理**，其权限等同于支持管理员。

在合作伙伴将这些角色分配给用户之前，必须先将合作伙伴作为委派管理员添加到你的帐户中。 此过程由授权合作伙伴发起。 合作伙伴将向你发送一封电子邮件，询问你是否要授予其作为委派管理员的权限。有关说明，请参阅[授权或删除合作伙伴关系](../misc/add-partner.md)。
  
## <a name="related-content"></a>相关内容

[分配管理员角色](assign-admin-roles.md)（文章）\
[Microsoft 365 管理中心中的 Azure AD 角色](azure-ad-roles-in-the-mac.md)（文章）\
[Microsoft 365 管理中心中的活动报告](../activity-reports/activity-reports.md)（文章）\
[Exchange Online 管理员角色](about-exchange-online-admin-role.md)（文章）
