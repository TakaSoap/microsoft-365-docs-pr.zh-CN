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
ms.openlocfilehash: 3744bd48ccb25a98bb61d379783afd669bf6da67
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168742"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>设置连接器以存档 WeChat 数据

使用电子邮件中的 TeleMessage Microsoft 365 合规中心导入和存档 WeChat 和 WeCom 呼叫、聊天、附件、文件和已撤回的消息。 设置和配置连接器后，它将连接到您组织的 TeleMessage 帐户，并且使用 TeleMessage WeChat 存档器将员工的移动通信导入 Microsoft 365 中的邮箱。

将 WeChat 存档连接器数据存储在用户邮箱中后，您可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 WeChat 通信数据。 例如，您可以使用内容搜索搜索 WeChat 通信，或将包含 WeChat 存档连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用 WeChat 存档连接器在 Microsoft 365 导入和存档数据可帮助组织遵守公司管理法规和法规策略。

## <a name="overview-of-archiving-wechat-communication-data"></a>存档 WeChat 通信数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档 WeChat 通信数据的过程。

![WeChat 存档程序数据的存档工作流。](../media/WeChatConnectorWorkflow.png)

1. 您的组织与 TeleMessage 合作，以设置 WeChat 存档器连接器。

2. 实时将组织的 WeChat 数据复制到 TeleMessage 网站。

3. 在 Microsoft 365 合规中心 创建的 WeChat 存档连接器每天连接到 TeleMessage 站点，将过去 24 小时内的电子邮件转移到 Microsoft 云中的安全 Azure 存储 区域。

4. 连接器将移动通信项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建名为 WeChat Archiver 的新文件夹，并且项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址" *属性的值进行映射* 。 每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。 除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含用户的移动电话号码和每个用户Microsoft 365相应的邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。 如果找不到与用户Microsoft 365用户对应的有效邮件，连接器将使用电子邮件项目的"用户的电子邮件地址"属性。 如果连接器在自定义映射文件或Microsoft 365项的电子邮件地址属性中找不到有效的邮件用户，该项目将不会导入。 

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 使用 TeleMessage 设置 WeChat 存档连接器。 有关详细信息，请参阅激活[TeleMessage WeChat Archiver for Microsoft 365。](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)

- 为用户设置 TeleMessage Microsoft 365并获取有效的公司管理帐户。 有关详细信息，请参阅 Order [Microsoft 365 Mobile Archiving](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)。

- 在 TeleMessage 帐户中注册需要 WeChat 存档的所有用户，其电子邮件地址与用户的 Microsoft 365 相同。

- 你需要在组织中用户的移动电话上安装并激活该应用。 WeCom 应用允许用户与其他 WeChat 和 WeCom 用户进行通信和聊天。

- 必须为在服务器中创建 WeChat 存档Microsoft 365 合规中心用户分配邮箱导入导出Exchange Online。 这是在合规中心的"数据连接器 **"页中添加** 连接器所必需。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 此数据连接器可用于美国政府GCC中Microsoft 365环境中。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-wechat-archiver-connector"></a>创建 WeChat 存档器连接器

按照本节中的步骤在邮箱中创建微信存档Microsoft 365 合规中心。 连接器使用您提供的信息连接到 TeleMessage 站点，将 WeChat 通信数据传输至 Microsoft 365 中的相应用户邮箱。

1. 转到 ， <https://compliance.microsoft.com> 然后单击"**数据连接器**  >  **WeChat Archiver"。**

2. 在 **"WeChat 存档器** 产品说明"页上，单击" **添加连接器"**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**

    - **用户名**：你的 TeleMessage 用户名。

    - **密码**：你的 TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口转到下一页。

6. 在" **用户映射"** 页上，启用自动用户映射。 您还可以上载自定义用户映射 CSV 文件。

7. 单击 **"下** 一步"，查看设置，然后单击" **完成** "以创建连接器。

8. 转到"**数据连接器"** 页上的"连接器"选项卡以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
