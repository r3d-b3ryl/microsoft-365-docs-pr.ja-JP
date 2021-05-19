---
title: アクティビティ エクスプローラーで報告されたラベル付けアクション
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: アクティビティ エクスプローラーで使用できるラベル付けアクティビティの一覧。
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532256"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="2e386-103">アクティビティ エクスプローラーで使用できるアクティビティのラベル付け</span><span class="sxs-lookup"><span data-stu-id="2e386-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="2e386-104">適用される感度ラベル</span><span class="sxs-lookup"><span data-stu-id="2e386-104">Sensitivity label applied</span></span>

<span data-ttu-id="2e386-105">このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、電子メールが感度ラベル付きで送信されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="2e386-106">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="2e386-107">Azure Information Protection アドインで発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="2e386-108">ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e386-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="2e386-109">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-109">Source</span></span>  |<span data-ttu-id="2e386-110">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-110">Reported in activity explorer</span></span> | <span data-ttu-id="2e386-111">注</span><span class="sxs-lookup"><span data-stu-id="2e386-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="2e386-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="2e386-113">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-113">yes</span></span> |
|<span data-ttu-id="2e386-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-114">Outlook</span></span>| <span data-ttu-id="2e386-115">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-115">yes</span></span> |<span data-ttu-id="2e386-116">From Win 32</span><span class="sxs-lookup"><span data-stu-id="2e386-116">from Win 32</span></span> |
|<span data-ttu-id="2e386-117">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="2e386-118">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-118">yes</span></span> | |
|<span data-ttu-id="2e386-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-119">Exchange</span></span>        |<span data-ttu-id="2e386-120">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-120">yes</span></span>         | |
|<span data-ttu-id="2e386-121">Azure Information Protection (AIP) 統合クライアントと AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="2e386-122">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-122">yes</span></span> |<span data-ttu-id="2e386-123">AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="2e386-124">Microsoft 情報保護 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="2e386-125">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-125">yes</span></span>|<span data-ttu-id="2e386-126">AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="2e386-127">Rights Management Service (RMS)</span><span class="sxs-lookup"><span data-stu-id="2e386-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="2e386-128">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-128">not applicable</span></span>         | |
|<span data-ttu-id="2e386-129">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-129">Power BI desktop and web</span></span>        | <span data-ttu-id="2e386-130">no</span><span class="sxs-lookup"><span data-stu-id="2e386-130">no</span></span>| <span data-ttu-id="2e386-131">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="2e386-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="2e386-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="2e386-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="2e386-133">no</span><span class="sxs-lookup"><span data-stu-id="2e386-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="2e386-134">感度ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="2e386-134">Sensitivity label changed</span></span>

