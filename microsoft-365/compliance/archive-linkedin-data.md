---
title: 设置连接器以存档 LinkedIn 数据
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解管理员如何设置&使用本机连接器将数据从 LinkedIn 公司页面导入Microsoft 365。
ms.openlocfilehash: 70d17c0cf9eaeec7110ea178f1f3db56c3d3b553
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167494"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>设置连接器以存档 LinkedIn 数据

使用 Microsoft 365 合规中心连接器从 LinkedIn 公司页面导入和存档数据。 设置和配置连接器后，它每 24 小时连接到特定 LinkedIn 公司页面的帐户一次。 连接器会将发送到"公司"页面的邮件转换为电子邮件，然后将这些项目导入到 Microsoft 365 中的邮箱。

将 LinkedIn 公司页面数据存储在邮箱中后，您可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核和 Microsoft 365 保留策略）应用于 LinkedIn 数据。 例如，您可以使用内容搜索搜索这些项目，或将存储邮箱与案例的保管人Advanced eDiscovery关联。 创建连接器以导入和存档 LinkedIn 数据Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 必须为创建 LinkedIn 公司页面连接器的用户分配邮箱导入导出Exchange Online。 在"数据连接器"页的"数据连接器"**页中添加连接器** Microsoft 365 合规中心。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 你必须拥有作为要) 存档 (LinkedIn 公司页面管理员的 LinkedIn 用户帐户的登录凭据 (电子邮件地址或电话号码和密码。 设置连接器时，使用这些凭据登录 LinkedIn。

- LinkedIn 连接器在一天中总共可以导入 200，000 个项目。 如果一天中 LinkedIn 项目超过 200，000 个，则这些项均不会导入Microsoft 365。

## <a name="create-a-linkedin-connector"></a>创建 LinkedIn 连接器

1. 转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **LinkedIn 公司页面**。

2. 在 **LinkedIn 公司页面** 产品页面上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，选择"接受 **"。**

4. 在"**使用 LinkedIn 登录"** 页上，单击 **"使用 LinkedIn 登录"。**

   将显示 LinkedIn 登录页。

   ![LinkedIn 登录页。](../media/LinkedInSigninPage.png)

5. 在 LinkedIn 登录页面上，输入与要存档的公司页面关联的 LinkedIn 帐户的电子邮件地址 (或电话号码) 和密码，然后单击"**登录"。**

   将显示向导页面，其中列出了与登录帐户关联的所有 LinkedIn 公司页面。 连接器只能为一个公司页面进行配置。 如果您的组织有多个 LinkedIn 公司页面，您必须为每个页面创建一个连接器。

   ![将显示包含 LinkedIn 公司页面列表的页面。](../media/LinkedInSelectCompanyPage.png)

6. 选择要存档其项目的公司页面，然后单击"下一步 **"。**

7. 在"**选择** 存储位置"页上，在框中单击，选择 Microsoft 365 LinkedIn 项目将导入到的邮箱的电子邮件地址，然后单击"下一步 **"。** 项目将导入到此邮箱中的收件箱文件夹。

8. 单击 **"下** 一步"查看连接器设置，然后单击" **完成** "以完成连接器设置。

创建连接器后，可以返回到"数据连接器"页以查看新连接器的导入过程的进度 (如有必要，选择"刷新"以更新连接器) 。  "状态 **"** 列中的值为 **"正在等待启动"。** 初始导入过程最多需要 24 小时才能启动。 连接器首次运行并导入 LinkedIn 项目后，连接器将每 24 小时运行一次，并导入前 24 小时内在 LinkedIn 公司页面上创建的任何新项。

若要查看更多详细信息，请在"数据连接器"页上的列表中选择 **连接器以显示该** 飞出页。 在 **"** 状态"下，显示的日期范围指示创建连接器时选择的年龄筛选器。

## <a name="more-information"></a>更多信息

LinkedIn 项目将导入到 Microsoft 365 中存储邮箱的收件箱中的 LinkedIn 子Microsoft 365。 它们显示为电子邮件。