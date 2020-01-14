---
title: 从 Office 365 商业高级版升级到 Microsoft 365 商业版
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 将你的企业从 Office 365 商业高级升级到 Microsoft 365 业务的步骤。
ms.openlocfilehash: 61da9148ccb87654aa2391ff90c4f086a4cbbe24
ms.sourcegitcommit: 3c296126ba69a32af07e339f2f1eacdd8e5b878e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41120133"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>从 Office 365 商业高级版升级到 Microsoft 365 商业版

如果你有[office 365 for business 订阅](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)（例如 Office 365 商业高级版），你可以轻松地升级到 Microsoft 365 business。 如果要添加以下内容，请升级到 Microsoft 365 商业版： 
- Windows 10 专业版（对运行 Windows 8 或更高版本的电脑）
- 管理设备上的业务数据的简单控件
- 高级安全功能。
有关[Microsoft.com](https://www.microsoft.com/microsoft-365/business)的详细信息，请参阅 Microsoft 365 商业版

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>Office 365 商业高级版和 Microsoft 365 商业版之间的区别是什么？
我们已将这两个计划的并行比较添加到[Microsoft 365 业务服务说明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)中。 

## <a name="before-you-get-started"></a>开始前的准备

- **我应该何时选择升级？** 如果要升级分配给单个计划的**所有用户**，则升级是正确的选择。 当您选择 "升级" 时，所有计划用户都会同时切换到另一个计划。 如果您不想将每个分配到单个计划的用户进行升级，请为新计划购买许可证（在此示例中为 Microsoft 365 企业版），并[将这些许可证单独分配](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)给您要升级的每个用户。 
- **某些加载项可能会阻止升级**如果您尝试启动升级且您的加载项无法继续运行，则可以先删除加载项，以后再将其添加回来（如果仍需要）。 
- **如果预付计划**预付计划没有直接的升级路径。 你会知道你是否拥有预付计划，因为你使用可能已在商店中购买的产品 ID 设置你的计划。 联系合作伙伴，转到 Microsoft Store，或等到预付计划过期，以切换到新计划。

## <a name="upgrade-to-microsoft-365-business"></a>升级到 Microsoft 365 商业版
通过在[新管理中心](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)中执行以下步骤来购买你的许可证：
1. 登录到管理员中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。
2. 转到导航窗格，然后选择 "**计费** \> **产品 & 服务**"。 查找你的 Office 365 订阅并将其选中以查看详细信息。 

    ![屏幕截图显示如何在管理中心查找和选择订阅。](media/FindYourSubscription.png)

3. 在下一个页面上，选择 "**升级**"。 

      ![屏幕截图显示在管理中心中选择 "升级" 的位置。](media/SelectUpgrade.png)

  > [!NOTE]
  > 如果您看到一条消息，指出**在 Azure Active Directory 中不支持将订阅升级到基于组的许可证**，则可以安全地忽略此消息，除非您的组织非常大。 已选择此选项的组织将知道他们使用的是基于组的许可。

4. 接下来，您可以查看可以升级到的 Office 计划的列表。 在这种情况下，请查找 Microsoft 365 商业版计划。 如果想要查看此计划中包含的所有 Office 应用和服务，可以向下滚动。 在**Microsoft 365 商业**版下，选择 "**升级**" 以将 Microsoft 365 业务添加到你的购物车。
5. 在购物车中：
    1. 我们将自动为你的所有当前用户包含许可证。 如果你需要更多或更少的许可证，你需要[单独购买并分配这些许可证](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)。  
    2. 您可以调整您想要支付的方式：每月或每年。 选择下拉菜单以做出选择。
6. 选择您将看到购买摘要的 "**转到签出**"，其中包括此帐户的付款方式。 您还可以在此处添加促销代码（如果有的话）。
7. 选择 "**下订单**" 以完成购买。
需要 Microsoft 几分钟的时间来设置新的服务计划。 若要查看进度，请选择 "**检查升级状态**"。 
1. 计划准备就绪后，您可能需要在管理中心完成一些额外的设置步骤。 在导航窗格中，选择 "**主页**" 以完成任何其他设置步骤。

> [!NOTE]
> 你将收到一个你不再需要的 Office 365 许可证的按比例退款。 在设置新计划后，您的银行帐户或信用卡将会在两天内收取费用。
  
## <a name="protect-user-devices-and-files"></a>保护用户设备和文件

现在已分配 Microsoft 365 业务许可证，请完成启动保护设备和文件的步骤。 你将使用管理中心导航窗格中包含的一些新选项。
  
1. 在 "管理中心" 的导航窗格中，转到 "**设备** \> **策略**"。
    
2. 在 "**设备策略**" 页上，选择 "**添加**"。
    
3. 在 "**添加策略**" 窗格中，为策略指定一个名称（例如，"保护工作文件"），然后从下拉列表中选择一个**策略类型**。 
    
    您可以设置应用程序策略来保护 Android 和 iPhone 设备上的文件以及 Windows 10，还可以为公司拥有的 Windows 10 设备设置设备配置策略。 有关详细信息，请参阅以下链接：
    
  - [设置 Android 或 iOS 设备的应用保护设置](app-protection-settings-for-android-and-ios.md)
    
  - [设置 Windows 10 设备的应用程序保护设置](protection-settings-for-windows-10-devices.md)
    
  - [设置 Windows 10 电脑的设备保护设置](protection-settings-for-windows-10-pcs.md)
    
  
4. 设置策略后，你和你的员工可以设置设备：
    
  - 如果你的 Windows 设备尚未使用 Windows Pro Creator 更新，则需要将[其升级到 Windows Pro 创意者更新](upgrade-to-windows-pro-creators-update.md)。
    
  - 有关 Windows 设备的步骤，请参阅为[Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)。 
    
  - 有关 Android 手机和 Iphone 的步骤，请参阅为[Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。 
