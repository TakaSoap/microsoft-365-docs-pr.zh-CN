---
title: 使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13bcbc74fcb9c540c45a6eec7e7e506b6943986a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841784"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="aad6a-104">使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aad6a-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aad6a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aad6a-105">**Applies to:**</span></span>
- [<span data-ttu-id="aad6a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aad6a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aad6a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aad6a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aad6a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="aad6a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aad6a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="aad6a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="aad6a-110">本文介绍了如何使用 Ansible 在 Linux 上部署适用于终结点的 Defender。</span><span class="sxs-lookup"><span data-stu-id="aad6a-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="aad6a-111">成功的部署需要完成以下所有任务：</span><span class="sxs-lookup"><span data-stu-id="aad6a-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="aad6a-112">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="aad6a-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="aad6a-113">创建易读 YAML 文件</span><span class="sxs-lookup"><span data-stu-id="aad6a-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="aad6a-114">部署</span><span class="sxs-lookup"><span data-stu-id="aad6a-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="aad6a-115">References</span><span class="sxs-lookup"><span data-stu-id="aad6a-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="aad6a-116">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="aad6a-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="aad6a-117">在开始使用之前，请参阅 [Linux](microsoft-defender-endpoint-linux.md) 上的主 Defender for Endpoint 页面，了解当前软件版本的先决条件和系统要求说明。</span><span class="sxs-lookup"><span data-stu-id="aad6a-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="aad6a-118">此外，对于 Ansible 部署，您需要熟悉 Ansible 管理任务，配置了 Ansible，并知道如何部署操作手册和任务。</span><span class="sxs-lookup"><span data-stu-id="aad6a-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="aad6a-119">Ansible 有很多方法可以完成同一任务。</span><span class="sxs-lookup"><span data-stu-id="aad6a-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="aad6a-120">这些说明假定受支持的 Ansible 模块（例如 *，贴* 切和未 *存档* ）的可用性，以帮助部署程序包。</span><span class="sxs-lookup"><span data-stu-id="aad6a-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="aad6a-121">您的组织可能使用不同的工作流。</span><span class="sxs-lookup"><span data-stu-id="aad6a-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="aad6a-122">有关详细信息，请参阅 [Ansible](https://docs.ansible.com/) 文档。</span><span class="sxs-lookup"><span data-stu-id="aad6a-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="aad6a-123">Ansible 需要至少安装在一 (Ansible 调用此控件节点) 。</span><span class="sxs-lookup"><span data-stu-id="aad6a-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="aad6a-124">必须在控制节点和将在其上安装 Defender for Endpoint 的所有托管节点 (设备之间为管理员帐户配置 SSH) ，建议使用公钥身份验证进行配置。</span><span class="sxs-lookup"><span data-stu-id="aad6a-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="aad6a-125">必须在所有托管节点上安装以下软件：</span><span class="sxs-lookup"><span data-stu-id="aad6a-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="aad6a-126">一个</span><span class="sxs-lookup"><span data-stu-id="aad6a-126">curl</span></span>
  - <span data-ttu-id="aad6a-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="aad6a-127">python-apt</span></span>

- <span data-ttu-id="aad6a-128">所有托管节点都必须在 或相关文件中以 `/etc/ansible/hosts` 以下格式列出：</span><span class="sxs-lookup"><span data-stu-id="aad6a-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="aad6a-129">Ping 测试：</span><span class="sxs-lookup"><span data-stu-id="aad6a-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="aad6a-130">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="aad6a-130">Download the onboarding package</span></span>

<span data-ttu-id="aad6a-131">从以下网站下载载入Microsoft Defender 安全中心：</span><span class="sxs-lookup"><span data-stu-id="aad6a-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="aad6a-132">In Microsoft Defender 安全中心， go to **设置 > Device Management > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="aad6a-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="aad6a-133">在"第一个"下拉菜单中，选择 **"Linux Server"** 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="aad6a-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="aad6a-134">In the second drop-down menu， select **Your preferred Linux configuration management tool** as the deployment method.</span><span class="sxs-lookup"><span data-stu-id="aad6a-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="aad6a-135">选择 **下载载入程序包**。</span><span class="sxs-lookup"><span data-stu-id="aad6a-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="aad6a-136">将文件另存为WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="aad6a-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 安全中心屏幕截图](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="aad6a-138">在命令提示符下，验证您是否具有该文件。</span><span class="sxs-lookup"><span data-stu-id="aad6a-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="aad6a-139">提取存档的内容：</span><span class="sxs-lookup"><span data-stu-id="aad6a-139">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="aad6a-140">创建易读 YAML 文件</span><span class="sxs-lookup"><span data-stu-id="aad6a-140">Create Ansible YAML files</span></span>

<span data-ttu-id="aad6a-141">创建参与游戏手册或任务的子任务或角色文件。</span><span class="sxs-lookup"><span data-stu-id="aad6a-141">Create a subtask or role files that contribute to a playbook or task.</span></span>

- <span data-ttu-id="aad6a-142">创建载入任务 `onboarding_setup.yml` ：</span><span class="sxs-lookup"><span data-stu-id="aad6a-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- <span data-ttu-id="aad6a-143">添加适用于终结点的 Defender 存储库和密钥 `add_apt_repo.yml` ：</span><span class="sxs-lookup"><span data-stu-id="aad6a-143">Add the Defender for Endpoint repository and key, `add_apt_repo.yml`:</span></span>

    <span data-ttu-id="aad6a-144">Linux 上的 Defender for Endpoint 可以从以下频道之一进行部署 (下面表示为 *[channel]* *) ：insiders-fast、insiders-slow* 或 *prod*。 每个通道对应于 Linux 软件存储库。</span><span class="sxs-lookup"><span data-stu-id="aad6a-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="aad6a-145">通道的选择决定了提供给你的设备的更新的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="aad6a-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="aad6a-146">预览 *体验成员-快* 中的设备是首先接收更新和新功能的设备，随后是预览体验成员 - *慢* ，最后是 *受支持*。</span><span class="sxs-lookup"><span data-stu-id="aad6a-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="aad6a-147">为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用预览体验成员 *-快* 或预览体验成员-*慢。*</span><span class="sxs-lookup"><span data-stu-id="aad6a-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="aad6a-148">在初始安装后切换通道需要重新安装产品。</span><span class="sxs-lookup"><span data-stu-id="aad6a-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="aad6a-149">若要切换产品渠道：卸载现有程序包，将设备重新配置为使用新通道，然后按照本文档中的步骤从新位置安装程序包。</span><span class="sxs-lookup"><span data-stu-id="aad6a-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="aad6a-150">记下分发和版本，并确定 其最接近的 `https://packages.microsoft.com/config/` 条目。</span><span class="sxs-lookup"><span data-stu-id="aad6a-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="aad6a-151">在下列命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息。</span><span class="sxs-lookup"><span data-stu-id="aad6a-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aad6a-152">对于 Oracle Linux，将 *[distro]* 替换为"rhel"。</span><span class="sxs-lookup"><span data-stu-id="aad6a-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel]
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- <span data-ttu-id="aad6a-153">创建 Ansible 安装和卸载 YAML 文件。</span><span class="sxs-lookup"><span data-stu-id="aad6a-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="aad6a-154">对于基于位置的分发，请使用以下 YAML 文件：</span><span class="sxs-lookup"><span data-stu-id="aad6a-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="aad6a-155">对于基于 dnf 的分发，请使用以下 YAML 文件：</span><span class="sxs-lookup"><span data-stu-id="aad6a-155">For dnf-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="aad6a-156">部署</span><span class="sxs-lookup"><span data-stu-id="aad6a-156">Deployment</span></span>

