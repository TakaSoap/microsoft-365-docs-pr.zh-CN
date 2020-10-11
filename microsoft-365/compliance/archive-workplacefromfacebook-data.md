---
title: 在 Microsoft 365 中设置连接器以存档来自 Facebook 数据的工作区
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
description: 管理员可以设置连接器以将来自 Facebook 的工作区中的数据导入和存档（存档在 Globanet 的 Merge1 网站上）到 Microsoft 365。 设置连接器时，需要使用 Globanet 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: f8fadda12136d50f092dd86081b1186ab01c6e4e
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408644"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>设置连接器以存档来自 Facebook 数据的工作区

使用 Microsoft 365 合规性中心中的 Globanet 连接器在 Microsoft 365 组织中将来自 Facebook 的工作区中的数据导入和存档到用户邮箱。 Globanet 提供 [来自 Facebook 连接器的工作区](https://globanet.com/workplace/) ，该连接器配置为定期捕获第三方数据源 (中的项目) 并将这些项目导入到 Microsoft 365。 连接器将内容（如聊天、附件、帖子和视频）从工作区转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。

在将工作区数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。 使用 Facebook connector 中的工作区在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和管理法规策略。

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>从 Facebook 数据存档工作区概述

以下概述介绍了使用连接器在 Microsoft 365 中存档工作区数据的过程。

![为来自 Facebook 数据的工作区存档工作流](../media/WorkplaceConnectorWorkflow.png)

1. 你的组织使用 Facebook 中的工作区来设置和配置工作区网站。

2. 每24小时一次，将工作区中的项目复制到 Globanet Merge1 网站。 连接器还将这些项目的内容转换为电子邮件格式。

3. 你在 Microsoft 365 合规性中心创建的 Facebook 连接器中的工作区将每天连接到 Globanet Merge1，并将工作区项传输到 Microsoft 云中的安全 Azure 存储位置。

4. 连接器使用自动用户映射的 *电子邮件* 属性的值将转换后的项目导入到特定用户的邮箱中，如步骤3中所述。 创建一个名为 " **来自 Facebook 的工作区** " 的 "收件箱" 文件夹中的子文件夹，并将工作区项目导入该文件夹。 连接器通过使用 *电子邮件* 属性的值来实现此功能。 每个工作区项都包含此属性，该属性由每个聊天或帖子参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建 Globanet Merge1 帐户。 若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。 当您在步骤1中创建连接器时，需要登录到此帐户。

- 在中创建自定义集成， https://my.workplace.com/work/admin/apps/ 以通过 api 从工作区检索数据，以实现遵从性和 eDiscovery 目的。

   在创建集成时，工作区平台将生成一组唯一的凭据，用于生成用于身份验证的令牌。 这些令牌在步骤2中的 "Facebook 连接器配置向导" 中使用。 有关如何创建应用程序的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。

- 在步骤1中从 Facebook 连接器创建工作区的用户 (并在第3步中完成此操作) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。 此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。 默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>步骤1：设置来自 Facebook 连接器的工作区

第一步是访问 Microsoft 365 合规性中心中的 " **数据连接器** " 页，并为工作区数据创建连接器。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击**Data connectors**  >  **Facebook 中的**"数据连接器工作区"。

2. 在 " **来自 Facebook 的工作区** 产品说明" 页上，单击 " **添加连接器**"。

3. 在 " **服务条款** " 页上，单击 " **接受**"。

4. 输入标识连接器的唯一名称，然后单击 " **下一步**"。

5. 登录到您的 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a>步骤2：在 Globanet Merge1 网站上的 Facebook 连接器中配置工作区

第二步是在 Merge1 网站上的 Facebook 连接器中配置工作区。 有关如何从 Facebook 连接器配置工作区的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。

单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤3：映射用户并完成连接器设置

若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请按照以下步骤操作：

1. 在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。 工作区项目包含一个名为 *电子邮件* 的属性，其中包含组织中的用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。

2. 在 " **管理员同意** " 页上，单击 " **提供同意**"。 你将被重定向到 Microsoft 网站。 单击 " **接受** " 以提供许可。
  
   您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。 如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。

3. 单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>步骤4：从 Facebook 连接器监视工作区

从 Facebook 连接器创建工作区后，可以在 Microsoft 365 合规性中心中查看连接器状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。

2. 单击 " **连接器** " 选项卡，然后从 "Facebook 连接器" 中选择 " **工作区** " 以显示弹出页面，其中包含有关连接器的属性和信息。

3. 在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 较大项目的支持将在以后提供。
