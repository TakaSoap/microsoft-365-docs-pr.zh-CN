---
title: 验证新设备
description: 在订购设备之前，请获取每个型号之一并进行测试
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 772636fd72074c8fad30daa3eb25b785519e7772
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246023"
---
# <a name="validate-new-devices"></a><span data-ttu-id="7dd97-103">验证新设备</span><span class="sxs-lookup"><span data-stu-id="7dd97-103">Validate new devices</span></span>

<span data-ttu-id="7dd97-104">无论你完全不是Microsoft 托管桌面订阅者还是长期订阅者，最好测试首次在服务中注册的任何设备型号的示例。</span><span class="sxs-lookup"><span data-stu-id="7dd97-104">Whether you're completely new to Microsoft Managed Desktop or a long-time subscriber, it's best to test an example of any device model you're enrolling in the service for the first time.</span></span> <span data-ttu-id="7dd97-105">无论你是订购全新的设备还是重新使用现有设备，包括建议在购买商业Microsoft 托管桌面购买Windows 10 专业版[的设备](https://www.microsoft.com/windowsforbusiness/view-all-devices)，都是如此。</span><span class="sxs-lookup"><span data-stu-id="7dd97-105">This is true whether you're ordering brand-new devices or reusing existing ones, including devices recommended for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span> <span data-ttu-id="7dd97-106">在该网站中，查看建议用于服务的设备，方法为展开"按筛选"区域中的功能，然后选择 **"Microsoft 托管桌面"。**</span><span class="sxs-lookup"><span data-stu-id="7dd97-106">At that site, view the devices recommended for use with the service by expanding **Features** in the **Filter by** area, and then selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="7dd97-107">验证设备可确保它们能够提供你期望的用户体验。</span><span class="sxs-lookup"><span data-stu-id="7dd97-107">Validating devices ensures that they'll deliver the user experience you expect.</span></span>

## <a name="validate-devices"></a><span data-ttu-id="7dd97-108">验证设备</span><span class="sxs-lookup"><span data-stu-id="7dd97-108">Validate devices</span></span>

1. <span data-ttu-id="7dd97-109">通过以下文章中的步骤，以一个或多个新模型示例为例：</span><span class="sxs-lookup"><span data-stu-id="7dd97-109">Take one or more examples of new models through the steps in the following articles:</span></span>
    - [<span data-ttu-id="7dd97-110">设置 Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="7dd97-110">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
    - [<span data-ttu-id="7dd97-111">本地化用户体验</span><span class="sxs-lookup"><span data-stu-id="7dd97-111">Localize the user experience</span></span>](localization.md)
    - [<span data-ttu-id="7dd97-112">使用 Autopilot 和注册状态页的首次运行体验</span><span class="sxs-lookup"><span data-stu-id="7dd97-112">First-run experience with Autopilot and the Enrollment Status Page</span></span>](esp-first-run.md)
    - [<span data-ttu-id="7dd97-113">Windows 10 位置服务</span><span class="sxs-lookup"><span data-stu-id="7dd97-113">Windows 10 location service</span></span>](device-location.md)
    - [<span data-ttu-id="7dd97-114">开始使用应用程序控制</span><span class="sxs-lookup"><span data-stu-id="7dd97-114">Get started with app control</span></span>](get-started-app-control.md)
    - [<span data-ttu-id="7dd97-115">将应用部署到设备</span><span class="sxs-lookup"><span data-stu-id="7dd97-115">Deploy apps to devices</span></span>](deploy-apps.md)
2. <span data-ttu-id="7dd97-116">验证以下体验是否正常工作，而不出现任何失败、错误或提示：</span><span class="sxs-lookup"><span data-stu-id="7dd97-116">Verify that the following experiences work without any failures, errors, or prompts:</span></span>
    - <span data-ttu-id="7dd97-117">加入网络和用户登录后的 Autopilot 体验</span><span class="sxs-lookup"><span data-stu-id="7dd97-117">The Autopilot experience after joining the network and the user signs in</span></span>
    - <span data-ttu-id="7dd97-118">如果已启用"注册 [状态"页，](esp-first-run.md)它将正常工作。</span><span class="sxs-lookup"><span data-stu-id="7dd97-118">If you've enabled the [Enrollment Status Page](esp-first-run.md), it works.</span></span>
    - <span data-ttu-id="7dd97-119">用户可以登录到 Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="7dd97-119">User can sign into to Office applications</span></span>
    - <span data-ttu-id="7dd97-120">OneDrive文件夹同步，Windows桌面、文档和图片</span><span class="sxs-lookup"><span data-stu-id="7dd97-120">OneDrive folders sync, including Windows Desktop, Documents, and Pictures</span></span>
    - <span data-ttu-id="7dd97-121">设备接收更新、策略和业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="7dd97-121">Device receives updates, policies, and line-of-business applications</span></span>
3. <span data-ttu-id="7dd97-122">查看"设备清单"报告中报告的设备和硬件 [要求](../working-with-managed-desktop/device-inventory-report.md) ，以检查它们是否与预期匹配。</span><span class="sxs-lookup"><span data-stu-id="7dd97-122">Review the reported devices and hardware requirements in the [Device inventory report](../working-with-managed-desktop/device-inventory-report.md) to check that they match what you expect.</span></span>

<span data-ttu-id="7dd97-123">如果发生任何问题，可以在 [管理门户](../working-with-managed-desktop/admin-support.md) 中请求支持。</span><span class="sxs-lookup"><span data-stu-id="7dd97-123">If any problems occur, you can [request support](../working-with-managed-desktop/admin-support.md) in the Admin portal.</span></span>

<span data-ttu-id="7dd97-124">如果一切运行良好，你已准备好为部署所需的其余已验证设备排序。</span><span class="sxs-lookup"><span data-stu-id="7dd97-124">If everything goes well, you're ready to order the rest of the validated devices you need for your deployment.</span></span>