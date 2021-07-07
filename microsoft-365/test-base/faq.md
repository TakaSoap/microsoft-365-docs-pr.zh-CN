---
title: 测试基础常见问题解答
description: 查看常见问题
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322675"
---
# <a name="test-base-faq"></a><span data-ttu-id="3ab7d-103">测试基础常见问题解答</span><span class="sxs-lookup"><span data-stu-id="3ab7d-103">Test Base FAQ</span></span>

<span data-ttu-id="3ab7d-104">**问：如何将程序包提交到测试基础团队？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="3ab7d-105">**答：** 使用自助门户将程序包直接提交到测试基础环境。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="3ab7d-106">若要提交应用程序包，请导航到 [Azure](https://www.aka.ms/testbaseportal "测试基本主页") 门户，然后通过自助式测试基础门户仪表板上传包含应用程序二进制文件、依赖项和测试脚本的压缩文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="3ab7d-107">有关详细信息，请参阅载入用户指南，或联系我们的团队 <testbasepreview@microsoft.com> 获取帮助和详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="3ab7d-108">**问：OOB 测试 (开箱) 是什么？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="3ab7d-109">**答：** 开箱即用 OOB (测试) 标准化的默认测试运行，安装、启动和关闭应用程序包 30 (30 次) 卸载。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="3ab7d-110">为测试库创建的程序包将具有以下测试脚本：安装、启动、关闭和（可选）卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="3ab7d-111">开箱即用 OOB (测试) 应用程序上的标准化遥测，以跨内部版本Windows比较。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="3ab7d-112">**问：我们能否在安装、启动、关闭、卸载测试脚本 () 外部提交测试？。**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="3ab7d-113">**答：** 是的，客户还可以通过自助服务门户仪表板上载用于功能测试的应用程序包。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="3ab7d-114">**功能** 测试是使客户能够执行其脚本以在应用程序上运行自定义功能的测试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="3ab7d-115">测试</span><span class="sxs-lookup"><span data-stu-id="3ab7d-115">Testing</span></span>

<span data-ttu-id="3ab7d-116">**问：是否支持功能测试？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="3ab7d-117">**答：** 是，测试库支持功能测试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="3ab7d-118">功能测试是使我们的客户能够执行其脚本以在应用程序上运行自定义功能的测试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="3ab7d-119">若要提交应用程序包进行功能测试，只需通过自助服务门户仪表板上载包含应用程序二进制文件、依赖项和测试脚本的压缩文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="3ab7d-120">有关详细信息，请参阅载入用户指南，或联系我们的团队 <testbasepreview@microsoft.com> 获取帮助和详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="3ab7d-121">**问：测试基础如何处理我们的测试数据？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="3ab7d-122">**答：** 测试库安全地收集和管理 Azure 环境上的测试数据。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="3ab7d-123">**问：测试基础能否支持我们的自动测试？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="3ab7d-124">是的，测试库支持自动测试，但由于服务功能，目前不支持手动测试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="3ab7d-125">**问：你支持哪些语言和自动测试框架？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="3ab7d-126">**答：** 我们支持所有语言和框架。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="3ab7d-127">我们通过 PowerShell 调用所有脚本。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="3ab7d-128">你还需要提供 (上传) 所需框架的从属二进制文件。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="3ab7d-129">**问：测试基础多久提供测试结果？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="3ab7d-130">**答：** 对于针对预发布版本运行的每个测试，我们将在 48 小时内在 Azure 门户仪表板 [上提供](https://www.aka.ms/testbaseportal "测试基本主页") 结果。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="3ab7d-131">**问：能否在安装后重新启动？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="3ab7d-132">**答：** 是的，我们的过程支持在安装后重新启动。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="3ab7d-133">在载入门户上设置任务时，请务必从"可选设置"下拉列表中选择此选项。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="3ab7d-134">对于开箱即用 (OOB) 测试，您可以指定安装脚本是否需要 _重新启动。_</span><span class="sxs-lookup"><span data-stu-id="3ab7d-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![重新启动图片](Media/reboot.png)

<span data-ttu-id="3ab7d-136">对于功能测试，你可以指定添加的每个脚本是否需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![如何选择功能测试](Media/functionalreboot.png)

<span data-ttu-id="3ab7d-138">**问：Windows支持哪些版本？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="3ab7d-139">**答：** 我们目前Windows 10支持 Windows 10、Windows Server 2016、Windows Server 2016 Core 版本、Windows Server 2019 和 Windows Server 2019 Core 版本。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="3ab7d-140">**问：安全更新测试与功能更新测试之间有什么区别？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="3ab7d-141">**答：** 对于安全更新测试，我们针对每月预发布 **<ins></ins>** 安全更新进行测试Windows这些更新侧重于确保我们的用户始终安全和保护。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="3ab7d-142">对于功能更新测试，我们针对两年一次预发布 **<ins>功能</ins>** 更新进行测试，这些更新引入了新特性Windows。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="3ab7d-143">调试选项</span><span class="sxs-lookup"><span data-stu-id="3ab7d-143">Debugging options</span></span>

<span data-ttu-id="3ab7d-144">**问：在出现故障时，我们 (虚拟机) 虚拟机？测试基础共享是什么？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="3ab7d-145">**答：** 若要使服务合规且预发布更新是安全的，只有 Microsoft 可以访问 VM。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="3ab7d-146">但是，客户可以在门户仪表板上查看测试结果和其他测试指标，包括崩溃和挂起信号、可靠性指标、内存和 CPU 使用率等。我们还在仪表板上生成并提供测试运行的日志，以便下载和进一步分析。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="3ab7d-147">我们还可以根据需要提供用于崩溃调试的内存转储。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="3ab7d-148">**问：如果在测试过程中发现问题，那么解决这些问题的下一步是什么？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="3ab7d-149">**答：** 测试基础团队将执行初始会审过程以确定错误的根本原因，然后根据我们的结果，我们将路由至 Microsoft 内的客户或内部团队进行调试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="3ab7d-150">我们始终与客户密切合作，共同解决任何问题。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="3ab7d-151">**问：在问题解决之前，Microsoft 是否保留安全修补程序的发布？哪些备用分辨率可用？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="3ab7d-152">**答：** 测试基础的目标是确保我们的联合最终客户不会面临任何问题。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="3ab7d-153">我们将与软件供应商一起努力在发布之前解决任何问题，但如果修复不可行，我们还有其他解决方案，如填充码和块。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="3ab7d-154">其他</span><span class="sxs-lookup"><span data-stu-id="3ab7d-154">Miscellaneous</span></span>

<span data-ttu-id="3ab7d-155">**问：该服务如何与内部服务器一起运行？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="3ab7d-156">**答：** 我们目前不提供对地服务器的支持。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="3ab7d-157">但是，如果服务器公开 HTTP 终结点，我们可以通过 Internet 连接到它。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="3ab7d-158">**问：Who托管 VM？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="3ab7d-159">**答：** Microsoft 设置此服务的 VM，从客户处获得执行此操作的负载。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="3ab7d-160">**问：此服务是否支持 Web、移动或桌面应用程序？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="3ab7d-161">**答：** 目前，我们侧重于桌面应用程序，但是，我们计划将来载入 Web 应用程序，但我们目前不支持移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="3ab7d-162">**问：测试基础与 SUVP 之间有什么区别？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="3ab7d-163">**答：** 测试基础与 SUVP 之间的最大差异是，我们的合作伙伴将他们的应用程序载入测试基础 Azure 环境，以针对预发布更新运行验证，而不是自行执行测试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="3ab7d-164">除了预发布安全更新测试之外，我们还支持在平台上进行预发布功能更新测试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="3ab7d-165">我们的路线图中有很多其他类型的更新和操作系统测试。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="3ab7d-166">**问：服务是否有相关成本？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="3ab7d-167">**答：** 测试基础服务将免费向用户提供，直到通用 (GA) 。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="3ab7d-168">此时，我们将宣布一个成本结构，该结构将作用于所有客户。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="3ab7d-169">**问：如何提供有关测试基础的反馈？**</span><span class="sxs-lookup"><span data-stu-id="3ab7d-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="3ab7d-170">**答：** 若要共享有关测试基础的反馈，请选择门户左下角的反馈图标。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="3ab7d-171">在提交内容中包括屏幕截图，以帮助 Microsoft 更好地了解你的反馈。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="3ab7d-172">还可以提交产品建议，并可在 上对其他想法进行选择 <testbasepreview@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="3ab7d-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
