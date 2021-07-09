---
title: 在 Microsoft Defender for Endpoint 中配置警报通知
description: 可以使用 Microsoft Defender for Endpoint 根据严重性和其他条件配置安全警报的电子邮件通知设置。
keywords: 电子邮件通知， 配置警报通知， 适用于终结点的 Microsoft Defender， 适用于终结点的 Microsoft Defender 通知， 适用于终结点的 Microsoft Defender 警报， windows 10 企业版， windows 10 教育版
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2b638742e29d5ca0a8b74adfa6796380114d24a3
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339498"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a07c7-104">在 Microsoft Defender for Endpoint 中配置警报通知</span><span class="sxs-lookup"><span data-stu-id="a07c7-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a07c7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a07c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="a07c7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a07c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a07c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a07c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a07c7-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a07c7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a07c7-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a07c7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="a07c7-110">你可以将 Defender for Endpoint 配置为向指定收件人发送电子邮件通知，以接收新警报。</span><span class="sxs-lookup"><span data-stu-id="a07c7-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="a07c7-111">此功能使你能够识别将立即获得通知的一组个人，并可以基于其严重性对警报采取行动。</span><span class="sxs-lookup"><span data-stu-id="a07c7-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="a07c7-112">只有具有"管理安全设置"权限的用户才能配置电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a07c7-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="a07c7-113">如果选择使用基本权限管理，则具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a07c7-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="a07c7-114">你可以设置触发通知的警报严重性级别。</span><span class="sxs-lookup"><span data-stu-id="a07c7-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="a07c7-115">您还可以添加或删除电子邮件通知的收件人。</span><span class="sxs-lookup"><span data-stu-id="a07c7-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="a07c7-116">新收件人将收到有关在添加后触发的警报的通知。</span><span class="sxs-lookup"><span data-stu-id="a07c7-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="a07c7-117">有关警报详细信息，请参阅 [查看和组织警报队列](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="a07c7-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="a07c7-118">如果使用基于角色的访问控制 (RBAC) ，则收件人将仅根据通知规则中配置的设备组接收通知。</span><span class="sxs-lookup"><span data-stu-id="a07c7-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="a07c7-119">具有适当权限的用户只能创建、编辑或删除仅限于其设备组管理作用域的通知。</span><span class="sxs-lookup"><span data-stu-id="a07c7-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="a07c7-120">只有分配到全局管理员角色的用户才能管理所有设备组配置的通知规则。</span><span class="sxs-lookup"><span data-stu-id="a07c7-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="a07c7-121">电子邮件通知包括有关警报的基本信息和指向门户的链接，可在其中执行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="a07c7-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>

## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="a07c7-122">创建警报通知规则</span><span class="sxs-lookup"><span data-stu-id="a07c7-122">Create rules for alert notifications</span></span>
<span data-ttu-id="a07c7-123">可以创建规则，以确定要发送电子邮件通知的设备以及通知收件人的警报严重性。</span><span class="sxs-lookup"><span data-stu-id="a07c7-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="a07c7-124">在导航窗格中，**选择"设置**  >    >  **终结点""**  >  **常规电子邮件通知"。**</span><span class="sxs-lookup"><span data-stu-id="a07c7-124">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Email notifications**.</span></span>

2. <span data-ttu-id="a07c7-125">单击 **"添加项目"。**</span><span class="sxs-lookup"><span data-stu-id="a07c7-125">Click **Add item**.</span></span>

