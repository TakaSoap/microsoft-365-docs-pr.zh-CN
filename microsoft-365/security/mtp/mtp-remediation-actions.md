---
title: Microsoft 威胁防护中的自动调查和响应功能中的补救措施
description: 简要了解 Microsoft 威胁防护中的自动调查和响应功能
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225480"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="0cd46-104">Microsoft 威胁防护中的自动调查和响应功能中的补救措施</span><span class="sxs-lookup"><span data-stu-id="0cd46-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="0cd46-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0cd46-105">**Applies to:**</span></span>
- <span data-ttu-id="0cd46-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="0cd46-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0cd46-107">Microsoft 威胁防护中的自动化调查和响应功能包括某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="0cd46-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="0cd46-108">对设备（也称为终结点）执行某些类型的修正操作。</span><span class="sxs-lookup"><span data-stu-id="0cd46-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="0cd46-109">对电子邮件内容执行其他补救措施。</span><span class="sxs-lookup"><span data-stu-id="0cd46-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="0cd46-110">下表汇总了 Microsoft 威胁防护当前支持的补救措施：</span><span class="sxs-lookup"><span data-stu-id="0cd46-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="0cd46-111">终结点修正操作</span><span class="sxs-lookup"><span data-stu-id="0cd46-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="0cd46-112">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="0cd46-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="0cd46-113">隔离</span><span class="sxs-lookup"><span data-stu-id="0cd46-113">Quarantine file</span></span><br/><span data-ttu-id="0cd46-114">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="0cd46-114">Remove registry key</span></span><br/><span data-ttu-id="0cd46-115">终止进程</span><span class="sxs-lookup"><span data-stu-id="0cd46-115">Kill process</span></span> <br/><span data-ttu-id="0cd46-116">停止服务</span><span class="sxs-lookup"><span data-stu-id="0cd46-116">Stop service</span></span> <br/><span data-ttu-id="0cd46-117">禁用驱动程序</span><span class="sxs-lookup"><span data-stu-id="0cd46-117">Disable driver</span></span> <br/><span data-ttu-id="0cd46-118">删除计划任务</span><span class="sxs-lookup"><span data-stu-id="0cd46-118">Remove scheduled task</span></span>      |<span data-ttu-id="0cd46-119">软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="0cd46-119">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="0cd46-120">阻止 URL（单击时）</span><span class="sxs-lookup"><span data-stu-id="0cd46-120">Block URL (time-of-click)</span></span><br/><span data-ttu-id="0cd46-121">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="0cd46-121">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="0cd46-122">在[操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是等待审批还是已完成）。</span><span class="sxs-lookup"><span data-stu-id="0cd46-122">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0cd46-123">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0cd46-123">Next steps</span></span>

- [<span data-ttu-id="0cd46-124">批准或拒绝与自动调查和响应相关的操作</span><span class="sxs-lookup"><span data-stu-id="0cd46-124">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="0cd46-125">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="0cd46-125">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
