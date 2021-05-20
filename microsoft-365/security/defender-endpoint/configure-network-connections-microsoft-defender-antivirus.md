---
title: 配置和验证 Microsoft Defender 防病毒软件网络连接
description: 配置和测试与云保护Microsoft Defender 防病毒的连接。
keywords: 防病毒， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 攻击性， 保护级别
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572521"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="af9dd-104">配置和验证 Microsoft Defender 防病毒软件网络连接</span><span class="sxs-lookup"><span data-stu-id="af9dd-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="af9dd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="af9dd-105">**Applies to:**</span></span>

- [<span data-ttu-id="af9dd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af9dd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="af9dd-107">为了确保Microsoft Defender 防病毒保护正常工作，需要配置网络以允许终结点和某些 Microsoft 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="af9dd-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="af9dd-108">本文列出必须允许的连接（如使用防火墙规则）并提供验证连接的说明。</span><span class="sxs-lookup"><span data-stu-id="af9dd-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="af9dd-109">正确配置保护有助于确保从云提供的保护服务获得最佳价值。</span><span class="sxs-lookup"><span data-stu-id="af9dd-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="af9dd-110">有关网络连接的一些详细信息，请参阅博客文章 [对 Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 终结点的重要更改。</span><span class="sxs-lookup"><span data-stu-id="af9dd-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="af9dd-111">还可以访问 Microsoft Defender for Endpoint 演示[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 确认以下功能是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="af9dd-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="af9dd-112">云端保护</span><span class="sxs-lookup"><span data-stu-id="af9dd-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="af9dd-113">快速学习 (包括首次看到时阻止) </span><span class="sxs-lookup"><span data-stu-id="af9dd-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="af9dd-114">可能不需要的应用程序阻止</span><span class="sxs-lookup"><span data-stu-id="af9dd-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="af9dd-115">允许连接到 Microsoft Defender 防病毒 云服务</span><span class="sxs-lookup"><span data-stu-id="af9dd-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="af9dd-116">云Microsoft Defender 防病毒为终结点提供快速、强大的保护。</span><span class="sxs-lookup"><span data-stu-id="af9dd-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="af9dd-117">启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。</span><span class="sxs-lookup"><span data-stu-id="af9dd-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

> [!NOTE]
> <span data-ttu-id="af9dd-118">Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。</span><span class="sxs-lookup"><span data-stu-id="af9dd-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="af9dd-119">尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护，而是使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。</span><span class="sxs-lookup"><span data-stu-id="af9dd-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="af9dd-120">请参阅[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)，了解有关使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或在 Windows 安全中心 应用中各个客户端上启用服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af9dd-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="af9dd-121">启用该服务后，可能需要配置网络或防火墙以允许其与终结点连接。</span><span class="sxs-lookup"><span data-stu-id="af9dd-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="af9dd-122">由于你的保护是一项云服务，计算机必须能够访问 Internet 并访问 Microsoft Defender，Office 365机器学习服务。</span><span class="sxs-lookup"><span data-stu-id="af9dd-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="af9dd-123">请勿将 URL `*.blob.core.windows.net` 从任何类型的网络检查中排除。</span><span class="sxs-lookup"><span data-stu-id="af9dd-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="af9dd-124">下表列出了服务及其关联的 URL。</span><span class="sxs-lookup"><span data-stu-id="af9dd-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="af9dd-125">请确保没有防火墙或网络筛选规则拒绝访问这些 URL，或者您可能需要专门为它们创建允许规则 (排除 URL `*.blob.core.windows.net`) 。</span><span class="sxs-lookup"><span data-stu-id="af9dd-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="af9dd-126">下面提及 URL 正在使用端口 443 进行通信。</span><span class="sxs-lookup"><span data-stu-id="af9dd-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="af9dd-127">**服务**</span><span class="sxs-lookup"><span data-stu-id="af9dd-127">**Service**</span></span>| <span data-ttu-id="af9dd-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="af9dd-128">**Description**</span></span> |<span data-ttu-id="af9dd-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="af9dd-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="af9dd-130">Microsoft Defender 防病毒云提供的保护服务，也称为MICROSOFT ACTIVE PROTECTION SERVICE (MAPS) </span><span class="sxs-lookup"><span data-stu-id="af9dd-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="af9dd-131">由Microsoft Defender 防病毒提供云保护</span><span class="sxs-lookup"><span data-stu-id="af9dd-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="af9dd-132">MICROSOFT Update Service (MU) </span><span class="sxs-lookup"><span data-stu-id="af9dd-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="af9dd-133">Windows更新服务 (WU) </span><span class="sxs-lookup"><span data-stu-id="af9dd-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="af9dd-134">安全智能和产品更新</span><span class="sxs-lookup"><span data-stu-id="af9dd-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="af9dd-135">有关详细信息，请参阅[Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="af9dd-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="af9dd-136">安全智能更新 ADL (备用) </span><span class="sxs-lookup"><span data-stu-id="af9dd-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="af9dd-137">如果安装的安全Microsoft Defender 防病毒在安装后 7 天或 7 (过期，则安全智能更新的备用) </span><span class="sxs-lookup"><span data-stu-id="af9dd-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="af9dd-138">恶意软件提交存储</span><span class="sxs-lookup"><span data-stu-id="af9dd-138">Malware submission storage</span></span>|<span data-ttu-id="af9dd-139">Upload提交表单或自动示例提交提交到 Microsoft 的文件的提交位置</span><span class="sxs-lookup"><span data-stu-id="af9dd-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="af9dd-140">CRL (证书吊销) </span><span class="sxs-lookup"><span data-stu-id="af9dd-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="af9dd-141">供Windows创建与 MAPS 的 SSL 连接以更新 CRL 时使用</span><span class="sxs-lookup"><span data-stu-id="af9dd-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="af9dd-142">符号存储</span><span class="sxs-lookup"><span data-stu-id="af9dd-142">Symbol Store</span></span>|<span data-ttu-id="af9dd-143">由 Microsoft Defender 防病毒在修正流期间还原某些关键文件</span><span class="sxs-lookup"><span data-stu-id="af9dd-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="af9dd-144">通用遥测客户端</span><span class="sxs-lookup"><span data-stu-id="af9dd-144">Universal Telemetry Client</span></span>| <span data-ttu-id="af9dd-145">Used by Windows to send client diagnostic data;Microsoft Defender 防病毒遥测来监视产品质量</span><span class="sxs-lookup"><span data-stu-id="af9dd-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="af9dd-146">此更新使用 SSL (TCP 端口 443) 下载清单，将诊断数据上载到使用下列 DNS 终结点的 Microsoft：   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="af9dd-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="af9dd-147">验证网络和云之间的连接</span><span class="sxs-lookup"><span data-stu-id="af9dd-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="af9dd-148">允许上面列出的 URL 后，你可以测试你是否连接到 Microsoft Defender 防病毒 云服务并正确报告和接收信息，以确保完全受保护。</span><span class="sxs-lookup"><span data-stu-id="af9dd-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="af9dd-149">**使用 cmdline 工具验证云保护：**</span><span class="sxs-lookup"><span data-stu-id="af9dd-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="af9dd-150">将以下参数与 Microsoft Defender 防病毒 命令行实用程序 () 验证网络能否与 Microsoft Defender 防病毒 `mpcmdrun.exe` 云服务通信：</span><span class="sxs-lookup"><span data-stu-id="af9dd-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="af9dd-151">需要打开命令提示符的管理员级别版本。</span><span class="sxs-lookup"><span data-stu-id="af9dd-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="af9dd-152">右键单击"开始"菜单中的项，单击"以管理员角色运行 **"，** 在权限提示符下单击"是"。</span><span class="sxs-lookup"><span data-stu-id="af9dd-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="af9dd-153">此命令仅适用于版本Windows 10版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="af9dd-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="af9dd-154">有关详细信息，请参阅使用命令行Microsoft Defender 防病毒[管理mpcmdrun.exe管理。](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="af9dd-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="af9dd-155">**尝试从 Microsoft 下载假恶意软件文件：**</span><span class="sxs-lookup"><span data-stu-id="af9dd-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="af9dd-156">你可以下载示例文件，Microsoft Defender 防病毒正确连接到云，将检测并阻止该文件。</span><span class="sxs-lookup"><span data-stu-id="af9dd-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="af9dd-157">通过访问 下载 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 文件。</span><span class="sxs-lookup"><span data-stu-id="af9dd-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="af9dd-158">此文件不是恶意软件的实际部分。</span><span class="sxs-lookup"><span data-stu-id="af9dd-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="af9dd-159">这是一个假文件，旨在测试你是否正确连接到云。</span><span class="sxs-lookup"><span data-stu-id="af9dd-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="af9dd-160">如果连接正确，你将看到一条警告Microsoft Defender 防病毒通知。</span><span class="sxs-lookup"><span data-stu-id="af9dd-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="af9dd-161">如果您使用的是Microsoft Edge，则还会看到一条通知消息：</span><span class="sxs-lookup"><span data-stu-id="af9dd-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge通知用户已发现恶意软件](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="af9dd-163">如果您使用以下方法，则会出现Internet Explorer：</span><span class="sxs-lookup"><span data-stu-id="af9dd-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender 防病毒通知用户已发现恶意软件](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="af9dd-165">你还在应用扫描历史记录部分中的隔离威胁下看到Windows 安全中心检测：</span><span class="sxs-lookup"><span data-stu-id="af9dd-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="af9dd-166">通过Windows 安全中心任务栏中的防护图标或搜索"安全"的"开始"菜单打开"安全 **"菜单。**</span><span class="sxs-lookup"><span data-stu-id="af9dd-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="af9dd-167">选择 **病毒&威胁防护"，** 然后选择"保护 **历史记录"。**</span><span class="sxs-lookup"><span data-stu-id="af9dd-167">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="af9dd-168">在" **隔离的威胁"** 部分下， **选择"查看完整历史记录** "以查看检测到的假恶意软件。</span><span class="sxs-lookup"><span data-stu-id="af9dd-168">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="af9dd-169">版本 1703 Windows 10版本版本具有不同的用户界面。</span><span class="sxs-lookup"><span data-stu-id="af9dd-169">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="af9dd-170">请参阅[Microsoft Defender 防病毒应用中Windows 安全中心应用。](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="af9dd-170">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="af9dd-171">事件Windows还会显示客户端Windows Defender ID [1116](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="af9dd-171">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="af9dd-172">相关文章</span><span class="sxs-lookup"><span data-stu-id="af9dd-172">Related articles</span></span>

- [<span data-ttu-id="af9dd-173">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="af9dd-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="af9dd-174">启用云保护</span><span class="sxs-lookup"><span data-stu-id="af9dd-174">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="af9dd-175">命令行参数</span><span class="sxs-lookup"><span data-stu-id="af9dd-175">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="af9dd-176">对 Microsoft Active Protection Services 终结点的重要更改</span><span class="sxs-lookup"><span data-stu-id="af9dd-176">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
