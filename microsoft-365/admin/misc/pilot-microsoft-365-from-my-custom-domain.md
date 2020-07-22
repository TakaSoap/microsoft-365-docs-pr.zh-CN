---
title: 从我的自定义域试点 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何仅使用两个测试帐户将电子邮件功能试点从我的自定义域到 Microsoft 365 邮箱的电子邮件功能。
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186037"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>从我的自定义域试点 Microsoft 365

可以按照以下要求和限制试用 Microsoft 365：

- 你的当前电子邮件提供商必须提供电子邮件转发功能。

- 必须在 DNS 托管提供商处管理 Microsoft 365 DNS记录，而不是让 Microsoft 365 为你管理这些记录。

    要了解更多信息，请参阅[添加 DNS 记录以连接你的域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

- 没有其他电子邮件服务器上的用户的忙/闲信息。

- 管理员无法从单个位置管理所有用户帐户。

- 用户可能无法使用 Microsoft 365 垃圾邮件筛选。

## <a name="set-up-a-microsoft-365-pilot"></a>设置 Microsoft 365 试点

请按照以下步骤设置 Microsoft 365 试点：

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>步骤 1：登录到 Microsoft 365 管理中心。

1. 使用你的工作或学校帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。

2. 在左侧导航窗格中，选择“**设置**” > “**域**”。

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>步骤 2：验证你是否拥有要使用的域

1. 在“**域**”页面上，选择“**添加域**”。

2. 在框中键入域名，选择“**使用此域**”，然后选择“**继续**”。

3. 选择要在你的域中测试的服务，例如电子邮件和即时消息。

5. 在“**验证域**”页面上，按照分步说明进行操作，然后选择“**验证**”。

    DNS 更改需要几分钟到 72 小时才会生效。

    如果验证成功，系统将要求你修改 DNS 记录。

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>步骤 3：在 Exchange Online 中将域标记为共享

1. 在 Exchange 管理中心的“**邮件流**”部分，选择“**接受的域**”，然后选择要修改的域。

2. 双击以打开窗口，然后选择“**内部中继**”。 

3. 选择“**保存**”。

    此设置可能需要几分钟才能生效。

### <a name="step-4-unblock-the-existing-email-server-optional"></a>步骤 4：取消阻止现有电子邮件服务器（可选）

Microsoft 365 使用 Exchange Online Protection (EOP) 进行垃圾邮件防护。 如果 EOP 检测到当前邮件服务器转发了大量垃圾邮件，它可能会阻止你现有的邮件服务器。 如果你信任适用于其他电子邮件提供商的垃圾邮件保护，则可以在 Microsoft 365 中取消阻止服务器。

> [!NOTE]
> 通过取消阻止现有电子邮件服务器，通过原始服务器送达的任何垃圾邮件都会进入 Microsoft 365 邮箱，而且无法评估 Microsoft 365 防止垃圾邮件的效果。

1. 在 Exchange 管理中心导航窗格中，选择“**保护**”，然后选择“**连接筛选器**”。

2. 在“**IP 允许列表**”中，选择 **+**，然后添加当前电子邮件提供商的邮件服务器 IP 地址。 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>步骤 5：创建用户帐户和设置主答复地址

1. 在 Microsoft 365 管理中心的左侧窗格，选择“**用户**” > “**活动用户**”。

2. 通过添加两个现有用户，创建两个测试帐户。

    对于每个帐户，请选择“**+ 添加用户**”，然后填写所需的信息，包括要测试的密码方法。

    若要确保用户的电子邮件保持不变，“**用户名**”字段必须与用户的当前电子邮件地址相匹配。

3. 选择相应的许可证，单击“**下一步**”，然后单击“**完成添加**”。 

4. 在“**用户名**”旁边，从下拉列表中选择你的自定义域名。 

5. 选择“**创建**” > “**关闭**”。

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a>步骤 6：更新 DNS 托管提供商处的 DNS 记录

登录到 DNS 托管提供商的网站，然后按照[添加 DNS 记录以连接你的域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)上的说明进行操作。

**注意以下两项例外：**

- 请勿创建新 MX 记录或更改现有 MX 记录。

- 如果你已经有了上一个电子邮件提供商的发件人策略框架 (SPF) 记录，请不要为 Exchange Online 创建新 SPF (TXT) 记录，而是向当前 TXT 记录添加“include:spf.protection.outlook.com”。

    例如，"v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".

    如果你还没有 SPF 记录，请修改 Microsoft 365 推荐的 SPF 记录，以包括你的当前电子邮件提供商的域并添加 protection.outlook.com。 这样将为来自这两个电子邮件系统的传出邮件授权。

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a>步骤 7：在当前提供商处设置电子邮件转发

在当前电子邮件提供商处，将用户电子邮件帐户的转发设置为你的 onmicrosoft.com 域：

- 将用户 A 邮箱转发到 usera@yourcompany.onmicrosoft.com

- 将用户 B 邮箱转发到 userb@yourcompany.onmicrosoft.com

完成此步骤后，所有发送到 usera@yourcompany.com 和 userb@yourcompany.com 的电子邮件均可在 Microsoft 365 中使用。

> [!NOTE]
> 有关如何设置邮件转发的确切步骤，请联系你当前的电子邮件提供商。<br/>
> 无需在当前电子邮件提供商处保留邮件副本。<br/>
> 大多数提供商在转发电子邮件时会保留发件人的答复地址，所以答复会发送给原始发件人。

### <a name="step-8-test-mail-flow"></a>步骤 8：测试邮件流

1. 使用用户 A 的凭据登录 Outlook Web App。

2. 执行以下测试：

    - 通过向用户 B 发送电子邮件来测试本地 Microsoft 电子邮件。该电子邮件将立即送达。 在此方案中，该邮件不会路由到原始服务器上用户 B 的邮箱，因为 Microsoft 365 邮箱是本地的。

    - 通过发送电子邮件（例如，发送给用户 C）来测试在现有电子邮件系统上向用户发送的电子邮件。该电子邮件将传送到原始邮件服务器上用户 C 的邮箱。

    - 验证是否从外部帐户或现有电子邮件系统上的员工电子邮件帐户正确设置了转发。 例如，从用户 C 的原始服务器帐户或 Hotmail 帐户向用户 A 发送一封电子邮件，并验证电子邮件是否到达用户 A 的 Microsoft 365 邮箱。

### <a name="step-9-move-mailbox-contents"></a>步骤 9：移动邮箱内容

因为你仅移动两个测试用户，并且用户 A 和用户 B 都在使用Outlook，因此可以通过在新的 Outlook 配置文件中打开旧的 .PST 文件并复制邮件、日历项、联系人等来移动电子邮件。 有关更多信息，请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。

将项目导入到 Microsoft 365 邮箱中的适当位置后，可以从任何位置的任何设备访问这些项目。

如果涉及更多邮箱，或者员工未使用 Outlook，则可以使用 Exchange 管理中心中提供的迁移工具。 首先，请转到 Exchange 管理中心，然后按照[将电子邮件从 IMAP 服务器迁移到 Exchange Online 邮箱 – 我们需要新的文章资源]中的说明进行操作。