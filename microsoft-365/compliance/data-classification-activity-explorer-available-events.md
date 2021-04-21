---
title: アクティビティ エクスプローラーで報告されたアクションのラベル付け
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
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="749c2-103">アクティビティ エクスプローラーで使用できるアクティビティのラベル付け</span><span class="sxs-lookup"><span data-stu-id="749c2-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="749c2-104">適用される感度ラベル</span><span class="sxs-lookup"><span data-stu-id="749c2-104">Sensitivity label applied</span></span>

<span data-ttu-id="749c2-105">このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、ラベル付きメールが送信される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-105">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span> 

- <span data-ttu-id="749c2-106">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="749c2-107">Azure Information Protection アドインで発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="749c2-108">ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="749c2-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="749c2-109">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-109">Source</span></span>  |<span data-ttu-id="749c2-110">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-110">Reported in activity explorer</span></span> | <span data-ttu-id="749c2-111">注</span><span class="sxs-lookup"><span data-stu-id="749c2-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="749c2-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="749c2-113">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-113">yes</span></span> |
|<span data-ttu-id="749c2-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-114">Outlook</span></span>| <span data-ttu-id="749c2-115">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-115">yes</span></span> |<span data-ttu-id="749c2-116">From Win 32</span><span class="sxs-lookup"><span data-stu-id="749c2-116">from Win 32</span></span> |
|<span data-ttu-id="749c2-117">SharePoint online, OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="749c2-118">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-118">yes</span></span> | |
|<span data-ttu-id="749c2-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-119">Exchange</span></span>        |<span data-ttu-id="749c2-120">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-120">yes</span></span>         | |
|<span data-ttu-id="749c2-121">Azure Information Protection (AIP) 統合クライアントと AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="749c2-122">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-122">yes</span></span> |<span data-ttu-id="749c2-123">AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="749c2-124">Microsoft 情報保護 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="749c2-125">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-125">yes</span></span>|<span data-ttu-id="749c2-126">AIP の *新しいラベル* アクションは、アクティビティ エクスプローラー *に適用されるラベル* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="749c2-127">Rights Management Service (RMS)</span><span class="sxs-lookup"><span data-stu-id="749c2-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="749c2-128">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-128">not applicable</span></span>         | |
|<span data-ttu-id="749c2-129">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-129">Power BI desktop and web</span></span>        | <span data-ttu-id="749c2-130">no</span><span class="sxs-lookup"><span data-stu-id="749c2-130">no</span></span>| <span data-ttu-id="749c2-131">Microsoft 365 監査ログでアクセス可能</span><span class="sxs-lookup"><span data-stu-id="749c2-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="749c2-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="749c2-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="749c2-133">no</span><span class="sxs-lookup"><span data-stu-id="749c2-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="749c2-134">感度ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="749c2-134">Sensitivity label changed</span></span>

<span data-ttu-id="749c2-135">このイベントは、ドキュメントまたは電子メールでラベルが更新されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-135">This event is generated each time a label is updated on the document or email.</span></span>

