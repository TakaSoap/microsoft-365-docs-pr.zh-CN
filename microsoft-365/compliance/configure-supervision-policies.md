---
title: 配置监督策略
description: 为 Office 365 配置通信监督
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
titleSuffix: Office 365 Compliance
ms.openlocfilehash: c13e481cfc55e56d8cc1c0a772f2f661992f5353
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921454"
---
# <a name="configure-supervision-policies-in-office-365"></a>在 Office 365 中配置监督策略

>[!IMPORTANT]
>在 Microsoft 365 年 2 2020 月的兼容性符合通信合规性的情况下，将停用 Office 365 中的监督。 监督策略将不再可用于创建，并且最终会在一段较长的只读访问期后删除策略。
>
>如果您使用监督，请注意：
>
>- 从2020年6月15日起，租户将不能创建新的监察策略。
>- 2020年8月31日开始，现有策略将停止捕获新邮件。
>- 在10月26日开始，2020，将删除现有策略。
>
>我们积极鼓励当前正在探索或使用 Office 365 中的监督的客户使用新的[通信合规性](communication-compliance.md)解决方案，以通过一组更丰富的智能功能来满足您的通信监视或管理法规要求。

使用监督策略来捕获由内部或外部审阅者进行检查的员工通信。 有关监察策略如何帮助您监视组织中的通信的详细信息，请参阅[Office 365 中的监察策略](supervision-policies.md)。

>[!NOTE]
>监督策略监视的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或者包含在 Office 365 企业版 E5 订阅中，或者包含在 Microsoft 365 E5 订阅中。
>如果你没有现有的企业版 E5 计划，并且想要尝试监督，则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
按照以下步骤在组织中设置和使用监督：
  
