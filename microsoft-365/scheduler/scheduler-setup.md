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
ms.openlocfilehash: ba1e178545001473bf73eea3eb02b5ab1c7bf084
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861475"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="8dacd-103">为计划程序设置Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8dacd-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="8dacd-104">若要为计划程序设置Microsoft 365，先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="8dacd-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="8dacd-105">**我需要什么？**</span><span class="sxs-lookup"><span data-stu-id="8dacd-105">**What do I need?**</span></span> |<span data-ttu-id="8dacd-106">**描述**</span><span class="sxs-lookup"><span data-stu-id="8dacd-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="8dacd-107">Cortana 邮箱</span><span class="sxs-lookup"><span data-stu-id="8dacd-107">Cortana mailbox</span></span> |<span data-ttu-id="8dacd-108">租户管理员需要将邮箱设置为充当"Cortana"邮箱 (即 cortana@yourdomain.com) 。</span><span class="sxs-lookup"><span data-stu-id="8dacd-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="8dacd-109">Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="8dacd-109">Exchange Online mailbox</span></span> |<span data-ttu-id="8dacd-110">用户必须拥有Exchange Online日历</span><span class="sxs-lookup"><span data-stu-id="8dacd-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="8dacd-111">计划程序许可证</span><span class="sxs-lookup"><span data-stu-id="8dacd-111">Scheduler license</span></span> |<span data-ttu-id="8dacd-112">有关许可和定价信息，请参阅[Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="8dacd-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="8dacd-113">为 Cortana 创建邮箱</span><span class="sxs-lookup"><span data-stu-id="8dacd-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="8dacd-114">租户Exchange邮箱充当 Cortana 邮箱，供租户在 Cortana 之间发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8dacd-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="8dacd-115">发送到 Cortana 的所有电子邮件将基于保留策略保留在租户的 Cortana 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="8dacd-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="8dacd-116">使用Microsoft 365管理中心创建用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="8dacd-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="8dacd-117">建议使用 30 天的保留策略。</span><span class="sxs-lookup"><span data-stu-id="8dacd-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="8dacd-118">在邮箱的主 SMTP 地址中，使用名称 Cortana。</span><span class="sxs-lookup"><span data-stu-id="8dacd-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="8dacd-119">建议使用"Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"或"Cortana.Scheduler@yourdomain.com"等名称。</span><span class="sxs-lookup"><span data-stu-id="8dacd-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="8dacd-120">将邮箱指定为计划程序助理</span><span class="sxs-lookup"><span data-stu-id="8dacd-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="8dacd-121">创建 Cortana 计划程序的唯一邮箱后，必须将邮箱指定为Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="8dacd-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="8dacd-122">指定 Cortana 计划程序邮箱后，它将可以代表用户安排会议。</span><span class="sxs-lookup"><span data-stu-id="8dacd-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="8dacd-123">若要指定 Cortana 计划程序邮箱，授权管理员必须运行一行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="8dacd-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="8dacd-124">连接组织Microsoft 365远程 PowerShell 运行空间。</span><span class="sxs-lookup"><span data-stu-id="8dacd-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="8dacd-125">运行以下 PowerShell 脚本为计划程序指定邮箱：</span><span class="sxs-lookup"><span data-stu-id="8dacd-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="8dacd-126">在 Cortana 计划程序邮箱上运行此"set"命令后，将在邮箱上设置新的"PersistedCapability"，以表明此邮箱为"SchedulerAssistant"。</span><span class="sxs-lookup"><span data-stu-id="8dacd-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="8dacd-127">如果之前未执行这些步骤，请按照以下步骤将组织连接到 PowerShell：连接 powerShell Microsoft 365 [- Microsoft 365 企业版 |Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="8dacd-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="8dacd-128">若要发现组织中当前将哪个邮箱设置为 Cortana 计划程序助理，请运行 get 函数：</span><span class="sxs-lookup"><span data-stu-id="8dacd-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> <span data-ttu-id="8dacd-129">计划程序邮箱可能需要最多两个小时才能完成完全设置，才能设置 SchedulerAssistant 功能。</span><span class="sxs-lookup"><span data-stu-id="8dacd-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="8dacd-130">Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="8dacd-130">Exchange Online mailbox</span></span>
<span data-ttu-id="8dacd-131">计划程序是加载项Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8dacd-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="8dacd-132">会议组织者必须拥有Exchange Online邮箱和日历，计划程序正常工作。</span><span class="sxs-lookup"><span data-stu-id="8dacd-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="8dacd-133">Exchange 要求</span><span class="sxs-lookup"><span data-stu-id="8dacd-133">Exchange requirements</span></span>

<span data-ttu-id="8dacd-134">除了许可计划程序之外，还必须具有以下许可证之一：</span><span class="sxs-lookup"><span data-stu-id="8dacd-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="8dacd-135">Microsoft 365 E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="8dacd-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="8dacd-136">Business Basic、Business、Business Standard、Business 高级版</span><span class="sxs-lookup"><span data-stu-id="8dacd-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="8dacd-137">Office 365E1、A1、E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="8dacd-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="8dacd-138">商业基本信息、商业高级版</span><span class="sxs-lookup"><span data-stu-id="8dacd-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="8dacd-139">Exchange Online计划 1 或计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="8dacd-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="8dacd-140">**Microsoft 365** 计划程序不适用于由世纪Office 365运营的 Office 365 的用户。</span><span class="sxs-lookup"><span data-stu-id="8dacd-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="8dacd-141">使用数据被信任方德国电信Microsoft 365德国云的用户也不可用。</span><span class="sxs-lookup"><span data-stu-id="8dacd-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="8dacd-142">身处德国但其数据位置不在德国数据中心的用户仍然可以使用。</span><span class="sxs-lookup"><span data-stu-id="8dacd-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="8dacd-143">政府云（包括 GCC、消费者、GCC 高或 DoD）的用户也不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="8dacd-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
