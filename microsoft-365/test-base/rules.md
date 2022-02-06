---
title: 应用程序/测试规则
description: 上载应用程序/测试时要遵循的规则
search.appverid: MET150
author: andreicsibi-msft
ms.author: ancsibi
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: null
ms.reviewer: mapatel
f1.keywords: NOCSH
---
# <a name="applicationtest-rules"></a>应用程序/测试规则

测试基础中的所有应用程序或测试都需要符合以下规则：

## <a name="test-base-folders"></a>测试基本文件夹 

测试基基础结构使用下列文件夹：
* %SYSTEMDRIVE%\USL
* %SYSTEMDRIVE%\EtlExport
* %SYSTEMDRIVE%\Ffmpeg
* %SYSTEMDRIVE%\Monitoring
* %SYSTEMDRIVE%\powershell-yaml
* %SYSTEMDRIVE%\ProcMon
* %SYSTEMDRIVE%\PSTools
* %SYSTEMDRIVE%\TokenProviderTool
* %SYSTEMDRIVE%\USLPowershellModules
* %SYSTEMDRIVE%\UtcUtil
* %SYSTEMDRIVE%\WPT
* %SYSTEMDRIVE%\WULogs

> [!IMPORTANT]
> **避免以下事项**：
> * 阻止从这些文件夹执行任何进程。 如果应用程序是反恶意软件，请配置应用安装，以允许这些文件夹中的所有进程未受阻碍地执行。
> * 篡改其中任何文件夹。

## <a name="test-base-registry-keys"></a>测试基本注册表项

应用程序/测试不应删除或修改与以下项相关的任何注册表项：
* Windows遥测级别
* 删除 TLS 1.2
