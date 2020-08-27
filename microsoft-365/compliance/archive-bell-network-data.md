---
title: 设置连接器以存档铃声短信/MMS 网络数据
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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置 TeleMessage 连接器以导入和存档来自电铃网络的 SMS 和 MMS 数据。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: bc775a4a1e5494e7e21b272dc6e468a63c18e814
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282640"
---
# <a name="set-up-a-connector-to-archive-bell-network-data-preview"></a>设置连接器以存档铃声网络数据 (预览) 

使用 Microsoft 365 合规性中心中的 TeleMessage 连接器导入和存档短信服务 (SMS) 和多媒体邮件服务 (MMS) 来自电铃网络的邮件。 设置和配置连接器后，它每天连接到组织的响铃网络一次，并将短信和 MMS 邮件导入到 Microsoft 365 中的邮箱。

在将短信和 MMS 邮件存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、内容搜索和 Microsoft 365 保留策略，以响铃网络数据。 例如，可以使用内容搜索来搜索铃声网络短信/MMS，或将包含铃声网络连接器数据的邮箱与高级电子数据展示事例中的管理员关联起来。 使用铃声网络连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。

## <a name="overview-of-archiving-bell-network-data"></a>存档铃声网络数据概述

以下概述说明了使用连接器在 Microsoft 365 中存档铃声网络数据的过程。

![铃声网络存档工作流](../media/BellNetworkConnectorWorkflow.png)

1. 您的组织使用 TeleMessage 和电铃设置电铃网络连接器。 有关详细信息，请参阅 [铃声网络存档](https://www.telemessage.com/office365-activation-for-bell-network-archiver)。

2. 每24小时一次，来自组织的铃声网络的 SMS 和 MMS 邮件将复制到 TeleMessage 站点。

3. 您在 Microsoft 365 合规性中心中创建的电铃网络连接器每天连接到 TeleMessage 网站，并将短信和 MMS 邮件从以前的24小时传输到 Microsoft 云中的安全 Azure 存储位置。 连接器还将短信和 MMS 邮件的内容转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 在特定用户的邮箱中创建一个名为 " **电铃 SMS/MMS 网络存档** " 的新文件夹，并将这些项目导入其中。 连接器通过使用 *用户的电子邮件地址* 属性的值执行此映射。 每个短信和 MMS 邮件都包含此属性，该属性由邮件的每个参与者的电子邮件地址填充。

   除了使用 *用户电子邮件地址* 属性的值进行自动用户映射之外，还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件包含组织中用户的移动电话号码和相应的 Microsoft 365 电子邮件地址。 如果为每个电铃网络项启用了自动用户映射和自定义映射，则连接器将首先查找自定义映射文件。 如果找不到与用户的移动电话号码对应的有效 Microsoft 365 用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。 如果连接器在自定义映射文件中或在电铃网络项的电子邮件地址属性中找不到有效的 Microsoft 365 用户，则不会导入该项目。

## <a name="before-you-begin"></a>准备工作

存档电铃网络数据所需的许多实施步骤都是 Microsoft 365 外部的，必须先完成，然后才能在合规性中心中创建连接器。

- [从 TeleMessage 中对电铃网络存档服务](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)进行排序，并为您的组织获取有效的管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 获取您的铃声网络帐户和计费联系人详细信息，以便您可以填写 TeleMessage 载入表单，并从电铃中对邮件存档服务进行排序。

- 在 TeleMessage 帐户中注册需要震铃短信/MMS 网络存档的所有用户。 注册用户时，请确保使用的电子邮件地址与用于其 Microsoft 365 帐户的电子邮件地址相同。

- 你的员工必须在响铃移动网络上拥有公司拥有和公司责任的移动电话。 在 Microsoft 365 中存档邮件不适用于员工拥有或 "将自己的设备 (BYOD) 设备。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 您需要在创建连接器时提供此同意。 若要同意此请求，请转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能成功创建电铃网络连接器。

- 必须在 Exchange Online 中为创建电铃网络连接器的用户分配邮箱导入导出角色。 这是在 Microsoft 365 合规性中心的 " **数据连接器** " 页中添加连接器所必需的。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

## <a name="create-a-bell-network-connector"></a>创建电铃网络连接器

最后一步是在 Microsoft 365 合规性中心中创建电铃网络连接器。 连接器使用您提供的信息来连接到 TeleMessage 网站，并将 SMS/MMS 邮件传输到 Microsoft 365 中对应的用户邮箱框中。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后单击 "**数据连接器**"  >  **铃声短信/MMS 网络存档**。

2. 在 "**电铃网络**产品说明" 页上，单击 "**添加连接器**"

3. 在 " **服务条款** " 页上，单击 " **接受**"。

4. 在 " **登录到 TeleMessage** " 页上的 "步骤 3" 下的以下框中，输入所需信息，然后单击 " **下一步**"。

   - **Username：** 您的 TeleMessage 用户名。

   - **密码：** 您的 TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口并转到下一页。

6. 在 " **用户映射** " 页上，启用自动用户映射。 若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击 " **下一步**"。

7. 提供管理员同意，然后单击 " **下一步**"。

   若要提供管理员同意，必须使用 Office 365 全局管理员的凭据登录，然后接受同意请求。 如果你未以全局管理员身份登录，则可以转到 [此页面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 并使用全局管理员凭据登录以接受请求。

8. 查看您的设置，然后单击 " **完成** " 以创建连接器。

9. 转到合规中心 "**数据连接器**" 页上的 "**连接器**" 选项卡，以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 连接器未导入任何大于 10 MB 的项目。
