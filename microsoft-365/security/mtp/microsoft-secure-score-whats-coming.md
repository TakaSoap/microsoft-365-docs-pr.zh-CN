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
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895437"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 安全分数中的情况如何？

为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。 你的分数和可能的最大分数都将发生变化。 但是，这并不意味着您的安全状况发生了变化。

若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>2020年4月21日

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式

为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。

- 删除/阻止在过去30天内未使用的帐户
- 指定少于5个全局管理员
- 将 IRM 保护应用于文档
- 应用数据丢失防护策略

### <a name="adding-additional-control-support-in-the-preview-version"></a>在预览版本中添加其他控件支持
- 不允许用户向非托管应用程序授予许可（当前在已发布版本中可用）

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a>支持其他 Microsoft 云应用安全改进操作
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

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>对 Microsoft Defender ATP 威胁的支持 & 漏洞管理（TVM）安全建议
- TVM 提供的所有已发布的安全建议现在也将在 Microsoft 安全分数中提供。
