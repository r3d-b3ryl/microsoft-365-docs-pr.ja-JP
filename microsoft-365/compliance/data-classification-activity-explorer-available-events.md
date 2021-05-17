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
description: アクティビティ エクスプローラーで使用できるラベル付けアクションの一覧。
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902952"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="f4aaf-103">アクティビティ エクスプローラーで使用できるアクティビティのラベル付け</span><span class="sxs-lookup"><span data-stu-id="f4aaf-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="f4aaf-104">適用される感度ラベル</span><span class="sxs-lookup"><span data-stu-id="f4aaf-104">Sensitivity label applied</span></span>

<span data-ttu-id="f4aaf-105">このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、ラベル付きメールが送信される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-105">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span> 

- <span data-ttu-id="f4aaf-106">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="f4aaf-107">Azure Information Protection アドインで発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="f4aaf-108">ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="f4aaf-109">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-109">Source</span></span>  |<span data-ttu-id="f4aaf-110">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-110">Reported in activity explorer</span></span> | <span data-ttu-id="f4aaf-111">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="f4aaf-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="f4aaf-113">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-113">yes</span></span> |
|<span data-ttu-id="f4aaf-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-114">Outlook</span></span>| <span data-ttu-id="f4aaf-115">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-115">yes</span></span> |<span data-ttu-id="f4aaf-116">From Win 32</span><span class="sxs-lookup"><span data-stu-id="f4aaf-116">from Win 32</span></span> |
|<span data-ttu-id="f4aaf-117">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="f4aaf-118">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-118">yes</span></span> | |
|<span data-ttu-id="f4aaf-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-119">Exchange</span></span>        |<span data-ttu-id="f4aaf-120">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-120">yes</span></span>         | |
|<span data-ttu-id="f4aaf-121">Azure Information Protection (AIP) 統合クライアントと AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="f4aaf-122">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-122">yes</span></span> |<span data-ttu-id="f4aaf-123">AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="f4aaf-124">Microsoft 情報保護 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="f4aaf-125">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-125">yes</span></span>|<span data-ttu-id="f4aaf-126">AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="f4aaf-127">Rights Management Service (RMS)</span><span class="sxs-lookup"><span data-stu-id="f4aaf-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="f4aaf-128">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-128">not applicable</span></span>         | |
|<span data-ttu-id="f4aaf-129">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-129">Power BI desktop and web</span></span>        | <span data-ttu-id="f4aaf-130">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-130">no</span></span>| <span data-ttu-id="f4aaf-131">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="f4aaf-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="f4aaf-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="f4aaf-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="f4aaf-133">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="f4aaf-134">感度ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="f4aaf-134">Sensitivity label changed</span></span>

<span data-ttu-id="f4aaf-135">このイベントは、ドキュメントまたは電子メールでラベルが更新されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-135">This event is generated each time a label is updated on the document or email.</span></span>

- <span data-ttu-id="f4aaf-136">AIP Unified クライアント、Unified Scanner、MIP SDK ソースの場合 *、AIP* アップグレード ラベルとダウングレード ラベル アクションはアクティビティ エクスプローラー ラベルに *マップされます*。 </span><span class="sxs-lookup"><span data-stu-id="f4aaf-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="f4aaf-137">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存の時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="f4aaf-138">Azure Information Protection 統合クライアント アドインとスキャナーの適用で発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="f4aaf-139">ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="f4aaf-140">また *、位置合わせ* テキストは、[オンライン] および [SharePoint] 以外OneDrive。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="f4aaf-141">ファイルの保存/電子メール送信Office前にOutlookされた最後のアクションが収集されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="f4aaf-142">たとえば、ユーザーが送信前にメールのラベルを複数回変更した場合、電子メールの送信時に最後に見つかったラベルは監査ログに記録され、アクティビティ エクスプローラーで報告されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="f4aaf-143">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-143">Source</span></span>  |<span data-ttu-id="f4aaf-144">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-144">Reported in activity explorer</span></span>|<span data-ttu-id="f4aaf-145">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="f4aaf-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-147">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-147">yes</span></span>         |
|<span data-ttu-id="f4aaf-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-148">Outlook</span></span>         |<span data-ttu-id="f4aaf-149">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-149">yes</span></span>         |<span data-ttu-id="f4aaf-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="f4aaf-150">Win 32</span></span>|
|<span data-ttu-id="f4aaf-151">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-152">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-152">yes</span></span>         |
|<span data-ttu-id="f4aaf-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-153">Exchange</span></span>         |<span data-ttu-id="f4aaf-154">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-154">yes</span></span>         |
|<span data-ttu-id="f4aaf-155">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-155">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-156">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-156">yes</span></span>         |
|<span data-ttu-id="f4aaf-157">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-157">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-158">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-158">yes</span></span>         |
|<span data-ttu-id="f4aaf-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-159">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-160">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-160">yes</span></span>         |
|<span data-ttu-id="f4aaf-161">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-161">RMS service</span></span>         |<span data-ttu-id="f4aaf-162">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-162">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-163">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-164">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-164">no</span></span>         |<span data-ttu-id="f4aaf-165">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="f4aaf-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="f4aaf-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-166">MCAS</span></span>     |<span data-ttu-id="f4aaf-167">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="f4aaf-168">[感度ラベルの削除]</span><span class="sxs-lookup"><span data-stu-id="f4aaf-168">Sensitivity label removed</span></span>

