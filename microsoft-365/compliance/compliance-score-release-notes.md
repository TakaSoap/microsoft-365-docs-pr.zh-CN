---
title: Microsoft 合规性分数发行说明
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性分数的发行说明和已知问题（预览版）（M365 合规性中心中的一项功能，可帮助简化和自动化风险评估）。
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022189"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 合规性分数（预览）发行说明

**本文内容：** 此页面显示[Microsoft 合规性分数](compliance-score.md)的公共预览中的**新增**功能，这为你提供了对新功能的早期访问权限。

## <a name="assessment-creation-and-management-functionality"></a>评估创建和管理功能

2020年6月发布的版本为用户添加了用于在合规性分数中直接创建、删除和管理评估的功能。 以前，所有评估管理都驻留在合规性管理器中。 当您在合规性分数中创建或修改评估时，更新将在合规性管理器中呈现。 同样，在合规性管理器中执行的任何评估工作都会在合规性分数中显示出来。 了解如何[在合规性分数中管理评估](compliance-score-assessments.md)。 请注意，模板创建和修改仍在合规性管理器中进行管理。

## <a name="new-templates-for-assessments"></a>新的评估模板

新的准备好使用模板进行评估的功能将在合规性分数中发布，在它们变得可用时发布。 [在此处查看模板的完整列表](compliance-score-templates.md)。 最近添加的：

- 迪拜信息安全解决方案（DGISR）

## <a name="compliance-score-relationship-to-compliance-manager"></a>与合规性管理器的合规性分数关系

现在，在合规性管理器中处理的许多函数都可以在合规性分数中完成。 但是，一些功能仍在合规性管理器中。 在公共预览版过程中使用合规性分数和合规性管理器时，请牢记以下几点：

 - **创建用于评估的模板**： 
   - 用户必须转到合规性管理器以[创建新模板并修改现有模板](working-with-compliance-manager.md#templates)。
   - 新模板必须包括**产品**和**证书**的尺寸。
 - **设置权限**：合规性分数尚未在合规性管理器中拥有权限的用户需要在 Microsoft 365 合规性中心中设置其权限（[了解详细信息](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。
- **数据传输**：具有合规性管理器中的数据的组织将看到符合性分数中的数据，而与此不同的方法也是如此。
- **根据合规性分数登录合规性管理器**：如果用户已登录合规性分数并选择链接以转到合规性管理器，则用户不必再次登录。 单击该链接后，将在浏览器中打开一个新的选项卡，其中带有一个对话框。 在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？ 登录您的帐户，选择 "**登录**" 按钮以自动登录合规性管理器。

## <a name="known-issues-in-compliance-score-preview"></a>合规性分数中的已知问题（预览）

以下各节介绍了在即将发布的合规性分数中要解决的已知问题。

### <a name="long-load-times-for-non-admin-users"></a>非管理员用户的长时间加载时间
合规性分数在尝试登录时，保留非管理员角色角色的用户可能会遇到较长的加载时间。 刷新浏览器将解决此问题。 了解有关[合规性分数角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)的详细信息。

### <a name="supported-browsers"></a>支持的浏览器

- Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。
- 在刷新浏览器之前，有时不会显示更新后的数据。
- 不支持 Internet Explorer。
