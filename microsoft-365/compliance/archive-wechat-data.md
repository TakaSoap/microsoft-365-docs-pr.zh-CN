---
title: 设置连接器以将 WeChat 数据存档在 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 在邮箱中设置并使用连接器Microsoft 365 合规中心中导入和存档 WeChat Microsoft 365。
ms.openlocfilehash: f2adb42dfd8145658e8861c752cfb9c11e306f52
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328213"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>设置连接器以存档 WeChat 数据

使用远程服务器中的 TeleMessage 连接器Microsoft 365 合规中心和存档 WeChat 和 WeCom 呼叫、聊天、附件、文件和已撤回的消息。 设置和配置连接器后，它将连接到您组织的 TeleMessage 帐户，并且使用 TeleMessage WeChat 存档器将员工的移动通信导入 Microsoft 365 中的邮箱。

将 WeChat 存档连接器数据存储在用户邮箱中后，您可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 WeChat 通信数据。 例如，您可以使用内容搜索搜索 WeChat 通信，或将包含 WeChat 存档连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用 WeChat 存档连接器在 Microsoft 365 导入和存档数据可帮助组织遵守公司管理法规和法规策略。

## <a name="overview-of-archiving-wechat-communication-data"></a>存档 WeChat 通信数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档 WeChat 通信数据的过程。

![WeChat 存档程序数据的存档工作流。](../media/WeChatConnectorWorkflow.png)

1. 您的组织与 TeleMessage 合作，以设置 WeChat 存档器连接器。

2. 实时将组织的 WeChat 数据复制到 TeleMessage 网站。

3. 在 Microsoft 365 合规中心 创建的微信存档连接器每天连接到 TeleMessage 站点，将过去 24 小时内的电子邮件转移到 Microsoft 云中的安全 Azure 存储 区域。

4. 连接器将移动通信项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建名为 WeChat Archiver 的新文件夹，并且项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址" *属性的值进行映射* 。 每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。 除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含用户的移动电话号码和每个用户Microsoft 365相应的邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。 如果找不到与用户Microsoft 365用户对应的有效邮件，连接器将使用电子邮件项目的"用户的电子邮件地址"属性。 如果连接器在自定义映射文件或Microsoft 365项的电子邮件地址属性中找不到有效的邮件用户，该项目将不会导入。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 使用 TeleMessage 设置 WeChat 存档连接器。 有关详细信息，请参阅[激活 TeleMessage WeChat Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)。

- 为用户设置 TeleMessage Microsoft 365并获取有效的公司管理帐户。 有关详细信息，请参阅 Order [Microsoft 365 Mobile Archiving](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)。

- 在 TeleMessage 帐户中注册需要 WeChat 存档的所有用户，其电子邮件地址与用户的 Microsoft 365相同。

- 你需要在组织中用户的移动电话上安装"为 WeCom"应用并激活该应用。 WeCom 应用允许用户与其他 WeChat 和 WeCom 用户进行通信和聊天。

- 必须为在服务器中创建 WeChat 存档Microsoft 365 合规中心用户分配数据连接器管理员角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- 此 TeleMessage 数据连接器可用于美国政府GCC环境中Microsoft 365环境。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-wechat-archiver-connector"></a>创建 WeChat 存档器连接器

按照本节中的步骤在邮箱中创建微信存档Microsoft 365 合规中心。 连接器使用您提供的信息连接到 TeleMessage 站点，将 WeChat 通信数据传输至 Microsoft 365 中的相应用户邮箱。

1. 转到 ， <https://compliance.microsoft.com> 然后单击"数据 **连接器"** > **"聊天存档程序"**。

2. 在 **"WeChat 存档器** 产品说明"页上，单击" **添加连接器"**

3. 在" **服务条款"页上** ，单击"接受 **"**。

4. 在" **登录到 TeleMessage** "页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"**。

    - **用户名**：你的 TeleMessage 用户名。

    - **密码**：你的 TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口转到下一页。

6. 在" **用户映射"** 页上，启用自动用户映射。 您还可以上载自定义用户映射 CSV 文件。

7. 单击 **"下** 一步"，查看设置，然后单击" **完成** "以创建连接器。

8. 转到"**数据连接器"** 页上的"连接器"选项卡以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
