---
title: 设置连接器以存档 TeleMessage 企业号码存档器的数据
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
description: 管理员可以设置连接器以从 TeleMessage 企业号码存档程序导入和存档短信和彩信数据。 这使你可以存档 Microsoft 365 中第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921742"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>设置连接器以存档企业号码数据

使用 Microsoft 365 合规中心中的 TeleMessage 连接器，从企业号码存档器导入并存档短信服务 (SMS) 和彩信服务 (MMS) 消息、聊天消息、语音呼叫录像和语音呼叫日志。 设置和配置连接器后，它每天连接到组织的 TeleMessage 帐户一次，并且使用 TeleMessage 企业号码存档器将员工的移动通信数据导入到 Microsoft 365 中的邮箱。

在 TeleMessage 企业号码存档连接器数据存储在用户邮箱中之后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于企业号码存档器数据。 例如，可以使用内容搜索来搜索 TeleMessage 企业号码存档器 SMS、MMS 和语音呼叫，或者将包含企业号码存档器连接器数据的邮箱与高级电子数据展示案例中的保管人关联。 使用企业数字存档连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-enterprise-number-data"></a>存档企业数字数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档企业网络数据的过程。

![企业数字存档工作流](../media/EnterpriseNumberConnectorWorkflow.png)

1. 您的组织与 TeleMessage 合作，以设置企业号码存档器连接器。 有关更多详细信息，请参阅 [此处](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)。

2. 在 Microsoft 365 合规中心创建的企业号码存档器连接器每天连接到 TeleMessage 网站，将过去 24 小时内的电子邮件转移到 Microsoft 云中安全的 Azure 存储区域。

3. 连接器将移动通信项目导入到特定用户的邮箱。 将创建一个名为"企业数字存档程序"的新文件夹，该文件夹将导入到特定用户的邮箱中。 连接器使用"用户的电子邮件地址" *属性的值进行映射* 。 每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。 除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含每个用户的移动号码和相应的 Microsoft 365 邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。 如果找不到与用户移动电话号码对应的有效 Microsoft 365 用户，连接器将使用电子邮件项目的"用户的电子邮件地址"属性。 如果连接器在电子邮件项目的自定义映射文件或用户的电子邮件地址属性中找不到有效的 Microsoft 365 用户，则不导入该项目。

## <a name="before-you-begin"></a>开始之前

存档企业数字存档程序数据所需的一些实现步骤位于 Microsoft 365 外部，必须先完成这些步骤，然后才能在合规中心内创建连接器。

- 从 [TeleMessage 订购企业号码存档器服务，](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 在 TeleMessage 帐户中注册需要企业号码 SMS/MMS 网络存档的所有用户。 注册用户时，请务必使用用于其 Microsoft 365 帐户的相同电子邮件地址。

- 在员工的移动电话上安装和激活 TeleMessage Enterprise Number Archiver 应用。

- 必须在 Exchange Online 中为创建企业号码存档器连接器的用户分配邮箱导入导出角色。 这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。

## <a name="create-an-enterprise-number-archiver-connector"></a>创建企业号码存档器连接器

完成上一部分中所述的先决条件后，可以在 Microsoft 365 合规中心创建企业号码存档器连接器。 连接器使用你提供的信息连接到 TeleMessage 站点，将短信、彩信和语音呼叫消息转移到 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器""** \> **企业数字存档器"。**

2. 在" **企业数字存档器** 产品说明"页上，单击" **添加连接器"**

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