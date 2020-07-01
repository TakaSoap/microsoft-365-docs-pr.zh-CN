---
title: 设置连接器以存档 Bloomberg 消息数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以将数据连接器设置为将数据从 Bloomberg 邮件电子邮件工具导入和存档到 Microsoft 365。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 700a0619d2299fc7254628059787478cc0e168fa
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937324"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data-preview"></a>设置连接器以存档 Bloomberg 邮件数据（预览）

使用 Microsoft 365 合规性中心中的数据连接器从[Bloomberg 邮件](https://www.bloomberg.com/professional/product/collaboration/)协作工具导入和存档金融服务电子邮件数据。 设置和配置连接器后，它每天连接到组织的 Bloomberg 安全 FTP （SFTP）站点，并将电子邮件项目导入到 Microsoft 365 中的邮箱。

将 Bloomberg 邮件数据存储在用户邮箱中之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 Bloomberg 邮件数据。 例如，您可以使用内容搜索工具搜索 Bloomberg 邮件电子邮件，或将包含 Bloomberg 邮件数据的邮箱与高级电子数据展示事例中的保管人程序相关联。 使用 Bloomberg 消息连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。

## <a name="overview-of-archiving-bloomberg-message-data"></a>存档 Bloomberg 邮件数据概述

以下概述说明了使用连接器在 Microsoft 365 中存档 Bloomberg 邮件数据的过程。

![Bloomberg 邮件导入和存档过程](../media/BloombergMessageArchiving.png)

1. 您的组织与 Bloomberg 配合使用来设置 Bloomberg SFTP 站点。 您还将使用 Bloomberg 配置 Bloomberg 邮件以将电子邮件复制到 Bloomberg SFTP 站点。

2. 每24小时一次，来自 Bloomberg 邮件的电子邮件将被复制到 Bloomberg SFTP 站点。

3. 您在 Microsoft 365 合规性中心中创建的 Bloomberg 消息连接器每天连接到 Bloomberg SFTP 站点，并将电子邮件从以前的24小时传输到 Microsoft 云中的安全 Azure 存储区域。

4. 连接器将电子邮件项导入到特定用户的邮箱。 将在特定用户的邮箱中创建一个名为 BloombergMessage 的新文件夹，然后将这些项目导入该文件夹中。 

   连接器通过使用 CorporateEmailAddress 属性的值实现此功能。 每封电子邮件都包含此属性，该属性填入电子邮件的每个参与者的电子邮件地址。 除了使用*CorporateEmailAddress*属性的值进行自动用户映射之外，还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件包含 Bloomberg UUID 以及组织中每个用户的相应 Microsoft 365 邮箱地址。 如果为每个电子邮件项目启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件。 如果找不到与用户的 Bloomberg UUID 对应的有效 Microsoft 365 用户，连接器将使用电子邮件项目的*CorporateEmailAddress*属性。 如果连接器在自定义映射文件或电子邮件项目的*CorporateEmailAddress*属性中找不到有效的 Microsoft 365 用户，则不会导入该项目。

## <a name="before-you-begin"></a>准备工作

存档 Bloomberg 邮件数据所需的许多实施步骤在 Microsoft 365 中是外部的，并且必须先完成，然后才能在合规性中心中创建连接器。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能在步骤3中成功创建 Bloomberg 邮件连接器。

- 订阅[Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。 这是必需的，以便您可以登录到 Bloomberg Anywhere 以访问您必须设置和配置的 Bloomberg SFTP 站点。

- 设置 Bloomberg SFTP （安全文件传输协议）站点。 在使用 Bloomberg 设置 SFTP 站点后，Bloomberg 邮件中的数据每天都将上传到 SFTP 站点。 您在步骤2中创建的连接器将连接到此 SFTP 站点并将电子邮件数据传输到 Microsoft 365 邮箱。 SFTP 还对在传输过程中发送给邮箱的 Bloomberg 邮件数据进行加密。

  有关 Bloomberg SFTP （也称为*BB-SFTP*）的信息，请执行以下操作：

  - 请参阅[Bloomberg 支持](https://www.bloomberg.com/professional/support/documentation/)中的 "SFTP 连接标准" 文档。

  - 请联系[Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)部门。

   > [!NOTE]
   > 如果您的组织已部署了一个连接器以存档即时 Bloomberg 数据，则无需设置另一个 SFTP 站点。 您可以对 Bloomberg 消息连接器使用相同的 SFTP 网站。

- 在使用 Bloomberg 设置 SFTP 站点之后，在您响应 Bloomberg 实施电子邮件之后，Bloomberg 将为您提供一些信息。 保存以下信息的副本。 您可以使用它来设置步骤3中的连接器。

  - 固定代码，它是组织的 ID，用于登录到 Bloomberg SFTP 站点。

  - Bloomberg SFTP 站点的密码

  - Bloomberg SFTP 网站的 URL （例如，sftp.bloomberg.com）。 此外，Bloomberg 还可能提供 Bloomberg SFTP 站点的相应 IP 地址，该地址也可用于设置连接器。

  - Bloomberg SFTP 站点的端口号

- 必须在 Exchange Online 中为在步骤3中创建 Bloomberg 邮件连接器的用户（以及在第1步中下载公钥和 IP 地址的用户）分配邮箱导入导出角色。 这是在 Microsoft 365 合规性中心的 "**数据连接器**" 页中添加连接器所必需的。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步骤1：获取 SSH 和 PGP 公钥

第一步是获取用于安全命令行管理程序（SSH）和相当出色的隐私（PGP）的公钥副本。 您可以在步骤2中使用这些键来配置 Bloomberg SFTP 站点，以允许连接器（在步骤3中创建）连接到 SFTP 站点，并将 Bloomberg 邮件电子邮件数据转移到 Microsoft 365 邮箱。 您还可以在此步骤中获取 IP 地址，在配置 Bloomberg SFTP 站点时使用此地址。

1. 转到 [ https://compliance.microsoft.com\ ] （ https://compliance.microsoft.com) 并单击左侧导航中的 "**数据连接器**"。

2. 在 " **Bloomberg 邮件**" 下的 "**数据连接器**" 页上，单击 "**查看**"。

3. 在 " **Bloomberg 邮件**产品说明" 页上，单击 "**添加连接器**"

4. 在 "**服务条款**" 页上，单击 "**接受**"。

5. 在步骤1下的**BLOOMBERG SFTP 网站的 "添加凭据**" 中，单击 "**下载 SSH 密钥**"、"**下载 PGP 密钥**" 和 "**下载 IP 地址**" 链接以将每个文件的副本保存到本地计算机。 这些文件包含以下用于在步骤2中配置 Bloomberg SFTP 网站的项：

   - SSH 公钥：此密钥用于配置安全命令行管理程序（SSH），以便在连接器连接到 Bloomberg SFTP 站点时启用安全的远程登录。

   - PGP 公钥：此密钥用于配置从 Bloomberg SFTP 站点传输到 Microsoft 365 的数据的加密。

   - IP 地址： Bloomberg SFTP 站点配置为仅接受来自此 IP 地址的连接请求，该请求由您在步骤3中创建的 Bloomberg 邮件连接器使用。

6. 单击 "**取消**" 关闭该向导。 您将在步骤3中返回到此向导来创建连接器。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>步骤2：配置 Bloomberg SFTP 站点

> [!NOTE]
> 如前所述，如果您的组织之前已将 Bloomberg SFTP 站点设置为存档即时 Bloomberg 数据，则无需设置另一个。 当您在步骤3中创建连接器时，您可以指定相同的 SFTP 站点。

下一步是使用 SSH 和 PGP 公钥以及您在步骤1中获取的 IP 地址，以配置 Bloomberg SFTP 站点的 SSH 身份验证和 PGP 加密。 这将允许您在步骤3中创建的 Bloomberg 邮件连接器连接到 Bloomberg SFTP 站点，并将 Bloomberg 邮件数据传输到 Microsoft 365。 您需要与 Bloomberg 客户支持部门合作，以设置 Bloomberg SFTP 站点。 请联系[Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)以获取帮助。

> [!IMPORTANT]
> Bloomberg 建议您将您在步骤1中下载的三个文件附加到电子邮件中，并将其发送给其客户支持团队，同时使用它们设置 Bloomberg SFTP 站点。

## <a name="step-3-create-a-bloomberg-message-connector"></a>步骤3：创建 Bloomberg 消息连接器

最后一步是在 Microsoft 365 合规性中心中创建 Bloomberg 邮件连接器。 连接器使用您提供的信息来连接到 Bloomberg SFTP 站点，并将电子邮件传输到 Microsoft 365 中对应的用户邮箱框。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 "**数据连接器**"。

2. 在 " **Bloomberg 邮件**" 下的 "**数据连接器**" 页上，单击 "**查看**"。

3. 在 " **Bloomberg 邮件**产品说明" 页上，单击 "**添加连接器**"

4. 在 "**服务条款**" 页上，单击 "**接受**"。

5. 在 "**添加 BLOOMBERG SFTP 网站的凭据**" 页上的 "步骤 3" 中的以下框中，输入所需信息，然后单击 "**下一步**"。

      - **确认代码：** 您的组织的 ID，用作 Bloomberg SFTP 站点的用户名。

      - **密码：** 组织的 Bloomberg SFTP 站点的密码。

      - **SFTP URL：** Bloomberg SFTP 网站的 URL （例如，sftp.bloomberg.com）。

      - **SFTP 端口：** Bloomberg SFTP 站点的端口号。 连接器使用此端口连接到 SFTP 站点。

6. 在 "**用户映射**" 页上，启用自动用户映射并根据需要提供自定义用户映射

7. 单击 "**下一步**"，查看设置，然后单击 "准备" 以创建连接器。

8. 转到 "**数据连接器**" 页，查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 不支持导入到 Microsoft 365 的 Bloomberg 邮件电子邮件的线程。 发送给个人的单个邮件将被导入，但不会显示在线程对话中。 Microsoft 正在努力支持 Bloomberg 消息数据连接器的更高版本中的线程。
