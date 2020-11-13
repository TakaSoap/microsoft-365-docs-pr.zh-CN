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
description: 了解管理员如何设置和使用数据连接器以将来自即时 Bloomberg 聊天工具的数据导入和存档到 Microsoft 365。
ms.openlocfilehash: 18635e6f197d954ae90c32bf5e3ae1ea8193f06d
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002357"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>设置连接器以存档 Instant Bloomberg 数据

使用 Microsoft 365 合规性中心的本机连接器从 " [即时 Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) 协作" 工具导入和存档金融 services 聊天数据。 设置和配置连接器后，它会连接到组织的 Bloomberg 安全 FTP 站点 (SFTP) 每天一次，将聊天消息的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的邮箱中。

将即时 Bloomberg 数据存储在用户邮箱中之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于即时 Bloomberg 数据。 例如，您可以使用内容搜索来搜索即时 Bloomberg 聊天邮件，或将包含即时 Bloomberg 数据的邮箱与高级电子数据展示事例中的管理员关联起来。 使用即时 Bloomberg 连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。

## <a name="overview-of-archiving-instant-bloomberg-data"></a>存档即时 Bloomberg 数据概述

以下概述说明了使用连接器在 Microsoft 365 中存档即时 Bloomberg 聊天数据的过程。 

![即时 Bloomberg 导入和存档过程](../media/InstantBloombergDataArchiving.png)

1. 您的组织与 Bloomberg 配合使用来设置 Bloomberg SFTP 站点。 您还将使用 Bloomberg 将 "即时 Bloomberg" 配置为将聊天邮件复制到 Bloomberg SFTP 站点。

2. 每24小时一次，来自即时 Bloomberg 的聊天邮件将复制到 Bloomberg SFTP 站点。

3. 您在 Microsoft 365 合规性中心中创建的即时 Bloomberg 连接器每天连接到 Bloomberg SFTP 站点，并将聊天消息从以前的24小时传输到 Microsoft 云中的安全 Azure 存储区域。 连接器还将聊天 massage 的内容转换为电子邮件格式。

4. 连接器将聊天邮件项目导入到特定用户的邮箱中。 将在特定用户的邮箱中创建一个名为 InstantBloomberg 的新文件夹，然后将这些项目导入该文件夹中。 连接器通过使用 *CorporateEmailAddress* 属性的值实现此功能。 每个聊天邮件都包含此属性，该属性由聊天消息的每个参与者的电子邮件地址填充。 除了使用 *CorporateEmailAddress* 属性的值进行自动用户映射之外，还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含每个用户的 Bloomberg UUID 和相应的 Microsoft 365 邮箱地址。 如果为每个聊天项目启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件。 如果找不到与用户的 Bloomberg UUID 对应的有效 Microsoft 365 用户，连接器将使用聊天项目的 *CorporateEmailAddress* 属性。 如果连接器在自定义映射文件或聊天项目的 *CorporateEmailAddress* 属性中找不到有效的 Microsoft 365 用户，则不会导入该项目。

## <a name="before-you-begin"></a>准备工作

存档即时 Bloomberg 数据所需的某些实施步骤是 Microsoft 365 外部的，必须先完成，然后才能在合规性中心中创建连接器。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要同意此请求，请转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能在步骤3中成功创建即时 Bloomberg 连接器。