<span data-ttu-id="2e386-135">このイベントは、ドキュメントまたは電子メールで感度ラベルが更新されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="2e386-136">AIP Unified クライアント、Unified Scanner、MIP SDK ソースの場合 *、AIP* アップグレード ラベルとダウングレード ラベル アクションはアクティビティ エクスプローラー ラベルに *マップされます*。 </span><span class="sxs-lookup"><span data-stu-id="2e386-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="2e386-137">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存の時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="2e386-138">Azure Information Protection 統合クライアント アドインとスキャナーの適用で発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="2e386-139">ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e386-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="2e386-140">また *、位置合わせ* テキストは、[オンライン] および [SharePoint] 以外OneDrive。</span><span class="sxs-lookup"><span data-stu-id="2e386-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="2e386-141">ファイルの保存/電子メール送信Office前にOutlookされた最後のアクションが収集されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="2e386-142">たとえば、ユーザーが送信前にメールのラベルを複数回変更した場合、電子メールの送信時に最後に見つかったラベルは監査ログに記録され、アクティビティ エクスプローラーで報告されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="2e386-143">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-143">Source</span></span>  |<span data-ttu-id="2e386-144">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-144">Reported in activity explorer</span></span>|<span data-ttu-id="2e386-145">注</span><span class="sxs-lookup"><span data-stu-id="2e386-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2e386-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-147">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-147">yes</span></span>         |
|<span data-ttu-id="2e386-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-148">Outlook</span></span>         |<span data-ttu-id="2e386-149">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-149">yes</span></span>         |<span data-ttu-id="2e386-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="2e386-150">Win 32</span></span>|
|<span data-ttu-id="2e386-151">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-152">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-152">yes</span></span>         |
|<span data-ttu-id="2e386-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-153">Exchange</span></span>         |<span data-ttu-id="2e386-154">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-154">yes</span></span>         |
|<span data-ttu-id="2e386-155">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-155">AIP unified client</span></span>         |<span data-ttu-id="2e386-156">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-156">yes</span></span>         |
|<span data-ttu-id="2e386-157">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-157">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-158">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-158">yes</span></span>         |
|<span data-ttu-id="2e386-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-159">MIP SDK</span></span>         |<span data-ttu-id="2e386-160">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-160">yes</span></span>         |
|<span data-ttu-id="2e386-161">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-161">RMS service</span></span>         |<span data-ttu-id="2e386-162">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-162">not applicable</span></span>         |
|<span data-ttu-id="2e386-163">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-164">no</span><span class="sxs-lookup"><span data-stu-id="2e386-164">no</span></span>         |<span data-ttu-id="2e386-165">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="2e386-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="2e386-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-166">MCAS</span></span>     |<span data-ttu-id="2e386-167">no</span><span class="sxs-lookup"><span data-stu-id="2e386-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="2e386-168">[感度ラベルの削除]</span><span class="sxs-lookup"><span data-stu-id="2e386-168">Sensitivity label removed</span></span>

<span data-ttu-id="2e386-169">このイベントは、ファイルまたはドキュメントから感度ラベルが削除されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="2e386-170">このイベントは、ネイティブ アプリケーションおよび web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="2e386-171">Azure Information Protection アドインで発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="2e386-172">Outlook では、Office MIP ラベルを使用して、ファイルの保存/電子メール送信アクションの前に生成された最後のラベル付けイベントを収集します。</span><span class="sxs-lookup"><span data-stu-id="2e386-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="2e386-173">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-173">Source</span></span>  |<span data-ttu-id="2e386-174">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-174">Reported in activity explorer</span></span> | <span data-ttu-id="2e386-175">注</span><span class="sxs-lookup"><span data-stu-id="2e386-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2e386-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-177">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-177">yes</span></span>         |
|<span data-ttu-id="2e386-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-178">Outlook</span></span>         |<span data-ttu-id="2e386-179">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-179">yes</span></span>         |<span data-ttu-id="2e386-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="2e386-180">Win 32</span></span>|
|<span data-ttu-id="2e386-181">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-182">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-182">yes</span></span>         |
|<span data-ttu-id="2e386-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-183">Exchange</span></span>         |<span data-ttu-id="2e386-184">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-184">yes</span></span>         |
|<span data-ttu-id="2e386-185">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-185">AIP unified client</span></span>         |<span data-ttu-id="2e386-186">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-186">yes</span></span>         |<span data-ttu-id="2e386-187">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="2e386-188">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-188">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-189">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-189">yes</span></span>         |<span data-ttu-id="2e386-190">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="2e386-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-191">MIP SDK</span></span>         |<span data-ttu-id="2e386-192">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-192">yes</span></span>         |<span data-ttu-id="2e386-193">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="2e386-194">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-194">RMS service</span></span>         |<span data-ttu-id="2e386-195">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-195">not applicable</span></span>         |
|<span data-ttu-id="2e386-196">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-197">no</span><span class="sxs-lookup"><span data-stu-id="2e386-197">no</span></span>         |<span data-ttu-id="2e386-198">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="2e386-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="2e386-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-199">MCAS</span></span>     |<span data-ttu-id="2e386-200">no</span><span class="sxs-lookup"><span data-stu-id="2e386-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="2e386-201">感度ラベル ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="2e386-201">Sensitivity label file read</span></span>

