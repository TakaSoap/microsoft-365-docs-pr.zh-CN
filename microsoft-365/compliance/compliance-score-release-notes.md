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
ms.openlocfilehash: 1567921b8bd07b0fe4deda0bab6601898eed75a9
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330776"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 合规性分数（预览）发行说明

Microsoft 合规性分数的公开预览为你提供了对即将推出的功能和更新的早期访问权限。 请经常查看此页面，了解新增功能。

合规性分数是[Microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的一项新功能，可计算基于风险的分数，从而衡量完成建议的操作以帮助降低合规性风险的进度。

## <a name="new-templates-for-assessments"></a>新的评估模板

将新的预先配置的模板发布到生产中，以便在符合性分数（预览）变得可用时发布这些模板。 [在此处查看模板的完整列表](compliance-score.md#templates)。 最近添加的模板包括：

- 巴西常规数据保护法律（LGPD）
- 迪拜信息安全解决方案（DGISR）
- IRAP/澳大利亚政府版 ISM （预览）
- ISO 27701:2019
- SOC 1
- SOC 2

## <a name="improvements-in-managing-assessments"></a>管理评估方面的改进

2020年4月的合规性管理器的最新版本包括更新程序简化了如何创建和自定义评估以及如何将其更新。 有关详细信息，请查看[合规性管理器发行说明](compliance-manager-release-notes.md)。

## <a name="language-support"></a>语言支持

合规性分数现在不仅适用于英语：简体中文、中文（繁体）、法语、德语、意大利语、日语、朝鲜语、葡萄牙语（巴西）、俄语和西班牙语，还提供以下语言版本。

## <a name="common-actions-will-synch-status-across-groups"></a>常见操作将同步组之间的状态

如果您的组织具有多个评估组，**技术**操作（即影响整个组织的操作）的行为已发生更改。 跨组的任何重复操作都已合并到一个单一操作中。 该单个操作包含所有已上载的笔记和来自重复版本的证据。 进行此更改后，技术操作现在的行为与它们属于同一组时的行为相同。 现在，在一个组或评估中对操作所做的任何更改都将反映在所有实例中。  **实现状态**、**实现日期**、**测试状态**和**测试日期**   将反映最新的更新。

## <a name="compliance-score-relationship-to-compliance-manager"></a>与合规性管理器的合规性分数关系

现在，在合规性管理器中处理的许多函数都可以在合规性分数中完成。 但是，一些功能仍在合规性管理器中。 在公共预览版过程中使用合规性分数和合规性管理器时，请牢记以下几点：

- **管理评估**：用户可以按合规性分数查看评估及其状态详细信息。 但是，用户只能在合规性管理器中执行评估管理任务（[查看说明](working-with-compliance-manager.md#assessments)）。 这些任务的示例包括：
    - 创建和复制评估
    - 导出评估
    - 存档评估
    - 查看存档的评估
 - **创建用于评估的模板**： 
   - 用户必须转到合规性管理器以创建新模板并修改现有[模板](working-with-compliance-manager.md#templates)。 
   - 创建模板时，您必须包括**产品**和**证书**的维度，以确保您的模板在合规性分数中显示。
 - **设置权限**：合规性分数尚未在合规性管理器中拥有权限的用户需要在 Microsoft 365 合规性中心中设置其权限（[了解详细信息](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。
- **数据传输**：具有合规性管理器中的数据的组织将看到符合性分数中的数据，而与此不同的方法也是如此。
- **根据合规性分数登录合规性管理器**：如果用户已登录合规性分数并选择链接以转到合规性管理器，则用户不必再次登录。 单击该链接后，将在浏览器中打开一个新的选项卡，其中带有一个对话框。 在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？ 登录您的帐户，选择 "**登录**" 按钮以自动登录合规性管理器。

## <a name="known-issues-in-compliance-score-preview"></a>合规性分数中的已知问题（预览）

以下各节介绍了在即将发布的合规性分数中要解决的已知问题。

### <a name="long-load-times-for-non-admin-users"></a>非管理员用户的长时间加载时间
合规性分数在尝试登录时，保留非管理员角色角色的用户可能会遇到较长的加载时间。 刷新浏览器将解决此问题。 （了解有关[合规性分数角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)的详细信息。）

### <a name="supported-browsers"></a>支持的浏览器

- Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。
- 在刷新浏览器之前，有时不会显示更新后的数据。
- 不支持 Internet Explorer。