- <span data-ttu-id="749c2-136">AIP Unified クライアント、Unified Scanner、MIP SDK ソースの場合 *、AIP* アップグレード ラベルとダウングレード ラベル アクションはアクティビティ エクスプローラー ラベルに *マップされます*。 </span><span class="sxs-lookup"><span data-stu-id="749c2-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="749c2-137">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存の時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="749c2-138">Azure Information Protection 統合クライアント アドインとスキャナーの適用で発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="749c2-139">ラベルのアップグレードとダウングレードのアクションは、[ *ラベル* イベントの種類] フィールドとフィルターを使用して監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="749c2-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="749c2-140">また *、SharePoint* Online と OneDrive 以外の位置合わせテキストもキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="749c2-141">Outlook のネイティブ アプリで行Officeのラベル付けは、ファイルの保存/電子メール送信アクションの前に生成された最後のアクションを収集します。</span><span class="sxs-lookup"><span data-stu-id="749c2-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="749c2-142">たとえば、ユーザーが送信前にメールのラベルを複数回変更した場合、電子メールの送信時に最後に見つかったラベルは監査ログに記録され、アクティビティ エクスプローラーで報告されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="749c2-143">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-143">Source</span></span>  |<span data-ttu-id="749c2-144">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-144">Reported in activity explorer</span></span>|<span data-ttu-id="749c2-145">注</span><span class="sxs-lookup"><span data-stu-id="749c2-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="749c2-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-147">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-147">yes</span></span>         |
|<span data-ttu-id="749c2-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-148">Outlook</span></span>         |<span data-ttu-id="749c2-149">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-149">yes</span></span>         |<span data-ttu-id="749c2-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="749c2-150">Win 32</span></span>|
|<span data-ttu-id="749c2-151">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-152">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-152">yes</span></span>         |
|<span data-ttu-id="749c2-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-153">Exchange</span></span>         |<span data-ttu-id="749c2-154">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-154">yes</span></span>         |
|<span data-ttu-id="749c2-155">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-155">AIP unified client</span></span>         |<span data-ttu-id="749c2-156">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-156">yes</span></span>         |
|<span data-ttu-id="749c2-157">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-157">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-158">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-158">yes</span></span>         |
|<span data-ttu-id="749c2-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-159">MIP SDK</span></span>         |<span data-ttu-id="749c2-160">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-160">yes</span></span>         |
|<span data-ttu-id="749c2-161">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-161">RMS service</span></span>         |<span data-ttu-id="749c2-162">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-162">not applicable</span></span>         |
|<span data-ttu-id="749c2-163">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-164">no</span><span class="sxs-lookup"><span data-stu-id="749c2-164">no</span></span>         |<span data-ttu-id="749c2-165">Microsoft 365 監査ログでアクセス可能</span><span class="sxs-lookup"><span data-stu-id="749c2-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="749c2-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-166">MCAS</span></span>     |<span data-ttu-id="749c2-167">no</span><span class="sxs-lookup"><span data-stu-id="749c2-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="749c2-168">[感度ラベルの削除]</span><span class="sxs-lookup"><span data-stu-id="749c2-168">Sensitivity label removed</span></span>

<span data-ttu-id="749c2-169">このイベントは、ファイルまたはドキュメントからラベルが削除されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-169">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="749c2-170">このイベントは、ネイティブ アプリケーションおよび web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="749c2-171">Azure Information Protection アドインで発生した時点でキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="749c2-172">Outlook では、Office MIP ラベルを使用して、ファイルの保存/電子メール送信アクションの前に生成された最後のラベル付けイベントが収集されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="749c2-173">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-173">Source</span></span>  |<span data-ttu-id="749c2-174">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-174">Reported in activity explorer</span></span> | <span data-ttu-id="749c2-175">注</span><span class="sxs-lookup"><span data-stu-id="749c2-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="749c2-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-177">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-177">yes</span></span>         |
|<span data-ttu-id="749c2-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-178">Outlook</span></span>         |<span data-ttu-id="749c2-179">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-179">yes</span></span>         |<span data-ttu-id="749c2-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="749c2-180">Win 32</span></span>|
|<span data-ttu-id="749c2-181">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-182">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-182">yes</span></span>         |
|<span data-ttu-id="749c2-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-183">Exchange</span></span>         |<span data-ttu-id="749c2-184">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-184">yes</span></span>         |
|<span data-ttu-id="749c2-185">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-185">AIP unified client</span></span>         |<span data-ttu-id="749c2-186">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-186">yes</span></span>         |<span data-ttu-id="749c2-187">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="749c2-188">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-188">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-189">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-189">yes</span></span>         |<span data-ttu-id="749c2-190">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="749c2-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-191">MIP SDK</span></span>         |<span data-ttu-id="749c2-192">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-192">yes</span></span>         |<span data-ttu-id="749c2-193">AIP *削除ラベル アクション* は、アクティビティ エクスプローラーの *ラベル削除アクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="749c2-194">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-194">RMS service</span></span>         |<span data-ttu-id="749c2-195">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-195">not applicable</span></span>         |
|<span data-ttu-id="749c2-196">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-197">no</span><span class="sxs-lookup"><span data-stu-id="749c2-197">no</span></span>         |<span data-ttu-id="749c2-198">Microsoft 365 監査ログでアクセス可能</span><span class="sxs-lookup"><span data-stu-id="749c2-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="749c2-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-199">MCAS</span></span>     |<span data-ttu-id="749c2-200">no</span><span class="sxs-lookup"><span data-stu-id="749c2-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="749c2-201">感度ラベル ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="749c2-201">Sensitivity label file read</span></span>

