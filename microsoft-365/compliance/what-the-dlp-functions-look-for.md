---
title: 数据丢失防护（DLP）函数查找的内容
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解数据丢失防护（DLP）函数的查找内容。
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536307"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="d0d03-103">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="d0d03-103">What the DLP functions look for</span></span>

<span data-ttu-id="d0d03-104">数据丢失防护（DLP）包括敏感信息类型，如信用卡号和欧盟借记卡号，可供您在 DLP 策略中使用。</span><span class="sxs-lookup"><span data-stu-id="d0d03-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="d0d03-105">这些敏感信息类型查找特定模式，并通过确保正确的格式设置、强制校验和来查找相关的关键字或其他信息来 corroborate。</span><span class="sxs-lookup"><span data-stu-id="d0d03-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="d0d03-106">其中一些功能是由内部函数执行的。</span><span class="sxs-lookup"><span data-stu-id="d0d03-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="d0d03-107">例如，信用卡号敏感信息类型使用函数查找类似于到期日期的日期，以帮助 corroborate 号码是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="d0d03-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="d0d03-108">本文介绍了这些函数查找的内容，以帮助您了解预定义的敏感信息类型的工作原理。</span><span class="sxs-lookup"><span data-stu-id="d0d03-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="d0d03-109">有关详细信息，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="d0d03-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="d0d03-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="d0d03-110">Func_us_date</span></span>

<span data-ttu-id="d0d03-111">此函数以美国常用格式查找日期这包括格式 "月/日/年"、"月-日-年" 和 "年月日"。</span><span class="sxs-lookup"><span data-stu-id="d0d03-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="d0d03-112">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d0d03-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="d0d03-113">示例：</span><span class="sxs-lookup"><span data-stu-id="d0d03-113">Examples:</span></span>
  
- <span data-ttu-id="d0d03-114">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="d0d03-114">December 2, 2016</span></span>
    
- <span data-ttu-id="d0d03-115">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="d0d03-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="d0d03-116">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-116">dec 02 2016</span></span>
    
- <span data-ttu-id="d0d03-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-117">12/2/2016</span></span>
    
- <span data-ttu-id="d0d03-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="d0d03-118">12/02/16</span></span>
    
- <span data-ttu-id="d0d03-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="d0d03-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="d0d03-120">12-2-16</span></span>
    
<span data-ttu-id="d0d03-121">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="d0d03-121">Accepted month names:</span></span>
  
- <span data-ttu-id="d0d03-122">English</span><span class="sxs-lookup"><span data-stu-id="d0d03-122">English</span></span>
    
  - <span data-ttu-id="d0d03-123">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="d0d03-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d0d03-124">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="d0d03-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="d0d03-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="d0d03-125">Func_eu_date</span></span>

<span data-ttu-id="d0d03-126">此函数查找欧盟常用格式的日期</span><span class="sxs-lookup"><span data-stu-id="d0d03-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="d0d03-127">（以及美国以外的大多数位置），例如 "日/月/年"、"日-月-年" 和 "月年"。</span><span class="sxs-lookup"><span data-stu-id="d0d03-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="d0d03-128">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d0d03-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="d0d03-129">示例：</span><span class="sxs-lookup"><span data-stu-id="d0d03-129">Examples:</span></span>
  
- <span data-ttu-id="d0d03-130">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="d0d03-131">02年12月2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-131">02 dec 2016</span></span>
    
- <span data-ttu-id="d0d03-132">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="d0d03-132">2 Dec 16</span></span>
    
- <span data-ttu-id="d0d03-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-133">2/12/2016</span></span>
    
- <span data-ttu-id="d0d03-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d0d03-134">02/12/16</span></span>
    
- <span data-ttu-id="d0d03-135">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="d0d03-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="d0d03-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d0d03-136">2-12-16</span></span>
    
<span data-ttu-id="d0d03-137">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="d0d03-137">Accepted month names:</span></span>
  
