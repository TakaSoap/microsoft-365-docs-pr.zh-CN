---
title: 通信合规性入门
description: 设置通信合规性策略，以配置用户用户通信以供审阅。
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: da06544eaf6f994605189948d771c602dda2c66f
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60787150"
---
# <a name="get-started-with-communication-compliance"></a>通信合规性入门

使用通信合规性策略，以识别用户通信，供内部或外部审阅者检查。 有关通信合规性策略如何帮助监视组织内通信的详细信息，请参阅 [Microsoft 365 中的通信合规性策略](communication-compliance.md)。 如果您想查看 Contoso 如何快速配置通信合规性策略，以监视 Microsoft Teams、Exchange Online 和 Yammer 通信中的不当内容，请查看此[案例研究](communication-compliance-case-study.md)。

## <a name="subscriptions-and-licensing"></a>订阅和许可

在开始通信合规性入门之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 以及任何加载项。 若要访问和使用通信合规性，组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5 订阅（付费或试用版本）
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规加载项
- Microsoft 365 E3 订阅 + Microsoft 365 E5 预览体验成员风险管理加载项
- Microsoft 365 A5 订阅（付费或试用版本）
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规加载项
- Microsoft 365 A3 订阅 + Microsoft 365 A5 预览体验成员风险管理加载项
- Microsoft 365 G5 订阅（付费或试用版本）
- Microsoft 365 G5 订阅 + Microsoft 365 G5 合规加载项
- Microsoft 365 G5 订阅 + Microsoft 365 G5 预览体验成员风险管理加载项
- Office 365 企业版 E5 订阅（付费或试用版本）
- Office 365 A5 订阅（付费或试用版本）
- Office 365 企业版 E3 订阅 + Office 365 高级合规版加载项（新订阅已不再可用，请参阅注释）

通信合规性策略中包括的用户必须获得以上许可证之一。

> [!IMPORTANT]
> Office 365 高级合规版已不再作为独立订阅销售。 当前订阅到期后，客户应过渡到以上订阅之一，其中包含了相同的或其它合规性功能。