<span data-ttu-id="749c2-202">このイベントは、ラベル付きまたは保護されたドキュメントが開くごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-202">This event is generated each time a labeled or protected document is opened.</span></span>

|<span data-ttu-id="749c2-203">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-203">Source</span></span>  |<span data-ttu-id="749c2-204">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-204">Reported in activity explorer</span></span> | <span data-ttu-id="749c2-205">注</span><span class="sxs-lookup"><span data-stu-id="749c2-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="749c2-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-207">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-207">yes</span></span>         |
|<span data-ttu-id="749c2-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-208">Outlook</span></span>         |<span data-ttu-id="749c2-209">no</span><span class="sxs-lookup"><span data-stu-id="749c2-209">no</span></span>         |
|<span data-ttu-id="749c2-210">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-211">no</span><span class="sxs-lookup"><span data-stu-id="749c2-211">no</span></span>         |
|<span data-ttu-id="749c2-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-212">Exchange</span></span>         |<span data-ttu-id="749c2-213">no</span><span class="sxs-lookup"><span data-stu-id="749c2-213">no</span></span>         |
|<span data-ttu-id="749c2-214">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-214">AIP unified client</span></span>         |<span data-ttu-id="749c2-215">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-215">yes</span></span>         |<span data-ttu-id="749c2-216">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="749c2-217">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-217">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-218">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-218">yes</span></span>         |<span data-ttu-id="749c2-219">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="749c2-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-220">MIP SDK</span></span>         |<span data-ttu-id="749c2-221">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-221">yes</span></span>         |<span data-ttu-id="749c2-222">AIP アクセス アクション *は* 、アクティビティ エクスプローラーの *ファイル読み取り* アクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="749c2-223">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-223">RMS service</span></span>         |<span data-ttu-id="749c2-224">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-224">yes</span></span>         |<span data-ttu-id="749c2-225">アクセス *アクションは* 、アクティビティ エクスプローラーの *ファイル読み取* りアクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="749c2-226">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-227">no</span><span class="sxs-lookup"><span data-stu-id="749c2-227">no</span></span>         |<span data-ttu-id="749c2-228">Microsoft 365 監査ログでアクセス可能</span><span class="sxs-lookup"><span data-stu-id="749c2-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="749c2-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-229">MCAS</span></span>     |<span data-ttu-id="749c2-230">no</span><span class="sxs-lookup"><span data-stu-id="749c2-230">no</span></span>         |         |


## <a name="sensitivity-label-files-discovered"></a><span data-ttu-id="749c2-231">検出された感度ラベル ファイル</span><span class="sxs-lookup"><span data-stu-id="749c2-231">Sensitivity label files discovered</span></span>