<span data-ttu-id="2e386-202">このイベントは、ラベル付きまたは保護されたドキュメントが開く度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="2e386-203">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-203">Source</span></span>  |<span data-ttu-id="2e386-204">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-204">Reported in activity explorer</span></span> | <span data-ttu-id="2e386-205">注</span><span class="sxs-lookup"><span data-stu-id="2e386-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2e386-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-207">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-207">yes</span></span>         |
|<span data-ttu-id="2e386-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-208">Outlook</span></span>         |<span data-ttu-id="2e386-209">no</span><span class="sxs-lookup"><span data-stu-id="2e386-209">no</span></span>         |
|<span data-ttu-id="2e386-210">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-211">no</span><span class="sxs-lookup"><span data-stu-id="2e386-211">no</span></span>         |
|<span data-ttu-id="2e386-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-212">Exchange</span></span>         |<span data-ttu-id="2e386-213">no</span><span class="sxs-lookup"><span data-stu-id="2e386-213">no</span></span>         |
|<span data-ttu-id="2e386-214">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-214">AIP unified client</span></span>         |<span data-ttu-id="2e386-215">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-215">yes</span></span>         |<span data-ttu-id="2e386-216">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="2e386-217">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-217">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-218">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-218">yes</span></span>         |<span data-ttu-id="2e386-219">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="2e386-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-220">MIP SDK</span></span>         |<span data-ttu-id="2e386-221">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-221">yes</span></span>         |<span data-ttu-id="2e386-222">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="2e386-223">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-223">RMS service</span></span>         |<span data-ttu-id="2e386-224">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-224">yes</span></span>         |<span data-ttu-id="2e386-225">アクセス *アクションは* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="2e386-226">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-227">no</span><span class="sxs-lookup"><span data-stu-id="2e386-227">no</span></span>         |<span data-ttu-id="2e386-228">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="2e386-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="2e386-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-229">MCAS</span></span>     |<span data-ttu-id="2e386-230">no</span><span class="sxs-lookup"><span data-stu-id="2e386-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="2e386-231">検出されたファイル</span><span class="sxs-lookup"><span data-stu-id="2e386-231">Files discovered</span></span>

