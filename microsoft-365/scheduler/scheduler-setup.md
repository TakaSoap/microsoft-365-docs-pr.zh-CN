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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362542"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="46bf5-103">设置 Microsoft 365 专属计划员</span><span class="sxs-lookup"><span data-stu-id="46bf5-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="46bf5-104">若要为计划程序设置Microsoft 365，先决条件如下：</span><span class="sxs-lookup"><span data-stu-id="46bf5-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="46bf5-105">我需要什么？</span><span class="sxs-lookup"><span data-stu-id="46bf5-105">What do I need?</span></span> | <span data-ttu-id="46bf5-106">说明</span><span class="sxs-lookup"><span data-stu-id="46bf5-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="46bf5-107">Cortana邮箱</span><span class="sxs-lookup"><span data-stu-id="46bf5-107">Cortana mailbox</span></span> |<span data-ttu-id="46bf5-108">租户管理员需要将邮箱设置为"Cortana"邮箱 (，即 cortana@yourdomain.com) 。</span><span class="sxs-lookup"><span data-stu-id="46bf5-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="46bf5-109">Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="46bf5-109">Exchange Online mailbox</span></span> |<span data-ttu-id="46bf5-110">用户必须拥有Exchange Online日历</span><span class="sxs-lookup"><span data-stu-id="46bf5-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="46bf5-111">计划程序许可证</span><span class="sxs-lookup"><span data-stu-id="46bf5-111">Scheduler license</span></span> |<span data-ttu-id="46bf5-112">有关许可和定价信息，请参阅[Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="46bf5-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="46bf5-113">为邮箱创建Cortana</span><span class="sxs-lookup"><span data-stu-id="46bf5-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="46bf5-114">租户Exchange邮箱充当租户发送和接收Cortana发送和接收电子邮件的邮箱Cortana。</span><span class="sxs-lookup"><span data-stu-id="46bf5-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="46bf5-115">根据保留策略Cortana发送到租户的所有电子邮件Cortana租户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="46bf5-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="46bf5-116">使用 Microsoft 365 管理中心创建用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="46bf5-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="46bf5-117">建议使用 30 天的保留策略。</span><span class="sxs-lookup"><span data-stu-id="46bf5-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="46bf5-118">使用邮箱Cortana SMTP 地址中的名称。</span><span class="sxs-lookup"><span data-stu-id="46bf5-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="46bf5-119">"Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"或"Cortana"等名称。Scheduler@yourdomain.com"。</span><span class="sxs-lookup"><span data-stu-id="46bf5-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="46bf5-120">将邮箱指定为计划程序助理</span><span class="sxs-lookup"><span data-stu-id="46bf5-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="46bf5-121">创建计划程序Cortana邮箱后，必须将该邮箱指定为Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="46bf5-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="46bf5-122">指定计划Cortana邮箱后，可以代表用户安排会议。</span><span class="sxs-lookup"><span data-stu-id="46bf5-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="46bf5-123">若要指定Cortana计划程序邮箱，授权管理员必须运行一行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="46bf5-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="46bf5-124">连接组织Microsoft 365远程 PowerShell 运行空间。</span><span class="sxs-lookup"><span data-stu-id="46bf5-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="46bf5-125">运行以下 PowerShell 脚本为计划程序指定邮箱：</span><span class="sxs-lookup"><span data-stu-id="46bf5-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="46bf5-126">在计划程序邮箱上运行此Cortana"命令后，将在邮箱上设置一个新的"PersistedCapability"，以表明此邮箱是"SchedulerAssistant"。</span><span class="sxs-lookup"><span data-stu-id="46bf5-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="46bf5-127">如果之前未执行这些步骤，请按照以下步骤将组织连接到[PowerShell：连接 PowerShell Microsoft 365进行连接](../enterprise/connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="46bf5-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="46bf5-128">若要发现组织中当前将哪个邮箱设置为 Cortana计划程序助理，请运行 get 函数：</span><span class="sxs-lookup"><span data-stu-id="46bf5-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="46bf5-129">计划程序邮箱可能需要最多两个小时才能完成完全设置，才能设置 SchedulerAssistant 功能。</span><span class="sxs-lookup"><span data-stu-id="46bf5-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="46bf5-130">Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="46bf5-130">Exchange Online mailbox</span></span>
<span data-ttu-id="46bf5-131">计划程序许可证是会议Microsoft 365的加载项，它使会议组织者能够将其会议计划任务委派给计划程序助理。</span><span class="sxs-lookup"><span data-stu-id="46bf5-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="46bf5-132">若要使计划程序正常工作，通常Microsoft 365许可证，会议组织者需要以下组件：</span><span class="sxs-lookup"><span data-stu-id="46bf5-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="46bf5-133">指定为计划程序助理邮箱的邮箱</span><span class="sxs-lookup"><span data-stu-id="46bf5-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="46bf5-134">计划程序许可证</span><span class="sxs-lookup"><span data-stu-id="46bf5-134">Scheduler license</span></span>
- <span data-ttu-id="46bf5-135">Exchange Online邮箱和日历</span><span class="sxs-lookup"><span data-stu-id="46bf5-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="46bf5-136">与会者不需要计划程序或Microsoft 365许可证。</span><span class="sxs-lookup"><span data-stu-id="46bf5-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="46bf5-137">计划程序最终用户许可证要求</span><span class="sxs-lookup"><span data-stu-id="46bf5-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="46bf5-138">计划程序许可证需要以下许可证之一：</span><span class="sxs-lookup"><span data-stu-id="46bf5-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="46bf5-139">Microsoft 365 E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="46bf5-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="46bf5-140">Business Basic、Business、Business Standard、Business 高级版</span><span class="sxs-lookup"><span data-stu-id="46bf5-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="46bf5-141">Office 365 E1、A1、E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="46bf5-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="46bf5-142">商业基本信息、商业高级版</span><span class="sxs-lookup"><span data-stu-id="46bf5-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="46bf5-143">Exchange Online计划 1 或计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="46bf5-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="46bf5-144">Microsoft 365计划程序仅适用于英语的全球多租户环境。</span><span class="sxs-lookup"><span data-stu-id="46bf5-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="46bf5-145">**用户Microsoft 365** 计划程序：</span><span class="sxs-lookup"><span data-stu-id="46bf5-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="46bf5-146">Microsoft 365由世纪银行在中国运营</span><span class="sxs-lookup"><span data-stu-id="46bf5-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="46bf5-147">Microsoft 365使用数据被信任方德国电信的德国云</span><span class="sxs-lookup"><span data-stu-id="46bf5-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="46bf5-148">政府云，GCC、消费者、GCC高或 DoD</span><span class="sxs-lookup"><span data-stu-id="46bf5-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="46bf5-149">计划程序支持其数据位置不在德国数据中心的德国用户。</span><span class="sxs-lookup"><span data-stu-id="46bf5-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