- 订阅 [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。 这是必需的，以便您可以登录到 Bloomberg Anywhere 以访问您必须设置和配置的 Bloomberg SFTP 站点。

- 设置 Bloomberg SFTP (安全文件传输协议) 网站。 使用 Bloomberg 设置 SFTP 站点后，即时 Bloomberg 中的数据每天都将上传到 SFTP 站点。 您在步骤2中创建的连接器将连接到此 SFTP 站点，并将聊天数据传输到 Microsoft 365 邮箱。 SFTP 还对在传输过程中发送给邮箱的即时 Bloomberg 聊天数据进行加密。

  有关 Bloomberg SFTP (也称为 *BB-SFTP* ) 的信息：

  - 请参阅 [Bloomberg 支持](https://www.bloomberg.com/professional/support/documentation/)中的 "SFTP 连接标准" 文档。

  - 请联系 [Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)部门。

  在使用 Bloomberg 设置 SFTP 站点之后，在您响应 Bloomberg 实施电子邮件之后，Bloomberg 将为您提供一些信息。 保存以下信息的副本。 您可以使用它来设置步骤3中的连接器。

  - 固定代码，它是组织的 ID，用于登录到 Bloomberg SFTP 站点。

  - Bloomberg SFTP 站点的密码

  - Bloomberg SFTP 网站 (的 URL （例如，sftp.bloomberg.com) 

  - Bloomberg SFTP 站点的端口号

- 在步骤 3 (中创建即时 Bloomberg 连接器以及在第) 1 步中下载公钥和 IP 地址的用户必须在 Exchange Online 中分配邮箱导入导出角色。 这是在 Microsoft 365 合规性中心的 " **数据连接器** " 页中添加连接器所必需的。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步骤1：获取 SSH 和 PGP 公钥

第一步是获取用于安全命令行管理程序 (SSH) 的公钥副本，并获取相当出色的隐私 (PGP) 。 您可以在步骤2中使用这些键来配置 Bloomberg SFTP 站点，以允许您在步骤) 3 中创建的连接器 (以连接到 SFTP 站点，并将 "即时 Bloomberg" 聊天数据传输到 Microsoft 365 邮箱。 您还可以在此步骤中获取 IP 地址，在配置 Bloomberg SFTP 站点时使用此地址。

1. 转到 <https://compliance.microsoft.com> ，然后单击 " **数据连接器**  >  **即时 Bloomberg** "。

2. 在 " **即时 Bloomberg** 产品说明" 页上，单击 " **添加连接器** "

3. 在 " **服务条款** " 页上，单击 " **接受** "。

4. 在步骤1下的 **BLOOMBERG SFTP 网站的 "添加凭据** " 中，单击 " **下载 SSH 密钥** "、" **下载 PGP 密钥** " 和 " **下载 IP 地址** " 链接以将每个文件的副本保存到本地计算机。 这些文件包含以下用于在步骤2中配置 Bloomberg SFTP 网站的项：

   - SSH 公钥：此注册表项用于配置 (SSH) 的安全命令行管理程序，以便在连接器连接到 Bloomberg SFTP 站点时启用安全的远程登录。

   - PGP 公钥：此密钥用于配置从 Bloomberg SFTP 站点传输到 Microsoft 365 的数据的加密。

   - IP 地址： Bloomberg SFTP 站点配置为仅接受来自此 IP 地址的连接请求，该请求由您在步骤3中创建的 "即时 Bloomberg" 连接器使用。 

5. 单击 " **取消** " 关闭该向导。 您将在步骤3中返回到此向导来创建连接器。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>步骤2：配置 Bloomberg SFTP 站点

下一步是使用 SSH 和 PGP 公钥以及您在步骤1中获取的 IP 地址，以配置 Bloomberg SFTP 站点的 SSH 身份验证和 PGP 加密。 这将允许您在步骤3中创建的即时 Bloomberg 连接器连接到 Bloomberg SFTP 站点并将即时 Bloomberg 数据传输到 Microsoft 365。 您需要与 Bloomberg 客户支持部门合作，以设置 Bloomberg SFTP 站点。 请联系 [Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 以获取帮助。 

> [!IMPORTANT]
> Bloomberg 建议您将您在步骤1中下载的三个文件附加到电子邮件中，并将其发送给其客户支持团队，同时使用它们设置 Bloomberg SFTP 站点。

## <a name="step-3-create-an-instant-bloomberg-connector"></a>步骤3：创建即时 Bloomberg 连接器

最后一步是在 Microsoft 365 合规性中心中创建一个即时 Bloomberg 连接器。 连接器使用您提供的信息连接到 Bloomberg SFTP 站点，并将聊天邮件传输到 Microsoft 365 中对应的用户邮箱框中。

1. 转到 <https://compliance.microsoft.com> ，然后单击 " **数据连接器**  >  **即时 Bloomberg** "。

2. 在 " **即时 Bloomberg** 产品说明" 页上，单击 " **添加连接器** "

3. 在 " **服务条款** " 页上，单击 " **接受** "。

4. 在 " **添加 BLOOMBERG SFTP 网站的凭据** " 页上的 "步骤 3" 中的以下框中，输入所需信息，然后单击 " **下一步** "。

    - **确认代码：** 您的组织的 ID，用作 Bloomberg SFTP 站点的用户名。

    - **密码：** Bloomberg SFTP 网站的密码。

    - **SFTP URL：** Bloomberg SFTP 网站的 URL (例如，sftp.bloomberg.com) 。

    - **SFTP 端口：** Bloomberg SFTP 站点的端口号。 连接器使用此端口连接到 SFTP 站点。

5. 在 " **选择要导入的数据类型** " 页上，选择与 **邮件** 分开导入所需的数据类型

6. 在 " **用户映射** " 页上，启用自动用户映射并根据需要提供自定义用户映射

   > [!NOTE]
   > 连接器将聊天邮件项目导入到特定用户的邮箱中。 将在特定用户的邮箱中创建一个名为 **InstantBloomberg** 的新文件夹，然后将这些项目导入该文件夹中。 连接器通过使用 *CorporateEmailAddress* 属性的值来执行。 每个聊天邮件都包含此属性，并使用聊天消息的每个参与者的电子邮件地址填充该属性。 除了使用 *CorporateEmailAddress* 属性的值进行自动用户映射之外，还可以通过上载 CSV 映射文件来定义自定义映射。 映射文件应包含每个用户的 Bloomberg UUID 和相应的 Microsoft 365 邮箱地址。 如果为每个聊天项目启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件。 如果找不到与用户的 Bloomberg UUID 对应的有效 Microsoft 365 用户，连接器将使用聊天项目的 *CorporateEmailAddress* 属性。 如果连接器在自定义映射文件或聊天项目的 *CorporateEmailAddress* 属性中找不到有效的 Microsoft 365 用户，则不会导入该项目。

7. 单击 " **下一步** "，查看设置，然后单击 " **准备** " 以创建连接器。

8. 转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。
