---
title: 设置连接器以存档 ICE 聊天数据
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
description: 管理员可以将连接器设置为将数据从 ICE 聊天工具导入和存档到 Microsoft 365。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: c4abcc6b3ba8778616e4a9bf72955a6b6c959cd1
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937322"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data-preview"></a>设置连接器以存档 ICE 聊天数据（预览）

使用 Microsoft 365 合规性中心中的本机连接器导入并存档来自 ICE 聊天协作工具的金融服务聊天数据。 设置和配置连接器后，它每天连接到组织的 ICE 聊天安全 FTP （SFTP）站点，将聊天消息的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的邮箱中。

将 ICE 聊天数据存储在用户邮箱中之后，您可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、存档、审核、通信合规性和 Microsoft 365 保留策略）应用到 ICE 聊天数据中。 例如，可以使用内容搜索来搜索 ICE 聊天消息，或将包含 ICE 聊天数据的邮箱与高级电子数据展示事例中的管理员关联起来。 使用 ICE 聊天连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。

## <a name="overview-of-archiving-ice-chat-data"></a>存档 ICE 聊天数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 ICE 聊天数据的过程。

![ICE 聊天存档工作流](../media/ICEChatConnectorWorkflow.png)

1. 你的组织与 ICE 聊天一起设置了 ICE 聊天 SFTP 网站。 你还将使用 ICE 聊天来配置 ICE 聊天，将聊天消息复制到你的 ICE 聊天 SFTP 网站。

2. 每24小时一次，来自 ICE 聊天的聊天邮件将复制到你的 ICE 聊天 SFTP 站点。

3. 您在 Microsoft 365 合规性中心中创建的 ICE 聊天连接器每日连接到 ICE 聊天 SFTP 站点，并将聊天消息从以前的24小时传输到 Microsoft 云中的安全 Azure 存储位置。 连接器还将聊天 massage 的内容转换为电子邮件格式。

4. 连接器将聊天邮件项目导入到特定用户的邮箱。 将在用户邮箱中创建一个名为 " **ICE 聊天**" 的新文件夹，并将聊天邮件项目导入该文件夹中。 连接器通过使用*SenderEmail*和*RecipientEmail*属性的值来执行。 每个聊天邮件都包含这些属性，这些属性由发件人的电子邮件地址和聊天邮件的每个收件人/参与者填充。

   除了使用*SenderEmail*和*RecipientEmail*属性的值的自动用户映射（这意味着，连接器将聊天消息导入发件人的邮箱和每个收件人的邮箱），您还可以通过上载 CSV 映射文件来定义自定义用户映射。 此映射文件包含组织中每个用户的 ICE 聊天*ImId*和相应的 Microsoft 365 邮箱地址。 如果启用自动用户映射并提供自定义映射文件，则对于每个聊天项目，连接器将首先查看自定义映射文件。 如果找不到与用户的 ICE 聊天 ImId 对应的有效 Microsoft 365 用户帐户，连接器将使用聊天项目的*SenderEmail*和*RecipientEmail*属性将项目导入聊天参与者的邮箱中。 如果连接器在自定义映射文件或*SenderEmail*和*RecipientEmail*属性中找不到有效的 Microsoft 365 用户，则不会导入该项目。

## <a name="before-you-begin"></a>准备工作

存档 ICE 聊天数据所需的许多实施步骤在 Microsoft 365 中是外置的，并且必须先完成，然后才能在合规性中心中创建连接器。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要同意此请求，请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能在步骤3中成功创建 ICE 聊天连接器。

- ICE 研讨对客户收取外部合规性费用。 您的组织应联系 ICE 研讨销售组，以讨论和签署 "ICE 聊天数据服务" 协议，您可以在该协议中获取 [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) 。 本协议在 ICE 聊天与您的组织之间，不涉及 Microsoft。 在第2步中设置了 ICE 聊天 SFTP 网站后，"ICE 聊天" 将直接向您的组织提供 FTP 凭据。 然后，当您在步骤3中设置连接器时，将向 Microsoft 提供这些凭据。

- 在步骤3中创建连接器之前，必须设置 ICE 聊天 SFTP 站点。 在使用 ICE 聊天设置 SFTP 站点后，每日将 ICE 聊天中的数据上载到 SFTP 站点。 您在步骤3中创建的连接器将连接到此 SFTP 站点，并将聊天数据传输到 Microsoft 365 邮箱。 SFTP 还会对传输过程中发送给邮箱的 ICE 聊天数据进行加密。

- 在第3步（以及在第1步中下载公钥和 IP 地址的人）中创建 ICE 聊天连接器的管理员必须分配有 Exchange Online 中的邮箱导入导出角色。 此角色是在 Microsoft 365 合规性中心中的 "**数据连接器**" 页上添加连接器所必需的。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步骤1：获取 SSH 和 PGP 公钥