<span data-ttu-id="749c2-232">このイベントは、AIP スキャナーを使用してさまざまな場所で機密データをスキャンし、ファイルを検索するときに、ファイルが検出される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="749c2-233">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-233">Source</span></span>  |<span data-ttu-id="749c2-234">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-234">Reported in activity explorer</span></span> | <span data-ttu-id="749c2-235">注</span><span class="sxs-lookup"><span data-stu-id="749c2-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="749c2-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-237">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-237">not applicable</span></span>         |
|<span data-ttu-id="749c2-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-238">Outlook</span></span>         |<span data-ttu-id="749c2-239">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-239">not applicable</span></span>         |
|<span data-ttu-id="749c2-240">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-241">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-241">not applicable</span></span>         |
|<span data-ttu-id="749c2-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-242">Exchange</span></span>         |<span data-ttu-id="749c2-243">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-243">not applicable</span></span>         |
|<span data-ttu-id="749c2-244">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-244">AIP unified client</span></span>         |<span data-ttu-id="749c2-245">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-245">not applicable</span></span>       |
|<span data-ttu-id="749c2-246">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-246">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-247">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-247">yes</span></span>         |<span data-ttu-id="749c2-248">AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="749c2-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-249">MIP SDK</span></span>         |<span data-ttu-id="749c2-250">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-250">yes</span></span>         |<span data-ttu-id="749c2-251">AIP 検出 *アクション* は、アクティビティ エクスプローラーで検出 *されたファイルアクション* にマップされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="749c2-252">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-252">RMS service</span></span>         |<span data-ttu-id="749c2-253">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-253">not applicable</span></span>         |
|<span data-ttu-id="749c2-254">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-255">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-255">not applicable</span></span>         |
|<span data-ttu-id="749c2-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-256">MCAS</span></span>     |<span data-ttu-id="749c2-257">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="749c2-258">名前が変更された感度ラベル ファイル</span><span class="sxs-lookup"><span data-stu-id="749c2-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="749c2-259">このイベントは、感度ラベルが付いたドキュメントの名前が変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="749c2-260">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-260">Source</span></span>  | <span data-ttu-id="749c2-261">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-261">Reported in activity explorer</span></span> | <span data-ttu-id="749c2-262">注</span><span class="sxs-lookup"><span data-stu-id="749c2-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="749c2-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-264">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-264">yes</span></span>         |
|<span data-ttu-id="749c2-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-265">Outlook</span></span>         |<span data-ttu-id="749c2-266">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-266">not applicable</span></span>         |
|<span data-ttu-id="749c2-267">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-268">no</span><span class="sxs-lookup"><span data-stu-id="749c2-268">no</span></span>        |
|<span data-ttu-id="749c2-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-269">Exchange</span></span>         |<span data-ttu-id="749c2-270">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-270">not applicable</span></span>         |
|<span data-ttu-id="749c2-271">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-271">AIP unified client</span></span>         |<span data-ttu-id="749c2-272">no</span><span class="sxs-lookup"><span data-stu-id="749c2-272">no</span></span>         |
|<span data-ttu-id="749c2-273">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-273">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-274">no</span><span class="sxs-lookup"><span data-stu-id="749c2-274">no</span></span>         |
|<span data-ttu-id="749c2-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-275">MIP SDK</span></span>         |<span data-ttu-id="749c2-276">no</span><span class="sxs-lookup"><span data-stu-id="749c2-276">no</span></span>         |
|<span data-ttu-id="749c2-277">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-277">RMS service</span></span>         |<span data-ttu-id="749c2-278">no</span><span class="sxs-lookup"><span data-stu-id="749c2-278">no</span></span>      |
|<span data-ttu-id="749c2-279">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-280">no</span><span class="sxs-lookup"><span data-stu-id="749c2-280">no</span></span>         |
|<span data-ttu-id="749c2-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-281">MCAS</span></span>     |<span data-ttu-id="749c2-282">no</span><span class="sxs-lookup"><span data-stu-id="749c2-282">no</span></span>         |         |


## <a name="sensitivity-label-file-removed"></a><span data-ttu-id="749c2-283">感度ラベル ファイルが削除されました</span><span class="sxs-lookup"><span data-stu-id="749c2-283">Sensitivity label file removed</span></span>

