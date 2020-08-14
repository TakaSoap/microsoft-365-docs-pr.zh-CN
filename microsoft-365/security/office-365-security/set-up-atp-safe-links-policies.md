---
title: 设置 Office 365 ATP 安全链接策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 设置安全链接策略以保护您的组织免受 Word、Excel、PowerPoint 和 Visio 文件以及电子邮件中的恶意链接。
ms.openlocfilehash: f935002a300bd5f4553cbab429318dad4104b208
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662250"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>设置 Office 365 ATP 安全链接策略

> [!IMPORTANT]
> 本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。 如果您是在 Outlook 中查找有关安全链接的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

[Atp 安全链接](atp-safe-links.md)（ [Office 365 高级威胁防护](office-365-atp.md) 的一项功能 (ATP) ）可帮助保护您的组织免受在网络钓鱼和其他攻击中使用的恶意链接。 如果您具有 [安全 & 合规中心](permissions-in-the-security-and-compliance-center.md)的必要权限，则可以设置 ATP 安全链接策略，以帮助确保当用户单击 "web 地址 (url) 时，您的组织受到保护。 您的 ATP 安全链接策略可以配置为扫描 Office 文档中的电子邮件和 Url 中的 Url。

启用 ATP 安全链接后，如果用户单击电子邮件中的链接，并且该 URL 已被组织的自定义 "阻止 URL" 列表阻止，或者如果该 URL 被确定为 "恶意"，则会打开 "警告" 页。

[将新功能连续添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)。 添加新功能时，您可能需要对现有的 ATP 安全链接策略进行调整。

## <a name="what-to-do"></a>需执行的操作

1. 查看先决条件。

