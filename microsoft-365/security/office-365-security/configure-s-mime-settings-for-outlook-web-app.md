---
title: 配置 S/MIME 设置 - 适用于 Web 上的 Outlook 的 Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: 有关 Exchange Online 管理员在 Exchange Online 中查看和配置 Outlook 网页版中的 S/MIME 设置所需执行的操作的简短描述。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825697"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="2a1e4-103">为 Outlook 网页版配置 Exchange Online 中的 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="2a1e4-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="2a1e4-104">作为 Exchange Online 管理员，可以从以前称为Outlook Web App) 设置 Outlook (网页版应用，以允许发送和接收受 S/MIME 保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="2a1e4-105">在 Exchange Online PowerShell 中使用**Get-SmimeConfig 和 Set-SmimeConfig** cmdlet 来查看和管理此功能。 **Get-SmimeConfig**</span><span class="sxs-lookup"><span data-stu-id="2a1e4-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="2a1e4-106">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="2a1e4-107">有关语法和参数的详细信息，请参阅[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)和[Set-SmimeConfig。](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="2a1e4-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="2a1e4-108">新的 Microsoft Edge 基于 Chromium (的注意事) </span><span class="sxs-lookup"><span data-stu-id="2a1e4-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="2a1e4-109">若要在[新的 Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) Web 浏览器中使用 Outlook 网页版中的 S/MIME，必须设置 (或其他管理员) 才能在**ExtensionInstallForcelist**新的 Microsoft Edge 中安装 Microsoft S/MIME 扩展。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="2a1e4-110">策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="2a1e4-111">另请注意，应用此策略要求已加入域或已加入 Azure AD 的设备，因此在新的 Microsoft Edge 浏览器中使用 S/MIME 可有效地需要已加入域或加入 Azure AD 的设备。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="2a1e4-112">有关**ExtensionInstallForcelist 策略的详细信息，** 请参阅[ExtensionInstallForcelist。](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="2a1e4-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="2a1e4-113">此步骤是使用新 Microsoft Edge 的先决条件;不替换用户安装的 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="2a1e4-114">在用户首次使用 S/MIME 期间，会提示用户在 Web 上的 Outlook 中下载和安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="2a1e4-115">或者，用户可以主动转到其 Outlook 网页版设置中的 **S/MIME，** 以获取此控件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="2a1e4-116">Chrome 的注意事项</span><span class="sxs-lookup"><span data-stu-id="2a1e4-116">Considerations for Chrome</span></span>

<span data-ttu-id="2a1e4-117">若要在 Google Chrome Web 浏览器的 Outlook 网页版中使用 S/MIME，必须将 (或其他管理员) 设置为 Set and configure the Chromium policy named **ExtensionInstallForcelist** 以在 Chrome 中安装 Microsoft S/MIME 扩展。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="2a1e4-118">策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="2a1e4-119">请注意，应用此策略需要加入域的计算机，因此在 Chrome 中使用 S/MIME 实际上需要加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="2a1e4-120">有关**ExtensionInstallForcelist 策略的详细信息，** 请参阅[ExtensionInstallForcelist。](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="2a1e4-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="2a1e4-121">此步骤是使用 Chrome 的先决条件;不替换用户安装的 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="2a1e4-122">在用户首次使用 S/MIME 期间，会提示用户在 Web 上的 Outlook 中下载和安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="2a1e4-123">或者，用户可以主动转到其 Outlook 网页版设置中的 **S/MIME，** 以获取此控件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="2a1e4-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="2a1e4-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a1e4-124">For more information</span></span>

[<span data-ttu-id="2a1e4-125">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="2a1e4-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
