---
title: 数据丢失防护和 Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams聊天和频道支持数据丢失防护 (DLP) 策略。
ms.openlocfilehash: 66d451e55d5ee41abb0d43927e56295261bd4c8f
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786058"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>数据丢失防护和 Microsoft Teams

如果您的组织具有 DLP (数据丢失) ，您可以定义防止用户共享 Microsoft Teams 频道或聊天会话中敏感信息的策略。 以下是此保护工作方式的一些示例：

- **示例 1：保护邮件中的敏感信息**。 假设有人尝试在来宾聊天或频道中Teams与外部用户 (敏感信息) 。 如果已定义 DLP 策略以防止出现此情况，则包含发送给外部用户的敏感信息的邮件将被删除。 根据 DLP 策略的配置方式，这会自动发生，且在数秒钟内发生。

    > [!NOTE]
    > 与Microsoft Teams的用户共享时，用于Microsoft Teams DLP 会阻止敏感内容：<br/>- [团队和](/MicrosoftTeams/guest-access) 频道中的来宾访问;或<br/>- [会议和](/MicrosoftTeams/manage-external-access) 聊天会话中的外部访问。 <p>外部聊天会话的 DLP 仅在发送方和接收方均在仅Teams且使用本地联盟Microsoft Teams[才能工作](/microsoftteams/manage-external-access)。 DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.

- **示例 2：保护文档中的敏感信息**。 假设有人尝试在频道或聊天中与来宾共享Microsoft Teams，并且该文档包含敏感信息。 如果已定义 DLP 策略以防止出现此状态，文档将不会为这些用户打开。 DLP 策略必须包含 SharePoint 和 OneDrive，才能实施保护。 这是 SharePoint DLP 的一个示例，显示在 Microsoft Teams 中，因此要求用户获得 Office 365 DLP (Office 365 E3) 中的许可，但不需要用户获得 Office 365 高级合规版.) 

## <a name="dlp-licensing-for-microsoft-teams"></a>DLP 许可Microsoft Teams

[数据丢失防护](dlp-learn-about-dlp.md)功能已扩展为包括Microsoft Teams消息，包括用于以下功能的 **专用频道** 消息：

- Office 365 E5/A5/G5
- Microsoft 365 E5/A5/G5
- Microsoft 365 E5/A5/G5 信息保护和管理
- Microsoft 365 E5/A5/G5/F5 合规性和 F5 安全&合规性

Office 365和Microsoft 365 E3包括适用于 SharePoint Online、OneDrive 和 Exchange Online 的 DLP 保护。 这还包括通过 Teams 共享Teams，SharePoint Online OneDrive共享文件。

在聊天中支持 DLP Teams需要 E5。