<span data-ttu-id="2e386-232">このイベントは、AIP スキャナーを使用してさまざまな場所で機密データをスキャンし、ファイルを検索するときに、ファイルが検出される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="2e386-233">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-233">Source</span></span>  |<span data-ttu-id="2e386-234">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-234">Reported in activity explorer</span></span> | <span data-ttu-id="2e386-235">注</span><span class="sxs-lookup"><span data-stu-id="2e386-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2e386-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-237">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-237">not applicable</span></span>         |
|<span data-ttu-id="2e386-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-238">Outlook</span></span>         |<span data-ttu-id="2e386-239">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-239">not applicable</span></span>         |
|<span data-ttu-id="2e386-240">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-241">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-241">not applicable</span></span>         |
|<span data-ttu-id="2e386-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-242">Exchange</span></span>         |<span data-ttu-id="2e386-243">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-243">not applicable</span></span>         |
|<span data-ttu-id="2e386-244">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-244">AIP unified client</span></span>         |<span data-ttu-id="2e386-245">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-245">not applicable</span></span>       |
|<span data-ttu-id="2e386-246">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-246">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-247">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-247">yes</span></span>         |<span data-ttu-id="2e386-248">AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="2e386-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-249">MIP SDK</span></span>         |<span data-ttu-id="2e386-250">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-250">yes</span></span>         |<span data-ttu-id="2e386-251">AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="2e386-252">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-252">RMS service</span></span>         |<span data-ttu-id="2e386-253">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-253">not applicable</span></span>         |
|<span data-ttu-id="2e386-254">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-255">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-255">not applicable</span></span>         |
|<span data-ttu-id="2e386-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-256">MCAS</span></span>     |<span data-ttu-id="2e386-257">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="2e386-258">名前が変更された感度ラベル ファイル</span><span class="sxs-lookup"><span data-stu-id="2e386-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="2e386-259">このイベントは、感度ラベルが付いたドキュメントの名前が変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="2e386-260">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-260">Source</span></span>  | <span data-ttu-id="2e386-261">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-261">Reported in activity explorer</span></span> | <span data-ttu-id="2e386-262">注</span><span class="sxs-lookup"><span data-stu-id="2e386-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2e386-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-264">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-264">yes</span></span>         |
|<span data-ttu-id="2e386-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-265">Outlook</span></span>         |<span data-ttu-id="2e386-266">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-266">not applicable</span></span>         |
|<span data-ttu-id="2e386-267">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-268">no</span><span class="sxs-lookup"><span data-stu-id="2e386-268">no</span></span>        |
|<span data-ttu-id="2e386-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-269">Exchange</span></span>         |<span data-ttu-id="2e386-270">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-270">not applicable</span></span>         |
|<span data-ttu-id="2e386-271">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-271">AIP unified client</span></span>         |<span data-ttu-id="2e386-272">no</span><span class="sxs-lookup"><span data-stu-id="2e386-272">no</span></span>         |
|<span data-ttu-id="2e386-273">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-273">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-274">no</span><span class="sxs-lookup"><span data-stu-id="2e386-274">no</span></span>         |
|<span data-ttu-id="2e386-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-275">MIP SDK</span></span>         |<span data-ttu-id="2e386-276">no</span><span class="sxs-lookup"><span data-stu-id="2e386-276">no</span></span>         |
|<span data-ttu-id="2e386-277">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-277">RMS service</span></span>         |<span data-ttu-id="2e386-278">no</span><span class="sxs-lookup"><span data-stu-id="2e386-278">no</span></span>      |
|<span data-ttu-id="2e386-279">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-280">no</span><span class="sxs-lookup"><span data-stu-id="2e386-280">no</span></span>         |
|<span data-ttu-id="2e386-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-281">MCAS</span></span>     |<span data-ttu-id="2e386-282">no</span><span class="sxs-lookup"><span data-stu-id="2e386-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="2e386-283">削除されたファイル</span><span class="sxs-lookup"><span data-stu-id="2e386-283">File removed</span></span>

<span data-ttu-id="2e386-284">このイベントは、AIP スキャナーが以前にスキャンしたファイルが削除されたと検出する度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="2e386-285">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-285">Source</span></span>  |<span data-ttu-id="2e386-286">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-286">Reported in activity explorer</span></span> | <span data-ttu-id="2e386-287">注</span><span class="sxs-lookup"><span data-stu-id="2e386-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2e386-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-289">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-289">not applicable</span></span>         |
|<span data-ttu-id="2e386-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-290">Outlook</span></span>         |<span data-ttu-id="2e386-291">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-291">not applicable</span></span>         |
|<span data-ttu-id="2e386-292">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-293">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-293">not applicable</span></span>           |
|<span data-ttu-id="2e386-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-294">Exchange</span></span>         |<span data-ttu-id="2e386-295">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-295">not applicable</span></span>         |
|<span data-ttu-id="2e386-296">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-296">AIP unified client</span></span>         |<span data-ttu-id="2e386-297">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-297">not applicable</span></span>            |
|<span data-ttu-id="2e386-298">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-298">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-299">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-299">yes</span></span>         |
|<span data-ttu-id="2e386-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-300">MIP SDK</span></span>         |<span data-ttu-id="2e386-301">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-301">not applicable</span></span>            |
|<span data-ttu-id="2e386-302">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-302">RMS service</span></span>         |<span data-ttu-id="2e386-303">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-303">not applicable</span></span>         |
|<span data-ttu-id="2e386-304">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-305">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-305">not applicable</span></span>  |
|<span data-ttu-id="2e386-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-306">MCAS</span></span>     |<span data-ttu-id="2e386-307">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="2e386-308">適用される保護</span><span class="sxs-lookup"><span data-stu-id="2e386-308">Protection applied</span></span>

