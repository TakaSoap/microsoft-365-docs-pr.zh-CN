---
title: 保护非托管的 Windows 10 电脑和 Mac
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 使用 BYOD 保护非托管或自带设备 (BYOD) Microsoft 365。
ms.openlocfilehash: 40e94e2f961ab34827de4ce5e43e100af53a7340
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227495"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="1483f-103">保护非托管的 Windows 10 电脑和 Mac</span><span class="sxs-lookup"><span data-stu-id="1483f-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="1483f-104">可以通过在 Microsoft Intune 中注册 Windows 10 来管理这些电脑和 Mac，这允许你在访问环境中的数据之前确保它们正常运行和安全。</span><span class="sxs-lookup"><span data-stu-id="1483f-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="1483f-105">但是，许多市场活动和小型企业都包括自带设备办公 (BYOD) ，这将不会由组织管理。</span><span class="sxs-lookup"><span data-stu-id="1483f-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="1483f-106">对于这些非托管电脑和 Mac，请使用本文确保配置最低安全性功能。</span><span class="sxs-lookup"><span data-stu-id="1483f-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="1483f-107">保护运行 Windows 10 Mac 的计算机</span><span class="sxs-lookup"><span data-stu-id="1483f-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="1483f-108">如果你Windows 10电脑或 Mac 不由你的组织管理，请确保配置这些安全功能。</span><span class="sxs-lookup"><span data-stu-id="1483f-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="1483f-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1483f-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="1483f-110">**打开设备加密**</span><span class="sxs-lookup"><span data-stu-id="1483f-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="1483f-111">设备加密适用于各种Windows，并且有助于通过加密数据来保护数据。</span><span class="sxs-lookup"><span data-stu-id="1483f-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="1483f-112">如果打开设备加密，则只有经过授权的个人才能访问你的设备和数据。</span><span class="sxs-lookup"><span data-stu-id="1483f-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="1483f-113">有关 [说明，请参阅打开设备](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 加密。</span><span class="sxs-lookup"><span data-stu-id="1483f-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="1483f-114">如果设备加密在你的设备上不可用，你可以改为打开标准 [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 加密。</span><span class="sxs-lookup"><span data-stu-id="1483f-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="1483f-115"> (BitLocker 在 Windows 10 家庭版 版本上) </span><span class="sxs-lookup"><span data-stu-id="1483f-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="1483f-116">**使用安全保护Windows 安全中心**</span><span class="sxs-lookup"><span data-stu-id="1483f-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="1483f-117">如果你已Windows 10，你将使用最新防病毒Windows 安全中心。</span><span class="sxs-lookup"><span data-stu-id="1483f-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="1483f-118">首次启动Windows 10时，Windows 安全中心通过扫描恶意软件、恶意软件 (、病毒和安全威胁) 并主动帮助保护电脑。</span><span class="sxs-lookup"><span data-stu-id="1483f-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="1483f-119">Windows 安全中心实时保护扫描你在电脑上下载或运行的所有内容。</span><span class="sxs-lookup"><span data-stu-id="1483f-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="1483f-120">Windows 更新网站会自动下载 Windows 安全的更新，以帮助保护电脑的安全，防止其遭到威胁。</span><span class="sxs-lookup"><span data-stu-id="1483f-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="1483f-121">如果你有早期版本的 Windows并且正在使用Microsoft Security Essentials，则建议移动到 Windows 安全中心。</span><span class="sxs-lookup"><span data-stu-id="1483f-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="1483f-122">有关详细信息，请参阅使用帮助[保护我的设备Windows 安全中心。](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="1483f-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="1483f-123">**打开Windows防火墙**</span><span class="sxs-lookup"><span data-stu-id="1483f-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="1483f-124">即使已打开其他Windows，也应始终运行防火墙。</span><span class="sxs-lookup"><span data-stu-id="1483f-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="1483f-125">如果Windows防火墙， (你的设备和网络，如果你有一个) 未经授权访问。</span><span class="sxs-lookup"><span data-stu-id="1483f-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="1483f-126">有关[说明Windows打开或关闭防火墙](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="1483f-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions.</span></span>

## <a name="mac"></a>[<span data-ttu-id="1483f-127">Mac</span><span class="sxs-lookup"><span data-stu-id="1483f-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="1483f-128">**使用 FileVault 加密 Mac 磁盘**</span><span class="sxs-lookup"><span data-stu-id="1483f-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="1483f-129">磁盘加密在设备丢失或被盗时保护数据。</span><span class="sxs-lookup"><span data-stu-id="1483f-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="1483f-130">FileVault 全磁盘加密有助于防止对启动磁盘上的信息进行未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="1483f-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="1483f-131">有关 [说明，请参阅使用 FileVault](https://support.apple.com/HT204837) 加密 Mac 上的启动磁盘。</span><span class="sxs-lookup"><span data-stu-id="1483f-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="1483f-132">**保护 Mac 免受恶意软件的攻击**</span><span class="sxs-lookup"><span data-stu-id="1483f-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="1483f-133">Microsoft 建议在 Mac 上安装和使用可靠的防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="1483f-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="1483f-134">有关选项列表，请参阅以下文章 [：Best Mac antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。</span><span class="sxs-lookup"><span data-stu-id="1483f-134">See the following article for a list of choices: [Best Mac antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="1483f-135">您还可以通过使用仅来自可靠来源的软件来降低恶意软件的风险。</span><span class="sxs-lookup"><span data-stu-id="1483f-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="1483f-136">安全与&首选项中的设置允许你指定安装在 Mac 上的软件源。</span><span class="sxs-lookup"><span data-stu-id="1483f-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="1483f-137">有关详细信息，请参阅保护 [Mac 免受恶意软件的攻击](https://support.apple.com/kb/PH25087)。</span><span class="sxs-lookup"><span data-stu-id="1483f-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="1483f-138">**打开防火墙保护**</span><span class="sxs-lookup"><span data-stu-id="1483f-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="1483f-139">当连接到 Internet 或网络时，使用防火墙设置保护 Mac 免受其他计算机启动的不需要的联系人的干扰。</span><span class="sxs-lookup"><span data-stu-id="1483f-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="1483f-140">如果没有此保护，Mac 可能更容易受到未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="1483f-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="1483f-141">有关 [说明，请参阅有关应用程序](https://support.apple.com/HT201642) 防火墙。</span><span class="sxs-lookup"><span data-stu-id="1483f-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
