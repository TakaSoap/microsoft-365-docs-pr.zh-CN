---
title: 设置连接器以存档 Bloomberg 邮件数据
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
description: 管理员可以设置一个数据连接器，以将数据从 Bloomberg Message 电子邮件工具导入和存档到 Microsoft 365。 这允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如法定保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 0f08c4ff43cd868b95b965673cfbdd3308ed801f
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620058"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>设置连接器以存档 Bloomberg 邮件数据

使用 Microsoft 365 合规中心内的数据连接器从 [Bloomberg 邮件](https://www.bloomberg.com/professional/product/collaboration/) 协作工具导入和存档金融服务电子邮件数据。 设置和配置连接器后，它将每天连接到组织的一次安全 FTP (SFTP) 网站，将电子邮件项目导入到 Microsoft 365 中的邮箱。

在将 Bloomberg 邮件数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Bloomberg Message 数据。 例如，您可以使用内容搜索工具搜索 Bloomberg Message 电子邮件，或将包含 Bloomberg 邮件数据的邮箱与高级电子数据展示案例中的保管人关联。 使用一个 Bloomberg 邮件连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规政策。

## <a name="overview-of-archiving-bloomberg-message-data"></a>存档 Bloomberg 邮件数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 Bloomberg Message 数据的过程。

![Bloomberg 邮件导入和存档过程](../media/BloombergMessageArchiving.png)

1. 你的组织与 Bloomberg 合作，以设置一个 Bloomberg SFTP 网站。 You'll also work with Bloomberg to configure Bloomberg Message to copy email messages to the Bloomberg SFTP site.

2. 每 24 小时一次，来自 Bloomberg Message 的电子邮件将复制到 Bloomberg SFTP 网站。

3. 你在 Microsoft 365 合规中心创建的 Bloomberg 邮件连接器每天连接到 Bloomberg SFTP 网站，将过去 24 小时内的电子邮件转移到 Microsoft 云中安全的 Azure 存储区域。

4. 连接器将电子邮件项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建一个名为 BloombergMessage 的新文件夹，项目将导入到该文件夹中。 

   连接器通过使用 CorporateEmailAddress 属性的值来实现此操作。 每个电子邮件都包含此属性，此属性填充了电子邮件每个参与者的电子邮件地址。 除了使用 *CorporateEmailAddress* 属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件包含一个 Bloomberg UUID 和组织中每个用户的相应 Microsoft 365 邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件， 如果找不到与用户的 Bloomberg UUID 对应的有效 Microsoft 365 用户，连接器将使用电子邮件项目的 *CorporateEmailAddress* 属性。 如果连接器在电子邮件项目的自定义映射文件或 *CorporateEmailAddress* 属性中找不到有效的 Microsoft 365 用户，将不会导入该项目。

## <a name="before-you-begin"></a>开始之前

存档 Bloomberg Message 数据所需的一些实施步骤在 Microsoft 365 外部，必须先完成，然后才能在合规中心创建连接器。

- 订阅[Bloomberg Anywhere。](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA) 这是必需的，以便你可以登录到 Bloomberg Anywhere 以访问必须设置和配置的 Bloomberg SFTP 网站。

- 设置一个 Bloomberg SFTP (安全文件传输协议) 网站。 与 Bloomberg 合作设置 SFTP 网站后，将每天将一条来自 Bloomberg Message 的数据上载到 SFTP 网站。 在步骤 2 创建的连接器连接到此 SFTP 网站，将电子邮件数据传输给 Microsoft 365 邮箱。 SFTP 还加密在传输过程中发送到邮箱的一系列邮件数据。

  有关 Bloomberg SFTP (也称为 *BB-SFTP*) ：

  - 请参阅位于 Bloomberg Support 的"SFTP 连接标准 ["文档](https://www.bloomberg.com/professional/support/documentation/)。

  - 联系 [Bloomberg 客户支持人员](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)。

   > [!NOTE]
   > 如果组织已部署连接器来存档 Instant Bloomberg 数据，则无需设置其他 SFTP 网站。 您可以对 Bloomberg 邮件连接器使用相同的 SFTP 网站。

- 与 Bloomberg 合作设置 SFTP 网站后，在回复了 Bloomberg 实施电子邮件后，Bloomberg 会向您提供一些信息。 保存以下信息的副本。 您可以使用它在步骤 3 中设置连接器。

  - 公司代码，它是组织的 ID，用于登录到 Bloomberg SFTP 网站。

  - 你的 Bloomberg SFTP 网站的密码

  - Bloomberg SFTP 网站的 URL (例如，sftp.bloomberg.com) 。 此外，Bloomberg 还可以为 Bloomberg SFTP 网站提供相应的 IP 地址，该地址还可用于设置连接器。

  - Bloomberg SFTP 网站的端口号

- 在步骤 3 (中创建一个 Bloomberg 邮件连接器且在步骤 1) 中下载公钥和 IP 地址的用户必须在 Exchange Online 中分配邮箱导入导出角色。 这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步骤 1：获取 SSH 和 PGP 公钥

第一步是获取安全命令行管理程序 (SSH) PGP (的公钥) 。 在步骤 2 中使用这些密钥来配置 Bloomberg SFTP 网站，以允许步骤 3) 中创建的连接器 (连接到 SFTP 网站，将一封"一文"邮件电子邮件数据传输给 Microsoft 365 邮箱。 您还可以在此步骤中获取 IP 地址，该地址在配置 Bloomberg SFTP 网站时使用。

1. 转到 [ https://compliance.microsoft.com\ https://compliance.microsoft.com) ] (，然后单击左侧导航中的"数据连接器"。

2. 在"**数据连接器"** 页上的 **"一条"，单击**"**视图"。**

3. 在 **"Bloomberg 邮件** "产品说明页上，单击 **"添加连接器"**

4. 在"**服务条款"页上**，单击"**接受"。**

5. 在步骤 1 下的"为 **Bloomberg SFTP** 网站添加凭据"上，单击"下载 **SSH** 密钥"、"下载 **PGP** 密钥"和"下载 **IP** 地址"链接，将每个文件的副本保存到本地计算机。 这些文件包含以下项，用于配置步骤 2 中的 Bloomberg SFTP 网站：

   - SSH 公钥：此密钥用于配置安全命令行管理程序 (SSH) ，以在连接器连接到 Bloomberg SFTP 网站时启用安全远程登录。

   - PGP 公钥：此密钥用于配置从 Bloomberg SFTP 网站传输到 Microsoft 365 的数据加密。

   - IP 地址：将 Bloomberg SFTP 网站配置为仅接受来自此 IP 地址的连接请求，该 IP 地址由你在步骤 3 创建的 Bloomberg 邮件连接器使用。

6. 单击 **"** 取消"关闭向导。 在步骤 3 中返回到此向导以创建连接器。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>步骤 2：配置 Bloomberg SFTP 网站

> [!NOTE]
> 如前所述，如果你的组织之前已经设置了一个 Bloomberg SFTP 网站来存档 Instant Bloomberg 数据，则不必设置另一个。 可以在步骤 3 中创建连接器时指定相同的 SFTP 站点。

下一步是使用 SSH 和 PGP 公钥以及你在步骤 1 中获得的 IP 地址为 Bloomberg SFTP 网站配置 SSH 身份验证和 PGP 加密。 这样，你在步骤 3 中创建的 Bloomberg 邮件连接器可以连接到 Bloomberg SFTP 网站，将 Bloomberg 邮件数据传输给 Microsoft 365。 你需要与 Bloomberg 客户支持合作，以设置你的 Bloomberg SFTP 网站。 请联系 [Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 寻求帮助。

> [!IMPORTANT]
> Bloomberg 建议你在步骤 1 中下载的三个文件附加到电子邮件，并发送给客户支持团队，当与它们一起设置你的 Bloomberg SFTP 网站时。

## <a name="step-3-create-a-bloomberg-message-connector"></a>步骤 3：创建一个 Bloomberg 邮件连接器

最后一步是在 Microsoft 365 合规中心创建一个 Bloomberg 邮件连接器。 连接器使用你提供的信息连接到 Bloomberg SFTP 网站，将电子邮件转移到 Microsoft 365 中的相应用户邮箱。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。

2. 在"**数据连接器"** 页上的 **"一条"，单击**"**视图"。**

3. 在 **"Bloomberg 邮件** "产品说明页上，单击 **"添加连接器"**

4. 在"**服务条款"页上**，单击"**接受"。**

5. 在 **"为 Bloomberg SFTP** 添加凭据"网站页面的"步骤 3"下，在下列框中输入所需信息，然后单击"下一 **步"。**

      - **公司代码：** 用作 Bloomberg SFTP 网站的用户名的组织 ID。

      - **密码：** 贵组织的 Bloomberg SFTP 网站的密码。

      - **SFTP URL：** 例如，为一个 (SFTP 网站的 URL，sftp.bloomberg.com) 。

      - **SFTP 端口：** Bloomberg SFTP 网站的端口号。 连接器使用此端口连接到 SFTP 站点。

6. 在 **"用户映射"** 页上，启用自动用户映射并按需要提供自定义用户映射

7. 单击 **"下** 一步"，查看设置，然后单击"准备"创建连接器。

8. 转到" **数据连接器"** 页以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 不支持对导入到 Microsoft 365 的 Bloomberg 邮件电子邮件进行线程处理。 发送给某人的单个邮件将被导入，但它们不会在线程对话中显示。 Microsoft 致力于在更高版本的 Bloomberg 邮件数据连接器中支持线程处理。
