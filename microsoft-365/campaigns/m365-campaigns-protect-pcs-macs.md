---
title: 保护非托管 Windows 10 电脑和 Mac
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 针对针对市场活动的 Microsoft 365 防御网络钓鱼和其他攻击。
ms.openlocfilehash: 8b83fa9c145f2c17347fc4c2983c64d4003f46c8
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183230"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="e5ede-103">保护非托管 Windows 10 电脑和 Mac</span><span class="sxs-lookup"><span data-stu-id="e5ede-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="e5ede-104">你可以通过将这些电脑和 Mac 注册到 Microsoft Intune 中来管理 Windows 10 电脑和 Mac, 这使你能够在访问环境中的数据之前确保这些电脑和 Mac 的健康和安全。</span><span class="sxs-lookup"><span data-stu-id="e5ede-104">You can manage Windows 10 PCs and Macs by enrolling these into Microsoft Intune, which allows you to ensure these are healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="e5ede-105">但是, 许多市场活动和小型企业都包含的人员将拥有自己的设备 (byod), 而不会由组织进行管理。</span><span class="sxs-lookup"><span data-stu-id="e5ede-105">However, many campaigns and small businesses include staff that bring their own devices (byod) which will not be managed by the organization.</span></span> <span data-ttu-id="e5ede-106">对于这些非托管电脑和 Mac, 请使用本文以确保配置了最低安全功能。</span><span class="sxs-lookup"><span data-stu-id="e5ede-106">For these unmanaged PCs and Macs, use this article to ensure minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="e5ede-107">保护运行 Windows 10 或 Mac 的计算机</span><span class="sxs-lookup"><span data-stu-id="e5ede-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="e5ede-108">如果你的 Windows 10 电脑或 Mac 不受你的组织的管理, 请确保配置这些安全功能。</span><span class="sxs-lookup"><span data-stu-id="e5ede-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10tabwindows10"></a>[<span data-ttu-id="e5ede-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e5ede-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="e5ede-110">**启用设备加密**</span><span class="sxs-lookup"><span data-stu-id="e5ede-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="e5ede-111">设备加密在广泛的 Windows 设备上可用, 并通过对其加密来帮助保护您的数据。</span><span class="sxs-lookup"><span data-stu-id="e5ede-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="e5ede-112">如果打开设备加密, 只有经过授权的个人才能访问您的设备和数据。</span><span class="sxs-lookup"><span data-stu-id="e5ede-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="e5ede-113">有关说明, 请参阅[打开设备加密](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption)。</span><span class="sxs-lookup"><span data-stu-id="e5ede-113">See [turn on device encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="e5ede-114">如果设备加密在设备上不可用, 则可以改为打开标准[BitLocker 加密](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption)。</span><span class="sxs-lookup"><span data-stu-id="e5ede-114">If device encryption is not available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="e5ede-115">(BitLocker 在 Windows 10 家庭版中不可用。)</span><span class="sxs-lookup"><span data-stu-id="e5ede-115">(BitLocker is not available on Windows 10 Home edition.)</span></span> 



<span data-ttu-id="e5ede-116">**使用 Windows 安全保护你的设备**</span><span class="sxs-lookup"><span data-stu-id="e5ede-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="e5ede-117">如果你有 Windows 10, 你将获得最新的使用 Windows 安全的防病毒保护。</span><span class="sxs-lookup"><span data-stu-id="e5ede-117">If you have Windows 10, you’ll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="e5ede-118">当您首次启动 Windows 10 时, Windows 安全处于打开状态, 并通过扫描恶意软件 (恶意软件)、病毒和安全威胁来主动帮助保护你的电脑。</span><span class="sxs-lookup"><span data-stu-id="e5ede-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="e5ede-119">Windows 安全使用实时保护来扫描您在电脑上下载或运行的所有内容。</span><span class="sxs-lookup"><span data-stu-id="e5ede-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="e5ede-120">Windows 更新会自动下载 Windows 安全更新, 以帮助确保你的电脑安全并保护其免受威胁的侵扰。</span><span class="sxs-lookup"><span data-stu-id="e5ede-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="e5ede-121">如果你具有早期版本的 Windows 且正在使用 Microsoft 安全概要, 最好移动到 Windows 安全。</span><span class="sxs-lookup"><span data-stu-id="e5ede-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it’s a good idea to move to Windows Security.</span></span> <span data-ttu-id="e5ede-122">有关详细信息, 请参阅[help 使用 Windows 安全保护我的设备](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security)。</span><span class="sxs-lookup"><span data-stu-id="e5ede-122">See [help protect my device with Windows Security](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security) for more information.</span></span>

