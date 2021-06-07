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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca5737a0224825a0c88159c4a3931cc0c310b69b
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788447"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="46f6d-104">配置和验证 Microsoft Defender 防病毒软件网络连接</span><span class="sxs-lookup"><span data-stu-id="46f6d-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="46f6d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="46f6d-105">**Applies to:**</span></span>

- [<span data-ttu-id="46f6d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46f6d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="46f6d-107">为了确保Microsoft Defender 防病毒保护正常工作，安全团队必须将网络配置为允许终结点和某些 Microsoft 服务器连接。</span><span class="sxs-lookup"><span data-stu-id="46f6d-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, your security team must configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="46f6d-108">本文列出必须允许的连接（如使用防火墙规则）并提供验证连接的说明。</span><span class="sxs-lookup"><span data-stu-id="46f6d-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="46f6d-109">正确配置保护有助于确保从云提供的保护服务获得最佳价值。</span><span class="sxs-lookup"><span data-stu-id="46f6d-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="46f6d-110">有关网络连接的一些详细信息，请参阅博客文章 [对 Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 终结点的重要更改。</span><span class="sxs-lookup"><span data-stu-id="46f6d-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="46f6d-111">请访问 Microsoft Defender for Endpoint 演示 [网站，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 确认以下功能是否正常工作：</span><span class="sxs-lookup"><span data-stu-id="46f6d-111">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="46f6d-112">云端保护</span><span class="sxs-lookup"><span data-stu-id="46f6d-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="46f6d-113">快速学习 (包括首次看到时阻止) </span><span class="sxs-lookup"><span data-stu-id="46f6d-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="46f6d-114">可能不需要的应用程序阻止</span><span class="sxs-lookup"><span data-stu-id="46f6d-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="46f6d-115">允许连接到 Microsoft Defender 防病毒 云服务</span><span class="sxs-lookup"><span data-stu-id="46f6d-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="46f6d-116">云Microsoft Defender 防病毒为终结点提供快速、强大的保护。</span><span class="sxs-lookup"><span data-stu-id="46f6d-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="46f6d-117">启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。</span><span class="sxs-lookup"><span data-stu-id="46f6d-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span> <span data-ttu-id="46f6d-118">请参阅[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)，了解有关使用 Intune、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或在 Windows 安全中心 应用中各个客户端上启用服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="46f6d-118">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="46f6d-119">启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的连接。</span><span class="sxs-lookup"><span data-stu-id="46f6d-119">After you've enabled the service, you might need to configure your network or firewall to allow connections between it and your endpoints.</span></span> <span data-ttu-id="46f6d-120">由于你的保护是一项云服务，计算机必须能够访问 Internet 并访问 Microsoft Defender，Office 365机器学习服务。</span><span class="sxs-lookup"><span data-stu-id="46f6d-120">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="46f6d-121">请勿将 URL `*.blob.core.windows.net` 从任何类型的网络检查中排除。</span><span class="sxs-lookup"><span data-stu-id="46f6d-121">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

> [!NOTE]
> <span data-ttu-id="46f6d-122">Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。</span><span class="sxs-lookup"><span data-stu-id="46f6d-122">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="46f6d-123">尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护，而是使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。</span><span class="sxs-lookup"><span data-stu-id="46f6d-123">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

## <a name="services-and-urls"></a><span data-ttu-id="46f6d-124">服务和 URL</span><span class="sxs-lookup"><span data-stu-id="46f6d-124">Services and URLs</span></span>

<span data-ttu-id="46f6d-125">本节中的表列出了服务及其关联的网站地址 (URL) 。</span><span class="sxs-lookup"><span data-stu-id="46f6d-125">The table in this section lists the services and their associated website addresses (URLs).</span></span> 

<span data-ttu-id="46f6d-126">确保没有防火墙或网络筛选规则拒绝访问这些 URL。</span><span class="sxs-lookup"><span data-stu-id="46f6d-126">Make sure that there are no firewall or network filtering rules denying access to these URLs.</span></span> <span data-ttu-id="46f6d-127">否则，可能需要专门为他们创建允许规则， (URL `*.blob.core.windows.net`) 。</span><span class="sxs-lookup"><span data-stu-id="46f6d-127">Otherwise, you might need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="46f6d-128">下表中的 URL 使用端口 443 进行通信。</span><span class="sxs-lookup"><span data-stu-id="46f6d-128">The URLs in the following table use port 443 for communication.</span></span>

| <span data-ttu-id="46f6d-129">服务和说明</span><span class="sxs-lookup"><span data-stu-id="46f6d-129">Service and description</span></span> | <span data-ttu-id="46f6d-130">URL</span><span class="sxs-lookup"><span data-stu-id="46f6d-130">URL</span></span> |
|----|---- |
| <span data-ttu-id="46f6d-131">Microsoft Defender 防病毒云提供的保护服务，也称为MICROSOFT ACTIVE PROTECTION SERVICE (MAPS) </span><span class="sxs-lookup"><span data-stu-id="46f6d-131">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span><p><span data-ttu-id="46f6d-132">此服务由云Microsoft Defender 防病毒提供云保护</span><span class="sxs-lookup"><span data-stu-id="46f6d-132">This service is used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| <span data-ttu-id="46f6d-133">MICROSOFT Update Service (MU) and Windows Update Service (WU) </span><span class="sxs-lookup"><span data-stu-id="46f6d-133">Microsoft Update Service (MU) and Windows Update Service (WU)</span></span> <p><span data-ttu-id="46f6d-134">这些服务允许安全智能和产品更新</span><span class="sxs-lookup"><span data-stu-id="46f6d-134">These services allow for security intelligence and product updates</span></span>   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> <span data-ttu-id="46f6d-135">有关详细信息，请参阅[Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="46f6d-135">For more details, see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="46f6d-136">安全智能更新 ADL (备用) </span><span class="sxs-lookup"><span data-stu-id="46f6d-136">Security intelligence updates Alternate Download Location (ADL)</span></span><p><span data-ttu-id="46f6d-137">如果安装的安全智能在 Microsoft Defender 防病毒 7 天或 7 (过期，则这是安全智能更新的) </span><span class="sxs-lookup"><span data-stu-id="46f6d-137">This is an alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="46f6d-138">恶意软件提交存储</span><span class="sxs-lookup"><span data-stu-id="46f6d-138">Malware submission storage</span></span> <p><span data-ttu-id="46f6d-139">这是通过提交表单或自动示例提交提交到 Microsoft 的文件的上传位置</span><span class="sxs-lookup"><span data-stu-id="46f6d-139">This is the upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span> | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="46f6d-140">CRL (证书吊销) </span><span class="sxs-lookup"><span data-stu-id="46f6d-140">Certificate Revocation List (CRL)</span></span> <p><span data-ttu-id="46f6d-141">在创建与 MAPS 的 SSL Windows更新 CRL 时，系统使用此列表</span><span class="sxs-lookup"><span data-stu-id="46f6d-141">This list is used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="46f6d-142">符号存储</span><span class="sxs-lookup"><span data-stu-id="46f6d-142">Symbol Store</span></span> <p><span data-ttu-id="46f6d-143">符号存储由 Microsoft Defender 防病毒在修正流期间还原某些关键文件</span><span class="sxs-lookup"><span data-stu-id="46f6d-143">The symbol store is used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>   | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="46f6d-144">通用遥测客户端</span><span class="sxs-lookup"><span data-stu-id="46f6d-144">Universal Telemetry Client</span></span> <p><span data-ttu-id="46f6d-145">此客户端由 Windows用于发送客户端诊断数据</span><span class="sxs-lookup"><span data-stu-id="46f6d-145">This client is used by Windows to send client diagnostic data</span></span><p> <span data-ttu-id="46f6d-146">Microsoft Defender 防病毒遥测来监视产品质量</span><span class="sxs-lookup"><span data-stu-id="46f6d-146">Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>    | <span data-ttu-id="46f6d-147">此更新使用 SSL (TCP 端口 443) 下载清单，将诊断数据上载到使用下列 DNS 终结点的 Microsoft：</span><span class="sxs-lookup"><span data-stu-id="46f6d-147">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:</span></span> <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="46f6d-148">验证网络和云之间的连接</span><span class="sxs-lookup"><span data-stu-id="46f6d-148">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="46f6d-149">允许上面列出的 URL 后，你可以测试你是否连接到 Microsoft Defender 防病毒 云服务并正确报告和接收信息，以确保完全受保护。</span><span class="sxs-lookup"><span data-stu-id="46f6d-149">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a><span data-ttu-id="46f6d-150">使用 cmdline 工具验证云保护</span><span class="sxs-lookup"><span data-stu-id="46f6d-150">Use the cmdline tool to validate cloud-delivered protection</span></span>

<span data-ttu-id="46f6d-151">将以下参数与 Microsoft Defender 防病毒 命令行实用程序 () 验证网络能否与 Microsoft Defender 防病毒 `mpcmdrun.exe` 云服务通信：</span><span class="sxs-lookup"><span data-stu-id="46f6d-151">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="46f6d-152">需要打开命令提示符的管理员级别版本。</span><span class="sxs-lookup"><span data-stu-id="46f6d-152">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="46f6d-153">右键单击"开始"菜单中的项，单击"以管理员角色运行 **"，** 在权限提示符下单击"是"。</span><span class="sxs-lookup"><span data-stu-id="46f6d-153">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="46f6d-154">此命令仅适用于版本Windows 10版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="46f6d-154">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="46f6d-155">有关详细信息，请参阅使用命令行Microsoft Defender 防病毒[管理mpcmdrun.exe管理。](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="46f6d-155">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a><span data-ttu-id="46f6d-156">尝试从 Microsoft 下载假恶意软件文件</span><span class="sxs-lookup"><span data-stu-id="46f6d-156">Attempt to download a fake malware file from Microsoft</span></span>

<span data-ttu-id="46f6d-157">你可以下载示例文件，Microsoft Defender 防病毒正确连接到云，将检测并阻止该文件。</span><span class="sxs-lookup"><span data-stu-id="46f6d-157">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="46f6d-158">通过访问 下载 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 文件。</span><span class="sxs-lookup"><span data-stu-id="46f6d-158">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="46f6d-159">此文件不是恶意软件的实际部分。</span><span class="sxs-lookup"><span data-stu-id="46f6d-159">This file is not an actual piece of malware.</span></span> <span data-ttu-id="46f6d-160">这是一个假文件，旨在测试你是否正确连接到云。</span><span class="sxs-lookup"><span data-stu-id="46f6d-160">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="46f6d-161">如果连接正确，你将看到一条警告Microsoft Defender 防病毒通知。</span><span class="sxs-lookup"><span data-stu-id="46f6d-161">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="46f6d-162">如果您使用的是Microsoft Edge，则还会看到一条通知消息：</span><span class="sxs-lookup"><span data-stu-id="46f6d-162">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge通知用户已发现恶意软件](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="46f6d-164">如果您使用以下方法，则会出现Internet Explorer：</span><span class="sxs-lookup"><span data-stu-id="46f6d-164">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender 防病毒通知用户已发现恶意软件](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="46f6d-166">你还在应用扫描历史记录部分中的隔离威胁下看到Windows 安全中心检测：</span><span class="sxs-lookup"><span data-stu-id="46f6d-166">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="46f6d-167">通过Windows 安全中心任务栏中的防护图标或搜索"安全"的"开始"菜单打开"安全 **"菜单。**</span><span class="sxs-lookup"><span data-stu-id="46f6d-167">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="46f6d-168">选择 **病毒&威胁防护"，** 然后选择"保护 **历史记录"。**</span><span class="sxs-lookup"><span data-stu-id="46f6d-168">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="46f6d-169">在" **隔离的威胁"** 部分下， **选择"查看完整历史记录** "以查看检测到的假恶意软件。</span><span class="sxs-lookup"><span data-stu-id="46f6d-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46f6d-170">版本 1703 Windows 10版本版本具有不同的用户界面。</span><span class="sxs-lookup"><span data-stu-id="46f6d-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="46f6d-171">请参阅[Microsoft Defender 防病毒应用中Windows 安全中心应用。](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="46f6d-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="46f6d-172">事件Windows还会显示客户端Windows Defender ID [1116](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="46f6d-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

