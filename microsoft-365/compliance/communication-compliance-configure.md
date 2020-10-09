---
title: 通信合规性入门
description: 设置通信合规性策略以配置用户通信以供审阅。
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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 20f1a0cc38338bb054618726b5a399d237a979d2
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399497"
---
# <a name="get-started-with-communication-compliance"></a>通信合规性入门

使用通信合规性策略来确定内部或外部审阅者进行检查的用户通信。 有关通信合规性策略如何帮助您监视组织中的通信的详细信息，请参阅 [Microsoft 365 中的通信合规性策略](communication-compliance.md)。 如果您想要查看 Contoso 如何快速将通信合规性策略配置为在 Microsoft 团队、Exchange Online 和 Yammer 通信中监视攻击性语言，请查看此 [案例研究](communication-compliance-case-study.md)。

## <a name="before-you-begin"></a>准备工作

在开始进行通信合规性之前，应确认你的 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 和任何加载项。 若要访问和使用通信合规性，您的组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5 订阅 (付费或试用版) 
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规性加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 内幕人士风险管理加载项
- Microsoft 365 A5 订阅 (付费版或试用版) 
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规性加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 内幕成员风险管理加载项
- Microsoft 365 G5 订阅 (付费版或试用版) 
- Microsoft 365 G5 订阅 + Microsoft 365 G5 合规性附加
- Microsoft 365 G5 订阅 + Microsoft 365 G5 内幕版风险管理加载项
- Office 365 企业版 E5 订阅 (付费或试用版) 
- Office 365 企业版 E3 订阅 + Office 365 高级合规性外接程序 (不再可用于新订阅，请参阅 note) 

必须为通信合规性策略中包含的用户分配上述许可证之一。

>[!IMPORTANT]
>Office 365 高级合规性不再作为独立订阅销售。 当当前订阅过期时，客户应转换为上述订阅之一，其中包含相同或更多的合规性功能。

