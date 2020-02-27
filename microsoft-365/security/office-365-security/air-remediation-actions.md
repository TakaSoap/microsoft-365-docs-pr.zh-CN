---
title: Office 365 中的补救措施自动化调查和响应
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 高级威胁防护计划2中的自动调查和响应功能中的补救措施。
ms.openlocfilehash: 0db49a28fb90bcddcdd874ac54216957e4be5fa1
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288510"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365 中的自动调查遵循的补救措施

## <a name="remediation-actions"></a>修正操作

Office 365 中的[自动化调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)高级威胁防护包括某些修正操作。 当自动调查运行或完成时，您通常会看到一个或多个需要安全操作团队批准才能继续执行的修正操作。 

下表汇总了[Office 365 高级威胁防护](office-365-atp.md)中当前可用的补救措施。 

|操作 | 说明 |
|-----|-----|
|阻止 URL（单击时） |针对包含恶意 Url 的电子邮件和文档进行防护。 这样，当用户单击现有 Office 文件或旧电子邮件中的链接时，可以通过[安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)阻止恶意链接和任何相关的网页。 |
|软删除电子邮件  |软删除用户邮箱中的特定电子邮件|
|软删除电子邮件群集  |软删除与所有用户邮箱中的查询相匹配的恶意电子邮件|
|关闭外部邮件转发 |从特定最终用户的邮箱中删除转发规则|

## <a name="approve-or-reject-pending-actions"></a>批准（或拒绝）挂起的操作

![航空调查操作页](../../media/air-investigationactionspage.png)

在查看[调查的详细信息](air-view-investigation-results.md)时，您可以批准或拒绝任何待定的修正操作。 我们建议您尽快执行此操作，以便您的自动调查能够完成。

> [!IMPORTANT]
> 批准或拒绝修正操作需要适当的权限。 查看[使用空中功能所需的权限](office-365-air.md#required-permissions-to-use-air-capabilities)。

1. 选择 "**操作**" 选项卡。

2. 选择列表项。 （这将激活 "批准" 和 "拒绝" 按钮。）

3. 查看您选择的项目的可用信息，然后批准或拒绝该操作。 
 - **批准**可开始进行修正。
 - **拒绝**无需进一步操作

## <a name="next-steps"></a>后续步骤

- [了解已损坏的用户安全行动手册](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [查看你的 ATP 报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)