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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解管理员如何设置&使用本机连接器将数据从 LinkedIn 公司页面导入到 Microsoft 365。
ms.openlocfilehash: 42183be3663fbf4b55eadde2173b492feeae5373
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619978"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>设置连接器以存档 LinkedIn 数据

使用 Microsoft 365 合规中心中的连接器从 LinkedIn 公司页面导入和存档数据。 设置和配置连接器后，它将每 24 小时连接到一次特定 LinkedIn Company 页面的帐户。 连接器将张贴到"公司"页面的邮件转换为电子邮件，然后将这些项目导入到 Microsoft 365 中的邮箱。

在邮箱中存储 LinkedIn 公司页面数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核和 Microsoft 365 保留策略）应用于 LinkedIn 数据。 例如，您可以使用内容搜索搜索这些项目，或将存储邮箱与高级电子数据展示案例中的保管人关联。 创建连接器以在 Microsoft 365 中导入和存档 LinkedIn 数据可帮助组织遵守政府政策和法规策略。

## <a name="assign-roles-and-verify-credentials"></a>分配角色并验证凭据

- 必须在 Exchange Online 中为创建 LinkedIn 公司页面连接器的用户分配邮箱导入导出角色。 这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。

- 你必须拥有作为要存档的 LinkedIn 公司 (管理员的 LinkedIn 用户帐户的电子邮件地址或电话号码和密码) 登录凭据。 设置连接器时，可以使用这些凭据登录 LinkedIn。

## <a name="create-a-linkedin-connector"></a>创建 LinkedIn 连接器

1. 转到， <https://compliance.microsoft.com> 然后单击"**数据连接器**  >  **LinkedIn Company"页**。

2. 在 **LinkedIn 公司页面** 产品页面上，单击 **"添加连接器"。**

3. 在"**服务条款"页上**，选择"**接受"。**

4. 在"**使用 LinkedIn 登录"页上**，单击 **"使用 LinkedIn 登录"。**

   将显示 LinkedIn 登录页。

   ![LinkedIn 登录页](../media/LinkedInSigninPage.png)

5. 在 LinkedIn 登录页面上，输入电子邮件地址 (或电话号码) 以及与要存档的公司页面关联的 LinkedIn 帐户的密码，然后单击"登录 **"。**

   将显示一个向导页，其中列出了与登录的帐户关联的所有 LinkedIn 公司页面。 只能为一个公司页面配置连接器。 如果组织有多个 LinkedIn 公司页面，您必须为每个页面创建一个连接器。

   ![将显示包含 LinkedIn 公司页面列表的页面](../media/LinkedInSelectCompanyPage.png)

6. 选择要存档项目的公司页面，然后单击"下一 **步"。**

7. 在 **"选择** 存储位置"页上，在框中单击，选择 LinkedIn 项目将导入到的 Microsoft 365 邮箱的电子邮件地址，然后单击"下一 **步"。** 项目将导入到此邮箱的收件箱文件夹中。

8. 单击 **"** 下一步"查看连接器设置， **然后单击"** 完成"以完成连接器设置。

创建连接器后，可以返回到"数据连接器"页以查看新连接器的导入过程的进度 **(如有必要，** 选择"刷新"以更新连接器列表) 。 状态 **列中的值是****"正在等待启动"。** 启动初始导入过程最多需要 24 小时。 连接器首次运行并导入 LinkedIn 项目后，连接器将每 24 小时运行一次，并导入前 24 小时内在 LinkedIn 公司页面上创建的任何新项。

若要查看更多详细信息，请在"数据连接器"页上的列表中选择连接器以显示该飞出页。 在 **"** 状态"下，显示的日期范围指示创建连接器时选择的年龄筛选器。

## <a name="more-information"></a>更多信息

LinkedIn 项目将导入到 Microsoft 365 中存储邮箱收件箱中的 LinkedIn 子文件夹。 它们显示为电子邮件。
