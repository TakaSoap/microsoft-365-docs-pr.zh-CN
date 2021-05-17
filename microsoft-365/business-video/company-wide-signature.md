---
title: 创建公司范围的签名
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 了解如何创建公司范围的电子邮件签名。
ms.openlocfilehash: a1a85826be2a799b56cf3d06b6416778470a116f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578947"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="dbab1-103">创建公司范围的电子邮件签名</span><span class="sxs-lookup"><span data-stu-id="dbab1-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="dbab1-104">公司范围内的电子邮件签名将显示在组织中人员发送的每封电子邮件上。</span><span class="sxs-lookup"><span data-stu-id="dbab1-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="dbab1-105">您可以使用它显示重要详细信息，如公司联系人信息或法律免责声明。</span><span class="sxs-lookup"><span data-stu-id="dbab1-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="dbab1-106">试一试！</span><span class="sxs-lookup"><span data-stu-id="dbab1-106">Try it!</span></span>

1. <span data-ttu-id="dbab1-107">在管理Microsoft 365中，选择 **"Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="dbab1-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="dbab1-108">选择 **"邮件流"。**</span><span class="sxs-lookup"><span data-stu-id="dbab1-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="dbab1-109">选择 **"添加 +**"，然后选择"**应用免责声明"。**</span><span class="sxs-lookup"><span data-stu-id="dbab1-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="dbab1-110">在" **新建规则"** 页上：</span><span class="sxs-lookup"><span data-stu-id="dbab1-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="dbab1-111">输入规则的名称。</span><span class="sxs-lookup"><span data-stu-id="dbab1-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="dbab1-112">From the **Apply this rule if** drop-down list， select Apply to all **messages**.</span><span class="sxs-lookup"><span data-stu-id="dbab1-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="dbab1-113">在 **"执行以下操作"** 下拉列表中，验证 **是否显示"附加** 免责声明"。</span><span class="sxs-lookup"><span data-stu-id="dbab1-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="dbab1-114">在页面右侧，选择 **"输入** 文本"，然后在"指定免责声明"文本框中输入电子邮件 **签名** 的文本。</span><span class="sxs-lookup"><span data-stu-id="dbab1-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="dbab1-115">您可以通过使用 HTML 设置文本的格式来改进签名的外观。</span><span class="sxs-lookup"><span data-stu-id="dbab1-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="dbab1-116">如果希望图像显示在签名中，则需要使用该图像的公开 URL。</span><span class="sxs-lookup"><span data-stu-id="dbab1-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="dbab1-117">浏览到 Web 上的图像，右键单击它，然后选择复制 **图像地址**。</span><span class="sxs-lookup"><span data-stu-id="dbab1-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="dbab1-118">将地址粘贴到" **指定免责声明** "文本框中。</span><span class="sxs-lookup"><span data-stu-id="dbab1-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="dbab1-119">选择 **"确定**"，然后向下滚动。</span><span class="sxs-lookup"><span data-stu-id="dbab1-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="dbab1-120">若要确保签名适用于加密电子邮件，请添加回退选项。</span><span class="sxs-lookup"><span data-stu-id="dbab1-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="dbab1-121">在页面右侧，选择"选择一个"，选择"**自动** 换行"，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="dbab1-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="dbab1-122">向下滚动，将模式设置为"强制 **"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="dbab1-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="dbab1-123">将显示一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="dbab1-123">A warning message will appear.</span></span> <span data-ttu-id="dbab1-124">选择 **"是** "将规则应用于所有未来邮件。</span><span class="sxs-lookup"><span data-stu-id="dbab1-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="dbab1-125">已创建签名。</span><span class="sxs-lookup"><span data-stu-id="dbab1-125">Your signature has been created.</span></span> <span data-ttu-id="dbab1-126">发送下一封电子邮件时，不会看到刚创建的签名，但电子邮件收件人将看到它。</span><span class="sxs-lookup"><span data-stu-id="dbab1-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>