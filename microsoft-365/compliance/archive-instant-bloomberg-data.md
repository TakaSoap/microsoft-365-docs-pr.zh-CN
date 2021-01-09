---
title: 设置连接器以存档 Instant Bloomberg 数据
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解管理员如何设置和使用数据连接器将数据从 Instant Bloomberg 聊天工具导入和存档到 Microsoft 365。
ms.openlocfilehash: b7cd35e0613d9c278e8f36efc194de9dc9b5a5f2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790090"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>设置连接器以存档 Instant Bloomberg 数据

使用 Microsoft 365 合规中心中的本机连接器从 [Instant Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) 协作工具导入和存档金融服务聊天数据。 设置和配置连接器后，它将每天连接到组织的一次安全 FTP 网站 (SFTP) ，将聊天消息的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的邮箱。

Instant Bloomberg 数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Instant Bloomberg 数据。 例如，您可以使用内容搜索来搜索 Instant Bloomberg 聊天消息，或将包含 Instant Bloomberg 数据的邮箱与高级电子数据展示案例中的保管人关联。 使用 Instant Bloomberg 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府及法规政策。

## <a name="overview-of-archiving-instant-bloomberg-data"></a>存档 Instant Bloomberg 数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 Instant Bloomberg 聊天数据的过程。 

![Instant Bloomberg 导入和存档过程](../media/InstantBloombergDataArchiving.png)

1. 你的组织与 Bloomberg 合作，以设置一个 Bloomberg SFTP 网站。 你还将与 Bloomberg 合作，将 Instant Bloomberg 配置为将聊天消息复制到你的 Bloomberg SFTP 网站。

2. 每隔 24 小时一次，Instant Bloomberg 中的聊天消息会复制到一个 Bloomberg SFTP 网站。

3. 你在 Microsoft 365 合规中心创建的 Instant Bloomberg 连接器每天连接到 Bloomberg SFTP 网站，将之前 24 小时内的聊天消息转移到 Microsoft 云中安全的 Azure 存储区域。 连接器还会将聊天聊天者的内容转换为电子邮件格式。

4. 连接器将聊天消息项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建一个名为 InstantBloomberg 的新文件夹，项目将导入到该文件夹中。 连接器通过使用 *CorporateEmailAddress* 属性的值来实现此操作。 每个聊天消息都包含此属性，此属性用聊天消息每个参与者的电子邮件地址填充。 除了使用 *CorporateEmailAddress* 属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含一个 Bloomberg UUID 和每个用户的相应 Microsoft 365 邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件， 如果找不到与用户的 Bloomberg UUID 对应的有效 Microsoft 365 用户，连接器将使用聊天项目的 *CorporateEmailAddress* 属性。 如果连接器在聊天项目的自定义映射文件或 *CorporateEmailAddress* 属性中找不到有效的 Microsoft 365 用户，将不会导入该项目。

## <a name="before-you-begin"></a>准备工作

存档 Instant Bloomberg 数据所需的一些实施步骤在 Microsoft 365 外部，必须先完成，然后才能在合规中心创建连接器。

- 订阅[Bloomberg Anywhere。](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) 这是必需的，以便你可以登录到 Bloomberg Anywhere 以访问必须设置和配置的 Bloomberg SFTP 网站。

