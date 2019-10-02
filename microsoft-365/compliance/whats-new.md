---
title: Microsoft 365 合规性中心的新增功能
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 我们不断将新功能添加到 Microsoft 365 合规性中心，修复我们了解的问题，并根据你的反馈进行更改。 了解我们在本月所做的操作。
ms.openlocfilehash: b80edfb0425904b03426ef0ff3cdd1d251e638ea
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369633"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Microsoft 365 合规性中心的新增功能

我们不断将新功能添加到[Microsoft 365 合规性中心](microsoft-365-compliance-center.md)，修复我们了解的问题，并根据你的反馈进行更改。 请查看下面的内容，查看今天可为你提供的内容。 有些功能以不同的速度向客户推出。 如果尚未看到功能，请尝试将自己添加到[目标版本](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 对其他管理中心中的内容有兴趣？ 查看以下文章：<br>[Microsoft 365 管理中心的新增功能](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 管理中心的新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="september-2019"></a>2019 年 9 月

不知为什么在本月的版本中静音？ 我们正在开发的新的创新合规性解决方案将在11月的[Microsoft Ignite](https://www.microsoft.com/ignite)中 unveiled。 请随时关注！

### <a name="new-encryption-options-for-sensitivity-labels"></a>用于敏感度标签的新加密选项 

为敏感度标签配置加密时，您现在有两个选项，可让用户在手动将标签应用于电子邮件和文档时分配权限：<br>
- 将标签应用于**Outlook 电子邮件**时，用户可以强制实施与 "不转发" 选项等效的限制。 收件人将能够读取邮件，但不能转发、打印或复制内容。
- 将标签应用于**Word、PowerPoint 和 Excel 文件**时，系统将提示用户为特定用户和组分配访问权限。

[了解更多](encryption-sensitivity-labels.md#let-users-assign-permissions)

## <a name="august-2019"></a>2019 年 8 月

### <a name="update-to-data-investigations"></a>对数据调查的更新

在执行数据调查时，您现在可以从其原始位置删除项目。 这意味着您可以在组织中删除 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户中的项目。 由于已将项目作为证据收集，因此您可以将这些项目的副本保留在证据集中，以便您可以进一步调查或仅保留为参考。 [了解更多](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) 

## <a name="july-2019"></a>2019 年 7 月

### <a name="new-admin-roles"></a>新管理员角色

我们发布了两个新的管理员角色，以帮助管理您的组织中的安全性和合规性。请告诉你的所有朋友。

- **合规性数据管理员**。具有此角色的用户具有在 Microsoft 365 合规性中心、Microsoft 365 管理中心和 Azure 中保护和跟踪数据的权限。 它们还可以管理 Exchange 管理中心、合规性管理器、团队 & Skype for Business 管理中心并为 Azure 和 Microsoft 365 创建支持票证。
- **Security 运算符**。 具有此角色的用户可以管理警报并具有对安全相关功能的全局只读访问权限，其中包括 Microsoft 365 安全中心、Azure Active Directory、Identity Protection、特权身份管理和 Office 365 中的所有内容安全性 & 合规性中心。

[了解有关这些角色的详细信息](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>搜索和筛选报告

不会再滚动浏览报告的海洋，以查找您需要的报告。 您现在可以搜索报告（基于其标题），并筛选类别（如 "标签" 和 "合规性"）以及 "Office 365" 和 "Microsoft 云应用安全" 等源。

![包含已应用筛选器的报表的搜索和筛选按钮的屏幕捕获](media/mcc_report_filtering.png)