- <span data-ttu-id="d0d03-138">English</span><span class="sxs-lookup"><span data-stu-id="d0d03-138">English</span></span>
    
  - <span data-ttu-id="d0d03-139">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="d0d03-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d0d03-140">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="d0d03-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="d0d03-141">荷兰语</span><span class="sxs-lookup"><span data-stu-id="d0d03-141">Dutch</span></span>
    
  - <span data-ttu-id="d0d03-142">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="d0d03-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="d0d03-143">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="d0d03-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="d0d03-144">法语</span><span class="sxs-lookup"><span data-stu-id="d0d03-144">French</span></span>
    
  - <span data-ttu-id="d0d03-145">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="d0d03-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="d0d03-146">janv.</span><span class="sxs-lookup"><span data-stu-id="d0d03-146">janv.</span></span> <span data-ttu-id="d0d03-147">févr.</span><span class="sxs-lookup"><span data-stu-id="d0d03-147">févr.</span></span> <span data-ttu-id="d0d03-148">火星 avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="d0d03-148">mars avril mai juin juil.</span></span> <span data-ttu-id="d0d03-149">août 9 月。</span><span class="sxs-lookup"><span data-stu-id="d0d03-149">août sept.</span></span> <span data-ttu-id="d0d03-150">2008.</span><span class="sxs-lookup"><span data-stu-id="d0d03-150">oct.</span></span> <span data-ttu-id="d0d03-151">年11月.</span><span class="sxs-lookup"><span data-stu-id="d0d03-151">nov.</span></span> <span data-ttu-id="d0d03-152">déc.</span><span class="sxs-lookup"><span data-stu-id="d0d03-152">déc.</span></span>
    
- <span data-ttu-id="d0d03-153">德语</span><span class="sxs-lookup"><span data-stu-id="d0d03-153">German</span></span>
    
  - <span data-ttu-id="d0d03-154">jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember</span><span class="sxs-lookup"><span data-stu-id="d0d03-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="d0d03-155">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="d0d03-155">Jan./Jän.</span></span> <span data-ttu-id="d0d03-156">2003年 März 年4月 Juni Juli，Okt。</span><span class="sxs-lookup"><span data-stu-id="d0d03-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="d0d03-157">Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="d0d03-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="d0d03-158">意大利语</span><span class="sxs-lookup"><span data-stu-id="d0d03-158">Italian</span></span>
    
  - <span data-ttu-id="d0d03-159">gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="d0d03-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="d0d03-160">genn.</span><span class="sxs-lookup"><span data-stu-id="d0d03-160">genn.</span></span> <span data-ttu-id="d0d03-161">febbr.</span><span class="sxs-lookup"><span data-stu-id="d0d03-161">febbr.</span></span> <span data-ttu-id="d0d03-162">mar.</span><span class="sxs-lookup"><span data-stu-id="d0d03-162">mar.</span></span> <span data-ttu-id="d0d03-163">四月.</span><span class="sxs-lookup"><span data-stu-id="d0d03-163">apr.</span></span> <span data-ttu-id="d0d03-164">magg.</span><span class="sxs-lookup"><span data-stu-id="d0d03-164">magg.</span></span> <span data-ttu-id="d0d03-165">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="d0d03-165">giugno luglio ag.</span></span> <span data-ttu-id="d0d03-166">设置.</span><span class="sxs-lookup"><span data-stu-id="d0d03-166">sett.</span></span> <span data-ttu-id="d0d03-167">ott.</span><span class="sxs-lookup"><span data-stu-id="d0d03-167">ott.</span></span> <span data-ttu-id="d0d03-168">年11月.</span><span class="sxs-lookup"><span data-stu-id="d0d03-168">nov.</span></span> <span data-ttu-id="d0d03-169">home.dic.</span><span class="sxs-lookup"><span data-stu-id="d0d03-169">dic.</span></span>
    
