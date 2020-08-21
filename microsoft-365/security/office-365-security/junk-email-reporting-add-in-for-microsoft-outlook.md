---
title: 安装和使用 Microsoft Outlook 的垃圾邮件报告加载项
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: 了解如何安装和使用 Microsoft 垃圾电子邮件报告插件向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件。
ms.openlocfilehash: 42b38830b55ae3dbee4ec74a0e96531d920c24a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827095"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>安装和使用 Microsoft Outlook 的垃圾邮件报告加载项

> [!NOTE]
> 如果当前未使用垃圾电子邮件报告加载项，建议 [改为使用报告邮件](enable-the-report-message-add-in.md) 外接程序。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

用户可以通过 Microsoft Outlook 垃圾电子邮件报告外接程序将误报 (标记为垃圾邮件) 、允许邮件 (错误的邮件) 添加到 Microsoft。 如果您的组织不使用 Exchange Online Protection (例如，本地 Exchange 或 Exchange Online) 以外的电子邮件服务，您的垃圾邮件报告提交将不会影响垃圾邮件筛选。

本主题说明如何安装和使用垃圾邮件报告外接程序。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要安装垃圾电子邮件报告外接程序，请参阅 [本主题后面的"安装垃圾邮件](#install-the-junk-email-reporting-add-in) 报告加载项"部分。

- 垃圾电子邮件报告加载项可与 Outlook 的以下版本一起使用：

  - Outlook 2013 或更高版本
  - Microsoft 365 企业应用版随附的 Outlook

- 有关向 Microsoft 报告消息的详细信息，请参阅"[报告邮件和文件到 Microsoft"。](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>使用垃圾邮件报告加载项报告垃圾邮件和网络钓鱼邮件

1. 对于"收件箱"或"垃圾邮件"之外的任何其他电子邮件文件夹中的邮件，请使用下列任意一种方法报告垃圾邮件和网络钓鱼邮件：

   - 选择邮件或打开邮件。 在功能区**的"主页****"** 或"邮件"选项卡中，单击 **"垃圾邮件"，** 然后选择"**报告**为**网络钓鱼邮件"。**

     ![从功能区报告垃圾或钓鱼电子邮件](../../media/junk-email-reporting-ribbon.png)

   - 右键单击邮件，选择"垃圾邮件 **"，** 然后选择"**报告为网络**钓**鱼邮件"。**

     ![通过右键单击报告垃圾或网络钓鱼邮件](../../media/junk-email-reporting-right-click.png)

   - 选择多个邮件，右键单击，然后选择"报告**为网络****钓鱼邮件"。**

     ![从右击报告多个垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

2. 在出现的对话框中，阅读信息并单击"报告 **"。** 如果您改变了主想，请单击 **"不报告"。**

   !["报告为垃圾邮件"对话框](../../media/junk-email-reporting-report-as-junk-dialog.png)

   !["报告为网络钓鱼"对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 选定的消息会被发送至 Microsoft 以供分析，且：

   - 如果被报告为垃圾邮件，移动到"垃圾邮件"文件夹。
   - 删除（如果报告为钓鱼邮件）。
   
   若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>使用垃圾电子邮件报告外接程序从"垃圾邮件"文件夹报告非垃圾邮件和网络钓鱼邮件

1. 在"垃圾邮件"文件夹中，可使用以下任意一种方法报告垃圾邮件误报或网络钓鱼邮件：

   - 选择邮件或打开邮件。 在功能区**的"主页****"或**"邮件"选项卡中，单击 **"非垃圾邮件**"，然后选择"**报告****为网络钓鱼邮件"。**

     ![从功能区的"垃圾邮件"文件夹中报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - 右键单击邮件，单击"垃圾邮件 **"，** 然后选择"**报告为'非垃圾邮件'** 或 **'报告为网络钓鱼邮件'。**

     ![在"垃圾邮件"文件夹中，通过右键单击报告非垃圾邮件或网络钓鱼邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 选择多个邮件，右键单击，然后选择"报告**为网络**钓**鱼邮件"。**

     ![在"垃圾邮件"文件夹中通过右击报告多个非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 在出现的对话框中，阅读信息并单击"报告 **"。** 如果您改变了主想，请单击 **"不报告"。**

   ![报告为非垃圾邮件对话框](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   !["报告为网络钓鱼"对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 选定的消息会被发送至 Microsoft 以供分析，且：

   - 如果被报告为垃圾邮件，移动到"垃圾邮件"文件夹。
   - 删除（如果报告为钓鱼邮件）。

   若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="install-the-junk-email-reporting-add-in"></a>安装垃圾电子邮件报告加载项

- 您需要在要安装外接程序的计算机上拥有管理员权限。

- 转到 <https://www.microsoft.com/download/details.aspx?id=18275> 适用于您的 Office 版本的相应 .msi 文件并将其下载到易于查找的位置：

  - **32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- 对于 Outlook 2013 或更高版本，唯一的先决条件是 Microsoft .NET Framework 2.0。 在 Windows 10 中，不从下载安装 .NET Framework 2.0。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>使用安装向导安装垃圾电子邮件报告外接程序

1. 在您的计算机上关闭 Outlook。

2. 在 Windows 10 中，验证已启用 .NET Framework 2.0。 有关说明，请参阅["控制面板中启用 .NET Framework 3.5"。](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)

3. 找到您下载的 .msi 文件并双击它。

4. 在“欢迎使用 Microsoft 垃圾电子邮件报告外接程序安装程序”**** 页面上，单击“下一步”****。

5. 查看许可协议，如果您同订这些条款 **，** 请单击"我接受许可协议中的条款"，然后单击"下一**步"。**

6. 向导完成后，单击“完成”****。 

启动 Outlook。

查找 Outlook **功能区** 上的"垃圾邮件"按钮。 现在，可以通过在收件箱中选择垃圾电子邮件并单击“报告垃圾邮件”**** 按钮，向 Microsoft 报告垃圾电子邮件。

如果想要向 Microsoft 报告仿冒垃圾电子邮件，请选择****“垃圾邮件”旁边的向下箭头查看更多选项，如****“报告为仿冒邮件”。如果一封电子邮件被错误识别为垃圾邮件，则在垃圾邮件文件夹中，您还可以选择“报告不是垃圾邮件”****。

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>使用静默模式安装垃圾电子邮件报告外接程序

1. 在您的计算机上关闭 Outlook。

2. 在 Windows 10 中，通过运行以下命令安装 .NET Framework 2.0：

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. 若要在不进行任何用户交互的情况下安装加载项，请打开命令提示符，并使用以下语法：

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` 指定可以为一个提交选择的最大邮件数。 有效值为 1 至 50。 默认值为 15。

   - `BccEmailAddress` 指定接收所有用户提交副本的其他"Bcc"收件人。 默认值是不包含其他 (抄送收件人"列表，) 。

   此示例使用默认设置的指定路径安装 64 位版本的加载项。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   此示例使用以下其他设置，从指定路径安装 32 位版本的加载项：

   - 在一个提交中最多可选择 20 个邮件。
   - junkreports@contoso.com和 hollyd@treyresearch.net收到所有提交的 Bcc 副本。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功安装垃圾电子邮件报告外接程序，请在 Outlook 中执行以下任一步骤：

- 选择邮件或打开邮件。 在功能区**的"****主页**"或"邮件"选项卡中，**单击"垃圾邮件**"，然后验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为钓鱼邮件**
  - **垃圾邮件报告选项**
  - **报告垃圾邮件联机帮助**

  ![从功能区报告垃圾或钓鱼电子邮件](../../media/junk-email-reporting-ribbon.png)

- 右键单击邮件，选择" **垃圾邮件"，** 然后验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为钓鱼邮件**
  - **垃圾邮件报告选项**
  - **报告垃圾邮件联机帮助**

  ![通过右键单击报告垃圾或网络钓鱼邮件](../../media/junk-email-reporting-right-click.png)

- 选择多个邮件、右键单击，并验证以下选项是否可用：

  - **报告为垃圾邮件**
  - **报告为钓鱼邮件**

  ![从右击报告多个垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

- 在"垃圾邮件"文件夹中执行之前**的操作**并验证之前的**垃圾邮件报告**选项现在是否不是 **"垃圾邮件"。**

  ![从功能区的"垃圾邮件"文件夹中报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![在"垃圾邮件"文件夹中，通过右键单击报告非垃圾邮件或网络钓鱼邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![在"垃圾邮件"文件夹中通过右击报告多个非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>卸载垃圾电子邮件报告外接程序

关闭 Outlook 之后，请执行下列任意过程卸载垃圾电子邮件报告外接程序：

- **控制面板**：按 Windows 键 + R。在打开**的**"运行"对话框中，输入 `control appwiz.cpl` ，然后单击"确定 **"。**

  在列表中**查找并选择"Microsoft 垃圾电子邮件**报告外接程序"，然后单击"卸载 **"。**

- **Windows Installer 程序包**：查找或下载相应的 .msi 文件，然后双击该文件。

  - **32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  在出现的对话框中，选择"删除**Outlook 的 Microsoft 垃圾邮件报告外接程序"，** 然后单击"下一步 **"。**

- **静默模式：** 查找或下载相应的 .msi 文件。 在命令提示符窗口中， \<PathToFile\> 将 .msi 文件的位置替换为 .msi 文件的位置，然后运行以下命令之一：

  - **32 位**：

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 位**：

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

卸载后打开 Outlook 时，应该会删除垃圾邮件、非垃圾邮件和网络钓鱼报告选项。

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>疑难解答垃圾电子邮件报告加载项

有时，您的 Outlook 在添加垃圾邮件报告外接程序之后可能出现问题。 本节介绍您可能遇到的问题以及解决这些问题的提示。

### <a name="troubleshooting-for-users"></a>用户的疑难解答

您会遇到以下一个或多个问题：

- Nothing happens when you click **Report Junk**
- 当您选择一封电子邮件之后，Outlook 停止响应
- 由于收到"未送达"回复，报告的垃圾邮件无法传递

要解决此问题，请执行下列步骤：

1. 关闭并重新启动 Outlook。
2. 创建并发送测试邮件，并验证收件人是否收到此邮件。
3. 如果问题仍然存在，请与管理员联系。

有关可用于将邮件提交给 Microsoft 的其他方法，请参阅"[报告邮件和文件"提交给 Microsoft。](report-junk-email-messages-to-microsoft.md)

### <a name="troubleshooting-for-admins"></a>管理员疑难解答

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>问题：不一步显示错误消息，要求用户联系系统管理员

1. 验证或将 `LoggingLevel` 注册表项设置为值"详细"：

   - **32 位 Windows 上的 32 位 Outlook：**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 位 Windows 上的 32 位 Outlook：**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 位 Outlook：**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. 重新启动 Outlook，并要求用户在看到错误消息时回退。

3. 收集在以下位置找到的日志信息：

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. 联系 Exchange Online Protection 技术支持并向他们提供日志信息。

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>问题：用户在报告邮件时选择了不接收确认提示，而现在他们想要提示

1. 创建 `ConfirmReportJunk` 注册表项，其值为"True"：

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. 重新启动 Outlook。
