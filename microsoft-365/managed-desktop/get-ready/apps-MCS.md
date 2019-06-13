---
title: 使用 Microsoft 咨询服务
description: 使用 MCS 来打包应用程序需要遵循的准备和步骤
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用、MCS、打包
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918717"
---
# <a name="working-with-microsoft-consulting-services"></a>使用 Microsoft 咨询服务

你可以与 Microsoft 咨询服务 (MCS) 接洽, 以获取打包用于 Microsoft 托管桌面的应用。 有关详细信息, 请与你的帐户代表联系 MCS 并将你的特定应用打包项目限定为范围。

## <a name="roles-and-responsibilities"></a>角色和职责

若要使用 MCS 应用程序打包,**您必须提供以下元素**:

- 源安装程序文件 (例如, setup.exe 或 .msi)。
- 安装说明, 指定有关最终安装的外观的详细信息。 例如, 是否应有应用程序的桌面快捷方式？ 应用程序的可见性是什么？ 应用是否应连接到服务器, 如果是, 是否应使用哪一个？ <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- 您必须执行自己的验收测试, 以验证应用程序在您的环境中是否按需运行。

**MCS 将负责执行以下操作:**

- 在 Microsoft 托管桌面环境中检查是否禁止或限制应用程序。
- 测试应用程序的安装、启动和卸载, 以确保与 Windows 10 兼容。 如果 MCS 发现兼容性问题, 则会将应用程序分发到[桌面应用](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure)程序, 从而确保程序的补救。
- 将应用程序打包到规范, 然后使用 Microsoft Intune 测试应用程序部署。

## <a name="app-delivery-schedule"></a>应用程序交付计划

通过将应用程序信息上载到 Microsoft 托管桌面门户来启动打包过程。 打包团队每星期四查看一次新的提交。 查看和打包后, 打包后的应用程序将在下星期五提供。 可以将每周最长5个应用打包到开始, 但服务可进行扩展以满足你的需求。

![显示应用程序评审、打包和交付日期的日历](images/MCS-cal.png)

一旦应用程序被传递, 你将收到通知。 在这种情况下, 你有21天的时间执行验收测试, 并对 Microsoft 托管桌面门户中的工作进行签名。 如果在接受测试过程中发现应用程序出现问题, 请在 Microsoft 托管桌面门户中拒绝应用程序, 并通过电子邮件通过 MCS 包装程序进行连接, 以了解并解决该问题。

## <a name="testing-accounts-and-environment"></a>测试帐户和环境

对于打包团队, 若要完成到 Microsoft Intune 的迁移, 我们建议您提供某些权限:
 
-   对包装程序的 Microsoft Intune 应用程序部署功能的访问权限, 以添加和分配应用程序 
-   测试组、用户帐户和 packagers 的许可证, 以便能够测试应用程序

MCS 将使用这些权限执行以下操作:
 
-   确保应用程序在为 Microsoft 托管桌面配置的虚拟机上运行
-   将应用程序上载到 Microsoft Intune 以部署到你的用户

如果没有这些权限, MCS 可以向前移动, 但不能将应用程序上传到您的环境。