<span data-ttu-id="749c2-284">このイベントは、AIP スキャナーが以前にスキャンしたファイルが削除されたと検出する度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="749c2-285">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-285">Source</span></span>  |<span data-ttu-id="749c2-286">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-286">Reported in activity explorer</span></span> | <span data-ttu-id="749c2-287">注</span><span class="sxs-lookup"><span data-stu-id="749c2-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="749c2-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-289">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-289">not applicable</span></span>         |
|<span data-ttu-id="749c2-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-290">Outlook</span></span>         |<span data-ttu-id="749c2-291">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-291">not applicable</span></span>         |
|<span data-ttu-id="749c2-292">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-293">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-293">not applicable</span></span>           |
|<span data-ttu-id="749c2-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-294">Exchange</span></span>         |<span data-ttu-id="749c2-295">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-295">not applicable</span></span>         |
|<span data-ttu-id="749c2-296">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-296">AIP unified client</span></span>         |<span data-ttu-id="749c2-297">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-297">not applicable</span></span>            |
|<span data-ttu-id="749c2-298">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-298">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-299">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-299">yes</span></span>         |
|<span data-ttu-id="749c2-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-300">MIP SDK</span></span>         |<span data-ttu-id="749c2-301">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-301">not applicable</span></span>            |
|<span data-ttu-id="749c2-302">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-302">RMS service</span></span>         |<span data-ttu-id="749c2-303">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-303">not applicable</span></span>         |
|<span data-ttu-id="749c2-304">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-305">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-305">not applicable</span></span>  |
|<span data-ttu-id="749c2-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-306">MCAS</span></span>     |<span data-ttu-id="749c2-307">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-307">not applicable</span></span>        |         |

### <a name="sensitivity-label-protection-applied"></a><span data-ttu-id="749c2-308">適用される感度ラベル保護</span><span class="sxs-lookup"><span data-stu-id="749c2-308">Sensitivity label protection applied</span></span>

<span data-ttu-id="749c2-309">このイベントは、ラベルを持つアイテムに手動で追加される初めての保護が生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="749c2-310">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-310">Source</span></span>  |<span data-ttu-id="749c2-311">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-311">Reported in activity explorer</span></span> | <span data-ttu-id="749c2-312">注</span><span class="sxs-lookup"><span data-stu-id="749c2-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="749c2-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-314">no</span><span class="sxs-lookup"><span data-stu-id="749c2-314">no</span></span>         |
|<span data-ttu-id="749c2-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-315">Outlook</span></span>         |<span data-ttu-id="749c2-316">no</span><span class="sxs-lookup"><span data-stu-id="749c2-316">no</span></span>         |
|<span data-ttu-id="749c2-317">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-318">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-318">not applicable</span></span>           |
|<span data-ttu-id="749c2-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-319">Exchange</span></span>         |<span data-ttu-id="749c2-320">no</span><span class="sxs-lookup"><span data-stu-id="749c2-320">no</span></span>       |
|<span data-ttu-id="749c2-321">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-321">AIP unified client</span></span>         |<span data-ttu-id="749c2-322">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-322">yes</span></span>            |
|<span data-ttu-id="749c2-323">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-323">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-324">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-324">not applicable</span></span>         |
|<span data-ttu-id="749c2-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-325">MIP SDK</span></span>         |<span data-ttu-id="749c2-326">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-326">yes</span></span>            |
|<span data-ttu-id="749c2-327">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-327">RMS service</span></span>         |<span data-ttu-id="749c2-328">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-328">not applicable</span></span>         |
|<span data-ttu-id="749c2-329">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-330">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-330">not applicable</span></span>            |
|<span data-ttu-id="749c2-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-331">MCAS</span></span>     |<span data-ttu-id="749c2-332">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-332">not applicable</span></span>        |         |

