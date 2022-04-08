---
title: Linux 版 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Linux 上安装和使用Pertahanan Microsoft untuk Titik Akhir。
keywords: microsoft， defender， Pertahanan Microsoft untuk Titik Akhir， linux， 安装， 部署， 卸载， 木偶， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f04933d54bf02732fea34df25b25e3996e23932
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705071"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 版 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本主题介绍如何在 Linux 上安装、配置、更新和使用Pertahanan Microsoft untuk Titik Akhir。

> [!CAUTION]
> 在 Linux 上运行其他第三方终结点保护产品和Pertahanan Microsoft untuk Titik Akhir可能会导致性能问题和不可预知的副作用。 如果非 Microsoft 终结点保护是环境中的绝对要求，则在将防病毒功能配置为在[被动模式](linux-preferences.md#enforcement-level-for-antivirus-engine)下运行后，仍可以安全地利用 Linux 上的 Defender for Endpoint EDR功能。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>如何在 Linux 上安装Pertahanan Microsoft untuk Titik Akhir

适用于 Linux 的Pertahanan Microsoft untuk Titik Akhir包括反恶意软件和终结点检测和响应 (EDR) 功能。 


### <a name="prerequisites"></a>先决条件

- 访问Microsoft 365 Defender门户
- 使用 [系统系统管理器](https://systemd.io/) 的 Linux 分发

  >[!NOTE]
  >使用系统管理器进行 Linux 分发，除了 RHEL/CentOS 6.x 支持 SystemV 和 Upstart。

- Linux 和 BASH 脚本中的初学者级体验
- 如果手动部署) ，设备上的管理权限 (

> [!NOTE]
> Linux 代理上的Pertahanan Microsoft untuk Titik Akhir独立于 [OMS 代理](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)。 Pertahanan Microsoft untuk Titik Akhir依赖于其自身的独立遥测管道。


### <a name="installation-instructions"></a>安装说明

有几种方法和部署工具可用于在 Linux 上安装和配置Pertahanan Microsoft untuk Titik Akhir。

一般情况下，需要执行以下步骤：

- 确保拥有Pertahanan Microsoft untuk Titik Akhir订阅。
- 使用以下部署方法之一在 Linux 上部署Pertahanan Microsoft untuk Titik Akhir：
  - 命令行工具：
    - [手动部署](linux-install-manually.md)
  - 第三方管理工具：
    - [使用 Puppet 配置管理工具进行部署](linux-install-with-puppet.md)
    - [使用 Ansible 配置管理工具进行部署](linux-install-with-ansible.md)
    - [使用 Chef 配置管理工具进行部署](linux-deploy-defender-for-endpoint-with-chef.md)

如果遇到任何安装故障，请参阅 [Linux 上的 Pertahanan Microsoft untuk Titik Akhir 中的安装故障排除](linux-support-install.md)。

> [!NOTE]
> 不支持在默认安装路径以外的任何其他位置安装Pertahanan Microsoft untuk Titik Akhir。 

### <a name="system-requirements"></a>系统要求

- 支持的 Linux 服务器分发和 x64 (AMD64/EM64T) 和x86_64版本：

  - Red Hat Enterprise Linux 6.7 或更高版本
  - Red Hat Enterprise Linux 7.2 或更高版本
  - Red Hat Enterprise Linux 8.x
  - CentOS 6.7 或更高版本 
  - CentOS 7.2 或更高版本
  - Ubuntu 16.04 LTS 或更高版本 LTS
  - Debian 9 或更高版本
  - SUSE Linux Enterprise服务器 12 或更高版本
  - Oracle Linux 7.2 或更高版本
  - Oracle Linux 8.x
  - Amazon Linux 2
  - Fedora 33 或更高版本

    > [!NOTE]
    > 未显式列出的发行版和版本不受支持 (即使它们派生自官方支持的发行版) 。

- 支持的内核版本列表
  - 最低内核版本 3.10.0-327 (对于上述所有受支持的 Linux 发行版，除了 Red Hat Enterprise Linux 6 和 CentOS 6) 
  - `fanotify`必须启用内核选项
  - Red Hat Enterprise Linux 6 和 CentOS 6：
    - 对于 6.7：2.6.32-573.*
    - 对于 6.8：2.6.32-642.*
    - 对于 6.9：2.6.32-696.* (，2.6.32-696.el6.x86_64) 
    - 对于 6.10：2.6.32.754.2.1.el6.x86_64到 2.6.32-754.43.1：
    
       - 2.6.32-754.10.1.el6.x86_64
       - 2.6.32-754.11.1.el6.x86_64
       - 2.6.32-754.12.1.el6.x86_64
       - 2.6.32-754.14.2.el6.x86_64
       - 2.6.32-754.15.3.el6.x86_64
       - 2.6.32-754.17.1.el6.x86_64
       - 2.6.32-754.18.2.el6.x86_64
       - 2.6.32-754.2.1.el6.x86_64
       - 2.6.32-754.22.1.el6.x86_64
       - 2.6.32-754.23.1.el6.x86_64
       - 2.6.32-754.24.2.el6.x86_64
       - 2.6.32-754.24.3.el6.x86_64
       - 2.6.32-754.25.1.el6.x86_64
       - 2.6.32-754.27.1.el6.x86_64
       - 2.6.32-754.28.1.el6.x86_64
       - 2.6.32-754.29.1.el6.x86_64
       - 2.6.32-754.29.2.el6.x86_64
       - 2.6.32-754.3.5.el6.x86_64
       - 2.6.32-754.30.2.el6.x86_64
       - 2.6.32-754.33.1.el6.x86_64
       - 2.6.32-754.35.1.el6.x86_64
       - 2.6.32-754.39.1.el6.x86_64
       - 2.6.32-754.41.2.el6.x86_64
       - 2.6.32-754.43.1.el6.x86_64
       - 2.6.32-754.6.3.el6.x86_64
       - 2.6.32-754.9.1.el6.x86_64

 > [!NOTE]
 > 发布新包版本后，对前两个版本的支持将减少到仅技术支持。 本部分中列出的版本早于该版本仅提供技术升级支持。


  > [!CAUTION]
  > 不支持在 Linux 上与其他 `fanotify`基于安全解决方案并行运行 Defender for Endpoint。 这可能会导致不可预知的结果，包括挂起操作系统。

- 磁盘空间：1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon 需要可执行权限。 有关详细信息，请参阅"确保守护程序具有可执行权限"，[以排查 Linux 上Pertahanan Microsoft untuk Titik Akhir的安装问题](/microsoft-365/security/defender-endpoint/linux-support-install)。

- 核心：2 个最小值，4 个首选

- 内存：1 GB 最小值，4 个首选

    > [!NOTE]
    > 请确保在 /var 中具有可用磁盘空间。

- 该解决方案目前为以下文件系统类型提供实时保护：

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

启用服务后，可能需要将网络或防火墙配置为允许其与终结点之间的出站连接。

- 必须启用审核框架 (`auditd`) 。

  > [!NOTE]
  > 添加到 `/etc/audit/rules.d/` 的规则捕获的系统事件将添加到 `audit.log` () ，并可能影响主机审核和上游收集。 Linux 上Pertahanan Microsoft untuk Titik Akhir添加的事件将用`mdatp`键进行标记。

### <a name="configuring-exclusions"></a>配置排除项

将排除项添加到Microsoft Defender 防病毒时，应注意[Microsoft Defender 防病毒的常见排除错误](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)

### <a name="network-connections"></a>网络连接

以下可下载电子表格列出了网络必须能够连接到的服务及其关联 URL。 应确保没有防火墙或网络筛选规则会拒绝访问这些 URL。 如果存在，可能需要专门为其创建 *允许* 规则。

<br>

****

|域列表的电子表格| 说明|
|---|---|
|商业客户Pertahanan Microsoft untuk Titik Akhir URL 列表| 针对商业客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| gov/GCC/DoD 的Pertahanan Microsoft untuk Titik Akhir URL 列表 | 适用于 Gov/GCC/DoD 客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

> [!NOTE]
> 有关更具体的 URL 列表，请参阅 [配置代理和 Internet 连接设置](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

Defender for Endpoint 可以使用以下发现方法发现代理服务器：

- 透明代理
- 手动静态代理配置

如果代理或防火墙阻止匿名流量，请确保允许在以前列出的 URL 中使用匿名流量。 对于透明代理，Defender for Endpoint 无需其他配置。 对于静态代理，请按照 [手动静态代理配置](linux-static-proxy-configuration.md)中的步骤操作。

> [!WARNING]
> 不支持 PAC、WPAD 和经过身份验证的代理。 确保仅使用静态代理或透明代理。
>
> 出于安全原因，也不支持 SSL 检查和拦截代理。 配置 SSL 检查和代理服务器的异常，以直接将数据从 Linux 上的 Defender for Endpoint 传递到相关 URL，而不进行拦截。 将拦截证书添加到全局存储不允许拦截。

有关故障排除步骤，请参阅[排查 Linux 上Pertahanan Microsoft untuk Titik Akhir的云连接问题](linux-support-connectivity.md)。

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>如何更新 Linux 上的Pertahanan Microsoft untuk Titik Akhir

Microsoft 定期发布软件更新，以提高性能、安全性和提供新功能。 若要在 Linux 上更新Pertahanan Microsoft untuk Titik Akhir，请参阅[在 Linux 上为Pertahanan Microsoft untuk Titik Akhir部署更新](linux-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>如何配置 Linux 版 Microsoft Defender for Endpoint

有关如何在企业环境中配置产品的指南，请参阅 [Linux 上Pertahanan Microsoft untuk Titik Akhir设置首选](linux-preferences.md)项。

## <a name="common-applications-to-microsoft-defender-for-endpoint-can-impact"></a>要Pertahanan Microsoft untuk Titik Akhir的常见应用程序可能会影响

安装Pertahanan Microsoft untuk Titik Akhir时，某些应用程序的高 I/O 工作负荷可能会遇到性能问题。 其中包括适用于 Jenkins 和 Jira 等开发人员方案的应用程序，以及 OracleDB 和 Postgres 等数据库工作负载。 如果遇到性能下降的情况，请考虑为受信任的应用程序设置排除项，请记住[Microsoft Defender 防病毒常见排除错误](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)。 有关其他指导，请考虑咨询有关第三方应用程序中防病毒排除的文档。

## <a name="resources"></a>资源

- 有关日志记录、卸载或其他主题的详细信息，请参阅 [资源](linux-resources.md)。
