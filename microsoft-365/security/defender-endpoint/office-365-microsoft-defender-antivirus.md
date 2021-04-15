---
title: 更好地结合 - Microsoft Defender 防病毒和 Office 365 (OneDrive) - 更好地防止勒索软件和网络威胁
description: 包括 OneDrive 的 Office 365 与 Microsoft Defender 防病毒一起千万万次。 阅读本文可了解更多信息。
keywords: windows defender， 防病毒， office 365， onedrive， 还原， 勒索软件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 41f22375aa117ba617eae59d4b8e9f8bb15ad4f0
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764095"
---
# <a name="better-together-microsoft-defender-antivirus-and-office-365"></a><span data-ttu-id="22d19-105">一起更得心防万一：Microsoft Defender 防病毒软件和 Office 365</span><span class="sxs-lookup"><span data-stu-id="22d19-105">Better together: Microsoft Defender Antivirus and Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="22d19-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="22d19-106">**Applies to:**</span></span>
- [<span data-ttu-id="22d19-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="22d19-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="22d19-108">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="22d19-108">Microsoft Defender Antivirus</span></span>
- <span data-ttu-id="22d19-109">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22d19-109">Microsoft 365</span></span>

<span data-ttu-id="22d19-110">您可能已经知道：</span><span class="sxs-lookup"><span data-stu-id="22d19-110">You might already know that:</span></span>

- <span data-ttu-id="22d19-111">**Microsoft Defender 防病毒可保护 Windows 10 设备** 免受软件威胁（如病毒、恶意软件和间谍软件）的侵害。</span><span class="sxs-lookup"><span data-stu-id="22d19-111">**Microsoft Defender Antivirus protects your Windows 10 device from software threats, such as viruses, malware, and spyware**.</span></span> <span data-ttu-id="22d19-112">Microsoft Defender 防病毒是完整的持续保护，内置于 Windows 10 中，随时可供使用。</span><span class="sxs-lookup"><span data-stu-id="22d19-112">Microsoft Defender Antivirus is your complete, ongoing protection, built into Windows 10 and ready to go.</span></span> <span data-ttu-id="22d19-113">[Microsoft Defender 防病毒是下一代保护](./microsoft-defender-antivirus-in-windows-10.md)。</span><span class="sxs-lookup"><span data-stu-id="22d19-113">[Microsoft Defender Antivirus is your next-generation protection](./microsoft-defender-antivirus-in-windows-10.md).</span></span> 

- <span data-ttu-id="22d19-114">**Office 365 包括反病毒、反垃圾邮件和反恶意软件保护**。</span><span class="sxs-lookup"><span data-stu-id="22d19-114">**Office 365 includes antiphishing, antispam, and antimalware protection**.</span></span> <span data-ttu-id="22d19-115">借助 Office 365 订阅，可以通过 OneDrive) 获取高级电子邮件和日历、Office 应用、1 TB 云存储空间 (以及所有设备的高级安全性。</span><span class="sxs-lookup"><span data-stu-id="22d19-115">With your Office 365 subscription, you get premium email and calendars, Office apps, 1 TB of cloud storage (via OneDrive), and advanced security across all your devices.</span></span> <span data-ttu-id="22d19-116">这适用于家庭用户和业务用户。</span><span class="sxs-lookup"><span data-stu-id="22d19-116">This is true for home and business users.</span></span> <span data-ttu-id="22d19-117">如果你是商业用户，并且你的组织正在使用 Office 365 E5，则通过 Microsoft Defender for Office 365 抵御 [Office 365](/microsoft-365/security/office-365-security/protect-against-threats)的威胁，你可以获得更多保护。</span><span class="sxs-lookup"><span data-stu-id="22d19-117">And if you're a business user, and your organization is using Office 365 E5, you get even more protection through Microsoft Defender for Office 365 [Protect against threats with Office 365](/microsoft-365/security/office-365-security/protect-against-threats).</span></span>

- <span data-ttu-id="22d19-118">**Office 365** 中包含的 OneDrive 使你能够联机存储文件和文件夹，并尽可能共享它们。</span><span class="sxs-lookup"><span data-stu-id="22d19-118">**OneDrive, included in Office 365, enables you to store your files and folders online, and share them as you see fit**.</span></span> <span data-ttu-id="22d19-119">你可以与用户协作 (工作或) ，以及存储在 OneDrive 中的共同作者文件。</span><span class="sxs-lookup"><span data-stu-id="22d19-119">You can work together with people (for work or fun), and coauthor files that are stored in OneDrive.</span></span> <span data-ttu-id="22d19-120">还可以在 PC、手机和平板电脑设备上访问 (设备中的) 。</span><span class="sxs-lookup"><span data-stu-id="22d19-120">You can also access your files across all your devices (your PC, phone, and tablet).</span></span> <span data-ttu-id="22d19-121">[在 OneDrive 中管理共享](/OneDrive/manage-sharing)。</span><span class="sxs-lookup"><span data-stu-id="22d19-121">[Manage sharing in OneDrive](/OneDrive/manage-sharing).</span></span>

<span data-ttu-id="22d19-122">**但是，你是否知道将 Microsoft Defender 防病毒与 Office 365** 一起使用有很多安全原因？</span><span class="sxs-lookup"><span data-stu-id="22d19-122">**But did you know there are good security reasons to use Microsoft Defender Antivirus together with Office 365**?</span></span> <span data-ttu-id="22d19-123">有两种支持方式：</span><span class="sxs-lookup"><span data-stu-id="22d19-123">Here are two:</span></span>

 1. <span data-ttu-id="22d19-124">[你获得勒索软件保护和恢复](#ransomware-protection-and-recovery)。</span><span class="sxs-lookup"><span data-stu-id="22d19-124">[You get ransomware protection and recovery](#ransomware-protection-and-recovery).</span></span>

 2. <span data-ttu-id="22d19-125">[集成意味着更好的保护](#integration-means-better-protection)。</span><span class="sxs-lookup"><span data-stu-id="22d19-125">[Integration means better protection](#integration-means-better-protection).</span></span>

<span data-ttu-id="22d19-126">阅读以下部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="22d19-126">Read the following sections to learn more.</span></span>

## <a name="ransomware-protection-and-recovery"></a><span data-ttu-id="22d19-127">勒索软件保护和恢复</span><span class="sxs-lookup"><span data-stu-id="22d19-127">Ransomware protection and recovery</span></span>

<span data-ttu-id="22d19-128">当你将文件保存到 [OneDrive](/onedrive)， [并且 Microsoft Defender 防病毒](./microsoft-defender-antivirus-in-windows-10.md) 在你的设备上检测到勒索软件威胁时，会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="22d19-128">When you save your files to [OneDrive](/onedrive), and [Microsoft Defender Antivirus](./microsoft-defender-antivirus-in-windows-10.md) detects a ransomware threat on your device, the following things occur:</span></span>

1. <span data-ttu-id="22d19-129">**将告知你威胁**。</span><span class="sxs-lookup"><span data-stu-id="22d19-129">**You are told about the threat**.</span></span> <span data-ttu-id="22d19-130"> (如果你的组织使用 Microsoft Defender [for Endpoint，](microsoft-defender-endpoint.md)你的安全运营团队也会收到通知。) </span><span class="sxs-lookup"><span data-stu-id="22d19-130">(If your organization is using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), your security operations team is notified, too.)</span></span>

2. <span data-ttu-id="22d19-131">**Microsoft Defender 防病毒可帮助你 (** 组织的安全团队) 从设备中删除勒索软件 () 。</span><span class="sxs-lookup"><span data-stu-id="22d19-131">**Microsoft Defender Antivirus helps you (and your organization's security team) remove the ransomware** from your device(s).</span></span> <span data-ttu-id="22d19-132"> (如果你的组织使用 Microsoft Defender for Endpoint，你的安全运营团队可以确定其他设备是否受到感染，并采取适当的措施。) </span><span class="sxs-lookup"><span data-stu-id="22d19-132">(If your organization is using Microsoft Defender for Endpoint, your security operations team can determine whether other devices are infected and take appropriate action, too.)</span></span>

3. <span data-ttu-id="22d19-133">**你可以选择恢复 OneDrive 中的文件**。</span><span class="sxs-lookup"><span data-stu-id="22d19-133">**You get the option to recover your files in OneDrive**.</span></span> <span data-ttu-id="22d19-134">使用 OneDrive 文件还原功能，可以将 OneDrive 中的文件恢复到勒索软件攻击发生之前的状态。</span><span class="sxs-lookup"><span data-stu-id="22d19-134">With the OneDrive Files Restore feature, you can recover your files in OneDrive to the state they were in before the ransomware attack occurred.</span></span> <span data-ttu-id="22d19-135">请参阅 [勒索软件检测和恢复文件](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)。</span><span class="sxs-lookup"><span data-stu-id="22d19-135">See [Ransomware detection and recovering your files](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f).</span></span>

<span data-ttu-id="22d19-136">考虑节省时间和麻烦这可以节省的时间。</span><span class="sxs-lookup"><span data-stu-id="22d19-136">Think of the time and hassle this can save.</span></span> 

## <a name="integration-means-better-protection"></a><span data-ttu-id="22d19-137">集成意味着更好的保护</span><span class="sxs-lookup"><span data-stu-id="22d19-137">Integration means better protection</span></span>

<span data-ttu-id="22d19-138">Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成意味着对组织的更好保护。</span><span class="sxs-lookup"><span data-stu-id="22d19-138">Microsoft Defender for Office 365 integrated with Microsoft Defender for Endpoint means better protection for your organization.</span></span> <span data-ttu-id="22d19-139">操作步骤如下：</span><span class="sxs-lookup"><span data-stu-id="22d19-139">Here's how:</span></span>

- <span data-ttu-id="22d19-140">[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp) 可保护你的组织免受电子邮件、电子邮件附件和 Office 文档中 (URL) 恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="22d19-140">[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp) safeguards your organization against malicious threats posed in email messages, email attachments, and links (URLs) in Office documents.</span></span>

    <span data-ttu-id="22d19-141">AND</span><span class="sxs-lookup"><span data-stu-id="22d19-141">AND</span></span>

- <span data-ttu-id="22d19-142">[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) 可保护你的设备免受网络威胁，检测高级攻击和数据泄露，自动执行安全事件，并改进你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="22d19-142">[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) protects your devices from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves your security posture.</span></span>

    <span data-ttu-id="22d19-143">SO</span><span class="sxs-lookup"><span data-stu-id="22d19-143">SO</span></span>

- <span data-ttu-id="22d19-144">启用集成后，安全运营团队可以在 Microsoft Defender 安全中心 () 中查看任何检测到的 URL 或电子邮件的收件人所使用的设备列表，以及这些设备的最新 [https://securitycenter.windows.com](https://securitycenter.windows.com) 警报。</span><span class="sxs-lookup"><span data-stu-id="22d19-144">Once integration is enabled, your security operations team can see a list of devices that are used by the recipients of any detected URLs or email messages, along with recent alerts for those devices, in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="22d19-145">如果尚未这样做，请集成 Microsoft [Defender for Office 365 和 Microsoft Defender for Endpoint](/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="22d19-145">If you haven't already done so, [integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="more-good-reasons-to-use-onedrive"></a><span data-ttu-id="22d19-146">使用 OneDrive 的更多理由</span><span class="sxs-lookup"><span data-stu-id="22d19-146">More good reasons to use OneDrive</span></span>

<span data-ttu-id="22d19-147">防止勒索软件是将文件放入 OneDrive 的一个重要原因。</span><span class="sxs-lookup"><span data-stu-id="22d19-147">Protection from ransomware is one great reason to put your files in OneDrive.</span></span> <span data-ttu-id="22d19-148">此外，还有一些更值得说明的原因，在此视频中进行了总结：</span><span class="sxs-lookup"><span data-stu-id="22d19-148">And there are several more good reasons, summarized in this video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/70b4d256-46fb-481f-ad9b-921ef5fd7bed]

## <a name="want-to-learn-more-see-these-resources"></a><span data-ttu-id="22d19-149">想要了解详细信息？</span><span class="sxs-lookup"><span data-stu-id="22d19-149">Want to learn more?</span></span> <span data-ttu-id="22d19-150">请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="22d19-150">See these resources:</span></span>

- [<span data-ttu-id="22d19-151">OneDrive</span><span class="sxs-lookup"><span data-stu-id="22d19-151">OneDrive</span></span>](/onedrive)

- [<span data-ttu-id="22d19-152">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="22d19-152">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

- [<span data-ttu-id="22d19-153">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="22d19-153">Microsoft Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)