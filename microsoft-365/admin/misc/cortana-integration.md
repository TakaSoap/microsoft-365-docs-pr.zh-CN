---
title: Cortana 与 Office 365 集成
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: '了解如何使用 Cortana 与 Office 365 集成。 你可以在管理中心关闭 Cortana 以限制其对你组织的数据的访问。 '
ms.openlocfilehash: 8f20c9b96ee57dcdf5da99dc08ffeb72465bc515
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361433"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="0cd5e-104">Office 365 中的 Cortana</span><span class="sxs-lookup"><span data-stu-id="0cd5e-104">Cortana in Office 365</span></span>

<span data-ttu-id="0cd5e-105">Cortana 是一种基于云的数字助理以及 Microsoft 365 和 Office 365 服务，可跨设备和 Microsoft 服务工作。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="0cd5e-106">Cortana 可以使用存储在 Microsoft 365 和 Office 365 中的信息来帮助组织中的人员保持最新状态，并获取有关会议、文档和联系人的见解、建议的任务和帮助。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="0cd5e-107">适用于管理员的信息</span><span class="sxs-lookup"><span data-stu-id="0cd5e-107">Info for admins</span></span>

<span data-ttu-id="0cd5e-108">合规性是 Microsoft 向企业客户提出的承诺。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="0cd5e-109">了解有关 Microsoft 合规性框架的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="0cd5e-110">与其他 Microsoft 365 和 Office 365 服务保持一致，合规性的 Cortana 功能受保护且受保护，包括一系列承诺，其中包括保护用户数据免受意外丢失、改变、未经授权的泄露或访问权限，或非法销毁。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="0cd5e-111">所有其他 Cortana 功能（即 Cortana 可选的已连接服务）都服从[Microsoft 服务协议](https://go.microsoft.com/fwlink/p/?LinkId=2109174)和[microsoft 隐私声明。](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span><span class="sxs-lookup"><span data-stu-id="0cd5e-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="0cd5e-112">Cortana 服务分为两个数据类别、**合规**和**可选的已连接服务**，您可以对它们进行控制。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="0cd5e-113">关闭 Cortana 可选的已连接服务</span><span class="sxs-lookup"><span data-stu-id="0cd5e-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="0cd5e-114">可以为组织中的员工关闭 Cortana 可选的已连接服务。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="0cd5e-115">这将在 Windows 和 Cortana 移动应用上的 Cortana 中禁用 Cortana 可选连接的服务。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="0cd5e-116">这包括 Cortana 提醒、列表、任务和其他功能。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="0cd5e-117">兼容类别（即 Cortana OST 体验）中的服务（如 Cortana 的简报电子邮件）和在 Outlook mobile 中播放我的电子邮件将保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="0cd5e-118">在 Microsoft 365 管理中心，选择 "**设置** > **设置**"，然后选择 " **Cortana**"。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="0cd5e-119">选中 "**允许 cortana 可选连接体验" 复选框，以使用组织的 Microsoft 托管数据**来启用或禁用 Cortana 连接体验。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="0cd5e-120">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="0cd5e-121">关闭 Cortana OST 体验</span><span class="sxs-lookup"><span data-stu-id="0cd5e-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="0cd5e-122">您的组织的员工可以通过执行以下步骤逐个选择拒绝 Cortana OST 体验。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="0cd5e-123">打开 Outlook mobile。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="0cd5e-124">转到 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="0cd5e-125">选择 **"播放我的电子邮件"**。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="0cd5e-126">在要禁用的帐户上将切换移到 "关闭"。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="0cd5e-127">简报电子邮件</span><span class="sxs-lookup"><span data-stu-id="0cd5e-127">Briefing email</span></span>

<span data-ttu-id="0cd5e-128">禁用任务栏上的 Cortana 不会禁用 Cortana 的简报电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="0cd5e-129">员工必须单独取消订阅。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="0cd5e-130">组织中的个人可以通过在邮件的页脚中选择 "**取消订阅**" 来退出 Cortana 的简介电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0cd5e-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>
