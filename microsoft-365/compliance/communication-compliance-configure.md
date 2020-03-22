---
title: 配置通信合规性
description: 设置通信合规性策略以配置员工通信以供审阅。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 5f105912c5163b69368683cd4c6eaebf96250e3c
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894827"
---
# <a name="configure-communication-compliance-in-microsoft-365"></a>在 Microsoft 365 中配置通信合规性

>[!IMPORTANT]
>本主题适用于在 Microsoft 365 订阅中配置通信合规性。 如果要为 Office 365 订阅配置监督策略，请参阅[configure 监督 For office 365](supervision-policies.md)。

使用通信合规性策略，以捕获内部或外部审阅者进行检查的员工通信。 有关通信合规性策略如何帮助您监视组织中的通信的详细信息，请参阅[Microsoft 365 中的通信合规性策略](communication-compliance.md)。

## <a name="before-you-begin"></a>准备工作

在开始进行通信合规性之前，应确认你的 Microsoft 365 订阅。 通信合规性策略中包含的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或者包含在 Office 365 企业版 E5 订阅中，或包含在 Microsoft365 E5 订阅。

如果您没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试使用内幕风险管理，则可以[将 microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)到现有的 Office 365 订阅中，或注册 Microsoft 365 企业版 e5 的[试用版](https://www.microsoft.com/microsoft-365/enterprise)。
  
完成以下步骤以设置和使用 Microsoft 365 组织中的通信合规性：

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>步骤1（必需）：启用通信合规性的权限

>[!Important]
>默认情况下，全局管理员不具有对通信合规性功能的访问权限。 在此步骤中分配的角色在所有通信合规性功能都可访问之前是必需的。

若要在 Microsoft 365 合规性中心中将**通信合规性**用作菜单选项，您必须分配有**监管审核管理员**角色。 您必须为具有**监管审核管理员**、**案例管理**、**合规性管理员**和**审阅**角色的审阅者创建新的角色组，以使用策略匹配来调查和修正邮件。

### <a name="create-a-new-role-group"></a>创建新的角色组

1. 在 Microsoft [https://protection.office.com/permissions](https://protection.office.com/permissions) 365 组织中使用管理员帐户的凭据进行登录。

2. 在 Microsoft Office 365 安全与合规中心中，转到 "**权限**"。 选择用于查看和管理 Office 365 中的角色的链接。

3. 选择“创建”****。

4. 在 "**名称**" 字段中，为新角色组指定一个友好名称。 选择“下一步”****。

5. 选择 "**选择角色**"，然后选择 "**添加**"。 选中 "**监察审核管理员**、**案例管理**、**合规性管理员**和**审阅**" 复选框，然后选择 "**添加**并**完成**"。 选择“下一步”****。

    ![满足通信合规性角色组](../media/communication-compliance-role-groups-1.png)

6. 选择 "**选择成员**"，然后选择 "**添加**"。 选中您想要创建策略的所有用户和组的复选框，并使用策略匹配来管理邮件，然后选择 "**添加**并**完成**"。 选择“下一步”****。

7. 选择 "**创建角色组**" 以完成。

有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。

## <a name="step-2-required-enable-the-office-365-audit-log"></a>步骤2（必需）：启用 Office 365 审核日志

通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。 审核日志是与定义的组织策略关联的所有活动的摘要，也是任何与通信合规性策略更改相关的活动。

有关启用审核的分步说明，请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。 启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。 您只需执行一次此操作。 有关使用审核日志的详细信息，请参阅[Search the audit log](search-the-audit-log-in-security-and-compliance.md)。


## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>步骤3（可选）：设置组以实现通信合规性

 创建通信合规性策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。 在策略中，您将使用电子邮件地址来标识个人或用户组。 为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。 如果使用的是组，可能需要多个。 例如，如果要监视两个不同的人员组之间的通信，或者要指定不受监督的组。

使用下图可帮助您为组织中的通信合规性策略配置组：

| **Policy 成员** | **支持的组** | **不受支持的组** |
|:-----|:-----|:-----|
|受监督用户 <br> 非监督用户 | 通讯组 <br> Office 365 组 | 动态通讯组 |
| Reviewers | 无 | 通讯组 <br> 动态通讯组 <br> 启用邮件功能的安全组 |
  
当您为受监督的用户选择 Office 365 组时，该策略将监视共享 Office 365 邮箱的内容以及与该组关联的 Microsoft 团队频道。 当您选择通讯组列表时，该策略将监视单个用户邮箱。

有关设置组的详细信息，请参阅：

- [创建和管理通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [管理启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Office 365 组概述](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-required-create-a-communication-compliance-policy"></a>步骤4（必需）：创建通信合规性策略
  
1. 在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。

2. 在 Microsoft 365 合规性中心中，选择 "**通信合规性**"。
  
3. 选择 "**策略**" 选项卡。

4. 选择 "**创建策略**"，从模板创建和配置新策略，或创建和配置自定义策略。

    如果选择策略模板来创建策略，您将：

    - 确认或更新策略名称。 一旦创建了策略，便无法更改策略名称。
    - 选择要监督的用户或组，包括选择要排除的用户或组。
    - 选择策略的审阅者。 审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。 所有审阅者都必须在 Exchange Online 上托管邮箱。 在这里添加的审阅者是在调查和修正工作流中上报通知时可供选择的审阅者。
    - 选择 "受限条件" 字段，通常是要应用于策略的敏感信息类型或关键字词典。

    如果您选择使用策略向导创建自定义策略，您将：

    - 为策略指定名称和说明。 一旦创建了策略，便无法更改策略名称。
    - 选择要监督的用户或组，包括组织中的所有用户、特定用户和组，或者要排除的其他用户和组。
    - 选择策略的审阅者。 审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。 所有审阅者都必须在 Exchange Online 上托管邮箱。
    - 选择要扫描的通信通道，包括 Exchange、Microsoft 团队或 Skype for Business。 如果您在 Microsoft 365 中配置了连接器，您还将选择扫描第三方源。
    - 选择要监视的通信方向，包括入站、出站或内部通信。
    - 定义通信合规性策略[条件](communication-compliance-feature-reference.md#ConditionalSettings)。 您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。
    - 选择是否要包含敏感信息类型。 在此步骤中，您可以选择默认和自定义的敏感信息类型。 从 "通信合规性策略向导" 中的现有自定义敏感信息类型或自定义关键字词典中进行选择。 如果需要，可以在运行向导之前创建这些项目。 您还可以在 "通信合规性策略" 向导中创建新的敏感信息类型。
    - 选择是否要启用冒犯性语言分类器。 此分类器检测在电子邮件正文中发送或接收的不正确语言。
    - 定义要查看的通信百分比。
    - 查看策略选择并创建策略。

5. 使用 "自定义策略" 向导时，选择 "使用模板或**提交**时**创建策略**"。

6. **您的策略已创建**页面将显示有关何时激活策略以及将捕获哪些通信的指南。

## <a name="step-5-optional-create-employee-notice-templates"></a>步骤5（可选）：创建员工通知模板

如果希望通过向关联的员工发送提醒通知来选择对策略警报做出响应，您需要在您的组织中至少创建一个通知模板。 在将 "通知模板" 字段作为警报修正过程的一部分发送并为每个通信合规性策略创建自定义的通知模板之前，这些字段都是可编辑的。

1. 在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。

2. 在 Microsoft 365 合规性中心中，转到 "**通信合规性**"。

3. 选择 "**通知模板**" 选项卡，然后选择 "**创建通知模板**"。

4. 在 "**修改通知模板**" 页上，填写下列字段：

    - 通知模板名称（必需）
    - 发件人（必需）
    - "抄送" 和 "密件抄送" （可选）
    - 主题（必需）
    - 邮件正文（必需）

5. 选择 "**保存**" 以创建并保存 "通知" 模板。

## <a name="step-6-optional-test-your-communication-compliance-policy"></a>步骤6（可选）：测试通信合规性策略

创建通信合规性策略后，最好对其进行测试，以确保策略正确地强制实施了您定义的条件。 如果通信合规性策略包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。 请确保为策略激活时间，以便捕获要测试的通信。

按照以下步骤测试您的通信合规性策略：

1. 打开电子邮件客户端或 Microsoft 团队，同时以您要测试的策略中定义的监督用户的身份登录。
2. 发送符合通信合规性策略中定义的条件的电子邮件或 Microsoft 团队聊天。 此测试可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。

    > [!NOTE]
    > 所有源通道中的通信可能需要长达24小时才能在策略中完全处理。

3. 以通信合规性策略中指定的审阅者的资格登录到 Microsoft 365。 导航到 "**通信合规性** > **警报**" 以查看策略的警报。

4. 使用修正控件修正警报，并验证是否正确解决了警报。
