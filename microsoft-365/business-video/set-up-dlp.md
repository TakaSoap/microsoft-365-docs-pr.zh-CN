---
title: 防止数据丢失
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何管理设置的数据丢失防护策略。
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701636"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="83008-103">使用 DLP 防止数据丢失</span><span class="sxs-lookup"><span data-stu-id="83008-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="83008-104">数据丢失防护策略可帮助识别和保护企业敏感信息，如社会保险号或医疗记录。</span><span class="sxs-lookup"><span data-stu-id="83008-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="83008-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="83008-105">Try it!</span></span>

1. <span data-ttu-id="83008-106">若要开始，请转到管理 [中心](https://admin.microsoft.com)，然后选择"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="83008-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="83008-107">向下滚动以 **设置数据丢失防护**， **然后选择"查看**"，然后 **管理**。</span><span class="sxs-lookup"><span data-stu-id="83008-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="83008-108">若要编辑策略，请选择它，选择"编辑 **策略**"，然后选择要更改的策略。</span><span class="sxs-lookup"><span data-stu-id="83008-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="83008-109">例如，选择 **"位置** "可更改扫描内容。</span><span class="sxs-lookup"><span data-stu-id="83008-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="83008-110">若要启用 Microsoft Teams 中内容的扫描，将切换开关切换到"打开 **"位置，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="83008-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="83008-111">若要编辑策略设置，请选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="83008-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="83008-112">需要设置适用于检测到的少量和大量敏感内容的单独规则。</span><span class="sxs-lookup"><span data-stu-id="83008-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="83008-113">展开低音量规则。</span><span class="sxs-lookup"><span data-stu-id="83008-113">Expand your low volume rule.</span></span> <span data-ttu-id="83008-114">选择 **"编辑规则"。**</span><span class="sxs-lookup"><span data-stu-id="83008-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="83008-115">查看设置并根据需要调整设置。</span><span class="sxs-lookup"><span data-stu-id="83008-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="83008-116">例如，你可以选择自定义电子邮件 **文本和\*\*\*\*自定义策略提示文本**。</span><span class="sxs-lookup"><span data-stu-id="83008-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="83008-117">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="83008-117">Select **Save**.</span></span>
1. <span data-ttu-id="83008-118">对高音量规则重复执行。</span><span class="sxs-lookup"><span data-stu-id="83008-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="83008-119">选择 **"保存**"，然后 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="83008-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="83008-120">若要创建新策略，请选择"**创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="83008-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="83008-121">你可以创建自定义策略或从模板开始。</span><span class="sxs-lookup"><span data-stu-id="83008-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="83008-122">例如，若要创建 HIPAA 策略，请选择"医疗健康"模板，然后选择 **HIPAA (美国健康保险) 。**</span><span class="sxs-lookup"><span data-stu-id="83008-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="83008-123">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="83008-123">Select **Next**.</span></span>
1. <span data-ttu-id="83008-124">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="83008-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="83008-125">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="83008-125">Select **Next**.</span></span>
1. <span data-ttu-id="83008-126">选择要扫描的位置。</span><span class="sxs-lookup"><span data-stu-id="83008-126">Choose the locations to scan.</span></span> <span data-ttu-id="83008-127">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="83008-127">Select **Next**.</span></span>
1. <span data-ttu-id="83008-128">选择要保护的内容类型。</span><span class="sxs-lookup"><span data-stu-id="83008-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="83008-129">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="83008-129">Select **Next**.</span></span>
1. <span data-ttu-id="83008-130">选择在检测到敏感信息时要发生的情况。</span><span class="sxs-lookup"><span data-stu-id="83008-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="83008-131">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="83008-131">Select **Next**.</span></span>
1. <span data-ttu-id="83008-132">自定义访问和替代权限。</span><span class="sxs-lookup"><span data-stu-id="83008-132">Customize your access and override permissions.</span></span> <span data-ttu-id="83008-133">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="83008-133">Select **Next**.</span></span>
1. <span data-ttu-id="83008-134">选择您希望策略生效时间。</span><span class="sxs-lookup"><span data-stu-id="83008-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="83008-135">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="83008-135">Select **Next**.</span></span>
1. <span data-ttu-id="83008-136">查看你的设置，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="83008-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="83008-137">策略生效后，包含描述的敏感信息的电子邮件将被阻止，并且尝试发送该信息的发件人将看到一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="83008-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>