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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6189b61826cd56e2a8652032998c3b2df8f980ce
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468668"
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

1. 在 Jamf Pro仪表板中，导航到"**注册邀请"**。

   :::image type="content" source="images/a347307458d6a9bbfa88df7dbe15398f.png" alt-text="配置设置1" lightbox="images/a347307458d6a9bbfa88df7dbe15398f.png":::

2. 选择 **" + 新建"**。

   :::image type="content" source="images/b6c7ad56d50f497c38fc14c1e315456c.png" alt-text="自动生成的徽标说明的关闭" lightbox="images/b6c7ad56d50f497c38fc14c1e315456c.png":::

3. 在 **"为邀请指定** 收件人>电子邮件地址"下，输入收件人 (电子邮件地址) 电子邮件地址。

    :::image type="content" source="images/718b9d609f9f77c8b13ba88c4c0abe5d.png" alt-text="配置设置2" lightbox="images/718b9d609f9f77c8b13ba88c4c0abe5d.png":::

    :::image type="content" source="images/ae3597247b6bc7c5347cf56ab1e820c0.png" alt-text="配置设置3" lightbox="images/ae3597247b6bc7c5347cf56ab1e820c0.png":::

    例如：janedoe@contoso.com

    :::image type="content" source="images/4922c0fcdde4c7f73242b13bf5e35c19.png" alt-text="配置设置4" lightbox="images/4922c0fcdde4c7f73242b13bf5e35c19.png":::

4. 为邀请配置邮件。

   :::image type="content" source="images/ce580aec080512d44a37ff8e82e5c2ac.png" alt-text="配置设置5" lightbox="images/ce580aec080512d44a37ff8e82e5c2ac.png":::

   :::image type="content" source="images/5856b765a6ce677caacb130ca36b1a62.png" alt-text="配置设置6" lightbox="images/5856b765a6ce677caacb130ca36b1a62.png":::

   :::image type="content" source="images/3ced5383a6be788486d89d407d042f28.png" alt-text="配置设置7" lightbox="images/3ced5383a6be788486d89d407d042f28.png":::

   :::image type="content" source="images/54be9c6ed5b24cebe628dc3cd9ca4089.png" alt-text="配置设置8" lightbox="images/54be9c6ed5b24cebe628dc3cd9ca4089.png":::

## <a name="enrollment-method-2-prestage-enrollments"></a>注册方法 2：预阶段注册

1. 在 Jamf Pro仪表板中，导航到 **"Prestage 注册"**。

   :::image type="content" source="images/6fd0cb2bbb0e60a623829c91fd0826ab.png" alt-text="配置设置9" lightbox="images/6fd0cb2bbb0e60a623829c91fd0826ab.png":::

2. 按照 Computer [PreStage Enrollments中的说明操作](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)。

## <a name="enroll-macos-device"></a>注册 macOS 设备

1. 选择 **"继续** "，然后从"系统首选项" **窗口安装 CA** 证书。

   :::image type="content" source="images/jamfpro-ca-certificate.png" alt-text="Jamf Pro enrollment1" lightbox="images/jamfpro-ca-certificate.png":::

2. 安装 CA 证书后，返回到浏览器窗口，然后选择" **继续** "并安装 MDM 配置文件。

   :::image type="content" source="images/jamfpro-install-mdm-profile.png" alt-text="Jamf Pro enrollment2" lightbox="images/jamfpro-install-mdm-profile.png":::

3. 选择 **允许** 从 JAMF 下载。

   :::image type="content" source="images/jamfpro-download.png" alt-text="Jamf Pro enrollment3" lightbox="images/jamfpro-download.png":::

4. 选择 **"** 继续"继续安装 MDM 配置文件。

   :::image type="content" source="images/jamfpro-install-mdm.png" alt-text="Jamf Pro enrollment4" lightbox="images/jamfpro-install-mdm.png":::

5. 选择 **"继续** "以安装 MDM 配置文件。

   :::image type="content" source="images/jamfpro-mdm-unverified.png" alt-text="Jamf Pro注册5" lightbox="images/jamfpro-mdm-unverified.png":::

6. 选择 **"继续**  "完成配置。

   :::image type="content" source="images/jamfpro-mdm-profile.png" alt-text="Jamf Pro enrollment6" lightbox="images/jamfpro-mdm-profile.png":::
