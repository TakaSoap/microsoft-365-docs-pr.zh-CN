---
title: 配置和验证 Microsoft Defender 防病毒软件网络连接
description: 配置和测试与 Microsoft Defender 防病毒云保护服务的连接。
keywords: 防病毒， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 攻击性， 保护级别
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6218bc32690ca42c06b5606d8a3922f6fc5c7307
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765151"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="6211f-104">配置和验证 Microsoft Defender 防病毒软件网络连接</span><span class="sxs-lookup"><span data-stu-id="6211f-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6211f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6211f-105">**Applies to:**</span></span>

- [<span data-ttu-id="6211f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6211f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6211f-107">若要确保 Microsoft Defender 防病毒云保护正常工作，需要配置网络以允许终结点和某些 Microsoft 服务器之间连接。</span><span class="sxs-lookup"><span data-stu-id="6211f-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span>

<span data-ttu-id="6211f-108">本文列出必须允许的连接（如使用防火墙规则）并提供验证连接的说明。</span><span class="sxs-lookup"><span data-stu-id="6211f-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="6211f-109">正确配置保护有助于确保从云提供的保护服务获得最佳价值。</span><span class="sxs-lookup"><span data-stu-id="6211f-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="6211f-110">有关网络连接的一些详细信息，请参阅博客文章 [对 Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 终结点的重要更改。</span><span class="sxs-lookup"><span data-stu-id="6211f-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

>[!TIP]
><span data-ttu-id="6211f-111">还可以访问 Microsoft Defender for Endpoint 演示[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 确认以下功能是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="6211f-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
>- <span data-ttu-id="6211f-112">云保护</span><span class="sxs-lookup"><span data-stu-id="6211f-112">Cloud-delivered protection</span></span>
>- <span data-ttu-id="6211f-113">快速学习 (包括首次看到时阻止) </span><span class="sxs-lookup"><span data-stu-id="6211f-113">Fast learning (including block at first sight)</span></span>
>- <span data-ttu-id="6211f-114">可能不需要的应用程序阻止</span><span class="sxs-lookup"><span data-stu-id="6211f-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="6211f-115">允许连接到 Microsoft Defender 防病毒云服务</span><span class="sxs-lookup"><span data-stu-id="6211f-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="6211f-116">Microsoft Defender 防病毒云服务为终结点提供快速、强大的保护。</span><span class="sxs-lookup"><span data-stu-id="6211f-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="6211f-117">启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。</span><span class="sxs-lookup"><span data-stu-id="6211f-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

>[!NOTE]
><span data-ttu-id="6211f-118">Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。</span><span class="sxs-lookup"><span data-stu-id="6211f-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="6211f-119">尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护，而是使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。</span><span class="sxs-lookup"><span data-stu-id="6211f-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="6211f-120">有关 [使用](enable-cloud-protection-microsoft-defender-antivirus.md) Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或在 Windows 安全应用个别客户端上启用服务的详细信息，请参阅启用云保护。</span><span class="sxs-lookup"><span data-stu-id="6211f-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="6211f-121">启用该服务后，可能需要配置网络或防火墙以允许其与终结点连接。</span><span class="sxs-lookup"><span data-stu-id="6211f-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="6211f-122">由于保护是云服务，因此计算机必须有权访问 Internet 并访问 Microsoft Defender for Office 365 机器学习服务。</span><span class="sxs-lookup"><span data-stu-id="6211f-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="6211f-123">请勿将 URL `*.blob.core.windows.net` 从任何类型的网络检查中排除。</span><span class="sxs-lookup"><span data-stu-id="6211f-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="6211f-124">下表列出了服务及其关联的 URL。</span><span class="sxs-lookup"><span data-stu-id="6211f-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="6211f-125">请确保没有防火墙或网络筛选规则拒绝访问这些 URL，或者您可能需要专门为它们创建允许规则 (排除 URL `*.blob.core.windows.net`) 。</span><span class="sxs-lookup"><span data-stu-id="6211f-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="6211f-126">下面提及 URL 正在使用端口 443 进行通信。</span><span class="sxs-lookup"><span data-stu-id="6211f-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="6211f-127">**服务**</span><span class="sxs-lookup"><span data-stu-id="6211f-127">**Service**</span></span>| <span data-ttu-id="6211f-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="6211f-128">**Description**</span></span> |<span data-ttu-id="6211f-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="6211f-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="6211f-130">Microsoft Defender 防病毒云保护服务，也称为 Microsoft Active Protection Service (MAPS) </span><span class="sxs-lookup"><span data-stu-id="6211f-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="6211f-131">由 Microsoft Defender 防病毒用于提供云保护</span><span class="sxs-lookup"><span data-stu-id="6211f-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="6211f-132">MICROSOFT Update Service (MU) </span><span class="sxs-lookup"><span data-stu-id="6211f-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="6211f-133">WINDOWS 更新服务 (WU) </span><span class="sxs-lookup"><span data-stu-id="6211f-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="6211f-134">安全智能和产品更新</span><span class="sxs-lookup"><span data-stu-id="6211f-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="6211f-135">有关详细信息， [请参阅 Windows 更新的连接终结点](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="6211f-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="6211f-136">安全智能更新 ADL (备用) </span><span class="sxs-lookup"><span data-stu-id="6211f-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="6211f-137">Microsoft Defender 防病毒安全智能更新的备用位置（如果安装的安全智能在 (7 天或) </span><span class="sxs-lookup"><span data-stu-id="6211f-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="6211f-138">恶意软件提交存储</span><span class="sxs-lookup"><span data-stu-id="6211f-138">Malware submission storage</span></span>|<span data-ttu-id="6211f-139">上传通过提交表单或自动提交示例提交到 Microsoft 的文件的位置</span><span class="sxs-lookup"><span data-stu-id="6211f-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="6211f-140">CRL (证书吊销) </span><span class="sxs-lookup"><span data-stu-id="6211f-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="6211f-141">Windows 在创建与 MAPS 的 SSL 连接以更新 CRL 时使用</span><span class="sxs-lookup"><span data-stu-id="6211f-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="6211f-142">符号存储</span><span class="sxs-lookup"><span data-stu-id="6211f-142">Symbol Store</span></span>|<span data-ttu-id="6211f-143">由 Microsoft Defender 防病毒用于在修正流期间还原某些关键文件</span><span class="sxs-lookup"><span data-stu-id="6211f-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="6211f-144">通用遥测客户端</span><span class="sxs-lookup"><span data-stu-id="6211f-144">Universal Telemetry Client</span></span>| <span data-ttu-id="6211f-145">由 Windows 用来发送客户端诊断数据;Microsoft Defender 防病毒使用遥测进行产品质量监视</span><span class="sxs-lookup"><span data-stu-id="6211f-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="6211f-146">此更新使用 SSL (TCP 端口 443) 下载清单，将诊断数据上载到使用下列 DNS 终结点的 Microsoft：   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="6211f-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="6211f-147">验证网络和云之间的连接</span><span class="sxs-lookup"><span data-stu-id="6211f-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="6211f-148">允许上面列出的 URL 后，可以测试你是否连接到 Microsoft Defender 防病毒云服务，并正确报告和接收信息以确保完全受保护。</span><span class="sxs-lookup"><span data-stu-id="6211f-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="6211f-149">**使用 cmdline 工具验证云保护：**</span><span class="sxs-lookup"><span data-stu-id="6211f-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="6211f-150">将以下参数与 Microsoft Defender 防病毒命令行实用程序 () 验证网络能否与 `mpcmdrun.exe` Microsoft Defender 防病毒云服务通信：</span><span class="sxs-lookup"><span data-stu-id="6211f-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="6211f-151">需要打开命令提示符的管理员级别版本。</span><span class="sxs-lookup"><span data-stu-id="6211f-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="6211f-152">右键单击"开始"菜单中的项，单击"以管理员角色运行 **"，** 在权限提示符下单击"是"。</span><span class="sxs-lookup"><span data-stu-id="6211f-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="6211f-153">此命令仅适用于 Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6211f-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="6211f-154">有关详细信息，请参阅使用命令行工具mpcmdrun.exe [Microsoft Defender 防病毒](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="6211f-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="6211f-155">**尝试从 Microsoft 下载假恶意软件文件：**</span><span class="sxs-lookup"><span data-stu-id="6211f-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="6211f-156">如果正确连接到云，你可以下载 Microsoft Defender 防病毒将检测并阻止的示例文件。</span><span class="sxs-lookup"><span data-stu-id="6211f-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="6211f-157">通过访问 下载 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 文件。</span><span class="sxs-lookup"><span data-stu-id="6211f-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

>[!NOTE]
><span data-ttu-id="6211f-158">此文件不是恶意软件的实际部分。</span><span class="sxs-lookup"><span data-stu-id="6211f-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="6211f-159">这是一个假文件，旨在测试你是否正确连接到云。</span><span class="sxs-lookup"><span data-stu-id="6211f-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="6211f-160">如果连接正确，你将看到一条警告 Microsoft Defender 防病毒通知。</span><span class="sxs-lookup"><span data-stu-id="6211f-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="6211f-161">如果你使用的是 Microsoft Edge，还将看到一条通知消息：</span><span class="sxs-lookup"><span data-stu-id="6211f-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge 通知用户已发现恶意软件](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="6211f-163">如果您使用以下方法，则会出现Internet Explorer：</span><span class="sxs-lookup"><span data-stu-id="6211f-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender 防病毒通知，通知用户已发现恶意软件](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="6211f-165">你还在 Windows 安全应用的扫描历史记录部分中的隔离威胁下看到检测：</span><span class="sxs-lookup"><span data-stu-id="6211f-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="6211f-166">通过单击任务栏中的防护图标或搜索 Defender 的开始菜单打开 Windows 安全 **应用**。</span><span class="sxs-lookup"><span data-stu-id="6211f-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="6211f-167">选择病毒& **威胁** 防护磁贴 (左侧菜单栏上的防护图标) "扫描 **历史记录** "标签：</span><span class="sxs-lookup"><span data-stu-id="6211f-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Windows 安全应用中扫描历史记录标签的屏幕截图](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="6211f-169">在" **隔离的威胁"** 部分下， **选择"查看完整历史记录** "以查看检测到的假恶意软件。</span><span class="sxs-lookup"><span data-stu-id="6211f-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6211f-170">版本 1703 之前版本的 Windows 10 具有不同的用户界面。</span><span class="sxs-lookup"><span data-stu-id="6211f-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="6211f-171">请参阅 [Windows 安全中心应用中的 Microsoft Defender 防病毒](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="6211f-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="6211f-172">Windows 事件日志还将显示客户端 [Windows Defender ID 1116](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="6211f-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="6211f-173">相关文章</span><span class="sxs-lookup"><span data-stu-id="6211f-173">Related articles</span></span>

- [<span data-ttu-id="6211f-174">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="6211f-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="6211f-175">启用云保护</span><span class="sxs-lookup"><span data-stu-id="6211f-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="6211f-176">命令行参数</span><span class="sxs-lookup"><span data-stu-id="6211f-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="6211f-177">对 Microsoft Active Protection Services 终结点的重要更改</span><span class="sxs-lookup"><span data-stu-id="6211f-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)