## <a name="sensitivity-label-protection-changed"></a><span data-ttu-id="749c2-333">ラベルの保護が変更された</span><span class="sxs-lookup"><span data-stu-id="749c2-333">Sensitivity label protection changed</span></span>

<span data-ttu-id="749c2-334">このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="749c2-335">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-335">Source</span></span>  |<span data-ttu-id="749c2-336">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="749c2-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-338">no</span><span class="sxs-lookup"><span data-stu-id="749c2-338">no</span></span>         |
|<span data-ttu-id="749c2-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-339">Outlook</span></span>         |<span data-ttu-id="749c2-340">no</span><span class="sxs-lookup"><span data-stu-id="749c2-340">no</span></span>         |
|<span data-ttu-id="749c2-341">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-342">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-342">not applicable</span></span>           |
|<span data-ttu-id="749c2-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-343">Exchange</span></span>         |<span data-ttu-id="749c2-344">no</span><span class="sxs-lookup"><span data-stu-id="749c2-344">no</span></span>       |
|<span data-ttu-id="749c2-345">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-345">AIP unified client</span></span>         |<span data-ttu-id="749c2-346">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-346">yes</span></span>            |
|<span data-ttu-id="749c2-347">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-347">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-348">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-348">not applicable</span></span>         |
|<span data-ttu-id="749c2-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-349">MIP SDK</span></span>         |<span data-ttu-id="749c2-350">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-350">yes</span></span>            |
|<span data-ttu-id="749c2-351">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-351">RMS service</span></span>         |<span data-ttu-id="749c2-352">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-352">not applicable</span></span>         |
|<span data-ttu-id="749c2-353">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-354">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-354">not applicable</span></span>            |
|<span data-ttu-id="749c2-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-355">MCAS</span></span>     |<span data-ttu-id="749c2-356">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-356">not applicable</span></span>        |

## <a name="sensitivity-label-protection-removed"></a><span data-ttu-id="749c2-357">ラベルの保護が削除された</span><span class="sxs-lookup"><span data-stu-id="749c2-357">Sensitivity label protection removed</span></span>

<span data-ttu-id="749c2-358">このイベントは、ラベルのないドキュメントの保護が手動で変更される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="749c2-359">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-359">Source</span></span>  |<span data-ttu-id="749c2-360">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="749c2-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="749c2-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="749c2-362">no</span><span class="sxs-lookup"><span data-stu-id="749c2-362">no</span></span>         |
|<span data-ttu-id="749c2-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="749c2-363">Outlook</span></span>         |<span data-ttu-id="749c2-364">no</span><span class="sxs-lookup"><span data-stu-id="749c2-364">no</span></span>         |
|<span data-ttu-id="749c2-365">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="749c2-366">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-366">not applicable</span></span>           |
|<span data-ttu-id="749c2-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-367">Exchange</span></span>         |<span data-ttu-id="749c2-368">no</span><span class="sxs-lookup"><span data-stu-id="749c2-368">no</span></span>       |
|<span data-ttu-id="749c2-369">AIP 統合クライアント</span><span class="sxs-lookup"><span data-stu-id="749c2-369">AIP unified client</span></span>         |<span data-ttu-id="749c2-370">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-370">yes</span></span>            |
|<span data-ttu-id="749c2-371">AIP 統合スキャナー</span><span class="sxs-lookup"><span data-stu-id="749c2-371">AIP unified scanner</span></span>         |<span data-ttu-id="749c2-372">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-372">not applicable</span></span>         |
|<span data-ttu-id="749c2-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="749c2-373">MIP SDK</span></span>         |<span data-ttu-id="749c2-374">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-374">yes</span></span>            |
|<span data-ttu-id="749c2-375">RMS サービス</span><span class="sxs-lookup"><span data-stu-id="749c2-375">RMS service</span></span>         |<span data-ttu-id="749c2-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-376">not applicable</span></span>         |
|<span data-ttu-id="749c2-377">Power BI デスクトップと Web</span><span class="sxs-lookup"><span data-stu-id="749c2-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="749c2-378">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-378">not applicable</span></span>            |
|<span data-ttu-id="749c2-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-379">MCAS</span></span>     |<span data-ttu-id="749c2-380">該当なし</span><span class="sxs-lookup"><span data-stu-id="749c2-380">not applicable</span></span>        |

