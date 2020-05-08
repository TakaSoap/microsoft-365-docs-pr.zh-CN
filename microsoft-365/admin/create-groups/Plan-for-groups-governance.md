---
title: 规划组治理
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: 了解如何规划 Microsoft 365 组治理。
ms.openlocfilehash: 85dfbb27899d7b79257eba4cff4b7cd715f762a5
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064783"
---
# <a name="plan-for-governance-in-groups"></a>在组中规划管理

Microsoft 365 组提供了一组丰富的工具来实施您的组织可能需要的任何管理功能。 本文指导 IT 专业人员提出正确的问题，以确定他们的治理要求以及如何根据组织的配置文件来满足这些要求。

## <a name="why-microsoft-365-groups"></a>为什么为 Microsoft 365 组？
![图像 desc](../../media/01.png)

我们知道，目前的组织使用不同的工具集。 拥有团队聊天的开发人员团队、负责发送电子邮件的开发人员以及通过企业社会进行连接的整个组织。 由于每个组都是唯一的，并且拥有自己的功能需求和工作方式，因此使用多个协作工具。 有些将仅使用电子邮件，而其他人将主要驻留在聊天中。 

如果用户认为 IT 提供的工具不能满足其需求，他们可能会下载其喜爱的使用者应用程序来支持其应用场景。 虽然此过程允许用户快速入门，但它会导致在组织中遇到多个登录、难以共享且没有查看内容的单一位置的用户体验。 此概念称为 "隐藏 IT"，并给组织带来了巨大风险。 它降低了统一管理用户访问、确保安全性和服务合规性需求的能力。

Microsoft 365 组为用户提供了多个协作所需工具的步骤并降低了卷影风险。 通过 Microsoft 365 组，您可以选择要与之进行协作的一组人员，并轻松为要共享的人员设置资源的集合。 手动将权限分配给资源是过去将成员添加到组中的任务。自动为组提供的所有资产授予所需的权限。

## <a name="technical-architecture"></a>技术体系结构

Microsoft 365 组支持三种主要的通信方法。 可以在这些体验中创建组，并在 Microsoft 365 中使用这些组：
- Outlook：通过使用共享组收件箱和日历的电子邮件进行协作
- Microsoft 团队：一种基于持久聊天的工作区，您可以在其中围绕各种主题（按特定子组组织的主题）进行非正式、实时的对话
- Yammer：协作的企业社交体验

> [!NOTE]
> 通过其他团队应用程序（如 SharePoint、Planner 或 Stream）创建新组-将使用 Outlook 收件箱创建一个组，并能够连接到 Microsoft 团队。

根据创建组的位置，将自动预配某些资源，如：
- [收件箱](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)-组成员之间的电子邮件对话。 此收件箱有一个电子邮件地址，可以将其设置为接受来自组外部的人的邮件，甚至来自您的组织外部的邮件，这与传统的通讯组列表非常相似。
 - [日历](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)–用于计划与组相关的事件
- [SharePoint 团队网站](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)–中心存储库，其中提供了与您的组相关的信息、链接和内容
- [SharePoint 文档库](https://support.microsoft.com/en-us/office/share-group-files-in-outlook-749bc73b-90c9-4760-9b6f-9aa1cf01b403)–用于存储和共享文件的组的中心位置
- [OneNote 笔记本](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)–用于收集想法、研究和信息
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) –用于分配和管理组成员中的项目任务
- [Yammer 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)–一个用于提供对话和共享信息的常见位置
- Microsoft 团队– Microsoft 365 中的基于聊天的工作区

