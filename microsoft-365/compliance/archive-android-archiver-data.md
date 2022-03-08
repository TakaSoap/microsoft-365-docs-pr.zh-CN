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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 管理员可以设置 TeleMessage 连接器，以从 Android 移动电话导入和存档短信、彩信和语音呼叫。 这样，您就可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 78eb94bb23b5b6f1b0801bcbfad4a6fc43022398
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325385"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>设置连接器以存档 Android 移动数据

使用 Microsoft 365 合规中心 中的 TeleMessage 连接器从 Android 移动电话导入和存档短信、彩信、语音呼叫和呼叫日志。 设置和配置连接器后，它每天连接到组织的 TeleMessage 帐户一次，并且使用 TeleMessage Android 存档器将员工的移动通信导入 Microsoft 365 中的邮箱。

将 Android 移动电话的数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 Android 存档程序数据。 例如，您可以使用内容搜索搜索 Android Archiver 移动应用，或将包含 Android 存档连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用 Android 存档器连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-android-mobile-data"></a>存档 Android 移动数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档 Android 移动数据的过程。

![Android 存档连接器工作流。](../media/AndroidArchiverConnectorWorkflow.png)

1. 你的组织与 TeleMessage 合作，以设置 Android 存档器连接器。 有关详细信息，请参阅 [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/)。

2. 实时地，来自组织的 Android 移动电话的短信、彩信、语音呼叫和呼叫日志将复制到 TeleMessage 站点。

3. 在 Microsoft 365 合规中心 创建的 Android 存档器连接器每天连接到 TeleMessage 站点，将过去 24 小时内的 Android 数据转移到 Microsoft 云中的安全 Azure 存储 位置。 连接器还会将 Android 数据转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 名为 Android Archiver 的新文件夹将创建于特定用户的邮箱中，并且项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址" *属性的值进行映射* 。 每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。 除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含每个用户Microsoft 365移动电话号码和相应的邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。 如果找不到与用户Microsoft 365用户对应的有效邮件，连接器将使用电子邮件项目的用户电子邮件地址属性。 如果连接器在自定义映射文件或Microsoft 365用户的电子邮件地址属性中找不到有效的邮件用户，该项目将不会导入。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

存档 Android 通信数据所需的一些实现步骤位于 Microsoft 365且必须先完成，然后才能在合规中心创建连接器。

- 从 [TeleMessage 订购 Android 存档器服务，](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 并获取组织的有效管理帐户。 创建连接器时，需要登录此帐户。

- 在 TeleMessage 帐户中注册需要 Android 存档器服务的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 在员工的移动电话上安装和激活 TeleMessage Android Archiver 应用。

- 必须为创建 Android 存档连接器的用户分配数据连接器管理员角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- 此 TeleMessage 数据连接器可用于美国政府GCC环境中Microsoft 365环境。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-an-android-archiver-connector"></a>创建 Android 存档器连接器

最后一步是在设备上创建 Android 存档Microsoft 365 合规中心。 连接器使用你提供的信息连接到 TeleMessage 站点，将 Android 通信转移到 Microsoft 365 中相应的用户邮箱框。

1. 转到 并 [https://compliance.microsoft.com](https://compliance.microsoft.com) 单击" **数据连接器""** > **Android 存档程序"**。

2. 在 **"Android 存档器** 产品说明"页上，单击" **添加连接器"**。

3. 在" **服务条款"页上** ，单击"接受 **"**。

4. 在" **登录到 TeleMessage** "页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"**。

   - **用户名：** 你的 TeleMessage 用户名。

   - **密码：** 你的 TeleMessage 密码。

5. 创建连接器后，关闭弹出窗口并单击"下一步 **"**。

6. 在" **用户映射"页上** ，启用自动用户映射并单击"下一步 **"**。 如果需要自定义映射上传 CSV 文件，请单击"下一步 **"**。

7. 查看设置，然后单击" **完成** "创建连接器。

8. 转到"数据连接器" **页中的"** 连接器"选项卡以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