如果你没有现有的 Office 365 企业版 E5 套餐，并且想要尝试通信合规性，可以 [添加 Microsoft 365](/office365/admin/try-or-buy-microsoft-365) 到现有订阅，或 [注册试用](https://www.microsoft.com/microsoft-365/enterprise) Office 365 企业版 E5。

## <a name="recommended-actions-preview"></a>建议 (预览) 

建议的操作可帮助组织充分使用通信合规性功能和现有策略。 建议的操作 **包含在"概述** "页上，可提供见解并汇总组织中通信中的敏感信息类型和不适当的内容活动。

![通信合规性建议操作。](../media/communication-compliance-recommended-actions.png)

包含不当内容的邮件中的活动按分类器类型从使用不当内容模板的现有策略或使用分类器处理不当内容的自定义策略中枚举。 调查策略警报仪表板上这些消息的警报。

现有策略涵盖的邮件以及现有策略未涵盖的邮件中检测到涉及敏感信息类型的活动。 Insights所有敏感信息类型，包括组织之前未在现有通信合规性策略中定义的敏感信息类型。 使用这些见解创建新的通信合规性策略或更新现有策略。

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>步骤 1（必选）：启用通信合规性权限

> [!IMPORTANT]
> 默认状态下，全局管理员没有对通信合规性功能的访问权限。 在可以访问任何通信合规性功能之前，必须在此步骤中分配角色。 配置角色组之后，可能需要长达 30 分钟时间将角色组权限应用到整个组织的已分配用户。

共有 5 个角色组，用于配置权限以管理通信合规性功能。 若要在 Microsoft 365 合规中心中将 **通信合规性** 作为菜单选项提供并继续执行这些配置步骤，必须将你分配给 *通信符合性* 或 *通信符合性管理员* 角色组。 若要在初始配置后访问和管理通信合规性功能，用户必须是至少一个通信合规性角色组的成员。

根据希望管理通信策略和警报的方式，你需要将用户分配到特定的角色组。 可以选择将具有不同合规性职责的用户分配给特定的角色组，以管理不同区域的通信合规性功能。 或者可以决定将指定管理员、分析者、调查者和查看者的所有用户账户分配到 *通信合规性* 角色组。 使用单个角色组或多个角色组，以充分符合你的合规性管理要求。

配置通信合规性时，请从这些角色组中进行选择：

| 角色 | 角色权限 |
|:-----|:-----|
| **通信合规性** | 使用此角色组在单个组中管理组织的通信合规性。 通过添加指定管理员、分析者、调查者和查看者的所有用户账户，可以在单个组中配置通信合规性权限。 此角色组包含所有通信合规性权限角色。 这一配置是通信合规性快速入门的最简单方式，非常适合不需要为单独用户组定义单独权限的组织。 |
| **通信合规性管理员** | 使用此角色组进行通信合规性初始配置，后期可将通信合规性管理员隔离到已定义组中。 分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。 分配到此角色组的用户无法查看消息警报。 |
| **通信合规性分析者** | 使用此组向执行通信合规性分析者操作的用户分配权限。 分配到此角色组的用户可以查看分配其为审阅者的策略，查看消息元数据（而不是消息内容）、升级到其他审阅者，或向用户发送通知。 分析者不能解决挂起的警报。 |
| **通信合规性调查者** | 使用此组向执行通信合规性调查者操作的用户分配权限。 分配到此角色组的用户可以查看消息元数据和内容、升级到其他审阅者、升级到高级 eDiscovery 案例、向用户发送通知、以及解决警报。 |
| **通信合规性查看者** | 使用此组向管理通信报告的用户分配权限。 分配到此角色组的用户可以访问通信合规性主页上的所有报告小组件，并且可以查看所有通信合规性报告。 |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>选项 1： 将所有合规用户分配到通信合规性角色组

1. 使用 Microsoft 365 组织中的管理员账户凭据登录 [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions)。

2. 在安全 &amp; 合规中心中，转到“**权限**”。 选择链接以查看和管理 Office 365 中的角色。

3. 选择“*通信合规性*”角色组，然后选择“**编辑角色组**”。

4. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。

5. 选择“**添加**”，然后选中希望添加到 *通信合规性* 角色组的所有用户的复选框。

6. 选择“**添加**”，然后选择“**完成**”。

7. 选择“**保存**”以将用户添加到角色组。 选择“**关闭**”以完成步骤

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>选项 2： 将用户分配到特定通信合规性角色组

使用此选项将用户分配到特定角色组，以区分组织中不同用户的通信合规性访问和职责。

1. 使用 Microsoft 365 合规中心 组织中管理员帐户的凭据登录 Microsoft 365，然后转到"<a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**权限"。**</a>

2. 选择链接以查看和管理 Office 365 中的角色。

3. 选择通信合规性角色组之一，然后选择“**编辑角色组**”。

4. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。

5. 选择“**添加**”，然后选中希望添加到角色组的所有用户的复选框。

6. 选择“**添加**”，然后选择“**完成**”。

7. 选择“**保存**”以将用户添加到角色组。

8. 选择下一个通信合规性角色组，然后为每个需要的角色组重复步骤 4-7。

9. 选择“**关闭**”以完成步骤。

有关角色组和权限的详细信息，请参阅 [合规中心中的权限](../security/office-365-security/protect-against-threats.md)。

## <a name="step-2-required-enable-the-audit-log"></a>步骤 2（必选）：启用审核日志

通信合规性需要审核日志显示警报和跟踪审阅者采取的修正操作。 审核日志是与已定义的组织策略，或任何时刻的通信合规性策略更改相关联的所有活动摘要。

默认情况下，为Microsoft 365启用审核。 某些组织可能由于特定原因禁用了审核。 如果为组织禁用了审核，这可能是因为另一个管理员已将其关闭。 我们建议确认在完成此步骤时可以重新启用审核。

有关启用审核的逐步操作说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 打开审核之后，将显示一条消息，内容为正在准备审核日志，你可以在准备完成后几个小时内运行搜索。 此操作只需要执行一次。 有关使用审核日志的详细信息，请参阅 [搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>步骤 3（可选）：设置通信合规性组

 创建通信合规性策略时，即定义了要审阅谁的通信和谁来执行审阅。 在策略中，可以使用电子邮件地址来标识个人或人员组。 若要简化设置，可以为接受通信审阅的人员创建组，也可以为审阅这些通信的人员创建组。 如果正在使用组，可能需要若干个组。 例如，如果希望监视两个不同组人员之间的通信，或如果希望指定一个不会受到监督的组。

使用下图帮助配置组织中的组以实施通信合规性策略：

| **策略成员** | **支持的组** | **不支持的组** |
|:-----|:-----|:-----|
|受监督用户 <br> 已排除用户 | 通讯组 <br> Microsoft 365 组 | 动态通讯组 <br> 嵌套通讯组 <br> 启用邮件的安全组 <br> Microsoft 365动态成员身份的组 |
| 审阅者 | 无 | 通讯组 <br> 动态通讯组 <br> 嵌套通讯组 <br> 启用邮件的安全组 |

在策略中分配通讯组时，策略会监视通讯组每个用户的所有电子邮件和 Teams 聊天。 在策略中分配 Microsoft 365 组时，策略会监视发送到该组的所有电子邮件和 Teams 聊天，而不是每个团队成员收到的单个电子邮件和聊天。

如果你是具有 Exchange 本地部署或外部电子邮件提供商的组织，并且想要监视用户的 Microsoft Teams 聊天，则必须创建一个通讯组以便具有本地或外部邮箱的用户进行监视。 在这些步骤的稍后部分，你将此通讯组分配为策略向导中的 **受监督用户和组**。 有关为本地用户启用基于云的存储和 Teams 支持的要求和限制，请参阅 Search for Teams chat data for [on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md)。

若要在大型企业组织中管理受监督的用户，可能需要监视大型组的所有用户。 可使用 PowerShell 为已分配组配置全局通信合规性策略的通讯组。 这样，可以使用一个策略监视成千上万个用户，并在新员工加入组织时保持通信合规性策略的更新。

1. 为全局通信合规性策略创建一个专用的 [通讯组](/powershell/module/exchange/new-distributiongroup)，该策略具有以下属性：确保此通讯组未用于其他目的或其他 Office 365 服务。

    - **MemberDepartRestriction = Closed**。 确保用户无法将自己从通讯组中删除。
    - **MemberJoinRestriction = Closed**。 确保用户无法将自己添加到通讯组。
    - **ModerationEnabled = True**。 确保发送到此组的所有邮件都受制于审批，并且组未用于在通信合规性策略配置外部进行通信。

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 选择未使用的 [Exchange 自定义属性](/Exchange/recipients/mailbox-custom-attributes) 以跟踪添加到组织内通信合规性策略的用户。

3. 按定期计划运行以下 PowerShell 脚本，将用户添加到通信合规性策略：

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

- [创建和管理通讯组](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Microsoft 365 组概述](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>步骤 4（可选）：验证 Yammer 租户是否处于本机模式

在本机模式下，所有 Yammer 用户都在 Azure Active Directory (Azure AD) 中，所有组都是 Office 365 组，并且所有文件都存储在 SharePoint Online 中。 你的 Yammer 租户必须为本机模式，以便通信合规性策略可以扫描和识别 Yammer 中私人消息和社区对话中的风险对话。

有关以本机模式配置 Yammer 详细信息，请参阅：

- [Microsoft 365 中 Yammer 本机模式概述](/yammer/configure-your-yammer-network/overview-native-mode)
- [配置适用于 Microsoft 365 本机模式的 Yammer 网络](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>步骤 5（必需）：创建通信合规性策略

>[!IMPORTANT]
>不支持使用 PowerShell 创建和管理通信合规性策略。 若要创建和管理这些策略，必须使用 [Microsoft 365 通信合规性解决方案](https://compliance.microsoft.com/supervisoryreview) 中的策略管理控件。

>[!TIP]  
>想要查看有关设置新通信合规性策略和修正警报的深入演练？ 观看 [此 15](communication-compliance-plan.md#creating-a-communication-compliance-policy-walkthrough) 分钟的视频，了解通信合规性策略如何帮助您检测不恰当的消息、调查潜在的违反和修正合规性问题。

1. 使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心组织中</a>管理员帐户的凭据登录Microsoft 365帐户。

2. 在 Microsoft 365 合规中心中，选择“**通信合规性**”。

3. 选择“**策略**”选项卡。

4. 选择“**创建策略**”从模板创建和配置新策略，或创建和配置自定义策略。

    如果选择策略模板来创建策略，将需要：

    - 确认或更新策略名称。 创建策略后，不能更改策略名称。

    - 选择要监督的用户或组，包括选择要排除的用户或组。 使用利益冲突模板时，需要选择两个组或两个用户来进行内部通信监视。

    - 选择该策略的审阅者。 审阅者是单个用户，所有审阅者都必须拥有在 Exchange Online 上托管的邮箱。 此处添加的审阅者是可在调查和修正工作流中升级警报时选择的审阅者。 审阅者添加到策略时，他们会自动收到一封电子邮件，通知他们分配到此策略，并提供有关审阅过程的信息的链接。

    - 选择有限条件字段，通常是要应用于该策略的敏感信息类型或关键字词典。

    > [!NOTE]
    > 如果要启用光学字符识别 [ (OCR)](communication-compliance-policies.md#optical-character-recognition-ocr)以扫描邮件中嵌入或附加的图像，以找到符合策略条件的打印或手写文本，请选择"自定义策略条件和百分比"，并启用"从图像中提取打印或  >  **手写** 文本"进行评估。

    如果选择使用策略向导创建自定义策略，将需要：

    - 为策略指定名称和说明。 创建策略后，无法更改策略名称。

    - 选择要监视的用户或组，包括你组织中所有用户、特定用户和组，或者希望排除的其他用户和组。

    - 选择该策略的审阅者。 审阅者是单个用户，所有审阅者都必须拥有在 Exchange Online 上托管的邮箱。 此处添加的审阅者是可在调查和修正工作流中升级警报时选择的审阅者。 审阅者添加到策略时，他们会自动收到一封电子邮件，通知他们分配到此策略，并提供有关审阅过程的信息的链接。

    - 选择要扫描的信道，包括 Exchange、Microsoft Teams、Yammer 或 Skype for Business。 如果在 Microsoft 365 中配置了连接器，还可选择扫描第三方源。

    - 选择要监视的通信方向，包括入站、出站或内部通信。

    - 定义通信合规性策略 [条件](communication-compliance-policies.md#ConditionalSettings)。 可以从邮件地址、关键字、文件类型和大小匹配条件中进行选择。

    - 选择是否希望包含敏感信息类型。 此步骤可用于选择默认和自定义敏感信息类型。 在通信合规性策略向导中，从现有自定义敏感信息类型或自定义关键字词典进行选取。 如果需要，可在运行向导前创建这些项目。 还可从通信合规性策略向导中创建新的敏感信息类型。

    - 选择是否启用分类器。 分类器可以检测电子邮件正文或其他类型的文本中发送或接收的不当语言和图像。 可选择以下内置分类器： *威胁*、*猥亵*、*有针对性的骚扰*、*成人图像*、*色情图像* 和 *血腥图像*。

    - 启用 [光学字符识别 (OCR ](communication-compliance-policies.md#optical-character-recognition-ocr)) 扫描邮件中嵌入或附加的图像，以找到符合策略条件的打印或手写文本。 对于自定义策略，必须在策略中配置一个或多个与文本、关键字、分类器或敏感信息类型关联的条件设置，以允许选择光学字符识别扫描。

    - 定义要审阅的通信的百分比。

    - 查看策略选择并创建策略。

5. 使用模板时选择“**创建策略**”，或者使用自定义策略向导时选择“**提交**”。

6. 将显示 **策略已创建** 页面，其中将包含有关何时激活策略以及捕获哪些通信的准则。

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>步骤 6（可选）：创建通知模板并配置用户匿名处理

如果要选择通过向关联用户发送提醒通知来响应策略警报，你需要在组织中至少创建一个通知模板。 通知模板字段在作为警报修正过程的一部分发送之前可编辑，建议为每条通信合规性策略创建自定义通知模板。

当调查策略匹配并针对邮件采取措施时，还可以选择对显示用户名启用匿名处理。

1. 使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心组织中</a>管理员帐户的凭据登录Microsoft 365帐户。

2. 在 Microsoft 365 合规中心中，转到“**通信合规性**”。

3. 若要配置用户名的匿名处理，请选择“**隐私**”选项卡。

4. 若要启用匿名处理，请选择“**显示用户名的匿名版本**”。

5. 选择“**保存**”。

6. 导航到“**通知模板**”选项卡，然后选择“**创建通知模板**”。

7. 在 **修改通知模板** 页面，完成以下字段：

    - 模板名称（必需）
    - 发送自（必需）
    - 抄送和密件抄送（可选）
    - 主题（必需）
    - 邮件正文（必需）

8. 选择“**另存为**” ，以创建并保存通知模板。

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>步骤 7（可选）：测试通信合规性策略

创建通信合规性策略后，建议进行测试，以确保已定义的条件已由策略正确强制执行。 如果通信合规性策略包含敏感信息类型，也可以 [测试数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md)。 请务必为策略提供激活时间，以便捕获要测试的通信。

请按照以下步骤测试通信合规性策略：

1. 以要测试的策略中定义的受监督用户登录时，打开电子邮件客户端、Microsoft Teams 或 Yammer。

2. 发送电子邮件、Microsoft Teams 聊天或 Yammer 消息，这些内容需要满足通信合规性策略中定义的条件。 此测试可以是关键字、附件大小、域等。请确保确定策略中已配置的条件设置是否过于严格或过于宽松。

    > [!NOTE]
    > 在策略中完全处理电子邮件可能需要 24 小时。 Microsoft Teams、Yammer 和第三方平台中的通信可能需要长达 48 小时才能完全执行策略处理。

3. 作为通信合规性策略中指定的审阅者登录到 Microsoft 365。 导航到“**通信合规性**” > “**警报**”以查看策略的警报。

4. 使用修正控件修正警报，并验证警报是否正确解决。

## <a name="next-steps"></a>后续步骤

完成这些步骤以创建第一个通信合规性策略后，将在 24-48 小时之后开始从活动指标接收警报。 使用本文中步骤 5 中的指南，根据需要配置其他策略。

若要深入了解如何调查通信合规性警报，请参阅 [调查并修正通信合规性警报](communication-compliance-investigate-remediate.md)。
