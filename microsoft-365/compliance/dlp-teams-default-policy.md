---
title: '了解 Microsoft Teams (预览版中的默认数据丢失) '
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 了解 Microsoft Teams 中的默认数据丢失防护策略
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826223"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="fa2f4-103">了解 Microsoft Teams (预览版中的默认数据丢失) </span><span class="sxs-lookup"><span data-stu-id="fa2f4-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="fa2f4-104">[数据丢失防护](data-loss-prevention-policies.md) (DLP) 功能已扩展为包括 Microsoft Teams 聊天和频道消息，包括私人频道消息。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-104">[Data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="fa2f4-105">作为此版本的一部分，我们为首次使用合规性中心的客户创建了默认 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="fa2f4-106">适用于</span><span class="sxs-lookup"><span data-stu-id="fa2f4-106">Applies to</span></span>

<span data-ttu-id="fa2f4-107">通过以下一个或多个许可证获得许可并拥有活动 Teams 用户的任何租户</span><span class="sxs-lookup"><span data-stu-id="fa2f4-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="fa2f4-108">ME5、</span><span class="sxs-lookup"><span data-stu-id="fa2f4-108">ME5,</span></span> 
- <span data-ttu-id="fa2f4-109">MA5、</span><span class="sxs-lookup"><span data-stu-id="fa2f4-109">MA5,</span></span> 
- <span data-ttu-id="fa2f4-110">E5/A5 合规性、</span><span class="sxs-lookup"><span data-stu-id="fa2f4-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="fa2f4-111">IP+G、</span><span class="sxs-lookup"><span data-stu-id="fa2f4-111">IP+G,</span></span> 
- <span data-ttu-id="fa2f4-112">OE5、</span><span class="sxs-lookup"><span data-stu-id="fa2f4-112">OE5,</span></span> 
- <span data-ttu-id="fa2f4-113">O365 高级合规性</span><span class="sxs-lookup"><span data-stu-id="fa2f4-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="fa2f4-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="fa2f4-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="fa2f4-115">默认策略有什么功能？</span><span class="sxs-lookup"><span data-stu-id="fa2f4-115">What does the default policy do?</span></span>

<span data-ttu-id="fa2f4-116">默认 DLP 策略跟踪在组织内部和外部共享的所有信用卡号。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="fa2f4-117">默认情况下，租户的所有用户都启用此策略。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="fa2f4-118">它不会为最终用户生成任何策略提示，但会生成警报事件，还会触发低严重性电子邮件给管理员 (添加到策略策略) 。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="fa2f4-119">管理员可以通过登录到合规中心查看活动并编辑策略详细信息。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="fa2f4-120">管理员可以在合规中心查看此策略>[](https://compliance.microsoft.com/compliancesettings)数据丢失防护策略"页面。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="fa2f4-121">![默认 Teams DLP 策略](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="fa2f4-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="fa2f4-122">编辑或删除默认策略</span><span class="sxs-lookup"><span data-stu-id="fa2f4-122">Edit or delete the default policy</span></span>

<span data-ttu-id="fa2f4-123">若要 [编辑默认策略以提高性能或将其删除](create-test-tune-dlp-policy.md#tune-a-dlp-policy)，只需使用具有 **DLP 合规性管理权限** 的帐户。</span><span class="sxs-lookup"><span data-stu-id="fa2f4-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="fa2f4-124">有关详细信息，请参阅权限[。](create-test-tune-dlp-policy.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="fa2f4-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

