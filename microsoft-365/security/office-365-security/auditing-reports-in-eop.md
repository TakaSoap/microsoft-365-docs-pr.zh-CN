---
title: 独立 EOP 中的审核报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: '管理员可以了解 Exchange Online Protection (EOP) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08432f97d196df8b661d63a5d4cdf3680b78e070
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921284"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="22ab4-103">独立 EOP 中的审核报告</span><span class="sxs-lookup"><span data-stu-id="22ab4-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="22ab4-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="22ab4-104">**Applies to**</span></span>
-  [<span data-ttu-id="22ab4-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="22ab4-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="22ab4-106">在独立 Exchange Online Protection (EOP) 组织中，审核报告可以帮助您满足组织的法规、合规性和诉讼要求。</span><span class="sxs-lookup"><span data-stu-id="22ab4-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="22ab4-107">您可以随时获取审核报告以确定已对 EOP 配置所做的更改。</span><span class="sxs-lookup"><span data-stu-id="22ab4-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="22ab4-108">这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。</span><span class="sxs-lookup"><span data-stu-id="22ab4-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="22ab4-109">独立 EOP 中提供两个审核报告：</span><span class="sxs-lookup"><span data-stu-id="22ab4-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="22ab4-110">**管理员角色组报告**：管理员角色组报告允许您查看何时向管理员角色组的成员身份添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="22ab4-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="22ab4-111">您可以使用此报告监视对分配给组织用户的管理员权限的更改。</span><span class="sxs-lookup"><span data-stu-id="22ab4-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="22ab4-112">有关详细信息，请参阅在独立 EOP 中运行管理员 [角色组报告](run-an-administrator-role-group-report-in-eop-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="22ab4-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="22ab4-113">**管理员审核日志：** 管理员审核日志记录 (管理员或具有管理权限的用户基于) EOP PowerShell cmdlet 执行的任何操作。</span><span class="sxs-lookup"><span data-stu-id="22ab4-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="22ab4-114">有关详细信息，请参阅在 Exchange Online 中查看 [管理员审核日志](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)。</span><span class="sxs-lookup"><span data-stu-id="22ab4-114">For more information, see [View the Administrator Audit Log in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>