<span data-ttu-id="f4aaf-169">このイベントは、ファイルまたはドキュメントからラベルが削除されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-169">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="f4aaf-170">このイベントは、ネイティブ アプリケーションおよび web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="f4aaf-171">Azure Information Protection アドインで発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="f4aaf-172">Outlook では、Office MIP ラベルを使用して、ファイルの保存/電子メール送信アクションの前に生成された最後のラベル付けイベントを収集します。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="f4aaf-173">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-173">Source</span></span>  |<span data-ttu-id="f4aaf-174">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-174">Reported in activity explorer</span></span> | <span data-ttu-id="f4aaf-175">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="f4aaf-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-177">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-177">yes</span></span>         |
|<span data-ttu-id="f4aaf-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-178">Outlook</span></span>         |<span data-ttu-id="f4aaf-179">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-179">yes</span></span>         |<span data-ttu-id="f4aaf-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="f4aaf-180">Win 32</span></span>|
|<span data-ttu-id="f4aaf-181">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-182">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-182">yes</span></span>         |
|<span data-ttu-id="f4aaf-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-183">Exchange</span></span>         |<span data-ttu-id="f4aaf-184">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-184">yes</span></span>         |
|<span data-ttu-id="f4aaf-185">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-185">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-186">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-186">yes</span></span>         |<span data-ttu-id="f4aaf-187">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="f4aaf-188">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-188">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-189">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-189">yes</span></span>         |<span data-ttu-id="f4aaf-190">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="f4aaf-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-191">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-192">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-192">yes</span></span>         |<span data-ttu-id="f4aaf-193">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="f4aaf-194">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-194">RMS service</span></span>         |<span data-ttu-id="f4aaf-195">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-195">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-196">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-197">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-197">no</span></span>         |<span data-ttu-id="f4aaf-198">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="f4aaf-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="f4aaf-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-199">MCAS</span></span>     |<span data-ttu-id="f4aaf-200">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="f4aaf-201">感度ラベル ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="f4aaf-201">Sensitivity label file read</span></span>

<span data-ttu-id="f4aaf-202">このイベントは、ラベル付きまたは保護されたドキュメントが開くごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-202">This event is generated each time a labeled or protected document is opened.</span></span>

|<span data-ttu-id="f4aaf-203">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-203">Source</span></span>  |<span data-ttu-id="f4aaf-204">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-204">Reported in activity explorer</span></span> | <span data-ttu-id="f4aaf-205">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="f4aaf-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-207">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-207">yes</span></span>         |
|<span data-ttu-id="f4aaf-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-208">Outlook</span></span>         |<span data-ttu-id="f4aaf-209">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-209">no</span></span>         |
|<span data-ttu-id="f4aaf-210">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-211">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-211">no</span></span>         |
|<span data-ttu-id="f4aaf-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-212">Exchange</span></span>         |<span data-ttu-id="f4aaf-213">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-213">no</span></span>         |
|<span data-ttu-id="f4aaf-214">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-214">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-215">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-215">yes</span></span>         |<span data-ttu-id="f4aaf-216">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="f4aaf-217">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-217">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-218">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-218">yes</span></span>         |<span data-ttu-id="f4aaf-219">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="f4aaf-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-220">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-221">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-221">yes</span></span>         |<span data-ttu-id="f4aaf-222">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="f4aaf-223">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-223">RMS service</span></span>         |<span data-ttu-id="f4aaf-224">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-224">yes</span></span>         |<span data-ttu-id="f4aaf-225">アクセス *アクションは* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="f4aaf-226">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-227">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-227">no</span></span>         |<span data-ttu-id="f4aaf-228">監査ログでMicrosoft 365アクセス可能</span><span class="sxs-lookup"><span data-stu-id="f4aaf-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="f4aaf-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-229">MCAS</span></span>     |<span data-ttu-id="f4aaf-230">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-230">no</span></span>         |         |