## <a name="sensitivity-label-dlp-policy-matched"></a><span data-ttu-id="749c2-381">一致した感度ラベル DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="749c2-381">Sensitivity label DLP policy matched</span></span>

<span data-ttu-id="749c2-382">このイベントは、DLP ポリシーが一致する度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-382">This event is generated each time a DLP policy is matched.</span></span>

|<span data-ttu-id="749c2-383">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-383">Source</span></span>  |<span data-ttu-id="749c2-384">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="749c2-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-385">Exchange</span></span>         |<span data-ttu-id="749c2-386">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-386">yes</span></span>       |
|<span data-ttu-id="749c2-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="749c2-387">SharePoint Online</span></span>|<span data-ttu-id="749c2-388">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-388">yes</span></span>          |
|<span data-ttu-id="749c2-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-389">OneDrive</span></span> |<span data-ttu-id="749c2-390">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-390">yes</span></span>|
|<span data-ttu-id="749c2-391">Teams</span><span class="sxs-lookup"><span data-stu-id="749c2-391">Teams</span></span> |<span data-ttu-id="749c2-392">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-392">yes</span></span>   |
|<span data-ttu-id="749c2-393">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="749c2-393">Windows 10 devices</span></span>         |<span data-ttu-id="749c2-394">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-394">yes</span></span> |
|<span data-ttu-id="749c2-395">MAC</span><span class="sxs-lookup"><span data-stu-id="749c2-395">MAC</span></span>         |<span data-ttu-id="749c2-396">no</span><span class="sxs-lookup"><span data-stu-id="749c2-396">no</span></span>     |
|<span data-ttu-id="749c2-397">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="749c2-397">on-premises</span></span>         |<span data-ttu-id="749c2-398">no</span><span class="sxs-lookup"><span data-stu-id="749c2-398">no</span></span>|
|<span data-ttu-id="749c2-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="749c2-399">MCAS</span></span>     |<span data-ttu-id="749c2-400">no</span><span class="sxs-lookup"><span data-stu-id="749c2-400">no</span></span>        | 

<span data-ttu-id="749c2-401">Windows 10 デバイス (エンドポイント DLP) のイベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="749c2-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="749c2-402">ファイルが削除されました</span><span class="sxs-lookup"><span data-stu-id="749c2-402">file deleted</span></span>
- <span data-ttu-id="749c2-403">作成されたファイル</span><span class="sxs-lookup"><span data-stu-id="749c2-403">file created</span></span>
- <span data-ttu-id="749c2-404">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="749c2-404">file copied to clipboard</span></span>
- <span data-ttu-id="749c2-405">変更されたファイル</span><span class="sxs-lookup"><span data-stu-id="749c2-405">file modified</span></span>
- <span data-ttu-id="749c2-406">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="749c2-406">file read</span></span>
- <span data-ttu-id="749c2-407">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="749c2-407">file printed</span></span>
- <span data-ttu-id="749c2-408">ファイルの名前が変更されました</span><span class="sxs-lookup"><span data-stu-id="749c2-408">file renamed</span></span>
- <span data-ttu-id="749c2-409">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="749c2-409">file copied to network share</span></span>
- <span data-ttu-id="749c2-410">許可されていないアプリによってアクセスされるファイル</span><span class="sxs-lookup"><span data-stu-id="749c2-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="749c2-411">アイテム保持ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="749c2-411">Retention label applied</span></span> 

<span data-ttu-id="749c2-412">このイベントは、ラベル付けされていないドキュメントにラベルが付いた場合や、ラベル付きメールが送信される度に生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-412">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span>

