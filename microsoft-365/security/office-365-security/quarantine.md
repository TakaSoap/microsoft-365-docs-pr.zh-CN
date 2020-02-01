---
title: 隔离
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: 了解 Exchange Online 和 Exchange Online Protection 的托管隔离。
ms.openlocfilehash: bcbd0db1c05834882c464fa28012b82a13929d7f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598649"
---
# <a name="quarantine"></a><span data-ttu-id="9b21a-103">Quarantine</span><span class="sxs-lookup"><span data-stu-id="9b21a-103">Quarantine</span></span>

<span data-ttu-id="9b21a-104">以下主题提供有关 Exchange Online 和 Exchange Online Protection (EOP) 管理员和最终用户的托管隔离邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="9b21a-104">The following topics provide information about the hosted quarantine for both Exchange Online and Exchange Online Protection (EOP) admins and end users:</span></span>

- <span data-ttu-id="9b21a-105">[隔离常见问题解答](quarantine-faq.md) - 提供有关管理员和最终用户的隔离邮箱的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="9b21a-105">[Quarantine FAQ](quarantine-faq.md) - Provides general questions and answers about the quarantine for both admins and end users</span></span>

- <span data-ttu-id="9b21a-106">[以管理员身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-an-administrator.md)：介绍了管理员如何在 Exchange 管理中心（EAC）中查找和释放驻留在隔离区中的任何邮件，并可选择将其报告为误报（非垃圾邮件）到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9b21a-106">[Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md): Describes how admins can find and release any message that resides in the quarantine in the Exchange admin center (EAC), and optionally report it as a false positive (not junk) message to Microsoft.</span></span>

- <span data-ttu-id="9b21a-107">[以 Office 365 中的用户的形式查找和释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)：介绍最终用户如何在垃圾邮件隔离用户界面中查找和释放自己的垃圾邮件隔离邮件，并将其报告为非垃圾邮件到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9b21a-107">[Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md): Describes how end users can find and release their own spam-quarantined messages in the spam quarantine user interface, and report them as not junk to Microsoft.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="9b21a-108">若要访问最终用户垃圾邮件隔离邮箱，最终用户必须具有有效 Office 365 用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="9b21a-108">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="9b21a-109">保护本地邮箱的 EOP 客户必须是通过目录同步或 EAC 创建的有效电子邮件用户。</span><span class="sxs-lookup"><span data-stu-id="9b21a-109">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="9b21a-110">有关管理用户的详细信息，EOP 管理员可以参阅[Manage mail users IN EOP](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="9b21a-110">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="9b21a-111">对于 EOP 独立客户，建议使用目录同步并启用基于目录的边缘阻止，有关详细信息，请参阅[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="9b21a-111">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>