<span data-ttu-id="e5ede-123">**启用 Windows 防火墙**</span><span class="sxs-lookup"><span data-stu-id="e5ede-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="e5ede-124">即使已打开另一个防火墙, 也应始终运行 Windows 防火墙。</span><span class="sxs-lookup"><span data-stu-id="e5ede-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="e5ede-125">关闭 Windows 防火墙可能会使你的设备 (如果你的网络可用) 更容易受到未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="e5ede-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="e5ede-126">请参阅[打开或关闭 Windows 防火墙](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)获取说明</span><span class="sxs-lookup"><span data-stu-id="e5ede-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mactabmac"></a>[<span data-ttu-id="e5ede-127">Mac</span><span class="sxs-lookup"><span data-stu-id="e5ede-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="e5ede-128">**使用 FileVault 对您的 Mac 磁盘进行加密**</span><span class="sxs-lookup"><span data-stu-id="e5ede-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="e5ede-129">磁盘加密可在设备丢失或被盗时保护数据。</span><span class="sxs-lookup"><span data-stu-id="e5ede-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="e5ede-130">FileVault 的完整磁盘加密有助于防止对您的启动磁盘上的信息进行未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="e5ede-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="e5ede-131">有关说明, 请参阅[使用 FileVault 对 Mac 上的启动盘进行加密](https://support.apple.com/HT204837)。</span><span class="sxs-lookup"><span data-stu-id="e5ede-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="e5ede-132">**保护 mac 免受恶意软件的攻击**</span><span class="sxs-lookup"><span data-stu-id="e5ede-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="e5ede-133">Microsoft 建议您在 Mac 上安装和使用可靠的防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="e5ede-133">Microsoft recommends you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="e5ede-134">请参阅以下文章, 获取选项列表:[最佳 Mac 防病毒 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。</span><span class="sxs-lookup"><span data-stu-id="e5ede-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="e5ede-135">您还可以使用仅来自可靠来源的软件来降低恶意软件的风险。</span><span class="sxs-lookup"><span data-stu-id="e5ede-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="e5ede-136">Security & 隐私首选项中的设置允许您指定 Mac 上安装的软件的来源。</span><span class="sxs-lookup"><span data-stu-id="e5ede-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="e5ede-137">有关详细信息, 请参阅[保护 Mac 免受恶意软件的攻击](https://support.apple.com/kb/PH25087)。</span><span class="sxs-lookup"><span data-stu-id="e5ede-137">See [protect your Mac from malware](https://support.apple.com/kb/PH25087) for more information.</span></span>

<span data-ttu-id="e5ede-138">**启用防火墙保护**</span><span class="sxs-lookup"><span data-stu-id="e5ede-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="e5ede-139">在连接到 Internet 或网络时, 使用防火墙设置来保护 Mac 免受其他计算机启动的不需要的联系人的阻止。</span><span class="sxs-lookup"><span data-stu-id="e5ede-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you’re connected to the Internet or a network.</span></span> <span data-ttu-id="e5ede-140">如果没有此保护, 你的 Mac 可能更容易受到未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="e5ede-140">Without this protection your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="e5ede-141">有关说明, 请参阅[关于应用程序防火墙](https://support.apple.com/HT201642)。</span><span class="sxs-lookup"><span data-stu-id="e5ede-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