<span data-ttu-id="2e386-309">このイベントは、ラベルを持つアイテムに手動で追加される初めての保護が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="2e386-310">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-310">Source</span></span>  |<span data-ttu-id="2e386-311">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-311">Reported in activity explorer</span></span> | <span data-ttu-id="2e386-312">注</span><span class="sxs-lookup"><span data-stu-id="2e386-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="2e386-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-314">no</span><span class="sxs-lookup"><span data-stu-id="2e386-314">no</span></span>         |
|<span data-ttu-id="2e386-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-315">Outlook</span></span>         |<span data-ttu-id="2e386-316">no</span><span class="sxs-lookup"><span data-stu-id="2e386-316">no</span></span>         |
|<span data-ttu-id="2e386-317">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-318">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-318">not applicable</span></span>           |
|<span data-ttu-id="2e386-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-319">Exchange</span></span>         |<span data-ttu-id="2e386-320">no</span><span class="sxs-lookup"><span data-stu-id="2e386-320">no</span></span>       |
|<span data-ttu-id="2e386-321">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-321">AIP unified client</span></span>         |<span data-ttu-id="2e386-322">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-322">yes</span></span>            |
|<span data-ttu-id="2e386-323">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-323">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-324">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-324">not applicable</span></span>         |
|<span data-ttu-id="2e386-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-325">MIP SDK</span></span>         |<span data-ttu-id="2e386-326">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-326">yes</span></span>            |
|<span data-ttu-id="2e386-327">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-327">RMS service</span></span>         |<span data-ttu-id="2e386-328">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-328">not applicable</span></span>         |
|<span data-ttu-id="2e386-329">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-330">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-330">not applicable</span></span>            |
|<span data-ttu-id="2e386-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-331">MCAS</span></span>     |<span data-ttu-id="2e386-332">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="2e386-333">保護の変更</span><span class="sxs-lookup"><span data-stu-id="2e386-333">Protection changed</span></span>

<span data-ttu-id="2e386-334">このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="2e386-335">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-335">Source</span></span>  |<span data-ttu-id="2e386-336">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2e386-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-338">no</span><span class="sxs-lookup"><span data-stu-id="2e386-338">no</span></span>         |
|<span data-ttu-id="2e386-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-339">Outlook</span></span>         |<span data-ttu-id="2e386-340">no</span><span class="sxs-lookup"><span data-stu-id="2e386-340">no</span></span>         |
|<span data-ttu-id="2e386-341">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-342">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-342">not applicable</span></span>           |
|<span data-ttu-id="2e386-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-343">Exchange</span></span>         |<span data-ttu-id="2e386-344">no</span><span class="sxs-lookup"><span data-stu-id="2e386-344">no</span></span>       |
|<span data-ttu-id="2e386-345">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-345">AIP unified client</span></span>         |<span data-ttu-id="2e386-346">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-346">yes</span></span>            |
|<span data-ttu-id="2e386-347">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-347">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-348">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-348">not applicable</span></span>         |
|<span data-ttu-id="2e386-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-349">MIP SDK</span></span>         |<span data-ttu-id="2e386-350">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-350">yes</span></span>            |
|<span data-ttu-id="2e386-351">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-351">RMS service</span></span>         |<span data-ttu-id="2e386-352">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-352">not applicable</span></span>         |
|<span data-ttu-id="2e386-353">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-354">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-354">not applicable</span></span>            |
|<span data-ttu-id="2e386-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-355">MCAS</span></span>     |<span data-ttu-id="2e386-356">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="2e386-357">保護が削除されました</span><span class="sxs-lookup"><span data-stu-id="2e386-357">Protection removed</span></span>

