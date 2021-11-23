---
title: Linux 版 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Linux 上安装和使用 Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 045f3ed99f119ff744d7c8e3cbed8a5cdab88fee
ms.sourcegitcommit: a15ea6bc8f60895e791a08a5a88d346c6581ea38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2021
ms.locfileid: "61145030"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 版 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本主题介绍如何在 Linux 上安装、配置、更新和使用 Microsoft Defender for Endpoint。

> [!CAUTION]
> 在 Linux 上运行其他第三方终结点保护产品以及 Microsoft Defender for Endpoint 可能会导致性能问题和不可预知的副作用。 如果非 Microsoft 终结点保护在你的环境中是绝对要求，在将防病毒功能配置为在被动模式下运行后，你仍然可以安全地利用 Linux EDR 上的 Defender for [Endpoint 功能](linux-preferences.md#enable--disable-passive-mode)。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>如何在 Linux 上安装 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>先决条件

- 访问 Microsoft 365 Defender 门户
- 使用系统系统 [管理器的](https://systemd.io/) Linux 分发
- Linux 和 BASH 脚本的初学者级体验
- 手动部署时，设备上 (管理权限) 

> [!NOTE]
> Linux 代理上的 Microsoft Defender for Endpoint 独立于 [OMS 代理](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)。 Microsoft Defender for Endpoint 依赖于自己的独立遥测管道。


### <a name="installation-instructions"></a>安装说明

有几种方法和部署工具可用于在 Linux 上安装和配置 Microsoft Defender for Endpoint。

通常，您需要执行以下步骤：

- 确保你拥有适用于终结点的 Microsoft Defender 订阅，并且你有权访问 [适用于终结点](microsoft-defender-security-center.md)的 Microsoft Defender 门户。
- 使用下列部署方法之一在 Linux 上部署 Microsoft Defender for Endpoint：
  - 命令行工具：
    - [手动部署](linux-install-manually.md)
  - 第三方管理工具：
    - [使用配置管理工具进行部署](linux-install-with-puppet.md)
    - [使用可配置管理工具进行部署](linux-install-with-ansible.md)
    - [使用部署配置管理工具进行部署](linux-deploy-defender-for-endpoint-with-chef.md)

如果遇到任何安装失败，请参阅 Linux 上的 Microsoft Defender for Endpoint 中的安装 [失败疑难解答](linux-support-install.md)。

> [!NOTE]
> 不支持在默认安装路径外的其他任何其他位置安装 Microsoft Defender for Endpoint。 

### <a name="system-requirements"></a>系统要求

- 支持 Linux 服务器分发和 x64 (AMD64/EM64T) 版本：

  - Red Hat Enterprise Linux 6.7 或更高版本
  - Red Hat Enterprise Linux 7.2 或更高版本 
  - CentOS 6.7 或更高版本 
  - CentOS 7.2 或更高版本
  - Ubuntu 16.04 LTS 或更高版本 LTS
  - Debian 9 或更高版本
  - SUSE Linux Enterprise Server 12 或更高版本
  - Oracle Linux 7.2 或更高版本
  - Amazon Linux 2
  - Fedora 33 或更高版本

    > [!NOTE]
    > 未明确列出的分发和版本不受支持 (即使它们派生自正式支持的分发) 。


    对于 Red Hat Enterprise Linux 6 和 CentOS 6，受支持的内核版本列表为：
       - 对于 6.7：2.6.32-573。* 
       - 对于 6.8：2.6.32-642.* 
       - 对于 6.9：2.6.32-696.* 
       - 对于 6.10：2.6.32.754.2.1.el6.x86_64 2.6.32-754.41.2：

    版本列表：

    - 2.6.32-754.2.1.el6.x86_64 
    - 2.6.32-754.17.1.el6.x86_64
    - 2.6.32-754.29.1.el6.x86_64
    - 2.6.32-754.3.5.el6.x86_64 
    - 2.6.32-754.18.2.el6.x86_64
    - 2.6.32-754.29.2.el6.x86_64
    - 2.6.32-754.6.3.el6.x86_64 
    - 2.6.32-754.22.1.el6.x86_64
    - 2.6.32-754.30.2.el6.x86_64
    - 2.6.32-754.9.1.el6.x86_64 
    - 2.6.32-754.23.1.el6.x86_64
    - 2.6.32-754.33.1.el6.x86_64
    - 2.6.32-754.10.1.el6.x86_64
    - 2.6.32-754.24.2.el6.x86_64
    - 2.6.32-754.35.1.el6.x86_64
    - 2.6.32-754.11.1.el6.x86_64
    - 2.6.32-754.24.3.el6.x86_64
    - 2.6.32-754.39.1.el6.x86_64
    - 2.6.32-754.12.1.el6.x86_64
    - 2.6.32-754.25.1.el6.x86_64
    - 2.6.32-754.41.2.el6.x86_64
    - 2.6.32-754.14.2.el6.x86_64
    - 2.6.32-754.27.1.el6.x86_64
    - 2.6.32-754.15.3.el6.x86_64
    - 2.6.32-754.28.1.el6.x86_64       


- 最低内核版本 3.10.0-327

- `fanotify`必须启用内核选项

  > [!CAUTION]
  > 不支持在 Linux 上并行运行 Defender for Endpoint 和基于 `fanotify` 其他的安全解决方案。 它可能会导致不可预知的结果，包括挂起操作系统。

- 磁盘空间：1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon 需要可执行权限。 有关详细信息，请参阅在 Linux 上解决 Microsoft Defender for Endpoint 的安装问题中的"确保守护程序具有[可执行权限"。](/microsoft-365/security/defender-endpoint/linux-support-install)

- 核心：最少 2 个，首选 4 个

- 内存：最小 1 GB，首选 4 GB

    > [!NOTE]
    > 请确保 /var 中具有可用磁盘空间。

- 解决方案当前为以下文件系统类型提供实时保护：

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

启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的出站连接。

- 必须 `auditd` () 审核框架。

  > [!NOTE]
  > 通过添加到 的规则捕获的系统事件将添加到 (，) 并可能影响主机审核和上游 `/etc/audit/rules.d/` `audit.log` 集合。 Linux 上的 Microsoft Defender for Endpoint 添加的事件将用密钥 `mdatp` 进行标记。

### <a name="configuring-exclusions"></a>配置排除项

将排除项添加到Microsoft Defender 防病毒时，应注意用于Microsoft Defender 防病毒[](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)

### <a name="network-connections"></a>网络连接

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则。 如果有，可能需要专门为 *他们创建允许* 规则。

<br>

****

|域列表的电子表格|说明|
|---|---|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图。](images/mdatp-urls.png)|服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <p> 在此处下载 [电子表格](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)。|
|||

