---
title: 在 macOS 设备上注册 Microsoft Defender for Endpoint 到 Jamf Pro
description: 在 macOS 设备上注册 Microsoft Defender for Endpoint 到 Jamf Pro
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: bec8c6a2a329bff8e80c6822480ea03dd5db4898
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171073"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>在 macOS 设备上注册 Microsoft Defender for Endpoint 到 Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

## <a name="enroll-macos-devices"></a>注册 macOS 设备

有多种方法注册 JamF。

本文将指导你采用两种方法：

- [方法 1：注册邀请](#enrollment-method-1-enrollment-invitations)
- [方法 2：Prestage 注册](#enrollment-method-2-prestage-enrollments)

有关完整列表，请参阅关于 [计算机注册](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)。

## <a name="enrollment-method-1-enrollment-invitations"></a>注册方法 1：注册邀请

1. 在 Jamf Pro仪表板中，导航到注册 **邀请**。

    ![配置设置 1 的图像。](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. 选择 **+ 新建**。

    ![自动生成的徽标描述的关闭。](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. 在 **"为邀请指定** 收件人>电子邮件地址"下，输入收件人 (电子邮件地址) 电子邮件地址。

    ![配置设置 2 的图像。](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![配置设置 3 的图像。](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    例如：janedoe@contoso.com

    ![配置设置的图像4。](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. 为邀请配置邮件。

    ![配置设置的图像5。](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![配置设置的图像6。](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![配置设置7 的图像。](images/3ced5383a6be788486d89d407d042f28.png)

    ![配置设置的图像8。](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>注册方法 2：预阶段注册

1. 在 Jamf Pro仪表板中，导航到 **Prestage 注册**。

    ![配置设置9 的图像。](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. 按照 Computer [PreStage Enrollments 中的说明操作](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)。

## <a name="enroll-macos-device"></a>注册 macOS 设备

1. 选择 **"继续** "，然后从"系统首选项" **窗口安装 CA** 证书。

    ![Jamf Pro 1 的图像。](images/jamfpro-ca-certificate.png)

2. 安装 CA 证书后，返回到浏览器窗口，然后选择" **继续** "并安装 MDM 配置文件。

    ![Jamf Pro enrollment2 的图像。](images/jamfpro-install-mdm-profile.png)

3. 选择 **允许** 从 JAMF 下载。

    ![Jamf Pro注册3 的图像。](images/jamfpro-download.png)

4. 选择 **"** 继续"继续安装 MDM 配置文件。

    ![Jamf Pro注册4 的图像。](images/jamfpro-install-mdm.png)

5. 选择 **"继续** "以安装 MDM 配置文件。

    ![Jamf Pro注册5 的图像。](images/jamfpro-mdm-unverified.png)

6. 选择 **"继续**  "完成配置。

    ![Jamf Pro注册6 的图像。](images/jamfpro-mdm-profile.png)
