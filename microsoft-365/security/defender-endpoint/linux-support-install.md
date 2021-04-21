---
title: 解决 Linux 上的 Microsoft Defender for Endpoint 的安装问题
ms.reviewer: ''
description: 解决 Linux 上的 Microsoft Defender for Endpoint 的安装问题
keywords: microsoft， defender， atp， linux， 安装
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 270ad1145308aaa2af703cda84307a4a96097a53
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903126"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b62ba-104">解决 Linux 上的 Microsoft Defender for Endpoint 的安装问题</span><span class="sxs-lookup"><span data-stu-id="b62ba-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b62ba-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b62ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="b62ba-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b62ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b62ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b62ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b62ba-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b62ba-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b62ba-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b62ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="b62ba-110">验证安装是否成功</span><span class="sxs-lookup"><span data-stu-id="b62ba-110">Verify if installation succeeded</span></span>

<span data-ttu-id="b62ba-111">安装错误可能导致包管理器产生有意义的错误消息，也可能没有意义。</span><span class="sxs-lookup"><span data-stu-id="b62ba-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="b62ba-112">若要验证安装是否成功，请运行以下方法获取并检查安装日志：</span><span class="sxs-lookup"><span data-stu-id="b62ba-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

<span data-ttu-id="b62ba-113">来自具有正确安装日期和时间的上一个命令的输出指示成功。</span><span class="sxs-lookup"><span data-stu-id="b62ba-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="b62ba-114">此外， [检查客户端配置](linux-install-manually.md#client-configuration) 以验证产品的运行状况并检测 EICAR 文本文件。</span><span class="sxs-lookup"><span data-stu-id="b62ba-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="b62ba-115">确保你拥有正确的程序包</span><span class="sxs-lookup"><span data-stu-id="b62ba-115">Make sure you have the correct package</span></span>

<span data-ttu-id="b62ba-116">请注意，要安装的程序包与主机分发和版本匹配。</span><span class="sxs-lookup"><span data-stu-id="b62ba-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="b62ba-117">package</span><span class="sxs-lookup"><span data-stu-id="b62ba-117">package</span></span>                       | <span data-ttu-id="b62ba-118">distribution</span><span class="sxs-lookup"><span data-stu-id="b62ba-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="b62ba-119">mdatp-rhel8。Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="b62ba-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="b62ba-120">Oracle、RHEL 和 CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="b62ba-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="b62ba-121">mdatp-sles12。Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="b62ba-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="b62ba-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="b62ba-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="b62ba-123">mdatp-sles15。Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="b62ba-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="b62ba-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="b62ba-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="b62ba-125">mdatp.Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="b62ba-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="b62ba-126">Oracle、RHEL 和 CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="b62ba-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="b62ba-127">mdatp.Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="b62ba-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="b62ba-128">Debian 和 Ubuntu 16.04、18.04 和 20.04</span><span class="sxs-lookup"><span data-stu-id="b62ba-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="b62ba-129">对于 [手动部署](linux-install-manually.md)，请确保已选择正确的 distro 和版本。</span><span class="sxs-lookup"><span data-stu-id="b62ba-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="b62ba-130">安装失败</span><span class="sxs-lookup"><span data-stu-id="b62ba-130">Installation failed</span></span>

