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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583711"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 安全分数中的情况如何？

为了使[Microsoft 安全得分](microsoft-secure-score.md)更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。 你的分数和可能的最大分数都将发生变化。 但是，这并不意味着您的安全状况发生了变化。

若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>2020年4月21日

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式

为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。

- 将 IRM 保护应用于文档
- 应用数据丢失防护策略

### <a name="adding-azure-ad-improvement-action-to-preview"></a>将 Azure AD 改进操作添加到预览

将以下 Azure Active Directory 改善操作添加到[Microsoft 安全分数的预览版本](microsoft-secure-score-preview.md)：

- 不允许用户向非托管应用程序授予许可（当前在已发布版本中可用）

### <a name="adding-azure-atp-improvement-actions-to-preview"></a>添加 Azure ATP 改进操作以供预览

将以下 Azure 高级威胁防护改进操作添加到[Microsoft 安全分数的预览版本](microsoft-secure-score-preview.md)：

- 在域控制器上禁用打印后台处理程序服务
- 修改不安全的 Kerberos 委派以阻止模拟
- 使用 Microsoft LAPS 保护和管理本地管理员密码
- 降低横向移动路径对敏感实体的风险
- 删除敏感组中的非活动帐户
- 从实体中删除不安全的 SID 历史记录属性
- 解决不安全帐户属性
- 停止明文凭据公开
- 停止旧协议通信
- 停止弱密码使用

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a>在预览中支持 Microsoft Defender ATP 威胁 & 漏洞管理（TVM）安全建议

TVM 提供的所有已发布的安全建议现在也将提供[Microsoft 安全分数的预览版本](microsoft-secure-score-preview.md)。
