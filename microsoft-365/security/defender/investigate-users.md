---
title: 调查 Microsoft 365 安全中心中的用户
description: 调查 Microsoft 365 安全中心中的用户
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 标识， 数据， 设备， 应用， 事件， 分析， 响应
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: c03e4d5bd94eb6105ffab91c6dad2b74d7159dde
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300057"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="e1620-104">调查 Microsoft 365 安全中心中的用户</span><span class="sxs-lookup"><span data-stu-id="e1620-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e1620-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e1620-105">**Applies to:**</span></span>

- <span data-ttu-id="e1620-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1620-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e1620-107">事件调查的一部分可能包括用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e1620-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="e1620-108">从"事件 **"** 和"用户"中事件 **&">">\*\*\*\*开始**。</span><span class="sxs-lookup"><span data-stu-id="e1620-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的用户页面示例":::

<span data-ttu-id="e1620-110">若要获取事件的用户帐户的快速摘要，请选择用户帐户名称旁边的选中标记。</span><span class="sxs-lookup"><span data-stu-id="e1620-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="e1620-111">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="e1620-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 安全中心内事件的用户帐户摘要窗格示例":::

> [!NOTE]
> <span data-ttu-id="e1620-113">用户页面显示 Azure Active Directory (AD) 组织以及组，帮助你了解与用户关联的组和权限。</span><span class="sxs-lookup"><span data-stu-id="e1620-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="e1620-114">在此飞出页面中，你可以查看用户威胁信息，包括任何当前事件、活动警报和风险级别以及用户曝光、帐户、设备等。</span><span class="sxs-lookup"><span data-stu-id="e1620-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="e1620-115">此外，你可以直接在 Microsoft 365 安全中心采取措施来解决受损用户的问题，确认用户受到威胁或要求他们重新登录。</span><span class="sxs-lookup"><span data-stu-id="e1620-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="e1620-116">从此处，可以选择" **转到用户页面** "以查看用户帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1620-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="e1620-117">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="e1620-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 安全中心内事件的用户帐户页面示例":::

<span data-ttu-id="e1620-119">您还可以通过从"用户"页上的列表中选择用户帐户的名称来 **查看此页面。**</span><span class="sxs-lookup"><span data-stu-id="e1620-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="e1620-120">Microsoft 365 安全中心用户页面将来自 Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Cloud App Security (的信息合并在一起，具体取决于你拥有哪些) 。</span><span class="sxs-lookup"><span data-stu-id="e1620-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="e1620-121">此页面显示特定于用户帐户安全风险的信息。</span><span class="sxs-lookup"><span data-stu-id="e1620-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="e1620-122">这包括一个分数，可帮助评估风险以及导致用户的整体风险的最新事件和警报。</span><span class="sxs-lookup"><span data-stu-id="e1620-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="e1620-123">在此页中，你可以执行以下附加操作：</span><span class="sxs-lookup"><span data-stu-id="e1620-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="e1620-124">将用户帐户标记为已泄露</span><span class="sxs-lookup"><span data-stu-id="e1620-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="e1620-125">要求用户重新登录</span><span class="sxs-lookup"><span data-stu-id="e1620-125">Require the user to sign in again</span></span>
- <span data-ttu-id="e1620-126">暂停用户帐户</span><span class="sxs-lookup"><span data-stu-id="e1620-126">Suspend the user account</span></span>
- <span data-ttu-id="e1620-127">请参阅 Azure Active Directory (Azure AD) 用户帐户设置</span><span class="sxs-lookup"><span data-stu-id="e1620-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="e1620-128">查看用户帐户拥有的文件</span><span class="sxs-lookup"><span data-stu-id="e1620-128">View the files owned by the user account</span></span>
- <span data-ttu-id="e1620-129">查看与该用户共享的文件。</span><span class="sxs-lookup"><span data-stu-id="e1620-129">View files shared with this user.</span></span> 

<span data-ttu-id="e1620-130">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="e1620-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 安全中心内针对事件的用户帐户的操作示例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="e1620-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e1620-132">Next steps</span></span>

<span data-ttu-id="e1620-133">如果需要处理内事件，请继续执行 [调查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="e1620-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1620-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1620-134">See also</span></span>

- [<span data-ttu-id="e1620-135">事件概述</span><span class="sxs-lookup"><span data-stu-id="e1620-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e1620-136">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="e1620-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e1620-137">管理事件</span><span class="sxs-lookup"><span data-stu-id="e1620-137">Manage incidents</span></span>](manage-incidents.md)