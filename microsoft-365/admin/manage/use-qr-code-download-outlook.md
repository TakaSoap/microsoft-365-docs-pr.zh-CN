---
title: 使用 QR 代码登录到 Outlook移动应用
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 了解如何使用 QR 代码在移动设备上进行身份验证和Outlook下载。
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914962"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="e0c42-103">使用 QR 代码登录到 Outlook移动应用</span><span class="sxs-lookup"><span data-stu-id="e0c42-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0c42-104">此功能仅适用于在管理中心内打开定向发布Microsoft 365使用。</span><span class="sxs-lookup"><span data-stu-id="e0c42-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e0c42-105">若要打开定向发布并了解其工作方式的详细信息，请参阅 [设置标准或定向发布选项](release-options-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e0c42-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="e0c42-106">未来几周内，我们将通过公共预览版扩展到更多组织。</span><span class="sxs-lookup"><span data-stu-id="e0c42-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="e0c42-107">公共预览版可提前访问Microsoft 365功能。</span><span class="sxs-lookup"><span data-stu-id="e0c42-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="e0c42-108">作为Microsoft 365管理员，你可以让用户登录到 Outlook for Android 或 iOS 应用，而无需输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e0c42-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="e0c42-109">通过扫描 QR 代码，用户可以安全地进行身份验证并登录到Outlook登录。</span><span class="sxs-lookup"><span data-stu-id="e0c42-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="e0c42-110">在Outlook或其他桌面Outlook应用程序中，用户可能会看到通知，通知他们可在Outlook使用移动设备。</span><span class="sxs-lookup"><span data-stu-id="e0c42-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="e0c42-111">管理员可以使用 Powershell 管理Exchange通知。</span><span class="sxs-lookup"><span data-stu-id="e0c42-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="e0c42-112">如果用户选择向自己发送短信短信，以在移动设备上下载应用，QR 代码将显示在其计算机上。</span><span class="sxs-lookup"><span data-stu-id="e0c42-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="e0c42-113">他们将能够扫描 QR 代码，以登录到Outlook或平板电脑上的设备。</span><span class="sxs-lookup"><span data-stu-id="e0c42-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="e0c42-114">此 QR 代码是只能兑换一次短期令牌。</span><span class="sxs-lookup"><span data-stu-id="e0c42-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="e0c42-115">在某些情况下，用户必须在计算机上重新进行身份验证以生成 QR 代码。</span><span class="sxs-lookup"><span data-stu-id="e0c42-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="e0c42-116">使用 Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0c42-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="e0c42-117">默认情况下，启用此功能。</span><span class="sxs-lookup"><span data-stu-id="e0c42-117">This feature is on by default.</span></span> <span data-ttu-id="e0c42-118">若要禁用此功能，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="e0c42-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="e0c42-119">[连接 PowerShell Exchange 。](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="e0c42-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="e0c42-120">使用 PowerShell，可以禁用通知用户有关Outlook通知。</span><span class="sxs-lookup"><span data-stu-id="e0c42-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="e0c42-121">这还将阻止显示 QR 代码登录流。</span><span class="sxs-lookup"><span data-stu-id="e0c42-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="e0c42-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="e0c42-122">Related topics</span></span>

[<span data-ttu-id="e0c42-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="e0c42-123">Set-OrganizationConfig</span></span>](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)