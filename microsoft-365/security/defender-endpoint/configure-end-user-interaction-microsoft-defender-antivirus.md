---
title: 配置用户如何与 Microsoft Defender AV 交互
description: 配置最终用户与 Microsoft Defender AV 的交互方式、他们看到的通知，以及他们能否覆盖设置。
keywords: 终结点， 用户， 交互， 通知， ui 锁定模式， 无头模式， 隐藏界面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: df9f87e725575bad2f36cf7b016d257e766e523b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765223"
---
# <a name="configure-end-user-interaction-with-microsoft-defender-antivirus"></a><span data-ttu-id="22297-104">配置最终用户与 Microsoft Defender 防病毒的交互</span><span class="sxs-lookup"><span data-stu-id="22297-104">Configure end-user interaction with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="22297-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="22297-105">**Applies to:**</span></span>

- [<span data-ttu-id="22297-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="22297-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="22297-107">你可以配置网络上终结点的用户如何与 Microsoft Defender 防病毒进行交互。</span><span class="sxs-lookup"><span data-stu-id="22297-107">You can configure how users of the endpoints on your network can interact with Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="22297-108">这包括他们是否看到 Microsoft Defender 防病毒界面、他们看到哪些通知，以及是否可以本地覆盖全局部署的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="22297-108">This includes whether they see the Microsoft Defender Antivirus interface, what notifications they see, and if they can locally override globally-deployed Group Policy settings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="22297-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="22297-109">In this section</span></span>

<span data-ttu-id="22297-110">主题</span><span class="sxs-lookup"><span data-stu-id="22297-110">Topic</span></span> | <span data-ttu-id="22297-111">说明</span><span class="sxs-lookup"><span data-stu-id="22297-111">Description</span></span> 
---|---
[<span data-ttu-id="22297-112">配置终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="22297-112">Configure notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md) | <span data-ttu-id="22297-113">配置和自定义其他通知、通知的自定义文本，以及有关重新启动以修正的通知</span><span class="sxs-lookup"><span data-stu-id="22297-113">Configure and customize additional notifications, customized text for notifications, and notifications about reboots for remediation</span></span>
[<span data-ttu-id="22297-114">阻止用户查看 Microsoft Defender 防病毒用户界面或与之交互</span><span class="sxs-lookup"><span data-stu-id="22297-114">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="22297-115">向用户隐藏用户界面</span><span class="sxs-lookup"><span data-stu-id="22297-115">Hide the user interface from users</span></span>
[<span data-ttu-id="22297-116">阻止用户在本地修改策略设置</span><span class="sxs-lookup"><span data-stu-id="22297-116">Prevent users from locally modifying policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) | <span data-ttu-id="22297-117">阻止 (或) 用户覆盖其各个终结点上的策略设置</span><span class="sxs-lookup"><span data-stu-id="22297-117">Prevent (or allow) users from overriding policy settings on their individual endpoints</span></span>