## <a name="sensitivity-label-files-discovered"></a><span data-ttu-id="f4aaf-231">検出された感度ラベル ファイル</span><span class="sxs-lookup"><span data-stu-id="f4aaf-231">Sensitivity label files discovered</span></span>

<span data-ttu-id="f4aaf-232">このイベントは、AIP スキャナーを使用してさまざまな場所で機密データをスキャンし、ファイルを検索するときに、ファイルが検出される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="f4aaf-233">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-233">Source</span></span>  |<span data-ttu-id="f4aaf-234">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-234">Reported in activity explorer</span></span> | <span data-ttu-id="f4aaf-235">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="f4aaf-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-237">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-237">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-238">Outlook</span></span>         |<span data-ttu-id="f4aaf-239">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-239">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-240">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-241">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-241">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-242">Exchange</span></span>         |<span data-ttu-id="f4aaf-243">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-243">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-244">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-244">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-245">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-245">not applicable</span></span>       |
|<span data-ttu-id="f4aaf-246">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-246">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-247">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-247">yes</span></span>         |<span data-ttu-id="f4aaf-248">AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="f4aaf-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-249">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-250">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-250">yes</span></span>         |<span data-ttu-id="f4aaf-251">AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="f4aaf-252">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-252">RMS service</span></span>         |<span data-ttu-id="f4aaf-253">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-253">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-254">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-255">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-255">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-256">MCAS</span></span>     |<span data-ttu-id="f4aaf-257">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="f4aaf-258">名前が変更された感度ラベル ファイル</span><span class="sxs-lookup"><span data-stu-id="f4aaf-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="f4aaf-259">このイベントは、感度ラベルが付いたドキュメントの名前が変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="f4aaf-260">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-260">Source</span></span>  | <span data-ttu-id="f4aaf-261">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-261">Reported in activity explorer</span></span> | <span data-ttu-id="f4aaf-262">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="f4aaf-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-264">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-264">yes</span></span>         |
|<span data-ttu-id="f4aaf-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-265">Outlook</span></span>         |<span data-ttu-id="f4aaf-266">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-266">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-267">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-268">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-268">no</span></span>        |
|<span data-ttu-id="f4aaf-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-269">Exchange</span></span>         |<span data-ttu-id="f4aaf-270">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-270">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-271">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-271">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-272">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-272">no</span></span>         |
|<span data-ttu-id="f4aaf-273">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-273">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-274">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-274">no</span></span>         |
|<span data-ttu-id="f4aaf-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-275">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-276">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-276">no</span></span>         |
|<span data-ttu-id="f4aaf-277">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-277">RMS service</span></span>         |<span data-ttu-id="f4aaf-278">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-278">no</span></span>      |
|<span data-ttu-id="f4aaf-279">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-280">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-280">no</span></span>         |
|<span data-ttu-id="f4aaf-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-281">MCAS</span></span>     |<span data-ttu-id="f4aaf-282">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-282">no</span></span>         |         |


## <a name="sensitivity-label-file-removed"></a><span data-ttu-id="f4aaf-283">感度ラベル ファイルが削除されました</span><span class="sxs-lookup"><span data-stu-id="f4aaf-283">Sensitivity label file removed</span></span>