若要了解有关为每个组创建的资源的详细信息，请参阅[了解 Microsoft 365 组](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

> [!NOTE]
> 当通过 Yammer 或团队创建新的 Microsoft 365 组时，该组在 Outlook 或通讯簿中不可见，因为这些用户之间的主要通信发生在其各自的客户端中。 Yammer 组无法连接到 Microsoft 团队。

## <a name="where-to-start-a-conversation"></a>开始对话的位置
在 Microsoft 365 中有多个位置在对话中。 了解从何处开始对话可帮助组织定义通信策略。

![图像 desc](../../media/03.png)

- 团队：基于聊天的工作区（高速度协作）–内部循环
   - 为与每天合作的人员进行协作而构建
  - 通过单一体验将信息放在用户的手边
  - 添加选项卡、连接器和 bot
  - 实时聊天、音频/视频会议、录制的会议

- Yammer：跨组织（企业社交）–外部循环连接
  - 实践的社区-跨职能组的人员，这些人共享共同的兴趣或专业技能，但不一定每天都在进行协作。
  - 领导层连接、学习社区、基于角色的社区

- Outlook 组：新式 DL （基于电子邮件的协作）
  - 目标通信的普遍情况
  - 将 Dl 升级到 Microsoft 365 组–[为什么要升级？](https://support.microsoft.com/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint –所有 Microsoft 365 组的核心内容协作体验
  - 每个组都将获取一个连接的 SharePoint 团队网站
  - 共享内容、创建自定义页面和创作新闻
  - [将](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)现有 SharePoint 团队网站连接到新的 Microsoft 365 组

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>在规模扩展时管理和管理 Microsoft 365

Microsoft 365 组提供了一组丰富的工具来实施您的组织可能需要的任何管理功能。 下一节介绍了功能、建议最佳做法，并提供了指导以确定对调控的要求以及如何满足这些要求的指导。

**本节**内容：
- [控制可以创建 Microsoft 365 组的用户](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [组软删除和还原](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [组命名策略](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [组过期策略](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [组来宾访问](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [组策略 & 信息保护](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [升级传统协作工具](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [组报告](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>控制可以创建 Microsoft 365 组的用户
最终用户可以从多个终结点（包括 Outlook、SharePoint、团队和其他环境）创建组。

![图像 desc](../../media/04.png)
> [!Tip]
>- 强烈考虑自助式，以便为组所有者做准备。
>- 记录并传达如何请求组。
>- 重新访问在你的云旅程期间可以创建组的用户。
>- 请考虑使用动态成员身份来配置安全组的成员，以控制组创建。
>- 评估可通过动态成员资格管理的组方案，并允许对 rest 使用自助服务。

组中有三个主要的预配模型：开放、IT 打头阵和可控。 下表介绍了每个模型的优点。

| 模型          | 优点                                                   |
| -------------- | ------------------------------------------------------------ |
| 打开（默认） | 用户可以根据需要创建自己的组，而无需等待或困扰它。 |
| IT-led         | 用户从其请求组。 在选择最佳协作工具以满足其需求时，可以对其进行指导。 |
| 控制     | 组创建仅限于特定人员、团队或服务。 若要了解详细信息，请参阅[管理可创建 Microsoft 365 组的用户](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)。 |

您的组织可能具有对可以创建组的用户实施严格控制的特定要求。 使用下表可帮助制定有关适合贵组织的设置模型的决策。

|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>哪种设置模型适合您的组织要求？</li><li>您的组织是否需要将组创建限制为管理员？</li><li>您的组织是否需要将组创建限制为安全组成员？</li><li>您的组织是否需要根据用户属性（如部门）动态创建某些组？</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>记录组织对组和团队创建的要求。</li><li>计划在你的组部署过程中实施这些要求。</li><li>交流并发布策略以通知用户他们可能会想到的行为</li><li>计划在适用的情况下实施动态成员资格。</li></ul>|

> [!Important]
> 限制组和团队创建会降低用户工作效率，因为许多 Microsoft 365 服务都需要创建组才能使服务正常工作。 若要了解详细信息，请参阅[为什么控制谁创建了 Microsoft 365 组？](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)

#### <a name="resources"></a>*资源*
- [管理可以创建 Microsoft 365 组的用户](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [根据对象属性动态填充组](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [如何将适用于 Outlook 的 Microsoft 365 组的默认设置更改为公用或专用](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [将安全组与团队成员身份同步](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>组软删除和还原
如果已删除 Microsoft 365 组，默认情况下它将保留30天。 这 30 天时间被称为"软删除"，因为仍然可以对组进行还原。 30 天后，组和相关内容将永久删除且无法还原。

> [!Tip]
>- 将还原过程传达给用户。
>- 培训帮助台团队。
>- 跟踪将使用 PowerShell 脚本删除的即将到来的组。

|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>您是否需要将某些资产存档以用于长期存储？</li><li>您的组织是否有一定的保留要求？</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>传递和发布删除和还原策略，以通知用户他们可能会想到的行为 </li><li> 记录监视已删除组的组织需求。</li><li>计划在你的组部署过程中实施这些要求。</li></ul>|

> [!Important]
>在"软删除"过程中，如果用户尝试访问该网站，将显示 403 禁止访问消息。 该过程结束后，如果用户尝试访问该网站，将显示 404 未找到消息。

#### <a name="resources"></a>*资源*
- [还原已删除的 Microsoft 365 组](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [在 Azure Active Directory 中还原已删除的 Microsoft 365 组](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [使用 Remove-UnifiedGroup cmdlet 删除组](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>组命名策略
命名策略可帮助您和您的用户标识组、成员身份、地理区域或创建组的用户的功能。 命名策略还有助于对通讯簿中的组进行分类。 您可以使用该策略阻止在组名称和别名中使用特定字词。

> [!Tip]
> - 将短字符串用作后缀。
> - 将属性与值结合使用。
> - 不太富有创意，总名称长度最多为264个字符。
> - 将组织特定阻止的词上传以限制使用。


|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>您的组织是否需要特定的组命名约定？</li><li>您的组织是否需要跨所有工作负载的命名约定？</li><li>您的组织是否有您想要阻止用户使用的特定词语？</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>记录组织命名组的要求。 </li><li> 计划在你的组部署过程中实施这些要求。</li><li> 交流并发布命名策略和标准，以通知用户。</li></ul>|

> [!Important]
>命名策略适用于跨所有组工作负荷（如 Outlook、Microsoft 团队、SharePoint、Planner、Yammer 等）创建的组。 它将应用于组名称和组别名。 当用户创建组时，或者在编辑现有组的组名称或别名时，将应用此方法。

#### <a name="resources"></a>*资源*
- [Microsoft 365 组命名策略](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [在 Azure Active Directory 中强制实施 Microsoft 365 组的命名策略](https://go.microsoft.com/fwlink/?linkid=868340)
- [用于配置组设置的 Azure Active Directory cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
- [组命名的预览功能](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>组过期策略
管理员可以指定过期时间和到达该时间段结束的任何组，并且不会进行续订，将被删除。 过期时间是在创建组时开始，或在上次续订日期时开始。 在过期之前，将自动向组所有者发送一封电子邮件，以允许他们为其他过期间隔续订组。 活动组自动续订。

将组设置为过期后：
- 在临近过期时，会通知组的所有者续订组
- 任何未续订的组都将被删除
- 可以由组所有者或管理员在30天内恢复删除的任何组

> [!Tip]
> - 最初使用特定组的试点。
> - 根据 Microsoft 365 管理中心中的活动报告选择非活动组。
> - 将续订过程传达给组所有者。
> - 板载你的帮助台团队。
> - 确保组具有多个所有者，并为孤立组配置电子邮件。


|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>你的组织是否需要为团队指定到期日期？</li><li>确定处理孤立组的策略。</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>记录组织对组过期、数据保留和存档的要求。</li><li>计划在你的组部署过程中实施这些要求。</li><li>计划实施自定义作业，以报告拥有单个所有者或 ownerless 的组。 </li></ul>|

> [!Important]
>当您更改过期策略时，服务将重新计算每个组的到期日期。 它始终从创建组的日期开始计数，然后应用新的过期策略。

#### <a name="resources"></a>*资源*
- [Microsoft 365 组过期策略](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [为 Microsoft 365 组配置过期策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>组来宾访问
管理员可以控制是否允许来宾访问整个组织或单个 Microsoft 365 组的 Microsoft 365 组。 他们还可以控制谁能允许将来宾添加到组中。
>[!Tip]
>- 在租户级别启用来宾访问。 如果需要，请为特定组进行阻止。
>- 使用 "允许/阻止来宾域"、"来宾邀请者" 角色、"访问权限" 和使用条款来管理。
>- 通过审核日志跟踪来宾用户活动。

|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>是否需要限制以每组为单位向团队添加来宾的能力？</li><li> 您的组织是否需要为法律或合规性要求提供相关免责声明？</li><li>您的组织是否需要减少添加和删除用户的管理工作？</li><li>您的组织是否需要来宾/外部访问的审核控件？</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>对某些分类组（包括保留期和匹配项）的来宾/外部访问的文档要求。</li><li>记录组织对哪些组需要使用条款和访问权限评审的要求。 </li><li>执行检查以有效管理内部和来宾用户的组成员身份。</li></ul>|


#### <a name="resources"></a>*资源*
- [与组织外部的人员进行协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [在 Microsoft 365 组中管理来宾访问](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Microsoft 365 组中的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Azure AD 访问审查](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Azure Active Directory 使用条款功能](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google 联合](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>组策略 & 信息保护
Microsoft 365 组基于 Microsoft 365 的高级安全性和合规性功能，并支持分类、审核和报告、合规性内容搜索、电子发现、合法保留和保留策略。
>[!Tip]
>- 配置与您的组织的需求相适应的分类、使用指南和标签。
>- 可以独立于标签定义保留策略。
>- 审核组活动：创建、删除等。
>- 根据分类管理组隐私和来宾访问。

|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>您的组织是否有需要向所有用户传递的特定使用要求？</li><li>您的组织是否需要所有内容的分类？</li><li>您的组织是否要求在特定时间段内保留内容？</li><li>您的组织是否需要对组应用特定的数据保留策略？</li><li>您的组织是否希望能够将非活动组存档以保留内容？</li><li>组创建者是否需要能够将组织特定的分类分配给团队？</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>记录组织的组使用指南</li><li>记录组织对分类的要求。</li><li>根据分类（如敏感度、保留、来宾访问）确定要强制实施的策略。</li><li>为您的组织定义敏感度标签以及要关联的保护设置。</li><li>定义一个标签策略来控制哪些用户和组可以查看这些标签。</li><li>配置[组敏感度标签预览](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)，并开始对组织中的组进行分类。</li><li>计划在你的组部署过程中实施这些要求。</li></ul>|


#### <a name="resources"></a>*资源*
- [链接到 Microsoft 365 组使用指南](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [为组织中的 Office 组创建分类](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [配置组设置](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [保留策略概述](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [敏感度标签概述](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)
- [标签概述](https://docs.microsoft.com/office365/securitycompliance/labels)
- [搜索审核日志](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)
- [创建或删除就地法定保留](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [创建保留策略](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [在安全 & 合规中心中运行内容搜索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search)
- [使用 PowerShell 批量创建和发布保留标签](https://docs.microsoft.com/office365/securitycompliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>升级传统协作工具
多年来，组织依靠通讯组与公司内部和外部的一组人员进行通信和协作。 但是现在，Outlook 中的 Microsoft 365 组为协作提供了更强大的解决方案。 此外，如果您想要将 Microsoft 365 组连接到现有 SharePoint 网站，则必须对该网站进行现代化。

>[!Tip]
>- 通过 Exchange 管理中心或使用 PowerShell cmdlet 轻松升级所有符合条件的通讯组列表（以秒为单位）。
>- 将现有 SharePoint 团队网站连接到新的 Microsoft 365 组。

|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>您的组织是否有[不符合升级条件](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade)的通讯组列表？<li>确定哪种类型的组是最适合迁移到的通讯组列表。</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>确定哪些通讯组列表将成为升级到 Microsoft 365 组的首选。</li><li>分析现有的 SharePoint 团队网站，以查看哪些网站已准备好进行组连接。</li><li>让您的公司中的其他团队知道您是否已升级通讯组以及为成功而采取的步骤！</li></ul>|


#### <a name="resources"></a>*资源*
- [将通讯组列表（DL）升级到 Outlook 中的组](https://aka.ms/whyupgradedls)
- 通过 Exchange 管理中心或通过[PowerShell 脚本](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)只单击一次即可进行升级
- [将通讯组列表迁移到 Microsoft 365 组-管理员帮助](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [将现有 SharePoint 网站连接到 Microsoft 365 组：](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [分析和使用扫描程序数据](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint 现代化扫描程序](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization)（位于 GitHub 上的工具）

### <a name="groups-reporting"></a><a name="groups-reporting"></a>组报告
Microsoft 365 "报告" 仪表板显示组织中的所有 Microsoft 产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。
> [!TIP]
>- 您可以使用组报告深入了解组织中的 Microsoft 365 组活动，并查看创建和使用的组数。
>-可查看最近7天、30天、90天或180天的趋势的 Microsoft 365 组报告。
>- 跨组邮箱对话监视组活动、分组网站/文件活动，以及有关组成员身份的详细信息，包括外部成员计数。
>- 定期监视以进入活动组的所有者，以了解使用案例并在内部扩展它们。
>- 利用 Power BI 内容包获取更多见解。


|         |         |         |
|---------|---------|---------|
|![图像 desc](../../media/decision_point.png)|决策点|<ul><li>您的组织是否需要常规报告来了解 Microsoft 365 组的使用情况？<li>您的组织是否需要对具有外部成员的所有组进行报告？</li></ul>|
|![图像 desc](../../media/next_steps.png)|后续步骤|<ul><li>记录组织对定期查看组活动报告的要求。</li></ul>|


#### <a name="resources"></a>*资源*
- [管理中心中的 Microsoft 365 报表](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Office 365 采用内容包](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD 内容包](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph 组活动 API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Microsoft 365 组报告（统一组）](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Azure Active Directory 门户中的审核活动报告](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph-使用 delta 查询跟踪更改](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>入门基于你的云采用旅程

Microsoft 365 组提供了您的组织可能需要的一组丰富的管理功能。 请考虑以下组织配置文件作为了解最佳实践的指导，提出正确的问题来确定对公司治理的要求，以及如何满足这些要求。

**请考虑以下组织配置文件：**
- 小型企业
- 中小型企业
- 管控或企业

### <a name="small-business"></a>小型企业
请考虑部署了 Microsoft 365 的组织，至少具有 Exchange Online 和 SharePoint Online 许可证，其中包括业务重点和业务高级计划，以及没有 Azure 主动控制器高级许可的企业版 E1、E3 和 E5 计划。

| 阶段 | 说明 |
| --------------- | ------------------------------------------------------------ |
| 指南 |<ul><li>考虑自助服务设置模型。</li><li> [默认情况下](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395)，Outlook & SharePoint 网站中的组是私有的。</li><li> 可以通过将现有通讯组列表（Dl）或通过 PowerShell 批量升级来创建组。 请参阅[将通讯组列表升级到 Microsoft 365 组](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)。</li><li> 启用来宾访问，但使用允许/阻止来宾域管理。</li><li> 使用组报告获取有关用户使用组的方式的见解。</li><li> 考虑创建一个组织范围的团队 Microsoft 团队团队，使每个人都成为单个团队协作的一部分。 </li></ul>|
| 后续步骤      |<ul><li>请考虑使用[网站设计和网站脚本](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)，将默认设计定义为使用[JSON 架构引用](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)中定义的操作的控件。</li><li>查看[组报告](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)。</li><li>跟踪总组和非活动/活动组。</li><li>同时跟踪使用的 Exchange 和 SharePoint 存储。</li><li>跨组邮箱对话查看组活动、分组网站/文件活动等。</li></ul> |

### <a name="medium-sized-business"></a>中小型企业
除了上述建议之外，还请考虑使用至少部署了带有 Azure Active Directory 高级 P1 许可证的企业版 E3/E5 的 Microsoft 365 的中型企业的以下各项。

| 阶段 | 说明 |
| --------------- | ------------------------------------------------------------ |
| 指南 |<ul><li>确定开放或 IT led 设置模型。</li><li> 考虑基于 Azure AD 属性（如部门）创建绑定到[动态成员身份规则](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)的特定组</li><li> 在您的组织内定义分类，例如高度机密、机密（默认）、常规。</li><li>  根据分类（如保留和敏感度）定义策略。</li><li> SharePoint 是每个 Microsoft 365 组的内容服务。 考虑为三层保护（基准、敏感和高度机密）设计和[部署 SharePoint Online 网站](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection)。 有关三层保护的详细信息，请参阅[保护 SharePoint Online 网站和文件](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)。</li><li> 默认情况下，公共组和专用组都列在 GAL 中。 确定要在 Microsoft 团队之外的特定于 GAL 中创建的组中显示的组。  使用[remove-unifiedgroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) cmdlet 的 "HiddenFromAddressListsEnabled" 或 "HidefromExchangeClients" 可隐藏特定组。</li></ul> |
| 后续步骤      |<ul><li>定义[使用指南](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)，以向用户介绍有助于保持其组织有效的最佳做法，并在内部内容策略上进行培训。 例如，了解分类、策略和过程。 </li><li>定义组生命周期周期必须更新组或将被删除-过期策略。</li><li>考虑创建以下自定义作业，以根据分类实施策略。</li><li>将隐私设置为私有。</li><li>禁用外部成员身份/共享。 </li><li>向[没有所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)的组通知组成员的电子邮件。</li><li>强制实施所有权策略（最小2所有者）。</li><li> 根据分类定义组的保留策略。 </li><li>保留策略概述。</li><li>使用 Powershell 确定具有分类和[new-retentioncompliancepolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)的组。</li><li>请考虑使用网站设计和网站脚本来定义使用[JSON 架构引用](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)中定义的操作的控件。</li><li>请考虑[使用网站设计和 Microsoft 流构建一个简单的网站目录](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial)。 每当使用此网站设计创建网站时，都会捕获网站的详细信息并将其写入列表。 </li></ul>|

### <a name="regulated-or-enterprise"></a>管控或企业
除了上述建议之外，还请考虑以下几个方面的 prises （如政府、金融服务或保健），其中至少部署了带有 Azure Active Directory 高级 P1/P2 许可证的企业版 E3/E5 的 Office 365。

| 阶段 | 说明 |
| --------------- | ------------------------------------------------------------ |
| 指南 |<ul><li> 根据分类定义与组关联的 SharePoint 网站的数据管理策略。</li><li>[使用标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)。</li><li>[使用 Azure 信息保护来保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。</li><li> 在与用户的首选数据位置（[多地理](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)位置）关联的区域中预配的组网站。</li><li> 具有外部成员的组的成员身份检查（[访问评审](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)）。</li><li>在获取访问权限之前，请确保员工或来宾用户看到有关法律或合规性要求的相关免责声明。 （[使用条款](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)）。</li><li>使用特定[分类（也有外部用户](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561)）标识和报告 Microsoft 365 组。</li><li>必须使用[remove-unifiedgroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) cmdlet （使用 HiddenGroup-MembershipEnabled 开关）在组创建时创建需要隐藏的成员身份的机密组。</li><li>为组织定义[敏感度标签](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)，以[使用加密来限制对内容的访问](https://docs.microsoft.com/Office365/SecurityCompliance/encryption-sensitivity-labels)并发布到特定的 Microsoft 365 组。</li><li>使用[具有 Windows 信息保护的敏感度标签，](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)防止敏感内容在运行 Windows 的设备上离开组织。 |
| 后续步骤      | <ul><li> 使用网站设计和网站脚本定义在创建新网站时发生的默认[操作](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/)。 例如，[配置外部共享设置](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting)或[触发 Microsoft 流，以调用 Azure 函数](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function)以应用本机不支持的配置。 </li><li> 记录要求，以[使用标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)与 Microsoft 365 组关联的网站。</li><li>对连接到 Microsoft 365 组的[SharePoint Online 网站和文件进行保护](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files)的文档组织要求。 </li><li>记录对特定用户或组发布[敏感度标签](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)以保护内容的组织要求。</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>组管理功能规划清单

可以通过 Azure Active Directory 管理许多与组相关的控件。 若要了解有关配置组设置的详细信息，请参阅[用于配置组设置的 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

使用下表确定部署组织要求所需的功能。 它将帮助您确定所需的许可证，以便您可以提前规划。

| **功能**      | **详细信息**                                    | **需要 Azure AD Premium 许可证** | **决策** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| 组命名策略 | 使用基于前缀后缀的自定义阻止的单词。 | P1                                    |      待定     |
| 组分类 | 向团队分配分类。 | P1                                    |   待定        |
| 组来宾访问 | 允许或阻止向组添加来宾。 | 否                                    |  待定        |
| 组创建 | 将团队创建限制为管理员。 | 否                                    |   待定        |
| 组创建 | 将团队创建限制为安全组成员。 | P1                                    |     待定      |
| 组使用指南 | 设置链接将在所有组创建终结点上可见的组使用指南。 | P1                                    |   待定        |
| 隐藏成员身份 | 对不是组成员的用户隐藏 Microsoft 365 组的成员 | 否                                    |   待定        |
| 过期策略 | 通过设置过期策略来管理 Microsoft 365 组的生命周期。 | P1                                    |  待定        |
| 分组活动报告 | 深入了解组织中 Microsoft 365 组的活动，并查看创建和使用了多少个 Microsoft 365 组。 | 否                                    |    待定       |
| 保留策略 | 在安全 & 合规中心中为 Microsoft 365 组设置保留策略，以保留或删除特定时间段内的数据。 **注意：** 若要使用此功能，需要许可 Office 365 企业版 E3 或更高版本。 | 否                                    |    待定       |
| 数据丢失防护策略 | 在 Microsoft 365 组连接的网站中识别敏感信息，并防止意外共享。 **注意：** 若要使用此功能，需要许可 Office 365 企业版 E3 或更高版本。 | 否                                    |     待定      |
| 存档和还原 | 如果团队不再处于活动状态，但您想要将其保留为引用或在将来重新激活，请存档团队。 | 否                                    |   待定        |
| 访问评论 | 执行检查以有效管理内部和来宾用户的组成员身份 | 又                                    |   待定       |
| 使用条款 | 组织可用于向最终用户显示信息的简单方法。 此演示文稿确保用户可以看到相关免责声明以满足法律或合规性要求。 | P1                                    |         待定  |

