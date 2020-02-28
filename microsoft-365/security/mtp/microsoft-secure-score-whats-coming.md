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
ms.openlocfilehash: 4d445d4c917a46b12592308f599570725ace8e9d
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322561"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 安全分数中的情况如何？

为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。 你的分数和可能的最大分数都将发生变化。 但是，这并不意味着您的安全状况发生了变化。

若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)

## <a name="march-2nd-2020"></a>第2月2日2020

### <a name="removing-improvement-actions-from-intune"></a>从 Intune 删除改进操作

评估了 Intune 提供的 Microsoft 安全得分改进操作后，它决定了它们不提供组织中设备的安全状态的有用表示形式。 我们正在努力引入可直接评估设备配置状态的安全控制，而不是重点关注策略。

将删除以下 Intune 改进操作：

- 启用 Microsoft Intune 移动设备管理
- 创建适用于 Android 的 Microsoft Intune 合规性策略
- 创建适用于 Android 的 Microsoft Intune 合规性策略
- 创建适用于 Android 的 Microsoft Intune 应用保护策略
- 创建适用于 iOS 的 Microsoft Intune 应用保护策略
- 标记不符合 Microsoft Intune 合规性策略的设备（未分配为不合规）
- 创建适用于 iOS 的 Microsoft Intune 合规性策略
- 为 macOS 创建 Microsoft Intune 合规性策略
- 创建适用于 Windows 的 Microsoft Intune 合规性策略
- 创建适用于 Android 的 Microsoft Intune 配置配置文件
- 为适用于 Android 的工作创建 Microsoft Intune 配置配置文件
- 为 macOS 创建 Microsoft Intune 配置文件
- 为 iOS 创建 Microsoft Intune 配置文件
- 为 Windows 创建 Microsoft Intune 配置文件
- 在 Microsoft Intune 中启用增强型 jailbreak 检测
- 要求对所有设备进行修补，并启用防病毒和防火墙
- 启用 Microsoft Intune 中的 Windows Defender ATP 集成
- 创建 Microsoft Intune Windows 信息保护策略
- 要求所有设备都具有高级安全配置
- 每周查看阻止的设备报告

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>删除不符合可靠测量预期的改进措施 

为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。

- 启用审核数据记录
- 发现有风险和不兼容的卷影 IT 应用程序
- 查看权限 & 阻止连接到您的环境的有风险的 OAuth 应用程序
- 在 SharePoint online 文档库中设置版本控制

### <a name="mfa-improvement-action-updates"></a>MFA 改进操作更新

为了反映企业在应用使用其业务的策略时确保 upmost 安全性的需求，Microsoft 安全记分将删除围绕多重身份验证的三个改进操作，并添加两个。

将删除的三个：

- 为多因素身份验证注册所有用户
- 要求对所有用户进行 MFA
- 需要对 Azure AD 特权角色进行 MFA

添加了新的改进操作：

- 确保所有用户都可以完成多重身份验证以实现安全访问
- 需要对管理角色进行 MFA

 这些新的改进操作需要为你的用户或管理员在你的目录中注册多重身份验证（MFA），并建立符合你的组织需求的一组适当的策略。 主要目标具有灵活性，同时确保所有用户和管理员都可以通过多个因素或基于风险的身份验证提示进行身份验证。 这可以采用具有多个策略的形式，这些策略将应用范围决定，或者设置安全默认值（即将3月16日），让 Microsoft 决定何时对用户进行 MFA 质询。

### <a name="removing-review-improvement-actions"></a>删除 "审阅" 改进操作

安全得分的原则之一是，分数应标准化且易于关联。 具有不可衡量或可操作的改进操作已导致混淆。 仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。 与其他改进操作相比，评审改进操作的计算方式不是相同标准。  

出于这些原因，需要审阅节奏的所有改进操作都将暂时删除。 您的部件不需要执行任何操作。

## <a name="march-16th-2020"></a>3月16日2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式

为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。

- 将用户文档存储在 OneDrive for Business 中
- 设置 Office 365 ATP 安全附件策略
- 设置 Office 365 安全链接以验证 Url
- 不允许邮箱委派
- 允许匿名来宾共享网站和文档的链接
- 启用云应用安全控制台

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>支持 Azure AD 改进操作的安全默认值

Microsoft 安全分数将更新改进操作以支持[AZURE AD 中的安全默认](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)设置，这使组织可以更轻松地使用预配置的常见攻击安全设置来保护组织。

这将影响以下改进操作：

- 确保所有用户都可以完成多重身份验证以实现安全访问
- 需要对管理角色进行 MFA
- 启用策略以阻止旧版身份验证
