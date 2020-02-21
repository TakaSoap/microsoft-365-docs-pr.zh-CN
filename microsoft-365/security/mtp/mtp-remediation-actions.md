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
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175903"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="2897a-104">Microsoft 威胁防护中的自动调查和响应功能中的补救措施</span><span class="sxs-lookup"><span data-stu-id="2897a-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="2897a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2897a-105">**Applies to:**</span></span>
- <span data-ttu-id="2897a-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="2897a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2897a-107">Microsoft 威胁防护中的自动化调查和响应功能包括某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="2897a-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="2897a-108">对设备（也称为终结点）执行某些类型的修正操作。</span><span class="sxs-lookup"><span data-stu-id="2897a-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="2897a-109">对电子邮件内容执行其他补救措施。</span><span class="sxs-lookup"><span data-stu-id="2897a-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="2897a-110">下表汇总了 Microsoft 威胁防护当前支持的补救措施：</span><span class="sxs-lookup"><span data-stu-id="2897a-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="2897a-111">终结点修正操作</span><span class="sxs-lookup"><span data-stu-id="2897a-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="2897a-112">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="2897a-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="2897a-113">隔离</span><span class="sxs-lookup"><span data-stu-id="2897a-113">Quarantine file</span></span><br/><span data-ttu-id="2897a-114">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="2897a-114">Remove registry key</span></span><br/><span data-ttu-id="2897a-115">终止进程</span><span class="sxs-lookup"><span data-stu-id="2897a-115">Kill process</span></span> <br/><span data-ttu-id="2897a-116">停止服务</span><span class="sxs-lookup"><span data-stu-id="2897a-116">Stop service</span></span> <br/><span data-ttu-id="2897a-117">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="2897a-117">Remove registry key</span></span> <br/><span data-ttu-id="2897a-118">禁用驱动程序</span><span class="sxs-lookup"><span data-stu-id="2897a-118">Disable driver</span></span> <br/><span data-ttu-id="2897a-119">删除计划任务</span><span class="sxs-lookup"><span data-stu-id="2897a-119">Remove scheduled task</span></span>      |<span data-ttu-id="2897a-120">软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="2897a-120">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="2897a-121">阻止 URL（单击时）</span><span class="sxs-lookup"><span data-stu-id="2897a-121">Block URL (time-of-click)</span></span><br/><span data-ttu-id="2897a-122">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="2897a-122">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="2897a-123">在[操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是等待审批还是已完成）。</span><span class="sxs-lookup"><span data-stu-id="2897a-123">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2897a-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2897a-124">Next steps</span></span>

- [<span data-ttu-id="2897a-125">批准或拒绝与自动调查和响应相关的操作</span><span class="sxs-lookup"><span data-stu-id="2897a-125">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="2897a-126">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="2897a-126">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
