---
title: 创建和使用模板来添加用户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 您可以在添加多个用户时创建并使用模板来节省时间和标准化设置。
ms.openlocfilehash: cacb3fc6ef2a145cbfe4c4131b2e5e38eca2c257
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161842"
---
# <a name="create-and-use-a-template-to-add-users"></a>创建和使用模板来添加用户

您可以在添加多个用户时创建并使用模板来节省时间和标准化设置。 如果你的用户拥有共享许多常见属性的用户，例如那些角色相同且在同一位置工作的用户和需要相同软件的用户，则模板尤其有用。 例如，您可能有一个支持工程师团队在同一个办公室工作。  

## <a name="create-a-template"></a>创建模板

模板易于创建，您可以选择"用户""活动用户""用户模板"，然后从下拉列表中选择"添加模板"，也可以添加新用户，完成后，您可以选择将条目另存为模板。 &mdash;   >    >   

添加用户后创建模板时，为以下设置选择的值将保存在模板中：

- 域名
- 密码设置选择：可以选择创建密码或自动生成密码
- 一次密码选择：可以要求用户在首次登录后创建新密码
- 许可证位置
- 许可证选择
- 应用程序选择
- Role
- 大多数个人资料信息，例如作业 **配置文件**、**部门****、Office、Office****电话和****街道地址** 

以下信息特定于用户，不会保存在模板中：

- 姓和名
- 显示名称
- 用户名
- 选择通过电子邮件发送密码以及向谁发送密码电子邮件
- 移动电话号码

如果选择不输入部分中设置的信息，该值将为空，并且该设置不会显示在模板中。 例如， **如果将"职务** "留空，在查看模板时以及使用模板时，" **职务"将** 完全不显示。 如果将所有 **"配置文件"** 部分设置留空，" **配置文件** "部分将显示最终 **模板中** 提供的"无"。

通过选择"添加模板"选项创建模板 **时** ，可以选择要完成的值。 任何保留为空的内容都将显示为 **模板中提供的** "无"。

## <a name="use-a-template-to-add-a-user"></a>使用模板添加用户

若要使用现有模板添加用户，

1. 在管理中心中，选择"**用户**  >  **""活动用户"。**

2. 选择 **"用户模板**"，然后从下拉列表中选择模板。  (列表将仅包含你创建的模板，而不包含由其他管理员创建的模板) 

   > [!NOTE]
   > You can also use a template to add a user by selecting **User templates** Manage  >  **templates，** selecting a template， and then selecting **Use template**.

3. 按照步骤从所选的模板创建用户。

   > [!NOTE]
   > 如果你添加的用户可用的许可证不足，并且你的付款信息可用，我们将尝试使用你的现有付款信息购买另一个许可证。 如果付款信息不可用，用户将被创建为未授权用户。

## <a name="manage-templates"></a>管理模板

只能删除不再需要的模板并添加新模板。 删除模板：

1. 在管理中心中，选择"**用户**  >  **""活动用户"。**

2. 选择 **"模板**"，然后 **从** 下拉列表中选择"管理模板"。

3. 将显示模板列表。 可以通过执行以下任一操作来删除模板：
    - 选择一个或多个模板， **然后选择删除**。 
    - 选择模板名称右边的三个点， **然后选择删除**。
    - 选择模板名称。 当模板详细信息显示在屏幕右侧时，选择"删除 **模板"。**

## <a name="related-articles"></a>相关文章

[同时添加用户和分配许可证](add-users.md)

[从公司中删除以前的Microsoft 365](remove-former-employee.md)
  
