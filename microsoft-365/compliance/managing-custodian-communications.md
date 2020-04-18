---
title: 在高级电子数据展示中使用通信
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 利用高级电子数据展示，可以轻松管理法律封存通知工作流，避免在法律调查中通知保管人。
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551234"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="3a766-103">在高级电子数据展示中使用通信</span><span class="sxs-lookup"><span data-stu-id="3a766-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="3a766-104">高级电子数据展示允许法律部门简化跟踪和分发合法保留通知的过程。</span><span class="sxs-lookup"><span data-stu-id="3a766-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="3a766-105">通过保管人通信工具，法律部门可以管理和自动化整个合法保留过程，从初始通知、提醒和升级到一个位置。</span><span class="sxs-lookup"><span data-stu-id="3a766-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="3a766-106">什么是合法保留通知？</span><span class="sxs-lookup"><span data-stu-id="3a766-106">What is a legal hold notification?</span></span>

<span data-ttu-id="3a766-107">法定保留（也称为 "*诉讼保留*"）通知是从组织的法律部门向员工、临时员工或可与法律调查相关的数据的保管人发送的通知。</span><span class="sxs-lookup"><span data-stu-id="3a766-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="3a766-108">这些通知指示保管人保留以电子方式存储的信息，以及可能与活跃或即将发生的法律事务相关的任何内容。</span><span class="sxs-lookup"><span data-stu-id="3a766-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="3a766-109">法律团队必须知道每位管理员已收到、阅读、理解并同意符合给定的说明。</span><span class="sxs-lookup"><span data-stu-id="3a766-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="3a766-110">合法保留通知过程</span><span class="sxs-lookup"><span data-stu-id="3a766-110">The legal hold notification process</span></span>

<span data-ttu-id="3a766-111">组织有责任在了解即将进行的诉讼或法规调查时保留相关信息。</span><span class="sxs-lookup"><span data-stu-id="3a766-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="3a766-112">为了符合调查的保留要求，组织应立即通知潜在保管人的责任，以保留相关信息。</span><span class="sxs-lookup"><span data-stu-id="3a766-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="3a766-113">使用高级电子数据展示，法律团队可以创建和自定义其法律保留通知工作流。</span><span class="sxs-lookup"><span data-stu-id="3a766-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="3a766-114">保管人通信工具允许法律团队配置以下通知和工作流：</span><span class="sxs-lookup"><span data-stu-id="3a766-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="3a766-115">**颁发通知：** 从法律部门向保管人发出通知（或发起）的合法保留通知，其中可能包含有关案例的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3a766-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="3a766-116">此通知指示保管人保留发现可能需要的任何信息。</span><span class="sxs-lookup"><span data-stu-id="3a766-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="3a766-117">**重新发布通知：** 在一种情况下，可能需要保管人来保留比之前请求更多的内容（或较少的内容）。</span><span class="sxs-lookup"><span data-stu-id="3a766-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="3a766-118">在这种情况下，您可以更新现有保留通知，并将其重新颁发给保管人。</span><span class="sxs-lookup"><span data-stu-id="3a766-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="3a766-119">**发布通知：** 一旦问题得到解决且保管人不再受保留要求的制约，就可以从该案例发布保管人。</span><span class="sxs-lookup"><span data-stu-id="3a766-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="3a766-120">此外，还可以通知管理员他们不再需要保留内容，并提供有关如何恢复其数据相关的正常工作活动的说明。</span><span class="sxs-lookup"><span data-stu-id="3a766-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="3a766-121">**提醒和升级：** 在某些情况下，仅发出通知足以满足法律查询要求。</span><span class="sxs-lookup"><span data-stu-id="3a766-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="3a766-122">对于每个通知，法律团队可以安排一组提醒和升级工作流，以自动跟踪不响应的保管人。</span><span class="sxs-lookup"><span data-stu-id="3a766-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="3a766-123">**提醒：** 在向一组保管人颁发或重新颁发法律保留通知后，组织可以设置提醒，以通知保管人的响应者。</span><span class="sxs-lookup"><span data-stu-id="3a766-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="3a766-124">**升级：** 在某些情况下，即使在一段时间后，保管人仍无响应，但法律团队可以设置升级工作流，以通知不响应保管人及其经理。</span><span class="sxs-lookup"><span data-stu-id="3a766-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="3a766-125">有关管理保管人通信进程的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="3a766-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="3a766-126">创建合法保留通知</span><span class="sxs-lookup"><span data-stu-id="3a766-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="3a766-127">使用通信编辑器</span><span class="sxs-lookup"><span data-stu-id="3a766-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="3a766-128">管理保留通知</span><span class="sxs-lookup"><span data-stu-id="3a766-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="3a766-129">确认保留通知</span><span class="sxs-lookup"><span data-stu-id="3a766-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)