---
title: 在生产环境中为 Microsoft Defender Office 365评估环境，激活评估、激活
description: 激活 Microsoft Defender for Office365 评估的步骤，包括试用许可证、MX 记录处理、&接受域和入站连接的审核。
keywords: Microsoft 365 Defender试用版， 试用 Microsoft 365 Defender， 评估 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室， Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457696"
---
# <a name="enable-the-evaluation-environment"></a><span data-ttu-id="a4626-104">启用评估环境</span><span class="sxs-lookup"><span data-stu-id="a4626-104">Enable the evaluation environment</span></span>

<span data-ttu-id="a4626-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a4626-105">**Applies to:**</span></span>
- <span data-ttu-id="a4626-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4626-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a4626-107">本文是设置 Microsoft Defender for Office 365 评估环境过程中的第 2 步（第[3](eval-defender-office-365-overview.md) Office 365）。</span><span class="sxs-lookup"><span data-stu-id="a4626-107">This article is [Step 2 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a4626-108">有关此过程详细信息，请参阅 [概述文章](eval-defender-office-365-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a4626-108">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="a4626-109">使用以下步骤启用 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="a4626-109">Use the following steps to enable the evaluation for Microsoft Defender for Office 365.</span></span>


![在 Microsoft Defender 评估Office 365启用 Microsoft Defender for Office 365的步骤](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [<span data-ttu-id="a4626-111">步骤 1：激活试用许可证</span><span class="sxs-lookup"><span data-stu-id="a4626-111">Step 1: Activate trial licenses</span></span>](#step-1-activate-trial-licenses)
- [<span data-ttu-id="a4626-112">步骤 2：审核和验证公共 MX 记录</span><span class="sxs-lookup"><span data-stu-id="a4626-112">Step 2: Audit and verify the public MX record</span></span>](#step-2-audit-and-verify-the-public-mx-record)
- [<span data-ttu-id="a4626-113">步骤 3：审核接受的域</span><span class="sxs-lookup"><span data-stu-id="a4626-113">Step 3: Audit accepted domains</span></span>](#step-3-audit-accepted-domains)
- [<span data-ttu-id="a4626-114">步骤 4：审核入站连接器</span><span class="sxs-lookup"><span data-stu-id="a4626-114">Step 4: Audit inbound connectors</span></span>](#step-4-audit-inbound-connectors)
- [<span data-ttu-id="a4626-115">步骤 5：激活评估</span><span class="sxs-lookup"><span data-stu-id="a4626-115">Step 5: Activate the evaluation</span></span>](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a><span data-ttu-id="a4626-116">步骤 1：激活试用许可证</span><span class="sxs-lookup"><span data-stu-id="a4626-116">Step 1: Activate trial licenses</span></span>

<span data-ttu-id="a4626-117">登录到现有 Microsoft Defender for Office 365或租户管理门户。</span><span class="sxs-lookup"><span data-stu-id="a4626-117">Log on to your existing Microsoft Defender for Office 365 environment or tenant administration portal.</span></span>

1. <span data-ttu-id="a4626-118">导航到管理门户。</span><span class="sxs-lookup"><span data-stu-id="a4626-118">Navigate to the administration portal.</span></span>
2. <span data-ttu-id="a4626-119">从快速启动中选择"购买服务"。</span><span class="sxs-lookup"><span data-stu-id="a4626-119">Select Purchase Services from the quick launch.</span></span>

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="单击导航窗格上的&quot;购买服务&quot;Office 365。":::

3.  <span data-ttu-id="a4626-121">向下滚动到"Add-On"部分 (或搜索"Defender") 找到 Microsoft Defender for Office 365 计划。</span><span class="sxs-lookup"><span data-stu-id="a4626-121">Scroll down to the Add-On section (or search for "Defender") to locate the Microsoft Defender for Office 365 plans.</span></span>
4.  <span data-ttu-id="a4626-122">单击要评估的计划旁边的"详细信息"。</span><span class="sxs-lookup"><span data-stu-id="a4626-122">Click Details next the plan you want to evaluate.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="单击&quot;详细信息&quot;按钮，下一步。":::

5. <span data-ttu-id="a4626-124">单击" *开始免费试用"* 链接。</span><span class="sxs-lookup"><span data-stu-id="a4626-124">Click the *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="单击此面板上的&quot;开始免费试用 *超链接*&quot;。":::

6. <span data-ttu-id="a4626-126">确认请求并单击"立即 *尝试"* 按钮。</span><span class="sxs-lookup"><span data-stu-id="a4626-126">Confirm your request and click the *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="现在，单击&quot;立即尝试 *&quot;按钮*。":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a><span data-ttu-id="a4626-128">步骤 2：审核和验证公共 MX 记录</span><span class="sxs-lookup"><span data-stu-id="a4626-128">Step 2: Audit and verify the public MX record</span></span>

<span data-ttu-id="a4626-129">若要有效评估 Microsoft Defender Office 365，必须经过与租户关联的 Exchange Online Protection (EOP) 中继入站外部电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a4626-129">To effectively evaluate Microsoft Defender for Office 365, it's important that inbound external email be relayed through the Exchange Online Protection (EOP) instance associated with your tenant.</span></span>

1. <span data-ttu-id="a4626-130">登录到 M365 管理门户，展开"设置"，然后选择"域"。</span><span class="sxs-lookup"><span data-stu-id="a4626-130">Log on to the M365 Admin Portal, expand Settings, and select Domains.</span></span>
2. <span data-ttu-id="a4626-131">选择已验证的电子邮件域，然后单击"管理 DNS"。</span><span class="sxs-lookup"><span data-stu-id="a4626-131">Select your verified email domain and click Manage DNS.</span></span>
3. <span data-ttu-id="a4626-132">记下生成并分配给 EOP 租户的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="a4626-132">Make note of the MX record generated and assigned to your EOP tenant.</span></span>
4. <span data-ttu-id="a4626-133">访问外部 (DNS) ，并检查与您的电子邮件域关联的主 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="a4626-133">Access your external (public) DNS zone and check the primary MX record associated with your email domain.</span></span>
    - <span data-ttu-id="a4626-134">*如果公共 MX 记录当前与分配的 EOP* 地址匹配 (例如 tenant-com.mail.protection.outlook.com) ，则不需要进一步路由更改。</span><span class="sxs-lookup"><span data-stu-id="a4626-134">*If your public MX record currently matches the assigned EOP address (e.g. tenant-com.mail.protection.outlook.com) then no further routing changes should be required*.</span></span>
    - <span data-ttu-id="a4626-135">如果公共 MX 记录当前解析为第三方或本地 SMTP 网关，可能需要其他路由配置。</span><span class="sxs-lookup"><span data-stu-id="a4626-135">If your public MX record currently resolves to a third-party or on-premises SMTP gateway then additional routing configurations may be required.</span></span>
    - <span data-ttu-id="a4626-136">如果公共 MX 记录当前解析为本地Exchange则您可能仍在混合模型中，其中某些收件人邮箱尚未迁移到 EXO。</span><span class="sxs-lookup"><span data-stu-id="a4626-136">If your public MX record currently resolves to on-premises Exchange then you may still be in a hybrid model where some recipient mailbox have not yet been migrated to EXO.</span></span>

## <a name="step-3-audit-accepted-domains"></a><span data-ttu-id="a4626-137">步骤 3：审核接受的域</span><span class="sxs-lookup"><span data-stu-id="a4626-137">Step 3: Audit accepted domains</span></span>

1. <span data-ttu-id="a4626-138">登录管理Exchange Online，选择"邮件Flow，然后单击"接受域"。</span><span class="sxs-lookup"><span data-stu-id="a4626-138">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Accepted Domains.</span></span>
2. <span data-ttu-id="a4626-139">在租户中添加并验证的接受域列表中，记下 **主电子邮件域** 的域类型。</span><span class="sxs-lookup"><span data-stu-id="a4626-139">From the list of accepted domains that have been added and verified in your tenant, make note of the **domain type** for your primary email domain.</span></span>
    - <span data-ttu-id="a4626-140">如果域类型设置为 ***"*** 权威"，则假定组织的所有收件人邮箱当前都位于Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a4626-140">If the domain type is set to ***Authoritative*** then it is assumed all recipient mailboxes for your organization currently reside in Exchange Online.</span></span>
    - <span data-ttu-id="a4626-141">如果域类型设置为" ***内部*** 中继"，则您可能仍在混合模型中，其中某些收件人邮箱仍驻留在本地。</span><span class="sxs-lookup"><span data-stu-id="a4626-141">If the domain type is set to ***Internal Relay*** then you may still be in a hybrid model where some recipient mailboxes still reside on-premises.</span></span>

## <a name="step-4-audit-inbound-connectors"></a><span data-ttu-id="a4626-142">步骤 4：审核入站连接器</span><span class="sxs-lookup"><span data-stu-id="a4626-142">Step 4: Audit inbound connectors</span></span>

1. <span data-ttu-id="a4626-143">登录管理Exchange Online，选择"邮件Flow，然后单击"连接器"。</span><span class="sxs-lookup"><span data-stu-id="a4626-143">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Connectors.</span></span>
2. <span data-ttu-id="a4626-144">从配置的连接器列表中，记下来自合作伙伴组织且可能与第三方 SMTP 网关关联的任何条目。</span><span class="sxs-lookup"><span data-stu-id="a4626-144">From the list of configured connectors, make note of any entries which are from **Partner Organization** and may correlate to a third-party SMTP gateway.</span></span>
3. <span data-ttu-id="a4626-145">从已配置的连接器列表中，记下组织的电子邮件服务器中标记的任何条目，这些条目可能指示你仍处于混合方案。</span><span class="sxs-lookup"><span data-stu-id="a4626-145">From the list of configured connectors, make note of any entries labeled **From your organization's email server** which may indicate that you are still in hybrid scenario.</span></span>

## <a name="step-5-activate-the-evaluation"></a><span data-ttu-id="a4626-146">步骤 5：激活评估</span><span class="sxs-lookup"><span data-stu-id="a4626-146">Step 5: Activate the evaluation</span></span>

<span data-ttu-id="a4626-147">按照此处的说明从 microsoft Defender 门户Office 365 Microsoft Defender Microsoft 365 Defender评估。</span><span class="sxs-lookup"><span data-stu-id="a4626-147">Use the instructions here to activate your Microsoft Defender for Office 365 evaluation from the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="a4626-148">使用有权访问租户门户的帐户登录到Microsoft 365 Defender门户。</span><span class="sxs-lookup"><span data-stu-id="a4626-148">Log on to your tenant with an account that has access to the Microsoft 365 Defender portal.</span></span>
2. <span data-ttu-id="a4626-149">选择是否要将 Microsoft 365 Defender 门户作为 Microsoft Defender 管理的默认界面Office 365推荐 (Microsoft Defender) 。</span><span class="sxs-lookup"><span data-stu-id="a4626-149">Choose whether you want to make the **Microsoft 365 Defender portal** your default interface for Microsoft Defender for Office 365 administration (recommended).</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="单击&quot;打开设置&quot;按钮以使用集中式和改进Microsoft 365 Defender门户进行管理。":::

3. <span data-ttu-id="a4626-151">From the navigation menu， select **Policies & Rules** under Email & *Collaboration*.</span><span class="sxs-lookup"><span data-stu-id="a4626-151">From the navigation menu, select **Policies & Rules** under *Email & Collaboration*.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="下面是指向策略&规则的电子邮件协作&图片。单击该按钮！":::

4. <span data-ttu-id="a4626-153">在策略策略 *&仪表板上* ，单击威胁 **策略**。</span><span class="sxs-lookup"><span data-stu-id="a4626-153">On the *Policy & Rules* dashboard, click **Threat Policies**.</span></span>

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="策略策略策略&仪表板的图片和指向威胁策略的箭头。单击下一步！":::

5. <span data-ttu-id="a4626-155">向下滚动到 *"其他策略"，* 然后选择"**评估 Defender Office 365** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="a4626-155">Scroll down to *Additional Policies* and select the **Evaluate Defender for Office 365** tile.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Eval Defender for Office 365磁贴显示它是跨电子邮件和协作矢量进行 30 &试用版。单击浏览。":::

6. <span data-ttu-id="a4626-157">现在，选择是直接将外部电子邮件路由Exchange Online路由到第三方网关还是第三方网关或服务，然后单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a4626-157">Now choose whether external email routes to Exchange Online directly, or to a third-party gateway or service, and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365将评估发送到你的邮箱Exchange Online邮件。提供现在如何路由邮件的详细信息，包括路由邮件的出站连接器的名称。如果您仅Exchange Online Protection (EOP) 您将没有连接器。选择我使用第三方或本地提供商之一，或者我仅使用 EOP。":::

7. <span data-ttu-id="a4626-159">如果使用第三方网关，请从下拉列表中选择供应商名称以及与该解决方案关联的入站连接器。</span><span class="sxs-lookup"><span data-stu-id="a4626-159">If you use a third-party gateway, select the vendor name from the drop-down along with the inbound connector associated with that solution.</span></span> <span data-ttu-id="a4626-160">列出答案后，单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a4626-160">When you've listed your answers, click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="在此对话框中，选择组织使用的第三方供应商服务，或选择&quot;*其他*&quot;。下一个对话框中，选择入站连接器。然后单击&quot;下一步&quot;。":::

8. <span data-ttu-id="a4626-162">查看设置并单击"创建 **评估"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="a4626-162">Review your settings and click the **Create Evaluation** button.</span></span>

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="此窗格有一个下拉列表，用于查看你的设置。如果需要，它还具有&quot;编辑路由类型&quot;的可单击链接。准备好后，单击大蓝色&quot;创建评估&quot;按钮。":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="现在设置已完成。此页面上的蓝色按钮显示&quot;转到评估&quot;。":::      |

## <a name="next-steps"></a><span data-ttu-id="a4626-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a4626-165">Next steps</span></span>

<span data-ttu-id="a4626-166">步骤 3/3：设置 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a4626-166">Step 3 of 3: Set up the pilot for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a4626-167">返回到评估 Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365</span><span class="sxs-lookup"><span data-stu-id="a4626-167">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="a4626-168">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a4626-168">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>