- **步骤1（可选）**：[为监督设置组](#step-1-set-up-groups-for-supervision-optional)

    在开始使用监察策略之前，请确定哪些用户需要查看通信以及谁执行了检查。 如果您只想开始几个用户来了解监督工作的工作方式，则可以跳过 "立即" 设置组。

- **步骤2（必需）**：[让监督在你的组织中可用](#step-2-make-supervision-available-in-your-organization-required)

    将自己添加到监管审核角色组，以便您可以设置策略。 分配此角色的任何人都可以访问安全 & 合规性中心内的**监督**页面。 如果 reviewable 电子邮件托管在 Exchange Online 中，则每个审阅者都必须具有[对 Exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。

- **步骤3（可选）**：[创建自定义敏感信息类型和自定义关键字词典](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    如果您需要针对监督策略的自定义敏感信息类型或自定义关键字词典，则需要在启动监督向导之前创建它。

- **步骤4（必需）**：[设置监督策略](#step-4-set-up-a-supervision-policy-required)

    在安全 & 合规性中心创建监督策略。 这些策略定义哪些通信将在组织中进行审核，并指定执行审阅的用户。 通信包括电子邮件和 Microsoft 团队通信，以及第三方平台通信（如 Facebook、Twitter 等）。 在 Microsoft 365 订阅的通信监督中不支持在组织中创建的监督策略。

- **步骤5（可选）**：[测试通信监督策略](#step-5-test-your-supervision-policy-optional)

    测试您的监督策略以确保其按预期工作。 一定要确保符合性策略满足您的标准。

## <a name="step-1-set-up-groups-for-supervision-optional"></a>步骤1：设置组以进行监控（可选）

 在创建监督策略时，您需要定义哪些用户扫描了其通信，以及谁执行了审阅。 在策略中，您将使用电子邮件地址来标识个人或用户组。 为简化您的设置，您可以为已扫描其通信的用户创建组，并为查看这些通信的用户分组。 如果使用的是组，可能需要多个。 例如，您想要监视两个不同的人员组之间的通信，或者如果您想要指定一个不受监督的组。

使用下图可帮助您为组织中的通信监督策略配置组：

| **Policy 成员** | **支持的组** | **不受支持的组** |
|:-----|:-----|:-----|
|受监督用户 <br> 非监督用户 | 通讯组 <br> Microsoft 365 组 | 动态通讯组 |
| Reviewers | 启用邮件的安全组  | 通讯组 <br> 动态通讯组 |
  
当您为受监督的用户选择 Microsoft 365 组时，该策略将监视共享邮箱的内容以及与该组关联的 Microsoft 团队频道。 当您选择通讯组列表时，该策略将监视单个用户邮箱。

若要在大型企业组织中管理受监督的用户，您可能需要监视跨大型组的所有用户。 您可以使用 PowerShell 为分配的组配置全局监督策略的通讯组。 这使您可以使用单个策略监视数千个用户，并在新员工加入您的组织时保持监督策略的更新。

1. 为具有以下属性的全局监督策略创建专用[通讯组](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)：确保此通讯组不用于其他目的或其他 Office 365 服务。

    - **MemberDepartRestriction = 已关闭**。 确保用户无法将自己从通讯组中删除。
    - **MemberJoinRestriction = 已关闭**。 确保用户无法将自己添加到通讯组。
    - **ModerationEnabled = True**。 确保发送到此组的所有邮件均可供审批，并且该组未用于在监督策略配置外部进行通信。

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 选择一个未使用的[Exchange 自定义属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)来跟踪添加到组织中的监督策略的用户。

3. 定期对计划运行以下 PowerShell 脚本，以将用户添加到监督策略：

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

有关设置组的详细信息，请参阅：

- [创建和管理通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [管理启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Microsoft 365 组概述](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>步骤2：让监督在你的组织中可用（必需）

若要在安全 & 合规性中心中将**监察**功能作为菜单选项提供，您必须分配有监管审核管理员角色。
  
若要执行此操作，您可以将自己添加为监管审核角色组的成员，也可以创建角色组。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>将成员添加到监管审核角色组

1. 在组织[https://protection.office.com](https://protection.office.com)中使用管理员帐户的凭据进行登录。

2. 在安全 & 合规性中心中，转到 "**权限**"。

3. 选择 "**监管审核**" 角色组，然后单击 "编辑" 图标。

4. 在 "**成员**" 部分，添加要为组织管理通信监督的人员。

### <a name="create-a-new-role-group"></a>创建新的角色组

1. 在组织[https://protection.office.com/permissions](https://protection.office.com/permissions)中使用管理员帐户的凭据进行登录。

2. 在安全 & 合规性中心中，转到 "**权限**"，然后**+** 单击 "添加" （）。

3. 在 "**角色**" 部分中，单击**+**"添加" （），然后向下滚动到 "**监察审核管理员**"。 将此角色添加到角色组。

4. 在 "**成员**" 部分，添加要为组织管理通信监督的人员。

有关角色组和权限的详细信息，请参阅[合规性中心中的权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>为审阅者启用远程 PowerShell 访问（如果 Exchange Online 上托管电子邮件）

1. 按照[启用或禁用对 Exchange Online PowerShell 的访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导进行操作。

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>步骤3：创建自定义敏感信息类型和自定义关键字词典（可选）

若要从监督策略向导中的现有自定义敏感信息类型或自定义关键字词典中进行选择，需要先创建这些项目。

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>创建自定义关键字词典/词典（可选）

使用文本编辑器（如记事本）创建一个文件，其中包含要在监督策略中监视的关键字术语。 确保每个术语都位于单独的行中，并将文件保存为**Unicode/UTF-16 （小 Endian）** 格式。

### <a name="create-custom-sensitive-information-types"></a>创建自定义敏感信息类型

1. 创建新的敏感信息类型，并将您的自定义词典添加到安全 & 合规性中心。 导航到 "**分类** \> " "**敏感信息**类型"，然后按照新的 "**敏感信息类型" 向导**中的步骤操作。 你将在此处执行以下操作：

    - 定义敏感信息类型的名称和说明
    - 定义邻近度、置信度和主要模式元素
    - 将自定义词典作为匹配元素的要求导入
    - 查看您的选择并创建敏感信息类型

    有关更多详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)和[创建关键字词典](create-a-keyword-dictionary.md)

    创建自定义词典/词典之后，可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 查看配置的关键字，也可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet 添加和删除术语。

## <a name="step-4-set-up-a-supervision-policy-required"></a>步骤4：设置监督策略（必需）
  
1. 在组织[https://protection.office.com](https://protection.office.com)中使用管理员帐户的凭据进行登录。

2. 在安全 & 合规性中心中，选择 "**监督**"。
  
3. 选择 "**创建**"，然后按照向导设置策略配置。 使用该向导，您将：

    - 为策略指定名称和说明。
    - 选择要监督的用户或组，包括选择要排除的用户或组。
    - 定义监督策略[条件](supervision-policies.md#ConditionalSettings)。 您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。
    - 选择是否要包含敏感信息类型。 你可以在此处选择默认和自定义敏感信息类型。
    - 选择是否要启用冒犯性语言模型。 这将检测在电子邮件正文中发送或接收的不正确的语言。
    - 定义要查看的通信百分比。
    - 选择策略的审阅者。 审阅者可以是单个用户，也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。 所有审阅者都必须在 Exchange Online 上托管邮箱。
    - 查看策略选择并创建策略。

## <a name="step-5-test-your-supervision-policy-optional"></a>步骤5：测试监督策略（可选）

创建通信监督策略后，最好进行测试以确保策略正确地实施了您定义的条件。 如果监督策略中包含敏感信息类型，您可能还需要[测试数据丢失防护（DLP）策略](create-test-tune-dlp-policy.md)。 按照以下步骤测试您的监督策略：

1. 打开以您要测试的策略中定义的监督用户身份登录的电子邮件客户端或 Microsoft 团队。
2. 发送符合您在监督策略中定义的条件的电子邮件或 Microsoft 团队聊天。 它可以是关键字、附件大小、域等。确保您确定策略中配置的条件设置过于严格或太 lenient。

    >[!NOTE]
    >已定义策略的电子邮件将在接近实时的情况中进行处理，并且可以在配置策略后立即进行测试。 Microsoft 团队中的聊天可能需要长达24小时才能在策略中完全处理。 

3. 以通信监督策略中指定的审阅者的形式登录 Microsoft 365。 导航到 "**监控** > "*您的自定义策略* > **打开**以查看该策略的报告。

