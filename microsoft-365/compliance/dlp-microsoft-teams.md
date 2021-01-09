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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 现在可以将 DLP 策略应用于 Microsoft Teams 聊天和频道。 阅读本文，详细了解其工作方式。
ms.openlocfilehash: 25ba5850f496c188c2a38d6cc5b68960a85e5e5f
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790156"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>数据丢失防护和 Microsoft Teams

> [!NOTE]
> 数据丢失防护功能最近已添加到 Microsoft Teams 聊天和频道消息中，这些消息适用于获得 Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 信息保护和治理或 Office 365 高级合规性许可的用户。 Office 365 和 Microsoft 365 E3 包括 SharePoint Online、OneDrive 和 Exchange Online 的 DLP 保护。 这还包括通过 Teams 共享的文件，因为 Teams 使用 SharePoint Online 和 OneDrive 共享文件。
支持 Teams 聊天中的 DLP 保护需要 E5。
要详细了解许可要求，请参阅 [Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。

> [!IMPORTANT]
> 仅在用户拥有 Exchange Online 中的邮箱时，才支持适用于 Teams 的 DLP

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft Teams DLP 概述

最近 [，DLP (](data-loss-prevention-policies.md) 数据丢失防护) 包括 Microsoft Teams 聊天和频道消息， **包括私人频道消息**。


如果你的组织具有 DLP，你现在可以定义阻止用户共享 Microsoft Teams 频道或聊天会话中的敏感信息的策略。 下面是此保护的工作原理的一些示例：

- **示例 1：保护邮件中的敏感信息**。 假设有人尝试在 Teams 聊天或频道中与外部用户或外部 (共享) 。 如果已定义 DLP 策略以防止出现此情况，则包含发送给外部用户的敏感信息的邮件将被删除。 根据 DLP 策略的配置方式，这会自动发生，且在几秒钟内发生。

    > [!NOTE]
    > 与具有：<br/>- [团队和](https://docs.microsoft.com/MicrosoftTeams/guest-access) 频道中的来宾访问;或<br/>- [会议和](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) 聊天会话中的外部访问。 <p>外部聊天会话的 DLP 仅在发件人和接收方都采用"仅 Teams"模式并且使用 [Microsoft Teams 本机联盟时才能工作](https://docs.microsoft.com/microsoftteams/manage-external-access)。 DLP for Teams 不会阻止[](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)与 Skype for Business 或非本机联合聊天会话进行互操作的消息。

- **示例 2：保护文档中的敏感信息**。 假设某人尝试在 Microsoft Teams 频道或聊天中与来宾共享文档，并且该文档包含敏感信息。 如果已定义 DLP 策略以防止这种情况发生，文档将不会为这些用户打开。 请注意，在这种情况下，DLP 策略必须包含 SharePoint 和 OneDrive，才能实施保护。  (这是显示在 Microsoft Teams 中的适用于 SharePoint 的 DLP 示例，因此要求用户获得 Office 365 E3 (中包含的 Office 365 DLP) 的许可，但不要求用户获得 Office 365 高级合规性许可。) 

## <a name="policy-tips-help-educate-users"></a>策略提示可帮助培训用户

与 DLP 在 [Exchange、Outlook、Outlook 网页](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)版 [、SharePoint Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)网站和 [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)桌面客户端中的工作方式类似，当操作与 DLP 策略冲突时，会显示策略提示。 下面是策略提示的示例：

![Teams 中阻止的消息通知](../media/dlp-teams-blockedmessage-notification.png)

在这种情况下，发件人尝试在 Microsoft Teams 频道中共享社会保险号码。 The **What can I do？** link opens a dialog box that provides options for the sender to resolve the issue. 请注意，在这种情况下，发件人可以选择覆盖策略，或通知管理员查看并解决它。

![用于解析阻止的邮件的选项](../media/dlp-teams-blockedmessage-possibleactions.png)

在组织中，可以选择允许用户覆盖 DLP 策略。 此外，当您配置 DLP 策略时，您可以使用默认策略提示，或 [为](#to-customize-policy-tips) 组织自定义策略提示。

返回到我们的示例，其中发件人在 Teams 频道中共享了社会保险号码，以下是收件人看到的示例：

![邮件被阻止](../media/dlp-teams-blockedmessage-notification-to-user.png)

The **What's this？** link opens an [article](data-loss-prevention-policies.md) about DLP policies， which helps why the message was blocked.

### <a name="to-customize-policy-tips"></a>自定义策略提示

若要执行此任务，您必须获得有权编辑 DLP 策略的角色。 若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

1. 转到安全&合规 [https://protection.office.com](https://protection.office.com) () 登录。

2. 选择 **数据丢失防护**  >  **策略**。

3. 选择策略，在策略设置 **旁边** 选择"编辑 **"。**

4. 创建新规则，或编辑策略的现有规则。<br/>![编辑策略的规则](../media/dlp-teams-editrule.png)<br/>

5. 在" **用户通知"** 选项卡上，选择"自定义 **电子邮件文本"** 和/或" **自定义策略提示文本** 选项"。<br/>![自定义用户通知和策略提示](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 指定要用于电子邮件通知和/或策略提示的文本，然后选择"保存 **"。**

7. 在"**策略设置"** 选项卡上，选择"**保存"。**

允许大约 1 小时更改通过数据中心工作，并同步到用户帐户。
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>将 Microsoft Teams 添加为现有 DLP 策略的位置

若要执行此任务，您必须获得有权编辑 DLP 策略的角色。 若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

1. 转到安全&合规 [https://protection.office.com](https://protection.office.com) () 登录。

2. 选择 **数据丢失防护**  >  **策略**。

3. 选择一个策略，然后查看位置 **下的值**。 如果你看到 **Teams 聊天和频道消息**，则你已全部设置。 如果没有，请单击"编辑 **"。**<br/>![现有策略的位置](../media/dlp-teams-editexistingpolicy.png)<br/>

4. 在 **"状态** "列中，打开 Teams 聊天 **和频道消息的策略**。<br/>![适用于 Teams 聊天和频道的 DLP](../media/dlp-teams-addteamschatschannels.png)<br/>

5. 在" **选择** 位置"选项卡上，保留所有帐户的默认设置，或选择"允许 **我** 选择特定位置"，并指定要包含和排除的帐户、通讯组列表或安全组。 然后选择“**下一步**”。

6. 单击“**保存**”。

允许大约 1 小时更改通过数据中心工作，并同步到用户帐户。
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>为 Microsoft Teams 定义新的 DLP 策略

若要执行此任务，您必须获得有权编辑 DLP 策略的角色。 若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

1. 转到安全&合规 [https://protection.office.com](https://protection.office.com) () 登录。

2. 选择 **"数据丢失防护**  >  **策略**  >  **+ 创建策略"。**

3. 选择模板 [，](data-loss-prevention-policies.md#dlp-policy-templates)然后选择"下一 **步"。**<br/>在我们的示例中，我们选择了"美国个人身份信息数据"模板。<br/>![DLP 策略的隐私模板](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. 在 **"命名策略"** 选项卡上，指定策略的名称和说明，然后选择"下一步 **"。**

5. 在" **选择** 位置"选项卡上，保留所有帐户的默认设置，或选择"允许 **我** 选择特定位置"，并指定要包含和排除的帐户、通讯组列表或安全组。 然后选择“**下一步**”。

![DLP 策略位置](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> 如果你想要确保在 Teams 中不包含不当共享包含敏感信息的文档，请确保 **SharePoint** 网站和 **OneDrive** 帐户以及 Teams 聊天和频道消息已 **打开**。


6. 在"**策略设置**"选项卡上的"自定义要保护的内容类型"下，保留默认的简单设置，或选择"使用 **高级** 设置"，然后选择"下一 **步"。** 如果选择高级设置，可以创建或编辑策略规则。  (若要获取此帮助，请参阅"简单设置"与 ["高级](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)设置") 

7.  在 **"策略设置** " **选项卡上的"** 如果检测到敏感信息，该怎么办？"下，查看设置。  (可以在此处选择保留默认策略提示和电子邮件通知，或自定义它们[](use-notifications-and-policy-tips.md)。) <br/>![带提示和通知的 DLP 策略设置](../media/dlp-teams-policysettings-tipsemails.png)<br/>完成查看或编辑设置后，选择"下一 **步"。**

8. 在"策略设置"选项卡上的"是否要先打开策略或先测试内容 **？"，** 选择是打开策略，还是先测试它，或将其 [](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)保持为现在关闭状态，然后选择"下一步 **"。**<br/>![指定是否打开策略](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. 在 **"查看设置"** 选项卡上，查看新策略的设置。 选择 **"** 编辑"进行更改。 完成后，选择"创建 **"。**

允许新策略大约一小时通过数据中心工作并同步到用户帐户。

## <a name="prevent-external-access-to-sensitive-documents"></a>阻止外部访问敏感文档

若要确保外部来宾默认情况下无法从 SharePoint 或 Teams 访问包含敏感信息的 SharePoint 文档，请选择以下选项：

- 通过默认将新文件标记为敏感，可以确保文档在 DLP 扫描之前受到保护，并标记为可 [安全共享](https://docs.microsoft.com/sharepoint/sensitive-by-default)
- 建议的 DLP 策略结构
    - **条件**
        - 内容包含以下任何敏感信息类型：[选择所有适用内容]
        - 内容从 Microsoft 365 与组织外部人员共享
        <br/>![用于检测敏感内容的外部共享的 DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **操作**
        - 限制外部用户访问内容
        - 使用电子邮件和策略提示通知用户
        - 向管理员发送事件报告    
        <br/>![阻止外部共享敏感内容的 DLP 操作](../media/dlp-teams-external-sharing/external-action.png)<br/>

DLP 策略在尝试与外部来宾共享包含敏感信息的 SharePoint 文档时正在操作：
<br/>![外部共享被阻止](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


当来宾尝试在 Teams 中打开包含阻止外部阻止的文档时，DLP 策略在操作：
<br/>![外部访问被阻止](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>相关文章

[创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)

[发送电子邮件通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