<span data-ttu-id="2e386-358">このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="2e386-359">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-359">Source</span></span>  |<span data-ttu-id="2e386-360">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2e386-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2e386-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="2e386-362">no</span><span class="sxs-lookup"><span data-stu-id="2e386-362">no</span></span>         |
|<span data-ttu-id="2e386-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="2e386-363">Outlook</span></span>         |<span data-ttu-id="2e386-364">no</span><span class="sxs-lookup"><span data-stu-id="2e386-364">no</span></span>         |
|<span data-ttu-id="2e386-365">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="2e386-366">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-366">not applicable</span></span>           |
|<span data-ttu-id="2e386-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-367">Exchange</span></span>         |<span data-ttu-id="2e386-368">no</span><span class="sxs-lookup"><span data-stu-id="2e386-368">no</span></span>       |
|<span data-ttu-id="2e386-369">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="2e386-369">AIP unified client</span></span>         |<span data-ttu-id="2e386-370">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-370">yes</span></span>            |
|<span data-ttu-id="2e386-371">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="2e386-371">AIP unified scanner</span></span>         |<span data-ttu-id="2e386-372">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-372">not applicable</span></span>         |
|<span data-ttu-id="2e386-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="2e386-373">MIP SDK</span></span>         |<span data-ttu-id="2e386-374">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-374">yes</span></span>            |
|<span data-ttu-id="2e386-375">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="2e386-375">RMS service</span></span>         |<span data-ttu-id="2e386-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-376">not applicable</span></span>         |
|<span data-ttu-id="2e386-377">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="2e386-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="2e386-378">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-378">not applicable</span></span>            |
|<span data-ttu-id="2e386-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-379">MCAS</span></span>     |<span data-ttu-id="2e386-380">該当なし</span><span class="sxs-lookup"><span data-stu-id="2e386-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="2e386-381">DLP ポリシーの一致</span><span class="sxs-lookup"><span data-stu-id="2e386-381">DLP policy matched</span></span>

<span data-ttu-id="2e386-382">このイベントは、ドキュメントまたは電子メールで DLP ポリシーが一致する度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="2e386-383">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-383">Source</span></span>  |<span data-ttu-id="2e386-384">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2e386-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-385">Exchange</span></span>         |<span data-ttu-id="2e386-386">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-386">yes</span></span>       |
|<span data-ttu-id="2e386-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2e386-387">SharePoint Online</span></span>|<span data-ttu-id="2e386-388">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-388">yes</span></span>          |
|<span data-ttu-id="2e386-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-389">OneDrive</span></span> |<span data-ttu-id="2e386-390">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-390">yes</span></span>|
|<span data-ttu-id="2e386-391">Teams</span><span class="sxs-lookup"><span data-stu-id="2e386-391">Teams</span></span> |<span data-ttu-id="2e386-392">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-392">yes</span></span>   |
|<span data-ttu-id="2e386-393">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="2e386-393">Windows 10 devices</span></span>         |<span data-ttu-id="2e386-394">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-394">yes</span></span> |
|<span data-ttu-id="2e386-395">MAC</span><span class="sxs-lookup"><span data-stu-id="2e386-395">MAC</span></span>         |<span data-ttu-id="2e386-396">no</span><span class="sxs-lookup"><span data-stu-id="2e386-396">no</span></span>     |
|<span data-ttu-id="2e386-397">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="2e386-397">on-premises</span></span>         |<span data-ttu-id="2e386-398">no</span><span class="sxs-lookup"><span data-stu-id="2e386-398">no</span></span>|
|<span data-ttu-id="2e386-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="2e386-399">MCAS</span></span>     |<span data-ttu-id="2e386-400">no</span><span class="sxs-lookup"><span data-stu-id="2e386-400">no</span></span>        | 

<span data-ttu-id="2e386-401">デバイス (エンドポイント DLP) Windows 10イベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e386-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="2e386-402">ファイルが削除されました</span><span class="sxs-lookup"><span data-stu-id="2e386-402">file deleted</span></span>
- <span data-ttu-id="2e386-403">作成されたファイル</span><span class="sxs-lookup"><span data-stu-id="2e386-403">file created</span></span>
- <span data-ttu-id="2e386-404">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="2e386-404">file copied to clipboard</span></span>
- <span data-ttu-id="2e386-405">変更されたファイル</span><span class="sxs-lookup"><span data-stu-id="2e386-405">file modified</span></span>
- <span data-ttu-id="2e386-406">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="2e386-406">file read</span></span>
- <span data-ttu-id="2e386-407">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="2e386-407">file printed</span></span>
- <span data-ttu-id="2e386-408">ファイルの名前が変更されました</span><span class="sxs-lookup"><span data-stu-id="2e386-408">file renamed</span></span>
- <span data-ttu-id="2e386-409">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="2e386-409">file copied to network share</span></span>
- <span data-ttu-id="2e386-410">許可されていないアプリによってアクセスされるファイル</span><span class="sxs-lookup"><span data-stu-id="2e386-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="2e386-411">アイテム保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="2e386-411">Retention label applied</span></span> 

