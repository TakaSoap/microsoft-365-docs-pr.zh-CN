---
title: 确认保留通知
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
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用 Advanced eDiscovery通过电子邮件发送和跟踪合法保留通知，以及监视义务状态。
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034882"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="a83f6-103">确认保留通知</span><span class="sxs-lookup"><span data-stu-id="a83f6-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="a83f6-104">在响应法规请求或调查时，您可能需要通知保管人他们保留电子存储的信息 (ESI) 以及可能与活动或即将发生的法律事务相关的任何材料。</span><span class="sxs-lookup"><span data-stu-id="a83f6-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="a83f6-105">发送后，法律团队必须知道每个保管人已收到、阅读、理解并同意遵循给定的说明。</span><span class="sxs-lookup"><span data-stu-id="a83f6-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="a83f6-106">为了帮助减少跟进保管人的时间、成本和工作量，Advanced eDiscovery通过电子邮件发送和跟踪合法保留通知。</span><span class="sxs-lookup"><span data-stu-id="a83f6-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="a83f6-107">除了电子邮件通知之外，每个保管人将有权访问个性化合规性门户，从而让保管人随时了解其义务状态的变化。</span><span class="sxs-lookup"><span data-stu-id="a83f6-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="a83f6-108">电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="a83f6-108">Email notifications</span></span>

<span data-ttu-id="a83f6-109">在颁发法定保留通知后，每个保管人将收到一封唯一的个性化电子邮件，其中包含定义的法定保留通知并添加了说明。</span><span class="sxs-lookup"><span data-stu-id="a83f6-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="a83f6-110">了解如何使用内置通信编辑器，以允许保管[](using-communications-editor.md)人确认通知或直接从电子邮件访问其合规性门户。</span><span class="sxs-lookup"><span data-stu-id="a83f6-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="a83f6-111">根据法定保留通知的配置，保管人可能会收到以下通知：</span><span class="sxs-lookup"><span data-stu-id="a83f6-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="a83f6-112">**发布通知：** 发送给保管人的第一个通知。</span><span class="sxs-lookup"><span data-stu-id="a83f6-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="a83f6-113">此通知将包含你的发布说明以及附加到邮件末尾的保留通知。</span><span class="sxs-lookup"><span data-stu-id="a83f6-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="a83f6-114">**提醒通知：** 如果启用，将基于指定的频率和间隔向保管人发送提醒通知。</span><span class="sxs-lookup"><span data-stu-id="a83f6-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="a83f6-115">提醒将继续发送，直到保管人确认其通知或提醒次数用完为止。</span><span class="sxs-lookup"><span data-stu-id="a83f6-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="a83f6-116">**升级通知：** 如果启用，提醒通知用尽后，会向保管人及其经理发送上报通知。</span><span class="sxs-lookup"><span data-stu-id="a83f6-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="a83f6-117">系统将自动发送升级通知，直到完成指定的升级次数或直到保管人确认其保留通知为止。</span><span class="sxs-lookup"><span data-stu-id="a83f6-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="a83f6-118">**Reissue 通知：** 在调查过程中，如果更新了保留通知的内容，则更新的通知将自动发送给保管人。</span><span class="sxs-lookup"><span data-stu-id="a83f6-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="a83f6-119">**发布通知：** 当保管人从案件释放时，他们将被发送释放通知。</span><span class="sxs-lookup"><span data-stu-id="a83f6-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="a83f6-120">合规性门户</span><span class="sxs-lookup"><span data-stu-id="a83f6-120">Compliance Portal</span></span>

<span data-ttu-id="a83f6-121">除了电子邮件通知之外，每个保管人将有权访问唯一的合规性门户。</span><span class="sxs-lookup"><span data-stu-id="a83f6-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="a83f6-122">通过门户，每个保管人可以查看、访问并确认其主动保留通知。</span><span class="sxs-lookup"><span data-stu-id="a83f6-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![保管人合规性门户](../media/CustodianPortal.jpg)