2. 查看和编辑适用于每个人的默认 ATP 安全链接策略。 例如，您可以 [为 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。

3. 为特定的电子邮件收件人添加或编辑策略，包括 [设置 ATP 安全链接的自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。

4. 了解本文中 (的 ATP 安全链接策略选项) ，包括最近更改的设置。

## <a name="step-1-review-the-prerequisites"></a>步骤1：查看先决条件

- 确保您的组织具有 [Office 365 高级威胁防护](office-365-atp.md)。

- 请确保您具有必要的权限。 若要定义 (或编辑) ATP 策略，必须为您分配适当的角色。 下表介绍了一些示例：

    |角色|分配的位置/方式|
    |---|---|
    |全局管理员|默认情况下，注册购买 Microsoft 365 的人是全局管理员。  (参阅 [关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) ，了解详细信息。 ) |
    |安全管理员|Azure Active Directory 管理员中心 (<https://aad.portal.azure.com>) |
    |Exchange Online 组织管理|Exchange 管理中心 (<https://outlook.office365.com/ecp>)  <br>或 <br>  PowerShell cmdlet (参阅 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) |

    若要了解有关角色和权限的详细信息，请参阅 [Security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

- 请确保将 Office 客户端配置为使用 [新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (这适用于 office 文档中的 ATP 安全链接保护) 。

- 了解本文中 (的[ATP 安全链接策略选项](#step-4-learn-about-atp-safe-links-policy-options)) 。

- 最长允许30分钟，新的或更新的策略将传播到所有 Microsoft 365 数据中心。

## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>步骤2：定义 (或审阅) 适用于每个人的 ATP 安全链接策略

当您拥有 [Office 365 高级威胁防护功能](office-365-atp.md)时，将拥有适用于组织中每个人的默认 ATP 安全链接策略。 请务必查看，如果需要，请编辑您的默认策略。

1. 转到 <https://protection.office.com> 并使用你的工作或学校帐户登录。

2. 在左侧导航中的 "**威胁管理**" 下，选择 "**策略 \> ** **安全链接**"。

3. 在 " **适用于整个组织的策略** " 部分中，选择 " **默认**"，然后选择 " **编辑** " (编辑按钮类似于铅笔) 。

   ![单击 "编辑" 编辑安全链接保护的默认策略](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)

4. 在 " **阻止以下 url** " 部分中，指定要阻止组织中的用户访问的一个或多个 url。  (请参阅 [使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。 ) 

5. 在 " **应用于内容（电子邮件除外** ）" 部分的 "设置" 中，选择 " (" 或 "清除) 您要使用的选项"。  (建议您选择所有选项。 ) 

6. 选择“**保存**”。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients"></a>步骤3：添加 (或编辑适用于所有或特定电子邮件收件人的) ATP 安全链接策略

在查看 (或编辑) 适用于每个人的默认 ATP 安全链接策略之后，下一步是定义将应用于所有或特定的电子邮件收件人的其他策略。 例如，您可以通过定义其他策略或为所有员工创建更精确的限制来指定您的默认策略的例外。
  
1. 转到 <https://protection.office.com> 并使用你的工作或学校帐户登录。 
    
2. 在左侧导航中的 " **威胁管理**" 下，选择 " **策略**"。

3. 选择 " **安全链接**"。

4. 在 " **适用于特定收件人的策略** " 部分中，选择 " **新建** " (新按钮类似于加号 ( **+**) # A3。

   ![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

5. 指定策略的名称、说明和设置。

   **示例：** 若要设置一个名为 "无直接单击" 的策略，且不允许组织中特定组中的用户在没有 ATP 安全链接保护的情况下单击特定网站，可以指定以下推荐设置：

   - 在 " **名称** " 框中，键入 "无直接单击"。

   - 在 " **说明** " 框中，键入一个说明（如），以防止某些组中的用户在没有 ATP 安全链接验证的情况下单击到网站。

   - 在 " **选择操作** " 部分，选择 **"启用"**。

   - **对于可疑链接和指向文件的链接，请选择 "应用实时 url 扫描**"。如果您想要启用 URL 沙箱以查找可疑和文件指向的 url (建议的) 。 如果您希望仅在完全扫描 Url 后用户收到邮件，则 **在传递邮件之前，请选择 "等待 URL 扫描完成"** 。

   - 如果要为组织内的用户之间发送的邮件启用安全链接，请选择 **"将安全链接应用于在组织内发送的邮件"** 。 (建议的) 。

   - 如果您不希望单个用户覆盖*正在进行的扫描*或*URL 阻止*的通知页面，请选择 **"不允许用户单击到原始 URL"** 。

   -  (这是可选的) 在 " **不重写以下 url"** 部分中，指定一个或多个被视为对您的组织而言是安全的 url。  (参阅 [设置自定义 "不重写" 使用 ATP 安全链接的 url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)) 

   - 在 " **应用** 于" 部分中，选择 **"收件人是其成员**"，然后选择要在策略中包括的组 (s) 。 选择 " **添加**"，然后选择 **"确定"**。

6. 选择“**保存**”。

> [!NOTE]
> 优先级较高的 ATP 安全链接策略将优先。 如果用户接受两个或更多个策略，则只有较高优先级的策略才能生效。 如果您希望客户策略优先执行，则需要提高策略的优先级。

## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>步骤4：了解 ATP 安全链接策略选项

在设置或编辑 ATP 安全链接策略时，将看到几个可用选项。 如果您想知道这些选项是什么，下表介绍了每一个选项及其效果。 请注意，有两种主要的 ATP 安全链接策略可供定义或编辑：

- 适用于每个人的 [默认策略](#default-policy-options) ;并
- [针对特定收件人的其他策略](#policies-that-apply-to-specific-email-recipients)

### <a name="default-policy-options"></a>默认策略选项

默认策略选项适用于组织中的所有人。

****

|此选项|执行的操作|
|---|---|
|**阻止以下 Url**|允许您的组织具有自动阻止的自定义 Url 的自定义列表。 当用户单击此列表中的某个 URL 时，将会看到一个 [警告页面](atp-safe-links-warning-pages.md) ，说明为什么阻止了该 url。 若要了解详细信息，请参阅 [使用 Office 365 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。|
|**适用于企业的 Microsoft 365 应用、适用于 iOS 和 Android 的 Office**| 选择此选项时，ATP 安全链接保护适用于 Windows 或 Mac OS 上的 Word、Excel 和 PowerPoint 文件中的 Url、Outlook 中的电子邮件、iOS 或 Android 设备上的 Office 文档、Windows 上的 Visio 2016 文件以及在 Office 应用程序的 web 版本中打开的文件 (Word、PowerPoint、Excel、Outlook 和 OneNote) ，前提是用户已登录 Office 365。|
|**在用户单击 ATP 安全链接时不进行跟踪**|选择此选项后，将不存储在 Word、Excel、PowerPoint、Visio 文档和 Outlook 电子邮件中的 Url 的数据。|
|**不要让用户点击到原始 URL 的 ATP 安全链接**|选择此选项后，用户将无法继续处理被确定为恶意的 URL 之后的 [警告页](atp-safe-links-warning-pages.md) 。|
|

### <a name="policies-that-apply-to-specific-email-recipients"></a>适用于特定电子邮件收件人的策略

****

|此选项|执行的操作|
|---|---|
|**关闭**|不扫描电子邮件中的 Url。  <br/> 使您能够定义例外规则，如不扫描电子邮件中的 Url 的特定收件人组的 Url 的规则。|
|**On**|通过在用户单击电子邮件中的 Url 并启用 Outlook (C2R) 在 Windows 中的 ATP 安全链接，来重写 Url 以在 ATP 安全链接保护中路由用户。  <br/> 在对阻止或恶意 Url 列表单击时检查 URL，并在后台异步触发 URL 的沙箱，前提是该 URL 没有有效的信誉。|
|**对指向文件的可疑链接和链接应用实时 URL 扫描**|如果选择此选项，则会扫描指向可下载内容的可疑 Url 和链接。|
|**等待 URL 扫描完成后再传递邮件**|如果选择此选项，则将一直保留包含要扫描的 Url 的邮件，直到 Url 完成扫描并在传递邮件之前将其确认为安全。|
|**将安全链接应用于在组织内发送的邮件** <br/> | 当此选项可用并选中时，如果电子邮件帐户托管在 Office 365 中，则会将 ATP 安全链接保护应用于在组织中的人员之间发送的电子邮件。|
|**不跟踪用户点击**|选择此选项后，请单击 "来自外部发件人的电子邮件中的 Url 数据未存储"。 URL 单击 "跟踪" 以查找在组织内发送的电子邮件中的链接当前不受支持。|
|**不允许用户单击到原始 URL**|选择此选项后，用户将无法继续处理被确定为恶意的 URL 之后的 [警告页](atp-safe-links-warning-pages.md) 。|
|**不重写以下 Url**|将 Url 保留为。 保留自定义不需要在组织中对特定电子邮件收件人组进行扫描的安全 Url 列表。 有关更多详细信息，请参阅 [设置自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) （包括对通配符星号 () 支持的最新更改） \* 。|
|

## <a name="next-steps"></a>后续步骤

在 ATP 安全链接策略准备就绪后，您可以通过查看报告了解 ATP 是如何为您的组织工作的。 若要了解详细信息，请参阅以下资源：

- [查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)

- [使用安全与合规中心内的资源管理器](threat-explorer.md)

继续在新功能的前面提供 ATP。 请访问 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。