- <span data-ttu-id="d0d03-170">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="d0d03-170">Portuguese</span></span>
    
  - <span data-ttu-id="d0d03-171">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="d0d03-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="d0d03-172">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="d0d03-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="d0d03-173">西班牙语</span><span class="sxs-lookup"><span data-stu-id="d0d03-173">Spanish</span></span>
    
  - <span data-ttu-id="d0d03-174">enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="d0d03-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="d0d03-175">enero 2003 年2月。</span><span class="sxs-lookup"><span data-stu-id="d0d03-175">enero feb.</span></span> <span data-ttu-id="d0d03-176">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="d0d03-176">marzo abr.</span></span> <span data-ttu-id="d0d03-177">mayo 06。</span><span class="sxs-lookup"><span data-stu-id="d0d03-177">mayo jun.</span></span> <span data-ttu-id="d0d03-178">年7月.</span><span class="sxs-lookup"><span data-stu-id="d0d03-178">jul.</span></span> <span data-ttu-id="d0d03-179">agosto/set。</span><span class="sxs-lookup"><span data-stu-id="d0d03-179">agosto sept./set.</span></span> <span data-ttu-id="d0d03-180">2008.</span><span class="sxs-lookup"><span data-stu-id="d0d03-180">oct.</span></span> <span data-ttu-id="d0d03-181">年11月.</span><span class="sxs-lookup"><span data-stu-id="d0d03-181">nov.</span></span> <span data-ttu-id="d0d03-182">home.dic.</span><span class="sxs-lookup"><span data-stu-id="d0d03-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="d0d03-183">Func_eu_date1 （已弃用）</span><span class="sxs-lookup"><span data-stu-id="d0d03-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="d0d03-184">此函数已被弃用，因为它仅支持包含在上述函数中的葡萄牙月名称 `Func_eu_date` 。</span><span class="sxs-lookup"><span data-stu-id="d0d03-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="d0d03-185">此函数使用葡萄牙语中常用的格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="d0d03-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="d0d03-186">此函数的格式与 `Func_eu_date` 使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="d0d03-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="d0d03-187">示例：</span><span class="sxs-lookup"><span data-stu-id="d0d03-187">Examples:</span></span>
  
- <span data-ttu-id="d0d03-188">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="d0d03-189">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-189">02 dez 2016</span></span>
    
- <span data-ttu-id="d0d03-190">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="d0d03-190">2 Dez 16</span></span>
    
- <span data-ttu-id="d0d03-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-191">2/12/2016</span></span>
    
- <span data-ttu-id="d0d03-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d0d03-192">02/12/16</span></span>
    
- <span data-ttu-id="d0d03-193">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="d0d03-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d0d03-194">2-12-16</span></span>
    
<span data-ttu-id="d0d03-195">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="d0d03-195">Accepted month names:</span></span>
  
- <span data-ttu-id="d0d03-196">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="d0d03-196">Portuguese</span></span>
    
  - <span data-ttu-id="d0d03-197">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="d0d03-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="d0d03-198">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="d0d03-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="d0d03-199">Func_eu_date2 （已弃用）</span><span class="sxs-lookup"><span data-stu-id="d0d03-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="d0d03-200">此函数已被弃用，因为它仅支持荷兰月份名称，这些名称现在包含在 `Func_eu_date` 上述函数中。</span><span class="sxs-lookup"><span data-stu-id="d0d03-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="d0d03-201">此函数查找在荷兰语中常用的格式的日期。</span><span class="sxs-lookup"><span data-stu-id="d0d03-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="d0d03-202">此函数的格式与 `Func_eu_date` 使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="d0d03-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="d0d03-203">示例：</span><span class="sxs-lookup"><span data-stu-id="d0d03-203">Examples:</span></span>
  
- <span data-ttu-id="d0d03-204">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="d0d03-205">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-205">02 mei 2016</span></span>
    
- <span data-ttu-id="d0d03-206">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="d0d03-206">2 Mei 16</span></span>
    
- <span data-ttu-id="d0d03-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-207">2/12/2016</span></span>
    
- <span data-ttu-id="d0d03-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d0d03-208">02/12/16</span></span>
    
- <span data-ttu-id="d0d03-209">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="d0d03-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="d0d03-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d0d03-210">2-12-16</span></span>
    
<span data-ttu-id="d0d03-211">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="d0d03-211">Accepted month names:</span></span>
  