> [!NOTE]
> 有关更具体的 URL 列表，请参阅 [配置代理和 Internet 连接设置](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

Defender for Endpoint 可以使用以下发现方法发现代理服务器：

- 透明代理
- 手动静态代理配置

如果代理或防火墙阻止匿名流量，请确保前面列出的 URL 中允许匿名流量。 对于透明代理，不需要对 Defender for Endpoint 进行其他配置。 对于静态代理，请按照手动静态代理 [配置 中的步骤操作](linux-static-proxy-configuration.md)。

> [!WARNING]
> 不支持 PAC、WPAD 和经过身份验证的代理。 确保仅使用静态代理或透明代理。
>
> 出于安全考虑，也不支持 SSL 检查和截获代理。 为 SSL 检查和代理服务器配置例外，以直接将数据从 Linux 上的 Defender for Endpoint 传递到相关 URL，而不会拦截。 将拦截证书添加到全局存储将不允许拦截。

有关疑难解答步骤，请参阅在 Linux 上解决 [Microsoft Defender for Endpoint 的云连接问题](linux-support-connectivity.md)。

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>如何在 Linux 上更新 Microsoft Defender for Endpoint

Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。 若要在 Linux 上更新 Microsoft Defender for Endpoint，请参阅在 Linux 上部署 [Microsoft Defender for Endpoint 的更新](linux-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>如何配置 Linux 版 Microsoft Defender for Endpoint

有关如何在企业环境中配置产品的指南，可在在 Linux 上设置 [Microsoft Defender for Endpoint 的首选项中提供](linux-preferences.md)。

## <a name="common-applications-to-microsoft-defender-for-endpoint-can-impact"></a>适用于终结点的 Microsoft Defender 的常见应用程序可能会影响

安装 Microsoft Defender for Endpoint 时，某些应用程序中的高 I/O 工作负载可能会遇到性能问题。 其中包括用于开发人员方案（如 Jenkins 和 Jira）的应用程序，以及数据库工作负荷（如 OracleDB 和 Postgres）。 如果遇到性能下降，请考虑为受信任应用程序设置排除项，并记住[Microsoft Defender 防病毒错误。](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus) 有关其他指南，请考虑有关第三方应用程序的防病毒排除项的咨询文档。

## <a name="resources"></a>资源

- 有关日志记录、卸载或其他主题的信息，请参阅 [资源](linux-resources.md)。