如果您没有现成的 Office 365 企业版 E5 计划，并且想要尝试使用内幕风险管理，则可以 [将 Microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 到现有订阅或注册 Office 365 企业版 e5 的 [试用版](https://www.microsoft.com/microsoft-365/enterprise) 。

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>步骤 1 (必需) ：启用通信合规性的权限

>[!Important]
>默认情况下，全局管理员不具有对通信合规性功能的访问权限。 在此步骤中分配的角色在所有通信合规性功能都可访问之前是必需的。 配置角色组后，最多可能需要30分钟的时间才能将角色组权限应用到组织中分配的用户。

有五个角色组用于配置管理通信合规性功能的权限。 为了使 **通信合规性** 在 Microsoft 365 合规性中心中可用作菜单选项，若要继续执行这些配置步骤，您必须分配给 *通信合规* 性管理员角色组或 *通信合规性管理员* 角色组。 若要在初始配置后访问和管理通信合规性功能，用户必须是至少一个通信合规性角色组的成员。

根据您想要管理通信策略和通知的方式，您需要将用户分配给特定角色组。 您可以选择将具有不同合规性职责的用户分配给特定角色组，以管理通信合规性功能的不同方面。 或者，您可以决定将指定管理员、分析师、调查人员和查看者的所有用户帐户分配给 *通信合规性* 角色组。 使用一个或多个角色组以最大限度地满足合规性管理要求。

配置通信合规性时从这些角色组选项中进行选择：

|**角色**|**角色权限**|
|:-----|:-----|
| **通信合规性** | 使用此角色组管理单个组中的组织的通信合规性。 通过添加指定管理员、分析师、调查人员和查看者的所有用户帐户，您可以在单个组中配置通信合规性权限。 此角色组包含所有通信合规性权限角色。 此配置是快速开始使用通信合规性的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。 |
| **通信合规性管理员** | 使用此角色组最初配置通信合规性和更高版本，以将通信合规性管理员与定义的组隔离。 分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。 分配到此角色组的用户无法查看邮件通知。 |
| **通信合规性分析师** | 使用此组可将权限分配给将充当通信合规性分析员的用户。 分配到此角色组的用户可以查看将其分配为审阅者的策略、查看邮件元数据 (不是邮件内容) 、升级到其他审阅者或向用户发送通知。 分析师无法解决待处理的警报。 |
| **通信合规调查人员** | 使用此组将权限分配给将充当通信合规性调查人员的用户。 分配到此角色组的用户可以查看邮件元数据和内容、升级到其他审阅者、升级到高级电子数据展示事例、向用户发送通知以及解决警报。 |
| **通信合规性查看器** | 使用此组可为将管理通信报告的用户分配权限。 分配到此角色组的用户可以访问通信合规性主页上的所有报告小部件，并且可以查看所有通信合规性报告。 |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>选项1：将所有合规性用户分配给通信合规性角色组

1. [https://protection.office.com/permissions](https://protection.office.com/permissions)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。

2. 在 "安全 &amp; 合规性中心" 中，转到 " **权限**"。 选择用于查看和管理 Office 365 中的角色的链接。

3. 选择 " *通信合规性* 角色组"，然后选择 " **编辑角色组**"。

4. 从左侧导航窗格中选择 " **选择成员** "，然后选择 " **编辑**"。

5. 选择 " **添加** "，然后选中要添加到 *通信合规性* 角色组的所有用户的复选框。

6. 选择 " **添加**"，然后选择 " **完成**"。

7. 选择 " **保存** " 将用户添加到角色组。 选择 " **关闭** " 完成步骤

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>选项2：将用户分配给特定的通信合规性角色组

使用此选项可将用户分配给特定角色组，以在组织中的不同用户之间分段通信合规性访问和责任。

1. [https://protection.office.com/permissions](https://protection.office.com/permissions)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。

2. 在 "安全 &amp; 合规性中心" 中，转到 " **权限**"。 选择用于查看和管理 Office 365 中的角色的链接。

3. 选择其中一个通信合规性角色组，然后选择 " **编辑角色组**"。

4. 从左侧导航窗格中选择 " **选择成员** "，然后选择 " **编辑**"。

5. 选择 " **添加** "，然后选中要添加到角色组的所有用户的复选框。

6. 选择 " **添加**"，然后选择 " **完成**"。

7. 选择 " **保存** " 将用户添加到角色组。

8. 选择 "下一个通信合规性角色组"，然后对每个所需的角色组重复步骤4-7。

9. 选择 " **关闭** " 完成这些步骤。

有关角色组和权限的详细信息，请参阅 [合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。

## <a name="step-2-required-enable-the-audit-log"></a>步骤 2 (必需) ：启用审核日志

通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。 审核日志是与定义的组织策略关联的所有活动的摘要，也是任何与通信合规性策略更改相关的活动。

有关启用审核的分步说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。 您只需执行一次此操作。 有关使用审核日志的详细信息，请参阅 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)。

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>步骤 3 (可选) ：为通信合规性设置组

 创建通信合规性策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。 在策略中，您将使用电子邮件地址来标识个人或用户组。 为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。 如果使用的是组，可能需要多个。 例如，如果要监视两个不同的人员组之间的通信，或者要指定不受监督的组。

使用下图可帮助您为组织中的通信合规性策略配置组：

| **Policy 成员** | **支持的组** | **不受支持的组** |
|:-----|:-----|:-----|
|受监督用户 <br> 非监督用户 | 通讯组 <br> Microsoft 365 组 | 动态通讯组 |
| Reviewers | 无 | 通讯组 <br> 动态通讯组 <br> 启用邮件功能的安全组 |
  
当您在策略中分配通讯组时，该策略将监视通讯组中每个用户的所有电子邮件。 当您在策略中分配 Microsoft 365 组时，该策略将监视发送到该组的所有电子邮件，而不是每个组成员收到的单个电子邮件。

如果您是具有 Exchange 本地部署或外部电子邮件提供商的组织，并且您要为用户监视 Microsoft 团队聊天，则必须为具有内部部署或外部邮箱的用户创建通讯组以进行监视。 在后面的这些步骤中，您将分配此通讯组作为策略向导中的受 **监督的用户和组** 选择。

>[!IMPORTANT]
>你必须向 Microsoft 支持人员提交请求，以使贵组织能够使用安全与合规中心中的图形用户界面来搜索本地用户的 Teams 聊天数据。 有关详细信息，请参阅针对 [本地用户搜索基于云的邮箱](search-cloud-based-mailboxes-for-on-premises-users.md)。

有关设置组的详细信息，请参阅：

- [创建和管理通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Microsoft 365 组概述](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>步骤 4 (可选) ：验证 Yammer 租户是否处于本机模式

在本机模式中，所有 Yammer 用户都在 Azure Active Directory (AAD) 中，所有组都是 Office 365 组，并且所有文件都存储在 SharePoint Online 中。 您的 Yammer 租户必须处于本机模式，以实现通信合规性策略，以扫描和识别 Yammer 中的私人邮件和社区对话中的有风险的对话。

有关在本机模式中配置 Yammer 的详细信息，请参阅：

- [Microsoft 365 中的 Yammer 本机模式概述](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [配置适用于 Microsoft 365 本机模式的 Yammer 网络](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>步骤 5 (必需) ：创建通信合规性策略
  
>[!Important]
>不支持使用 PowerShell 创建和管理通信合规性策略。 若要创建和管理这些策略，必须使用 [Microsoft 365 通信合规性解决方案](https://compliance.microsoft.com/supervisoryreview)中的策略管理控件。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。

2. 在 Microsoft 365 合规性中心中，选择 " **通信合规性**"。
  
3. 选择 " **策略** " 选项卡。

4. 选择 " **创建策略** "，从模板创建和配置新策略，或创建和配置自定义策略。

    如果选择策略模板来创建策略，您将：

    - 确认或更新策略名称。 一旦创建了策略，便无法更改策略名称。
    - 选择要监督的用户或组，包括选择要排除的用户或组。
    - 选择策略的审阅者。 审阅者是单个用户，并且所有审阅者都必须在 Exchange Online 上托管邮箱。 在这里添加的审阅者是在调查和修正工作流中上报通知时可供选择的审阅者。 将审阅者添加到策略时，他们将自动收到一封电子邮件，通知他们对策略的分配，并提供有关审阅过程的信息的链接。
    - 选择 "受限条件" 字段，通常是要应用于策略的敏感信息类型或关键字词典。

    如果您选择使用策略向导创建自定义策略，您将：

    - 为策略指定名称和说明。 一旦创建了策略，便无法更改策略名称。
    - 选择要监督的用户或组，包括组织中的所有用户、特定用户和组，或者要排除的其他用户和组。
    - 选择策略的审阅者。 审阅者是单个用户，并且所有审阅者都必须在 Exchange Online 上托管邮箱。 在这里添加的审阅者是在调查和修正工作流中上报通知时可供选择的审阅者。 将审阅者添加到策略时，他们将自动收到一封电子邮件，通知他们对策略的分配，并提供有关审阅过程的信息的链接。
    - 选择要扫描的通信通道，包括 Exchange、Microsoft 团队、Yammer 或 Skype for Business。 如果您在 Microsoft 365 中配置了连接器，您还将选择扫描第三方源。
    - 选择要监视的通信方向，包括入站、出站或内部通信。
    - 定义通信合规性策略 [条件](communication-compliance-feature-reference.md#ConditionalSettings)。 您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。
    - 选择是否要包含敏感信息类型。 在此步骤中，您可以选择默认和自定义的敏感信息类型。 从 "通信合规性策略向导" 中的现有自定义敏感信息类型或自定义关键字词典中进行选择。 如果需要，可以在运行向导之前创建这些项目。 您还可以在 "通信合规性策略" 向导中创建新的敏感信息类型。
    - 选择是否要启用分类器。 分类器可以检测在电子邮件正文或其他类型的文本中发送或接收的不正确的语言和图像。 您可以选择以下内置分类符： *威胁*、 *猥亵*、 *目标骚扰*、 *成人图像*、 *Racy 图像*和 *Gory 图像*。

    >[!CAUTION]
    >我们正在弃用**冒犯性语言**内置分类器，因为它会生成大量误报。 请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。 建议改为使用 **威胁**、 **猥亵**和 **目标骚扰** 内置分类符。

    - 定义要查看的通信百分比。
    - 查看策略选择并创建策略。

5. 使用 "自定义策略" 向导时，选择 "使用模板或**提交**时**创建策略**"。

6. **您的策略已创建**页面将显示有关何时激活策略以及将捕获哪些通信的指南。

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>步骤 6 (可选) ：创建通知模板和配置用户 anonymization

如果希望通过向关联用户发送提醒通知来选择对策略警报做出响应，您需要在组织中至少创建一个通知模板。 在将 "通知模板" 字段作为警报修正过程的一部分发送并为每个通信合规性策略创建自定义的通知模板之前，这些字段都是可编辑的。

您还可以选择在调查策略匹配和对邮件采取操作时为显示的用户名启用 anonymization。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。

2. 在 Microsoft 365 合规性中心中，转到 " **通信合规性**"。

3. 若要为用户名配置 anonymization，请选择 " **隐私** " 选项卡。

4. 若要启用 anonymization，请选择 " **显示匿名版本的用户名**"。

5. 选择“**保存**”。

6. 导航到 " **通知模板** " 选项卡，然后选择 " **创建通知模板**"。

7. 在 " **修改通知模板** " 页上，填写下列字段：

    - 模板名称 (必需) 
    -  (必需的发送) 
    - "抄送" 和 "密件抄送" (可选) 
    - 必需的主题 () 
    - 邮件正文 (必需的) 

8. 选择 " **保存** " 以创建并保存 "通知" 模板。

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>第7步 (可选) ：测试通信合规性策略

创建通信合规性策略后，最好对其进行测试，以确保策略正确地强制实施了您定义的条件。 如果通信合规性策略包含敏感信息类型，您可能还需要 [测试您的数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md) 。 请确保为策略激活时间，以便捕获要测试的通信。

按照以下步骤测试您的通信合规性策略：

1. 在以要测试的策略中定义的受监督用户身份登录时，打开电子邮件客户端、Microsoft 团队或 Yammer。
2. 发送符合您在通信合规性策略中定义的条件的电子邮件、Microsoft 团队聊天或 Yammer 邮件。 此测试可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。

    > [!NOTE]
    > 所有源通道中的通信可能需要长达24小时才能在策略中完全处理。

3. 以通信合规性策略中指定的审阅者的资格登录到 Microsoft 365。 导航到 "**通信合规性**  >  **警报**" 以查看策略的警报。

4. 使用修正控件修正警报，并验证是否正确解决了警报。

## <a name="next-steps"></a>后续步骤

完成这些步骤以创建您的第一个通信合规性策略后，您将在大约24小时后开始接收来自活动指示器的警报。 根据需要使用本文步骤5中的指导配置其他策略。

若要了解有关调查通信合规性警报的详细信息，请参阅 [调查和修正通信合规性警报](communication-compliance-investigate-remediate.md)。