3. <span data-ttu-id="a07c7-126">指定常规信息：</span><span class="sxs-lookup"><span data-stu-id="a07c7-126">Specify the General information:</span></span>
    - <span data-ttu-id="a07c7-127">**规则名称** - 指定通知规则的名称。</span><span class="sxs-lookup"><span data-stu-id="a07c7-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="a07c7-128">**包含组织** 名称 - 指定电子邮件通知上显示的客户名称。</span><span class="sxs-lookup"><span data-stu-id="a07c7-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="a07c7-129">**包含特定于租户的门户链接** - 添加包含租户 ID 的链接，以允许访问特定租户。</span><span class="sxs-lookup"><span data-stu-id="a07c7-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="a07c7-130">**包括设备信息** - 在电子邮件警报正文中包含设备名称。</span><span class="sxs-lookup"><span data-stu-id="a07c7-130">**Include device information** - Includes the device name in the email alert body.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a07c7-131">此信息可能由不在你为 Defender for Endpoint 数据选择的地理位置中的收件人邮件服务器进行处理。</span><span class="sxs-lookup"><span data-stu-id="a07c7-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="a07c7-132">**设备** - 选择是通知收件人有关所有设备上警报 (全局管理员角色) 或所选设备组。</span><span class="sxs-lookup"><span data-stu-id="a07c7-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="a07c7-133">有关详细信息，请参阅创建 [和管理设备组](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="a07c7-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="a07c7-134">**警报严重性** - 选择警报严重性级别。</span><span class="sxs-lookup"><span data-stu-id="a07c7-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="a07c7-135">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a07c7-135">Click **Next**.</span></span>

5. <span data-ttu-id="a07c7-136">输入收件人的电子邮件地址，然后单击"**添加收件人"。**</span><span class="sxs-lookup"><span data-stu-id="a07c7-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="a07c7-137">可添加多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a07c7-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="a07c7-138">选中"发送测试电子邮件"，检查电子邮件收件人是否 **可接收电子邮件通知**。</span><span class="sxs-lookup"><span data-stu-id="a07c7-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="a07c7-139">单击 **"保存通知规则"。**</span><span class="sxs-lookup"><span data-stu-id="a07c7-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="a07c7-140">编辑通知规则</span><span class="sxs-lookup"><span data-stu-id="a07c7-140">Edit a notification rule</span></span>

1. <span data-ttu-id="a07c7-141">选择要编辑的通知规则。</span><span class="sxs-lookup"><span data-stu-id="a07c7-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="a07c7-142">更新"常规"和"收件人"选项卡信息。</span><span class="sxs-lookup"><span data-stu-id="a07c7-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="a07c7-143">单击 **"保存通知规则"。**</span><span class="sxs-lookup"><span data-stu-id="a07c7-143">Click **Save notification rule**.</span></span>

## <a name="delete-notification-rule"></a><span data-ttu-id="a07c7-144">删除通知规则</span><span class="sxs-lookup"><span data-stu-id="a07c7-144">Delete notification rule</span></span>

1. <span data-ttu-id="a07c7-145">选择要删除的通知规则。</span><span class="sxs-lookup"><span data-stu-id="a07c7-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="a07c7-146">单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="a07c7-146">Click **Delete**.</span></span>

## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="a07c7-147">警报电子邮件通知疑难解答</span><span class="sxs-lookup"><span data-stu-id="a07c7-147">Troubleshoot email notifications for alerts</span></span>

<span data-ttu-id="a07c7-148">本节列出了在使用电子邮件通知发出警报时可能遇到的各种问题。</span><span class="sxs-lookup"><span data-stu-id="a07c7-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="a07c7-149">**问题：** 目标收件人报告他们未收到通知。</span><span class="sxs-lookup"><span data-stu-id="a07c7-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="a07c7-150">**解决方案：** 确保电子邮件筛选器不会阻止通知：</span><span class="sxs-lookup"><span data-stu-id="a07c7-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="a07c7-151">检查 Defender for Endpoint 电子邮件通知是否未发送到垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="a07c7-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="a07c7-152">将其标记为"非垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="a07c7-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="a07c7-153">检查你的电子邮件安全产品是否未阻止来自 Defender for Endpoint 的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a07c7-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="a07c7-154">检查可能捕获和移动 Defender for Endpoint 电子邮件通知的电子邮件应用程序规则。</span><span class="sxs-lookup"><span data-stu-id="a07c7-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a07c7-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="a07c7-155">Related topics</span></span>

- [<span data-ttu-id="a07c7-156">更新数据保留设置</span><span class="sxs-lookup"><span data-stu-id="a07c7-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="a07c7-157">配置高级功能</span><span class="sxs-lookup"><span data-stu-id="a07c7-157">Configure advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="a07c7-158">在 Microsoft Defender for Endpoint 中配置漏洞电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="a07c7-158">Configure vulnerability email notifications in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
