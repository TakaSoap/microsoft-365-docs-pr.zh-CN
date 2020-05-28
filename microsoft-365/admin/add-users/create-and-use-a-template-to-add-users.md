---
title: 创建和使用模板来添加用户
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 您可以创建和使用模板来节省时间并在添加多个用户时标准化设置。
ms.openlocfilehash: 3173d28f27acdf1a084137d36cd71894e94e9547
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387221"
---
# <a name="create-and-use-a-template-to-add-users"></a>创建和使用模板来添加用户

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

您可以创建和使用模板来节省时间，并在添加多个用户时标准化设置。 如果有用户共享许多常用属性，如具有相同角色且在同一位置工作的用户以及需要同一软件的用户，则模板尤其有用。 例如，您可能拥有在同一 office 中工作的支持工程师团队。  

## <a name="create-a-template"></a>创建模板

可以轻松地创建模板 &mdash; 。可以选择 "**用户**  >  **活动用户**  >  "**用户模板**，然后从下拉列表中选择 "**添加模板**"，也可以添加新用户，完成后，可以选择将该条目保存为模板。

在添加用户后创建模板时，您为以下设置选择的值会保存在模板中：

- 域名
- 密码设置选项：可以选择创建密码或让密码自动生成
- 一次性密码选择：您可以要求用户在首次登录后创建新密码
- 许可证位置
- 许可证选择
- 应用程序选择
- Role
- 大多数配置文件信息，例如**作业配置文件**、**部门**、**办公室**、**办公室电话**和**街道地址** 

以下信息是特定于用户的，不会保存在模板中：

- 姓和名
- 可分辨名称 (DN)
- 用户名
- 以电子邮件形式发送密码以及将密码电子邮件发送到的选项
- 移动电话号码

如果选择不在部分中输入设置的信息，此值将为空，并且该设置不会显示在模板中。 例如，如果将**职务**保留为空，则在查看模板和使用模板时 **，将根本不显示职务。** 如果将所有 "**配置文件**" 部分设置保留为空，则**配置文件**部分将显示最终模板中提供的 "**无**"。

通过选择 "**添加模板**" 选项创建模板时，可以选择要完成的值。 保留为空的任何内容将显示为模板中提供的 "**无**"。

## <a name="use-a-template-to-add-a-user"></a>使用模板添加用户

若要使用现有模板添加用户，请执行以下操作：

1. 在管理中心内，选择 "**用户**  >  **活动用户**"。

2. 选择 "**用户模板**"，然后从下拉列表中选择一个模板。 （该列表将仅包含您创建的模板，而不是由其他管理员创建的模板。）

 > [!NOTE]
 > 您还可以使用模板来添加用户，方法是选择 "**用户模板**  >  " "**管理模板**"，选择一个模板，然后选择 "**使用模板**"。

3. 按照步骤操作，从所选的模板中创建用户。

> [!NOTE]
> 如果您所添加的用户的许可证不足，并且您的付款信息可用，我们将尝试使用您现有的付款信息购买另一个许可证。 如果你的付款信息不可用，则将以未授权用户的形式创建用户。

## <a name="manage-templates"></a>管理模板

您可以轻松地删除不再需要的模板并添加新模板。 若要删除模板，请执行以下操作：

1. 在管理中心内，选择 "**用户**  >  **活动用户**"。

2. 选择 "**模板**"，然后从下拉列表中选择 "**管理模板**"。

3. 将显示模板列表。 您可以通过执行以下任一操作来删除模板：
    - 选择一个或多个模板，然后选择 "**删除**"。 
    - 选择模板名称右侧的三个点，然后选择 "**删除**"。
    - 选择模板名称。 在屏幕右侧显示模板详细信息时，选择 "**删除模板**"。

## <a name="related-articles"></a>相关文章

[将用户逐个或批量添加到 Microsoft 365](add-users.md)

[从 Microsoft 365 中删除以前的员工](remove-former-employee.md)
  
