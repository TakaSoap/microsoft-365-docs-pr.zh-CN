---
title: 设置连接器以存档 Android 移动数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置 TeleMessage 连接器以导入和存档 Android 移动电话中的 SMS、MMS 和语音呼叫。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 35ff69ec3b8f0af5ed86350862bb7b0917a98909
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200257"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>设置连接器以存档 Android 移动数据

使用 Microsoft 365 合规性中心中的 TeleMessage 连接器导入并存档来自 Android 移动电话的 SMS、MMS、语音呼叫和呼叫日志。 设置和配置连接器后，它会每天连接到组织的 TeleMessage 帐户，并将使用 TeleMessage Android 存档器的员工的移动通信导入 Microsoft 365 中的邮箱。

将来自 Android 移动电话的数据存储在用户邮箱中之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用到 Android 存档数据。 例如，您可以使用内容搜索来搜索 Android 存档移动通信，或将包含 Android 存档连接器数据的邮箱与高级电子数据展示事例中的保管人程序关联。 使用 Android 存档连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。

## <a name="overview-of-archiving-android-mobile-data"></a>存档 Android 移动数据概述

以下概述说明使用连接器在 Microsoft 365 中存档 Android 移动数据的过程。

![Android 存档连接器工作流](../media/AndroidArchiverConnectorWorkflow.png)

1. 您的组织与 TeleMessage 协同工作以设置 Android 存档连接器。 有关详细信息，请参阅 [Android 存档](https://www.telemessage.com/office365-activation-for-android-archiver/)。

2. 每24小时一次，则会将来自组织的 Android 移动电话的短信、MMS、语音呼叫和呼叫日志复制到 TeleMessage 网站。

3. 您在 Microsoft 365 合规性中心中创建的 Android 存档连接器每天连接到 TeleMessage 网站，并将以前的24小时内的 Android 数据传输到 Microsoft 云中的安全 Azure 存储位置。 连接器还将 Android 数据转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建一个名为 "Android 存档" 的新文件夹，并将这些项目导入其中。 连接器通过使用 *用户的电子邮件地址* 属性的值进行映射。 每封电子邮件都包含此属性，该属性填入电子邮件的每个参与者的电子邮件地址。 除了使用 *用户电子邮件地址* 属性的值进行自动用户映射之外，还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含用户的移动电话号码以及每个用户对应的 Microsoft 365 邮箱地址。 如果为每个电子邮件项目启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件。 如果找不到与用户的移动电话号码相对应的有效 Microsoft 365 用户，连接器将使用电子邮件项目的用户电子邮件地址属性。 如果连接器在自定义映射文件或电子邮件项目的 *用户电子邮件地址* 属性中找不到有效的 Microsoft 365 用户，则不会导入该项目。

## <a name="before-you-begin"></a>准备工作

存档 Android 通信数据所需的某些实施步骤是 Microsoft 365 外部的，必须先完成这些步骤，然后才能在合规性中心中创建连接器。

- [从 TeleMessage 中对 Android 存档服务](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)进行排序，并为您的组织获取有效的管理帐户。 创建连接器时，需要登录到此帐户。

- 在 TeleMessage 帐户中注册需要 Android 存档服务的所有用户。 注册用户时，请确保使用的电子邮件地址与用于其 Microsoft 365 帐户的电子邮件地址相同。

- 在你的员工的移动电话上安装和激活 TeleMessage Android 存档应用。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 您需要在创建连接器时提供此同意。 若要同意此请求，请转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能成功创建&T 网络连接器。

- 必须在 Exchange Online 中为创建 Android 存档连接器的用户分配邮箱导入导出角色。 这是在 Microsoft 365 合规性中心的 " **数据连接器** " 页中添加连接器所必需的。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

## <a name="create-an-android-archiver-connector"></a>创建 Android 存档连接器

最后一步是在 Microsoft 365 合规性中心中创建 Android 存档连接器。 连接器使用您提供的信息来连接到 TeleMessage 网站，并将 Android 通信转移到 Microsoft 365 中对应的用户邮箱框中。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击 "**数据连接器**  >  **Android 存档**器"。

2. 在 " **Android 存档** 产品说明" 页上，单击 " **添加连接器**"。

3. 在 " **服务条款** " 页上，单击 " **接受**"。

4. 在 " **登录到 TeleMessage** " 页上的 "步骤 3" 下的以下框中，输入所需信息，然后单击 " **下一步**"。

   - **Username：** 您的 TeleMessage 用户名。

   - **密码：** 您的 TeleMessage 密码。

5. 创建连接器后，关闭弹出窗口并单击 " **下一步**"。

6. 在 " **用户映射** " 页上，启用自动用户映射，然后单击 " **下一步**"。 如果您需要自定义映射，请上载 CSV 文件，然后单击 " **下一步**"。

7. 提供管理员同意，然后单击 " **下一步**"。

   若要提供管理员同意，必须使用 Office 365 全局管理员的凭据登录，然后接受同意请求。 如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。

8. 查看您的设置，然后单击 " **完成** " 以创建连接器。

9. 转到 " **数据连接器** " 页中的 "连接器" 选项卡，查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 较大项目的支持将在以后提供。