- <span data-ttu-id="749c2-413">これは、ネイティブ アプリケーションおよび Web アプリケーションOffice保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-413">It is captured at the time of save in Office native applications and web applications.</span></span>

|<span data-ttu-id="749c2-414">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-414">Source</span></span>  |<span data-ttu-id="749c2-415">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="749c2-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-416">Exchange</span></span>         |<span data-ttu-id="749c2-417">no</span><span class="sxs-lookup"><span data-stu-id="749c2-417">no</span></span>       |
|<span data-ttu-id="749c2-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="749c2-418">SharePoint Online</span></span>|<span data-ttu-id="749c2-419">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-419">yes</span></span>          |
|<span data-ttu-id="749c2-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-420">OneDrive</span></span> |<span data-ttu-id="749c2-421">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="749c2-422">アイテム保持ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="749c2-422">Retention label changed</span></span>

<span data-ttu-id="749c2-423">このイベントは、ドキュメントまたは電子メールでラベルが更新されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="749c2-424">保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-424">It is captured at the time of save.</span></span>

|<span data-ttu-id="749c2-425">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-425">Source</span></span>  |<span data-ttu-id="749c2-426">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="749c2-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-427">Exchange</span></span>         |<span data-ttu-id="749c2-428">no</span><span class="sxs-lookup"><span data-stu-id="749c2-428">no</span></span>       |
|<span data-ttu-id="749c2-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="749c2-429">SharePoint Online</span></span>|<span data-ttu-id="749c2-430">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-430">yes</span></span>          |
|<span data-ttu-id="749c2-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-431">OneDrive</span></span> |<span data-ttu-id="749c2-432">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="749c2-433">アイテム保持ラベルの削除</span><span class="sxs-lookup"><span data-stu-id="749c2-433">Retention label removed</span></span>

<span data-ttu-id="749c2-434">このイベントは、ファイルまたはドキュメントからラベルが削除されるごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="749c2-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="749c2-435">保存時にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="749c2-435">It is captured at the time of save.</span></span>

|<span data-ttu-id="749c2-436">ソース</span><span class="sxs-lookup"><span data-stu-id="749c2-436">Source</span></span>  |<span data-ttu-id="749c2-437">アクティビティ エクスプローラーで報告される</span><span class="sxs-lookup"><span data-stu-id="749c2-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="749c2-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="749c2-438">Exchange</span></span>         |<span data-ttu-id="749c2-439">no</span><span class="sxs-lookup"><span data-stu-id="749c2-439">no</span></span>       |
|<span data-ttu-id="749c2-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="749c2-440">SharePoint Online</span></span>|<span data-ttu-id="749c2-441">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-441">yes</span></span>          |
|<span data-ttu-id="749c2-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="749c2-442">OneDrive</span></span> |<span data-ttu-id="749c2-443">はい</span><span class="sxs-lookup"><span data-stu-id="749c2-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="749c2-444">既知の問題</span><span class="sxs-lookup"><span data-stu-id="749c2-444">Known issues</span></span>
  
- <span data-ttu-id="749c2-445">推奨ラベル ツール ヒントがエンド ユーザーに表示されている場合、そのヒントはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="749c2-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="749c2-446">ただし、ユーザーが推奨ラベルの適用を選択した場合、ラベルは [適用方法] フィールドの下に [推奨]*として表示\*\*されます。*</span><span class="sxs-lookup"><span data-stu-id="749c2-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="749c2-447">現在、Sharepoint と OneDrive からの感度ラベルのダウングレードでは、位置合わせテキストを使用できません。</span><span class="sxs-lookup"><span data-stu-id="749c2-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="749c2-448">機密情報の種類は現在、Word、Excel、PowerPoint、Outlook、SharePoint Online、OneDrive の自動ラベル付けアクティビティでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="749c2-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