- <span data-ttu-id="d0d03-212">荷兰语</span><span class="sxs-lookup"><span data-stu-id="d0d03-212">Dutch</span></span>
    
  - <span data-ttu-id="d0d03-213">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="d0d03-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="d0d03-214">2004年1月1月 maart 日 mei 日09月8日，okt 年11月9日</span><span class="sxs-lookup"><span data-stu-id="d0d03-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="d0d03-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="d0d03-215">Func_expiration_date</span></span>

<span data-ttu-id="d0d03-216">此函数查找信用卡和借记卡常用格式的日期，其中不包括月份的天数。</span><span class="sxs-lookup"><span data-stu-id="d0d03-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="d0d03-217">此函数将以 "月/年"、"月-年"、"[月 name] year" 和 "[月缩写] 年" 的格式匹配日期。</span><span class="sxs-lookup"><span data-stu-id="d0d03-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="d0d03-218">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d0d03-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="d0d03-219">示例：</span><span class="sxs-lookup"><span data-stu-id="d0d03-219">Examples:</span></span>
  
- <span data-ttu-id="d0d03-220">MM/YY--例如，01/11 或1/11</span><span class="sxs-lookup"><span data-stu-id="d0d03-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="d0d03-221">MM/YYYY--例如，01/2011 或1/2011</span><span class="sxs-lookup"><span data-stu-id="d0d03-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="d0d03-222">MM-YY--例如，01-22 或1-11</span><span class="sxs-lookup"><span data-stu-id="d0d03-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="d0d03-223">MM--例如，01-2000 或1-2000</span><span class="sxs-lookup"><span data-stu-id="d0d03-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="d0d03-224">以下格式支持 YY 或 YYYY：</span><span class="sxs-lookup"><span data-stu-id="d0d03-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="d0d03-225">年月日--例如 Jan-2010 或一月-2010 或 Jan-10 或一月-10</span><span class="sxs-lookup"><span data-stu-id="d0d03-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="d0d03-226">年月日-例如，"一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="d0d03-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="d0d03-227">MonthYYYY-例如，"january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"</span><span class="sxs-lookup"><span data-stu-id="d0d03-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="d0d03-228">Month/YYYY-例如，"一月/2010" 或 "Jan/2010" 或 "一月/10" 或 "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="d0d03-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="d0d03-229">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="d0d03-229">Accepted month names:</span></span>
  
- <span data-ttu-id="d0d03-230">English</span><span class="sxs-lookup"><span data-stu-id="d0d03-230">English</span></span>
    
  - <span data-ttu-id="d0d03-231">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="d0d03-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d0d03-232">2004年2月3月4月5月8日12月8月8日</span><span class="sxs-lookup"><span data-stu-id="d0d03-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="d0d03-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="d0d03-233">Func_us_address</span></span>

<span data-ttu-id="d0d03-234">此函数查找美国的状态名称或邮政缩写，后跟有效的邮政编码，就像在邮政地址中使用一样。</span><span class="sxs-lookup"><span data-stu-id="d0d03-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="d0d03-235">邮政编码必须是与美国省/市/自治区名称或缩写相关联的正确邮政编码之一。</span><span class="sxs-lookup"><span data-stu-id="d0d03-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="d0d03-236">美国省/市/自治区名称和邮政编码不能由标点符号或字母分隔。</span><span class="sxs-lookup"><span data-stu-id="d0d03-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="d0d03-237">示例：</span><span class="sxs-lookup"><span data-stu-id="d0d03-237">Examples:</span></span>
  
- <span data-ttu-id="d0d03-238">华盛顿98052</span><span class="sxs-lookup"><span data-stu-id="d0d03-238">Washington 98052</span></span>
    
- <span data-ttu-id="d0d03-239">华盛顿98052-9998</span><span class="sxs-lookup"><span data-stu-id="d0d03-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="d0d03-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="d0d03-240">WA 98052</span></span>
    
- <span data-ttu-id="d0d03-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="d0d03-241">WA 98052-9998</span></span>
    