<span data-ttu-id="2e386-412">このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、保持ラベル付きメールが送信されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="2e386-413">ドキュメントの保存時と電子メールの送信時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="2e386-414">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-414">Source</span></span>  |<span data-ttu-id="2e386-415">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2e386-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-416">Exchange</span></span>         |<span data-ttu-id="2e386-417">no</span><span class="sxs-lookup"><span data-stu-id="2e386-417">no</span></span>       |
|<span data-ttu-id="2e386-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2e386-418">SharePoint Online</span></span>|<span data-ttu-id="2e386-419">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-419">yes</span></span>          |
|<span data-ttu-id="2e386-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-420">OneDrive</span></span> |<span data-ttu-id="2e386-421">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="2e386-422">アイテム保持ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="2e386-422">Retention label changed</span></span>

<span data-ttu-id="2e386-423">このイベントは、ドキュメントまたは電子メールでラベルが更新されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="2e386-424">ドキュメントの保存時と電子メールの送信時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="2e386-425">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-425">Source</span></span>  |<span data-ttu-id="2e386-426">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2e386-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-427">Exchange</span></span>         |<span data-ttu-id="2e386-428">no</span><span class="sxs-lookup"><span data-stu-id="2e386-428">no</span></span>       |
|<span data-ttu-id="2e386-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2e386-429">SharePoint Online</span></span>|<span data-ttu-id="2e386-430">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-430">yes</span></span>          |
|<span data-ttu-id="2e386-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-431">OneDrive</span></span> |<span data-ttu-id="2e386-432">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="2e386-433">アイテム保持ラベルの削除</span><span class="sxs-lookup"><span data-stu-id="2e386-433">Retention label removed</span></span>

<span data-ttu-id="2e386-434">このイベントは、ファイルまたはドキュメントからラベルが削除されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="2e386-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="2e386-435">ドキュメントの保存時と電子メールの送信時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e386-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="2e386-436">ソース</span><span class="sxs-lookup"><span data-stu-id="2e386-436">Source</span></span>  |<span data-ttu-id="2e386-437">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="2e386-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="2e386-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="2e386-438">Exchange</span></span>         |<span data-ttu-id="2e386-439">no</span><span class="sxs-lookup"><span data-stu-id="2e386-439">no</span></span>       |
|<span data-ttu-id="2e386-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2e386-440">SharePoint Online</span></span>|<span data-ttu-id="2e386-441">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-441">yes</span></span>          |
|<span data-ttu-id="2e386-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2e386-442">OneDrive</span></span> |<span data-ttu-id="2e386-443">はい</span><span class="sxs-lookup"><span data-stu-id="2e386-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="2e386-444">既知の問題</span><span class="sxs-lookup"><span data-stu-id="2e386-444">Known issues</span></span>
  
- <span data-ttu-id="2e386-445">推奨ラベル ツール ヒントがエンド ユーザーに表示されている場合、そのヒントはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="2e386-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="2e386-446">ただし、ユーザーが推奨ラベルの適用を選択した場合、ラベルは [適用方法] フィールドの下に [推奨]*として表示\*\*されます。*</span><span class="sxs-lookup"><span data-stu-id="2e386-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="2e386-447">現在、位置合わせテキストは、Sharepoint および Sharepoint および OneDrive からの感度ラベルのダウングレードでは使用OneDrive。</span><span class="sxs-lookup"><span data-stu-id="2e386-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="2e386-448">現在、機密情報の種類は、Word、Excel、PowerPoint、Outlook、および SharePoint Online、および OneDrive からの自動ラベル付けアクティビティでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2e386-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