要详细了解许可要求，请参阅 [Microsoft 365 租户级服务许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

> [!IMPORTANT]
> DLP 仅适用于聊天或频道线程中的实际消息。 活动通知（包括短消息预览，并且根据用户的通知设置显示）不包含在 DLP Teams中。 即使已应用 DLP 策略并删除了邮件本身的敏感信息，预览中显示的邮件部分的任何敏感信息仍将在通知中可见。

## <a name="scope-of-dlp-protection"></a>DLP 保护的范围

DLP 保护以不同方式应用于Teams实体。

|当策略的作用域为 |这些Teams实体 |将具有可用的 DLP 保护|
|---------|---------|---------|
|单个用户帐户     |1：1/n 聊天         |是         |
|     |常规聊天         |否         |
|     |私人频道         |是         |
|安全组/通讯组列表  | 1：1/n 聊天         |是         |
|     |常规聊天         |否         |
|     |私人频道         |是        |
|Microsoft 365组    |1：1/n 聊天          |否         |
|     |常规聊天          |是        |
|     |私人频道|否| 


## <a name="policy-tips-help-educate-users"></a>策略提示有助于培训用户

与 DLP 在[Exchange、Outlook、Outlook 网页版、SharePoint](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [Online、OneDrive for Business 网站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)和[Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)桌面客户端中的工作方式类似，当使用 DLP 策略触发操作时，会显示策略提示。 下面是策略提示的示例：

![阻止的邮件通知Teams。](../media/dlp-teams-blockedmessage-notification.png)

在此，发件人尝试在一个安全通道中共享Microsoft Teams号码。 The **What can I do？** link opens a dialog box that provides options for the sender to resolve the issue. 请注意，发件人可以选择覆盖策略，或通知管理员查看并解析策略。

![用于解决阻止的邮件的选项。](../media/dlp-teams-blockedmessage-possibleactions.png)

在组织中，可以选择允许用户覆盖 DLP 策略。 配置 DLP 策略时，可以使用默认策略提示，或 [为](#to-customize-policy-tips) 组织自定义策略提示。

返回到我们的示例，其中发件人在 Teams 频道中共享了社会保险号码，以下是收件人看到的信息：

> [!div class="mx-imgBorder"]
> ![邮件被阻止。](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>自定义策略提示

若要执行该任务，须被分配具有编辑 DLP 策略权限的角色。 若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

1. 转到合规中心 [https://compliance.microsoft.com](https://compliance.microsoft.com) () 并登录。

2. 选择“**数据丢失保护**” > “**策略**”。

3. 选择策略，在"策略设置 **"旁边**，选择"编辑 **"。**

4. 创建新规则，或编辑策略的现有规则。

    > [!div class="mx-imgBorder"]
    > ![编辑策略的规则。](../media/dlp-teams-editrule.png)

5. 在" **用户通知"** 选项卡上，选择"自定义 **电子邮件文本"和** /或 **"自定义策略提示文本选项** "。

    > [!div class="mx-imgBorder"]
    > ![自定义用户通知和策略提示。](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 指定要用于电子邮件通知和/或策略提示的文本，然后选择"保存 **"。**

7. 在"**策略设置"选项卡上**，选择"保存 **"。**

允许大约 1 小时更改通过数据中心运行并同步到用户帐户。
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>将 Microsoft Teams 作为位置添加到现有 DLP 策略

若要执行该任务，须被分配具有编辑 DLP 策略权限的角色。 若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

1. 转到合规中心 [https://compliance.microsoft.com](https://compliance.microsoft.com) () 并登录。

2. 选择“**数据丢失保护**” > “**策略**”。

3. 选择一个策略，然后查看"位置 **"下的值**。 如果看到 **Teams和频道消息，** 则一切都已设置。 如果不单击，请单击"编辑 **"。**

    > [!div class="mx-imgBorder"]
    > ![现有策略的位置。](../media/dlp-teams-editexistingpolicy.png)

4. 在状态 **列中**，打开聊天和Teams **消息的策略**。

    > [!div class="mx-imgBorder"]
    > ![用于Teams和频道的 DLP。](../media/dlp-teams-addteamschatschannels.png)

5. 在"**选择位置"** 选项卡上，保留所有帐户的默认设置，或选择"**允许选择特定位置"。** 可以指定：

    1. 最多包含或排除 1000 个个人帐户
    1. 要包含或排除的通讯组列表和安全组。 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. 然后选择“**下一步**”。

7. 单击 **“保存”**。

允许大约 1 小时更改通过数据中心运行并同步到用户帐户。
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>为 Microsoft Teams 定义新的 DLP 策略

若要执行该任务，须被分配具有编辑 DLP 策略权限的角色。 若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

1. 转到合规中心 [https://compliance.microsoft.com](https://compliance.microsoft.com) () 并登录。

2. 选择 **“数据丢失保护”** > **“策略”** > **“创建策略”**。

3. 选择模板 [，](data-loss-prevention-policies.md#dlp-policy-templates)然后选择下一 **步**。

    在我们的示例中，我们选择了"美国个人身份信息数据"模板。

    > [!div class="mx-imgBorder"]
    > ![DLP 策略的隐私模板。](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. 在"**命名策略"** 选项卡上，指定策略的名称和说明，然后选择"下一步 **"。**

5. 在"**选择位置"** 选项卡上，保留所有帐户的默认设置，或选择"**允许我选择特定位置"。** 可以指定：

    1. 最多包含或排除 1000 个个人帐户
    1. 要包含或排除的通讯组列表和安全组。 **这是公共预览功能。**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP 策略位置。](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > 如果您希望确保包含敏感信息的文档不会在 Teams 中以不当方式共享，请确保 **SharePoint 网站** 和 **OneDrive** 帐户以及 Teams 聊天和频道消息 **已** 打开。

6. 在"**策略设置**"选项卡上的"自定义要保护的内容类型"下，保留默认的简单设置，或选择"**使用** 高级设置"，然后选择"下一步 **"。** 如果选择高级设置，你可以为策略创建或编辑规则。 若要获取有关此的帮助，请参阅 [简单设置与高级设置](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。

7.  在" **策略设置"** 选项卡上的 **"** 如果检测到敏感信息，想要做什么？"下，查看设置。 你可以在此处选择保留默认 [策略](use-notifications-and-policy-tips.md)提示和电子邮件通知，或自定义它们。

    > [!div class="mx-imgBorder"]
    > ![具有提示和通知的 DLP 策略设置。](../media/dlp-teams-policysettings-tipsemails.png)

    完成查看或编辑设置后，选择"下一 **步"。**

8. 在"策略设置"选项卡上的"要先打开策略还是先测试内容 **？"** 下，选择是打开策略，还是先测试策略，还是 [](dlp-overview-plan-for-dlp.md#policy-deployment)将其保持为"现在关闭"，然后选择"下一步 **"。**

    > [!div class="mx-imgBorder"]
    > ![指定是否打开策略。](../media/dlp-teams-policysettings-turnonnow.png)

9. 在 **"查看设置"** 选项卡上，查看新策略的设置。 选择 **"** 编辑"进行更改。 完成后，选择"创建 **"。**

允许新策略大约一小时通过数据中心运行并同步到用户帐户。

## <a name="prevent-external-access-to-sensitive-documents"></a>阻止对敏感文档的外部访问

若要确保SharePoint外部来宾在默认情况下不能从 SharePoint 或 Teams访问包含敏感信息的文档，请选择以下选项：

- 通过默认将新文件标记为敏感，可以确保文档在 DLP 扫描之前受到保护，并标记为可 [安全共享](/sharepoint/sensitive-by-default)。

- 建议的 DLP 策略结构

    - **条件**
        - 内容包含以下任何敏感信息类型：[选择所有适用]
        
        - 与组织Microsoft 365人员共享内容
        
          > [!div class="mx-imgBorder"]
          > ![用于检测敏感内容的外部共享的 DLP 条件。](../media/dlp-teams-external-sharing/external-condition.png)

    - **操作**
        - 限制外部用户对内容的访问
        
        - 使用电子邮件和策略提示通知用户
        
        - 向管理员发送事件报告
        
        > [!div class="mx-imgBorder"]
        > ![DLP 操作，以阻止外部共享敏感内容。](../media/dlp-teams-external-sharing/external-action.png)

DLP 策略在尝试与外部来宾共享包含SharePoint的文档时正在操作：

> [!div class="mx-imgBorder"]
> ![外部共享被阻止。](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


当来宾尝试在包含阻止外部阻止的文档中打开文档时Teams DLP 策略：

> [!div class="mx-imgBorder"]
> ![外部访问被阻止。](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>相关文章

- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [发送电子邮件通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