- 设置一个 Bloomberg SFTP (安全文件传输协议) 网站。 与 Bloomberg 合作设置 SFTP 网站后，Instant Bloomberg 的数据将每天上载到 SFTP 网站。 在步骤 2 创建的连接器连接到此 SFTP 网站，将聊天数据传输给 Microsoft 365 邮箱。 SFTP 还加密在传输过程中发送到邮箱的 Instant Bloomberg 聊天数据。

  有关 Bloomberg SFTP (也称为 *BB-SFTP*) ：

  - 请参阅位于 Bloomberg Support 的"SFTP 连接标准 ["文档](https://www.bloomberg.com/professional/support/documentation/)。

  - 联系 [Bloomberg 客户支持部门](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)。

  与 Bloomberg 合作设置 SFTP 网站后，在回复了 Bloomberg 实施电子邮件后，Bloomberg 会向您提供一些信息。 保存以下信息的副本。 您可以使用它在步骤 3 中设置连接器。

  - 公司代码，它是组织的 ID，用于登录到 Bloomberg SFTP 网站。

  - 你的 Bloomberg SFTP 网站的密码

  - Bloomberg SFTP 网站的 URL (例如，sftp.bloomberg.com) 

  - Bloomberg SFTP 网站的端口号

- Instant Bloomberg 连接器在一天中总共可以导入 200，000 个项目。 如果 SFTP 网站上的项目超过 200，000 个，则这些项目不会导入到 Microsoft 365。

- 在步骤 3 (中创建 Instant Bloomberg 连接器且在步骤 1) 中下载公钥和 IP 地址的用户必须在 Exchange Online 中分配邮箱导入导出角色。 这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步骤 1：获取 SSH 和 PGP 公钥

第一步是获取安全命令行管理程序 (SSH) PGP (的公钥) 。 在步骤 2 中使用这些密钥配置 Bloomberg SFTP 网站，以允许步骤 3) 中创建的连接器 (连接到 SFTP 网站，将 Instant Bloomberg 聊天数据传输给 Microsoft 365 邮箱。 您还可以在此步骤中获取 IP 地址，该地址在配置 Bloomberg SFTP 网站时使用。

1. 转到， <https://compliance.microsoft.com> 然后单击"数据 **连接器**  >  **"Instant Bloomberg。**

2. 在 **Instant Bloomberg** 产品说明页上，单击 **"添加连接器"**

3. 在"**服务条款"页上**，单击"**接受"。**

4. 在步骤 1 下的"为 **Bloomberg SFTP** 网站添加凭据"上，单击"下载 **SSH** 密钥"、"下载 **PGP** 密钥"和"下载 **IP** 地址"链接，将每个文件的副本保存到本地计算机。 这些文件包含以下项，用于配置步骤 2 中的 Bloomberg SFTP 网站：

   - SSH 公钥：此密钥用于配置安全命令行管理程序 (SSH) ，以在连接器连接到 Bloomberg SFTP 网站时启用安全远程登录。

   - PGP 公钥：此密钥用于配置从 Bloomberg SFTP 网站传输到 Microsoft 365 的数据加密。

   - IP 地址：将 Bloomberg SFTP 网站配置为仅接受来自此 IP 地址的连接请求，由你在步骤 3 创建的 Instant Bloomberg 连接器使用。 

5. 单击 **"** 取消"关闭向导。 您将在步骤 3 中返回此向导以创建连接器。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>步骤 2：配置 Bloomberg SFTP 网站

下一步是使用 SSH 和 PGP 公钥以及你在步骤 1 中获得的 IP 地址为 Bloomberg SFTP 网站配置 SSH 身份验证和 PGP 加密。 这样，你在步骤 3 创建的 Instant Bloomberg 连接器可以连接到 Bloomberg SFTP 网站，将 Instant Bloomberg 数据传输给 Microsoft 365。 你需要与 Bloomberg 客户支持合作，以设置你的 Bloomberg SFTP 网站。 请联系 [Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 寻求帮助。 

> [!IMPORTANT]
> Bloomberg 建议你在步骤 1 中下载的三个文件附加到电子邮件，并发送给客户支持团队，当与它们一起设置你的 Bloomberg SFTP 网站时。

## <a name="step-3-create-an-instant-bloomberg-connector"></a>步骤 3：创建 Instant Bloomberg 连接器

最后一步是在 Microsoft 365 合规中心创建 Instant Bloomberg 连接器。 连接器使用你提供的信息连接到 Bloomberg SFTP 网站，将聊天消息转移到 Microsoft 365 中的相应用户邮箱。

1. 转到， <https://compliance.microsoft.com> 然后单击"数据 **连接器**  >  **"Instant Bloomberg。**

2. 在 **Instant Bloomberg** 产品说明页上，单击 **"添加连接器"**

3. 在"**服务条款"页上**，单击"**接受"。**

4. 在 **"为 Bloomberg SFTP** 添加凭据"网站页面的"步骤 3"下，在下列框中输入所需信息，然后单击"下一 **步"。**

    - **公司代码：** 用作 Bloomberg SFTP 网站的用户名的组织 ID。

    - **密码：** Bloomberg SFTP 网站的密码。

    - **SFTP URL：** Bloomberg SFTP 网站的 URL (例如，sftp.bloomberg.com) 。

    - **SFTP 端口：** Bloomberg SFTP 网站的端口号。 连接器使用此端口连接到 SFTP 站点。

5. 在 **"选择要导入的数据类型** "页上，选择要从"邮件"中导入的必需 **数据类型**

6. 在 **"用户映射"** 页上，启用自动用户映射并按需要提供自定义用户映射

   > [!NOTE]
   > 连接器将聊天消息项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建一个名为 **InstantBloomberg** 的新文件夹，项目将导入到该文件夹中。 连接器使用 *CorporateEmailAddress* 属性的值进行。 每个聊天消息都包含此属性，并且使用聊天消息每个参与者的电子邮件地址填充该属性。 除了使用 *CorporateEmailAddress* 属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 映射文件应包含每个用户的 Bloomberg UUID 和相应的 Microsoft 365 邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件， 如果找不到与用户的 Bloomberg UUID 对应的有效 Microsoft 365 用户，连接器将使用聊天项目的 *CorporateEmailAddress* 属性。 如果连接器在聊天项目的自定义映射文件或 *CorporateEmailAddress* 属性中找不到有效的 Microsoft 365 用户，将不会导入该项目。

7. 单击 **"下** 一步"，查看设置，然后单击 **"准备** "创建连接器。

8. 转到" **数据连接器"** 页以查看新连接器的导入过程的进度。
