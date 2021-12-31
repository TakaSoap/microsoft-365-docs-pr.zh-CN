---
title: 设置连接器以在 Microsoft 365
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
description: 管理员可以设置 TeleMessage 连接器，以在 Microsoft 365 中导入和存档用户网络Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: cdeeb8956620321b83bdd6b1ce85c656e7946936
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643528"
---
# <a name="set-up-a-connector-to-archive-rogers-network-data"></a>设置连接器以存档显示网络数据

使用企业版中的 TeleMessage 连接器Microsoft 365 合规中心并存档来自用户移动网络的短信和彩信数据。 在设置和配置[一个一个显示](https://www.telemessage.com/mobile-archiver/network-archiver/rogers/)连接器后，它将连接到您组织的为 Your Organization 的则移动网络，并导入短信和彩信数据到 Microsoft 365 中的邮箱。

在用户邮箱中存储了来自为用户网络提供的数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于数据。 例如，您可以使用内容搜索或与核心电子数据展示案例关联的搜索，搜索来自具有 Mobiles 移动网络的短信和彩信。 使用为组织导入和存档数据而使用 Microsoft 365 存档连接器可帮助组织遵守公司管理法规和法规策略。

## <a name="overview-of-archiving-rogers-mobile-network-data"></a>存档用户移动网络数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档用户短信和彩信Microsoft 365。

![Exchanges 网络存档工作流。](../media/RogersNetworkConnectorWorkflow.png)

1. 你的组织与 TeleMessage 合作，以设置一个"设置一个为"的"设置"网络存档器连接器。 有关详细信息，请参阅激活[TeleMessage 用于远程存档的 TeleMessage Microsoft 365。](https://www.telemessage.com/microsoft-365-activation-for-the-rogers-network-archiver/)

2. 实时地，您组织的管理组织移动网络数据将复制到 TeleMessage 网站。

3. 在 Microsoft 365 合规中心 创建的部署网络存档器连接器每天连接到 TeleMessage 网站，将过去 24 小时内的电子邮件转移到 Microsoft 云中的安全 Azure 存储 区域。

4. 连接器将移动通信项目导入到特定用户的邮箱。 将在特定用户的邮箱中创建名为"一条 Sms/MMS 网络存档器"的新文件夹，并且项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址" *属性的值执行映射* 。 每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。

   除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件应包含用户的移动电话号码和每个用户Microsoft 365相应的邮箱地址。 如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。 如果找不到与用户Microsoft 365用户对应的有效邮件，连接器将使用电子邮件项目的用户电子邮件地址属性。 如果连接器在自定义映射文件或Microsoft 365项的电子邮件地址属性中找不到有效的邮件用户，该项目将不会导入。 

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 从 [TeleMessage 订购一个为它准备的网络](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 存档器服务，并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 在 TeleMessage 帐户中注册需要为用户进行管理网络存档的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 你的员工必须在 O2 移动网络上拥有公司拥有和负责企业的移动电话。 存档 MICROSOFT 365中的消息不适用于员工拥有或"自带设备 (BYOD) 设备。

- 获取组织的管理帐户和帐单联系人详细信息，以便你可以填写载入表单，并订购来自为用户的邮件存档服务。

- 必须在步骤 3 中为在步骤 3 中创建一个管理程序网络存档器连接器的用户分配邮箱导入导出Exchange Online。 在"数据连接器"页的"数据连接器"页中添加连接器Microsoft 365 合规中心。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

- 此 TeleMessage 数据连接器可用于美国政府云GCC环境中Microsoft 365环境。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-rogers-network-archiver-connector"></a>创建一个设置网络存档器连接器

完成上一部分中所述的先决条件后，可以在部署中创建 Microsoft 365 合规中心。 连接器使用你提供的信息连接到 TeleMessage 站点，将一条短信/彩信数据传输给 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **系统网络存档器**。

2. 在 **"确定网络存档器** 产品说明"页上，单击"**添加连接器"。**

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
