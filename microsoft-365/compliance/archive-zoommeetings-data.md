---
title: 设置连接器以存档 Microsoft 365 中的缩放会议数据
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
description: 管理员可以将连接器设置为将数据从 Globanet Zoom 会议导入到 Microsoft 365。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: a94d0a776af05b609816d3fdbfede869018fa30a
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196355"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>设置连接器以存档缩放会议数据

使用 Microsoft 365 合规性中心中的 Globanet 连接器将数据从缩放会议导入到 Microsoft 365 组织中的用户邮箱。 Globanet 提供了一个 [缩放会议](https://globanet.com/zoom/) 连接器，该连接器配置为定期捕获第三方数据源中的项目 () 并将这些项目导入到 Microsoft 365。 连接器将会议的内容 (（包括聊天、录制的文件和元) 数据）从 "缩放会议" 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的 "用户邮箱" 中。

将 "缩放会议" 数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。 使用缩放会议连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和管理法规策略。

## <a name="overview-of-archiving-zoom-meetings-data"></a>存档缩放会议数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档缩放会议数据的过程。

![缩放会议存档工作流](../media/ZoomMeetingsConnectorWorkflow.png)

1. 您的组织可以使用缩放会议来设置和配置缩放会议网站。

2. 每24小时一次，来自缩放会议的会议项目将复制到 Globanet Merge1 网站。 连接器还将会议的内容转换为电子邮件格式。

3. 您在 Microsoft 365 合规中心中创建的缩放会议连接器每天连接到 Globanet Merge1，并将会议邮件传输到 Microsoft 云中的安全 Azure 存储位置。

4. 连接器使用 *电子邮件* 属性和自动用户映射的值将已转换的会议项目导入到特定用户的邮箱中，如步骤3中所述。 在用户邮箱中创建名为 " **缩放会议** " 的 "收件箱" 文件夹中的新子文件夹，并将会议项目导入该文件夹中。 连接器通过使用 *电子邮件* 属性的值来实现此功能。 每个会议项目都包含此属性，该属性填充会议的每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建 Globanet Merge1 帐户。 若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。 当您在步骤1中创建连接器时，需要登录到此帐户。

- 获取组织的缩放企业帐户或缩放企业帐户的用户名和密码。 配置缩放会议连接器时，您需要登录到步骤2中的此帐户。

- 在 [缩放 Marketplace](https://marketplace.zoom.us)中创建以下应用程序：

  - OAuth 应用程序

  - JWT 应用程序

  创建这些应用程序后，缩放平台将生成一组用于生成令牌的唯一凭据。 当连接到缩放帐户并将项目复制到 Merge1 站点时，这些令牌用于对连接器进行身份验证。 当您在步骤2中配置缩放连接器时，将使用这些令牌。

  有关如何创建 OAuth 和 JWT 应用程序的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。

- 在步骤1中创建缩放会议连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。 此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。 默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>步骤1：设置缩放会议连接器

第一步是访问 Microsoft 365 合规性中心中的 **数据连接器** ，并创建一个缩放会议连接器。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**" "  >  **缩放会议**"。

2. 在 " **缩放会议** 产品说明" 页上，单击 " **添加连接器**"。

3. 在 " **服务条款** " 页上，单击 " **接受**"。

4. 输入标识连接器的唯一名称，然后单击 " **下一步**"。

5. 登录到您的 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-zoom-meetings-connector"></a>步骤2：配置缩放会议连接器

第二步是在 Merge1 网站上配置缩放会议连接器。 有关如何在 Globanet Merge1 网站上配置缩放会议连接器的详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。

单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤3：映射用户并完成连接器设置

1. 在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。

   "缩放会议项目" 包含一个名为 *电子邮件* 的属性，其中包含组织中的用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱

2. 在 " **管理员同意** " 页面上，单击 " **提供同意** " 按钮。 你将被重定向到 Microsoft 网站。 单击 " **接受** " 以提供许可。
  
   您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。 如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。

3. 单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>步骤4：监视缩放会议连接器

创建缩放会议连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。

2. 单击 " **连接器** " 选项卡，然后选择 " **缩放会议** 连接器" 以显示弹出页面，其中包含有关连接器的属性和信息。

3. 在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 较大项目的支持将在以后提供。

- 若要使缩放会议连接器正常工作，必须在设置缩放会议时启用录制。