<span data-ttu-id="aad6a-157">现在，在 目录或 `/etc/ansible/playbooks/` 相关目录下运行任务文件。</span><span class="sxs-lookup"><span data-stu-id="aad6a-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="aad6a-158">安装：</span><span class="sxs-lookup"><span data-stu-id="aad6a-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="aad6a-159">当产品首次启动时，它将下载最新的反恶意软件定义。</span><span class="sxs-lookup"><span data-stu-id="aad6a-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="aad6a-160">根据您的 Internet 连接，这最多可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="aad6a-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="aad6a-161">验证/配置：</span><span class="sxs-lookup"><span data-stu-id="aad6a-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="aad6a-162">卸载：</span><span class="sxs-lookup"><span data-stu-id="aad6a-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="aad6a-163">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="aad6a-163">Log installation issues</span></span>

<span data-ttu-id="aad6a-164">请参阅 [日志](linux-resources.md#log-installation-issues) 安装问题，详细了解如何在发生错误时查找安装程序创建的自动生成的日志。</span><span class="sxs-lookup"><span data-stu-id="aad6a-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="aad6a-165">操作系统升级</span><span class="sxs-lookup"><span data-stu-id="aad6a-165">Operating system upgrades</span></span>

<span data-ttu-id="aad6a-166">将操作系统升级到新的主要版本时，必须先卸载 Linux 上的 Defender for Endpoint，安装升级，最后在设备上重新配置 Linux 上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="aad6a-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="aad6a-167">参考</span><span class="sxs-lookup"><span data-stu-id="aad6a-167">References</span></span>

- [<span data-ttu-id="aad6a-168">添加或删除 YUM 存储库</span><span class="sxs-lookup"><span data-stu-id="aad6a-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="aad6a-169">使用 dnf 程序包管理器管理程序包</span><span class="sxs-lookup"><span data-stu-id="aad6a-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="aad6a-170">添加和删除 APT 存储库</span><span class="sxs-lookup"><span data-stu-id="aad6a-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="aad6a-171">管理 apt-packages</span><span class="sxs-lookup"><span data-stu-id="aad6a-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a><span data-ttu-id="aad6a-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aad6a-172">See also</span></span>
- [<span data-ttu-id="aad6a-173">调查代理运行状况问题</span><span class="sxs-lookup"><span data-stu-id="aad6a-173">Investigate agent health issues</span></span>](health-status.md)
