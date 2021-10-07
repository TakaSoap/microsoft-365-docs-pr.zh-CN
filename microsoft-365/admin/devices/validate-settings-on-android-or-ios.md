---
title: 验证 Android 或 iOS 设备上的应用保护设置
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 了解如何验证 Android Microsoft 365 商业高级版 iOS 设备中的应用保护设置。
ms.openlocfilehash: 100c4f759578100ae94df24bb7009f4e76a6eb02
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165384"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>验证 Android 或 iOS 设备上的应用保护设置

按照以下部分中的说明验证 Android 或 iOS 设备上的应用保护设置。
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>检查应用保护设置在用户设备上是否正常工作

在[设置用于 Android 设备的应用配置](app-protection-settings-for-android-and-ios.md)以保护应用后，可按以下步骤验证所选设置是否有效。 
  
首先，确保该策略适用于你要验证它的应用。
  
1. 在管理 [Microsoft 365 商业高级版，](https://admin.microsoft.com)转到"策略 **""** \> **编辑策略"。**
    
2. 例如 **，选择"Android** 应用程序策略"作为你在设置时创建的设置或创建的另一个策略，并验证是否Outlook应用策略。 
    
    ![Shows all the apps for which this policy protects files.](../../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>验证"需要 PIN 或指纹才能访问 Office 应用"

在" **编辑策略**"窗格中，选择" **Office 文档的访问控制**"旁边的" **编辑**"，展开" **管理用户如何在移动设备上访问 Office 文件**"，并确保将" **需要 PIN 或指纹才能访问 Office 应用**"设置为" **开**"。
  
![确保"需要 PIN 或指纹来访问Office"设置为"打开"。](../../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 在用户的 Android 设备上，打开Outlook，然后使用用户的凭据Microsoft 365 商业高级版登录。
    
2. 系统还会提示你输入 PIN 或使用指纹。
    
    ![Enter a PIN on your Android device to access Office apps.](../../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>验证"超过登录失败次数限制后重置 PIN"

在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何在移动设备上访问 **Office** 文件"，并确保"在失败尝试次数后重置 **PIN"** 设置为一个数字。 默认情况下为 5。 
  
1. 在用户的 Android 设备上，打开Outlook，然后使用用户的凭据Microsoft 365 商业高级版登录。
    
2. 输入错误 PIN 的次数达到策略指定次数。 你将看到一条提示，指出 **"PIN 尝试限制已到达** "以重置 PIN。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. 按" **重置 PIN**"。 系统将提示你使用用户的凭据Microsoft 365 商业高级版登录，然后需要设置新的 PIN。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>验证"强制用户将所有工作文件保存到 OneDrive for Business"

在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **开**"。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 在用户的 Android 设备上，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。
    
2. 打开带附件的电子邮件，然后点击附件信息旁边的向下箭头图标。
    
    ![Tap the down arrow next to an attachment to try to save it.](../../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    你将在屏幕 **底部看到** 无法保存到设备。 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > 目前尚不可在 Android 上保存到 OneDrive for Business，因此仅会看到本地保存被阻止。 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>验证"Office 应用空闲指定时间后要求用户再次登录"

在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何访问移动设备上的 **Office** 文件"，并确保"要求用户在 Office 应用空闲后重新登录 **"** 设置为一定的分钟数。 默认情况下为 30 分钟。 
  
1. 在用户的 Android 设备上，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。
    
2. 现应该会显示 Outlook 收件箱。（最低标准）30 分钟不触碰 Android 设备而使其闲置（或者长于策略中指定时长的其他时间）。设备屏幕可能变暗。
    
3. 再次Outlook Android 设备上的应用。
    
4. 系统将提示你输入 PIN，然后才能再次访问Outlook PIN。
    
### <a name="validate-protect-work-files-with-encryption"></a>验证"使用加密保护工作文件"

在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **使用加密保护工作文件**"设置为" **开**"，将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **关**"。
  
1. 在用户的 Android 设备上，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。
    
2. 打开一封包含一些图像文件附件的电子邮件。
    
3. 点击附件信息旁边的向下箭头图标进行保存。
    
    ![Tap the down arrow to save the figure file to the Android device.](../../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. 系统可能会提示允许 Outlook 访问设备中的照片、媒体和文件。点击" **允许**"。
    
5. 在屏幕底部，选择" **保存到设备**"，然后打开" **库** "应用。 
    
6. 列表中应该会显示一张已加密的照片（如果保存了多个图像文件，将显示多张）。它可能会在"图片"列表中显示为灰色方框，其中心显示带白色感叹号的白色圆圈。
    
    ![An encrypted image file in the Gallery app.](../../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>检查"应用保护"设置在用户设备上是否正常工作

在[设置 iOS 设备的应用配置](app-protection-settings-for-android-and-ios.md)以保护应用后，可按以下步骤验证所选设置是否有效。 
  
首先，确保该策略适用于你要验证它的应用。
  
1. 在管理 [Microsoft 365 商业高级版，](https://admin.microsoft.com)转到"策略 **""** \> **编辑策略"。**
    
2. 选择 **"iOS** 的应用程序策略"作为在设置时创建的设置或创建的另一个策略，并验证是否对Outlook强制执行。 
    
    ![Shows all the apps for which this policy protects files.](../../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>验证需要 PIN 才能访问 Office 应用

在" **编辑策略**"窗格中，选择" **Office 文档的访问控制**"旁边的" **编辑**"，展开" **管理用户如何在移动设备上访问 Office 文件**"，并确保将" **需要 PIN 或指纹才能访问 Office 应用**"设置为" **开**"。
  
![确保"需要 PIN 或指纹来访问Office"设置为"打开"。](../../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. 在用户的 iOS 设备中，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录。
    
2. 系统还会提示你输入 PIN 或使用指纹。
    
    ![Enter a PIN on your IOS device to access Office apps.](../../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>验证"超过登录失败次数限制后重置 PIN"

在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何在移动设备上访问 **Office** 文件"，并确保"在失败尝试次数后重置 **PIN"** 设置为一个数字。 默认情况下为 5。 
  
1. 在用户的 iOS 设备中，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录。
    
2. 输入错误 PIN 的次数达到策略指定次数。 你将看到一条提示，指出 **"PIN 尝试限制已到达** "以重置 PIN。 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. 按" **确定**"。 系统将提示你使用用户的凭据Microsoft 365 商业高级版登录，然后需要设置新的 PIN。
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>验证"强制用户将所有工作文件保存到 OneDrive for Business"

在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **开**"。
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. 在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。
    
2. 打开包含附件的电子邮件，然后打开附件，在屏幕底部选择" **保存**"。 
    
    ![Tap the Save option after you open an attachment to try to save it.](../../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. 应只会看到用于 OneDrive for Business 的选项。 如果没有，请点击"**添加帐户****"，OneDrive for Business"** 添加帐户存储 **选择"帐户"。** 提供最终用户的登录Microsoft 365 商业高级版提示时进行登录。 
    
    点击" **保存**"，选择" **OneDrive for Business**"。
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>验证"Office 应用空闲指定时间后要求用户再次登录"

在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何访问移动设备上的 **Office** 文件"，并确保"要求用户在 Office 应用空闲后重新登录 **"** 设置为一定的分钟数。 默认情况下为 30 分钟。 
  
1. 在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。
    
2. 现应该会显示 Outlook 收件箱。在至少 30 分钟（或长于策略中指定时间的其他时间）内不触碰 iOS 设备。设备屏幕可能变暗。
    
3. 再次Outlook iOS 设备上访问设备。
    
4. 系统将提示你输入 PIN，然后才能再次访问Outlook PIN。
    
### <a name="validate-protect-work-files-with-encryption"></a>验证"使用加密保护工作文件"

在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **使用加密保护工作文件**"设置为" **开**"，将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **关**"。
  
1. 在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。
    
2. 打开一封包含一些图像文件附件的电子邮件。
    
3. 点击该附件，然后点击其下的" **保存**"选项。 
    
4. 从主屏幕打开" **照片**"应用。应看到已保存且加密的照片（如果保存了多个图像文件附件，将看到更多照片）。 
    
---

