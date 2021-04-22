---
title: 在 Microsoft 365 安全中心分析用户
description: 在 Microsoft 365 安全中心分析用户
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
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939726"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="28f9a-104">在 Microsoft 365 安全中心分析用户</span><span class="sxs-lookup"><span data-stu-id="28f9a-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="28f9a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="28f9a-105">**Applies to:**</span></span>

- <span data-ttu-id="28f9a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28f9a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="28f9a-107">事件分析的一部分可能包括用户帐户。</span><span class="sxs-lookup"><span data-stu-id="28f9a-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="28f9a-108">从"事件 **"** 和"用户"中事件 **&">">\*\*\*\*开始**。</span><span class="sxs-lookup"><span data-stu-id="28f9a-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的用户页面示例":::

<span data-ttu-id="28f9a-110">若要获取事件的用户帐户的快速摘要，请选择用户帐户名称旁边的选中标记。</span><span class="sxs-lookup"><span data-stu-id="28f9a-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="28f9a-111">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="28f9a-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 安全中心内事件的用户帐户摘要窗格示例":::

<span data-ttu-id="28f9a-113">从此处，可以选择" **转到用户页面** "以查看用户帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="28f9a-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="28f9a-114">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="28f9a-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 安全中心内事件的用户帐户页面示例":::

<span data-ttu-id="28f9a-116">您还可以通过从"用户"页上的列表中选择用户帐户的名称来 **查看此页面。**</span><span class="sxs-lookup"><span data-stu-id="28f9a-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="28f9a-117">Microsoft 365 安全中心用户页面将来自 Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Cloud App Security (的信息合并在一起，具体取决于你拥有哪些) 。</span><span class="sxs-lookup"><span data-stu-id="28f9a-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="28f9a-118">此页面显示特定于用户帐户安全风险的信息。</span><span class="sxs-lookup"><span data-stu-id="28f9a-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="28f9a-119">这包括一个分数，可帮助评估风险以及导致用户的整体风险的最新事件和警报。</span><span class="sxs-lookup"><span data-stu-id="28f9a-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="28f9a-120">在此页中，你可以执行以下附加操作：</span><span class="sxs-lookup"><span data-stu-id="28f9a-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="28f9a-121">将用户帐户标记为已泄露</span><span class="sxs-lookup"><span data-stu-id="28f9a-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="28f9a-122">要求用户重新登录</span><span class="sxs-lookup"><span data-stu-id="28f9a-122">Require the user to sign in again</span></span>
- <span data-ttu-id="28f9a-123">暂停用户帐户</span><span class="sxs-lookup"><span data-stu-id="28f9a-123">Suspend the user account</span></span>
- <span data-ttu-id="28f9a-124">请参阅 Azure Active Directory (Azure AD) 用户帐户设置</span><span class="sxs-lookup"><span data-stu-id="28f9a-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="28f9a-125">查看用户帐户拥有的文件</span><span class="sxs-lookup"><span data-stu-id="28f9a-125">View the files owned by the user account</span></span>
- <span data-ttu-id="28f9a-126">查看与该用户共享的文件。</span><span class="sxs-lookup"><span data-stu-id="28f9a-126">View files shared with this user.</span></span> 

<span data-ttu-id="28f9a-127">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="28f9a-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 安全中心内针对事件的用户帐户的操作示例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="28f9a-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="28f9a-129">Related topics</span></span>

- [<span data-ttu-id="28f9a-130">事件概述</span><span class="sxs-lookup"><span data-stu-id="28f9a-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="28f9a-131">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="28f9a-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="28f9a-132">管理事件</span><span class="sxs-lookup"><span data-stu-id="28f9a-132">Manage incidents</span></span>](manage-incidents.md)