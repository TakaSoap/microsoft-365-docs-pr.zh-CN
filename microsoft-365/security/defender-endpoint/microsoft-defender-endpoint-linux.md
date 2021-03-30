---
title: 适用于 Linux 的 Microsoft Defender ATP
ms.reviewer: ''
description: 介绍如何安装和使用适用于 Linux 的 Microsoft Defender ATP。
keywords: microsoft， defender， atp， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
ms.openlocfilehash: 08bb4c73cb9df429c4b07194f1c7615f44d745d8
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408333"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Endpoint for Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主题介绍如何安装、配置、更新和使用适用于 Linux 的 Microsoft Defender for Endpoint。

> [!CAUTION]
> 将其他第三方终结点保护产品与 Microsoft Defender for Endpoint for Linux 一起运行可能会导致性能问题和不可预知的系统错误。

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a>如何安装适用于 Linux 的 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>必备条件

- 访问 Microsoft Defender 安全中心门户
- 使用系统 [系统管理器的](https://systemd.io/) Linux 分发
- Linux 和 BASH 脚本的初学者级体验
- 手动部署时，设备上 (管理权限) 

### <a name="installation-instructions"></a>安装说明

有几种方法和部署工具可用于安装和配置 Microsoft Defender for Endpoint for Linux。

通常，您需要执行以下步骤：

- 确保你拥有适用于终结点的 Microsoft Defender 订阅，并且你有权访问 [适用于终结点](microsoft-defender-security-center.md)的 Microsoft Defender 门户。
- 使用下列部署方法之一部署适用于 Linux 的 Microsoft Defender for Endpoint：
  - 命令行工具：
    - [手动部署](linux-install-manually.md)
  - 第三方管理工具：
    - [使用配置管理工具进行部署](linux-install-with-puppet.md)
    - [使用可配置管理工具进行部署](linux-install-with-ansible.md)

如果遇到任何安装失败，请参阅 Microsoft [Defender for Endpoint for Linux](linux-support-install.md)中的安装失败疑难解答。

### <a name="system-requirements"></a>系统要求

- 支持的 Linux 服务器分发和版本：

  - Red Hat Enterprise Linux 7.2 或更高版本
  - CentOS 7.2 或更高版本
  - Ubuntu 16.04 LTS 或更高版本 LTS
  - Debian 9 或更高版本
  - SUSE Linux Enterprise Server 12 或更高版本
  - Oracle Linux 7.2 或更高版本

- 最低内核版本 3.10.0-327
- `fanotify`必须启用内核选项
  > [!CAUTION]
  > 不支持将适用于 Linux 的 Defender for Endpoint 与其他 `fanotify` 基于的安全解决方案并行运行。 它可能会导致不可预知的结果，包括挂起操作系统。

- 磁盘空间：1GB
- /opt/microsoft/mdatp/sbin/wdavdaemon 需要可执行权限。 有关详细信息，请参阅解决适用于 Linux 的 Microsoft Defender ATP 的安装问题中的"确保守护程序具有可执行[权限"。](/microsoft-365/security/defender-endpoint/linux-support-install)
- 内存：1GB
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
  >[!NOTE]
  > 通过添加到 的规则捕获的系统事件将添加到审核日志 `audit.logs` ，并可能影响主机审核和上游收集。 由 Microsoft Defender for Endopoint for Linux 添加的事件将用密钥 `mdatp` 进行标记。

### <a name="network-connections"></a>网络连接

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则。 如果有，可能需要专门为 *他们创建允许* 规则。

|**域列表电子表格**|**描述**|
|:-----|:-----|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/>  | 服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <br><br>[在此处下载电子表格。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> 有关更具体的 URL 列表，请参阅 [配置代理和 Internet 连接设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

Defender for Endpoint 可以使用以下发现方法发现代理服务器：
- 透明代理
- 手动静态代理配置

如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。 对于透明代理，不需要对 Defender for Endpoint 进行其他配置。 对于静态代理，请按照手动静态代理 [配置 中的步骤操作](linux-static-proxy-configuration.md)。

> [!WARNING]
> 不支持 PAC、WPAD 和经过身份验证的代理。 确保仅使用静态代理或透明代理。
>
> 出于安全考虑，也不支持 SSL 检查和截获代理。 为 SSL 检查和代理服务器配置例外，以直接将数据从 Defender for Endpoint for Linux 传递到相关 URL，而不会拦截。 将拦截证书添加到全局存储将不允许拦截。

有关疑难解答步骤，请参阅 [解决 Microsoft Defender for Endpoint for Linux 的云连接问题](linux-support-connectivity.md)。

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a>如何为 Linux 更新 Microsoft Defender for Endpoint

Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。 若要更新适用于 Linux 的 Microsoft Defender for Endpoint，请参阅 [部署适用于 Linux](linux-updates.md)的 Microsoft Defender for Endpoint 的更新。

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a>如何配置适用于 Linux 的 Microsoft Defender 终结点

有关如何在企业环境中配置产品的指南可在设置适用于 Linux 的 [Microsoft Defender for Endpoint 的首选项中提供](linux-preferences.md)。

## <a name="resources"></a>资源

- 有关日志记录、卸载或其他主题的信息，请参阅 [资源](linux-resources.md)。