<span data-ttu-id="f4aaf-284">このイベントは、AIP スキャナーが以前にスキャンしたファイルが削除されたと検出する度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="f4aaf-285">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-285">Source</span></span>  |<span data-ttu-id="f4aaf-286">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-286">Reported in activity explorer</span></span> | <span data-ttu-id="f4aaf-287">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="f4aaf-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-289">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-289">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-290">Outlook</span></span>         |<span data-ttu-id="f4aaf-291">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-291">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-292">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-293">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-293">not applicable</span></span>           |
|<span data-ttu-id="f4aaf-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-294">Exchange</span></span>         |<span data-ttu-id="f4aaf-295">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-295">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-296">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-296">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-297">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-297">not applicable</span></span>            |
|<span data-ttu-id="f4aaf-298">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-298">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-299">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-299">yes</span></span>         |
|<span data-ttu-id="f4aaf-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-300">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-301">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-301">not applicable</span></span>            |
|<span data-ttu-id="f4aaf-302">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-302">RMS service</span></span>         |<span data-ttu-id="f4aaf-303">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-303">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-304">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-305">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-305">not applicable</span></span>  |
|<span data-ttu-id="f4aaf-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-306">MCAS</span></span>     |<span data-ttu-id="f4aaf-307">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-307">not applicable</span></span>        |         |

### <a name="sensitivity-label-protection-applied"></a><span data-ttu-id="f4aaf-308">適用される感度ラベル保護</span><span class="sxs-lookup"><span data-stu-id="f4aaf-308">Sensitivity label protection applied</span></span>

<span data-ttu-id="f4aaf-309">このイベントは、ラベルを持つアイテムに手動で追加される初めての保護が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="f4aaf-310">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-310">Source</span></span>  |<span data-ttu-id="f4aaf-311">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-311">Reported in activity explorer</span></span> | <span data-ttu-id="f4aaf-312">注</span><span class="sxs-lookup"><span data-stu-id="f4aaf-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="f4aaf-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-314">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-314">no</span></span>         |
|<span data-ttu-id="f4aaf-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-315">Outlook</span></span>         |<span data-ttu-id="f4aaf-316">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-316">no</span></span>         |
|<span data-ttu-id="f4aaf-317">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-318">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-318">not applicable</span></span>           |
|<span data-ttu-id="f4aaf-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-319">Exchange</span></span>         |<span data-ttu-id="f4aaf-320">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-320">no</span></span>       |
|<span data-ttu-id="f4aaf-321">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-321">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-322">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-322">yes</span></span>            |
|<span data-ttu-id="f4aaf-323">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-323">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-324">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-324">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-325">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-326">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-326">yes</span></span>            |
|<span data-ttu-id="f4aaf-327">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-327">RMS service</span></span>         |<span data-ttu-id="f4aaf-328">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-328">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-329">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-330">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-330">not applicable</span></span>            |
|<span data-ttu-id="f4aaf-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-331">MCAS</span></span>     |<span data-ttu-id="f4aaf-332">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-332">not applicable</span></span>        |         |

## <a name="sensitivity-label-protection-changed"></a><span data-ttu-id="f4aaf-333">ラベルの保護が変更された</span><span class="sxs-lookup"><span data-stu-id="f4aaf-333">Sensitivity label protection changed</span></span>

<span data-ttu-id="f4aaf-334">このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="f4aaf-335">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-335">Source</span></span>  |<span data-ttu-id="f4aaf-336">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="f4aaf-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-338">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-338">no</span></span>         |
|<span data-ttu-id="f4aaf-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-339">Outlook</span></span>         |<span data-ttu-id="f4aaf-340">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-340">no</span></span>         |
|<span data-ttu-id="f4aaf-341">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-342">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-342">not applicable</span></span>           |
|<span data-ttu-id="f4aaf-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-343">Exchange</span></span>         |<span data-ttu-id="f4aaf-344">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-344">no</span></span>       |
|<span data-ttu-id="f4aaf-345">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-345">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-346">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-346">yes</span></span>            |
|<span data-ttu-id="f4aaf-347">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-347">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-348">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-348">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-349">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-350">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-350">yes</span></span>            |
|<span data-ttu-id="f4aaf-351">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-351">RMS service</span></span>         |<span data-ttu-id="f4aaf-352">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-352">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-353">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-354">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-354">not applicable</span></span>            |
|<span data-ttu-id="f4aaf-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-355">MCAS</span></span>     |<span data-ttu-id="f4aaf-356">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-356">not applicable</span></span>        |

## <a name="sensitivity-label-protection-removed"></a><span data-ttu-id="f4aaf-357">ラベルの保護が削除された</span><span class="sxs-lookup"><span data-stu-id="f4aaf-357">Sensitivity label protection removed</span></span>