第一步是获取用于安全命令行管理程序（SSH）和相当出色的隐私（PGP）的公钥副本。 您可以使用步骤2中的这些键配置 ICE 聊天 SFTP 站点，以允许连接器（在步骤3中创建）连接到 SFTP 站点，并将 "ICE 聊天" 数据转移到 Microsoft 365 邮箱。 您还将在此步骤中获取 IP 地址，在配置 ICE 聊天 SFTP 站点时使用此地址。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 "**数据连接器**"。

2. 在 " **ICE Chat**" 下的 "**数据连接器（预览）** " 页上，单击 "**查看**"。

3. 在 " **ICE 聊天**" 页面上，单击 "**添加连接器**"。

4. 在 "**服务条款**" 页上，单击 "**接受**"。

5. 在 "步骤 1" 下的 "**添加用于 ICE 聊天的凭据**" 页面下，单击 "**下载 SSH 密钥**"、"**下载 PGP 密钥**" 和 "**下载 IP 地址**" 链接以将每个文件的副本保存到本地计算机。 这些文件包含以下用于在步骤2中配置 ICE 聊天 SFTP 网站的项：

   - SSH 公钥：此项用于配置安全 SSH，以便在连接器连接到 ICE 聊天 SFTP 站点时启用安全的远程登录。

   - PGP 公钥：此键用于配置从 ICE 聊天 SFTP 网站传输到 Microsoft 365 的数据加密。

   - IP 地址：将 ICE 聊天 SFTP 站点配置为仅接受来自此 IP 地址的连接请求，该请求由您在步骤3中创建的 ICE 聊天连接器使用。

6. 单击 "**取消**" 关闭该向导。 您将在步骤3中返回到此向导来创建连接器。

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>步骤2：配置 ICE 聊天 SFTP 站点

下一步是使用 SSH 和 PGP 公钥以及您在步骤1中获取的 IP 地址，以配置对 "ICE 聊天 SFTP" 站点的 SSH 身份验证和 PGP 加密。 这将允许您在步骤3中创建的 ICE 聊天连接器连接到 ICE 聊天 SFTP 站点，并将 ICE 聊天数据传输到 Microsoft 365。 您需要使用 "ICE 研讨" 客户支持来设置您的 ICE 聊天 SFTP 站点。

## <a name="step-3-create-an-ice-chat-connector"></a>步骤3：创建 ICE 聊天连接器

最后一步是在 Microsoft 365 合规性中心中创建 ICE 聊天连接器。 连接器使用您提供的信息连接到 ICE 聊天 SFTP 站点，并将聊天邮件传输到 Microsoft 365 中对应的用户邮箱框。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 "**数据连接器**"。

2. 在 " **ICE Chat**" 下的 "**数据连接器**" 页上，单击 "**查看**"。

3. 在 " **ICE 聊天**" 页面上，单击 "**添加连接器**"。

4. 在 "**服务条款**" 页上，单击 "**接受**"。

5. 在 "**添加用于 ICE 聊天 SFTP 网站的凭据**" 页上的 "步骤 3" 中，在以下框中输入所需信息，然后单击 "**验证连接**"。

   - **确认代码：** 您的组织的 ID，用作 ICE 聊天 SFTP 网站的用户名。

   - **密码：** 您的 ICE 聊天 SFTP 网站的密码。

   - **SFTP URL：** ICE 聊天 SFTP 网站的 URL （例如，sftp.theice.com）。

   - **SFTP 端口：** ICE 聊天 SFTP 网站的端口号。 连接器使用此端口连接到 SFTP 站点。

6. 验证连接后，单击 "**下一步**"。

7. 在 "将**外部用户映射到 Microsoft 365 用户**" 页上，启用自动用户映射并根据需要提供自定义用户映射。 您可以在此页上下载用户映射 CSV 文件的副本。 您可以将用户映射添加到文件，然后将其上传。

   > [!NOTE]
   > 如前所述，自定义映射文件 CSV 文件包含每个用户的 ICE 聊天 imid 和相应的 Microsoft 365 邮箱地址。 如果为每个聊天项目启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件。 如果找不到与用户的 ICE 聊天 imid 对应的有效 Microsoft 365 用户，则连接器会将项目导入到聊天室的*SenderEmail*和*RecipientEmail*属性中指定的用户的邮箱中。 如果连接器未通过自动或自定义用户映射找到有效的 Microsoft 365 用户，则不会导入该项目。

8. 单击 "**下一步**"，查看设置，然后单击 "**完成**" 以创建连接器。

9. 转到 "**数据连接器**" 页，查看新连接器的导入过程的进度。
