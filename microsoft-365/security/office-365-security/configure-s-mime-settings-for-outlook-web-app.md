---
title: 为 web 上的 Outlook 配置 S/MIME 设置-Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange online 管理员在 Exchange Online 中查看和配置 Outlook 网页中的 S/MIME 设置时需要执行的操作的简短说明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9f4e6c33369640ad66956568959dd02b01c4fb9
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517481"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="6d3a8-103">在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="6d3a8-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="6d3a8-104">作为 Exchange Online 管理员，您可以设置 web 上的 Outlook （以前称为 "Outlook Web App"），以允许发送和接收受 S/MIME 保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="6d3a8-105">使用**get-smimeconfig**和**Get-smimeconfig** Cmdlet 在 Exchange Online PowerShell 中查看和管理此功能。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="6d3a8-106">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="6d3a8-107">有关语法和参数的详细信息，请参阅[get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)和[get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="6d3a8-108">新 Microsoft Edge 的注意事项（基于 Chromium）</span><span class="sxs-lookup"><span data-stu-id="6d3a8-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="6d3a8-109">若要在新的[Microsoft edge](https://www.microsoft.com/windows/microsoft-edge) web 浏览器中使用 web 上的 Outlook 中的 S/MIME，您（或另一个管理员）必须设置和配置名为**ExtensionInstallForcelist**的 microsoft Edge 浏览器策略，以便在新的 Microsoft Edge 中安装 microsoft S/MIME 扩展。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="6d3a8-110">策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="6d3a8-111">请注意，应用此策略需要加入域或 Azure 的设备，因此在新的 Microsoft Edge 浏览器中使用 S/MIME 将有效地要求加入域或 Azure 已加入 Azure 的设备。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="6d3a8-112">有关**ExtensionInstallForcelist**策略的详细信息，请参阅[ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="6d3a8-113">此步骤是使用新的 Microsoft Edge 的先决条件;它不会替换用户安装的 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="6d3a8-114">在首次使用 S/MIME 时，系统会提示用户在 web 上的 Outlook 中下载并安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="6d3a8-115">或者，用户可以在其 Outlook 的 web 设置中主动转到**S/MIME** ，以获取该控件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="6d3a8-116">Chrome 注意事项</span><span class="sxs-lookup"><span data-stu-id="6d3a8-116">Considerations for Chrome</span></span>

<span data-ttu-id="6d3a8-117">若要在 Google Chrome web 浏览器中使用 web 上的 Outlook 中的 S/MIME，您（或另一个管理员）必须设置和配置名为**ExtensionInstallForcelist**的 Chromium 策略，以在 Chrome 中安装 Microsoft S/mime 扩展。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="6d3a8-118">策略值为 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="6d3a8-119">请注意，应用此策略需要加入域的计算机，因此使用 Chrome 中的 S/MIME 可有效地要求加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="6d3a8-120">有关**ExtensionInstallForcelist**策略的详细信息，请参阅[ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="6d3a8-121">此步骤是使用 Chrome 的先决条件;它不会替换用户安装的 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="6d3a8-122">在首次使用 S/MIME 时，系统会提示用户在 web 上的 Outlook 中下载并安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="6d3a8-123">或者，用户可以在其 Outlook 的 web 设置中主动转到**S/MIME** ，以获取该控件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="6d3a8-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="6d3a8-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="6d3a8-124">For more information</span></span>

[<span data-ttu-id="6d3a8-125">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="6d3a8-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
