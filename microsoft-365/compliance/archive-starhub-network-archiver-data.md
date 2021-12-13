---
title: 设置连接器以将 StarHub 移动网络数据存档到Microsoft 365
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
description: 管理员可以设置 TeleMessage 连接器，以从 Microsoft 365 中的 StarHub 移动网络导入和存档Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 8f1c56259f2eb3fed5c78277aa7597d195a1c824
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61424015"
---
# <a name="set-up-a-connector-to-archive-starhub-network-data-preview"></a>设置连接器以存档 StarHub 网络数据 (预览) 

使用 Microsoft 365 合规中心 中的 TeleMessage 连接器从 StarHub 移动网络导入和存档语音呼叫数据。 设置和配置 StarHub 网络存档连接器后，它将连接到组织的 StarHub 移动网络，将语音呼叫数据导入到 Microsoft 365 中的邮箱。

将 StarHub 移动网络数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于数据。 例如，可以使用内容搜索或与核心电子数据展示案例关联的搜索，从 StarHub 移动网络搜索短信和彩信。 使用 StarHub 网络存档连接器在 Microsoft 365 导入和存档数据可帮助组织遵守企业管理法规和法规策略。

## <a name="overview-of-archiving-starhub-mobile-network-data"></a>存档 StarHub 移动网络数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档 StarHub 语音呼叫Microsoft 365。

![StarHub 网络存档工作流。](../media/StarHubNetworkConnectorWorkflow.png)

1. 你的组织与 TeleMessage 合作，以设置 StarHub 网络存档器连接器。 有关详细信息，请参阅激活[TeleMessage StarHub Network Archiver for Microsoft 365](https://www.telemessage.com/activating-the-telemessage-starhub-network-archiver-connector-for-microsoft-365/)。

2. 实时将组织的 StarHub 移动网络数据复制到 TeleMessage 网站。

3. 在 Microsoft 365 合规中心 中创建的 StarHub 网络存档器连接器每天连接到 TeleMessage 网站，将过去 24 小时内的电子邮件转移到 Microsoft 云中的安全 Azure 存储 区域。

4. 连接器将移动通信项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建名为 StarHub SMS/MMS 网络存档程序的新文件夹，并且项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址" *属性的值执行映射* 。 每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。

   除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含用户的移动电话号码和每个用户Microsoft 365相应的邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。 如果找不到与用户Microsoft 365用户对应的有效邮件，连接器将使用电子邮件项目的用户电子邮件地址属性。 如果连接器在自定义映射文件或Microsoft 365项的电子邮件地址属性中找不到有效的邮件用户，该项目将不会导入。 

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 从 [TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 订购 StarHub 网络存档器服务，并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 在 TeleMessage 帐户中注册需要 StarHub 网络存档的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 在员工的移动电话上安装并激活 TeleMessage Voice Call Archiver 应用。 有关详细信息，请参阅[TeleMessage Voice Call Archiver Onboarding Guide。](https://www.telemessage.com/voice-call-archiver-forwarding-incoming-calls/)

- 必须在步骤 3 中为在步骤 3 中创建 StarHub 网络存档器连接器的用户分配邮箱导入导出Exchange Online。 在"数据连接器"页的"数据连接器"页中添加连接器Microsoft 365 合规中心。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="create-a-starhub-network-archiver-connector"></a>创建 StarHub 网络存档器连接器

完成上一部分中所述的先决条件后，可以在部署中心内创建 StarHub 网络存档Microsoft 365 合规中心。 连接器使用你提供的信息连接到 TeleMessage 站点，将 StarHub 语音呼叫数据转移到 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **StarHub 网络存档器**。

2. 在 **StarHub 网络存档器** 产品说明页面上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**

    - **用户名：** 你的 TeleMessage 用户名。

    - **密码：** 你的 TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口并转到下一页。

6. 在" **用户映射"** 页上，启用自动用户映射。 若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击"下一步 **"。**

7. 查看设置，然后单击" **完成** "创建连接器。

8. 转到"数据连接器" **页中的"** 连接器"选项卡以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
