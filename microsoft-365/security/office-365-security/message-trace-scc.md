---
title: 邮件门户中的Microsoft 365 Defender跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理员可以使用邮件门户中的"邮件Microsoft 365 Defender链接来了解邮件发生了什么。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108111"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="73417-103">邮件门户中的Microsoft 365 Defender跟踪</span><span class="sxs-lookup"><span data-stu-id="73417-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="73417-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="73417-104">**Applies to**</span></span>
- [<span data-ttu-id="73417-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="73417-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="73417-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="73417-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="73417-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73417-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="73417-108">电子邮件门户中的Microsoft 365 Defender跟踪在电子邮件经过你的组织时Exchange Online跟踪。</span><span class="sxs-lookup"><span data-stu-id="73417-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="73417-109">您可以确定服务是否接收、拒绝、延迟或传递了邮件。</span><span class="sxs-lookup"><span data-stu-id="73417-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="73417-110">它还显示在邮件达到最终状态之前对邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="73417-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="73417-111">您可以使用邮件跟踪中的信息有效回答用户有关邮件发生的情况的问题、解决邮件流问题并验证策略更改。</span><span class="sxs-lookup"><span data-stu-id="73417-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="73417-112">邮件门户中Microsoft 365 Defender跟踪只是一个传递到管理中心内Exchange跟踪。</span><span class="sxs-lookup"><span data-stu-id="73417-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="73417-113">有关详细信息，请参阅新式邮件[管理中心Exchange跟踪。](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="73417-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="73417-114">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="73417-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="73417-115">你需要是组织中组织管理、合规性管理或 **技术支持** 角色 **Exchange Online的成员，** 以使用邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="73417-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="73417-116">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="73417-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="73417-117">**备注**：用户具有Azure Active Directory角色的成员身份Microsoft 365 管理中心为用户提供了对 Microsoft 365 中其他功能所需的权限。 </span><span class="sxs-lookup"><span data-stu-id="73417-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="73417-118">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="73417-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="73417-119">邮件跟踪结果中显示的邮件的最大数量取决于您选择的报告类型 (请参阅"选择报告类型"部分，了解) 。 [](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type)</span><span class="sxs-lookup"><span data-stu-id="73417-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="73417-120">PowerShell 或独立 EOP PowerShell 中的[Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet Exchange Online返回结果中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="73417-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="73417-121">打开邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="73417-121">Open message trace</span></span>

<span data-ttu-id="73417-122">在Microsoft 365 Defender门户 <https://security.microsoft.com> () ，转到"电子邮件&**协作** Exchange \> **跟踪"。**</span><span class="sxs-lookup"><span data-stu-id="73417-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="73417-123">或者，若要直接转到邮件跟踪页面，请使用 <https://admin.exchange.microsoft.com/#/messagetrace> 。</span><span class="sxs-lookup"><span data-stu-id="73417-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="73417-124">此时，EAC 中的邮件跟踪将打开。</span><span class="sxs-lookup"><span data-stu-id="73417-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="73417-125">有关详细信息，请参阅新式邮件[管理中心Exchange跟踪。](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="73417-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
