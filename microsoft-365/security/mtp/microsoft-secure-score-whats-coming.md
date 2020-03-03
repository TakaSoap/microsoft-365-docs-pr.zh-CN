---
title: Microsoft 安全分数中的情况如何？
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372000"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 安全分数中的情况如何？

为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。 你的分数和可能的最大分数都将发生变化。 但是，这并不意味着您的安全状况发生了变化。

若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>3月16日2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式

为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。

- 将用户文档存储在 OneDrive for Business 中
- 设置 Office 365 ATP 安全附件策略
- 设置 Office 365 安全链接以验证 Url
- 不允许邮箱委派
- 允许匿名来宾共享网站和文档的链接
- 启用云应用安全控制台
- 为外部共享链接配置过期时间

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>支持 Azure AD 改进操作的安全默认值

Microsoft 安全分数将更新改进操作以支持[AZURE AD 中的安全默认](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)设置，这使组织可以更轻松地使用预配置的常见攻击安全设置来保护组织。

这将影响以下改进操作：

- 确保所有用户都可以完成多重身份验证以实现安全访问
- 需要对管理角色进行 MFA
- 启用策略以阻止旧版身份验证
