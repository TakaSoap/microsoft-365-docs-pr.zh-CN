---
title: 为计划程序设置Microsoft 365。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 为计划程序设置Microsoft 365。
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286137"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="01a50-103">为计划程序设置Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01a50-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="01a50-104">若要为计划程序设置Microsoft 365，先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="01a50-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="01a50-105">**我需要什么？**</span><span class="sxs-lookup"><span data-stu-id="01a50-105">**What do I need?**</span></span> |<span data-ttu-id="01a50-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="01a50-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="01a50-107">Cortana 邮箱</span><span class="sxs-lookup"><span data-stu-id="01a50-107">Cortana mailbox</span></span> |<span data-ttu-id="01a50-108">租户管理员需要将邮箱设置为充当"Cortana"邮箱 (即 cortana@yourdomain.com) 。</span><span class="sxs-lookup"><span data-stu-id="01a50-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="01a50-109">Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="01a50-109">Exchange Online mailbox</span></span> |<span data-ttu-id="01a50-110">用户必须拥有Exchange Online日历</span><span class="sxs-lookup"><span data-stu-id="01a50-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="01a50-111">计划程序许可证</span><span class="sxs-lookup"><span data-stu-id="01a50-111">Scheduler license</span></span> |<span data-ttu-id="01a50-112">有关许可和定价信息，请参阅[Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="01a50-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="01a50-113">为 Cortana 创建邮箱</span><span class="sxs-lookup"><span data-stu-id="01a50-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="01a50-114">租户Exchange邮箱充当 Cortana 邮箱，供租户在 Cortana 之间发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="01a50-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="01a50-115">发送到 Cortana 的所有电子邮件将基于保留策略保留在租户的 Cortana 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="01a50-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="01a50-116">使用 Microsoft 365管理中心创建新邮箱。</span><span class="sxs-lookup"><span data-stu-id="01a50-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="01a50-117">建议使用 30 天的保留策略。</span><span class="sxs-lookup"><span data-stu-id="01a50-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="01a50-118">在邮箱的主 SMTP 地址中，使用名称 Cortana。</span><span class="sxs-lookup"><span data-stu-id="01a50-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="01a50-119">建议使用"Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"或"Cortana.Scheduler@yourdomain.com"等名称。</span><span class="sxs-lookup"><span data-stu-id="01a50-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="01a50-120">请联系 Microsoft (scheduler_m365@microsoft.com) 启用 Cortana 邮箱。</span><span class="sxs-lookup"><span data-stu-id="01a50-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="01a50-121">必须联系 Microsoft 以通过电子邮件将 Cortana 邮箱配置为使用计划程序 scheduler_m365@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="01a50-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="01a50-122">启用 Cortana 邮箱可能需要最多两周的时间。</span><span class="sxs-lookup"><span data-stu-id="01a50-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="01a50-123">Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="01a50-123">Exchange Online mailbox</span></span>
<span data-ttu-id="01a50-124">计划程序是加载项Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="01a50-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="01a50-125">会议组织者必须拥有Exchange Online邮箱和日历，计划程序正常工作。</span><span class="sxs-lookup"><span data-stu-id="01a50-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="01a50-126">Exchange 要求</span><span class="sxs-lookup"><span data-stu-id="01a50-126">Exchange requirements</span></span>

<span data-ttu-id="01a50-127">除了许可计划程序之外，还必须具有以下许可证之一：</span><span class="sxs-lookup"><span data-stu-id="01a50-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="01a50-128">Microsoft 365 E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="01a50-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="01a50-129">Business Basic、Business、Business Standard、Business 高级版</span><span class="sxs-lookup"><span data-stu-id="01a50-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="01a50-130">Office 365E1、A1、E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="01a50-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="01a50-131">商业基本信息、商业高级版</span><span class="sxs-lookup"><span data-stu-id="01a50-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="01a50-132">Exchange Online计划 1 或计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="01a50-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="01a50-133">**Microsoft 365** 计划程序不适用于由世纪Office 365运营的 Office 365 的用户。</span><span class="sxs-lookup"><span data-stu-id="01a50-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="01a50-134">使用数据被信任方德国电信Microsoft 365德国云的用户也不可用。</span><span class="sxs-lookup"><span data-stu-id="01a50-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="01a50-135">身处德国但其数据位置不在德国数据中心的用户仍然可以使用。</span><span class="sxs-lookup"><span data-stu-id="01a50-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="01a50-136">政府云（包括 GCC、消费者、GCC 高或 DoD）的用户也不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="01a50-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
