---
title: Microsoft 合规性管理器和 GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规合规性活动。
ms.openlocfilehash: b4a648c43fb20f557b85e24e9e67de036cc4f2e0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168658"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft 合规性管理器和 GDPR

根据欧盟 (GDPR) 一般数据保护条例可能会影响合规性策略，并强制采取特定操作来管理合规性管理器中使用的用户和客户信息。

## <a name="user-privacy-settings"></a>用户隐私设置

某些法规要求组织必须能够删除用户历史记录数据。 合规性管理器 **提供用户隐私设置** 功能，使管理员能够：
  
- [搜索用户](#search-for-a-user)
- [导出帐户数据历史记录报告](#export-a-report-of-account-data-history)
- [删除用户数据历史记录](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>搜索用户

若要搜索用户帐户，请执行以下操作：
  
1. Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the domain suffix list on the right. 对于具有多个注册域的组织，请仔细检查域名后缀以确保其正确无误。

2. 正确输入用户名后，请选择"搜索 **"。**

3. 对于未返回的用户帐户，页面将显示未找到 **用户**。 检查用户的电子邮件地址信息并在必要时进行更正。 若要重试，请选择"搜索 **"。**

4. 对于返回的用户帐户，按钮文本从 **"搜索"** 更改为 **"清除"。** 这表示返回的用户帐户是其他函数的操作上下文，并且这些函数适用于此用户帐户。

5. 若要清除搜索结果并搜索其他用户，请选择"清除 **"。**

## <a name="export-a-report-of-account-data-history"></a>导出帐户数据历史记录报告

对于标识的每个用户帐户，可以生成链接到该帐户的依赖关系报告。 此信息允许你重新分配打开的操作项或确保访问以前上载的证据。
  
 若要生成并导出报告，请执行以下操作：
  
1. 选择 **"** 导出"，生成并下载当前分配给返回用户帐户的合规性管理器控制行动项的报告，以及该用户上载的文档列表。 如果没有分配的操作或上载的文档，则会显示一条错误消息，指出"此用户没有数据"。

2. 如果看不到要检查浏览器下载历史记录的下载弹出窗口，报告将下载到活动浏览器窗口的后台。

3. 打开文档即可查看报告数据。

> [!IMPORTANT]
> 报表数据不是保留并显示对操作项分配历史记录的状态更改的历史列表。 生成的报告是运行报告时分配的控件行动项的快照， (日期和时间戳写入报告) 。 例如，如果为同一用户再次生成报告，则任何后续行动项重新分配都会导致不同的快照报告数据。
  
## <a name="delete-user-data-history"></a>删除用户数据历史记录

将分配给返回用户的所有控件操作项都设置为"未分配"。 将 **返回用户上载** 的任何文档的上传值设置为"已删除用户"。
  
若要删除用户帐户操作项和文档上载历史记录，请执行以下操作：
  
1. 选择“**删除**”。

    此时将显示确认对话框："*这将删除所选用户的所有控件行动项分配和文档上载历史记录。此操作是永久性的。确定要继续吗？*"

2. 若要继续，请选择 **"确定"，** 否则选择"**取消"。**