<span data-ttu-id="f4aaf-358">このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="f4aaf-359">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-359">Source</span></span>  |<span data-ttu-id="f4aaf-360">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="f4aaf-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f4aaf-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="f4aaf-362">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-362">no</span></span>         |
|<span data-ttu-id="f4aaf-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="f4aaf-363">Outlook</span></span>         |<span data-ttu-id="f4aaf-364">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-364">no</span></span>         |
|<span data-ttu-id="f4aaf-365">SharePointオンライン、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="f4aaf-366">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-366">not applicable</span></span>           |
|<span data-ttu-id="f4aaf-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-367">Exchange</span></span>         |<span data-ttu-id="f4aaf-368">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-368">no</span></span>       |
|<span data-ttu-id="f4aaf-369">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="f4aaf-369">AIP unified client</span></span>         |<span data-ttu-id="f4aaf-370">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-370">yes</span></span>            |
|<span data-ttu-id="f4aaf-371">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-371">AIP unified scanner</span></span>         |<span data-ttu-id="f4aaf-372">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-372">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="f4aaf-373">MIP SDK</span></span>         |<span data-ttu-id="f4aaf-374">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-374">yes</span></span>            |
|<span data-ttu-id="f4aaf-375">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-375">RMS service</span></span>         |<span data-ttu-id="f4aaf-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-376">not applicable</span></span>         |
|<span data-ttu-id="f4aaf-377">Power BIと Web</span><span class="sxs-lookup"><span data-stu-id="f4aaf-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="f4aaf-378">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-378">not applicable</span></span>            |
|<span data-ttu-id="f4aaf-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-379">MCAS</span></span>     |<span data-ttu-id="f4aaf-380">該当なし</span><span class="sxs-lookup"><span data-stu-id="f4aaf-380">not applicable</span></span>        |

## <a name="sensitivity-label-dlp-policy-matched"></a><span data-ttu-id="f4aaf-381">一致した感度ラベル DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="f4aaf-381">Sensitivity label DLP policy matched</span></span>

<span data-ttu-id="f4aaf-382">このイベントは、DLP ポリシーが一致する度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-382">This event is generated each time a DLP policy is matched.</span></span>

|<span data-ttu-id="f4aaf-383">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-383">Source</span></span>  |<span data-ttu-id="f4aaf-384">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="f4aaf-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-385">Exchange</span></span>         |<span data-ttu-id="f4aaf-386">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-386">yes</span></span>       |
|<span data-ttu-id="f4aaf-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4aaf-387">SharePoint Online</span></span>|<span data-ttu-id="f4aaf-388">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-388">yes</span></span>          |
|<span data-ttu-id="f4aaf-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-389">OneDrive</span></span> |<span data-ttu-id="f4aaf-390">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-390">yes</span></span>|
|<span data-ttu-id="f4aaf-391">Teams</span><span class="sxs-lookup"><span data-stu-id="f4aaf-391">Teams</span></span> |<span data-ttu-id="f4aaf-392">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-392">yes</span></span>   |
|<span data-ttu-id="f4aaf-393">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-393">Windows 10 devices</span></span>         |<span data-ttu-id="f4aaf-394">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-394">yes</span></span> |
|<span data-ttu-id="f4aaf-395">MAC</span><span class="sxs-lookup"><span data-stu-id="f4aaf-395">MAC</span></span>         |<span data-ttu-id="f4aaf-396">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-396">no</span></span>     |
|<span data-ttu-id="f4aaf-397">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="f4aaf-397">on-premises</span></span>         |<span data-ttu-id="f4aaf-398">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-398">no</span></span>|
|<span data-ttu-id="f4aaf-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="f4aaf-399">MCAS</span></span>     |<span data-ttu-id="f4aaf-400">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-400">no</span></span>        | 

<span data-ttu-id="f4aaf-401">デバイス (エンドポイント DLP) Windows 10イベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="f4aaf-402">ファイルが削除されました</span><span class="sxs-lookup"><span data-stu-id="f4aaf-402">file deleted</span></span>
- <span data-ttu-id="f4aaf-403">作成されたファイル</span><span class="sxs-lookup"><span data-stu-id="f4aaf-403">file created</span></span>
- <span data-ttu-id="f4aaf-404">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="f4aaf-404">file copied to clipboard</span></span>
- <span data-ttu-id="f4aaf-405">変更されたファイル</span><span class="sxs-lookup"><span data-stu-id="f4aaf-405">file modified</span></span>
- <span data-ttu-id="f4aaf-406">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="f4aaf-406">file read</span></span>
- <span data-ttu-id="f4aaf-407">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="f4aaf-407">file printed</span></span>
- <span data-ttu-id="f4aaf-408">ファイルの名前が変更されました</span><span class="sxs-lookup"><span data-stu-id="f4aaf-408">file renamed</span></span>
- <span data-ttu-id="f4aaf-409">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="f4aaf-409">file copied to network share</span></span>
- <span data-ttu-id="f4aaf-410">許可されていないアプリによってアクセスされるファイル</span><span class="sxs-lookup"><span data-stu-id="f4aaf-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="f4aaf-411">アイテム保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="f4aaf-411">Retention label applied</span></span> 

