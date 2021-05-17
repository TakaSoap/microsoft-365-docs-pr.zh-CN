---
title: 使用 Advanced eDiscovery
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
description: Advanced eDiscovery轻松管理法律调查中通知保管人的法律保留通知工作流。
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551234"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="1715d-103">使用 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1715d-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="1715d-104">Advanced eDiscovery允许法律部门简化其跟踪和分发合法保留通知的流程。</span><span class="sxs-lookup"><span data-stu-id="1715d-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="1715d-105">保管人通信工具使法律部门可以在一个位置管理和自动执行整个法定保留过程，包括初始通知、提醒和上报。</span><span class="sxs-lookup"><span data-stu-id="1715d-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="1715d-106">什么是法定保留通知？</span><span class="sxs-lookup"><span data-stu-id="1715d-106">What is a legal hold notification?</span></span>

<span data-ttu-id="1715d-107">合法 (也称为诉讼保留 *)* 通知是组织的法律部门发送给员工、临时员工或与法律调查相关的数据的保管人的通知。</span><span class="sxs-lookup"><span data-stu-id="1715d-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="1715d-108">这些通知指示保管人保留电子存储的信息，以及可能与活动或即将发生的法律事务相关的任何内容。</span><span class="sxs-lookup"><span data-stu-id="1715d-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="1715d-109">法律团队必须知道每个保管人已收到、阅读、理解并同意遵守给定的说明。</span><span class="sxs-lookup"><span data-stu-id="1715d-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="1715d-110">法定保留通知流程</span><span class="sxs-lookup"><span data-stu-id="1715d-110">The legal hold notification process</span></span>

<span data-ttu-id="1715d-111">组织在了解即将发生的诉讼或监管调查时，有责任保留相关信息。</span><span class="sxs-lookup"><span data-stu-id="1715d-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="1715d-112">为了符合调查的保留要求，组织应立即通知潜在的保管人其保留相关信息的责任。</span><span class="sxs-lookup"><span data-stu-id="1715d-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="1715d-113">借助Advanced eDiscovery，法律团队可以创建和自定义合法保留通知工作流。</span><span class="sxs-lookup"><span data-stu-id="1715d-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="1715d-114">保管人通信工具使法律团队可以配置以下通知和工作流：</span><span class="sxs-lookup"><span data-stu-id="1715d-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="1715d-115">**发布通知：** 法律部门通知 (法律部门) 保管人发送或启动法定保留通知，这些保管人可能拥有与案例相关的信息。</span><span class="sxs-lookup"><span data-stu-id="1715d-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="1715d-116">此通知指示保管人保留发现可能需要的任何信息。</span><span class="sxs-lookup"><span data-stu-id="1715d-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="1715d-117">**重新发布通知：** 在一种情况下，可能需要保管人保留其他内容 (或保存) 请求的内容。</span><span class="sxs-lookup"><span data-stu-id="1715d-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="1715d-118">对于此方案，可以更新现有保留通知，然后重新向保管人发出保留通知。</span><span class="sxs-lookup"><span data-stu-id="1715d-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="1715d-119">**发布通知：** 一旦解决了问题，并且保管人不再受保留要求所规定，就可以从案例释放保管人。</span><span class="sxs-lookup"><span data-stu-id="1715d-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="1715d-120">此外，你可以通知保管人他们不再需要保留内容，并提供有关如何恢复其数据正常工作活动的说明。</span><span class="sxs-lookup"><span data-stu-id="1715d-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="1715d-121">**提醒和上报：** 在某些情况下，仅发出通知不足以满足法律发现要求。</span><span class="sxs-lookup"><span data-stu-id="1715d-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="1715d-122">法律团队通过每个通知安排一组提醒和升级工作流，以自动跟进无响应保管人。</span><span class="sxs-lookup"><span data-stu-id="1715d-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="1715d-123">**提醒：** 在向一组保管人颁发或重新颁发法定保留通知后，组织可以设置提醒以提醒无响应保管人。</span><span class="sxs-lookup"><span data-stu-id="1715d-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="1715d-124">**升级：** 在某些情况下，如果保管人即使在一组提醒一段时间之后仍保持无响应，法律团队可以设置呈报工作流，以通知无响应保管人及其经理。</span><span class="sxs-lookup"><span data-stu-id="1715d-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="1715d-125">有关管理保管人通信过程的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="1715d-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="1715d-126">创建法定保留通知</span><span class="sxs-lookup"><span data-stu-id="1715d-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="1715d-127">使用通信编辑器</span><span class="sxs-lookup"><span data-stu-id="1715d-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="1715d-128">管理保留通知</span><span class="sxs-lookup"><span data-stu-id="1715d-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="1715d-129">确认保留通知</span><span class="sxs-lookup"><span data-stu-id="1715d-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)