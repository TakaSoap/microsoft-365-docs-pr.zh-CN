---
title: 在组织中使用自助注册
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: 了解 Microsoft 365自助注册和可用的自助服务计划，如 Microsoft Power Apps、Microsoft Power Automate 和 Dynamics 365 for Finance。
ms.date: 03/17/2021
ms.openlocfilehash: 87f432be0659d03a1e8f77b682997dc32d1dc111
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192687"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>在组织中使用自助注册

自助注册使贵组织的用户更容易从 Microsoft 注册联机服务。 我们将此注册过程称为"自助式注册"，因为您的用户可以注册以使用您的订阅付费的服务或使用免费服务，而无需要求您代表他们采取措施。

## <a name="how-self-service-sign-up-works"></a>自助服务注册的工作原理

以下示例介绍自注册如何适用于学校。 相同的过程适用于其租户中启用了自助服务计划的任何组织。

1. 学生和教职员工具有学校电子邮件地址，指示他们与机构关联。 例如，该 jakob@uw.edu 可能指示位于华盛顿大学的学生。
2. 学生和教职员工转到[我们的](https://go.microsoft.com/fwlink/p/?LinkId=536628)网站，并使用他们的电子邮件地址注册你的组织提供的服务，例如Microsoft 365 企业应用版。 他们还可以注册我们提供的其他免费服务。
3. 我们验证他们的电子邮件地址，然后他们可以立即开始Microsoft 365、Power BI或其他服务。
4. 作为业务管理员，可以通过在"许可"页上选择订阅来查看注册订阅Microsoft 365 管理中心。  这样，你可以查看租户中服务的新许可证或无法识别的许可证。 若要控制用户是否可以注册自助服务订阅，请使用 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell cmdlet 和 **AllowAdHocSubscriptions** 参数。 有关详细信息，请参阅 [如何控制自助服务设置？](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>可用的自助服务程序

以下是当前可用的自助服务程序。 此列表将在添加新程序时更新。

| 程序 <br/> | 说明 <br/> | 其他信息 <br/> | 自助式注册网站 <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |任何学生或教师都可以使用学校电子邮件地址注册免费 Office 365并获取适用于 Web 的 Office 应用、1 TB 的 OneDrive 云存储和 SharePoint Online 用于课堂、团队和项目网站。  <br/> |[Office 365 教育版技术常见问题解答](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 教育版](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1Plus** <br/> |符合条件的学生和教师可以注册 Office 365 A1 Plus，其中包括上面提到的一切以及Microsoft 365 企业应用版。 Microsoft 365 企业应用版是安装在台式机或笔记本电脑上的生产力软件，包括 Word、PowerPoint、Excel、Outlook、OneNote、Publisher、Access 和 Skype for Business。  <br/> |[Office 365 教育版技术常见问题解答](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 教育版](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI用户能够直观地以新方式可视化数据、共享发现和协作。 <br/> 如果你的组织已经订阅了，你可能还看到"Power BI Pro个人用户试用版"的许可证，这将为用户提供有限的免费高级功能访问权限。  <br/> |[Power BI组织中工作](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**权限管理服务 (RMS)** <br/> |个人 RMS 是组织中已发送受 Azure 权限管理 (Azure RMS) 保护的敏感文件，但其 IT 部门尚未实施 Azure 权限管理 (Azure RMS) 或 Active Directory Rights Management Services (AD RMS) 的用户的免费自助服务订阅。  <br/> |[个人 RMS 和 Azure 权限管理](/azure/information-protection/rms-for-individuals) <br/> |[Microsoft 权限管理](https://portal.azure.com/) 门户，以便您可以检查您是否可以打开给定的受权限保护的文档。  <br/> |
|**Microsoft Power Apps** <br/> |在Power Apps中，可以通过运行你创建的或其他人创建并与您共享的应用来管理组织数据。 应用在手机等移动设备上运行，或者可以通过打开 Dynamics 365 在浏览器中运行它们。 你可以创建无限不同的应用-所有这些应用都无需学习编程语言，如C#。  <br/> |[自助注册Power Apps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |获取适用于中小型企业的完整业务和财务管理解决方案。 Dynamics 365 for Financials 使订购、销售、开票和报告变得更简单-从第一天开始。  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |提高你的业务处理速度。 Dynamics 365 for Operations 中的完整 ERP 工具提供了全局可伸缩性和数字智能，可帮助你加快进度。  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource 是在 Microsoft 云平台上构建的软件即服务业务应用的目标。 AppSource 具有数百个应用、加载项和内容包，可扩展 Microsoft 产品（如 Azure、Dynamics 365、Office 365 和 Power BI）的功能。  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft 合作伙伴奖励** <br/> |Microsoft 合作伙伴网络提供三种类型的成员身份。 每种类型都提供了一组优势，可帮助你的业务增长。 当你实现目标时，请参与适合你的独特需求的计划，以访问更多权益并发展你与网络内的其他合作伙伴的关系。  <br/> |[Microsoft 合作伙伴奖励](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft 合作伙伴奖励](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft 商业中心** <br/> |Microsoft 商业中心是一个门户，供通过 MPSA (Microsoft 产品和服务协议进行) 。 <br/> |[快速入门：注册 Microsoft 商业中心](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft 商业中心](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft 批量许可服务中心** <br/> |Microsoft 批量许可证服务中心显示Enterprise、选择、教育版 (校园或学校) 、开放式价值、开放式许可证和 ISV 版税协议下购买的许可证。  <br/> |[VLSC 培训和资源](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**我的世界Education Edition** <br/> |通过使用我的世界学习平台，教师可以鼓励和激发每个学生实现更多目标，并激发学习动机。 加入教师社区，了解如何使用我的世界释放学生潜能。  <br/> |[我的世界Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[我的世界Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Upload并共享整个组织的视频，以改进沟通、参与和学习。  <br/> |[注册 &amp; 第 0 天体验](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate是一种有助于在常用应用和服务之间设置自动工作流的产品，以同步文件、获取通知、收集数据等。  <br/> |[注册并登录Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents使团队能够使用引导的无代码图形界面轻松创建功能强大的机器人，而无需数据工作者或开发人员。 Power Virtual Agents解决当今行业中机器人构建的许多关键问题。 它消除了主题专家与构建机器人的开发团队之间的空白，以及团队识别问题与更新机器人以解决问题之间的长期延迟。  <br/> |[许可和访问详细信息](/power-virtual-agents/requirements-licensing) <br/> |[注册Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) 企业到企业 (B2B) 协作允许你邀请外部用户 (或"来宾用户") 使用付费 Azure AD 服务。 某些功能是免费的，但对于任何付费的 Azure AD 功能，你可以为租户中的员工或非来宾用户拥有的每个 Azure AD 版本许可证邀请最多五个来宾用户。 <br/> |[Azure AD B2B 协作注册自助服务](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active DirectoryB2B 协作许可指南](/azure/active-directory/b2b/licensing-guidance) <br/> |