<span data-ttu-id="f4aaf-412">このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、ラベル付きメールが送信される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-412">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span>

- <span data-ttu-id="f4aaf-413">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-413">It is captured at the time of save in Office native applications and web applications.</span></span>

|<span data-ttu-id="f4aaf-414">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-414">Source</span></span>  |<span data-ttu-id="f4aaf-415">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="f4aaf-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-416">Exchange</span></span>         |<span data-ttu-id="f4aaf-417">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-417">no</span></span>       |
|<span data-ttu-id="f4aaf-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4aaf-418">SharePoint Online</span></span>|<span data-ttu-id="f4aaf-419">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-419">yes</span></span>          |
|<span data-ttu-id="f4aaf-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-420">OneDrive</span></span> |<span data-ttu-id="f4aaf-421">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="f4aaf-422">アイテム保持ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="f4aaf-422">Retention label changed</span></span>

<span data-ttu-id="f4aaf-423">このイベントは、ドキュメントまたは電子メールでラベルが更新されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="f4aaf-424">保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-424">It is captured at the time of save.</span></span>

|<span data-ttu-id="f4aaf-425">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-425">Source</span></span>  |<span data-ttu-id="f4aaf-426">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="f4aaf-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-427">Exchange</span></span>         |<span data-ttu-id="f4aaf-428">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-428">no</span></span>       |
|<span data-ttu-id="f4aaf-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4aaf-429">SharePoint Online</span></span>|<span data-ttu-id="f4aaf-430">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-430">yes</span></span>          |
|<span data-ttu-id="f4aaf-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-431">OneDrive</span></span> |<span data-ttu-id="f4aaf-432">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="f4aaf-433">アイテム保持ラベルの削除</span><span class="sxs-lookup"><span data-stu-id="f4aaf-433">Retention label removed</span></span>

<span data-ttu-id="f4aaf-434">このイベントは、ファイルまたはドキュメントからラベルが削除されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="f4aaf-435">保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-435">It is captured at the time of save.</span></span>

|<span data-ttu-id="f4aaf-436">ソース</span><span class="sxs-lookup"><span data-stu-id="f4aaf-436">Source</span></span>  |<span data-ttu-id="f4aaf-437">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="f4aaf-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="f4aaf-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="f4aaf-438">Exchange</span></span>         |<span data-ttu-id="f4aaf-439">no</span><span class="sxs-lookup"><span data-stu-id="f4aaf-439">no</span></span>       |
|<span data-ttu-id="f4aaf-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4aaf-440">SharePoint Online</span></span>|<span data-ttu-id="f4aaf-441">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-441">yes</span></span>          |
|<span data-ttu-id="f4aaf-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f4aaf-442">OneDrive</span></span> |<span data-ttu-id="f4aaf-443">はい</span><span class="sxs-lookup"><span data-stu-id="f4aaf-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="f4aaf-444">既知の問題</span><span class="sxs-lookup"><span data-stu-id="f4aaf-444">Known issues</span></span>
  
- <span data-ttu-id="f4aaf-445">推奨ラベル ツール ヒントがエンド ユーザーに表示されている場合、そのヒントはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="f4aaf-446">ただし、ユーザーが推奨ラベルの適用を選択した場合、ラベルは [適用方法] フィールドの下に [推奨]*として表示\*\*されます。*</span><span class="sxs-lookup"><span data-stu-id="f4aaf-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="f4aaf-447">現在、位置合わせテキストは、Sharepoint および Sharepoint および OneDrive からの感度ラベルのダウングレードでは使用OneDrive。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="f4aaf-448">現在、機密情報の種類は、Word、Excel、PowerPoint、Outlook、および SharePoint Online、および OneDrive からの自動ラベル付けアクティビティでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f4aaf-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
