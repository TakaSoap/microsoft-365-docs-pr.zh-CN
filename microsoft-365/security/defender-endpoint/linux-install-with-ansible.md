---
title: 使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos， fedora， amazon linux 2
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 796095323cfbe24a49ed4da712ceef55e8a5d941
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588181"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>使用 Ansible 在 Linux 上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

本文介绍了如何使用 Ansible 在 Linux 上部署适用于终结点的 Defender。 要成功部署，需要完成以下所有任务：

- [下载载入程序包](#download-the-onboarding-package)
- [创建易读 YAML 文件](#create-ansible-yaml-files)
- [部署](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>先决条件和系统要求

在开始使用之前，请参阅 [Linux](microsoft-defender-endpoint-linux.md) 上的主 Defender for Endpoint 页面，了解当前软件版本的先决条件和系统要求说明。

此外，对于 Ansible 部署，您需要熟悉 Ansible 管理任务，配置了 Ansible，并知道如何部署手册和任务。 Ansible 有很多方法可以完成同一任务。 这些说明假定受支持的 Ansible 模块（例如 *，贴* 切和未 *存档* ）的可用性，以帮助部署程序包。 您的组织可能使用不同的工作流。 有关详细信息，请参阅 [Ansible](https://docs.ansible.com/) 文档。

- ansible 需要安装在至少一台计算机 (Ansible 调用此控件节点) 。
- 必须在控制节点和将在其上安装 Defender for Endpoint 的所有托管节点 (设备之间为管理员帐户配置 SSH) ，建议使用公钥身份验证进行配置。
- 必须在所有托管节点上安装以下软件：
  - 一个
  - python-apt

- 所有托管节点都必须在 或相关文件中以 `/etc/ansible/hosts` 以下格式列出：

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Ping 测试：

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>下载载入程序包

从应用门户下载Microsoft 365 Defender包：

1. In Microsoft 365 Defender portal， go to **设置 > Endpoints > Device management > Onboarding**.
2. 在"第一个"下拉菜单中，选择 **"Linux Server"** 作为操作系统。 In the second drop-down menu， select **Your preferred Linux configuration management tool** as the deployment method.
3. 选择 **下载载入程序包**。 将文件另存为WindowsDefenderATPOnboardingPackage.zip。

    ![Microsoft 365 Defender门户屏幕截图。](images/portal-onboarding-linux-2.png)

4. 在命令提示符下，验证您是否具有该文件。 提取存档的内容：

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

## <a name="create-ansible-yaml-files"></a>创建易读 YAML 文件

创建参与游戏手册或任务的子任务或角色文件。

- 创建载入任务 `onboarding_setup.yml` ：

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

- 添加适用于终结点的 Defender 存储库和密钥 `add_apt_repo.yml` ：

    Linux 上的 Defender for Endpoint 可以从以下频道之一进行部署 (下面表示为 *[channel]* *) ：insiders-fast、insiders-slow* 或 *prod*。 每个通道对应于 Linux 软件存储库。

    通道的选择决定了提供给你的设备的更新的类型和频率。 预览 *体验成员 -快* 中的设备是首先接收更新和新功能的设备，随后是预览体验成员- 慢，最后是 *受支持*。

    为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用预览体验成员 *-快* 或预览体验成员-慢 *。*

    > [!WARNING]
    > 在初始安装后切换通道需要重新安装产品。 若要切换产品渠道：卸载现有程序包，将设备重新配置为使用新通道，然后按照本文档中的步骤从新位置安装程序包。

    记下分发和版本，并确定 其最接近的 `https://packages.microsoft.com/config/[distro]/` 条目。

    在下列命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息。

    > [!NOTE]
    > 对于 Oracle Linux 和 Amazon Linux 2，将 *[distro]* 替换为"rhel"。

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/config/[distro]/[version]/prod [channel] main
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
      name: packages-microsoft-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/ 
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- 创建 Ansible 安装和卸载 YAML 文件。

    - 对于基于位置的分发，请使用以下 YAML 文件：

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

    - 对于基于 dnf 的分发，请使用以下 YAML 文件：

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

## <a name="deployment"></a>部署

现在，在 目录或 `/etc/ansible/playbooks/` 相关目录下运行任务文件。

- 安装：

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> 当产品首次启动时，它将下载最新的反恶意软件定义。 根据您的 Internet 连接，这最多可能需要几分钟。

- 验证/配置：

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- 卸载：

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>记录安装问题

请参阅 [日志](linux-resources.md#log-installation-issues) 安装问题，详细了解如何在发生错误时查找安装程序创建的自动生成的日志。

## <a name="operating-system-upgrades"></a>操作系统升级

将操作系统升级到新的主要版本时，必须先卸载 Linux 上的 Defender for Endpoint，安装升级，最后在设备上重新配置 Linux 上的 Defender for Endpoint。

## <a name="references"></a>参考

- [添加或删除 YUM 存储库](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [使用 dnf 程序包管理器管理程序包](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [添加和删除 APT 存储库](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [管理 apt-packages](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>另请参阅
- [调查代理运行状况问题](health-status.md)