<span data-ttu-id="b62ba-131">检查 mdatp 服务是否正在运行：</span><span class="sxs-lookup"><span data-stu-id="b62ba-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="b62ba-132">mdatp 服务未运行时疑难解答的步骤</span><span class="sxs-lookup"><span data-stu-id="b62ba-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="b62ba-133">检查是否存在"mdatp"用户：</span><span class="sxs-lookup"><span data-stu-id="b62ba-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="b62ba-134">如果没有输出，请运行</span><span class="sxs-lookup"><span data-stu-id="b62ba-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="b62ba-135">尝试使用以下方法启用和重新启动服务：</span><span class="sxs-lookup"><span data-stu-id="b62ba-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="b62ba-136">如果在运行上一个命令时找不到 mdatp.service，请运行：</span><span class="sxs-lookup"><span data-stu-id="b62ba-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="b62ba-137">其中 ```<systemd_path>``` 用于 ```/lib/systemd/system``` Ubuntu 和 Debian 分发， ```/usr/lib/systemd/system``` 适用于 Rhel、CentOS、Oracle 和 SLES。</span><span class="sxs-lookup"><span data-stu-id="b62ba-137">where ```<systemd_path>``` is ```/lib/systemd/system``` for Ubuntu and Debian distributions and ```/usr/lib/systemd/system``` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="b62ba-138">然后重新运行步骤 2。</span><span class="sxs-lookup"><span data-stu-id="b62ba-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="b62ba-139">如果上述步骤不起作用，请检查是否安装了 SE 提供了实施模式。</span><span class="sxs-lookup"><span data-stu-id="b62ba-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="b62ba-140">如果是，请尝试将此设置设置为 (模式) 禁用模式。</span><span class="sxs-lookup"><span data-stu-id="b62ba-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="b62ba-141">可以通过在文件中将 参数设置为"许可"或"禁用"，然后 `SELINUX` `/etc/selinux/config` 重新启动来完成。</span><span class="sxs-lookup"><span data-stu-id="b62ba-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="b62ba-142">有关更多详细信息，请查看 se分页的"人名"页面。</span><span class="sxs-lookup"><span data-stu-id="b62ba-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="b62ba-143">现在，请尝试使用步骤 2 重新启动 mdatp 服务。</span><span class="sxs-lookup"><span data-stu-id="b62ba-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="b62ba-144">在尝试配置更改并重新启动后，出于安全考虑，立即还原配置更改。</span><span class="sxs-lookup"><span data-stu-id="b62ba-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="b62ba-145">如果 `/opt` 目录是符号链接，请为 创建绑定装载 `/opt/microsoft` 。</span><span class="sxs-lookup"><span data-stu-id="b62ba-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="b62ba-146">确保守护程序具有可执行权限。</span><span class="sxs-lookup"><span data-stu-id="b62ba-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="b62ba-147">如果守护程序没有可执行权限，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b62ba-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="b62ba-148">并重试运行步骤 2。</span><span class="sxs-lookup"><span data-stu-id="b62ba-148">and retry running step 2.</span></span>

7. <span data-ttu-id="b62ba-149">确保包含 wdavdaemon 的文件系统未装入"noexec"。</span><span class="sxs-lookup"><span data-stu-id="b62ba-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="b62ba-150">如果 mdatp 服务正在运行，但 EICAR 文本文件检测不起作用</span><span class="sxs-lookup"><span data-stu-id="b62ba-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="b62ba-151">使用以下方法检查文件系统类型：</span><span class="sxs-lookup"><span data-stu-id="b62ba-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="b62ba-152">当前支持的访问活动的文件系统在此处 [列出](microsoft-defender-endpoint-linux.md#system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="b62ba-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="b62ba-153">将不会扫描这些文件系统之外的任何文件。</span><span class="sxs-lookup"><span data-stu-id="b62ba-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="b62ba-154">命令行工具"mdatp"无法工作</span><span class="sxs-lookup"><span data-stu-id="b62ba-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="b62ba-155">如果运行命令行工具出错 `mdatp` ， `command not found` 请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b62ba-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="b62ba-156">然后重试。</span><span class="sxs-lookup"><span data-stu-id="b62ba-156">and try again.</span></span>

    <span data-ttu-id="b62ba-157">如果上述步骤均无帮助，请收集诊断日志：</span><span class="sxs-lookup"><span data-stu-id="b62ba-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="b62ba-158">包含日志的 zip 文件的路径将显示为输出。</span><span class="sxs-lookup"><span data-stu-id="b62ba-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="b62ba-159">使用这些日志联系我们的客户支持人员。</span><span class="sxs-lookup"><span data-stu-id="b62ba-159">Reach out to our customer support with these logs.</span></span>
