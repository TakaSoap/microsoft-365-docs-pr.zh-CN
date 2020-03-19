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
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836854"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Office 365 中的自动调查遵循的补救措施

## <a name="remediation-actions"></a>修正操作

Office 365 中的[自动化调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)（AIR）[高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)（Office 365 ATP）计划2包括某些修正操作。 当自动调查运行或完成时，您通常会看到一个或多个需要安全操作团队批准才能继续执行的修正操作。 

下表汇总了 Office 365 ATP 中当前提供的补救措施。 

|操作 | 说明 |
|-----|-----|
|阻止 URL（单击时） |针对包含恶意 Url 的电子邮件和文档提供保护。 这样，当用户单击现有 Office 文件或旧电子邮件中的链接时，可以通过[安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)阻止恶意链接和任何相关的网页。 |
|软删除电子邮件  |软删除用户邮箱中的特定电子邮件。 <br/>软删除的邮件将移至用户的 "可恢复的项目" 文件夹中，并将一直保留，直到已删除项目的保留期过期。 |
|软删除电子邮件群集  |软删除与所有用户邮箱中的查询相匹配的恶意电子邮件。 <br/>软删除的邮件将移至用户的 "可恢复的项目" 文件夹，并在已删除项目的保留期过期之前保留。 |
|关闭外部邮件转发 |从特定最终用户的邮箱中删除转发规则。|

> [!NOTE]
> 在 Office 365 ATP 中，不会自动执行任何修正操作。 仅在组织的安全团队进行审批时才采取更正措施。 

## <a name="next-steps"></a>后续步骤

- [查看 Office 365 中的自动调查后的挂起或已完成的修正操作](air-review-approve-pending-completed-actions.md)

- [Office 365 中的自动调查的详细信息和结果](air-view-investigation-results.md)